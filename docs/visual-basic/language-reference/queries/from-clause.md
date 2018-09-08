---
title: From 절(Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.QueryFrom
- vb.QueryFromIn
- vb.QueryFromLet
helpviewer_keywords:
- queries [Visual Basic], From
- From clause [Visual Basic]
- From statement [Visual Basic]
ms.assetid: 83e3665e-68a0-4540-a3a3-3d777a0f95d5
ms.openlocfilehash: 71573de48cc51c48291fc4b82a0628d2d0f96caa
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/08/2018
ms.locfileid: "44198246"
---
# <a name="from-clause-visual-basic"></a><span data-ttu-id="c6193-102">From 절(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c6193-102">From Clause (Visual Basic)</span></span>
<span data-ttu-id="c6193-103">하나 이상의 범위 변수 및 쿼리 하는 컬렉션을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="c6193-103">Specifies one or more range variables and a collection to query.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c6193-104">구문</span><span class="sxs-lookup"><span data-stu-id="c6193-104">Syntax</span></span>  
  
```  
From element [ As type ] In collection [ _ ]  
  [, element2 [ As type2 ] In collection2 [, ... ] ]  
```  
  
## <a name="parts"></a><span data-ttu-id="c6193-105">요소</span><span class="sxs-lookup"><span data-stu-id="c6193-105">Parts</span></span>  
  
|<span data-ttu-id="c6193-106">용어</span><span class="sxs-lookup"><span data-stu-id="c6193-106">Term</span></span>|<span data-ttu-id="c6193-107">정의</span><span class="sxs-lookup"><span data-stu-id="c6193-107">Definition</span></span>|  
|---|---|  
|`element`|<span data-ttu-id="c6193-108">필수.</span><span class="sxs-lookup"><span data-stu-id="c6193-108">Required.</span></span> <span data-ttu-id="c6193-109">A *범위 변수* 컬렉션의 요소를 반복 하는 데 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="c6193-109">A *range variable* used to iterate through the elements of the collection.</span></span> <span data-ttu-id="c6193-110">범위 변수는의 각 멤버에 대 한 참조를 사용 하는 `collection` 쿼리를 반복 하는 대로 `collection`합니다.</span><span class="sxs-lookup"><span data-stu-id="c6193-110">A range variable is used to refer to each member of the `collection` as the query iterates through the `collection`.</span></span> <span data-ttu-id="c6193-111">열거 가능한 형식 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c6193-111">Must be an enumerable type.</span></span>|  
|`type`|<span data-ttu-id="c6193-112">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="c6193-112">Optional.</span></span> <span data-ttu-id="c6193-113">`element`의 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="c6193-113">The type of `element`.</span></span> <span data-ttu-id="c6193-114">없으면 `type` 지정 된 형식의 `element` 에서 유추 됩니다 `collection`합니다.</span><span class="sxs-lookup"><span data-stu-id="c6193-114">If no `type` is specified, the type of `element` is inferred from `collection`.</span></span>|  
|`collection`|<span data-ttu-id="c6193-115">필수.</span><span class="sxs-lookup"><span data-stu-id="c6193-115">Required.</span></span> <span data-ttu-id="c6193-116">컬렉션을 쿼리할 수를 가리킵니다.</span><span class="sxs-lookup"><span data-stu-id="c6193-116">Refers to the collection to be queried.</span></span> <span data-ttu-id="c6193-117">열거 가능한 형식 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c6193-117">Must be an enumerable type.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c6193-118">설명</span><span class="sxs-lookup"><span data-stu-id="c6193-118">Remarks</span></span>  
 <span data-ttu-id="c6193-119">`From` 절을 사용 하는 쿼리 및 소스 컬렉션에서 요소를 참조 하는 데 사용 되는 변수에 대 한 원본 데이터를 식별 합니다.</span><span class="sxs-lookup"><span data-stu-id="c6193-119">The `From` clause is used to identify the source data for a query and the variables that are used to refer to an element from the source collection.</span></span> <span data-ttu-id="c6193-120">이러한 변수 라고 *범위 변수*합니다.</span><span class="sxs-lookup"><span data-stu-id="c6193-120">These variables are called *range variables*.</span></span> <span data-ttu-id="c6193-121">`From` 절이 필요한 경우를 제외 하 고 쿼리를 위해는 `Aggregate` 절은 반환에만 결과 집계 쿼리를 식별 하는 데 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c6193-121">The `From` clause is required for a query, except when the `Aggregate` clause is used to identify a query that returns only aggregated results.</span></span> <span data-ttu-id="c6193-122">자세한 내용은 [Aggregate 절](../../../visual-basic/language-reference/queries/aggregate-clause.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="c6193-122">For more information, see [Aggregate Clause](../../../visual-basic/language-reference/queries/aggregate-clause.md).</span></span>  
  
 <span data-ttu-id="c6193-123">여러 개 지정할 수 있습니다 `From` 조인할 여러 컬렉션을 식별 하는 쿼리 절.</span><span class="sxs-lookup"><span data-stu-id="c6193-123">You can specify multiple `From` clauses in a query to identify multiple collections to be joined.</span></span> <span data-ttu-id="c6193-124">여러 컬렉션 지정 되 면 이러한 반복 하지 독립적으로 또는 관련 되어 조인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c6193-124">When multiple collections are specified, they are iterated over independently, or you can join them if they are related.</span></span> <span data-ttu-id="c6193-125">사용 하 여 컬렉션을 암시적으로 연결할 수 있습니다 합니다 `Select` 절 또는 명시적으로 사용 하 여 합니다 `Join` 또는 `Group Join` 절.</span><span class="sxs-lookup"><span data-stu-id="c6193-125">You can join collections implicitly by using the `Select` clause, or explicitly by using the `Join` or `Group Join` clauses.</span></span> <span data-ttu-id="c6193-126">대신 지정할 수 있습니다 여러 범위 변수 및 컬렉션을 단일에서 `From` 각 관련된 범위 변수와 다른에서 쉼표로 구분 된 컬렉션을 사용 하 여 절.</span><span class="sxs-lookup"><span data-stu-id="c6193-126">As an alternative, you can specify multiple range variables and collections in a single `From` clause, with each related range variable and collection separated from the others by a comma.</span></span> <span data-ttu-id="c6193-127">다음 코드 예제에는 두 구문 옵션을 보여 줍니다는 `From` 절.</span><span class="sxs-lookup"><span data-stu-id="c6193-127">The following code example shows both syntax options for the `From` clause.</span></span>  
  
 [!code-vb[VbSimpleQuerySamples#21](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/from-clause_1.vb)]  
  
 <span data-ttu-id="c6193-128">합니다 `From` 범위의 비슷한 쿼리의 범위를 정의 하는 절을 `For` 루프입니다.</span><span class="sxs-lookup"><span data-stu-id="c6193-128">The `From` clause defines the scope of a query, which is similar to the scope of a `For` loop.</span></span> <span data-ttu-id="c6193-129">따라서 각 `element` 쿼리의 범위에 범위 변수는 고유한 이름이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c6193-129">Therefore, each `element` range variable in the scope of a query must have a unique name.</span></span> <span data-ttu-id="c6193-130">여러 개 지정할 수 있으므로 `From` 쿼리의 경우 후속 절 `From` 절에 범위 변수를 참조할 수는 `From` 하거나 절은 이전에 범위 변수를 참조할 수 `From` 절.</span><span class="sxs-lookup"><span data-stu-id="c6193-130">Because you can specify multiple `From` clauses for a query, subsequent `From` clauses can refer to range variables in the `From` clause, or they can refer to range variables in a previous `From` clause.</span></span> <span data-ttu-id="c6193-131">예를 들어, 다음 예제에서는 중첩 된 `From` 절 있는 두 번째 절에 있는 컬렉션은 속성을 기준으로 첫 번째 절의 범위 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="c6193-131">For example, the following example shows a nested `From` clause where the collection in the second clause is based on a property of the range variable in the first clause.</span></span>  
  
 [!code-vb[VbSimpleQuerySamples#22](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/from-clause_2.vb)]  
  
 <span data-ttu-id="c6193-132">각 `From` 절 쿼리를 구체화 하는 추가 쿼리 절 조합 올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c6193-132">Each `From` clause can be followed by any combination of additional query clauses to refine the query.</span></span> <span data-ttu-id="c6193-133">다음과 같은 방법으로 쿼리를 구체화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c6193-133">You can refine the query in the following ways:</span></span>  
  
-   <span data-ttu-id="c6193-134">여러 컬렉션을 사용 하 여 암시적으로 결합 합니다 `From` 및 `Select` 절 또는 명시적으로 사용 하 여 합니다 `Join` 또는 `Group Join` 절.</span><span class="sxs-lookup"><span data-stu-id="c6193-134">Combine multiple collections implicitly by using the `From` and `Select` clauses, or explicitly by using the `Join` or `Group Join` clauses.</span></span>  
  
-   <span data-ttu-id="c6193-135">사용 된 `Where` 절 쿼리 결과를 필터링 합니다.</span><span class="sxs-lookup"><span data-stu-id="c6193-135">Use the `Where` clause to filter the query result.</span></span>  
  
-   <span data-ttu-id="c6193-136">사용 하 여 결과 정렬 된 `Order By` 절.</span><span class="sxs-lookup"><span data-stu-id="c6193-136">Sort the result by using the `Order By` clause.</span></span>  
  
-   <span data-ttu-id="c6193-137">사용 하 여 비슷한 결과 함께 그룹화 된 `Group By` 절.</span><span class="sxs-lookup"><span data-stu-id="c6193-137">Group similar results together by using the `Group By` clause.</span></span>  
  
-   <span data-ttu-id="c6193-138">사용 하 여는 `Aggregate` 절에 집계 함수는 전체 쿼리 결과 대 한 평가를 식별 합니다.</span><span class="sxs-lookup"><span data-stu-id="c6193-138">Use the `Aggregate` clause to identify aggregate functions to evaluate for the whole query result.</span></span>  
  
-   <span data-ttu-id="c6193-139">사용 된 `Let` 절 값인 컬렉션 대신 식에 의해 결정 됩니다 하는 반복 변수를 도입 합니다.</span><span class="sxs-lookup"><span data-stu-id="c6193-139">Use the `Let` clause to introduce an iteration variable whose value is determined by an expression instead of a collection.</span></span>  
  
-   <span data-ttu-id="c6193-140">사용 하 여는 `Distinct` 절에 중복 되는 쿼리 결과 무시 합니다.</span><span class="sxs-lookup"><span data-stu-id="c6193-140">Use the `Distinct` clause to ignore duplicate query results.</span></span>  
  
-   <span data-ttu-id="c6193-141">사용 하 여 반환할 결과 부분을 식별 합니다 `Skip`, `Take`를 `Skip While`, 및 `Take While` 절.</span><span class="sxs-lookup"><span data-stu-id="c6193-141">Identify parts of the result to return by using the `Skip`, `Take`, `Skip While`, and `Take While` clauses.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c6193-142">예제</span><span class="sxs-lookup"><span data-stu-id="c6193-142">Example</span></span>  
 <span data-ttu-id="c6193-143">다음 쿼리 식에 사용을 `From` 범위 변수를 선언 하는 절 `cust` 각각에 대해 `Customer` 개체는 `customers` 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="c6193-143">The following query expression uses a `From` clause to declare a range variable `cust` for each `Customer` object in the `customers` collection.</span></span> <span data-ttu-id="c6193-144">`Where` 절 범위 변수를 사용 하 여 지정된 된 지역에서 고객에 게 출력을 제한 합니다.</span><span class="sxs-lookup"><span data-stu-id="c6193-144">The `Where` clause uses the range variable to restrict the output to customers from the specified region.</span></span> <span data-ttu-id="c6193-145">`For Each` 루프는 쿼리 결과에서 각 고객의 회사 이름을 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="c6193-145">The `For Each` loop displays the company name for each customer in the query result.</span></span>  
  
 [!code-vb[VbSimpleQuerySamples#23](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/from-clause_3.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="c6193-146">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c6193-146">See Also</span></span>  
 [<span data-ttu-id="c6193-147">쿼리</span><span class="sxs-lookup"><span data-stu-id="c6193-147">Queries</span></span>](../../../visual-basic/language-reference/queries/index.md)  
 [<span data-ttu-id="c6193-148">Visual Basic의 LINQ 소개</span><span class="sxs-lookup"><span data-stu-id="c6193-148">Introduction to LINQ in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)  
 [<span data-ttu-id="c6193-149">For Each...Next 문</span><span class="sxs-lookup"><span data-stu-id="c6193-149">For Each...Next Statement</span></span>](../../../visual-basic/language-reference/statements/for-each-next-statement.md)  
 [<span data-ttu-id="c6193-150">For...Next 문</span><span class="sxs-lookup"><span data-stu-id="c6193-150">For...Next Statement</span></span>](../../../visual-basic/language-reference/statements/for-next-statement.md)  
 [<span data-ttu-id="c6193-151">Select 절</span><span class="sxs-lookup"><span data-stu-id="c6193-151">Select Clause</span></span>](../../../visual-basic/language-reference/queries/select-clause.md)  
 [<span data-ttu-id="c6193-152">Where 절</span><span class="sxs-lookup"><span data-stu-id="c6193-152">Where Clause</span></span>](../../../visual-basic/language-reference/queries/where-clause.md)  
 [<span data-ttu-id="c6193-153">Aggregate 절</span><span class="sxs-lookup"><span data-stu-id="c6193-153">Aggregate Clause</span></span>](../../../visual-basic/language-reference/queries/aggregate-clause.md)  
 [<span data-ttu-id="c6193-154">Distinct 절</span><span class="sxs-lookup"><span data-stu-id="c6193-154">Distinct Clause</span></span>](../../../visual-basic/language-reference/queries/distinct-clause.md)  
 [<span data-ttu-id="c6193-155">Join 절</span><span class="sxs-lookup"><span data-stu-id="c6193-155">Join Clause</span></span>](../../../visual-basic/language-reference/queries/join-clause.md)  
 [<span data-ttu-id="c6193-156">Group Join 절</span><span class="sxs-lookup"><span data-stu-id="c6193-156">Group Join Clause</span></span>](../../../visual-basic/language-reference/queries/group-join-clause.md)  
 [<span data-ttu-id="c6193-157">Order By 절</span><span class="sxs-lookup"><span data-stu-id="c6193-157">Order By Clause</span></span>](../../../visual-basic/language-reference/queries/order-by-clause.md)  
 [<span data-ttu-id="c6193-158">Let 절</span><span class="sxs-lookup"><span data-stu-id="c6193-158">Let Clause</span></span>](../../../visual-basic/language-reference/queries/let-clause.md)  
 [<span data-ttu-id="c6193-159">Skip 절</span><span class="sxs-lookup"><span data-stu-id="c6193-159">Skip Clause</span></span>](../../../visual-basic/language-reference/queries/skip-clause.md)  
 [<span data-ttu-id="c6193-160">Take 절</span><span class="sxs-lookup"><span data-stu-id="c6193-160">Take Clause</span></span>](../../../visual-basic/language-reference/queries/take-clause.md)  
 [<span data-ttu-id="c6193-161">Skip While 절</span><span class="sxs-lookup"><span data-stu-id="c6193-161">Skip While Clause</span></span>](../../../visual-basic/language-reference/queries/skip-while-clause.md)  
 [<span data-ttu-id="c6193-162">Take While 절</span><span class="sxs-lookup"><span data-stu-id="c6193-162">Take While Clause</span></span>](../../../visual-basic/language-reference/queries/take-while-clause.md)
