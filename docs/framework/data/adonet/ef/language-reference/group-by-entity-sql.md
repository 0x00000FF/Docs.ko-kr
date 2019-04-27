---
title: GROUP BY(Entity SQL)
ms.date: 03/30/2017
ms.assetid: cf4f4972-4724-4945-ba44-943a08549139
ms.openlocfilehash: 574d952e0183eb65c88864f2788eb7d698c9f2ec
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61879543"
---
# <a name="group-by-entity-sql"></a><span data-ttu-id="cda7b-102">GROUP BY(Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="cda7b-102">GROUP BY (Entity SQL)</span></span>
<span data-ttu-id="cda7b-103">쿼리 식([SELECT](../../../../../../docs/framework/data/adonet/ef/language-reference/select-entity-sql.md))을 통해 반환되는 개체가 배치될 그룹을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="cda7b-103">Specifies groups into which objects returned by a query ([SELECT](../../../../../../docs/framework/data/adonet/ef/language-reference/select-entity-sql.md)) expression are to be placed.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cda7b-104">구문</span><span class="sxs-lookup"><span data-stu-id="cda7b-104">Syntax</span></span>  
  
```  
[ GROUP BY aliasedExpression [ ,...n ] ]  
```  
  
## <a name="arguments"></a><span data-ttu-id="cda7b-105">인수</span><span class="sxs-lookup"><span data-stu-id="cda7b-105">Arguments</span></span>  
 `aliasedExpression`  
 <span data-ttu-id="cda7b-106">그룹화가 수행되는 유효한 쿼리 식입니다.</span><span class="sxs-lookup"><span data-stu-id="cda7b-106">Any valid query expression on which grouping is performed.</span></span> <span data-ttu-id="cda7b-107">`expression` 은 속성일 수도 있고 FROM 절을 통해 반환되는 속성을 참조하는 비집계 식일 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cda7b-107">`expression` can be a property or a non-aggregate expression that references a property returned by the FROM clause.</span></span> <span data-ttu-id="cda7b-108">GROUP BY 절의 모든 식은 같지 않음을 비교할 수 있는 형식으로 계산되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="cda7b-108">Each expression in a GROUP BY clause must evaluate to a type that can be compared for equality.</span></span> <span data-ttu-id="cda7b-109">이런 형식은 일반적으로 숫자, 문자열, 날짜와 같은 스칼라 기본 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="cda7b-109">These types are generally scalar primitives such as numbers, strings, and dates.</span></span> <span data-ttu-id="cda7b-110">컬렉션을 기준으로 그룹화할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="cda7b-110">You cannot group by a collection.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="cda7b-111">설명</span><span class="sxs-lookup"><span data-stu-id="cda7b-111">Remarks</span></span>  
 <span data-ttu-id="cda7b-112">SELECT 절에 집계 함수가 포함 된 경우 \<select 목록 >, GROUP BY 각 그룹에 대 한 요약 값을 계산 합니다.</span><span class="sxs-lookup"><span data-stu-id="cda7b-112">If aggregate functions are included in the SELECT clause \<select list>, GROUP BY calculates a summary value for each group.</span></span> <span data-ttu-id="cda7b-113">GROUP BY가 지정된 경우, 선택 목록 내의 집계가 아닌 식에 있는 모든 속성 이름이 GROUP BY 목록에 포함되어야 하거나 아니면 GROUP BY 식이 선택 목록 식과 정확히 일치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="cda7b-113">When GROUP BY is specified, either each property name in any nonaggregate expression in the select list should be included in the GROUP BY list, or the GROUP BY expression must exactly match the select list expression.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="cda7b-114">ORDER BY 절이 지정되지 않은 경우에는 GROUP BY 절에 의해 반환되는 그룹에 특정 순서가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="cda7b-114">If the ORDER BY clause is not specified, groups returned by the GROUP BY clause are not in any particular order.</span></span> <span data-ttu-id="cda7b-115">데이터에 특정 정렬 순서를 지정하려면 항상 ORDER BY 절을 사용하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="cda7b-115">To specify a particular ordering of the data, we recommend that you always use the ORDER BY clause.</span></span>  
  
 <span data-ttu-id="cda7b-116">명시적으로든 암시적으로든(예: 쿼리에 HAVING 절 사용) GROUP BY 절이 지정된 경우, 현재 범위는 숨겨지고 새로운 범위가 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="cda7b-116">When a GROUP BY clause is specified, either explicitly or implicitly (for example, by a HAVING clause in the query), the current scope is hidden, and a new scope is introduced.</span></span>  
  
 <span data-ttu-id="cda7b-117">그러면 SELECT 절, HAVING 절 및 ORDER BY 절이 FROM 절에 지정된 요소 이름을 참조할 수 없게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="cda7b-117">The SELECT clause, the HAVING clause, and the ORDER BY clause will no longer be able to refer to element names specified in the FROM clause.</span></span> <span data-ttu-id="cda7b-118">그룹화 식 자체만 참조할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cda7b-118">You can only refer to the grouping expressions themselves.</span></span> <span data-ttu-id="cda7b-119">이렇게 하려면 각 그룹화에 새 이름(별칭)을 할당하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="cda7b-119">To do this, you can assign new names (aliases) to each grouping expression.</span></span> <span data-ttu-id="cda7b-120">그룹화 식에 별칭이 지정되지 않은 경우 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] 에서는 다음 예제에서 보여 주는 것처럼 별칭 생성 규칙에 따라 별칭을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="cda7b-120">If no alias is specified for a grouping expression, [!INCLUDE[esql](../../../../../../includes/esql-md.md)] tries to generate one by using the alias generation rules, as illustrated in the following example.</span></span>  
  
 `SELECT g1, g2, ...gn FROM c as c1`  
  
 `GROUP BY e1 as g1, e2 as g2, ...en as gn`  
  
 <span data-ttu-id="cda7b-121">GROUP BY 절의 식은 동일한 GROUP BY 절에 이전에 정의된 이름을 참조할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="cda7b-121">Expressions in the GROUP BY clause cannot refer to names defined earlier in the same GROUP BY clause.</span></span>  
  
 <span data-ttu-id="cda7b-122">그룹화 이름뿐만 아니라 SELECT 절, HAVING 절 및 ORDER BY 절의 집계를 지정할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cda7b-122">In addition to grouping names, you can also specify aggregates in the SELECT clause, HAVING clause, and the ORDER BY clause.</span></span> <span data-ttu-id="cda7b-123">집계에는 그룹의 각 요소에 대해 계산되는 식이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="cda7b-123">An aggregate contains an expression that is evaluated for each element of the group.</span></span> <span data-ttu-id="cda7b-124">집계 연산자를 이러한 모든 식의 값을 일반적으로(항상 그렇지는 않음) 단일 값으로 줄입니다.</span><span class="sxs-lookup"><span data-stu-id="cda7b-124">The aggregate operator reduces the values of all these expressions (usually, but not always, into a single value).</span></span> <span data-ttu-id="cda7b-125">집계 식은 부모 범위에 나타난 원래 요소 이름을 참조하거나 GROUP BY 절에 의해 생성된 새 이름을 참조할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cda7b-125">The aggregate expression can make references to the original element names visible in the parent scope, or to any of the new names introduced by the GROUP BY clause itself.</span></span> <span data-ttu-id="cda7b-126">집계가 SELECT 절, HAVING 절, ORDER BY 절에 나타나기는 하지만 다음 예제에서 보여 주는 것처럼 그룹화 식과 동일한 범위에서 실제로 계산됩니다.</span><span class="sxs-lookup"><span data-stu-id="cda7b-126">Although the aggregates appear in the SELECT clause, HAVING clause, and ORDER BY clause, they are actually evaluated under the same scope as the grouping expressions, as illustrated in the following example.</span></span>  
  
 `SELECT name, sum(o.Price * o.Quantity) as total`  
  
 `FROM orderLines as o`  
  
 `GROUP BY o.Product as name`  
  
 <span data-ttu-id="cda7b-127">이 쿼리는 GROUP BY 절을 사용하여 모든 주문 제품에 대해 제품별로 구분된 비용 보고서를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="cda7b-127">This query uses the GROUP BY clause to produce a report of the cost of all products ordered, broken down by product.</span></span> <span data-ttu-id="cda7b-128">여기서는 그룹화 식의 일부로서 제품에 이름 `name` 을 지정하며 그런 다음 이 이름을 SELECT 목록에서 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="cda7b-128">It gives the name `name` to the product as part of the grouping expression, and then references that name in the SELECT list.</span></span> <span data-ttu-id="cda7b-129">또한, 주문 라인의 가격과 수량을 내부적으로 참조하는 집계 `sum` 을 SELECT 목록에서 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="cda7b-129">It also specifies the aggregate `sum` in the SELECT list that internally references the price and quantity of the order line.</span></span>  
  
 <span data-ttu-id="cda7b-130">각 GROUP BY 키 식에는 입력 범위에 대한 참조가 하나 이상 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="cda7b-130">Each GROUP By key expression must have at least one reference to the input scope:</span></span>  
  
```  
SELECT FROM Persons as P  
GROUP BY Q + P   -- GOOD  
GROUP BY Q   -- BAD  
GROUP BY 1   -- BAD, a constant is not allowed  
```  
  
 <span data-ttu-id="cda7b-131">GROUP BY 사용 예제는 [HAVING](../../../../../../docs/framework/data/adonet/ef/language-reference/having-entity-sql.md)항목을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="cda7b-131">For an example of using GROUP BY, see [HAVING](../../../../../../docs/framework/data/adonet/ef/language-reference/having-entity-sql.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="cda7b-132">예제</span><span class="sxs-lookup"><span data-stu-id="cda7b-132">Example</span></span>  
 <span data-ttu-id="cda7b-133">다음 Entity SQL 쿼리에서는 GROUP BY 연산자를 사용하여 쿼리를 통해 반환되는 개체가 배치될 그룹을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="cda7b-133">The following Entity SQL query uses the GROUP BY operator to specify groups into which objects are returned by a query.</span></span> <span data-ttu-id="cda7b-134">쿼리는 AdventureWorks Sales 모델을 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="cda7b-134">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="cda7b-135">이 쿼리를 컴파일하고 실행하려면 다음 단계를 수행하세요.</span><span class="sxs-lookup"><span data-stu-id="cda7b-135">To compile and run this query, follow these steps:</span></span>  
  
1. <span data-ttu-id="cda7b-136">절차에 따라 [방법: PrimitiveType 결과 반환 하는 쿼리 실행](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-primitivetype-results.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="cda7b-136">Follow the procedure in [How to: Execute a Query that Returns PrimitiveType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-primitivetype-results.md).</span></span>  
  
2. <span data-ttu-id="cda7b-137">다음 쿼리를 `ExecutePrimitiveTypeQuery` 메서드에 인수로 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="cda7b-137">Pass the following query as an argument to the `ExecutePrimitiveTypeQuery` method:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#GROUPBY](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#groupby)]  
  
## <a name="see-also"></a><span data-ttu-id="cda7b-138">참고자료</span><span class="sxs-lookup"><span data-stu-id="cda7b-138">See also</span></span>

- [<span data-ttu-id="cda7b-139">엔터티 SQL 참조</span><span class="sxs-lookup"><span data-stu-id="cda7b-139">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
- [<span data-ttu-id="cda7b-140">쿼리 식</span><span class="sxs-lookup"><span data-stu-id="cda7b-140">Query Expressions</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/query-expressions-entity-sql.md)
