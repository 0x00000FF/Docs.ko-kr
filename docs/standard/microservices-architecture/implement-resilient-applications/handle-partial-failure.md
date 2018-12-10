---
title: 부분 실패 처리
description: '컨테이너화된 .NET 응용 프로그램용 .NET 마이크로 서비스 아키텍처 | 부분 실패 처리 '
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 06/08/2018
ms.openlocfilehash: 94239fc30292760b2bb28849f8c6ab72c7ceb33d
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/10/2018
ms.locfileid: "53144730"
---
# <a name="handling-partial-failure"></a><span data-ttu-id="f7d18-103">부분 실패 처리</span><span class="sxs-lookup"><span data-stu-id="f7d18-103">Handling partial failure</span></span>

<span data-ttu-id="f7d18-104">마이크로 서비스 기반 응용 프로그램과 같은 분산 시스템에서는 부분적으로 실패할 위험이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f7d18-104">In distributed systems like microservices-based applications, there is an ever-present risk of partial failure.</span></span> <span data-ttu-id="f7d18-105">예를 들어, 단일 마이크로 서비스/컨테이너가 실패하거나 짧은 시간 동안 응답하지 못할 수 있으며 단일 VM 또는 서버가 충돌될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f7d18-105">For instance, a single microservice/container can fail or might not be available to respond for a short time, or a single VM or server can crash.</span></span> <span data-ttu-id="f7d18-106">클라이언트와 서비스는 별도의 프로세스이기 때문에 서비스가 클라이언트의 요청에 적시에 응답하지 못할 수 있습니다. </span><span class="sxs-lookup"><span data-stu-id="f7d18-106">Since clients and services are separate processes, a service might not be able to respond in a timely way to a client’s request.</span></span> <span data-ttu-id="f7d18-107">서비스가 오버로드되고 요청에 매우 느리게 응답할 수 있거나, 네트워크 문제로 인해 짧은 시간 동안 액세스하지 못할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f7d18-107">The service might be overloaded and responding extremely slowly to requests or might simply not be accessible for a short time because of network issues.</span></span>

<span data-ttu-id="f7d18-108">예를 들어, eShopOnContainers 샘플 응용 프로그램의 주문 세부 정보 페이지를 고려하세요.</span><span class="sxs-lookup"><span data-stu-id="f7d18-108">For example, consider the Order details page from the eShopOnContainers sample application.</span></span> <span data-ttu-id="f7d18-109">사용자가 주문을 제출할 때 순서 마이크로 서비스가 응답하지 않으면 클라이언트 프로세스(MVC 웹 응용 프로그램)의 잘못된 구현은 - 예를 들어, 클라이언트 코드가 시간 제한없이 동기 RPC를 사용하는 경우 - 스레드가 응답을 무기한 대기하는 것을 차단합니다.</span><span class="sxs-lookup"><span data-stu-id="f7d18-109">If the ordering microservice is unresponsive when the user tries to submit an order, a bad implementation of the client process (the MVC web application)—for example, if the client code were to use synchronous RPCs with no timeout—would block threads indefinitely waiting for a response.</span></span> <span data-ttu-id="f7d18-110">안 좋은 사용자 환경을 만드는 것 외에도, 모든 응답이 없는 대기는 스레드를 소비하거나 차단하며, 스레드는 확장성이 뛰어난 응용 프로그램에서 매우 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="f7d18-110">In addition to creating a bad user experience, every unresponsive wait consumes or blocks a thread, and threads are extremely valuable in highly scalable applications.</span></span> <span data-ttu-id="f7d18-111">차단된 스레드가 많으면 결국 응용 프로그램의 런타임에 스레드가 부족할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f7d18-111">If there are many blocked threads, eventually the application’s runtime can run out of threads.</span></span> <span data-ttu-id="f7d18-112">이 경우에, 응용 프로그램은 그림 10-1과 같이, 부분적으로 응답하지 않는 대신 전체적으로 응답하지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f7d18-112">In that case, the application can become globally unresponsive instead of just partially unresponsive, as show in Figure 10-1.</span></span>

![](./media/image1.png)

<span data-ttu-id="f7d18-113">**그림 10-1**.</span><span class="sxs-lookup"><span data-stu-id="f7d18-113">**Figure 10-1**.</span></span> <span data-ttu-id="f7d18-114">서비스 스레드 가용성에 영향을 주는 종속성으로 인해 일부 실패합니다.</span><span class="sxs-lookup"><span data-stu-id="f7d18-114">Partial failures because of dependencies that impact service thread availability</span></span>

<span data-ttu-id="f7d18-115">대규모 마이크로 서비스 기반 응용 프로그램에서 부분 실패는 특히 내부 마이크로 서비스 상호 작용의 대부분이 동기식 HTTP 호출(이것은 안티 패턴으로 간주됨)에 기반하여 증폭될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f7d18-115">In a large microservices-based application, any partial failure can be amplified, especially if most of the internal microservices interaction is based on synchronous HTTP calls (which is considered an anti-pattern).</span></span> <span data-ttu-id="f7d18-116">하루에 수백만 건의 수신 호출을 받는 시스템에 대해 생각해 봅니다.</span><span class="sxs-lookup"><span data-stu-id="f7d18-116">Think about a system that receives millions of incoming calls per day.</span></span> <span data-ttu-id="f7d18-117">시스템이 동기식 HTTP 호출의 긴 체인을 기반으로 하는 잘못된 디자인인 경우, 이러한 수신 호출은 동기 종속성으로 수십 개의 내부 마이크로 서비스와 수백만 건의 발신 호출(1:4 비율로 가정)이 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f7d18-117">If your system has a bad design that is based on long chains of synchronous HTTP calls, these incoming calls might result in many more millions of outgoing calls (let’s suppose a ratio of 1:4) to dozens of internal microservices as synchronous dependencies.</span></span> <span data-ttu-id="f7d18-118">이 상황은 그림 10-2, 특히 종속성 \#3에 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f7d18-118">This situation is shown in Figure 10-2, especially dependency \#3.</span></span>

![](./media/image2.png)

<span data-ttu-id="f7d18-119">**그림 10-2**.</span><span class="sxs-lookup"><span data-stu-id="f7d18-119">**Figure 10-2**.</span></span> <span data-ttu-id="f7d18-120">HTTP 요청의 긴 체인을 특징으로 하는 잘못된 디자인의 영향</span><span class="sxs-lookup"><span data-stu-id="f7d18-120">The impact of having an incorrect design featuring long chains of HTTP requests</span></span>

<span data-ttu-id="f7d18-121">모든 종속성 자체에 우수한 가용성이 있더라도 클라우드 기반 분산 시스템에서는 일시적인 실패가 보장됩니다.</span><span class="sxs-lookup"><span data-stu-id="f7d18-121">Intermittent failure is guaranteed in a distributed and cloud-based system, even if every dependency itself has excellent availability.</span></span> <span data-ttu-id="f7d18-122">이는 실제로 고려해야 할 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="f7d18-122">It is fact you need to consider.</span></span>

<span data-ttu-id="f7d18-123">내결함성을 보장하는 기술을 디자인하고 구현하지 않으면, 작은 가동 중지 시간이 증폭될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f7d18-123">If you do not design and implement techniques to ensure fault tolerance, even small downtimes can be amplified.</span></span> <span data-ttu-id="f7d18-124">예를 들어 가용성이 99.99%인 각각 50개의 종속성은 이 파급 효과 때문에 매월 몇 시간의 가동 중지 시간을 초래합니다.</span><span class="sxs-lookup"><span data-stu-id="f7d18-124">As an example, 50 dependencies each with 99.99% of availability would result in several hours of downtime each month because of this ripple effect.</span></span> <span data-ttu-id="f7d18-125">대용량의 요청을 처리하는 동안 마이크로 서비스 종속성이 실패하면, 실패로 인해 각 서비스의 사용 가능한 모든 요청 스레드가 빠르게 포화되어 전체 응용 프로그램이 손상될 수 있습니다. </span><span class="sxs-lookup"><span data-stu-id="f7d18-125">When a microservice dependency fails while handling a high volume of requests, that failure can quickly saturate all available request threads in each service and crash the whole application.</span></span>

![](./media/image3.png)

<span data-ttu-id="f7d18-126">**그림 10-3**.</span><span class="sxs-lookup"><span data-stu-id="f7d18-126">**Figure 10-3**.</span></span> <span data-ttu-id="f7d18-127">동기식 HTTP 호출의 긴 체인이 있는 마이크로 서비스에 의해 증폭된 부분 실패</span><span class="sxs-lookup"><span data-stu-id="f7d18-127">Partial failure amplified by microservices with long chains of synchronous HTTP calls</span></span>

<span data-ttu-id="f7d18-128">이 문제를 최소화하려면 "*비동기식 마이크로 서비스 통합 적용 마이크로 서비스의 자율성*"(아키텍처 챕터) 섹션에서 이 지침은 내부 마이크 서비스 전반에 걸쳐 비동기 통신을 사용하도록 권장하고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f7d18-128">To minimize this problem, in the section "*Asynchronous microservice integration enforce microservice’s autonomy*” (in the architecture chapter), this guidance encourages you to use asynchronous communication across the internal microservices.</span></span> 

<span data-ttu-id="f7d18-129">또한 마이크로 서비스 및 클라이언트 응용 프로그램을 디자인하여 부분 실패를 처리하는 것이 중요합니다. 즉, 복원력 있는 마이크로 서비스 및 클라이언트 응용 프로그램을 구축하는 것입니다. </span><span class="sxs-lookup"><span data-stu-id="f7d18-129">In addition, it is essential that you design your microservices and client applications to handle partial failures—that is, to build resilient microservices and client applications.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="f7d18-130">[이전](index.md)
>[다음](partial-failure-strategies.md)</span><span class="sxs-lookup"><span data-stu-id="f7d18-130">[Previous](index.md)
[Next](partial-failure-strategies.md)</span></span>