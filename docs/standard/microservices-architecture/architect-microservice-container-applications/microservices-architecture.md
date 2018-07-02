---
title: 마이크로 서비스 아키텍처
description: 컨테이너화된 .NET 응용 프로그램을 위한 .NET 마이크로 서비스 아키텍처 | 마이크로 서비스 아키텍처
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.openlocfilehash: e41544a7c5f352321c3fa3e61a71568a6cf0f219
ms.sourcegitcommit: 979597cd8055534b63d2c6ee8322938a27d0c87b
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/29/2018
ms.locfileid: "37106686"
---
# <a name="microservices-architecture"></a><span data-ttu-id="38374-103">마이크로 서비스 아키텍처</span><span class="sxs-lookup"><span data-stu-id="38374-103">Microservices architecture</span></span>

<span data-ttu-id="38374-104">이름에서 알 수 있듯이 마이크로 서비스 아키텍처는 작은 서비스의 집합인 서버 응용 프로그램을 빌드하는 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="38374-104">As the name implies, a microservices architecture is an approach to building a server application as a set of small services.</span></span> <span data-ttu-id="38374-105">각 서비스는 자체 프로세스에서 실행되며 HTTP/HTTPS, WebSockets 또는 [AMQP](https://en.wikipedia.org/wiki/Advanced_Message_Queuing_Protocol)와 같은 프로토콜을 사용하여 다른 프로세스와 통신합니다.</span><span class="sxs-lookup"><span data-stu-id="38374-105">Each service runs in its own process and communicates with other processes using protocols such as HTTP/HTTPS, WebSockets, or [AMQP](https://en.wikipedia.org/wiki/Advanced_Message_Queuing_Protocol).</span></span> <span data-ttu-id="38374-106">각 마이크로 서비스는 특정 컨텍스트 경계 내에서 특정 종단 간 도메인이나 비즈니스 기능을 구현하고 자율적으로 개발되고 독립적으로 배포될 수 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="38374-106">Each microservice implements a specific end-to-end domain or business capability within a certain context boundary, and each must be developed autonomously and be deployable independently.</span></span> <span data-ttu-id="38374-107">마지막으로 각 마이크로 서비스는 다양한 데이터 저장소 기술(SQL, NoSQL) 및 프로그래밍 언어에 따라 관련 도메인 데이터 모델과 도메인 논리(주권 및 분산 데이터 관리)를 소유해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="38374-107">Finally, each microservice should own its related domain data model and domain logic (sovereignty and decentralized data management) based on different data storage technologies (SQL, NoSQL) and different programming languages.</span></span>

<span data-ttu-id="38374-108">마이크로 서비스의 크기는 얼마여야 하나요?</span><span class="sxs-lookup"><span data-stu-id="38374-108">What size should a microservice be?</span></span> <span data-ttu-id="38374-109">마이크로 서비스를 개발하는 경우 크기는 중요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="38374-109">When developing a microservice, size should not be the important point.</span></span> <span data-ttu-id="38374-110">대신 중요한 점은 각 서비스에 대해 개발, 배포 및 크기 조정의 자율성을 갖도록 느슨하게 결합된 서비스를 만드는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="38374-110">Instead, the important point should be to create loosely coupled services so you have autonomy of development, deployment, and scale, for each service.</span></span> <span data-ttu-id="38374-111">물론 마이크로 서비스를 식별하고 디자인하는 경우 다른 마이크로 서비스에서 과도한 직접 종속성이 없다면 가능한 작게 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="38374-111">Of course, when identifying and designing microservices, you should try to make them as small as possible as long as you do not have too many direct dependencies with other microservices.</span></span> <span data-ttu-id="38374-112">마이크로 서비스의 크기보다 중요한 점은 내부 응집력 및 다른 서비스로부터의 독립성입니다.</span><span class="sxs-lookup"><span data-stu-id="38374-112">More important than the size of the microservice is the internal cohesion it must have and its independence from other services.</span></span>

<span data-ttu-id="38374-113">마이크로 서비스 아키텍처를 사용하는 이유는 무엇인가요?</span><span class="sxs-lookup"><span data-stu-id="38374-113">Why a microservices architecture?</span></span> <span data-ttu-id="38374-114">즉, 장기 유연성을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="38374-114">In short, it provides long-term agility.</span></span> <span data-ttu-id="38374-115">마이크로 서비스를 사용하면 세부적이고 자율적인 수명 주기를 포함하는 많은 독립적으로 배포 가능한 서비스에 기반한 응용 프로그램을 만들 수 있도록 하여 복잡한 대규모의 확장성이 뛰어난 시스템에서 유지 관리 기능을 향상시킬 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="38374-115">Microservices enable better maintainability in complex, large, and highly-scalable systems by letting you create applications based on many independently deployable services that each have granular and autonomous lifecycles.</span></span>

<span data-ttu-id="38374-116">추가 이점으로 마이크로 서비스를 독립적으로 확장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="38374-116">As an additional benefit, microservices can scale out independently.</span></span> <span data-ttu-id="38374-117">단위로 확장해야 하는 단일 모놀리식 응용 프로그램 대신 특정 마이크로 서비스를 확장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="38374-117">Instead of having a single monolithic application that you must scale out as a unit, you can instead scale out specific microservices.</span></span> <span data-ttu-id="38374-118">이런 방식으로 확장해야 하는 응용 프로그램의 다른 영역을 확장하지 않고 추가 처리 기능이 필요한 기능 영역 또는 요청을 지원하는 네트워크 대역폭을 확장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="38374-118">That way, you can scale just the functional area that needs more processing power or network bandwidth to support demand, rather than scaling out other areas of the application that do not need to be scaled.</span></span> <span data-ttu-id="38374-119">즉, 하드웨어를 적게 사용하기 때문에 비용이 절감됩니다.</span><span class="sxs-lookup"><span data-stu-id="38374-119">That means cost savings because you need less hardware.</span></span>

![](./media/image6.png)

<span data-ttu-id="38374-120">**그림 4-6**</span><span class="sxs-lookup"><span data-stu-id="38374-120">**Figure 4-6**.</span></span> <span data-ttu-id="38374-121">모놀리식 배포 대 마이크로 서비스 접근 방식</span><span class="sxs-lookup"><span data-stu-id="38374-121">Monolithic deployment versus the microservices approach</span></span>

<span data-ttu-id="38374-122">그림 4-6에서 볼 수 있듯이 마이크로 서비스 접근 방식을 사용하면 복잡한 대규모의 확장 가능한 응용 프로그램의 작은 특정 영역을 변경할 수 있기 때문에 각 마이크로 서비스를 신속하게 변경하고 반복할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="38374-122">As Figure 4-6 shows, the microservices approach allows agile changes and rapid iteration of each microservice, because you can change specific, small areas of complex, large, and scalable applications.</span></span>

<span data-ttu-id="38374-123">세분화된 마이크로 서비스 기반 응용 프로그램을 구축하는 작업은 연속 통합 및 지속적인 업데이트 사례를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="38374-123">Architecting fine-grained microservices-based applications enables continuous integration and continuous delivery practices.</span></span> <span data-ttu-id="38374-124">또한 응용 프로그램이 새 기능을 사용하도록 가속화합니다.</span><span class="sxs-lookup"><span data-stu-id="38374-124">It also accelerates delivery of new functions into the application.</span></span> <span data-ttu-id="38374-125">응용 프로그램의 세분화된 컴퍼지션을 사용하면 격리된 마이크로 서비스를 실행하고 테스트하며, 해당 서비스 간에 지우기 계약을 유지하면서 자율적으로 변경할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="38374-125">Fine-grained composition of applications also allows you to run and test microservices in isolation, and to evolve them autonomously while maintaining clear contracts between them.</span></span> <span data-ttu-id="38374-126">인터페이스 또는 계약을 변경하지 않으면 다른 마이크로 서비스를 중단하지 않고 마이크로 서비스의 내부 구현을 변경하거나 새 기능을 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="38374-126">As long as you do not change the interfaces or contracts, you can change the internal implementation of any microservice or add new functionality without breaking other microservices.</span></span>

<span data-ttu-id="38374-127">마이크로 서비스 기반 시스템을 사용하여 프로덕션에 성공할 수 있는 중요한 측면은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="38374-127">The following are important aspects to enable success in going into production with a microservices-based system:</span></span>

-   <span data-ttu-id="38374-128">서비스와 인프라의 모니터링 및 상태 검사</span><span class="sxs-lookup"><span data-stu-id="38374-128">Monitoring and health checks of the services and infrastructure.</span></span>

-   <span data-ttu-id="38374-129">서비스에 대한 확장성 있는 인프라(즉, 클라우드 및 오케스트레이터)</span><span class="sxs-lookup"><span data-stu-id="38374-129">Scalable infrastructure for the services (that is, cloud and orchestrators).</span></span>

-   <span data-ttu-id="38374-130">여러 수준의 보안 설계 및 구현: 인증, 권한 부여, 암호 관리, 보안 통신 등</span><span class="sxs-lookup"><span data-stu-id="38374-130">Security design and implementation at multiple levels: authentication, authorization, secrets management, secure communication, etc.</span></span>

-   <span data-ttu-id="38374-131">일반적으로 다양한 마이크로 서비스에 중점을 두고 다양한 팀과 함께 신속한 응용 프로그램 배달</span><span class="sxs-lookup"><span data-stu-id="38374-131">Rapid application delivery, usually with different teams focusing on different microservices.</span></span>

-   <span data-ttu-id="38374-132">DevOps 및 CI/CD 사례 및 인프라</span><span class="sxs-lookup"><span data-stu-id="38374-132">DevOps and CI/CD practices and infrastructure.</span></span>

<span data-ttu-id="38374-133">이 중에서 처음 3개만을 이 가이드에서 다루거나 소개합니다.</span><span class="sxs-lookup"><span data-stu-id="38374-133">Of these, only the first three are covered or introduced in this guide.</span></span> <span data-ttu-id="38374-134">응용 프로그램 수명 주기와 관련된 마지막 두 가지는 추가 [Microsoft 플랫폼 및 도구를 사용하여 컨테이너화된 Docker 응용 프로그램 수명 주기](https://aka.ms/dockerlifecycleebook) 전자책에서 다룹니다.</span><span class="sxs-lookup"><span data-stu-id="38374-134">The last two points, which are related to application lifecycle, are covered in the additional [Containerized Docker Application Lifecycle with Microsoft Platform and Tools](https://aka.ms/dockerlifecycleebook) e-book.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="38374-135">추가 자료</span><span class="sxs-lookup"><span data-stu-id="38374-135">Additional resources</span></span>

-   <span data-ttu-id="38374-136">**Mark Russinovich 마이크로 서비스: 클라우드 기반의 응용 프로그램 혁명**
    [*https://azure.microsoft.com/blog/microservices-an-application-revolution-powered-by-the-cloud/*](https://azure.microsoft.com/blog/microservices-an-application-revolution-powered-by-the-cloud/)</span><span class="sxs-lookup"><span data-stu-id="38374-136">**Mark Russinovich. Microservices: An application revolution powered by the cloud**
[*https://azure.microsoft.com/blog/microservices-an-application-revolution-powered-by-the-cloud/*](https://azure.microsoft.com/blog/microservices-an-application-revolution-powered-by-the-cloud/)</span></span>

-   <span data-ttu-id="38374-137">**Martin Fowler. 마이크로 서비스**
    [*https://www.martinfowler.com/articles/microservices.html*](https://www.martinfowler.com/articles/microservices.html)</span><span class="sxs-lookup"><span data-stu-id="38374-137">**Martin Fowler. Microservices**
[*https://www.martinfowler.com/articles/microservices.html*](https://www.martinfowler.com/articles/microservices.html)</span></span>

-   <span data-ttu-id="38374-138">**Martin Fowler. 마이크로 서비스 필수 구성 요소**
    [*https://martinfowler.com/bliki/MicroservicePrerequisites.html*](https://martinfowler.com/bliki/MicroservicePrerequisites.html)</span><span class="sxs-lookup"><span data-stu-id="38374-138">**Martin Fowler. Microservice Prerequisites**
[*https://martinfowler.com/bliki/MicroservicePrerequisites.html*](https://martinfowler.com/bliki/MicroservicePrerequisites.html)</span></span>

-   <span data-ttu-id="38374-139">**Jimmy Nilsson. 청크 클라우드 컴퓨팅**
    [*https://www.infoq.com/articles/CCC-Jimmy-Nilsson*](https://www.infoq.com/articles/CCC-Jimmy-Nilsson)</span><span class="sxs-lookup"><span data-stu-id="38374-139">**Jimmy Nilsson. Chunk Cloud Computing**
[*https://www.infoq.com/articles/CCC-Jimmy-Nilsson*](https://www.infoq.com/articles/CCC-Jimmy-Nilsson)</span></span>

-   <span data-ttu-id="38374-140">**Cesar de la Torre. Microsoft 플랫폼 및 도구를 사용하여 컨테이너화된 Docker 응용 프로그램 수명 주기**(다운로드 가능한 전자책) [*https://aka.ms/dockerlifecycleebook*](https://aka.ms/dockerlifecycleebook)</span><span class="sxs-lookup"><span data-stu-id="38374-140">**Cesar de la Torre. Containerized Docker Application Lifecycle with Microsoft Platform and Tools** (downloadable e-book) [*https://aka.ms/dockerlifecycleebook*](https://aka.ms/dockerlifecycleebook)</span></span>




>[!div class="step-by-step"]
<span data-ttu-id="38374-141">[이전](service-oriented-architecture.md)
[다음](data-sovereignty-per-microservice.md)</span><span class="sxs-lookup"><span data-stu-id="38374-141">[Previous](service-oriented-architecture.md)
[Next](data-sovereignty-per-microservice.md)</span></span>
