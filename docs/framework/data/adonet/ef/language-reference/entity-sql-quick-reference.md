---
title: "Entity SQL 빠른 참조"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e53dad9e-5e83-426e-abb4-be3e78e3d6dc
caps.latest.revision: "2"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: 14d666624ac4572956364b3db3fd5ee7aad8799b
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="entity-sql-quick-reference"></a><span data-ttu-id="9ca2c-102">Entity SQL 빠른 참조</span><span class="sxs-lookup"><span data-stu-id="9ca2c-102">Entity SQL Quick Reference</span></span>
<span data-ttu-id="9ca2c-103">이 항목에서는 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] 쿼리에 대한 빠른 참조를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="9ca2c-103">This topic provides a quick reference to [!INCLUDE[esql](../../../../../../includes/esql-md.md)] queries.</span></span> <span data-ttu-id="9ca2c-104">이 항목의 쿼리는 AdventureWorks Sales 모델을 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="9ca2c-104">The queries in this topic are based on the AdventureWorks Sales model.</span></span>  
  
## <a name="literals"></a><span data-ttu-id="9ca2c-105">리터럴</span><span class="sxs-lookup"><span data-stu-id="9ca2c-105">Literals</span></span>  
  
### <a name="string"></a><span data-ttu-id="9ca2c-106">문자열</span><span class="sxs-lookup"><span data-stu-id="9ca2c-106">String</span></span>  
 <span data-ttu-id="9ca2c-107">유니코드 문자열 리터럴과 유니코드가 아닌 문자열 리터럴이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9ca2c-107">There are Unicode and non-Unicode character string literals.</span></span> <span data-ttu-id="9ca2c-108">유니코드 문자열은 N이 붙습니다. 예를 들어 `N'hello'`합니다.</span><span class="sxs-lookup"><span data-stu-id="9ca2c-108">Unicode strings are prepended with N. For example, `N'hello'`.</span></span>  
  
 <span data-ttu-id="9ca2c-109">다음은 비유니코드 문자열 리터럴의 예제입니다.</span><span class="sxs-lookup"><span data-stu-id="9ca2c-109">The following is an example of a Non-Unicode string literal:</span></span>  
  
```  
'hello'  
--same as  
"hello"  
```  
  
 <span data-ttu-id="9ca2c-110">출력:</span><span class="sxs-lookup"><span data-stu-id="9ca2c-110">Output:</span></span>  
  
|<span data-ttu-id="9ca2c-111">값</span><span class="sxs-lookup"><span data-stu-id="9ca2c-111">Value</span></span>|  
|-----------|  
|<span data-ttu-id="9ca2c-112">hello</span><span class="sxs-lookup"><span data-stu-id="9ca2c-112">hello</span></span>|  
  
### <a name="datetime"></a><span data-ttu-id="9ca2c-113">DateTime</span><span class="sxs-lookup"><span data-stu-id="9ca2c-113">DateTime</span></span>  
 <span data-ttu-id="9ca2c-114">DateTime 리터럴에서는 날짜와 시간 부분 모두 필수 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="9ca2c-114">In DateTime literals, both date and time parts are mandatory.</span></span> <span data-ttu-id="9ca2c-115">기본값은 없습니다.</span><span class="sxs-lookup"><span data-stu-id="9ca2c-115">There are no default values.</span></span>  
  
 <span data-ttu-id="9ca2c-116">예제:</span><span class="sxs-lookup"><span data-stu-id="9ca2c-116">Example:</span></span>  
  
```  
DATETIME '2006-12-25 01:01:00.000'   
--same as  
DATETIME '2006-12-25 01:01'  
```  
  
 <span data-ttu-id="9ca2c-117">출력:</span><span class="sxs-lookup"><span data-stu-id="9ca2c-117">Output:</span></span>  
  
|<span data-ttu-id="9ca2c-118">값</span><span class="sxs-lookup"><span data-stu-id="9ca2c-118">Value</span></span>|  
|-----------|  
|<span data-ttu-id="9ca2c-119">12/25/2006 1:01:00 AM</span><span class="sxs-lookup"><span data-stu-id="9ca2c-119">12/25/2006 1:01:00 AM</span></span>|  
  
### <a name="integer"></a><span data-ttu-id="9ca2c-120">Integer</span><span class="sxs-lookup"><span data-stu-id="9ca2c-120">Integer</span></span>  
 <span data-ttu-id="9ca2c-121">Integer 리터럴은 Int32(123), UInt32(123U), Int64(123L) 및 UInt64(123UL) 형식일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9ca2c-121">Integer literals can be of type Int32 (123), UInt32 (123U), Int64 (123L), and UInt64 (123UL).</span></span>  
  
 <span data-ttu-id="9ca2c-122">예제:</span><span class="sxs-lookup"><span data-stu-id="9ca2c-122">Example:</span></span>  
  
```  
--a collection of integers  
{1, 2, 3}  
```  
  
 <span data-ttu-id="9ca2c-123">출력:</span><span class="sxs-lookup"><span data-stu-id="9ca2c-123">Output:</span></span>  
  
|<span data-ttu-id="9ca2c-124">값</span><span class="sxs-lookup"><span data-stu-id="9ca2c-124">Value</span></span>|  
|-----------|  
|<span data-ttu-id="9ca2c-125">1</span><span class="sxs-lookup"><span data-stu-id="9ca2c-125">1</span></span>|  
|<span data-ttu-id="9ca2c-126">2</span><span class="sxs-lookup"><span data-stu-id="9ca2c-126">2</span></span>|  
|<span data-ttu-id="9ca2c-127">3</span><span class="sxs-lookup"><span data-stu-id="9ca2c-127">3</span></span>|  
  
### <a name="other"></a><span data-ttu-id="9ca2c-128">기타</span><span class="sxs-lookup"><span data-stu-id="9ca2c-128">Other</span></span>  
 <span data-ttu-id="9ca2c-129">[!INCLUDE[esql](../../../../../../includes/esql-md.md)]에서 지원되는 기타 리터럴은 Guid, Binary, Float/Double, Decimal, `null` 등입니다.</span><span class="sxs-lookup"><span data-stu-id="9ca2c-129">Other literals supported by [!INCLUDE[esql](../../../../../../includes/esql-md.md)] are Guid, Binary, Float/Double, Decimal, and `null`.</span></span> <span data-ttu-id="9ca2c-130">[!INCLUDE[esql](../../../../../../includes/esql-md.md)]에서 Null 리터럴은 개념적 모델의 다른 모든 형식과 호환 가능한 것으로 간주됩니다.</span><span class="sxs-lookup"><span data-stu-id="9ca2c-130">Null literals in [!INCLUDE[esql](../../../../../../includes/esql-md.md)] are considered to be compatible with every other type in the conceptual model.</span></span>  
  
## <a name="type-constructors"></a><span data-ttu-id="9ca2c-131">형식 생성자</span><span class="sxs-lookup"><span data-stu-id="9ca2c-131">Type Constructors</span></span>  
  
### <a name="row"></a><span data-ttu-id="9ca2c-132">ROW</span><span class="sxs-lookup"><span data-stu-id="9ca2c-132">ROW</span></span>  
 <span data-ttu-id="9ca2c-133">[행](../../../../../../docs/framework/data/adonet/ef/language-reference/row-entity-sql.md) 에서 같이 익명, 구조적으로 형식화 된 (레코드) 값을 생성 합니다.`ROW(1 AS myNumber, ‘Name’ AS myName).`</span><span class="sxs-lookup"><span data-stu-id="9ca2c-133">[ROW](../../../../../../docs/framework/data/adonet/ef/language-reference/row-entity-sql.md) constructs an anonymous, structurally-typed (record) value as in: `ROW(1 AS myNumber, ‘Name’ AS myName).`</span></span>  
  
 <span data-ttu-id="9ca2c-134">예제:</span><span class="sxs-lookup"><span data-stu-id="9ca2c-134">Example:</span></span>  
  
```  
SELECT VALUE row (product.ProductID as ProductID, product.Name   
    as ProductName) FROM AdventureWorksEntities.Product AS product  
```  
  
 <span data-ttu-id="9ca2c-135">출력:</span><span class="sxs-lookup"><span data-stu-id="9ca2c-135">Output:</span></span>  
  
|<span data-ttu-id="9ca2c-136">ProductID</span><span class="sxs-lookup"><span data-stu-id="9ca2c-136">ProductID</span></span>|<span data-ttu-id="9ca2c-137">이름</span><span class="sxs-lookup"><span data-stu-id="9ca2c-137">Name</span></span>|  
|---------------|----------|  
|<span data-ttu-id="9ca2c-138">1</span><span class="sxs-lookup"><span data-stu-id="9ca2c-138">1</span></span>|<span data-ttu-id="9ca2c-139">Adjustable Race</span><span class="sxs-lookup"><span data-stu-id="9ca2c-139">Adjustable Race</span></span>|  
|<span data-ttu-id="9ca2c-140">879</span><span class="sxs-lookup"><span data-stu-id="9ca2c-140">879</span></span>|<span data-ttu-id="9ca2c-141">All-Purpose Bike Stand</span><span class="sxs-lookup"><span data-stu-id="9ca2c-141">All-Purpose Bike Stand</span></span>|  
|<span data-ttu-id="9ca2c-142">712</span><span class="sxs-lookup"><span data-stu-id="9ca2c-142">712</span></span>|<span data-ttu-id="9ca2c-143">AWC Logo Cap</span><span class="sxs-lookup"><span data-stu-id="9ca2c-143">AWC Logo Cap</span></span>|  
|<span data-ttu-id="9ca2c-144">...</span><span class="sxs-lookup"><span data-stu-id="9ca2c-144">...</span></span>|<span data-ttu-id="9ca2c-145">...</span><span class="sxs-lookup"><span data-stu-id="9ca2c-145">...</span></span>|  
  
### <a name="multiset"></a><span data-ttu-id="9ca2c-146">MULTISET</span><span class="sxs-lookup"><span data-stu-id="9ca2c-146">MULTISET</span></span>  
 <span data-ttu-id="9ca2c-147">[MULTISET](../../../../../../docs/framework/data/adonet/ef/language-reference/multiset-entity-sql.md) 와 같은 컬렉션을 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="9ca2c-147">[MULTISET](../../../../../../docs/framework/data/adonet/ef/language-reference/multiset-entity-sql.md) constructs collections, such as:</span></span>  
  
 <span data-ttu-id="9ca2c-148">`MULTISET(1,2,2,3)` `--same as`-`{1,2,2,3}.`</span><span class="sxs-lookup"><span data-stu-id="9ca2c-148">`MULTISET(1,2,2,3)` `--same as`-`{1,2,2,3}.`</span></span>  
  
 <span data-ttu-id="9ca2c-149">예제:</span><span class="sxs-lookup"><span data-stu-id="9ca2c-149">Example:</span></span>  
  
```  
SELECT VALUE product FROM AdventureWorksEntities.Product AS product WHERE product.ListPrice IN MultiSet (125, 300)  
```  
  
 <span data-ttu-id="9ca2c-150">출력:</span><span class="sxs-lookup"><span data-stu-id="9ca2c-150">Output:</span></span>  
  
|<span data-ttu-id="9ca2c-151">ProductID</span><span class="sxs-lookup"><span data-stu-id="9ca2c-151">ProductID</span></span>|<span data-ttu-id="9ca2c-152">이름</span><span class="sxs-lookup"><span data-stu-id="9ca2c-152">Name</span></span>|<span data-ttu-id="9ca2c-153">ProductNumber</span><span class="sxs-lookup"><span data-stu-id="9ca2c-153">ProductNumber</span></span>|<span data-ttu-id="9ca2c-154">…</span><span class="sxs-lookup"><span data-stu-id="9ca2c-154">…</span></span>|  
|---------------|----------|-------------------|-------|  
|<span data-ttu-id="9ca2c-155">842</span><span class="sxs-lookup"><span data-stu-id="9ca2c-155">842</span></span>|<span data-ttu-id="9ca2c-156">Touring-Panniers, Large</span><span class="sxs-lookup"><span data-stu-id="9ca2c-156">Touring-Panniers, Large</span></span>|<span data-ttu-id="9ca2c-157">PA-T100</span><span class="sxs-lookup"><span data-stu-id="9ca2c-157">PA-T100</span></span>|<span data-ttu-id="9ca2c-158">…</span><span class="sxs-lookup"><span data-stu-id="9ca2c-158">…</span></span>|  
  
### <a name="object"></a><span data-ttu-id="9ca2c-159">Object</span><span class="sxs-lookup"><span data-stu-id="9ca2c-159">Object</span></span>  
 <span data-ttu-id="9ca2c-160">[형식 생성자를 명명 된](../../../../../../docs/framework/data/adonet/ef/language-reference/named-type-constructor-entity-sql.md) 와 같은 명명 된 사용자 정의 개체를 생성 `person("abc", 12)`합니다.</span><span class="sxs-lookup"><span data-stu-id="9ca2c-160">[Named Type Constructor](../../../../../../docs/framework/data/adonet/ef/language-reference/named-type-constructor-entity-sql.md) constructs (named) user-defined objects, such as `person("abc", 12)`.</span></span>  
  
 <span data-ttu-id="9ca2c-161">예제:</span><span class="sxs-lookup"><span data-stu-id="9ca2c-161">Example:</span></span>  
  
```  
SELECT VALUE AdventureWorksModel.SalesOrderDetail (o.SalesOrderDetailID, o.CarrierTrackingNumber, o.OrderQty,   
o.ProductID, o.SpecialOfferID, o.UnitPrice, o.UnitPriceDiscount,   
o.rowguid, o.ModifiedDate) FROM AdventureWorksEntities.SalesOrderDetail   
AS o  
```  
  
 <span data-ttu-id="9ca2c-162">출력:</span><span class="sxs-lookup"><span data-stu-id="9ca2c-162">Output:</span></span>  
  
|<span data-ttu-id="9ca2c-163">SalesOrderDetailID</span><span class="sxs-lookup"><span data-stu-id="9ca2c-163">SalesOrderDetailID</span></span>|<span data-ttu-id="9ca2c-164">CarrierTrackingNumber</span><span class="sxs-lookup"><span data-stu-id="9ca2c-164">CarrierTrackingNumber</span></span>|<span data-ttu-id="9ca2c-165">OrderQty</span><span class="sxs-lookup"><span data-stu-id="9ca2c-165">OrderQty</span></span>|<span data-ttu-id="9ca2c-166">ProductID</span><span class="sxs-lookup"><span data-stu-id="9ca2c-166">ProductID</span></span>|<span data-ttu-id="9ca2c-167">...</span><span class="sxs-lookup"><span data-stu-id="9ca2c-167">...</span></span>|  
|------------------------|---------------------------|--------------|---------------|---------|  
|<span data-ttu-id="9ca2c-168">1</span><span class="sxs-lookup"><span data-stu-id="9ca2c-168">1</span></span>|<span data-ttu-id="9ca2c-169">4911-403C-98</span><span class="sxs-lookup"><span data-stu-id="9ca2c-169">4911-403C-98</span></span>|<span data-ttu-id="9ca2c-170">1</span><span class="sxs-lookup"><span data-stu-id="9ca2c-170">1</span></span>|<span data-ttu-id="9ca2c-171">776</span><span class="sxs-lookup"><span data-stu-id="9ca2c-171">776</span></span>|<span data-ttu-id="9ca2c-172">...</span><span class="sxs-lookup"><span data-stu-id="9ca2c-172">...</span></span>|  
|<span data-ttu-id="9ca2c-173">2</span><span class="sxs-lookup"><span data-stu-id="9ca2c-173">2</span></span>|<span data-ttu-id="9ca2c-174">4911-403C-98</span><span class="sxs-lookup"><span data-stu-id="9ca2c-174">4911-403C-98</span></span>|<span data-ttu-id="9ca2c-175">3</span><span class="sxs-lookup"><span data-stu-id="9ca2c-175">3</span></span>|<span data-ttu-id="9ca2c-176">777</span><span class="sxs-lookup"><span data-stu-id="9ca2c-176">777</span></span>|<span data-ttu-id="9ca2c-177">...</span><span class="sxs-lookup"><span data-stu-id="9ca2c-177">...</span></span>|  
|<span data-ttu-id="9ca2c-178">...</span><span class="sxs-lookup"><span data-stu-id="9ca2c-178">...</span></span>|<span data-ttu-id="9ca2c-179">...</span><span class="sxs-lookup"><span data-stu-id="9ca2c-179">...</span></span>|<span data-ttu-id="9ca2c-180">...</span><span class="sxs-lookup"><span data-stu-id="9ca2c-180">...</span></span>|<span data-ttu-id="9ca2c-181">...</span><span class="sxs-lookup"><span data-stu-id="9ca2c-181">...</span></span>|<span data-ttu-id="9ca2c-182">...</span><span class="sxs-lookup"><span data-stu-id="9ca2c-182">...</span></span>|  
  
## <a name="references"></a><span data-ttu-id="9ca2c-183">참조</span><span class="sxs-lookup"><span data-stu-id="9ca2c-183">References</span></span>  
  
### <a name="ref"></a><span data-ttu-id="9ca2c-184">REF</span><span class="sxs-lookup"><span data-stu-id="9ca2c-184">REF</span></span>  
 <span data-ttu-id="9ca2c-185">[REF](../../../../../../docs/framework/data/adonet/ef/language-reference/ref-entity-sql.md) 엔터티 형식 인스턴스에 대 한 참조를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="9ca2c-185">[REF](../../../../../../docs/framework/data/adonet/ef/language-reference/ref-entity-sql.md) creates a reference to an entity type instance.</span></span> <span data-ttu-id="9ca2c-186">예를 들어, 다음 쿼리는 주문 엔터티 집합의 개별 주문 엔터티에 대한 참조를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="9ca2c-186">For example, the following query returns references to each Order entity in the Orders entity set:</span></span>  
  
```  
SELECT REF(o) AS OrderID FROM Orders AS o  
```  
  
 <span data-ttu-id="9ca2c-187">출력:</span><span class="sxs-lookup"><span data-stu-id="9ca2c-187">Output:</span></span>  
  
|<span data-ttu-id="9ca2c-188">값</span><span class="sxs-lookup"><span data-stu-id="9ca2c-188">Value</span></span>|  
|-----------|  
|<span data-ttu-id="9ca2c-189">1</span><span class="sxs-lookup"><span data-stu-id="9ca2c-189">1</span></span>|  
|<span data-ttu-id="9ca2c-190">2</span><span class="sxs-lookup"><span data-stu-id="9ca2c-190">2</span></span>|  
|<span data-ttu-id="9ca2c-191">3</span><span class="sxs-lookup"><span data-stu-id="9ca2c-191">3</span></span>|  
|<span data-ttu-id="9ca2c-192">...</span><span class="sxs-lookup"><span data-stu-id="9ca2c-192">...</span></span>|  
  
 <span data-ttu-id="9ca2c-193">다음 예제에서는 속성 추출 연산자(.)를 사용하여 엔터티의 속성에 액세스합니다.</span><span class="sxs-lookup"><span data-stu-id="9ca2c-193">The following example uses the property extraction operator (.) to access a property of an entity.</span></span> <span data-ttu-id="9ca2c-194">속성 추출 연산자가 사용되면 해당 참조가 자동으로 역참조됩니다.</span><span class="sxs-lookup"><span data-stu-id="9ca2c-194">When the property extraction operator is used, the reference is automatically dereferenced.</span></span>  
  
 <span data-ttu-id="9ca2c-195">예제:</span><span class="sxs-lookup"><span data-stu-id="9ca2c-195">Example:</span></span>  
  
```  
SELECT VALUE REF(p).Name FROM   
    AdventureWorksEntities.Product as p  
```  
  
 <span data-ttu-id="9ca2c-196">출력:</span><span class="sxs-lookup"><span data-stu-id="9ca2c-196">Output:</span></span>  
  
|<span data-ttu-id="9ca2c-197">값</span><span class="sxs-lookup"><span data-stu-id="9ca2c-197">Value</span></span>|  
|-----------|  
|<span data-ttu-id="9ca2c-198">Adjustable Race</span><span class="sxs-lookup"><span data-stu-id="9ca2c-198">Adjustable Race</span></span>|  
|<span data-ttu-id="9ca2c-199">All-Purpose Bike Stand</span><span class="sxs-lookup"><span data-stu-id="9ca2c-199">All-Purpose Bike Stand</span></span>|  
|<span data-ttu-id="9ca2c-200">AWC Logo Cap</span><span class="sxs-lookup"><span data-stu-id="9ca2c-200">AWC Logo Cap</span></span>|  
|<span data-ttu-id="9ca2c-201">...</span><span class="sxs-lookup"><span data-stu-id="9ca2c-201">...</span></span>|  
  
### <a name="deref"></a><span data-ttu-id="9ca2c-202">DEREF</span><span class="sxs-lookup"><span data-stu-id="9ca2c-202">DEREF</span></span>  
 <span data-ttu-id="9ca2c-203">[DEREF](../../../../../../docs/framework/data/adonet/ef/language-reference/deref-entity-sql.md) 역참조 참조 값과 해당 결과 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="9ca2c-203">[DEREF](../../../../../../docs/framework/data/adonet/ef/language-reference/deref-entity-sql.md) dereferences a reference value and produces the result of that dereference.</span></span> <span data-ttu-id="9ca2c-204">예를 들어, `SELECT DEREF(o2.r) FROM (SELECT REF(o) AS r FROM LOB.Orders AS o) AS o2` 쿼리는 Orders 엔터티 집합의 개별 Order별로 Order 엔터티를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="9ca2c-204">For example, the following query produces the Order entities for each Order in the Orders entity set: `SELECT DEREF(o2.r) FROM (SELECT REF(o) AS r FROM LOB.Orders AS o) AS o2`..</span></span>  
  
 <span data-ttu-id="9ca2c-205">예제:</span><span class="sxs-lookup"><span data-stu-id="9ca2c-205">Example:</span></span>  
  
```  
SELECT VALUE DEREF(REF(p)).Name FROM   
    AdventureWorksEntities.Product as p  
```  
  
 <span data-ttu-id="9ca2c-206">출력:</span><span class="sxs-lookup"><span data-stu-id="9ca2c-206">Output:</span></span>  
  
|<span data-ttu-id="9ca2c-207">값</span><span class="sxs-lookup"><span data-stu-id="9ca2c-207">Value</span></span>|  
|-----------|  
|<span data-ttu-id="9ca2c-208">Adjustable Race</span><span class="sxs-lookup"><span data-stu-id="9ca2c-208">Adjustable Race</span></span>|  
|<span data-ttu-id="9ca2c-209">All-Purpose Bike Stand</span><span class="sxs-lookup"><span data-stu-id="9ca2c-209">All-Purpose Bike Stand</span></span>|  
|<span data-ttu-id="9ca2c-210">AWC Logo Cap</span><span class="sxs-lookup"><span data-stu-id="9ca2c-210">AWC Logo Cap</span></span>|  
|<span data-ttu-id="9ca2c-211">...</span><span class="sxs-lookup"><span data-stu-id="9ca2c-211">...</span></span>|  
  
### <a name="createref-and-key"></a><span data-ttu-id="9ca2c-212">CREATEREF 및 KEY</span><span class="sxs-lookup"><span data-stu-id="9ca2c-212">CREATEREF AND KEY</span></span>  
 <span data-ttu-id="9ca2c-213">[CREATEREF](../../../../../../docs/framework/data/adonet/ef/language-reference/createref-entity-sql.md) 는 키를 전달 하는 참조를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="9ca2c-213">[CREATEREF](../../../../../../docs/framework/data/adonet/ef/language-reference/createref-entity-sql.md) creates a reference passing a key.</span></span> <span data-ttu-id="9ca2c-214">[키](../../../../../../docs/framework/data/adonet/ef/language-reference/key-entity-sql.md) 형식 참조가 있는 식의 키 부분을 추출 합니다.</span><span class="sxs-lookup"><span data-stu-id="9ca2c-214">[KEY](../../../../../../docs/framework/data/adonet/ef/language-reference/key-entity-sql.md) extracts the key portion of an expression with type reference.</span></span>  
  
 <span data-ttu-id="9ca2c-215">예제:</span><span class="sxs-lookup"><span data-stu-id="9ca2c-215">Example:</span></span>  
  
```  
SELECT VALUE Key(CreateRef(AdventureWorksEntities.Product, row(p.ProductID)))   
    FROM AdventureWorksEntities.Product as p  
```  
  
 <span data-ttu-id="9ca2c-216">출력:</span><span class="sxs-lookup"><span data-stu-id="9ca2c-216">Output:</span></span>  
  
|<span data-ttu-id="9ca2c-217">ProductID</span><span class="sxs-lookup"><span data-stu-id="9ca2c-217">ProductID</span></span>|  
|---------------|  
|<span data-ttu-id="9ca2c-218">980</span><span class="sxs-lookup"><span data-stu-id="9ca2c-218">980</span></span>|  
|<span data-ttu-id="9ca2c-219">365</span><span class="sxs-lookup"><span data-stu-id="9ca2c-219">365</span></span>|  
|<span data-ttu-id="9ca2c-220">771</span><span class="sxs-lookup"><span data-stu-id="9ca2c-220">771</span></span>|  
|<span data-ttu-id="9ca2c-221">...</span><span class="sxs-lookup"><span data-stu-id="9ca2c-221">...</span></span>|  
  
## <a name="functions"></a><span data-ttu-id="9ca2c-222">함수</span><span class="sxs-lookup"><span data-stu-id="9ca2c-222">Functions</span></span>  
  
### <a name="canonical"></a><span data-ttu-id="9ca2c-223">정식</span><span class="sxs-lookup"><span data-stu-id="9ca2c-223">Canonical</span></span>  
 <span data-ttu-id="9ca2c-224">에 대 한 네임 스페이스 [정식 함수](../../../../../../docs/framework/data/adonet/ef/language-reference/canonical-functions.md) 에서 같이 Edm은 `Edm.Length("string")`합니다.</span><span class="sxs-lookup"><span data-stu-id="9ca2c-224">The namespace for [canonical functions](../../../../../../docs/framework/data/adonet/ef/language-reference/canonical-functions.md) is Edm, as in `Edm.Length("string")`.</span></span> <span data-ttu-id="9ca2c-225">정식 함수와 이름이 같은 함수가 포함된 다른 네임스페이스를 가져오지 않는 한, 네임스페이스를 지정할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="9ca2c-225">You do not have to specify the namespace unless another namespace is imported that contains a function with the same name as a canonical function.</span></span> <span data-ttu-id="9ca2c-226">두 네임스페이스의 함수가 동일한 경우 사용자는 전체 이름을 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9ca2c-226">If two namespaces have the same function, the user should specific the full name.</span></span>  
  
 <span data-ttu-id="9ca2c-227">예제:</span><span class="sxs-lookup"><span data-stu-id="9ca2c-227">Example:</span></span>  
  
```  
SELECT Length(c. FirstName) As NameLen FROM   
    AdventureWorksEntities.Contact AS c   
    WHERE c.ContactID BETWEEN 10 AND 12  
```  
  
 <span data-ttu-id="9ca2c-228">출력:</span><span class="sxs-lookup"><span data-stu-id="9ca2c-228">Output:</span></span>  
  
|<span data-ttu-id="9ca2c-229">NameLen</span><span class="sxs-lookup"><span data-stu-id="9ca2c-229">NameLen</span></span>|  
|-------------|  
|<span data-ttu-id="9ca2c-230">6</span><span class="sxs-lookup"><span data-stu-id="9ca2c-230">6</span></span>|  
|<span data-ttu-id="9ca2c-231">6</span><span class="sxs-lookup"><span data-stu-id="9ca2c-231">6</span></span>|  
|<span data-ttu-id="9ca2c-232">5</span><span class="sxs-lookup"><span data-stu-id="9ca2c-232">5</span></span>|  
  
### <a name="microsoft-provider-specific"></a><span data-ttu-id="9ca2c-233">Microsoft 공급자 특정</span><span class="sxs-lookup"><span data-stu-id="9ca2c-233">Microsoft Provider-Specific</span></span>  
 <span data-ttu-id="9ca2c-234">[Microsoft 공급자 특정 함수](../../../../../../docs/framework/data/adonet/ef/sqlclient-for-ef-functions.md) 에 `SqlServer` 네임 스페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="9ca2c-234">[Microsoft provider-specific functions](../../../../../../docs/framework/data/adonet/ef/sqlclient-for-ef-functions.md) are in the `SqlServer` namespace.</span></span>  
  
 <span data-ttu-id="9ca2c-235">예제:</span><span class="sxs-lookup"><span data-stu-id="9ca2c-235">Example:</span></span>  
  
```  
SELECT SqlServer.LEN(c.EmailAddress) As EmailLen FROM   
    AdventureWorksEntities.Contact AS c WHERE   
    c.ContactID BETWEEN 10 AND 12  
```  
  
 <span data-ttu-id="9ca2c-236">출력:</span><span class="sxs-lookup"><span data-stu-id="9ca2c-236">Output:</span></span>  
  
|<span data-ttu-id="9ca2c-237">EmailLen</span><span class="sxs-lookup"><span data-stu-id="9ca2c-237">EmailLen</span></span>|  
|--------------|  
|<span data-ttu-id="9ca2c-238">27</span><span class="sxs-lookup"><span data-stu-id="9ca2c-238">27</span></span>|  
|<span data-ttu-id="9ca2c-239">27</span><span class="sxs-lookup"><span data-stu-id="9ca2c-239">27</span></span>|  
|<span data-ttu-id="9ca2c-240">26</span><span class="sxs-lookup"><span data-stu-id="9ca2c-240">26</span></span>|  
  
## <a name="namespaces"></a><span data-ttu-id="9ca2c-241">네임스페이스</span><span class="sxs-lookup"><span data-stu-id="9ca2c-241">Namespaces</span></span>  
 <span data-ttu-id="9ca2c-242">[사용 하 여](../../../../../../docs/framework/data/adonet/ef/language-reference/using-entity-sql.md) 쿼리 식에 사용 되는 네임 스페이스를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="9ca2c-242">[USING](../../../../../../docs/framework/data/adonet/ef/language-reference/using-entity-sql.md) specifies namespaces used in a query expression.</span></span>  
  
 <span data-ttu-id="9ca2c-243">예제:</span><span class="sxs-lookup"><span data-stu-id="9ca2c-243">Example:</span></span>  
  
```  
using SqlServer; LOWER('AA');  
```  
  
 <span data-ttu-id="9ca2c-244">출력:</span><span class="sxs-lookup"><span data-stu-id="9ca2c-244">Output:</span></span>  
  
|<span data-ttu-id="9ca2c-245">값</span><span class="sxs-lookup"><span data-stu-id="9ca2c-245">Value</span></span>|  
|-----------|  
|<span data-ttu-id="9ca2c-246">aa</span><span class="sxs-lookup"><span data-stu-id="9ca2c-246">aa</span></span>|  
  
## <a name="paging"></a><span data-ttu-id="9ca2c-247">페이징</span><span class="sxs-lookup"><span data-stu-id="9ca2c-247">Paging</span></span>  
 <span data-ttu-id="9ca2c-248">페이징 선언 하 여 표현할 수 있습니다는 [SKIP](../../../../../../docs/framework/data/adonet/ef/language-reference/skip-entity-sql.md) 및 [제한](../../../../../../docs/framework/data/adonet/ef/language-reference/limit-entity-sql.md) 하위 절에는 [ORDER BY](../../../../../../docs/framework/data/adonet/ef/language-reference/order-by-entity-sql.md) 절.</span><span class="sxs-lookup"><span data-stu-id="9ca2c-248">Paging can be expressed by declaring a [SKIP](../../../../../../docs/framework/data/adonet/ef/language-reference/skip-entity-sql.md) and [LIMIT](../../../../../../docs/framework/data/adonet/ef/language-reference/limit-entity-sql.md) sub-clauses to the [ORDER BY](../../../../../../docs/framework/data/adonet/ef/language-reference/order-by-entity-sql.md) clause.</span></span>  
  
 <span data-ttu-id="9ca2c-249">예제:</span><span class="sxs-lookup"><span data-stu-id="9ca2c-249">Example:</span></span>  
  
```  
SELECT c.ContactID as ID, c.LastName as Name FROM   
    AdventureWorks.Contact AS c ORDER BY c.ContactID SKIP 9 LIMIT 3;  
```  
  
 <span data-ttu-id="9ca2c-250">출력:</span><span class="sxs-lookup"><span data-stu-id="9ca2c-250">Output:</span></span>  
  
|<span data-ttu-id="9ca2c-251">ID</span><span class="sxs-lookup"><span data-stu-id="9ca2c-251">ID</span></span>|<span data-ttu-id="9ca2c-252">이름</span><span class="sxs-lookup"><span data-stu-id="9ca2c-252">Name</span></span>|  
|--------|----------|  
|<span data-ttu-id="9ca2c-253">10</span><span class="sxs-lookup"><span data-stu-id="9ca2c-253">10</span></span>|<span data-ttu-id="9ca2c-254">Adina</span><span class="sxs-lookup"><span data-stu-id="9ca2c-254">Adina</span></span>|  
|<span data-ttu-id="9ca2c-255">11</span><span class="sxs-lookup"><span data-stu-id="9ca2c-255">11</span></span>|<span data-ttu-id="9ca2c-256">Agcaoili</span><span class="sxs-lookup"><span data-stu-id="9ca2c-256">Agcaoili</span></span>|  
|<span data-ttu-id="9ca2c-257">12</span><span class="sxs-lookup"><span data-stu-id="9ca2c-257">12</span></span>|<span data-ttu-id="9ca2c-258">Aguilar</span><span class="sxs-lookup"><span data-stu-id="9ca2c-258">Aguilar</span></span>|  
  
## <a name="grouping"></a><span data-ttu-id="9ca2c-259">그룹화</span><span class="sxs-lookup"><span data-stu-id="9ca2c-259">Grouping</span></span>  
 <span data-ttu-id="9ca2c-260">[GROUPING BY](../../../../../../docs/framework/data/adonet/ef/language-reference/group-by-entity-sql.md) 쿼리에서 반환 된 개체를 그룹 지정 ([선택](../../../../../../docs/framework/data/adonet/ef/language-reference/select-entity-sql.md)) 배치 하는 식.</span><span class="sxs-lookup"><span data-stu-id="9ca2c-260">[GROUPING BY](../../../../../../docs/framework/data/adonet/ef/language-reference/group-by-entity-sql.md) specifies groups into which objects returned by a query ([SELECT](../../../../../../docs/framework/data/adonet/ef/language-reference/select-entity-sql.md)) expression are to be placed.</span></span>  
  
 <span data-ttu-id="9ca2c-261">예제:</span><span class="sxs-lookup"><span data-stu-id="9ca2c-261">Example:</span></span>  
  
```  
SELECT VALUE name FROM AdventureWorksEntities.Product as P   
    GROUP BY P.Name HAVING MAX(P.ListPrice) > 5  
```  
  
 <span data-ttu-id="9ca2c-262">출력:</span><span class="sxs-lookup"><span data-stu-id="9ca2c-262">Output:</span></span>  
  
|<span data-ttu-id="9ca2c-263">name</span><span class="sxs-lookup"><span data-stu-id="9ca2c-263">name</span></span>|  
|----------|  
|<span data-ttu-id="9ca2c-264">LL Mountain Seat Assembly</span><span class="sxs-lookup"><span data-stu-id="9ca2c-264">LL Mountain Seat Assembly</span></span>|  
|<span data-ttu-id="9ca2c-265">ML Mountain Seat Assembly</span><span class="sxs-lookup"><span data-stu-id="9ca2c-265">ML Mountain Seat Assembly</span></span>|  
|<span data-ttu-id="9ca2c-266">HL Mountain Seat Assembly</span><span class="sxs-lookup"><span data-stu-id="9ca2c-266">HL Mountain Seat Assembly</span></span>|  
|<span data-ttu-id="9ca2c-267">...</span><span class="sxs-lookup"><span data-stu-id="9ca2c-267">...</span></span>|  
  
## <a name="navigation"></a><span data-ttu-id="9ca2c-268">탐색</span><span class="sxs-lookup"><span data-stu-id="9ca2c-268">Navigation</span></span>  
 <span data-ttu-id="9ca2c-269">관계 탐색 연산자를 사용하여 엔터티 간의(시작 End에서 끝 End) 관계를 탐색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9ca2c-269">The relationship navigation operator allows you to navigate over the relationship from one entity (from end) to another (to end).</span></span> <span data-ttu-id="9ca2c-270">[NAVIGATE](../../../../../../docs/framework/data/adonet/ef/language-reference/navigate-entity-sql.md) 으로 한정 된 관계형 형식을 하나 \<네임 스페이스 >.\< 관계 유형 이름 >.</span><span class="sxs-lookup"><span data-stu-id="9ca2c-270">[NAVIGATE](../../../../../../docs/framework/data/adonet/ef/language-reference/navigate-entity-sql.md) takes the relationship type qualified as \<namespace>.\<relationship type name>.</span></span> <span data-ttu-id="9ca2c-271">탐색 Ref 반환\<T > 경우의 카디널리티는 종료 하는 1입니다.</span><span class="sxs-lookup"><span data-stu-id="9ca2c-271">Navigate returns Ref\<T> if the cardinality of the to end is 1.</span></span> <span data-ttu-id="9ca2c-272">하는 경우의 카디널리티는 종료 하려면 n을 컬렉션은 < Ref\<T >> 반환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9ca2c-272">If the cardinality of the to end is n, the Collection<Ref\<T>> will be returned.</span></span>  
  
 <span data-ttu-id="9ca2c-273">예제:</span><span class="sxs-lookup"><span data-stu-id="9ca2c-273">Example:</span></span>  
  
```  
SELECT a.AddressID, (SELECT VALUE DEREF(v) FROM   
    NAVIGATE(a, AdventureWorksModel.FK_SalesOrderHeader_Address_BillToAddressID) AS v)   
    FROM AdventureWorksEntities.Address AS a  
```  
  
 <span data-ttu-id="9ca2c-274">출력:</span><span class="sxs-lookup"><span data-stu-id="9ca2c-274">Output:</span></span>  
  
|<span data-ttu-id="9ca2c-275">AddressID</span><span class="sxs-lookup"><span data-stu-id="9ca2c-275">AddressID</span></span>|  
|---------------|  
|<span data-ttu-id="9ca2c-276">1</span><span class="sxs-lookup"><span data-stu-id="9ca2c-276">1</span></span>|  
|<span data-ttu-id="9ca2c-277">2</span><span class="sxs-lookup"><span data-stu-id="9ca2c-277">2</span></span>|  
|<span data-ttu-id="9ca2c-278">3</span><span class="sxs-lookup"><span data-stu-id="9ca2c-278">3</span></span>|  
|<span data-ttu-id="9ca2c-279">...</span><span class="sxs-lookup"><span data-stu-id="9ca2c-279">...</span></span>|  
  
## <a name="select-value-and-select"></a><span data-ttu-id="9ca2c-280">SELECT VALUE 및 SELECT</span><span class="sxs-lookup"><span data-stu-id="9ca2c-280">SELECT VALUE AND SELECT</span></span>  
  
### <a name="select-value"></a><span data-ttu-id="9ca2c-281">SELECT VALUE</span><span class="sxs-lookup"><span data-stu-id="9ca2c-281">SELECT VALUE</span></span>  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)]<span data-ttu-id="9ca2c-282">에서는 암시적 행 생성을 건너뛰도록 SELECT VALUE 절을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="9ca2c-282"> provides the SELECT VALUE clause to skip the implicit row construction.</span></span> <span data-ttu-id="9ca2c-283">SELECT VALUE 절에 항목을 하나만 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9ca2c-283">Only one item can be specified in a SELECT VALUE clause.</span></span> <span data-ttu-id="9ca2c-284">이러한 절을 사용 하 고 SELECT 절의 항목 주위에 없는 행 래퍼가 생성 원하는 모양의 컬렉션이 만들어질 수 있습니다 예: `SELECT VALUE a`합니다.</span><span class="sxs-lookup"><span data-stu-id="9ca2c-284">When such a clause is used, no row wrapper is constructed around the items in the SELECT clause, and a collection of the desired shape can be produced, for example: `SELECT VALUE a`.</span></span>  
  
 <span data-ttu-id="9ca2c-285">예제:</span><span class="sxs-lookup"><span data-stu-id="9ca2c-285">Example:</span></span>  
  
```  
SELECT VALUE p.Name FROM AdventureWorksEntities.Product as p  
```  
  
 <span data-ttu-id="9ca2c-286">출력:</span><span class="sxs-lookup"><span data-stu-id="9ca2c-286">Output:</span></span>  
  
|<span data-ttu-id="9ca2c-287">이름</span><span class="sxs-lookup"><span data-stu-id="9ca2c-287">Name</span></span>|  
|----------|  
|<span data-ttu-id="9ca2c-288">Adjustable Race</span><span class="sxs-lookup"><span data-stu-id="9ca2c-288">Adjustable Race</span></span>|  
|<span data-ttu-id="9ca2c-289">All-Purpose Bike Stand</span><span class="sxs-lookup"><span data-stu-id="9ca2c-289">All-Purpose Bike Stand</span></span>|  
|<span data-ttu-id="9ca2c-290">AWC Logo Cap</span><span class="sxs-lookup"><span data-stu-id="9ca2c-290">AWC Logo Cap</span></span>|  
|<span data-ttu-id="9ca2c-291">...</span><span class="sxs-lookup"><span data-stu-id="9ca2c-291">...</span></span>|  
  
### <a name="select"></a><span data-ttu-id="9ca2c-292">SELECT</span><span class="sxs-lookup"><span data-stu-id="9ca2c-292">SELECT</span></span>  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)]<span data-ttu-id="9ca2c-293">에서는 임의의 행을 만드는 행 생성자도 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="9ca2c-293"> also provides the row constructor to construct arbitrary rows.</span></span> <span data-ttu-id="9ca2c-294">SELECT는 `SELECT a, b, c`와 같이 프로젝션의 요소를 하나 이상 사용하며 필드가 있는 데이터 레코드를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="9ca2c-294">SELECT takes one or more elements in the projection and results in a data record with fields, for example: `SELECT a, b, c`.</span></span>  
  
 <span data-ttu-id="9ca2c-295">예제:</span><span class="sxs-lookup"><span data-stu-id="9ca2c-295">Example:</span></span>  
  
 <span data-ttu-id="9ca2c-296">SELECT p.Name, p.ProductID FROM AdventureWorksEntities.Product as p 출력:</span><span class="sxs-lookup"><span data-stu-id="9ca2c-296">SELECT p.Name, p.ProductID FROM AdventureWorksEntities.Product as p Output:</span></span>  
  
|<span data-ttu-id="9ca2c-297">이름</span><span class="sxs-lookup"><span data-stu-id="9ca2c-297">Name</span></span>|<span data-ttu-id="9ca2c-298">ProductID</span><span class="sxs-lookup"><span data-stu-id="9ca2c-298">ProductID</span></span>|  
|----------|---------------|  
|<span data-ttu-id="9ca2c-299">Adjustable Race</span><span class="sxs-lookup"><span data-stu-id="9ca2c-299">Adjustable Race</span></span>|<span data-ttu-id="9ca2c-300">1</span><span class="sxs-lookup"><span data-stu-id="9ca2c-300">1</span></span>|  
|<span data-ttu-id="9ca2c-301">All-Purpose Bike Stand</span><span class="sxs-lookup"><span data-stu-id="9ca2c-301">All-Purpose Bike Stand</span></span>|<span data-ttu-id="9ca2c-302">879</span><span class="sxs-lookup"><span data-stu-id="9ca2c-302">879</span></span>|  
|<span data-ttu-id="9ca2c-303">AWC Logo Cap</span><span class="sxs-lookup"><span data-stu-id="9ca2c-303">AWC Logo Cap</span></span>|<span data-ttu-id="9ca2c-304">712</span><span class="sxs-lookup"><span data-stu-id="9ca2c-304">712</span></span>|  
|<span data-ttu-id="9ca2c-305">...</span><span class="sxs-lookup"><span data-stu-id="9ca2c-305">...</span></span>|<span data-ttu-id="9ca2c-306">...</span><span class="sxs-lookup"><span data-stu-id="9ca2c-306">...</span></span>|  
  
## <a name="case-expression"></a><span data-ttu-id="9ca2c-307">CASE 식</span><span class="sxs-lookup"><span data-stu-id="9ca2c-307">CASE EXPRESSION</span></span>  
 <span data-ttu-id="9ca2c-308">[case 식](../../../../../../docs/framework/data/adonet/ef/language-reference/case-entity-sql.md) 결과 결정 하는 부울 식 집합을 계산 합니다.</span><span class="sxs-lookup"><span data-stu-id="9ca2c-308">The [case expression](../../../../../../docs/framework/data/adonet/ef/language-reference/case-entity-sql.md) evaluates a set of Boolean expressions to determine the result.</span></span>  
  
 <span data-ttu-id="9ca2c-309">예제:</span><span class="sxs-lookup"><span data-stu-id="9ca2c-309">Example:</span></span>  
  
```  
CASE WHEN AVG({25,12,11}) < 100 THEN TRUE ELSE FALSE END  
```  
  
 <span data-ttu-id="9ca2c-310">출력:</span><span class="sxs-lookup"><span data-stu-id="9ca2c-310">Output:</span></span>  
  
|<span data-ttu-id="9ca2c-311">값</span><span class="sxs-lookup"><span data-stu-id="9ca2c-311">Value</span></span>|  
|-----------|  
|<span data-ttu-id="9ca2c-312">true</span><span class="sxs-lookup"><span data-stu-id="9ca2c-312">TRUE</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="9ca2c-313">참고 항목</span><span class="sxs-lookup"><span data-stu-id="9ca2c-313">See Also</span></span>  
 [<span data-ttu-id="9ca2c-314">엔터티 SQL 참조</span><span class="sxs-lookup"><span data-stu-id="9ca2c-314">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)  
 [<span data-ttu-id="9ca2c-315">Entity SQL 개요</span><span class="sxs-lookup"><span data-stu-id="9ca2c-315">Entity SQL Overview</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-overview.md)
