---
title: "마이크로 서비스 아키텍처"
description: "컨테이너 화 된.NET 응용 프로그램에 대 한.NET Microservices 아키텍처 | Microservices 아키텍처"
keywords: "Docker, 마이크로 서비스, ASP.NET, 컨테이너"
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.openlocfilehash: 5ede1f0ad19270ca6b7556ff1bb7e4cf8ccf7cbe
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="microservices-architecture"></a><span data-ttu-id="94031-104">마이크로 서비스 아키텍처</span><span class="sxs-lookup"><span data-stu-id="94031-104">Microservices architecture</span></span>

<span data-ttu-id="94031-105">이름에서 알 수 있듯이 microservices 아키텍처는 작은 서비스 집합으로는 서버 응용 프로그램을 빌드하기 위한 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="94031-105">As the name implies, a microservices architecture is an approach to building a server application as a set of small services.</span></span> <span data-ttu-id="94031-106">각 서비스는 자체 프로세스에서 실행 되며 WebSockets, HTTP/HTTPS 같은 프로토콜을 사용 하 여 다른 프로세스와 통신 또는 [AMQP](https://en.wikipedia.org/wiki/Advanced_Message_Queuing_Protocol)합니다.</span><span class="sxs-lookup"><span data-stu-id="94031-106">Each service runs in its own process and communicates with other processes using protocols such as HTTP/HTTPS, WebSockets, or [AMQP](https://en.wikipedia.org/wiki/Advanced_Message_Queuing_Protocol).</span></span> <span data-ttu-id="94031-107">특정 종단 간 도메인 이나 특정 컨텍스트 경계 내에서 비즈니스 기능을 구현 하는 각 마이크로 서비스 및 각 자치 적으로 개발 해야 하 고 독립적으로 배포할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="94031-107">Each microservice implements a specific end-to-end domain or business capability within a certain context boundary, and each must be developed autonomously and be deployable independently.</span></span> <span data-ttu-id="94031-108">마지막으로, 각 마이크로 서비스 관련된 도메인 데이터 모델과 다른 데이터 저장소 기술을 사용 (SQL, NoSQL) 및 다양 한 프로그래밍 언어에 따라 도메인 논리 (sovereignty 및 분산된 데이터 관리)를 소유 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="94031-108">Finally, each microservice should own its related domain data model and domain logic (sovereignty and decentralized data management) based on different data storage technologies (SQL, NoSQL) and different programming languages.</span></span>

<span data-ttu-id="94031-109">크기는 마이크로 서비스 해야 합니까?</span><span class="sxs-lookup"><span data-stu-id="94031-109">What size should a microservice be?</span></span> <span data-ttu-id="94031-110">마이크로 서비스를 개발 하는 경우 크기는 중요 한 점은 되지 않아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="94031-110">When developing a microservice, size should not be the important point.</span></span> <span data-ttu-id="94031-111">대신, 중요 한 점은 만들려는 느슨하게 결합 된 서비스 개발, 배포 및 각 서비스에 대 한 크기 조정의 자치 성을 갖도록 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="94031-111">Instead, the important point should be to create loosely coupled services so you have autonomy of development, deployment, and scale, for each service.</span></span> <span data-ttu-id="94031-112">물론, 식별 하 고 microservices 디자인 하는 경우에 않아도 다른 microservices와 너무 많은 직접 종속성으로 가능한 한 작게 만들 하려고 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="94031-112">Of course, when identifying and designing microservices, you should try to make them as small as possible as long as you do not have too many direct dependencies with other microservices.</span></span> <span data-ttu-id="94031-113">마이크로 서비스는 크기가 있어야 내부 응집력 및 다른 서비스에서 해당 독립성 보다 더 중요 합니다.</span><span class="sxs-lookup"><span data-stu-id="94031-113">More important than the size of the microservice is the internal cohesion it must have and its independence from other services.</span></span>

<span data-ttu-id="94031-114">이유는 microservices 아키텍처?</span><span class="sxs-lookup"><span data-stu-id="94031-114">Why a microservices architecture?</span></span> <span data-ttu-id="94031-115">즉, 장기 유연성을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="94031-115">In short, it provides long-term agility.</span></span> <span data-ttu-id="94031-116">Microservices 세부적인 및 자치 수명 주기에 포함 하는 많은 독립적으로 배포 가능한 서비스 기반 응용 프로그램을 만들 수 있도록 하 여 복잡 한 크고 확장성이 뛰어난 시스템에서 더 나은 유지 관리를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="94031-116">Microservices enable better maintainability in complex, large, and highly-scalable systems by letting you create applications based on many independently deployable services that each have granular and autonomous lifecycles.</span></span>

<span data-ttu-id="94031-117">추가 혜택으로 microservices 수 독립적으로 확장할 합니다.</span><span class="sxs-lookup"><span data-stu-id="94031-117">As an additional benefit, microservices can scale out independently.</span></span> <span data-ttu-id="94031-118">하나의 단위로 수평 확장 해야 하는 단일 모놀리식 응용 프로그램 대신 대신 특정 microservices 아웃 확장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="94031-118">Instead of having a single monolithic application that you must scale out as a unit, you can instead scale out specific microservices.</span></span> <span data-ttu-id="94031-119">이런 방식으로 더 많은 처리 전원 또는 네트워크 대역폭 크기를 조정할 수 필요 하지 않은 응용 프로그램의 다른 영역을 확장 하는 것이 아니라 요청을 지원 하기 위해 필요로 하는 기능 영역에 방금 확장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="94031-119">That way, you can scale just the functional area that needs more processing power or network bandwidth to support demand, rather than scaling out other areas of the application that do not need to be scaled.</span></span> <span data-ttu-id="94031-120">하드웨어가 덜 필요 하기 때문에 비용 절감 것입니다.</span><span class="sxs-lookup"><span data-stu-id="94031-120">That means cost savings because you need less hardware.</span></span>

![](./media/image6.png)

<span data-ttu-id="94031-121">**그림 4-6**합니다.</span><span class="sxs-lookup"><span data-stu-id="94031-121">**Figure 4-6**.</span></span> <span data-ttu-id="94031-122">모놀리식 배포 microservices 접근 방식 비교</span><span class="sxs-lookup"><span data-stu-id="94031-122">Monolithic deployment versus the microservices approach</span></span>

<span data-ttu-id="94031-123">그림 4-6에서 볼 수 있듯이 microservices 접근 방식을 사용 하면 agile 변경 내용 및 각 마이크로 서비스의 신속한 반복 있으므로 특정, 작은 복잡 하 고 확장 가능한 대형 응용 프로그램의 영역을 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="94031-123">As Figure 4-6 shows, the microservices approach allows agile changes and rapid iteration of each microservice, because you can change specific, small areas of complex, large, and scalable applications.</span></span>

<span data-ttu-id="94031-124">세분화 된 microservices 기반 응용 프로그램 사용에 대 한 연속 통합 및 지속적인 업데이트 방법을 설계 합니다.</span><span class="sxs-lookup"><span data-stu-id="94031-124">Architecting fine-grained microservices-based applications enables continuous integration and continuous delivery practices.</span></span> <span data-ttu-id="94031-125">또한 응용 프로그램에 새 함수의 배달을 가속화 됩니다.</span><span class="sxs-lookup"><span data-stu-id="94031-125">It also accelerates delivery of new functions into the application.</span></span> <span data-ttu-id="94031-126">세분화 된 컴퍼지션 응용 프로그램의 실행 및 격리 수준 microservices를 테스트 하 고 서로 지우기 계약을 유지 하면서 자율적으로 변경 하면 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="94031-126">Fine-grained composition of applications also allows you to run and test microservices in isolation, and to evolve them autonomously while maintaining clear contracts between them.</span></span> <span data-ttu-id="94031-127">인터페이스 또는 계약을 변경 하지 않는 상태로 모든 마이크로 서비스의 내부 구현 변경 하거나 다른 microservices 중단시 키 지 않고도 새 기능을 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="94031-127">As long as you do not change the interfaces or contracts, you can change the internal implementation of any microservice or add new functionality without breaking other microservices.</span></span>

<span data-ttu-id="94031-128">다음은 성공 microservices 기반 시스템으로 프로덕션 환경으로 옮기기에 사용할 수 있도록 중요 한 측면입니다.</span><span class="sxs-lookup"><span data-stu-id="94031-128">The following are important aspects to enable success in going into production with a microservices-based system:</span></span>

-   <span data-ttu-id="94031-129">서비스와 인프라의 모니터링 및 상태 검사 합니다.</span><span class="sxs-lookup"><span data-stu-id="94031-129">Monitoring and health checks of the services and infrastructure.</span></span>

-   <span data-ttu-id="94031-130">(즉, 클라우드 및 orchestrators) 서비스에 대 한 확장성 있는 인프라입니다.</span><span class="sxs-lookup"><span data-stu-id="94031-130">Scalable infrastructure for the services (that is, cloud and orchestrators).</span></span>

-   <span data-ttu-id="94031-131">보안 설계 및 여러 수준에서 구현: 인증, 권한 부여, 암호 관리, 보안 통신 등입니다.</span><span class="sxs-lookup"><span data-stu-id="94031-131">Security design and implementation at multiple levels: authentication, authorization, secrets management, secure communication, etc.</span></span>

-   <span data-ttu-id="94031-132">일반적으로 다른 microservices에 중점을 두기 하는 다른 팀과 신속한 응용 프로그램 배달</span><span class="sxs-lookup"><span data-stu-id="94031-132">Rapid application delivery, usually with different teams focusing on different microservices.</span></span>

-   <span data-ttu-id="94031-133">DevOps 및 CI/CD 사례 및 인프라를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="94031-133">DevOps and CI/CD practices and infrastructure.</span></span>

<span data-ttu-id="94031-134">이 중 처음 3 개 설명 또는이 가이드에서 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="94031-134">Of these, only the first three are covered or introduced in this guide.</span></span> <span data-ttu-id="94031-135">응용 프로그램 수명 주기 관련 된, 마지막 두 지점에는 추가에 대해서는 설명 [컨테이너 화 된 Docker 응용 프로그램 수명 주기 Microsoft 플랫폼 및 도구와](https://aka.ms/dockerlifecycleebook) 전자책 (영문) 합니다.</span><span class="sxs-lookup"><span data-stu-id="94031-135">The last two points, which are related to application lifecycle, are covered in the additional [Containerized Docker Application Lifecycle with Microsoft Platform and Tools](https://aka.ms/dockerlifecycleebook) e-book.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="94031-136">추가 리소스</span><span class="sxs-lookup"><span data-stu-id="94031-136">Additional resources</span></span>

-   <span data-ttu-id="94031-137">**Mark Russinovich 합니다. Microservices:는 응용 프로그램 revolution 클라우드가**
    [*https://azure.microsoft.com/blog/microservices-an-application-revolution-powered-by-the-cloud/*](https://azure.microsoft.com/blog/microservices-an-application-revolution-powered-by-the-cloud/)</span><span class="sxs-lookup"><span data-stu-id="94031-137">**Mark Russinovich. Microservices: An application revolution powered by the cloud**
[*https://azure.microsoft.com/blog/microservices-an-application-revolution-powered-by-the-cloud/*](https://azure.microsoft.com/blog/microservices-an-application-revolution-powered-by-the-cloud/)</span></span>

-   <span data-ttu-id="94031-138">**Martin Fowler. Microservices**
    [*http://www.martinfowler.com/articles/microservices.html*](http://www.martinfowler.com/articles/microservices.html)</span><span class="sxs-lookup"><span data-stu-id="94031-138">**Martin Fowler. Microservices**
[*http://www.martinfowler.com/articles/microservices.html*](http://www.martinfowler.com/articles/microservices.html)</span></span>

-   <span data-ttu-id="94031-139">**Martin Fowler. 마이크로 서비스 필수 구성 요소**
    [*http://martinfowler.com/bliki/MicroservicePrerequisites.html*](http://martinfowler.com/bliki/MicroservicePrerequisites.html)</span><span class="sxs-lookup"><span data-stu-id="94031-139">**Martin Fowler. Microservice Prerequisites**
[*http://martinfowler.com/bliki/MicroservicePrerequisites.html*](http://martinfowler.com/bliki/MicroservicePrerequisites.html)</span></span>

-   <span data-ttu-id="94031-140">**Jimmy Nilsson. 청크 클라우드 컴퓨팅**
    [*https://www.infoq.com/articles/CCC-Jimmy-Nilsson*](https://www.infoq.com/articles/CCC-Jimmy-Nilsson)</span><span class="sxs-lookup"><span data-stu-id="94031-140">**Jimmy Nilsson. Chunk Cloud Computing**
[*https://www.infoq.com/articles/CCC-Jimmy-Nilsson*](https://www.infoq.com/articles/CCC-Jimmy-Nilsson)</span></span>

-   <span data-ttu-id="94031-141">**Cesar de la Torre. Microsoft 플랫폼 및 도구와 응용 프로그램 수명 주기 Docker 컨테이너 화 된** (다운로드 가능한 전자책) [ *https://aka.ms/dockerlifecycleebook*](https://aka.ms/dockerlifecycleebook)</span><span class="sxs-lookup"><span data-stu-id="94031-141">**Cesar de la Torre. Containerized Docker Application Lifecycle with Microsoft Platform and Tools** (downloadable e-book) [*https://aka.ms/dockerlifecycleebook*](https://aka.ms/dockerlifecycleebook)</span></span>




>[!div class="step-by-step"]
<span data-ttu-id="94031-142">[이전] (서비스-지향-architecture.md) [다음] (데이터-sovereignty-당-microservice.md)</span><span class="sxs-lookup"><span data-stu-id="94031-142">[Previous] (service-oriented-architecture.md) [Next] (data-sovereignty-per-microservice.md)</span></span>
