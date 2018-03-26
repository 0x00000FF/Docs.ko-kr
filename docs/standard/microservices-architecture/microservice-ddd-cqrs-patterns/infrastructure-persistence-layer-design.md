---
title: 인프라 지속성 계층 디자인
description: 컨테이너화된 .NET 응용 프로그램을 위한 .NET 마이크로 서비스 아키텍처 | 인프라 지속성 계층 디자인
keywords: Docker, 마이크로 서비스, ASP.NET, 컨테이너
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 11/08/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 76db5388c75d4eb3b5cc23c1e57cc391a15f2934
ms.sourcegitcommit: c883637b41ee028786edceece4fa872939d2e64c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/26/2018
---
# <a name="designing-the-infrastructure-persistence-layer"></a><span data-ttu-id="1c0b1-104">인프라 지속성 계층 디자인</span><span class="sxs-lookup"><span data-stu-id="1c0b1-104">Designing the infrastructure persistence layer</span></span>

<span data-ttu-id="1c0b1-105">데이터 지속성 구성 요소는 마이크로 서비스(즉, 마이크로 서비스의 데이터베이스)의 경계 내에서 호스팅된 데이터에 대한 액세스를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="1c0b1-105">Data persistence components provide access to the data hosted within the boundaries of a microservice (that is, a microservice’s database).</span></span> <span data-ttu-id="1c0b1-106">이 구성 요소에는 사용자 지정 EF DBContexts 같은 [작업 단위](http://martinfowler.com/eaaCatalog/unitOfWork.html) 클래스 및 리포지토리 등의 구성 요소의 실제 구현을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="1c0b1-106">They contain the actual implementation of components such as repositories and [Unit of Work](http://martinfowler.com/eaaCatalog/unitOfWork.html) classes, like custom EF DBContexts.</span></span>

## <a name="the-repository-pattern"></a><span data-ttu-id="1c0b1-107">리포지토리 패턴</span><span class="sxs-lookup"><span data-stu-id="1c0b1-107">The Repository pattern</span></span>

<span data-ttu-id="1c0b1-108">리포지토리는 데이터 원본에 액세스하는 데 필요한 논리를 캡슐화하는 클래스 또는 구성 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="1c0b1-108">Repositories are classes or components that encapsulate the logic required to access data sources.</span></span> <span data-ttu-id="1c0b1-109">리포지토리는 공통 데이터 액세스 기능에 집중해 더 나은 유지관리를 제공하고 도메인 모델 계층에서 데이터베이스에 액세스하는 데 사용되는 기술이나 인프라를 분리합니다.</span><span class="sxs-lookup"><span data-stu-id="1c0b1-109">They centralize common data access functionality, providing better maintainability and decoupling the infrastructure or technology used to access databases from the domain model layer.</span></span> <span data-ttu-id="1c0b1-110">Entity Framework 같은 ORM을 사용하는 경우 LINQ 및 강력한 형식화 덕분에 구현해야 할 코드가 간소화됩니다.</span><span class="sxs-lookup"><span data-stu-id="1c0b1-110">If you use an ORM like Entity Framework, the code that must be implemented is simplified, thanks to LINQ and strong typing.</span></span> <span data-ttu-id="1c0b1-111">이렇게 하면 데이터 액세스 내부 작업보다 데이터 지 속성 논리에 더 집중하게 합니다.</span><span class="sxs-lookup"><span data-stu-id="1c0b1-111">This lets you focus on the data persistence logic rather than on data access plumbing.</span></span>

<span data-ttu-id="1c0b1-112">이런 리포지토리 패턴은 데이터 원본을 사용한 작업의 잘 문서화된 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="1c0b1-112">The Repository pattern is a well-documented way of working with a data source.</span></span> <span data-ttu-id="1c0b1-113">[엔터프라이즈 응용 프로그램 아키텍처 패턴(Patterns of Enterprise Application Architecture)](https://www.amazon.com/Patterns-Enterprise-Application-Architecture-Martin/dp/0321127420/)이란 책에서, Martin Fowler는 다음과 같이 리포지토리에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="1c0b1-113">In the book [Patterns of Enterprise Application Architecture](https://www.amazon.com/Patterns-Enterprise-Application-Architecture-Martin/dp/0321127420/), Martin Fowler describes a repository as follows:</span></span>

<span data-ttu-id="1c0b1-114">리포지토리는 도메인 모델 계층과 데이터 매핑의 중간자 역할을 하며 메모리의 도메인 개체 집합에 대해서도 비슷한 방식으로 작업을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="1c0b1-114">A repository performs the tasks of an intermediary between the domain model layers and data mapping, acting in a similar way to a set of domain objects in memory.</span></span> <span data-ttu-id="1c0b1-115">클라이언트 개체는 쿼리를 선언적으로 빌드하고 리포지토리로 보내 답변합니다.</span><span class="sxs-lookup"><span data-stu-id="1c0b1-115">Client objects declaratively build queries and send them to the repositories for answers.</span></span> <span data-ttu-id="1c0b1-116">개념적으로, 리포지토리는 데이터베이스 내에 저장된 개체 집합과 수행할 수 있는 작업을 캡슐화해 지속성 계층에 더 가까운 방법을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="1c0b1-116">Conceptually, a repository encapsulates a set of objects stored in the database and operations that can be performed on them, providing a way that is closer to the persistence layer.</span></span> <span data-ttu-id="1c0b1-117">리포지토리는 또한 작업 도메인 및 데이터 할당 또는 매핑 간의 종속성을 명확하게 한 방향으로 구분하려는 목적을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="1c0b1-117">Repositories, also, support the purpose of separating, clearly and in one direction, the dependency between the work domain and the data allocation or mapping.</span></span>

### <a name="define-one-repository-per-aggregate"></a><span data-ttu-id="1c0b1-118">집계 당 하나의 리포지토리 정의</span><span class="sxs-lookup"><span data-stu-id="1c0b1-118">Define one repository per aggregate</span></span>

<span data-ttu-id="1c0b1-119">각 집계 또는 집계 루트에 대해 하나의 리포지토리 클래스를 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1c0b1-119">For each aggregate or aggregate root, you should create one repository class.</span></span> <span data-ttu-id="1c0b1-120">도메인 기반 디자인 패턴을 기반으로 한 마이크로 서비스에서 데이터베이스 업데이트에 사용해야 하는 유일한 채널은 리포지토리여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1c0b1-120">In a microservice based on domain-driven design patterns, the only channel you should use to update the database should be the repositories.</span></span> <span data-ttu-id="1c0b1-121">즉, 집계의 invariant와 트랜잭션 일관성을 제어하는 집계 루트와 일대일 관계를 갖기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="1c0b1-121">This is because they have a one-to-one relationship with the aggregate root, which controls the aggregate’s invariants and transactional consistency.</span></span> <span data-ttu-id="1c0b1-122">다른 채널(CQRS 방법을 따를 수 있을 때)을 통해 데이터베이스를 쿼리하는 것이 좋습니다. 쿼리는 데이터베이스 상태를 변경하지 않기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="1c0b1-122">It is okay to query the database through other channels (as you can do following a CQRS approach), because queries do not change the state of the database.</span></span> <span data-ttu-id="1c0b1-123">그러나 트랜잭션 영역, 곧 업데이트는 언제나 집계 루트와 리포지토리에 의해 제어되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1c0b1-123">However, the transactional area—the updates—must always be controlled by the repositories and the aggregate roots.</span></span>

<span data-ttu-id="1c0b1-124">기본적으로, 리포지토리는 데이터베이스에서 도메인 엔터티의 형태로 제공되는 메모리에 데이터를 채울 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1c0b1-124">Basically, a repository allows you to populate data in memory that comes from the database in the form of the domain entities.</span></span> <span data-ttu-id="1c0b1-125">엔터티가 메모리에 있으면, 변경되고 트랜잭션을 통해 데이터베이스에서 다시 지속될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1c0b1-125">Once the entities are in memory, they can be changed and then persisted back to the database through transactions.</span></span>

<span data-ttu-id="1c0b1-126">앞에서 설명한 대로, CQS/CQRS 아키텍처 패턴을 사용 하는 경우 초기 쿼리는 Dapper를 사용하는 간단한 SQL 문에 의해 수행된 도메인 모델 외부의 사이드 쿼리에 의해 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="1c0b1-126">As noted earlier, if you are using the CQS/CQRS architectural pattern, the initial queries will be performed by side queries out of the domain model, performed by simple SQL statements using Dapper.</span></span> <span data-ttu-id="1c0b1-127">이 방법은 필요한 모든 테이블을 쿼리하고 조인할 수 있으며 또한 이러한 쿼리는 집계 규칙에 의해 제한을 받지 않기 때문에 리포지토리보다 훨씬 더 유연합니다.</span><span class="sxs-lookup"><span data-stu-id="1c0b1-127">This approach is much more flexible than repositories because you can query and join any tables you need, and these queries are not restricted by rules from the aggregates.</span></span> <span data-ttu-id="1c0b1-128">해당 데이터는 프레젠테이션 계층 또는 클라이언트 응용 프로그램으로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="1c0b1-128">That data will go to the presentation layer or client app.</span></span>

<span data-ttu-id="1c0b1-129">사용자가 변경하는 경우 업데이트될 데이터는 클라이언트 응용 프로그램 또는 프레젠테이션 계층에서 응용 프로그램 계층(Web API 서비스 같은)로 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="1c0b1-129">If the user makes changes, the data to be updated will come from the client app or presentation layer to the application layer (such as a Web API service).</span></span> <span data-ttu-id="1c0b1-130">명령 처리기에서 명령(데이터와 함께)을 받는 경우 리포지토리를 이용해 데이터베이스에서 업데이트하고자 하는 데이터를 얻을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1c0b1-130">When you receive a command (with data) in a command handler, you use repositories to get the data you want to update from the database.</span></span> <span data-ttu-id="1c0b1-131">명령으로 전달되는 정보를 통해 데이터를 메모리에 업데이트한 다음, 트랜잭션을 통해 데이터베이스에 데이터(도메인 엔터티)를 추가하거나 업데이트합니다.</span><span class="sxs-lookup"><span data-stu-id="1c0b1-131">You update it in memory with the information passed with the commands, and you then add or update the data (domain entities) in the database through a transaction.</span></span>

<span data-ttu-id="1c0b1-132">그림 9-17에서 보는 것처럼 각 집계 루트에 대해 한 리포지토리만을 정의해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1c0b1-132">Remember that only one repository should be defined for each aggregate root, as shown in Figure 9-17.</span></span> <span data-ttu-id="1c0b1-133">집계 내 모든 개체 간의 트랜잭션 일관성을 유지하기 위한 집계 루트의 목표를 달성하려면 데이터베이스에 각 테이블에 대한 리포지토리를 결코 만들어서는 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1c0b1-133">To achieve the goal of the aggregate root to maintain transactional consistency between all the objects within the aggregate, you should never create a repository for each table in the database.</span></span>

![](./media/image18.png)

<span data-ttu-id="1c0b1-134">**그림 9-17**.</span><span class="sxs-lookup"><span data-stu-id="1c0b1-134">**Figure 9-17**.</span></span> <span data-ttu-id="1c0b1-135">리포지토리, 집계, 데이터베이스 테이블 간의 관계</span><span class="sxs-lookup"><span data-stu-id="1c0b1-135">The relationship between repositories, aggregates, and database tables</span></span>

### <a name="enforcing-one-aggregate-root-per-repository"></a><span data-ttu-id="1c0b1-136">리포지토리당 하나의 집계 루트 적용</span><span class="sxs-lookup"><span data-stu-id="1c0b1-136">Enforcing one aggregate root per repository</span></span>

<span data-ttu-id="1c0b1-137">집계 루트만 리포지토리를 갖는다는 규칙을 적용하는 것과 같은 방법으로 리포지티리 디자인을 구현하는 것은 유용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1c0b1-137">It can be valuable to implement your repository design in such a way that it enforces the rule that only aggregate roots should have repositories.</span></span> <span data-ttu-id="1c0b1-138">IAggregateRoot 마커 인터페이스를 갖도록 함께 작동하는 엔터티 형식을 제한하는 제네릭 또는 기본 리포지토리 형식을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1c0b1-138">You can create a generic or base repository type that constrains the type of entities it works with to ensure they have the IAggregateRoot marker interface.</span></span>

<span data-ttu-id="1c0b1-139">따라서 인프라 계층에서 구현되는 각 리포지토리 클래스는 다음 코드에 보이는 것처럼 자체 계약이나 인터페이스를 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="1c0b1-139">Thus, each repository class implemented at the infrastructure layer implements its own contract or interface, as shown in the following code:</span></span>

```csharp
namespace Microsoft.eShopOnContainers.Services.Ordering.Infrastructure.Repositories
{
    public class OrderRepository : IOrderRepository
    {
```

<span data-ttu-id="1c0b1-140">각 특정 리포지토리 인터페이스는 제네릭 IRepository 인터페이스를 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="1c0b1-140">Each specific repository interface implements the generic IRepository interface:</span></span>

```csharp
public interface IOrderRepository : IRepository<Order>
{
    Order Add(Order order);
    // ...
}
```

<span data-ttu-id="1c0b1-141">그러나 해당 코드가 각 리포지토리는 단일 집계와 관련있어야 한다는 규칙을 적용하게 하는 더 나은 방법은 명시적으로 특정 집계를 대상으로 하는 리포지토리를 사용할 수 있도록 제네릭 리포지토리 형식을 구현하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="1c0b1-141">However, a better way to have the code enforce the convention that each repository should be related to a single aggregate would be to implement a generic repository type so it is explicit that you are using a repository to target a specific aggregate.</span></span> <span data-ttu-id="1c0b1-142">다음 코드에서처럼 IRepository 기본 인터페이스에서 해당 제네릭을 구현함으로써 쉽게 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1c0b1-142">That can be easily done by implementing that generic in the IRepository base interface, as in the following code:</span></span>

```csharp
  public interface IRepository<T> where T : IAggregateRoot
```

### <a name="the-repository-pattern-makes-it-easier-to-test-your-application-logic"></a><span data-ttu-id="1c0b1-143">리포지토리 패턴은 응용 프로그램 논리를 보다 쉽게 테스트하게 합니다</span><span class="sxs-lookup"><span data-stu-id="1c0b1-143">The Repository pattern makes it easier to test your application logic</span></span>

<span data-ttu-id="1c0b1-144">리포지토리 패턴은 단위 테스트를 사용해 응용 프로그램을 쉽게 테스트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1c0b1-144">The Repository pattern allows you to easily test your application with unit tests.</span></span> <span data-ttu-id="1c0b1-145">단위 테스트만 인프라가 아닌 해당 코드를 테스트함으로써 리포지토리 추상적 개념이 목표를 더 쉽게 달성하게 합니다.</span><span class="sxs-lookup"><span data-stu-id="1c0b1-145">Remember that unit tests only test your code, not infrastructure, so the repository abstractions make it easier to achieve that goal.</span></span>

<span data-ttu-id="1c0b1-146">이전 단원에서 설명했듯이, 응용 프로그램 계층(예를 들어, Web API 마이크로 서비스)이 실제 리포지토리 클래스를 구현한 인프라 계층에 직접 종속되지 않도록 도메인 모델 계층에서 리포지토리 인터페이스를 정의하고 배치합니다.</span><span class="sxs-lookup"><span data-stu-id="1c0b1-146">As noted in an earlier section, it is recommended that you define and place the repository interfaces in the domain model layer so the application layer (for instance, your Web API microservice) does not depend directly on the infrastructure layer where you have implemented the actual repository classes.</span></span> <span data-ttu-id="1c0b1-147">이렇게 하는 동시에 Web API의 컨트롤러에서 종속성 주입을 사용함으로써 데이터베이스에서 데이터 대신 가짜 데이터를 반환하는 모의 리포지토리를 구현할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1c0b1-147">By doing this and using Dependency Injection in the controllers of your Web API, you can implement mock repositories that return fake data instead of data from the database.</span></span> <span data-ttu-id="1c0b1-148">분리된 접근방식은 단위 테스트를 만들고 실행할 수 있게 함으로써 데이터베이스에 연결을 요구하지 않고도 응용 프로그램의 논리를 테스트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1c0b1-148">That decoupled approach allows you to create and run unit tests that can test just the logic of your application without requiring connectivity to the database.</span></span>

<span data-ttu-id="1c0b1-149">데이터베이스에 대 한 연결이 실패할 수 하며, 무엇 보다도 데이터베이스에 대해 수백 번의 테스트를 실행 합니다. 잘못 된 두 가지 이유로 합니다.</span><span class="sxs-lookup"><span data-stu-id="1c0b1-149">Connections to databases can fail and, more importantly, running hundreds of tests against a database is bad for two reasons.</span></span> <span data-ttu-id="1c0b1-150">첫째, 방대한 양의 테스트 때문에 많은 시간이 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1c0b1-150">First, it can take a lot of time because of the large number of tests.</span></span> <span data-ttu-id="1c0b1-151">둘째, 데이터베이스 레코드는 테스트 결과를 변경하고 영향을 줄 수 있으므로 결과가 일관되지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1c0b1-151">Second, the database records might change and impact the results of your tests, so that they might not be consistent.</span></span> <span data-ttu-id="1c0b1-152">데이터베이스의 테스트는 단위 테스트가 아닌 통합 테스트입니다.</span><span class="sxs-lookup"><span data-stu-id="1c0b1-152">Testing against the database is not a unit tests but an integration test.</span></span> <span data-ttu-id="1c0b1-153">많은 단위 테스트를 신속하게 실행해야 하지만 데이터베이스에 대해 통합 테스트는 거의 실행되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1c0b1-153">You should have many unit tests running fast, but fewer integration tests against the databases.</span></span>

<span data-ttu-id="1c0b1-154">단위 테스트에 대한 관심의 분리란 관점에서 해당 논리는 메모리의 도메인 엔터티에서 작동합니다.</span><span class="sxs-lookup"><span data-stu-id="1c0b1-154">In terms of separation of concerns for unit tests, your logic operates on domain entities in memory.</span></span> <span data-ttu-id="1c0b1-155">리포지토리 클래스가 단위 테스트를 전달한 것으로 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="1c0b1-155">It assumes the repository class has delivered those.</span></span> <span data-ttu-id="1c0b1-156">일단 해당 논리가 도메인 엔터티를 수정하면 리포지토리 클래스가 이를 올바르게 저장할 것으로 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="1c0b1-156">Once your logic modifies the domain entities, it assumes the repository class will store them correctly.</span></span> <span data-ttu-id="1c0b1-157">여기서 중요한 것은 해당 도메인 모델 및 도메인 논리에 대해 단위 테스트를 만드는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="1c0b1-157">The important point here is to create unit tests against your domain model and its domain logic.</span></span> <span data-ttu-id="1c0b1-158">집계 루트는 DDD에서의 주된 일관성 경계입니다.</span><span class="sxs-lookup"><span data-stu-id="1c0b1-158">Aggregate roots are the main consistency boundaries in DDD.</span></span>

### <a name="the-difference-between-the-repository-pattern-and-the-legacy-data-access-class-dal-class-pattern"></a><span data-ttu-id="1c0b1-159">리포지토리 패턴 및 레거시 데이터 액세스 클래스(DAL 클래스) 패턴의 차이</span><span class="sxs-lookup"><span data-stu-id="1c0b1-159">The difference between the Repository pattern and the legacy Data Access class (DAL class) pattern</span></span>

<span data-ttu-id="1c0b1-160">데이터 액세스 개체는 저장소에 대한 데이터 액세스 및 지속성 작업을 직접 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="1c0b1-160">A data access object directly performs data access and persistence operations against storage.</span></span> <span data-ttu-id="1c0b1-161">리포지토리는 작업 개체 단위(DbContext를 사용하는 경우 EF에서처럼)의 메모리에서 수행하고자 하는 작업을 통해 데이터를 표시하지만 이러한 업데이트는 즉시 수행되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1c0b1-161">A repository marks the data with the operations you want to perform in the memory of a unit of work object (as in EF when using the DbContext), but these updates aren't performed immediately.</span></span>

<span data-ttu-id="1c0b1-162">작업 단위는 다중 삽입, 업데이트, 삭제 작업과 관련된 단일 트랜잭션이라고도 합니다.</span><span class="sxs-lookup"><span data-stu-id="1c0b1-162">A unit of work is referred to as a single transaction that involves multiple insert, update, or delete operations.</span></span> <span data-ttu-id="1c0b1-163">간단히 말해 특정 사용자 작업(예를 들어, 웹사이트 등록)의 경우 모든 삽입, 업데이트 및 삭제 트랜잭션은 단일 트랜잭션으로 처리된다는 의미입니다.</span><span class="sxs-lookup"><span data-stu-id="1c0b1-163">In simple terms, it means that for a specific user action (for example, registration on a website), all the insert, update, and delete transactions are handled in a single transaction.</span></span> <span data-ttu-id="1c0b1-164">단일 트랜잭션 처리는 복잡한 방식으로 다중 데이터베이스 트랜잭션을 처리하는 것보다 더 효율적입니다.</span><span class="sxs-lookup"><span data-stu-id="1c0b1-164">This is more efficient than handling multiple database transactions in a chattier way.</span></span>

<span data-ttu-id="1c0b1-165">이러한 다중 지속성 작업은 응용 프로그램 계층에서 해당 코드가 명령을 내리는 경우 나중에 단일 작업으로 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="1c0b1-165">These multiple persistence operations are performed later in a single action when your code from the application layer commands it.</span></span> <span data-ttu-id="1c0b1-166">실제 데이터베이스 저장소에 메모리 내 변경을 적용은 일반적으로 [작업 단위 패턴](http://martinfowler.com/eaaCatalog/unitOfWork.html)에 기반을 두고 결정됩니다.</span><span class="sxs-lookup"><span data-stu-id="1c0b1-166">The decision about applying the in-memory changes to the actual database storage is typically based on the [Unit of Work pattern](http://martinfowler.com/eaaCatalog/unitOfWork.html).</span></span> <span data-ttu-id="1c0b1-167">EF에서, 작업 단위 패턴은 DBContext로서 구현됩니다.</span><span class="sxs-lookup"><span data-stu-id="1c0b1-167">In EF, the Unit of Work pattern is implemented as the DBContext.</span></span>

<span data-ttu-id="1c0b1-168">대부분의 경우, 저장소에 작업을 적용하는 방식이나 패턴은 응용 프로그램 성능을 향상시키고 불일치 가능성을 줄일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1c0b1-168">In many cases, this pattern or way of applying operations against the storage can increase application performance and reduce the possibility of inconsistencies.</span></span> <span data-ttu-id="1c0b1-169">또한, 의도된 모든 작업은 한 트랜잭션의 일부로서 커밋되기 때문에 데이터베이스 테이블에서 트랜잭션 차단을 줄여줍니다.</span><span class="sxs-lookup"><span data-stu-id="1c0b1-169">Also, it reduces transaction blocking in the database tables, because all the intended operations are committed as part of one transaction.</span></span> <span data-ttu-id="1c0b1-170">이 방법은 데이터베이스에 대해 많은 격리된 작업 실행에 비해 더 효율적입니다.</span><span class="sxs-lookup"><span data-stu-id="1c0b1-170">This is more efficient in comparison to executing many isolated operations against the database.</span></span> <span data-ttu-id="1c0b1-171">따라서 선택한 ORM은 많은 소형 및 별도 트랜잭션 실행과 대조적으로 동일한 트랜잭션 내에서 여러 가지 업데이트 작업을 그룹화하여 데이터베이스에서의 실행을 최적화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1c0b1-171">Therefore, the selected ORM is able to optimize the execution against the database by grouping several update actions within the same transaction, as opposed to many small and separate transaction executions.</span></span>

### <a name="repositories-should-not-be-mandatory"></a><span data-ttu-id="1c0b1-172">리포지토리는 필수가 아닙니다</span><span class="sxs-lookup"><span data-stu-id="1c0b1-172">Repositories should not be mandatory</span></span>

<span data-ttu-id="1c0b1-173">사용자 지정 리포지토리는 앞에서 언급한 이유 때문에 유용하며 eShopOnContainers에서 주문형 마이크로 서비스용 접근방식입니다.</span><span class="sxs-lookup"><span data-stu-id="1c0b1-173">Custom repositories are useful for the reasons cited earlier, and that is the approach for the ordering microservice in eShopOnContainers.</span></span> <span data-ttu-id="1c0b1-174">그러나 DDD 디자인이나 .NET에서의 일반 개발에서도 구현을 위한 필수 패턴은 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="1c0b1-174">However, it is not an essential pattern to implement in a DDD design or even in general development in .NET.</span></span>

<span data-ttu-id="1c0b1-175">예를 들어, Jimmy Bogard는 이 가이드를 위한 피드백을 직접 제공하면서 다음과 같이 말했습니다.</span><span class="sxs-lookup"><span data-stu-id="1c0b1-175">For instance, Jimmy Bogard, when providing direct feedback for this guide, said the following:</span></span>

<span data-ttu-id="1c0b1-176">이것이 아마도 나의 가장 큰 피드백일 것입니다.</span><span class="sxs-lookup"><span data-stu-id="1c0b1-176">This’ll probably be my biggest feedback.</span></span> <span data-ttu-id="1c0b1-177">주로 리포지토리가 기본 지속성 메커니즘의 중요한 세부 정보를 숨기기 때문에 실제로 리포지토리를 좋아하지는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1c0b1-177">I’m really not a fan of repositories, mainly because they hide the important details of the underlying persistence mechanism.</span></span> <span data-ttu-id="1c0b1-178">때문에 나는 명령용 MediatR도 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="1c0b1-178">It’s why I go for MediatR for commands, too.</span></span> <span data-ttu-id="1c0b1-179">지속성 계층의 모든 기능을 사용할 수 있으며 모든 도메인 동작을 집계 루트로 밀어 넣을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1c0b1-179">I can use the full power of the persistence layer, and push all that domain behavior into my aggregate roots.</span></span> <span data-ttu-id="1c0b1-180">보통 내 리포지토리를 흉내내고 싶지는 않습니다 – 여전히 실제 사물을 통한 통합 테스트가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="1c0b1-180">I don’t usually want to mock my repositories – I still need to have that integration test with the real thing.</span></span> <span data-ttu-id="1c0b1-181">CQRS로의 전환은 실제로 리포지토리가 더 이상 필요하지 않다는 것을 의미합니다.</span><span class="sxs-lookup"><span data-stu-id="1c0b1-181">Going CQRS meant that we didn’t really have a need for repositories any more.</span></span>

<span data-ttu-id="1c0b1-182">우리는 리포지토리가 유용하다고 생각하지만 집계 모듈과 풍성한 도메인 모델만큼 DDD에는 중요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1c0b1-182">We find repositories useful, but we acknowledge that they are not critical for your DDD, in the way that the Aggregate pattern and rich domain model are.</span></span> <span data-ttu-id="1c0b1-183">따라서 필요에 따라 리포지토리 패턴을 사용하거나 사용하지 마십시오.</span><span class="sxs-lookup"><span data-stu-id="1c0b1-183">Therefore, use the Repository pattern or not, as you see fit.</span></span>

## <a name="the-specification-pattern"></a><span data-ttu-id="1c0b1-184">사양 패턴</span><span class="sxs-lookup"><span data-stu-id="1c0b1-184">The Specification pattern</span></span>

<span data-ttu-id="1c0b1-185">사양 패턴(전체 이름은 쿼리 사양 패턴입니다)은 선택적 정렬과 페이징 논리를 사용해 쿼리를 정의내릴 수 있는 공간으로 디자인된 도메인 기반 디자인 패턴입니다.</span><span class="sxs-lookup"><span data-stu-id="1c0b1-185">The Specification pattern (its full name would be Query-specification pattern) is a Domain-Driven Design pattern designed as the place where you can put the definition of a query with optional sorting and paging logic.</span></span>

<span data-ttu-id="1c0b1-186">사양 패턴은 개체에서 쿼리를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="1c0b1-186">The Specification pattern defines a query in an object.</span></span> <span data-ttu-id="1c0b1-187">예를 들어, 일부 제품을 검색하는 페이징된 쿼리를 캡슐화하려면 필요한 입력 매개 변수(pageNumber, pageSize, 필터 등)를 사용하는 PagedProduct 사양을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1c0b1-187">For example, in order to encapsulate a paged query that searches for some products, you can create a PagedProduct specification that takes the necessary input parameters (pageNumber, pageSize, filter, etc.).</span></span> <span data-ttu-id="1c0b1-188">그런 다음, 모든 리포지토리 메서드(일반적으로 목록() 오버로드) 내에서 ISpecification을 수용하고 해당 사양을 기반으로 필요한 쿼리를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="1c0b1-188">Then, within any Repository method (usually a List() overload) it would accept an ISpecification and run the expected query based on that specification.</span></span>

<span data-ttu-id="1c0b1-189">이 방법에는 여러 장점이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1c0b1-189">There are several benefits to this approach:</span></span>

* <span data-ttu-id="1c0b1-190">사양에는 논의할 수 있는 이름(많은 LINQ 식과는 대조적으로)이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1c0b1-190">The specification has a name (as opposed to just a bunch of LINQ expressions) that you can discuss about.</span></span>

* <span data-ttu-id="1c0b1-191">사양이 올바른지 확인하려면 격리 상태에서 단위 테스트가 가능합니다.</span><span class="sxs-lookup"><span data-stu-id="1c0b1-191">The specification can be unit tested in isolation to ensure it is right.</span></span> <span data-ttu-id="1c0b1-192">비슷한 동작이 필요한 경우 쉽게 재사용될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1c0b1-192">It can also easily be reused if you need similar behavior.</span></span> <span data-ttu-id="1c0b1-193">예를 들어, MVC View 작업과 Web API 작업에서뿐 아니라 다양한 서비스에서도 가능합니다.</span><span class="sxs-lookup"><span data-stu-id="1c0b1-193">For example, on an MVC View action and a Web API action, as well as in various services.</span></span>

* <span data-ttu-id="1c0b1-194">사양은 쿼리가 필요한 데이터만 반환할 수 있도록 반환될 데이터의 모양을 설명하는 데 사용될 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1c0b1-194">A specification can also be used to describe the shape of the data to be returned, so that queries can return just the data they required.</span></span> <span data-ttu-id="1c0b1-195">이렇게 함으로써 웹 응용 프로그램(일반적으로 좋은 생각이 아닌)에서 지연 로드에 대한 필요를 없애고 리포지토리 구현이 세부 정보와 겹쳐 복잡해지지 않게 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="1c0b1-195">This eliminates the need for lazy loading in web applications (which is usually not a good idea) and helps keep repository implementations from becoming cluttered with these details.</span></span>

<span data-ttu-id="1c0b1-196">제네릭 사양 인터페이스의 예제는 [eShopOnWeb](https://github.com/dotnet-architecture/eShopOnWeb )의 다음 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="1c0b1-196">An example of a generic Specification interface is the following code from [eShopOnWeb](https://github.com/dotnet-architecture/eShopOnWeb ).</span></span>

```csharp
// https://github.com/dotnet-architecture/eShopOnWeb 
public interface ISpecification<T>
{
    Expression<Func<T, bool>> Criteria { get; }
    List<Expression<Func<T, object>>> Includes { get; }
    List<string> IncludeStrings { get; }
}
```

<span data-ttu-id="1c0b1-197">이후 단원에서는 Entity Framework Core 2.0으로 사양 패턴을 구현하는 방법과 모든 리포지토릭 클래스에서 이 패턴을 사용하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="1c0b1-197">In the upcoming sections, it is explained how to implement the Specification pattern with Entity Framework Core 2.0 and how to use it from any Repository class.</span></span>

<span data-ttu-id="1c0b1-198">**중요 참고:** 사양 패턴은 다음의 추가 리소스에서와 같이 다양한 방식으로 구현될 수 있는 이전 패턴입니다.</span><span class="sxs-lookup"><span data-stu-id="1c0b1-198">**Important note:** The specification pattern is an old pattern that can be implemented in many different ways, as in the following additional resources.</span></span> <span data-ttu-id="1c0b1-199">패턴/개념으로서 이전 방법이 익히기에 좋지만 Linq 및 식 같은 현대 언어 역량을 이용하지 않는 이전 구현은 주의하십시오.</span><span class="sxs-lookup"><span data-stu-id="1c0b1-199">As a pattern/idea, older approaches are good to know, but beware of older implementations that are not taking advantage of modern language capabilities like Linq and expressions.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="1c0b1-200">추가 자료</span><span class="sxs-lookup"><span data-stu-id="1c0b1-200">Additional resources</span></span>

### <a name="the-repository-pattern"></a><span data-ttu-id="1c0b1-201">리포지토리 패턴</span><span class="sxs-lookup"><span data-stu-id="1c0b1-201">The Repository pattern</span></span>

-   <span data-ttu-id="1c0b1-202">**Edward Hieatt와 Rob Mee. 리포지토리 패턴입니다.**
    [*http://martinfowler.com/eaaCatalog/repository.html*](http://martinfowler.com/eaaCatalog/repository.html)</span><span class="sxs-lookup"><span data-stu-id="1c0b1-202">**Edward Hieatt and Rob Mee. Repository pattern.**
[*http://martinfowler.com/eaaCatalog/repository.html*](http://martinfowler.com/eaaCatalog/repository.html)</span></span>

-   <span data-ttu-id="1c0b1-203">**리포지토리 패턴**
    [*https://msdn.microsoft.com/library/ff649690.aspx*](https://msdn.microsoft.com/library/ff649690.aspx)</span><span class="sxs-lookup"><span data-stu-id="1c0b1-203">**The Repository pattern**
[*https://msdn.microsoft.com/library/ff649690.aspx*](https://msdn.microsoft.com/library/ff649690.aspx)</span></span>

-   <span data-ttu-id="1c0b1-204">**리포지토리 패턴: 데이터 지 속성 추상화**
    [*http://deviq.com/repository-pattern/*](http://deviq.com/repository-pattern/)</span><span class="sxs-lookup"><span data-stu-id="1c0b1-204">**Repository Pattern: A data persistence abstraction**
[*http://deviq.com/repository-pattern/*](http://deviq.com/repository-pattern/)</span></span>

-   <span data-ttu-id="1c0b1-205">**Eric Evans. 도메인 기반 디자인: 소프트웨어 핵심에서 복잡성 처리.**</span><span class="sxs-lookup"><span data-stu-id="1c0b1-205">**Eric Evans. Domain-Driven Design: Tackling Complexity in the Heart of Software.**</span></span> <span data-ttu-id="1c0b1-206">(예약; 리포지토리 패턴에 대 한 설명이 포함) [*https://www.amazon.com/Domain-Driven-Design-Tackling-Complexity-Software/dp/0321125215/*](https://www.amazon.com/Domain-Driven-Design-Tackling-Complexity-Software/dp/0321125215/)</span><span class="sxs-lookup"><span data-stu-id="1c0b1-206">(Book; includes a discussion of the Repository pattern) [*https://www.amazon.com/Domain-Driven-Design-Tackling-Complexity-Software/dp/0321125215/*](https://www.amazon.com/Domain-Driven-Design-Tackling-Complexity-Software/dp/0321125215/)</span></span>

### <a name="unit-of-work-pattern"></a><span data-ttu-id="1c0b1-207">작업 단위 패턴</span><span class="sxs-lookup"><span data-stu-id="1c0b1-207">Unit of Work pattern</span></span>

-   <span data-ttu-id="1c0b1-208">**Martin Fowler. 단위 작업 패턴입니다.**
    [*http://martinfowler.com/eaaCatalog/unitOfWork.html*](http://martinfowler.com/eaaCatalog/unitOfWork.html)</span><span class="sxs-lookup"><span data-stu-id="1c0b1-208">**Martin Fowler. Unit of Work pattern.**
[*http://martinfowler.com/eaaCatalog/unitOfWork.html*](http://martinfowler.com/eaaCatalog/unitOfWork.html)</span></span>

<!-- -->

-   <span data-ttu-id="1c0b1-209">**ASP.NET MVC 응용 프로그램에서 작업 패턴의 리포지토리 및 단위 구현**
    [*https://www.asp.net/mvc/overview/older-versions/getting-started-with-ef-5-using-mvc-4/implementing-the-repository-and-unit-of-work-patterns-in-an-asp-net-mvc-application*](https://www.asp.net/mvc/overview/older-versions/getting-started-with-ef-5-using-mvc-4/implementing-the-repository-and-unit-of-work-patterns-in-an-asp-net-mvc-application)</span><span class="sxs-lookup"><span data-stu-id="1c0b1-209">**Implementing the Repository and Unit of Work Patterns in an ASP.NET MVC Application**
[*https://www.asp.net/mvc/overview/older-versions/getting-started-with-ef-5-using-mvc-4/implementing-the-repository-and-unit-of-work-patterns-in-an-asp-net-mvc-application*](https://www.asp.net/mvc/overview/older-versions/getting-started-with-ef-5-using-mvc-4/implementing-the-repository-and-unit-of-work-patterns-in-an-asp-net-mvc-application)</span></span>

### <a name="the-specification-pattern"></a><span data-ttu-id="1c0b1-210">사양 패턴</span><span class="sxs-lookup"><span data-stu-id="1c0b1-210">The Specification pattern</span></span>

-   <span data-ttu-id="1c0b1-211">**사양 패턴입니다.**
    [*http://deviq.com/specification-pattern/*](http://deviq.com/specification-pattern/)</span><span class="sxs-lookup"><span data-stu-id="1c0b1-211">**The Specification pattern.**
[*http://deviq.com/specification-pattern/*](http://deviq.com/specification-pattern/)</span></span>

-   <span data-ttu-id="1c0b1-212">**Evans, Eric(2004). 도메인 기반 디자인. Addison-Wesley. p. 224.**</span><span class="sxs-lookup"><span data-stu-id="1c0b1-212">**Evans, Eric (2004). Domain Driven Design. Addison-Wesley. p. 224.**</span></span>

-   <span data-ttu-id="1c0b1-213">**사양. Martin Fowler**
    [*https://www.martinfowler.com/apsupp/spec.pdf/*](https://www.martinfowler.com/apsupp/spec.pdf)</span><span class="sxs-lookup"><span data-stu-id="1c0b1-213">**Specifications. Martin Fowler**
[*https://www.martinfowler.com/apsupp/spec.pdf/*](https://www.martinfowler.com/apsupp/spec.pdf)</span></span>

>[!div class="step-by-step"]
<span data-ttu-id="1c0b1-214">[이전] (domain-events-design-implementation.md) [다음] (infrastructure-persistence-layer-implemenation-entity-framework-core.md)</span><span class="sxs-lookup"><span data-stu-id="1c0b1-214">[Previous] (domain-events-design-implementation.md) [Next] (infrastructure-persistence-layer-implemenation-entity-framework-core.md)</span></span>
