---
title: 집계 함수(Entity Framework용 SqlClient)
ms.date: 03/30/2017
ms.assetid: 03303f01-b591-4efc-9875-f9c608edff0b
ms.openlocfilehash: 8ed9a58da9914724fe312876d6594cb526f2e0e9
ms.sourcegitcommit: 3c1c3ba79895335ff3737934e39372555ca7d6d0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/06/2018
ms.locfileid: "43856519"
---
# <a name="aggregate-functions-sqlclient-for-entity-framework"></a><span data-ttu-id="ca003-102">집계 함수(Entity Framework용 SqlClient)</span><span class="sxs-lookup"><span data-stu-id="ca003-102">Aggregate Functions (SqlClient for Entity Framework)</span></span>
<span data-ttu-id="ca003-103">.NET Framework Data Provider for SQL Server(SqlClient)에서는 집계 함수를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="ca003-103">The .NET Framework Data Provider for SQL Server (SqlClient) provides aggregate functions.</span></span> <span data-ttu-id="ca003-104">집계 함수는 입력 값 집합에 대해 계산을 수행하여 하나의 값을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="ca003-104">Aggregate functions perform calculations on a set of input values and return a value.</span></span> <span data-ttu-id="ca003-105">이 함수는 SqlClient를 사용할 때 사용 가능한 SqlServer 네임스페이스에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ca003-105">These functions are in the SqlServer namespace, which is available when you use SqlClient.</span></span> <span data-ttu-id="ca003-106">공급자의 네임스페이스 속성이 있으면 특정 구문(예: 형식 및 함수)에 대해 이 공급자가 사용하는 접두사를 Entity Framework에서 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ca003-106">A provider's namespace property allows the Entity Framework to discover which prefix is used by this provider for specific constructs, such as types and functions.</span></span>  
  
 <span data-ttu-id="ca003-107">SqlClient 집계 함수는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="ca003-107">The following are the SqlClient aggregate functions.</span></span>  

## <a name="avgexpression"></a><span data-ttu-id="ca003-108">AVG(expression)</span><span class="sxs-lookup"><span data-stu-id="ca003-108">AVG(expression)</span></span>

<span data-ttu-id="ca003-109">컬렉션에 포함된 값의 평균을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="ca003-109">Returns the average of the values in a collection.</span></span> <span data-ttu-id="ca003-110">Null 값은 무시됩니다.</span><span class="sxs-lookup"><span data-stu-id="ca003-110">Null values are ignored.</span></span>

<span data-ttu-id="ca003-111">**인수**</span><span class="sxs-lookup"><span data-stu-id="ca003-111">**Arguments**</span></span>

<span data-ttu-id="ca003-112">`Int32`, `Int64`, `Double` 및 `Decimal`입니다.</span><span class="sxs-lookup"><span data-stu-id="ca003-112">An `Int32`, `Int64`, `Double`, and `Decimal`.</span></span>

<span data-ttu-id="ca003-113">**반환 값**</span><span class="sxs-lookup"><span data-stu-id="ca003-113">**Return Value**</span></span>

<span data-ttu-id="ca003-114">`expression`의 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="ca003-114">The type of `expression`.</span></span>

<span data-ttu-id="ca003-115">**예제**</span><span class="sxs-lookup"><span data-stu-id="ca003-115">**Example**</span></span>

[!code-csharp[DP EntityServices Concepts#SQLSERVER_AVG](~/samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#sqlserver_avg)]
 [!code-sql[DP EntityServices Concepts#SQLSERVER_AVG](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_avg)]

## <a name="checksumaggcollection"></a><span data-ttu-id="ca003-116">CHECKSUM_AGG(collection)</span><span class="sxs-lookup"><span data-stu-id="ca003-116">CHECKSUM_AGG(collection)</span></span>
 
 <span data-ttu-id="ca003-117">컬렉션에 있는 값의 체크섬을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="ca003-117">Returns the checksum of the values in a collection.</span></span> <span data-ttu-id="ca003-118">Null 값은 무시됩니다.</span><span class="sxs-lookup"><span data-stu-id="ca003-118">Null values are ignored.</span></span>
 
 <span data-ttu-id="ca003-119">**인수**</span><span class="sxs-lookup"><span data-stu-id="ca003-119">**Arguments**</span></span>
 
 <span data-ttu-id="ca003-120">컬렉션 (`Int32`).</span><span class="sxs-lookup"><span data-stu-id="ca003-120">A Collection(`Int32`).</span></span>
 
 <span data-ttu-id="ca003-121">**반환 값**</span><span class="sxs-lookup"><span data-stu-id="ca003-121">**Return Value**</span></span>
 
 <span data-ttu-id="ca003-122">`Int32`입니다.</span><span class="sxs-lookup"><span data-stu-id="ca003-122">An `Int32`.</span></span>
 
 <span data-ttu-id="ca003-123">**예제**</span><span class="sxs-lookup"><span data-stu-id="ca003-123">**Example**</span></span>
 
 [!code-csharp[DP EntityServices Concepts#SQLSERVER_CHECKSUM](~/samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#sqlserver_checksum)]
 [!code-sql[DP EntityServices Concepts#SQLSERVER_CHECKSUM](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_checksum)]
   
## <a name="countexpression"></a><span data-ttu-id="ca003-124">COUNT(expression)</span><span class="sxs-lookup"><span data-stu-id="ca003-124">COUNT(expression)</span></span>

<span data-ttu-id="ca003-125">컬렉션의 항목 수를 `Int32`로 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="ca003-125">Returns the number of items in a collection as an `Int32`.</span></span>

<span data-ttu-id="ca003-126">**인수**</span><span class="sxs-lookup"><span data-stu-id="ca003-126">**Arguments**</span></span>

<span data-ttu-id="ca003-127">컬렉션\<T >, 여기서 T는 다음 형식 중 하나:</span><span class="sxs-lookup"><span data-stu-id="ca003-127">A Collection\<T>, where T is one of the following types:</span></span>

|   |   |   |   |
|---|---|---|---|
|`Boolean`|`Double`|`DateTime`|`DateTimeOffset`|
|`Time`|`String`|`Binary`|<span data-ttu-id="ca003-128">`Guid` (SQL Server 2000에서는 반환 되지 않음)</span><span class="sxs-lookup"><span data-stu-id="ca003-128">`Guid` (not returned in SQL Server 2000)</span></span>|

<span data-ttu-id="ca003-129">**반환 값**</span><span class="sxs-lookup"><span data-stu-id="ca003-129">**Return Value**</span></span>

<span data-ttu-id="ca003-130">`Int32`입니다.</span><span class="sxs-lookup"><span data-stu-id="ca003-130">An `Int32`.</span></span>

<span data-ttu-id="ca003-131">**예제**</span><span class="sxs-lookup"><span data-stu-id="ca003-131">**Example**</span></span>

[!code-csharp[DP EntityServices Concepts#SQLSERVER_COUNT](~/samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#sqlserver_count)]
<span data-ttu-id="ca003-132">[! 코드 sql[DP EntityServices 개념 &#40; SQLSERVER_COUNT](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_count)</span><span class="sxs-lookup"><span data-stu-id="ca003-132">[!code-sql[DP EntityServices Concepts#SQLSERVER_COUNT](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_count)</span></span>
 
## <a name="countbigexpression"></a><span data-ttu-id="ca003-133">COUNT_BIG(expression)</span><span class="sxs-lookup"><span data-stu-id="ca003-133">COUNT_BIG(expression)</span></span>
 
 <span data-ttu-id="ca003-134">컬렉션의 항목 수를 `bigint`로 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="ca003-134">Returns the number of items in a collection as a `bigint`.</span></span>
 
 <span data-ttu-id="ca003-135">**인수**</span><span class="sxs-lookup"><span data-stu-id="ca003-135">**Arguments**</span></span>
 
 <span data-ttu-id="ca003-136">여기서 T는 다음 형식 중 하나는 Collection(T):</span><span class="sxs-lookup"><span data-stu-id="ca003-136">A Collection(T), where T is one of the following types:</span></span>
 
 |   |   |   |   |
|---|---|---|---|
|`Boolean`|`Double`|`DateTime`|`DateTimeOffset`|
|`Time`|`String`|`Binary`|<span data-ttu-id="ca003-137">`Guid` (SQL Server 2000에서는 반환 되지 않음)</span><span class="sxs-lookup"><span data-stu-id="ca003-137">`Guid` (not returned in SQL Server 2000)</span></span>|

<span data-ttu-id="ca003-138">**반환 값**</span><span class="sxs-lookup"><span data-stu-id="ca003-138">**Return Value**</span></span>

<span data-ttu-id="ca003-139">`Int64`입니다.</span><span class="sxs-lookup"><span data-stu-id="ca003-139">An `Int64`.</span></span>

<span data-ttu-id="ca003-140">**예제**</span><span class="sxs-lookup"><span data-stu-id="ca003-140">**Example**</span></span>

[!code-csharp[DP EntityServices Concepts#SQLSERVER_COUNTBIG](~/samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#sqlserver_countbig)]
[!code-sql[DP EntityServices Concepts#SQLSERVER_COUNTBIG](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_countbig)]

## <a name="maxexpression"></a><span data-ttu-id="ca003-141">MAX(expression)</span><span class="sxs-lookup"><span data-stu-id="ca003-141">MAX(expression)</span></span>

<span data-ttu-id="ca003-142">컬렉션의 최대값을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="ca003-142">Returns the maximum value the collection.</span></span>

<span data-ttu-id="ca003-143">**인수**</span><span class="sxs-lookup"><span data-stu-id="ca003-143">**Arguments**</span></span>

<span data-ttu-id="ca003-144">여기서 T는 다음 형식 중 하나는 Collection(T):</span><span class="sxs-lookup"><span data-stu-id="ca003-144">A Collection(T), where T is one of the following types:</span></span> 

|   |   |   |   |
|---|---|---|---|
|`Boolean`|`Double`|`DateTime`|`DateTimeOffset`|
|`Time`|`String`|`Binary`||

<span data-ttu-id="ca003-145">**반환 값**</span><span class="sxs-lookup"><span data-stu-id="ca003-145">**Return Value**</span></span>

<span data-ttu-id="ca003-146">`expression`의 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="ca003-146">The type of `expression`.</span></span>

<span data-ttu-id="ca003-147">**예제**</span><span class="sxs-lookup"><span data-stu-id="ca003-147">**Example**</span></span>

[!code-csharp[DP EntityServices Concepts#SQLSERVER_MAX](~/samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#sqlserver_max)]
[!code-sql[DP EntityServices Concepts#SQLSERVER_MAX](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_max)]

## <a name="minexpression"></a><span data-ttu-id="ca003-148">MIN(expression)</span><span class="sxs-lookup"><span data-stu-id="ca003-148">MIN(expression)</span></span>

<span data-ttu-id="ca003-149">컬렉션의 최소값을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="ca003-149">Returns the minimum value in a collection.</span></span>

<span data-ttu-id="ca003-150">**인수**</span><span class="sxs-lookup"><span data-stu-id="ca003-150">**Arguments**</span></span>

<span data-ttu-id="ca003-151">여기서 T는 다음 형식 중 하나는 Collection(T):</span><span class="sxs-lookup"><span data-stu-id="ca003-151">A Collection(T), where T is one of the following types:</span></span> 

|   |   |   |   |
|---|---|---|---|
|`Boolean`|`Double`|`DateTime`|`DateTimeOffset`|
|`Time`|`String`|`Binary`||

<span data-ttu-id="ca003-152">**반환 값**</span><span class="sxs-lookup"><span data-stu-id="ca003-152">**Return Value**</span></span>

<span data-ttu-id="ca003-153">`expression`의 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="ca003-153">The type of `expression`.</span></span>

<span data-ttu-id="ca003-154">**예제**</span><span class="sxs-lookup"><span data-stu-id="ca003-154">**Example**</span></span>

[!code-csharp[DP EntityServices Concepts#SQLSERVER_MIN](~/samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#sqlserver_min)]
[!code-sql[DP EntityServices Concepts#SQLSERVER_MIN](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_min)]

## <a name="stdevexpression"></a><span data-ttu-id="ca003-155">STDEV(expression)</span><span class="sxs-lookup"><span data-stu-id="ca003-155">STDEV(expression)</span></span>

<span data-ttu-id="ca003-156">지정한 식의 모든 값에 대한 통계적 표준 편차를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="ca003-156">Returns the statistical standard deviation of all values in the specified expression.</span></span>

<span data-ttu-id="ca003-157">**인수**</span><span class="sxs-lookup"><span data-stu-id="ca003-157">**Arguments**</span></span>

<span data-ttu-id="ca003-158">컬렉션 (`Double`).</span><span class="sxs-lookup"><span data-stu-id="ca003-158">A Collection(`Double`).</span></span>

<span data-ttu-id="ca003-159">**반환 값**</span><span class="sxs-lookup"><span data-stu-id="ca003-159">**Return Value**</span></span>

<span data-ttu-id="ca003-160">`Double`</span><span class="sxs-lookup"><span data-stu-id="ca003-160">A `Double`.</span></span>

<span data-ttu-id="ca003-161">**예제**</span><span class="sxs-lookup"><span data-stu-id="ca003-161">**Example**</span></span>

[!code-csharp[DP EntityServices Concepts#SQLSERVER_STDEV](~/samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#sqlserver_stdev)]
[!code-sql[DP EntityServices Concepts#SQLSERVER_STDEV](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_stdev)]

## <a name="stdevpexpression"></a><span data-ttu-id="ca003-162">STDEVP(expression)</span><span class="sxs-lookup"><span data-stu-id="ca003-162">STDEVP(expression)</span></span>

<span data-ttu-id="ca003-163">지정한 식에 있는 모든 값의 모집단에 대한 통계적 표준 편차를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="ca003-163">Returns the statistical standard deviation for the population for all values in the specified expression.</span></span>

<span data-ttu-id="ca003-164">**인수**</span><span class="sxs-lookup"><span data-stu-id="ca003-164">**Arguments**</span></span>

<span data-ttu-id="ca003-165">컬렉션 (`Double`).</span><span class="sxs-lookup"><span data-stu-id="ca003-165">A Collection(`Double`).</span></span>

<span data-ttu-id="ca003-166">**반환 값**</span><span class="sxs-lookup"><span data-stu-id="ca003-166">**Return Value**</span></span>

<span data-ttu-id="ca003-167">`Double`</span><span class="sxs-lookup"><span data-stu-id="ca003-167">A `Double`.</span></span>

<span data-ttu-id="ca003-168">**예제**</span><span class="sxs-lookup"><span data-stu-id="ca003-168">**Example**</span></span>

[!code-csharp[DP EntityServices Concepts#SQLSERVER_STDEVP](~/samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#sqlserver_stdevp)]
[!code-sql[DP EntityServices Concepts#SQLSERVER_STDEVP](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_stdevp)]

## <a name="sumexpression"></a><span data-ttu-id="ca003-169">SUM(expression)</span><span class="sxs-lookup"><span data-stu-id="ca003-169">SUM(expression)</span></span>

<span data-ttu-id="ca003-170">컬렉션에 있는 모든 값의 합계를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="ca003-170">Returns the sum of all the values in the collection.</span></span>

<span data-ttu-id="ca003-171">**인수**</span><span class="sxs-lookup"><span data-stu-id="ca003-171">**Arguments**</span></span>

<span data-ttu-id="ca003-172">여기서 T는 다음 형식 중 하나는 Collection(T): `Int32`, `Int64`를 `Double`, `Decimal`합니다.</span><span class="sxs-lookup"><span data-stu-id="ca003-172">A Collection(T) where T is one of the following types: `Int32`, `Int64`, `Double`, `Decimal`.</span></span>

<span data-ttu-id="ca003-173">**반환 값**</span><span class="sxs-lookup"><span data-stu-id="ca003-173">**Return Value**</span></span>

<span data-ttu-id="ca003-174">`expression`의 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="ca003-174">The type of `expression`.</span></span>

<span data-ttu-id="ca003-175">**예제**</span><span class="sxs-lookup"><span data-stu-id="ca003-175">**Example**</span></span>

[!code-csharp[DP EntityServices Concepts#SQLSERVER_SUM](~/samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#sqlserver_sum)]
[!code-sql[DP EntityServices Concepts#SQLSERVER_SUM](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_sum)]

## <a name="varexpression"></a><span data-ttu-id="ca003-176">VAR(expression)</span><span class="sxs-lookup"><span data-stu-id="ca003-176">VAR(expression)</span></span>

<span data-ttu-id="ca003-177">지정한 식에 있는 모든 값의 통계적 분산을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="ca003-177">Returns the statistical variance of all values in the specified expression.</span></span>

<span data-ttu-id="ca003-178">**인수**</span><span class="sxs-lookup"><span data-stu-id="ca003-178">**Arguments**</span></span>

<span data-ttu-id="ca003-179">컬렉션 (`Double`).</span><span class="sxs-lookup"><span data-stu-id="ca003-179">A Collection(`Double`).</span></span>

<span data-ttu-id="ca003-180">**반환 값**</span><span class="sxs-lookup"><span data-stu-id="ca003-180">**Return Value**</span></span>

<span data-ttu-id="ca003-181">`Double`</span><span class="sxs-lookup"><span data-stu-id="ca003-181">A `Double`.</span></span>

<span data-ttu-id="ca003-182">**예제**</span><span class="sxs-lookup"><span data-stu-id="ca003-182">**Example**</span></span>

[!code-csharp[DP EntityServices Concepts#SQLSERVER_VAR](~/samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#sqlserver_var)]
[!code-sql[DP EntityServices Concepts#SQLSERVER_VAR](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_var)]

## <a name="varpexpression"></a><span data-ttu-id="ca003-183">VARP(expression)</span><span class="sxs-lookup"><span data-stu-id="ca003-183">VARP(expression)</span></span>

<span data-ttu-id="ca003-184">지정한 식에 있는 모든 값의 모집단에 대한 통계적 분산을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="ca003-184">Returns the statistical variance for the population for all values in the specified expression.</span></span>

<span data-ttu-id="ca003-185">**인수**</span><span class="sxs-lookup"><span data-stu-id="ca003-185">**Arguments**</span></span>

<span data-ttu-id="ca003-186">컬렉션 (`Double`).</span><span class="sxs-lookup"><span data-stu-id="ca003-186">A Collection(`Double`).</span></span>

<span data-ttu-id="ca003-187">**반환 값**</span><span class="sxs-lookup"><span data-stu-id="ca003-187">**Return Value**</span></span>

<span data-ttu-id="ca003-188">`Double`</span><span class="sxs-lookup"><span data-stu-id="ca003-188">A `Double`.</span></span>

<span data-ttu-id="ca003-189">**예제**</span><span class="sxs-lookup"><span data-stu-id="ca003-189">**Example**</span></span>

[!code-csharp[DP EntityServices Concepts#SQLSERVER_VARP](~/samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#sqlserver_varp)]
[!code-sql[DP EntityServices Concepts#SQLSERVER_VARP](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_varp)] 
  
## <a name="see-also"></a><span data-ttu-id="ca003-190">참고자료</span><span class="sxs-lookup"><span data-stu-id="ca003-190">See also</span></span>

<span data-ttu-id="ca003-191">SqlClient에서 지원하는 집계 함수에 대한 자세한 내용은 SqlClient 공급자 매니페스트에 지정한 SQL Server 버전의 설명서를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ca003-191">For more information about the aggregate functions that SqlClient supports, see the documentation for the SQL Server version that you specified in the SqlClient provider manifest:</span></span>  
  
<span data-ttu-id="ca003-192">**SQL Server 2005**: [집계 함수 (TRANSACT-SQL)](https://docs.microsoft.com/previous-versions/sql/sql-server-2005/ms173454(v=sql.90))</span><span class="sxs-lookup"><span data-stu-id="ca003-192">**SQL Server 2005**: [Aggregate Functions (Transact-SQL)](https://docs.microsoft.com/previous-versions/sql/sql-server-2005/ms173454(v=sql.90))</span></span>  
<span data-ttu-id="ca003-193">**SQL Server 2008 이상**: [집계 함수 (TRANSACT-SQL)](/sql/t-sql/functions/aggregate-functions-transact-sql)</span><span class="sxs-lookup"><span data-stu-id="ca003-193">**SQL Server 2008 and later**:  [Aggregate Functions (Transact-SQL)](/sql/t-sql/functions/aggregate-functions-transact-sql)</span></span>  
[<span data-ttu-id="ca003-194">Entity SQL 언어</span><span class="sxs-lookup"><span data-stu-id="ca003-194">Entity SQL Language</span></span>](../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-language.md)  
[<span data-ttu-id="ca003-195">집계 정식 함수</span><span class="sxs-lookup"><span data-stu-id="ca003-195">Aggregate Canonical Functions</span></span>](../../../../../docs/framework/data/adonet/ef/language-reference/aggregate-canonical-functions.md)
