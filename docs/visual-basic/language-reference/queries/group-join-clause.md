---
title: Group Join 절(Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.QueryGroupJoinIn
- vb.QueryGroupJoinOn
- vb.QueryGroupJoin
- vb.QueryGroupJoinInto
helpviewer_keywords:
- Group Join clause [Visual Basic]
- Group Join statement [Visual Basic]
- queries [Visual Basic], Group Join
ms.assetid: 37dbf79c-7b5c-421b-bbb7-dadfd2b92a1c
ms.openlocfilehash: f4c0d7fa9f14868404cde6201692e26b919198be
ms.sourcegitcommit: fe02afbc39e78afd78cc6050e4a9c12a75f579f8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/30/2018
ms.locfileid: "43258019"
---
# <a name="group-join-clause-visual-basic"></a><span data-ttu-id="621ce-102">Group Join 절(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="621ce-102">Group Join Clause (Visual Basic)</span></span>
<span data-ttu-id="621ce-103">두 컬렉션을 단일 계층 구조 컬렉션으로 결합합니다.</span><span class="sxs-lookup"><span data-stu-id="621ce-103">Combines two collections into a single hierarchical collection.</span></span> <span data-ttu-id="621ce-104">조인 작업은 키를 일치 하는 기준으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="621ce-104">The join operation is based on matching keys.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="621ce-105">구문</span><span class="sxs-lookup"><span data-stu-id="621ce-105">Syntax</span></span>  
  
```  
Group Join element [As type] In collection _  
  On key1 Equals key2 [ And key3 Equals key4 [... ] ] _  
  Into expressionList  
```  
  
## <a name="parts"></a><span data-ttu-id="621ce-106">요소</span><span class="sxs-lookup"><span data-stu-id="621ce-106">Parts</span></span>  
  
|<span data-ttu-id="621ce-107">용어</span><span class="sxs-lookup"><span data-stu-id="621ce-107">Term</span></span>|<span data-ttu-id="621ce-108">정의</span><span class="sxs-lookup"><span data-stu-id="621ce-108">Definition</span></span>|  
|---|---|  
|`element`|<span data-ttu-id="621ce-109">필수.</span><span class="sxs-lookup"><span data-stu-id="621ce-109">Required.</span></span> <span data-ttu-id="621ce-110">조인 중인 컬렉션에 대 한 제어 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="621ce-110">The control variable for the collection being joined.</span></span>|  
|`type`|<span data-ttu-id="621ce-111">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="621ce-111">Optional.</span></span> <span data-ttu-id="621ce-112">`element`의 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="621ce-112">The type of `element`.</span></span> <span data-ttu-id="621ce-113">없으면 `type` 지정 된 형식의 `element` 에서 유추 됩니다 `collection`합니다.</span><span class="sxs-lookup"><span data-stu-id="621ce-113">If no `type` is specified, the type of `element` is inferred from `collection`.</span></span>|  
|`collection`|<span data-ttu-id="621ce-114">필수.</span><span class="sxs-lookup"><span data-stu-id="621ce-114">Required.</span></span> <span data-ttu-id="621ce-115">왼쪽에 있는 컬렉션과 결합할 컬렉션을 `Group Join` 연산자입니다.</span><span class="sxs-lookup"><span data-stu-id="621ce-115">The collection to combine with the collection that is on the left side of the `Group Join` operator.</span></span> <span data-ttu-id="621ce-116">A `Group Join` 절에 중첩 될 수는 `Join` 절 또는 다른 `Group Join` 절.</span><span class="sxs-lookup"><span data-stu-id="621ce-116">A `Group Join` clause can be nested in a `Join` clause or in another `Group Join` clause.</span></span>|  
|<span data-ttu-id="621ce-117">`key1` `Equals` `key2`</span><span class="sxs-lookup"><span data-stu-id="621ce-117">`key1` `Equals` `key2`</span></span>|<span data-ttu-id="621ce-118">필수.</span><span class="sxs-lookup"><span data-stu-id="621ce-118">Required.</span></span> <span data-ttu-id="621ce-119">조인 중인 컬렉션에 대 한 키를 식별 합니다.</span><span class="sxs-lookup"><span data-stu-id="621ce-119">Identifies keys for the collections being joined.</span></span> <span data-ttu-id="621ce-120">사용 해야는 `Equals` 조인 중인 컬렉션에서 키를 비교 하는 연산자입니다.</span><span class="sxs-lookup"><span data-stu-id="621ce-120">You must use the `Equals` operator to compare keys from the collections being joined.</span></span> <span data-ttu-id="621ce-121">조인 조건을 사용 하 여 결합할 수 있습니다는 `And` 여러 키를 식별 하는 연산자입니다.</span><span class="sxs-lookup"><span data-stu-id="621ce-121">You can combine join conditions by using the `And` operator to identify multiple keys.</span></span> <span data-ttu-id="621ce-122">`key1` 의 왼쪽에 있는 컬렉션에서 매개 변수 여야 합니다 `Join` 연산자.</span><span class="sxs-lookup"><span data-stu-id="621ce-122">The `key1` parameter must be from the collection on the left side of the `Join` operator.</span></span> <span data-ttu-id="621ce-123">`key2` 의 오른쪽에 있는 컬렉션에서 매개 변수 여야 합니다 `Join` 연산자.</span><span class="sxs-lookup"><span data-stu-id="621ce-123">The `key2` parameter must be from the collection on the right side of the `Join` operator.</span></span><br /><br /> <span data-ttu-id="621ce-124">조인 조건에 사용 되는 키 컬렉션에서 둘 이상의 항목을 포함 하는 식을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="621ce-124">The keys used in the join condition can be expressions that include more than one item from the collection.</span></span> <span data-ttu-id="621ce-125">그러나 각 키 식에는 해당 컬렉션의 항목만 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="621ce-125">However, each key expression can contain only items from its respective collection.</span></span>|  
|`expressionList`|<span data-ttu-id="621ce-126">필수.</span><span class="sxs-lookup"><span data-stu-id="621ce-126">Required.</span></span> <span data-ttu-id="621ce-127">컬렉션에서 요소 그룹 집계 되는 방법을 식별 하는 하나 이상의 식입니다.</span><span class="sxs-lookup"><span data-stu-id="621ce-127">One or more expressions that identify how the groups of elements from the collection are aggregated.</span></span> <span data-ttu-id="621ce-128">그룹화 된 결과의 멤버 이름을 식별 하려면 사용 합니다 `Group` 키워드 (`<alias> = Group`).</span><span class="sxs-lookup"><span data-stu-id="621ce-128">To identify a member name for the grouped results, use the `Group` keyword (`<alias> = Group`).</span></span> <span data-ttu-id="621ce-129">그룹에 적용할 집계 함수를 포함할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="621ce-129">You can also include aggregate functions to apply to the group.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="621ce-130">설명</span><span class="sxs-lookup"><span data-stu-id="621ce-130">Remarks</span></span>  
 <span data-ttu-id="621ce-131">`Group Join` 절 조인 중인 컬렉션에서 키 값을 일치를 기준으로 하는 두 개의 컬렉션을 결합 합니다.</span><span class="sxs-lookup"><span data-stu-id="621ce-131">The `Group Join` clause combines two collections based on matching key values from the collections being joined.</span></span> <span data-ttu-id="621ce-132">결과 컬렉션을 첫 번째 컬렉션에서 키 값과 일치 하는 두 번째 컬렉션에서 요소의 컬렉션을 참조 하는 멤버를 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="621ce-132">The resulting collection can contain a member that references a collection of elements from the second collection that match the key value from the first collection.</span></span> <span data-ttu-id="621ce-133">또한 두 번째 컬렉션에서 그룹화 된 요소에 적용할 집계 함수를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="621ce-133">You can also specify aggregate functions to apply to the grouped elements from the second collection.</span></span> <span data-ttu-id="621ce-134">집계 함수에 대 한 자세한 내용은 [Aggregate 절](../../../visual-basic/language-reference/queries/aggregate-clause.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="621ce-134">For information about aggregate functions, see [Aggregate Clause](../../../visual-basic/language-reference/queries/aggregate-clause.md).</span></span>  
  
 <span data-ttu-id="621ce-135">예를 들어, 관리자의 컬렉션 및 컬렉션 직원을 고려해 야 합니다.</span><span class="sxs-lookup"><span data-stu-id="621ce-135">Consider, for example, a collection of managers and a collection of employees.</span></span> <span data-ttu-id="621ce-136">두 컬렉션의 요소를 특정 관리자에 게 보고 하는 직원을 식별 하는 ManagerID 속성을 가집니다.</span><span class="sxs-lookup"><span data-stu-id="621ce-136">Elements from both collections have a ManagerID property that identifies the employees that report to a particular manager.</span></span> <span data-ttu-id="621ce-137">조인 연산의 결과는 각 관리자와 일치 하는 ManagerID 값을 사용 하 여 직원에 대 한 결과 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="621ce-137">The results from a join operation would contain a result for each manager and employee with a matching ManagerID value.</span></span> <span data-ttu-id="621ce-138">결과 `Group Join` 작업 관리자의 전체 목록을 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="621ce-138">The results from a `Group Join` operation would contain the complete list of managers.</span></span> <span data-ttu-id="621ce-139">각 관리자 결과 멤버는 특정 관리자와 일치 하는 직원의 목록을 참조 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="621ce-139">Each manager result would have a member that referenced the list of employees that were a match for the specific manager.</span></span>  
  
 <span data-ttu-id="621ce-140">결과 컬렉션을 `Group Join` 작업에서 식별 된 컬렉션에서 값의 조합을 포함할 수 있습니다는 `From` 절 및 식에서 식별 된를 `Into` 절을 `Group Join` 절.</span><span class="sxs-lookup"><span data-stu-id="621ce-140">The collection resulting from a `Group Join` operation can contain any combination of values from the collection identified in the `From` clause and the expressions identified in the `Into` clause of the `Group Join` clause.</span></span> <span data-ttu-id="621ce-141">에 대 한 올바른 식에 대 한 자세한 내용은 합니다 `Into` 절을 참조 하세요 [Aggregate 절](../../../visual-basic/language-reference/queries/aggregate-clause.md).</span><span class="sxs-lookup"><span data-stu-id="621ce-141">For more information about valid expressions for the `Into` clause, see [Aggregate Clause](../../../visual-basic/language-reference/queries/aggregate-clause.md).</span></span>  
  
 <span data-ttu-id="621ce-142">A `Group Join` 작업은 왼쪽에서 식별 된 컬렉션에서 모든 결과 반환 합니다 `Group Join` 연산자입니다.</span><span class="sxs-lookup"><span data-stu-id="621ce-142">A `Group Join` operation will return all results from the collection identified on the left side of the `Group Join` operator.</span></span> <span data-ttu-id="621ce-143">일치 하는 조인 중인 컬렉션에 없는 경우에 마찬가지입니다.</span><span class="sxs-lookup"><span data-stu-id="621ce-143">This is true even if there are no matches in the collection being joined.</span></span> <span data-ttu-id="621ce-144">비슷합니다는 `LEFT OUTER JOIN` sql에서입니다.</span><span class="sxs-lookup"><span data-stu-id="621ce-144">This is like a `LEFT OUTER JOIN` in SQL.</span></span>  
  
 <span data-ttu-id="621ce-145">사용할 수는 `Join` 절을 단일 컬렉션으로 결합할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="621ce-145">You can use the `Join` clause to combine collections into a single collection.</span></span> <span data-ttu-id="621ce-146">이 해당 하는 `INNER JOIN` sql에서입니다.</span><span class="sxs-lookup"><span data-stu-id="621ce-146">This is equivalent to an `INNER JOIN` in SQL.</span></span>  
  
## <a name="example"></a><span data-ttu-id="621ce-147">예제</span><span class="sxs-lookup"><span data-stu-id="621ce-147">Example</span></span>  
 <span data-ttu-id="621ce-148">다음 코드 예제를 사용 하 여 두 컬렉션 조인 된 `Group Join` 절.</span><span class="sxs-lookup"><span data-stu-id="621ce-148">The following code example joins two collections by using the `Group Join` clause.</span></span>  
  
 [!code-vb[VbSimpleQuerySamples#14](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/group-join-clause_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="621ce-149">참고 항목</span><span class="sxs-lookup"><span data-stu-id="621ce-149">See Also</span></span>  
 [<span data-ttu-id="621ce-150">Visual Basic의 LINQ 소개</span><span class="sxs-lookup"><span data-stu-id="621ce-150">Introduction to LINQ in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)  
 [<span data-ttu-id="621ce-151">쿼리</span><span class="sxs-lookup"><span data-stu-id="621ce-151">Queries</span></span>](../../../visual-basic/language-reference/queries/index.md)  
 [<span data-ttu-id="621ce-152">Select 절</span><span class="sxs-lookup"><span data-stu-id="621ce-152">Select Clause</span></span>](../../../visual-basic/language-reference/queries/select-clause.md)  
 [<span data-ttu-id="621ce-153">From 절</span><span class="sxs-lookup"><span data-stu-id="621ce-153">From Clause</span></span>](../../../visual-basic/language-reference/queries/from-clause.md)  
 [<span data-ttu-id="621ce-154">Join 절</span><span class="sxs-lookup"><span data-stu-id="621ce-154">Join Clause</span></span>](../../../visual-basic/language-reference/queries/join-clause.md)  
 [<span data-ttu-id="621ce-155">Where 절</span><span class="sxs-lookup"><span data-stu-id="621ce-155">Where Clause</span></span>](../../../visual-basic/language-reference/queries/where-clause.md)  
 [<span data-ttu-id="621ce-156">Group By 절</span><span class="sxs-lookup"><span data-stu-id="621ce-156">Group By Clause</span></span>](../../../visual-basic/language-reference/queries/group-by-clause.md)
