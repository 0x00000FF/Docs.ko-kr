---
title: ".NET core 마이크로 서비스 도메인 모델 구현"
description: "컨테이너 화 된.NET 응용 프로그램에 대 한.NET Microservices 아키텍처 | .NET core 마이크로 서비스 도메인 모델 구현"
keywords: "Docker, 마이크로 서비스, ASP.NET, 컨테이너"
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.openlocfilehash: 26c480a82ad7bb806734decebdfbe5b4a07998e6
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="implementing-a-microservice-domain-model-with-net-core"></a><span data-ttu-id="dc0d6-104">.NET core 마이크로 서비스 도메인 모델 구현</span><span class="sxs-lookup"><span data-stu-id="dc0d6-104">Implementing a microservice domain model with .NET Core</span></span> 

<span data-ttu-id="dc0d6-105">이전 섹션에서 기본적인 디자인 원칙 및 도메인 모델을 디자인 하기 위한 패턴 설명 했습니다.</span><span class="sxs-lookup"><span data-stu-id="dc0d6-105">In the previous section, the fundamental design principles and patterns for designing a domain model were explained.</span></span> <span data-ttu-id="dc0d6-106">이제.NET Core를 사용 하 여 도메인 모델을 구현 하는 가능한 방법을 탐색할 (일반 C\# 코드) 및 EF 코어입니다.</span><span class="sxs-lookup"><span data-stu-id="dc0d6-106">Now it is time to explore possible ways to implement the domain model by using .NET Core (plain C\# code) and EF Core.</span></span> <span data-ttu-id="dc0d6-107">도메인 모델은 코드의 단순히 구성 될 참고 합니다.</span><span class="sxs-lookup"><span data-stu-id="dc0d6-107">Note that your domain model will be composed simply of your code.</span></span> <span data-ttu-id="dc0d6-108">EF에 EF 코어 모델 요구 사항 이지만 실제 하지 종속성은입니다.</span><span class="sxs-lookup"><span data-stu-id="dc0d6-108">It will have just the EF Core model requirements, but not real dependencies on EF.</span></span> <span data-ttu-id="dc0d6-109">없어야 하드 종속성 또는 EF Core 설치 옵션이 나 다른 ORM에 대 한 참조가 도메인 모델입니다.</span><span class="sxs-lookup"><span data-stu-id="dc0d6-109">You should not have hard dependencies or references to EF Core or any other ORM in your domain model.</span></span>

## <a name="domain-model-structure-in-a-custom-net-standard-library"></a><span data-ttu-id="dc0d6-110">사용자 지정.NET 표준 라이브러리의 도메인 모델 구조</span><span class="sxs-lookup"><span data-stu-id="dc0d6-110">Domain model structure in a custom .NET Standard library</span></span>

<span data-ttu-id="dc0d6-111">폴더 조직 eShopOnContainers 참조 응용 프로그램에 사용 되는 응용 프로그램에 대 한 DDD 모델을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="dc0d6-111">The folder organization used for the eShopOnContainers reference application demonstrates the DDD model for the application.</span></span> <span data-ttu-id="dc0d6-112">다른 폴더 조직에서 응용 프로그램에 대 한 설계 선택 사항은 보다 명확 하 게 통신 하는 경우가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dc0d6-112">You might find that a different folder organization more clearly communicates the design choices made for your application.</span></span> <span data-ttu-id="dc0d6-113">그림 9-10을 볼 수 있듯이 순서 도메인 모델에서 두 개의 집계, 순서 집계 및 없는 구매자 집계 합니다.</span><span class="sxs-lookup"><span data-stu-id="dc0d6-113">As you can see in Figure 9-10, in the ordering domain model there are two aggregates, the order aggregate and the buyer aggregate.</span></span> <span data-ttu-id="dc0d6-114">각 집계는 단일 도메인 엔터티 (집계 루트 또는 루트 엔터티)도 구성 집계 있을 수 있지만 도메인 엔터티 및 값 개체의 그룹.</span><span class="sxs-lookup"><span data-stu-id="dc0d6-114">Each aggregate is a group of domain entities and value objects, although you could have an aggregate composed of a single domain entity (the aggregate root or root entity) as well.</span></span>

![](./media/image11.png)

<span data-ttu-id="dc0d6-115">**그림 9-10**합니다.</span><span class="sxs-lookup"><span data-stu-id="dc0d6-115">**Figure 9-10**.</span></span> <span data-ttu-id="dc0d6-116">EShopOnContainers에 정렬 마이크로 서비스에 대 한 도메인 모델 구조</span><span class="sxs-lookup"><span data-stu-id="dc0d6-116">Domain model structure for the ordering microservice in eShopOnContainers</span></span>

<span data-ttu-id="dc0d6-117">또한 도메인 모델 계층은 도메인 모델의 인프라 요구 사항 리포지토리 계약 (인터페이스)를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="dc0d6-117">Additionally, the domain model layer includes the repository contracts (interfaces) that are the infrastructure requirements of your domain model.</span></span> <span data-ttu-id="dc0d6-118">즉, 이러한 인터페이스 express 인프라 계층 구현 해야 하는 저장소와 방법을 합니다.</span><span class="sxs-lookup"><span data-stu-id="dc0d6-118">In other words, these interfaces express what repositories the infrastructure layer must implement and how.</span></span> <span data-ttu-id="dc0d6-119">도메인 모델 계층 인프라 계층 라이브러리에서의 바깥쪽에 있으므로 도메인 모델 계층은 하지 "오염" API 또는 Entity Framework와 같은 인프라 기술에서 클래스 리포지토리와 구현을 배치 합니다.</span><span class="sxs-lookup"><span data-stu-id="dc0d6-119">It is critical that the implementation of the repositories be placed outside of the domain model layer, in the infrastructure layer library, so the domain model layer is not “contaminated” by API or classes from infrastructure technologies, like Entity Framework.</span></span>

<span data-ttu-id="dc0d6-120">확인할 수 있습니다는 [SeedWork](https://martinfowler.com/bliki/Seedwork.html) 각 도메인의 개체 클래스에 대 한 중복 번호가 있으므로 도메인 엔터티 및 값에 대 한 기본으로 사용할 수 있는 사용자 지정 기본 클래스를 포함 된 폴더 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="dc0d6-120">You can also see a [SeedWork](https://martinfowler.com/bliki/Seedwork.html) folder that contains custom base classes that you can use as a base for your domain entities and value objects, so you do not have redundant code in each domain’s object class.</span></span>

## <a name="structuring-aggregates-in-a-custom-net-standard-library"></a><span data-ttu-id="dc0d6-121">사용자 지정.NET 표준 라이브러리의 집계를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="dc0d6-121">Structuring aggregates in a custom .NET Standard library</span></span>

<span data-ttu-id="dc0d6-122">집계는 트랜잭션 일관성에 맞게 그룹화 하는 도메인 개체의 클러스터를 참조 합니다.</span><span class="sxs-lookup"><span data-stu-id="dc0d6-122">An aggregate refers to a cluster of domain objects grouped together to match transactional consistency.</span></span> <span data-ttu-id="dc0d6-123">가치를 더하는 개체와 해당 개체에 엔터티 (그 중 하나는 집계 루트 또는 루트 엔터티)의 인스턴스 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dc0d6-123">Those objects could be instances of entities (one of which is the aggregate root or root entity) plus any additional value objects.</span></span>

<span data-ttu-id="dc0d6-124">트랜잭션 일관성 집계 일관 되 고 비즈니스 작업의 끝에 최신 상태로 되도록 보장을 의미 합니다.</span><span class="sxs-lookup"><span data-stu-id="dc0d6-124">Transactional consistency means that an aggregate is guaranteed to be consistent and up to date at the end of a business action.</span></span> <span data-ttu-id="dc0d6-125">예를 들어, 마이크로 서비스 도메인 모델 순서 eShopOnContainers에서 순서 집계는 그림 9-11에서와 같이 구성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="dc0d6-125">For example, the order aggregate from the eShopOnContainers ordering microservice domain model is composed as shown in Figure 9-11.</span></span>

![](./media/image12.png)

<span data-ttu-id="dc0d6-126">**그림 9-11**합니다.</span><span class="sxs-lookup"><span data-stu-id="dc0d6-126">**Figure 9-11**.</span></span> <span data-ttu-id="dc0d6-127">Visual Studio 솔루션에서 집계 되는 순서</span><span class="sxs-lookup"><span data-stu-id="dc0d6-127">The order aggregate in Visual Studio solution</span></span>

<span data-ttu-id="dc0d6-128">집계 폴더에 파일을 열고 볼 수 있습니다 어떻게 것으로 표시는 기본 사용자 지정 클래스 또는 인터페이스 엔터티 또는 값 개체와 마찬가지로 구현 되는 [Seedwork](https://github.com/dotnet-architecture/eShopOnContainers/tree/master/src/Services/Ordering/Ordering.Domain/SeedWork) 폴더입니다.</span><span class="sxs-lookup"><span data-stu-id="dc0d6-128">If you open any of the files in an aggregate folder, you can see how it is marked as either a custom base class or interface, like entity or value object, as implemented in the [Seedwork](https://github.com/dotnet-architecture/eShopOnContainers/tree/master/src/Services/Ordering/Ordering.Domain/SeedWork) folder.</span></span>

## <a name="implementing-domain-entities-as-poco-classes"></a><span data-ttu-id="dc0d6-129">도메인 엔터티 POCO 클래스 구현</span><span class="sxs-lookup"><span data-stu-id="dc0d6-129">Implementing domain entities as POCO classes</span></span>

<span data-ttu-id="dc0d6-130">도메인 엔터티를 구현 하는 POCO 클래스를 만들어.net에서 도메인 모델을 구현 합니다.</span><span class="sxs-lookup"><span data-stu-id="dc0d6-130">You implement a domain model in .NET by creating POCO classes that implement your domain entities.</span></span> <span data-ttu-id="dc0d6-131">다음 예제에서는 Order 클래스는 엔터티를 및 집계를 루트로 정의 됩니다.</span><span class="sxs-lookup"><span data-stu-id="dc0d6-131">In the following example, the Order class is defined as an entity and also as an aggregate root.</span></span> <span data-ttu-id="dc0d6-132">Order 클래스를 엔터티 기본 클래스에서 파생, 되기 때문에 엔터티와 관련 된 공통 코드를 재사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="dc0d6-132">Because the Order class derives from the Entity base class, it can reuse common code related to entities.</span></span> <span data-ttu-id="dc0d6-133">이러한 기본 클래스 및 인터페이스는 의해 정의 되는 사용자 도메인 모델 프로젝트에서 코드, EF 같은 ORM에서 인프라 코드가 아닌 이므로 염두에 두어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="dc0d6-133">Bear in mind that these base classes and interfaces are defined by you in the domain model project, so it is your code, not infrastructure code from an ORM like EF.</span></span>

```csharp
// COMPATIBLE WITH ENTITY FRAMEWORK CORE 1.0
// Entity is a custom base class with the ID
public class Order : Entity, IAggregateRoot
{
    public int BuyerId { get; private set; }
    public DateTime OrderDate { get; private set; }
    public int StatusId { get; private set; }
    public ICollection<OrderItem> OrderItems { get; private set; }
    public Address ShippingAddress { get; private set; }
    public int PaymentId { get; private set; }
    protected Order() { } //Design constraint needed only by EF Core
    public Order(int buyerId, int paymentId)
    {
        BuyerId = buyerId;
        PaymentId = paymentId;
        StatusId = OrderStatus.InProcess.Id;
        OrderDate = DateTime.UtcNow;
        OrderItems = new List<OrderItem>();
    }

    public void AddOrderItem(productName,
        pictureUrl,
        unitPrice,
        discount,
        units)
    {
        //...
        // Domain rules/logic for adding the OrderItem to the order
        // ...
        OrderItem item = new OrderItem(this.Id, ProductId, productName,
            pictureUrl, unitPrice, discount, units);
  
        OrderItems.Add(item);
    }
    // ...
    // Additional methods with domain rules/logic related to the Order aggregate
    // ...
}
```

<span data-ttu-id="dc0d6-134">이 POCO 클래스로 구현 되는 도메인 엔터티는 두는 것이 유용 합니다.</span><span class="sxs-lookup"><span data-stu-id="dc0d6-134">It is important to note that this is a domain entity implemented as a POCO class.</span></span> <span data-ttu-id="dc0d6-135">Entity Framework Core에 대 한 직접 종속성 또는 다른 인프라 프레임 워크 없을지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="dc0d6-135">It does not have any direct dependency on Entity Framework Core or any other infrastructure framework.</span></span> <span data-ttu-id="dc0d6-136">이 구현은 그 속도가, 방금 C\# 도메인 모델을 구현 하는 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="dc0d6-136">This implementation is as it should be, just C\# code implementing a domain model.</span></span>

<span data-ttu-id="dc0d6-137">또한 클래스 IAggregateRoot 이라는 인터페이스도 데코레이팅되 어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dc0d6-137">In addition, the class is decorated with an interface named IAggregateRoot.</span></span> <span data-ttu-id="dc0d6-138">해당 인터페이스는 라고도 하는 빈 인터페이스는 *표시 인터페이스*, 즉 바로을이 엔터티 클래스는 또한 집계 루트를 나타내는 데 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="dc0d6-138">That interface is an empty interface, sometimes called a *marker interface*, that is used just to indicate that this entity class is also an aggregate root.</span></span>

<span data-ttu-id="dc0d6-139">표시 인터페이스 안티패턴;로 간주 경우가 됩니다. 그러나 특히 해당 인터페이스 수 발전 하 고 하는 경우는 클래스를 표시 하는 방법은 이기도 합니다.</span><span class="sxs-lookup"><span data-stu-id="dc0d6-139">A marker interface is sometimes considered as an anti-pattern; however, it is also a clean way to mark a class, especially when that interface might be evolving.</span></span> <span data-ttu-id="dc0d6-140">특성의 표식에 대해 다른 선택 될 수 있지만 기본 클래스 (엔터티) 클래스는 집계 특성 표시 하는 대신 IAggregate 인터페이스 옆에 있는 참조 보다 빠릅니다.</span><span class="sxs-lookup"><span data-stu-id="dc0d6-140">An attribute could be the other choice for the marker, but it is quicker to see the base class (Entity) next to the IAggregate interface instead of putting an Aggregate attribute marker above the class.</span></span> <span data-ttu-id="dc0d6-141">어떤 경우 든 것이 기본 설정의 metter입니다.</span><span class="sxs-lookup"><span data-stu-id="dc0d6-141">It is a metter of preferences, in any case.</span></span>

<span data-ttu-id="dc0d6-142">일관성와 관련 된 대부분의 코드는 집계 엔터티의 비즈니스 규칙 (예: AddOrderItem OrderItem 개체는 집계를 추가 하는 경우)의 순서 집계 루트 클래스의 메서드로 구현 해야 하는 집계 루트 것 .</span><span class="sxs-lookup"><span data-stu-id="dc0d6-142">Having an aggregate root means that most of the code related to consistency and business rules of the aggregate’s entities should be implemented as methods in the Order aggregate root class (for example, AddOrderItem when adding an OrderItem object to the aggregate).</span></span> <span data-ttu-id="dc0d6-143">만들기 또는 독립적으로 또는 직접; OrderItems 개체를 업데이트 해야 AggregateRoot 클래스 컨트롤과 해당 자식 엔터티에 대 한 업데이트 작업의 일관성을 유지 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="dc0d6-143">You should not create or update OrderItems objects independently or directly; the AggregateRoot class must keep control and consistency of any update operation against its child entities.</span></span>

<span data-ttu-id="dc0d6-144">해야 하는 예를 들어 *하지* 명령 처리기 메서드 또는 응용 프로그램 계층 클래스에서 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="dc0d6-144">For example, you should *not* do the following from any command handler method or application layer class:</span></span>

```csharp
// WRONG ACCORDING TO DDD PATTERNS – CODE AT THE APPLICATION LAYER OR
// COMMAND HANDLERS
// Code in command handler methods or Web API controllers
//... (WRONG) Some code with business logic out of the domain classes ...
OrderItem myNewOrderItem = new OrderItem(orderId, productId, productName,
    pictureUrl, unitPrice, discount, units);

//... (WRONG) Accessing the OrderItems colletion directly from the application layer // or command handlers
myOrder.OrderItems.Add(myNewOrderItem);
//...
```

<span data-ttu-id="dc0d6-145">이 경우 Add 메서드는 순수 하 게 OrderItems 컬렉션에 직접 액세스할 수 있는 데이터를 추가 하려면 작업.</span><span class="sxs-lookup"><span data-stu-id="dc0d6-145">In this case, the Add method is purely an operation to add data, with direct access to the OrderItems collection.</span></span> <span data-ttu-id="dc0d6-146">따라서 대부분의 도메인 논리, 규칙 또는 유효성 검사 관련 된 자식 엔터티를 사용 하 여 작업 (명령 처리기 및 Web API 컨트롤러) 응용 프로그램 계층 간에 고르게입니다.</span><span class="sxs-lookup"><span data-stu-id="dc0d6-146">Therefore, most of the domain logic, rules, or validations related to that operation with the child entities will be spread across the application layer (command handlers and Web API controllers).</span></span>

<span data-ttu-id="dc0d6-147">집계 루트 주위 전환 되는 경우에 고정, 그 유효성을 확인 하거나 일관성 집계 루트 보장할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="dc0d6-147">If you go around the aggregate root, the aggregate root cannot guarantee its invariants, its validity, or its consistency.</span></span> <span data-ttu-id="dc0d6-148">결국 코드 또는 트랜잭션 스크립트 코드를 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="dc0d6-148">Eventually you will have spaghetti code or transactional script code.</span></span>

<span data-ttu-id="dc0d6-149">DDD 패턴을 수행 하려면 엔터티 해야 public setter에에서는 모든 엔터티 속성.</span><span class="sxs-lookup"><span data-stu-id="dc0d6-149">To follow DDD patterns, entities must not have public setters in any entity property.</span></span> <span data-ttu-id="dc0d6-150">엔터티의 변경 내용은 엔터티에 수행 하는 변경에 대 한 명시적 유비쿼터스 언어를 사용 하 여 명시적 메서드에 따라 결정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="dc0d6-150">Changes in an entity should be driven by explicit methods with explicit ubiquitous language about the change they are performing in the entity.</span></span>

<span data-ttu-id="dc0d6-151">또한 컬렉션 (예: 주문 항목)는 엔터티 내에서 읽기 전용 속성 해야 (AsReadOnly 메서드 뒷부분에서 설명).</span><span class="sxs-lookup"><span data-stu-id="dc0d6-151">Furthermore, collections within the entity (like the order items) should be read-only properties (the AsReadOnly method explained later).</span></span> <span data-ttu-id="dc0d6-152">집계 루트 클래스 메서드 또는 자식 엔터티 메서드 내 에서만 업데이트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dc0d6-152">You should be able to update it only from within the aggregate root class methods or the child entity methods.</span></span>

<span data-ttu-id="dc0d6-153">순서 집계 루트에 대 한 코드에서 볼 수 있습니다, 모든 setter 해야 전용 또는 읽기 전용이 이상 외부적으로 해당 자식 엔터티 또는 엔터티의 데이터에 대해 어떠한 작업 엔터티 클래스의 메서드를 통해 수행할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="dc0d6-153">As you can see in the code for the Order aggregate root, all setters should be private or at least read-only externally, so that any operation against the entity’s data or its child entities has to be performed through methods in the entity class.</span></span> <span data-ttu-id="dc0d6-154">이 제어 되 고 개체 지향적인 방식으로 트랜잭션 스크립트 코드를 구현 하는 대신 일관성을 유지 합니다.</span><span class="sxs-lookup"><span data-stu-id="dc0d6-154">This maintains consistency in a controlled and object-oriented way instead of implementing transactional script code.</span></span>

<span data-ttu-id="dc0d6-155">다음 코드 조각에서는 순서 집계에 OrderItem 개체를 추가 하는 작업을 코딩 하는 적절 한 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="dc0d6-155">The following code snippet shows the proper way to code the task of adding an OrderItem object to the Order aggregate.</span></span>

```csharp
// RIGHT ACCORDING TO DDD--CODE AT THE APPLICATION LAYER OR COMMAND HANDLERS
// The code in command handlers or WebAPI controllers, related only to application stuff
// There is NO code here related to OrderItem object’s business logic
myOrder.AddOrderItem(productId, productName, pictureUrl, unitPrice, discount, units);

// The code related to OrderItem params validations or domain rules should
// be WITHIN the AddOrderItem method.

//...
```

<span data-ttu-id="dc0d6-156">이 코드 조각에서 유효성을 검사 하거나 논리 OrderItem 개체 만들기와 관련 된 대부분 순서 집계 루트에 의해 제어 됩니다-AddOrderItem 메서드에서-유효성 검사 및 논리 특히 관련 된 다른 요소에 집계 합니다.</span><span class="sxs-lookup"><span data-stu-id="dc0d6-156">In this snippet, most of the validations or logic related to the creation of an OrderItem object will be under the control of the Order aggregate root—in the AddOrderItem method—especially validations and logic related to other elements in the aggregate.</span></span> <span data-ttu-id="dc0d6-157">예를 들어, 동일한 제품 항목 AddOrderItem 여러 번 호출의 결과로 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dc0d6-157">For instance, you might get the same product item as the result of multiple calls to AddOrderItem.</span></span> <span data-ttu-id="dc0d6-158">해당 메서드의 제품 항목을 검토 하 고 OrderItem 있는 개체를 여러 장치에 동일한 제품 항목을 통합 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dc0d6-158">In that method, you could examine the product items and consolidate the same product items into a single OrderItem object with several units.</span></span> <span data-ttu-id="dc0d6-159">또한 다양 한 할인 금액 있지만 제품 ID가 동일한, 더 높은 할인을 적용 가능성이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="dc0d6-159">Additionally, if there are different discount amounts but the product ID is the same, you would likely apply the higher discount.</span></span> <span data-ttu-id="dc0d6-160">이 원칙은 OrderItem 개체에 대 한 다른 도메인 논리에 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="dc0d6-160">This principle applies to any other domain logic for the OrderItem object.</span></span>

<span data-ttu-id="dc0d6-161">또한 새 OrderItem(params) 작업 또한 제어 되며 순서 집계 루트에서 AddOrderItem 메서드로 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="dc0d6-161">In addition, the new OrderItem(params) operation will also be controlled and performed by the AddOrderItem method from the Order aggregate root.</span></span> <span data-ttu-id="dc0d6-162">따라서 대부분의 논리 또는 유효성 검사 관련 작업 (특히 모든 다른 자식 엔터티 간의 일관성에 영향을 주는)이 집계 루트 내에서 한 곳에 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="dc0d6-162">Therefore, most of the logic or validations related to that operation (especially anything that impacts the consistency between other child entities) will be in a single place within the aggregate root.</span></span> <span data-ttu-id="dc0d6-163">집계 루트 패턴의 최종 목적은입니다.</span><span class="sxs-lookup"><span data-stu-id="dc0d6-163">That is the ultimate purpose of the aggregate root pattern.</span></span>

<span data-ttu-id="dc0d6-164">Entity Framework 1.1을 사용 하면 DDD 엔터티 수를 보다 잘 표현할 수 있다는 Entity Framework Core 1.1의 새로운 기능 중 하나 이므로 [필드에 매핑](https://docs.microsoft.com/ef/core/modeling/backing-field) 속성 외에도 합니다.</span><span class="sxs-lookup"><span data-stu-id="dc0d6-164">When you use Entity Framework 1.1, a DDD entity can be better expressed because one of the new features of Entity Framework Core 1.1 is that it allows [mapping to fields](https://docs.microsoft.com/ef/core/modeling/backing-field) in addition to properties.</span></span> <span data-ttu-id="dc0d6-165">자식 엔터티 또는 값 개체의 컬렉션을 보호 하는 경우에 유용 합니다.</span><span class="sxs-lookup"><span data-stu-id="dc0d6-165">This is useful when protecting collections of child entities or value objects.</span></span> <span data-ttu-id="dc0d6-166">이 향상 된이 기능 속성 대신 간단한 private 필드를 사용할 수 있습니다 및 필드 컬렉션에 업데이트를 적용 공용 메서드를 구현 하 고 AsReadOnly 메서드를 통해 읽기 전용 액세스를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="dc0d6-166">With this enhancement, you can use simple private fields instead of properties and you can implement any update to the field collection in public methods and provide read-only access through the AsReadOnly method.</span></span>

<span data-ttu-id="dc0d6-167">따라서만 모든 고정 및 데이터의 일관성을 제어 하기 위해 엔터티 (또는 생성자)의 메서드를 통해 엔터티를 업데이트 하려면 DDD, 속성은 get 접근자만 함께 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="dc0d6-167">In DDD you want to update the entity only through methods in the entity (or the constructor) in order to control any invariant and the consistency of the data, so properties are defined only with a get accessor.</span></span> <span data-ttu-id="dc0d6-168">속성은 전용 필드에 의해 지원 됩니다.</span><span class="sxs-lookup"><span data-stu-id="dc0d6-168">The properties are backed by private fields.</span></span> <span data-ttu-id="dc0d6-169">만 전용 멤버 클래스 내에서 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dc0d6-169">Private members can only be accessed from within the class.</span></span> <span data-ttu-id="dc0d6-170">그러나 위치 1 예외: EF 코어도에 이러한 필드를 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="dc0d6-170">However, there one exception: EF Core needs to set these fields as well.</span></span>

```csharp
// ENTITY FRAMEWORK CORE 1.1 OR LATER
// Entity is a custom base class with the ID
public class Order : Entity, IAggregateRoot
{
    // DDD Patterns comment
    // Using private fields, allowed since EF Core 1.1, is a much better
    // encapsulation aligned with DDD aggregates and domain entities (instead of
    // properties and property collections)
    private bool _someOrderInternalState;
    private DateTime _orderDate;
    public Address Address { get; private set; }
    public Buyer Buyer { get; private set; }
    private int _buyerId;
    public OrderStatus OrderStatus { get; private set; }
    private int _orderStatusId;

    // DDD patterns comment
    // Using a private collection field is better for DDD aggregate encapsulation.
    // OrderItem objects cannot be added from outside the aggregate root
    // directly to the collection, but only through the
    // OrderAggrergateRoot.AddOrderItem method, which includes behavior.
    private readonly List<OrderItem> _orderItems;
    public IEnumerable<OrderItem> OrderItems => _orderItems.AsReadOnly();
    // Using List<>.AsReadOnly()
    // This will create a read-only wrapper around the private list so it is
    // protected against external updates. It's much cheaper than .ToList(),
    // because it will not have to copy all items in a new collection.
    // (Just one heap alloc for the wrapper instance)
    // https://msdn.microsoft.com/en-us/library/e78dcd75(v=vs.110).aspx
    public PaymentMethod PaymentMethod { get; private set; }
    private int _paymentMethodId;

    protected Order() { }

    public Order(int buyerId, int paymentMethodId, Address address)
    {
        _orderItems = new List<OrderItem>();
        _buyerId = buyerId;
        _paymentMethodId = paymentMethodId;
        _orderStatusId = OrderStatus.InProcess.Id;
        _orderDate = DateTime.UtcNow;
        Address = address;
    }

    // DDD patterns comment
    // The Order aggregate root method AddOrderitem() should be the only way
    // to add items to the Order object, so that any behavior (discounts, etc.)
    // and validations are controlled by the aggregate root in order to
    // maintain consistency within the whole aggregate.
    public void AddOrderItem(int productId, string productName, decimal unitPrice,
        decimal discount, string pictureUrl, int units = 1)
    {
        // ...
        // Domain rules/logic here for adding OrderItem objects to the order
        // ...
        OrderItem item = new OrderItem(this.Id, productId, productName,
            pictureUrl, unitPrice, discount, units);
        OrderItems.Add(item);
    }

    // ...
    // Additional methods with domain rules/logic related to the Order aggregate
    // ...
}
```

### <a name="mapping-properties-with-only-get-accessors-to-the-fields-in-the-database-table"></a><span data-ttu-id="dc0d6-171">만 사용 하 여 매핑 속성 get 접근자의 필드에 데이터베이스 테이블에</span><span class="sxs-lookup"><span data-stu-id="dc0d6-171">Mapping properties with only get accessors to the fields in the database table</span></span>

<span data-ttu-id="dc0d6-172">데이터베이스 테이블 열에 속성 매핑은 아니며 도메인 책임은 인프라 및 지 속성 계층의 일부입니다.</span><span class="sxs-lookup"><span data-stu-id="dc0d6-172">Mapping properties to the database table columns is not a domain responsibility, but part of the infrastructure and persistence layer.</span></span> <span data-ttu-id="dc0d6-173">엔터티를 모델링할 수 있습니다 어떻게 관련이 EF 1.1의 새로운 기능에 대해 알고 있으므로 정당한이 여기 언급 합니다.</span><span class="sxs-lookup"><span data-stu-id="dc0d6-173">We mention this here just so you are aware of the new capabilities in EF 1.1 related to how you can model entities.</span></span> <span data-ttu-id="dc0d6-174">이 항목에 대 한 자세한 정보는 인프라 및 지 속성 섹션에 설명 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dc0d6-174">Additional details on this topic are explained in the infrastructure and persistence section.</span></span>

<span data-ttu-id="dc0d6-175">EF 1.0을 사용 하는 경우 내에서 DbContext 해야 데이터베이스 테이블의 실제 필드에는 getter과만 함께 정의 된 속성에 매핑합니다.</span><span class="sxs-lookup"><span data-stu-id="dc0d6-175">When you use EF 1.0, within the DbContext you need to map the properties that are defined only with getters to the actual fields in the database table.</span></span> <span data-ttu-id="dc0d6-176">이 PropertyBuilder 클래스의 HasField 메서드와 수행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="dc0d6-176">This is done with the HasField method of the PropertyBuilder class.</span></span>

### <a name="mapping-fields-without-properties"></a><span data-ttu-id="dc0d6-177">속성 없이 필드 매핑</span><span class="sxs-lookup"><span data-stu-id="dc0d6-177">Mapping fields without properties</span></span>

<span data-ttu-id="dc0d6-178">필드에 열을 매핑할 EF 코어 1.1의 새로운 기능을 것도 가능 속성을 사용 하지 않도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="dc0d6-178">With the new feature in EF Core 1.1 to map columns to fields, it is also possible to not use properties.</span></span> <span data-ttu-id="dc0d6-179">대신 필드에 테이블의 열만 매핑할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dc0d6-179">Instead, you can just map columns from a table to fields.</span></span> <span data-ttu-id="dc0d6-180">이 대 한 일반적인 사용 사례는 전용 필드에 엔터티 외부에서 액세스할 수는 필요 하지 않은 내부 상태에 대 한 합니다.</span><span class="sxs-lookup"><span data-stu-id="dc0d6-180">A common use case for this is private fields for an internal state that does not need to be accessed from outside the entity.</span></span>

<span data-ttu-id="dc0d6-181">예를 들어 앞의 코드 예제에에서는 \_someOrderInternalState 필드에는 setter 또는 getter에 대 한 관련된 속성이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="dc0d6-181">For example, in the preceding code example, the \_someOrderInternalState field has no related property for either a setter or getter.</span></span> <span data-ttu-id="dc0d6-182">해당 필드는도 순서의 비즈니스 논리 내에서 계산 되 고 순서의 방법 중에서 사용 되지만 데이터베이스에 영구 저장 해야 하는 데 필요한 합니다.</span><span class="sxs-lookup"><span data-stu-id="dc0d6-182">That field will also be calculated within the order’s business logic and used from the order’s methods, but it needs to be persisted in the database as well.</span></span> <span data-ttu-id="dc0d6-183">따라서 EF 1.1의 경우 데이터베이스에서 열을 관련된 속성이 없는 필드를 매핑하는 방법</span><span class="sxs-lookup"><span data-stu-id="dc0d6-183">So, in EF 1.1 there is a way to map a field without a related property to a column in the database.</span></span> <span data-ttu-id="dc0d6-184">이에 설명 되어는 [인프라 계층](#the-infrastructure-layer) 이 가이드의 섹션입니다.</span><span class="sxs-lookup"><span data-stu-id="dc0d6-184">This is also explained in the [Infrastructure layer](#the-infrastructure-layer) section of this guide.</span></span>

### <a name="additional-resources"></a><span data-ttu-id="dc0d6-185">추가 리소스</span><span class="sxs-lookup"><span data-stu-id="dc0d6-185">Additional resources</span></span>

-   <span data-ttu-id="dc0d6-186">**Vaughn Vernon. DDD 및 Entity Framework를 사용 하 여 집계를 모델링 합니다.**</span><span class="sxs-lookup"><span data-stu-id="dc0d6-186">**Vaughn Vernon. Modeling Aggregates with DDD and Entity Framework.**</span></span> <span data-ttu-id="dc0d6-187">이것은 *하지* Entity Framework Core 합니다.</span><span class="sxs-lookup"><span data-stu-id="dc0d6-187">Note that this is *not* Entity Framework Core.</span></span>
    [<span data-ttu-id="dc0d6-188">*https://vaughnvernon.co/?p=879*</span><span class="sxs-lookup"><span data-stu-id="dc0d6-188">*https://vaughnvernon.co/?p=879*</span></span>](https://vaughnvernon.co/?p=879)

-   <span data-ttu-id="dc0d6-189">**Julie Lerman 합니다. 도메인 기반 디자인에 대 한 코딩: 데이터 중심 개발자 들에 대 한 팁**
    [*https://msdn.microsoft.com/en-us/magazine/dn342868.aspx*](https://msdn.microsoft.com/en-us/magazine/dn342868.aspx)</span><span class="sxs-lookup"><span data-stu-id="dc0d6-189">**Julie Lerman. Coding for Domain-Driven Design: Tips for Data-Focused Devs**
[*https://msdn.microsoft.com/en-us/magazine/dn342868.aspx*](https://msdn.microsoft.com/en-us/magazine/dn342868.aspx)</span></span>

-   <span data-ttu-id="dc0d6-190">**Udi Dahan 합니다. 완벽 하 게 만드는 방법에는 도메인 모델 캡슐화**
    [*http://udidahan.com/2008/02/29/how-to-create-fully-encapsulated-domain-models/*](http://udidahan.com/2008/02/29/how-to-create-fully-encapsulated-domain-models/)</span><span class="sxs-lookup"><span data-stu-id="dc0d6-190">**Udi Dahan. How to create fully encapsulated Domain Models**
[*http://udidahan.com/2008/02/29/how-to-create-fully-encapsulated-domain-models/*](http://udidahan.com/2008/02/29/how-to-create-fully-encapsulated-domain-models/)</span></span>


>[!div class="step-by-step"]
<span data-ttu-id="dc0d6-191">[이전] (마이크로 서비스-도메인-model.md) [다음] (seedwork-domain-model-base-classes-interfaces.md)</span><span class="sxs-lookup"><span data-stu-id="dc0d6-191">[Previous] (microservice-domain-model.md) [Next] (seedwork-domain-model-base-classes-interfaces.md)</span></span>
