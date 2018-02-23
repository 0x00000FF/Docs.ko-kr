---
title: "마이크로 서비스 응용 프로그램 레이어 및 웹 API 설계"
description: "컨테이너화된 .NET 응용 프로그램을 위한 .NET 마이크로 서비스 아키텍처 | 마이크로 서비스 응용 프로그램 레이어 및 웹 API 설계"
keywords: "Docker, 마이크로 서비스, ASP.NET, 컨테이너"
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 12/12/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: c166e0286d0769e24a6361037eb6c4694fb821ae
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/23/2017
---
# <a name="designing-the-microservice-application-layer-and-web-api"></a><span data-ttu-id="c9343-104">마이크로 서비스 응용 프로그램 레이어 및 웹 API 설계</span><span class="sxs-lookup"><span data-stu-id="c9343-104">Designing the microservice application layer and Web API</span></span>

## <a name="using-solid-principles-and-dependency-injection"></a><span data-ttu-id="c9343-105">SOLID 원칙 및 종속성 주입 사용</span><span class="sxs-lookup"><span data-stu-id="c9343-105">Using SOLID principles and Dependency Injection</span></span>

<span data-ttu-id="c9343-106">SOLID 원칙은 DDD 패턴을 통한 마이크로 서비스 개발처럼 현대적인 필수 응용 프로그램에서 사용되는 중요한 기법입니다.</span><span class="sxs-lookup"><span data-stu-id="c9343-106">SOLID principles are critical techniques to be used in any modern and mission-critical application, such as developing a microservice with DDD patterns.</span></span> <span data-ttu-id="c9343-107">SOLID는 5가지 기본 원칙을 묶은 머리글자어입니다.</span><span class="sxs-lookup"><span data-stu-id="c9343-107">SOLID is an acronym that groups five fundamental principles:</span></span>

-   <span data-ttu-id="c9343-108">Single Responsibility(단일 책임) 원칙</span><span class="sxs-lookup"><span data-stu-id="c9343-108">Single Responsibility principle</span></span>

-   <span data-ttu-id="c9343-109">Open/closed(개방/폐쇄) 원칙</span><span class="sxs-lookup"><span data-stu-id="c9343-109">Open/closed principle</span></span>

-   <span data-ttu-id="c9343-110">Liskov 대체 원칙</span><span class="sxs-lookup"><span data-stu-id="c9343-110">Liskov substitution principle</span></span>

-   <span data-ttu-id="c9343-111">Inversion Segregation(반전 분리) 원칙</span><span class="sxs-lookup"><span data-stu-id="c9343-111">Inversion Segregation principle</span></span>

-   <span data-ttu-id="c9343-112">Dependency Inversion(종속성 반전) 원칙</span><span class="sxs-lookup"><span data-stu-id="c9343-112">Dependency Inversion principle</span></span>

<span data-ttu-id="c9343-113">SOLID는 응용 프로그램 또는 마이크로 서비스 내부 계층을 설계하는 방식과 계층 간의 종속성을 분리하는 방법에 관한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="c9343-113">SOLID is more about how you design your application or microservice internal layers and about decoupling dependencies between them.</span></span> <span data-ttu-id="c9343-114">도메인이 아니라 응용 프로그램의 기술적 설계와 관련이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c9343-114">It is not related to the domain, but to the application’s technical design.</span></span> <span data-ttu-id="c9343-115">마지막 원칙인 DI(종속성 반전) 원칙에서는 인프라 계층을 나머지 계층과 분리하여 DDD 계층의 분리 구현을 향상시킬 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c9343-115">The final principle, the Dependency Inversion (DI) principle, allows you to decouple the infrastructure layer from the rest of the layers, which allows a better decoupled implementation of the DDD layers.</span></span>

<span data-ttu-id="c9343-116">DI는 종속성 반전 원칙을 구현하는 한 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="c9343-116">DI is one way to implement the Dependency Inversion principle.</span></span> <span data-ttu-id="c9343-117">개체와 그 종속성 간의 느슨한 결합을 실현하기 위한 기술입니다.</span><span class="sxs-lookup"><span data-stu-id="c9343-117">It is a technique for achieving loose coupling between objects and their dependencies.</span></span> <span data-ttu-id="c9343-118">협력자를 직접 인스턴스화하거나 고정 참조를 사용하는 대신 클래스가 해당 작업을 수행하기 위해 필요한 개체를 클래스에 제공(또는 "주입")합니다.</span><span class="sxs-lookup"><span data-stu-id="c9343-118">Rather than directly instantiating collaborators, or using static references, the objects that a class needs in order to perform its actions are provided to (or "injected into") the class.</span></span> <span data-ttu-id="c9343-119">대부분의 경우 클래스는 해당 생성자를 통해 해당 종속성을 선언하게 되며 명시적 종속성 원칙을 따르도록 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="c9343-119">Most often, classes will declare their dependencies via their constructor, allowing them to follow the Explicit Dependencies principle.</span></span> <span data-ttu-id="c9343-120">DI은 일반적으로 특정 IoC(Inversion of Control) 컨테이너를 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="c9343-120">DI is usually based on specific Inversion of Control (IoC) containers.</span></span> <span data-ttu-id="c9343-121">ASP.NET Core에는 간단한 기본 제공 IoC가 있지만 Autofac 또는 Ninject처럼 사용자가 원하는 IoC 컨테이너를 사용할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c9343-121">ASP.NET Core provides a simple built-in IoC container, but you can also use your favorite IoC container, like Autofac or Ninject.</span></span>

<span data-ttu-id="c9343-122">SOLID 원칙에 따르면 클래스는 당연히 작고 잘 구성되며 쉽게 테스트됩니다.</span><span class="sxs-lookup"><span data-stu-id="c9343-122">By following the SOLID principles, your classes will tend naturally to be small, well-factored, and easily tested.</span></span> <span data-ttu-id="c9343-123">그러나 클래스에 너무 많은 종속성이 주입된 것을 어떻게 알 수 있을까요?</span><span class="sxs-lookup"><span data-stu-id="c9343-123">But how can you know if too many dependencies are being injected into your classes?</span></span> <span data-ttu-id="c9343-124">생성자를 통해 DI를 사용할 경우 생성자에 대한 매개 변수 수를 살피기만 해도 이를 쉽게 감지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c9343-124">If you use DI through the constructor, it will be easy to detect that by just looking at the number of parameters for your constructor.</span></span> <span data-ttu-id="c9343-125">종속성이 너무 많은 경우 이는 일반적으로 클래스가 너무 많은 작업을 시도하고 있으며 아마도 SRP([단일 책임 원칙](http://deviq.com/code-smells/))를 위반하고 있다는 신호입니다.</span><span class="sxs-lookup"><span data-stu-id="c9343-125">If there are too many dependencies, this is generally a sign (a [code smell](http://deviq.com/code-smells/)) that your class is trying to do too much, and is probably violating the Single Responsibility principle.</span></span>

<span data-ttu-id="c9343-126">SOLID에 대해서는 다른 가이드에서 자세히 다룰 것입니다.</span><span class="sxs-lookup"><span data-stu-id="c9343-126">It would take another guide to cover SOLID in detail.</span></span> <span data-ttu-id="c9343-127">따라서 이 가이드에서는 이 항목에 대한 최소한의 지식만 요구합니다.</span><span class="sxs-lookup"><span data-stu-id="c9343-127">Therefore, this guide requires you to have only a minimum knowledge of these topics.</span></span>

#### <a name="additional-resources"></a><span data-ttu-id="c9343-128">추가 리소스</span><span class="sxs-lookup"><span data-stu-id="c9343-128">Additional resources</span></span>

-   <span data-ttu-id="c9343-129">**SOLID: 기본 OOP 원칙**
    [*http://deviq.com/solid/*](http://deviq.com/solid/%20)</span><span class="sxs-lookup"><span data-stu-id="c9343-129">**SOLID: Fundamental OOP Principles**
[*http://deviq.com/solid/*](http://deviq.com/solid/%20)</span></span>

-   <span data-ttu-id="c9343-130">**종속성 주입 패턴 및 제어 컨테이너 반전**
    [*https://martinfowler.com/articles/injection.html*](https://martinfowler.com/articles/injection.html)</span><span class="sxs-lookup"><span data-stu-id="c9343-130">**Inversion of Control Containers and the Dependency Injection pattern**
[*https://martinfowler.com/articles/injection.html*](https://martinfowler.com/articles/injection.html)</span></span>

-   <span data-ttu-id="c9343-131">**Steve Smith. 새로운 연결**
    [*http://ardalis.com/new-is-glue*](http://ardalis.com/new-is-glue)</span><span class="sxs-lookup"><span data-stu-id="c9343-131">**Steve Smith. New is Glue**
[*http://ardalis.com/new-is-glue*](http://ardalis.com/new-is-glue)</span></span>


>[!div class="step-by-step"]
<span data-ttu-id="c9343-132">[이전] (nosql-database-persistence-infrastructure.md) [다음] (microservice-application-layer-implementation-web-api.md)</span><span class="sxs-lookup"><span data-stu-id="c9343-132">[Previous] (nosql-database-persistence-infrastructure.md) [Next] (microservice-application-layer-implementation-web-api.md)</span></span>
