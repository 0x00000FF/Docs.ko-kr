---
title: TREAT(Entity SQL)
ms.date: 03/30/2017
ms.assetid: 5b77f156-55de-4cb4-8154-87f707d4c635
ms.openlocfilehash: 82e1ad172148065ce90628b7e23578623cc7199a
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54632610"
---
# <a name="treat-entity-sql"></a><span data-ttu-id="c252b-102">TREAT(Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="c252b-102">TREAT (Entity SQL)</span></span>
<span data-ttu-id="c252b-103">특정 기본 형식의 개체를 지정된 파생 형식의 개체로 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="c252b-103">Treats an object of a particular base type as an object of the specified derived type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c252b-104">구문</span><span class="sxs-lookup"><span data-stu-id="c252b-104">Syntax</span></span>  
  
```  
TREAT ( expression as type)  
```  
  
## <a name="arguments"></a><span data-ttu-id="c252b-105">인수</span><span class="sxs-lookup"><span data-stu-id="c252b-105">Arguments</span></span>  
 `expression`  
 <span data-ttu-id="c252b-106">엔터티를 반환하는 모든 유효한 쿼리 식입니다.</span><span class="sxs-lookup"><span data-stu-id="c252b-106">Any valid query expression that returns an entity.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c252b-107">지정된 식의 형식이 지정된 데이터 형식의 하위 형식이어야 하거나, 데이터 형식이 식 형식의 하위 형식이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c252b-107">The type of the specified expression must be a subtype of the specified data type, or the data type must be a subtype of the type of expression.</span></span>  
  
 `type`  
 <span data-ttu-id="c252b-108">엔터티 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="c252b-108">An entity type.</span></span> <span data-ttu-id="c252b-109">형식은 네임스페이스로 한정되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c252b-109">The type must be qualified by a namespace.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c252b-110">지정된 식이 지정된 데이터 형식의 하위 형식이어야 하거나, 데이터 형식이 식의 하위 형식이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c252b-110">The specified expression must be a subtype of the specified data type, or the data type must be a subtype of the expression.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c252b-111">반환 값</span><span class="sxs-lookup"><span data-stu-id="c252b-111">Return Value</span></span>  
 <span data-ttu-id="c252b-112">지정된 데이터 형식의 값입니다.</span><span class="sxs-lookup"><span data-stu-id="c252b-112">A value of the specified data type.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c252b-113">설명</span><span class="sxs-lookup"><span data-stu-id="c252b-113">Remarks</span></span>  
 <span data-ttu-id="c252b-114">TREAT는 관련 클래스 간에 업캐스팅을 수행하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="c252b-114">TREAT is used to perform upcasting between related classes.</span></span> <span data-ttu-id="c252b-115">예를 들어, `Employee` 가 `Person` 에서 파생되고 p가 `Person`형식인 경우 `TREAT(p AS NamespaceName.Employee)` 는 일반 `Person` 인스턴스를 `Employee`로 업캐스팅합니다. 다시 말해서, p를 `Employee`로 취급할 수 있게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c252b-115">For example, if `Employee` derives from `Person` and p is of type `Person`, `TREAT(p AS NamespaceName.Employee)` upcasts a generic `Person` instance to `Employee`; that is, it allows you to treat p as `Employee`.</span></span>  
  
 <span data-ttu-id="c252b-116">TREAT는 다음과 같이 쿼리할 수 있는 상속 시나리오에서 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="c252b-116">TREAT is used in inheritance scenarios where you can do a query like the following:</span></span>  
  
```  
SELECT TREAT(p AS NamespaceName.Employee)  
FROM ContainerName.Person AS p  
WHERE p IS OF (NamespaceName.Employee)   
```  
  
 <span data-ttu-id="c252b-117">이 쿼리는 `Person` 엔터티를 `Employee` 형식으로 업캐스팅합니다.</span><span class="sxs-lookup"><span data-stu-id="c252b-117">This query upcasts `Person` entities to the `Employee` type.</span></span> <span data-ttu-id="c252b-118">p의 값이 실제로 `Employee`형식이 아닌 경우 식의 값은 `null`입니다.</span><span class="sxs-lookup"><span data-stu-id="c252b-118">If the value of p is not actually of type `Employee`, the expression yields the value `null`.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c252b-119">지정된 된 식 `Employee` 지정 된 데이터 형식의 하위 형식 이어야 `Person`, 또는 데이터 형식이 식의 하위 형식 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c252b-119">The specified expression `Employee` must be a subtype of the specified data type `Person`, or the data type must be a subtype of the expression.</span></span> <span data-ttu-id="c252b-120">그렇지 않으면 식에서 컴파일 시간 오류가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="c252b-120">Otherwise, the expression will result in a compile-time error.</span></span>  
  
 <span data-ttu-id="c252b-121">다음 표에서는 일반 패턴 및 비교적 특수한 패턴에 대한 TREAT의 동작을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="c252b-121">The following table shows the behavior of treat over some typical patterns and some less common patterns.</span></span> <span data-ttu-id="c252b-122">공급자 호출 이전에 모든 예외가 클라이언트 측에서 throw됩니다.</span><span class="sxs-lookup"><span data-stu-id="c252b-122">All exceptions are thrown from the client side before the provider gets invoked:</span></span>  
  
|<span data-ttu-id="c252b-123">패턴</span><span class="sxs-lookup"><span data-stu-id="c252b-123">Pattern</span></span>|<span data-ttu-id="c252b-124">동작</span><span class="sxs-lookup"><span data-stu-id="c252b-124">Behavior</span></span>|  
|-------------|--------------|  
|`TREAT (null AS EntityType)`|<span data-ttu-id="c252b-125">`DbNull`를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="c252b-125">Returns `DbNull`.</span></span>|  
|`TREAT (null AS ComplexType)`|<span data-ttu-id="c252b-126">예외를 throw합니다.</span><span class="sxs-lookup"><span data-stu-id="c252b-126">Throws an exception.</span></span>|  
|`TREAT (null AS RowType)`|<span data-ttu-id="c252b-127">예외를 throw합니다.</span><span class="sxs-lookup"><span data-stu-id="c252b-127">Throws an exception/</span></span>|  
|`TREAT (EntityType AS EntityType)`|<span data-ttu-id="c252b-128">`EntityType` 또는 `null`을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="c252b-128">Returns `EntityType` or `null`.</span></span>|  
|`TREAT (ComplexType AS ComplexType)`|<span data-ttu-id="c252b-129">예외를 throw합니다.</span><span class="sxs-lookup"><span data-stu-id="c252b-129">Throws an exception.</span></span>|  
|`TREAT (RowType AS RowType)`|<span data-ttu-id="c252b-130">예외를 throw합니다.</span><span class="sxs-lookup"><span data-stu-id="c252b-130">Throws an exception.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="c252b-131">예제</span><span class="sxs-lookup"><span data-stu-id="c252b-131">Example</span></span>  
 <span data-ttu-id="c252b-132">다음 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] 쿼리에서는 TREAT 연산자를 사용하여 Course 형식의 개체를 OnsiteCourse 형식의 개체 컬렉션으로 변환합니다.</span><span class="sxs-lookup"><span data-stu-id="c252b-132">The following [!INCLUDE[esql](../../../../../../includes/esql-md.md)] query uses the TREAT operator to convert an object of the type Course to a collection of objects of the type OnsiteCourse.</span></span> <span data-ttu-id="c252b-133">쿼리는 [School 모델](https://msdn.microsoft.com/library/859a9587-81ea-4a45-9bc0-f8d330e1adac)을 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="c252b-133">The query is based on the [School Model](https://msdn.microsoft.com/library/859a9587-81ea-4a45-9bc0-f8d330e1adac).</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#TREAT_ISOF](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#treat_isof)]  
  
## <a name="see-also"></a><span data-ttu-id="c252b-134">참고자료</span><span class="sxs-lookup"><span data-stu-id="c252b-134">See also</span></span>
- [<span data-ttu-id="c252b-135">엔터티 SQL 참조</span><span class="sxs-lookup"><span data-stu-id="c252b-135">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
- [<span data-ttu-id="c252b-136">null 허용 구조적 형식</span><span class="sxs-lookup"><span data-stu-id="c252b-136">Nullable Structured Types</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/nullable-structured-types-entity-sql.md)
