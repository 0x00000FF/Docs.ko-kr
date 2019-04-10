---
title: HAVING (Entity SQL)
ms.date: 03/30/2017
ms.assetid: b5d52d97-8372-4335-beac-2d0b79dc3707
ms.openlocfilehash: 19da828d3c7e7763c3dd9ba0e34da8849f90cf0b
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59155144"
---
# <a name="having-entity-sql"></a><span data-ttu-id="c2740-102">HAVING (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="c2740-102">HAVING (Entity SQL)</span></span>
<span data-ttu-id="c2740-103">그룹이나 집계에 대한 검색 조건을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="c2740-103">Specifies a search condition for a group or an aggregate.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c2740-104">구문</span><span class="sxs-lookup"><span data-stu-id="c2740-104">Syntax</span></span>  
  
```  
[ HAVING search_condition ]  
```  
  
## <a name="arguments"></a><span data-ttu-id="c2740-105">인수</span><span class="sxs-lookup"><span data-stu-id="c2740-105">Arguments</span></span>  
 `search_condition`  
 <span data-ttu-id="c2740-106">그룹이나 집계에 대해 충족해야 하는 검색 조건을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="c2740-106">Specifies the search condition for the group or the aggregate to meet.</span></span> <span data-ttu-id="c2740-107">HAVING을 GROUP BY ALL과 함께 사용하면 HAVING 절이 ALL을 재정의합니다.</span><span class="sxs-lookup"><span data-stu-id="c2740-107">When HAVING is used with GROUP BY ALL, the HAVING clause overrides ALL.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c2740-108">설명</span><span class="sxs-lookup"><span data-stu-id="c2740-108">Remarks</span></span>  
 <span data-ttu-id="c2740-109">HAVING 절은 그룹화 결과에 추가 필터링 조건을 지정하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="c2740-109">The HAVING clause is used to specify an additional filtering condition on the result of a grouping.</span></span> <span data-ttu-id="c2740-110">쿼리 식에 GROUP BY 절이 지정되지 않으면 암시적인 단일 집합 그룹이 선택됩니다.</span><span class="sxs-lookup"><span data-stu-id="c2740-110">If no GROUP BY clause is specified in the query expression, an implicit single-set group is assumed.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c2740-111">HAVING에만 사용할 수는 [선택](../../../../../../docs/framework/data/adonet/ef/language-reference/select-entity-sql.md) 문입니다.</span><span class="sxs-lookup"><span data-stu-id="c2740-111">HAVING can be used only with the [SELECT](../../../../../../docs/framework/data/adonet/ef/language-reference/select-entity-sql.md) statement.</span></span> <span data-ttu-id="c2740-112">때 [GROUP BY](../../../../../../docs/framework/data/adonet/ef/language-reference/group-by-entity-sql.md) 는 HAVING을 사용 하지는 WHERE 절 처럼 동작 합니다.</span><span class="sxs-lookup"><span data-stu-id="c2740-112">When [GROUP BY](../../../../../../docs/framework/data/adonet/ef/language-reference/group-by-entity-sql.md) is not used, HAVING behaves like a WHERE clause.</span></span>  
  
 <span data-ttu-id="c2740-113">HAVING 절은 GROUP BY 연산 이후에 적용된다는 점을 제외하고는 WHERE 절과 비슷하게 작동합니다.</span><span class="sxs-lookup"><span data-stu-id="c2740-113">The HAVING clause works like the WHERE clause except that it is applied after the GROUP BY operation.</span></span> <span data-ttu-id="c2740-114">다시 말해서, HAVING 절은 다음 예제와 같이 그룹화 별칭 및 집계만 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="c2740-114">This means that the HAVING clause can only make references to grouping aliases and aggregates, as illustrated in the following example.</span></span>  
  
```  
SELECT Name, SUM(o.Price * o.Quantity) AS Total FROM orderLines AS o GROUP BY o.Product AS Name  
HAVING SUM(o.Quantity) > 1  
```  
  
 <span data-ttu-id="c2740-115">위 예에서는 제품 두 개 이상이 포함된 그룹으로만 제한되었습니다.</span><span class="sxs-lookup"><span data-stu-id="c2740-115">The previous restricts the groups to only those that include more than one product.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c2740-116">예제</span><span class="sxs-lookup"><span data-stu-id="c2740-116">Example</span></span>  
 <span data-ttu-id="c2740-117">다음 Entity SQL 쿼리에서는 HAVING 및 GROUP BY 연산자를 사용하여 그룹이나 집계에 대한 검색 조건을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="c2740-117">The following Entity SQL query uses the HAVING and GROUP BY operators to specify a search condition for a group or an aggregate.</span></span> <span data-ttu-id="c2740-118">쿼리는 AdventureWorks Sales 모델을 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="c2740-118">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="c2740-119">이 쿼리를 컴파일하고 실행하려면 다음 단계를 수행하세요.</span><span class="sxs-lookup"><span data-stu-id="c2740-119">To compile and run this query, follow these steps:</span></span>  
  
1.  <span data-ttu-id="c2740-120">절차에 따라 [방법: PrimitiveType 결과 반환 하는 쿼리 실행](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-primitivetype-results.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="c2740-120">Follow the procedure in [How to: Execute a Query that Returns PrimitiveType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-primitivetype-results.md).</span></span>  
  
2.  <span data-ttu-id="c2740-121">다음 쿼리를 `ExecutePrimitiveTypeQuery` 메서드에 인수로 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="c2740-121">Pass the following query as an argument to the `ExecutePrimitiveTypeQuery` method:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#HAVING](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#having)]  
  
## <a name="see-also"></a><span data-ttu-id="c2740-122">참고자료</span><span class="sxs-lookup"><span data-stu-id="c2740-122">See also</span></span>

- [<span data-ttu-id="c2740-123">엔터티 SQL 참조</span><span class="sxs-lookup"><span data-stu-id="c2740-123">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
- [<span data-ttu-id="c2740-124">쿼리 식</span><span class="sxs-lookup"><span data-stu-id="c2740-124">Query Expressions</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/query-expressions-entity-sql.md)
