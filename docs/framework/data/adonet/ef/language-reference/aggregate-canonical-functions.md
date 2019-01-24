---
title: 집계 정식 함수
ms.date: 03/30/2017
ms.assetid: 3bcff826-ca90-41b3-a791-04d6ff0e5085
ms.openlocfilehash: f65557703070a43f586a668903d049a374ef70d3
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54708976"
---
# <a name="aggregate-canonical-functions"></a><span data-ttu-id="388de-102">집계 정식 함수</span><span class="sxs-lookup"><span data-stu-id="388de-102">Aggregate Canonical Functions</span></span>

<span data-ttu-id="388de-103">집계는 일련의 입력 값을 단일 값으로 줄이는 식입니다.</span><span class="sxs-lookup"><span data-stu-id="388de-103">Aggregates are expressions that reduce a series of input values into, for example, a single value.</span></span> <span data-ttu-id="388de-104">집계는 일반적으로 SELECT 식의 GROUP BY 절과 함께 사용되며 사용할 수 있는 위치에 대한 제약 조건이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="388de-104">Aggregates are normally used in conjunction with the GROUP BY clause of the SELECT expression, and there are constraints on where they can be used.</span></span>

## <a name="aggegate-entity-sql-canonical-functions"></a><span data-ttu-id="388de-105">Aggegate Entity SQL 정식 함수</span><span class="sxs-lookup"><span data-stu-id="388de-105">Aggegate Entity SQL canonical functions</span></span>

<span data-ttu-id="388de-106">집계 Entity SQL 정식 함수는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="388de-106">The following are the aggregate Entity SQL canonical functions.</span></span>

### <a name="avgexpression"></a><span data-ttu-id="388de-107">Avg(expression)</span><span class="sxs-lookup"><span data-stu-id="388de-107">Avg(expression)</span></span>

<span data-ttu-id="388de-108">null이 아닌 값의 평균을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="388de-108">Returns the average of the non-null values.</span></span>

<span data-ttu-id="388de-109">**인수**</span><span class="sxs-lookup"><span data-stu-id="388de-109">**Arguments**</span></span>

<span data-ttu-id="388de-110">`Int32`, `Int64`, `Double` 및 `Decimal`입니다.</span><span class="sxs-lookup"><span data-stu-id="388de-110">An `Int32`, `Int64`, `Double`, and `Decimal`.</span></span>

<span data-ttu-id="388de-111">**반환 값**</span><span class="sxs-lookup"><span data-stu-id="388de-111">**Return Value**</span></span>

<span data-ttu-id="388de-112">유형의 `expression`, 또는 `null` 모든 입력된 값이 `null` 값입니다.</span><span class="sxs-lookup"><span data-stu-id="388de-112">The type of `expression`, or `null` if all input values are `null` values.</span></span>

<span data-ttu-id="388de-113">**예제**</span><span class="sxs-lookup"><span data-stu-id="388de-113">**Example**</span></span>

[!code-csharp[DP EntityServices Concepts#EDM_AVG](~/samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#edm_avg)] 
[!code-sql[DP EntityServices Concepts#EDM_AVG](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#edm_avg)]

### <a name="bigcountexpression"></a><span data-ttu-id="388de-114">BigCount(expression)</span><span class="sxs-lookup"><span data-stu-id="388de-114">BigCount(expression)</span></span>

<span data-ttu-id="388de-115">null 값과 중복 값을 비롯한 집계의 크기를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="388de-115">Returns the size of the aggregate including null and duplicate values.</span></span>

<span data-ttu-id="388de-116">**인수**</span><span class="sxs-lookup"><span data-stu-id="388de-116">**Arguments**</span></span>

<span data-ttu-id="388de-117">모든 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="388de-117">Any type.</span></span>

<span data-ttu-id="388de-118">**반환 값**</span><span class="sxs-lookup"><span data-stu-id="388de-118">**Return Value**</span></span>

<span data-ttu-id="388de-119">`Int64`입니다.</span><span class="sxs-lookup"><span data-stu-id="388de-119">An `Int64`.</span></span>

<span data-ttu-id="388de-120">**예제**</span><span class="sxs-lookup"><span data-stu-id="388de-120">**Example**</span></span>

[!code-csharp[DP EntityServices Concepts#EDM_BIGCOUNT](~/samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#edm_bigcount)] 
[!code-sql[DP EntityServices Concepts#EDM_BIGCOUNT](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#edm_bigcount)]

### <a name="countexpression"></a><span data-ttu-id="388de-121">Count(expression)</span><span class="sxs-lookup"><span data-stu-id="388de-121">Count(expression)</span></span> 

<span data-ttu-id="388de-122">null 값과 중복 값을 비롯한 집계의 크기를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="388de-122">Returns the size of the aggregate including null and duplicate values.</span></span>

<span data-ttu-id="388de-123">**인수**</span><span class="sxs-lookup"><span data-stu-id="388de-123">**Arguments**</span></span>

<span data-ttu-id="388de-124">모든 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="388de-124">Any type.</span></span>

<span data-ttu-id="388de-125">**반환 값**</span><span class="sxs-lookup"><span data-stu-id="388de-125">**Return Value**</span></span>

<span data-ttu-id="388de-126">`Int32`입니다.</span><span class="sxs-lookup"><span data-stu-id="388de-126">An `Int32`.</span></span>

<span data-ttu-id="388de-127">**예제**</span><span class="sxs-lookup"><span data-stu-id="388de-127">**Example**</span></span>

[!code-csharp[DP EntityServices Concepts#EDM_COUNT](~/samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#edm_count)]
[!code-sql[DP EntityServices Concepts#EDM_COUNT](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#edm_count)]

### <a name="maxexpression"></a><span data-ttu-id="388de-128">Max(expression)</span><span class="sxs-lookup"><span data-stu-id="388de-128">Max(expression)</span></span>

<span data-ttu-id="388de-129">null이 아닌 값의 최대값을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="388de-129">Returns the maximum of the non-null values.</span></span>

<span data-ttu-id="388de-130">**인수**</span><span class="sxs-lookup"><span data-stu-id="388de-130">**Arguments**</span></span>

<span data-ttu-id="388de-131">`Byte`, `Int16`, `Int32`, `Int64`, `Byte`, `Single`, `Double`, `Decimal`, `DateTime`, `DateTimeOffset`, `Time`, `String`, `Binary`입니다.</span><span class="sxs-lookup"><span data-stu-id="388de-131">A `Byte`, `Int16`, `Int32`, `Int64`, `Byte`, `Single`, `Double`, `Decimal`, `DateTime`, `DateTimeOffset`, `Time`, `String`, `Binary`.</span></span>

<span data-ttu-id="388de-132">**반환 값**</span><span class="sxs-lookup"><span data-stu-id="388de-132">**Return Value**</span></span>

<span data-ttu-id="388de-133">유형의 `expression`, 또는 `null` 모든 입력된 값이 `null` 값입니다.</span><span class="sxs-lookup"><span data-stu-id="388de-133">The type of `expression`, or `null` if all input values are `null` values.</span></span>

<span data-ttu-id="388de-134">**예제**</span><span class="sxs-lookup"><span data-stu-id="388de-134">**Example**</span></span>

[!code-csharp[DP EntityServices Concepts#EDM_MAX](~/samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#edm_max)]
[!code-sql[DP EntityServices Concepts#EDM_MAX](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#edm_max)]

### <a name="minexpression"></a><span data-ttu-id="388de-135">Min(expression)</span><span class="sxs-lookup"><span data-stu-id="388de-135">Min(expression)</span></span>

<span data-ttu-id="388de-136">null이 아닌 값의 최소값을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="388de-136">Returns the minimum of the non-null values.</span></span>

<span data-ttu-id="388de-137">**인수**</span><span class="sxs-lookup"><span data-stu-id="388de-137">**Arguments**</span></span>

<span data-ttu-id="388de-138">`Byte`, `Int16`, `Int32`, `Int64`, `Byte`, `Single`, `Double`, `Decimal`, `DateTime`, `DateTimeOffset`, `Time`, `String`, `Binary`입니다.</span><span class="sxs-lookup"><span data-stu-id="388de-138">A `Byte`, `Int16`, `Int32`, `Int64`, `Byte`, `Single`, `Double`, `Decimal`, `DateTime`, `DateTimeOffset`, `Time`, `String`, `Binary`.</span></span>

<span data-ttu-id="388de-139">**반환 값**</span><span class="sxs-lookup"><span data-stu-id="388de-139">**Return Value**</span></span>

<span data-ttu-id="388de-140">유형의 `expression`, 또는 `null` 모든 입력된 값이 `null` 값입니다.</span><span class="sxs-lookup"><span data-stu-id="388de-140">The type of `expression`, or `null` if all input values are `null` values.</span></span>

<span data-ttu-id="388de-141">**예제**</span><span class="sxs-lookup"><span data-stu-id="388de-141">**Example**</span></span>

[!code-csharp[DP EntityServices Concepts#EDM_MIN](~/samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#edm_min)]
[!code-sql[DP EntityServices Concepts#EDM_MIN](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#edm_min)]

### <a name="stdevexpression"></a><span data-ttu-id="388de-142">StDev(expression)</span><span class="sxs-lookup"><span data-stu-id="388de-142">StDev(expression)</span></span>

<span data-ttu-id="388de-143">null이 아닌 값의 표준 편차를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="388de-143">Returns the standard deviation of the non-null values.</span></span>

<span data-ttu-id="388de-144">**인수**</span><span class="sxs-lookup"><span data-stu-id="388de-144">**Arguments**</span></span>

<span data-ttu-id="388de-145">`Int32`, `Int64`, `Double`, `Decimal`입니다.</span><span class="sxs-lookup"><span data-stu-id="388de-145">An `Int32`, `Int64`, `Double`, `Decimal`.</span></span>

<span data-ttu-id="388de-146">**반환 값**</span><span class="sxs-lookup"><span data-stu-id="388de-146">**Return Value**</span></span>

<span data-ttu-id="388de-147">`Double`</span><span class="sxs-lookup"><span data-stu-id="388de-147">A `Double`.</span></span> <span data-ttu-id="388de-148">모든 입력 값이 `Null` 값인 경우 `null`입니다.</span><span class="sxs-lookup"><span data-stu-id="388de-148">`Null`, if all input values are `null` values.</span></span>

<span data-ttu-id="388de-149">**예제**</span><span class="sxs-lookup"><span data-stu-id="388de-149">**Example**</span></span>

[!code-csharp[DP EntityServices Concepts#EDM_STDEV](~/samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#edm_stdev)]
[!code-sql[DP EntityServices Concepts#EDM_STDEV](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#edm_stdev)]

### <a name="stdevpexpression"></a><span data-ttu-id="388de-150">StDevP(expression)</span><span class="sxs-lookup"><span data-stu-id="388de-150">StDevP(expression)</span></span>

<span data-ttu-id="388de-151">모든 값의 모집단에 대한 표준 편차를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="388de-151">Returns the standard deviation for the population of all values.</span></span>

<span data-ttu-id="388de-152">**인수**</span><span class="sxs-lookup"><span data-stu-id="388de-152">**Arguments**</span></span>

<span data-ttu-id="388de-153">`Int32`, `Int64`, `Double`, `Decimal`입니다.</span><span class="sxs-lookup"><span data-stu-id="388de-153">An `Int32`, `Int64`, `Double`, `Decimal`.</span></span>

<span data-ttu-id="388de-154">**반환 값**</span><span class="sxs-lookup"><span data-stu-id="388de-154">**Return Value**</span></span>

<span data-ttu-id="388de-155">A `Double`, 또는 `null` 모든 입력된 값이 `null` 값입니다.</span><span class="sxs-lookup"><span data-stu-id="388de-155">A `Double`, or `null` if all input values are `null` values.</span></span>

<span data-ttu-id="388de-156">**예제**</span><span class="sxs-lookup"><span data-stu-id="388de-156">**Example**</span></span>

[!code-csharp[DP EntityServices Concepts#EDM_STDEVP](~/samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#edm_stdevp)]
[!code-sql[DP EntityServices Concepts#EDM_STDEVP](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#edm_stdevp)]

### <a name="sumexpression"></a><span data-ttu-id="388de-157">Sum(expression)</span><span class="sxs-lookup"><span data-stu-id="388de-157">Sum(expression)</span></span>

<span data-ttu-id="388de-158">null이 아닌 값의 합계를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="388de-158">Returns the sum of the non-null values.</span></span>

<span data-ttu-id="388de-159">**인수**</span><span class="sxs-lookup"><span data-stu-id="388de-159">**Arguments**</span></span>

<span data-ttu-id="388de-160">`Int32`, `Int64`, `Double`, `Decimal`입니다.</span><span class="sxs-lookup"><span data-stu-id="388de-160">An `Int32`, `Int64`, `Double`, `Decimal`.</span></span>

<span data-ttu-id="388de-161">**반환 값**</span><span class="sxs-lookup"><span data-stu-id="388de-161">**Return Value**</span></span>

<span data-ttu-id="388de-162">A `Double`, 또는 `null` 모든 입력된 값이 `null` 값입니다.</span><span class="sxs-lookup"><span data-stu-id="388de-162">A `Double`, or `null` if all input values are `null` values.</span></span>

<span data-ttu-id="388de-163">**예제**</span><span class="sxs-lookup"><span data-stu-id="388de-163">**Example**</span></span>

[!code-csharp[DP EntityServices Concepts#EDM_SUM](~/samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#edm_sum)]
[!code-sql[DP EntityServices Concepts#EDM_SUM](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#edm_sum)]

### <a name="varexpression"></a><span data-ttu-id="388de-164">Var(expression)</span><span class="sxs-lookup"><span data-stu-id="388de-164">Var(expression)</span></span>

<span data-ttu-id="388de-165">null이 아닌 모든 값의 분산을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="388de-165">Returns the variance of all non-null values.</span></span>

<span data-ttu-id="388de-166">**인수**</span><span class="sxs-lookup"><span data-stu-id="388de-166">**Arguments**</span></span>

<span data-ttu-id="388de-167">`Int32`, `Int64`, `Double`, `Decimal`입니다.</span><span class="sxs-lookup"><span data-stu-id="388de-167">An `Int32`, `Int64`, `Double`, `Decimal`.</span></span>

<span data-ttu-id="388de-168">**반환 값**</span><span class="sxs-lookup"><span data-stu-id="388de-168">**Return Value**</span></span>

<span data-ttu-id="388de-169">A `Double`, 또는 `null` 모든 입력된 값이 `null` 값입니다.</span><span class="sxs-lookup"><span data-stu-id="388de-169">A `Double`, or `null` if all input values are `null` values.</span></span>

<span data-ttu-id="388de-170">**예제**</span><span class="sxs-lookup"><span data-stu-id="388de-170">**Example**</span></span>

[!code-csharp[DP EntityServices Concepts#EDM_VAR](~/samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#edm_var)]
[!code-sql[DP EntityServices Concepts#EDM_VAR](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#edm_var)]

### <a name="varpexpression"></a><span data-ttu-id="388de-171">VarP(expression)</span><span class="sxs-lookup"><span data-stu-id="388de-171">VarP(expression)</span></span>

<span data-ttu-id="388de-172">null이 아닌 모든 값의 모집단에 대한 분산을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="388de-172">Returns the variance for the population of all non-null values.</span></span>

<span data-ttu-id="388de-173">**인수**</span><span class="sxs-lookup"><span data-stu-id="388de-173">**Arguments**</span></span>

<span data-ttu-id="388de-174">`Int32`, `Int64`, `Double`, `Decimal`입니다.</span><span class="sxs-lookup"><span data-stu-id="388de-174">An `Int32`, `Int64`, `Double`, `Decimal`.</span></span>

<span data-ttu-id="388de-175">**반환 값**</span><span class="sxs-lookup"><span data-stu-id="388de-175">**Return Value**</span></span>

<span data-ttu-id="388de-176">A `Double`, 또는 `null` 모든 입력된 값이 `null` 값입니다.</span><span class="sxs-lookup"><span data-stu-id="388de-176">A `Double`, or `null` if all input values are `null` values.</span></span>

<span data-ttu-id="388de-177">**예제**</span><span class="sxs-lookup"><span data-stu-id="388de-177">**Example**</span></span>

[!code-csharp[DP EntityServices Concepts#EDM_VARP](~/samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#edm_varp)]
[!code-sql[DP EntityServices Concepts#EDM_VARP](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#edm_varp)] 

<span data-ttu-id="388de-178">동일한 기능을 Microsoft SQL 클라이언트 관리 공급자에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="388de-178">Equivalent functionality is available in the Microsoft SQL Client Managed Provider.</span></span> <span data-ttu-id="388de-179">자세한 내용은 [Entity Framework 함수에 대 한 SqlClient](../../../../../../docs/framework/data/adonet/ef/sqlclient-for-ef-functions.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="388de-179">For more information, see [SqlClient for Entity Framework Functions](../../../../../../docs/framework/data/adonet/ef/sqlclient-for-ef-functions.md).</span></span>

## <a name="collection-based-aggregates"></a><span data-ttu-id="388de-180">컬렉션 기반 집계</span><span class="sxs-lookup"><span data-stu-id="388de-180">Collection-based aggregates</span></span>

<span data-ttu-id="388de-181">컬렉션 기반 집계(컬렉션 함수)는 컬렉션에 대해 작업을 수행하고 값을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="388de-181">Collection-based aggregates (collection functions) operate on collections and return a value.</span></span> <span data-ttu-id="388de-182">예를 들어 주문 모든 주문의 컬렉션인 경우 다음 식 사용 하 여 가장 빠른 운송 날짜를 계산할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="388de-182">For example if ORDERS is a collection of all orders, you can calculate the earliest ship date with the following expression:</span></span>

```sql
min(select value o.ShipDate from LOB.Orders as o)
```

<span data-ttu-id="388de-183">컬렉션 기반 집계 내의 식은 현재 앰비언트 이름 결정 범위 내에서 계산됩니다.</span><span class="sxs-lookup"><span data-stu-id="388de-183">Expressions inside collection-based aggregates are evaluated within the current ambient name-resolution scope.</span></span>

## <a name="group-based-aggregates"></a><span data-ttu-id="388de-184">그룹 기반 집계</span><span class="sxs-lookup"><span data-stu-id="388de-184">Group-based aggregates</span></span>

<span data-ttu-id="388de-185">그룹 기반 집계는 GROUP BY 절에 정의된 대로 그룹에 대해 계산됩니다.</span><span class="sxs-lookup"><span data-stu-id="388de-185">Group-based aggregates are calculated over a group as defined by the GROUP BY clause.</span></span> <span data-ttu-id="388de-186">결과의 각 그룹별로 각 그룹의 요소를 집계 계산에 대한 입력으로 사용하여 개별 집계가 계산됩니다.</span><span class="sxs-lookup"><span data-stu-id="388de-186">For each group in the result, a separate aggregate is calculated by using the elements in each group as input to the aggregate calculation.</span></span> <span data-ttu-id="388de-187">SELECT 식에 GROUP BY 절이 사용되는 경우에는 식 이름, 집계 또는 상수를 그룹화하는 식만 프로젝션 또는 ORDER BY 절에 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="388de-187">When a group-by clause is used in a select expression, only grouping expression names, aggregates, or constant expressions can be present in the projection or order-by clause.</span></span>

<span data-ttu-id="388de-188">다음 예제에서는 각 제품에 대해 주문된 평균 수량을 계산합니다.</span><span class="sxs-lookup"><span data-stu-id="388de-188">The following example calculates the average quantity ordered for each product:</span></span>

```sql
select p, avg(ol.Quantity) from LOB.OrderLines as ol 
  group by ol.Product as p
```

<span data-ttu-id="388de-189">SELECT 식에서 명시적 group by 절이 없는 그룹 기반 집계를 가질 수는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="388de-189">It's possible to have a group-based aggregate without an explicit group-by clause in the SELECT expression.</span></span> <span data-ttu-id="388de-190">이 경우 모든 요소가 단일 그룹으로 처리 됩니다.</span><span class="sxs-lookup"><span data-stu-id="388de-190">In this case, all elements are treated as a single group.</span></span> <span data-ttu-id="388de-191">이 상수를 기준으로 그룹화를 지정 하는 것과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="388de-191">This is equivalent of specifying a grouping based on a constant.</span></span> <span data-ttu-id="388de-192">예를 들어, 다음 식을 살펴보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="388de-192">Take, for example, the following expression:</span></span>

```sql
select avg(ol.Quantity) from LOB.OrderLines as ol
```

<span data-ttu-id="388de-193">이 식은 다음 식과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="388de-193">This is equivalent to the following:</span></span>

```sql
select avg(ol.Quantity) from LOB.OrderLines as ol group by 1
```

<span data-ttu-id="388de-194">그룹 기반 집계 내의 식은 WHERE 절 식에 표시되는 이름 결정 범위 내에서 계산됩니다.</span><span class="sxs-lookup"><span data-stu-id="388de-194">Expressions inside the group-based aggregate are evaluated within the name-resolution scope that would be visible to the WHERE clause expression.</span></span>

<span data-ttu-id="388de-195">와 같이 [!INCLUDE[tsql](../../../../../../includes/tsql-md.md)], 그룹 기반 집계는 모두를 지정할 수도 있습니다 한정자 나 DISTINCT 한정자입니다.</span><span class="sxs-lookup"><span data-stu-id="388de-195">As in [!INCLUDE[tsql](../../../../../../includes/tsql-md.md)], group-based aggregates can also specify an ALL or DISTINCT modifier.</span></span> <span data-ttu-id="388de-196">DISTINCT 한정자를 지정하면 집계가 계산되기 전에 집계 입력 컬렉션에서 중복 항목이 제거됩니다.</span><span class="sxs-lookup"><span data-stu-id="388de-196">If the DISTINCT modifier is specified, duplicates are eliminated from the aggregate input collection, before the aggregate is computed.</span></span> <span data-ttu-id="388de-197">ALL 한정자를 지정하거나 어떠한 한정자도 지정하지 않으면 중복 항목이 제거되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="388de-197">If the ALL modifier is specified (or if no modifier is specified), no duplicate elimination is performed.</span></span>  

## <a name="see-also"></a><span data-ttu-id="388de-198">참고자료</span><span class="sxs-lookup"><span data-stu-id="388de-198">See also</span></span>

- [<span data-ttu-id="388de-199">정식 함수</span><span class="sxs-lookup"><span data-stu-id="388de-199">Canonical Functions</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/canonical-functions.md)
