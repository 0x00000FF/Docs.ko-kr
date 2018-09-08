---
title: Join 절(Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.QueryJoinIn
- vb.QueryJoin
- vb.QueryJoinOn
helpviewer_keywords:
- queries [Visual Basic], Join
- Join statement [Visual Basic]
- Join clause [Visual Basic]
ms.assetid: 6dd37936-b27c-4e00-98ad-154b23f4de64
ms.openlocfilehash: b1551583079c66d1bf5f6963a42d5d24e518fff3
ms.sourcegitcommit: 64f4baed249341e5bf64d1385bf48e3f2e1a0211
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/07/2018
ms.locfileid: "44137345"
---
# <a name="join-clause-visual-basic"></a><span data-ttu-id="dc545-102">Join 절(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="dc545-102">Join Clause (Visual Basic)</span></span>
<span data-ttu-id="dc545-103">두 컬렉션을 단일 컬렉션으로 결합합니다.</span><span class="sxs-lookup"><span data-stu-id="dc545-103">Combines two collections into a single collection.</span></span> <span data-ttu-id="dc545-104">조인 연산은 일치 하는 키 기준으로 하며 사용 하 여 `Equals` 연산자입니다.</span><span class="sxs-lookup"><span data-stu-id="dc545-104">The join operation is based on matching keys and uses the `Equals` operator.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dc545-105">구문</span><span class="sxs-lookup"><span data-stu-id="dc545-105">Syntax</span></span>  
  
```  
Join element In collection _  
  [ joinClause _ ]   
  [ groupJoinClause ... _ ]   
On key1 Equals key2 [ And key3 Equals key4 [... ]  
```  
  
## <a name="parts"></a><span data-ttu-id="dc545-106">요소</span><span class="sxs-lookup"><span data-stu-id="dc545-106">Parts</span></span>  
 `element`  
 <span data-ttu-id="dc545-107">필수.</span><span class="sxs-lookup"><span data-stu-id="dc545-107">Required.</span></span> <span data-ttu-id="dc545-108">조인 중인 컬렉션에 대 한 제어 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="dc545-108">The control variable for the collection being joined.</span></span>  
  
 `collection`  
 <span data-ttu-id="dc545-109">필수.</span><span class="sxs-lookup"><span data-stu-id="dc545-109">Required.</span></span> <span data-ttu-id="dc545-110">왼쪽에 식별 된 컬렉션과 결합할 컬렉션을 `Join` 연산자입니다.</span><span class="sxs-lookup"><span data-stu-id="dc545-110">The collection to combine with the collection identified on the left side of the `Join` operator.</span></span> <span data-ttu-id="dc545-111">A `Join` 절의 다른 중첩 될 수 있습니다 `Join` 절 또는 `Group Join` 절.</span><span class="sxs-lookup"><span data-stu-id="dc545-111">A `Join` clause can be nested in another `Join` clause, or in a `Group Join` clause.</span></span>  
  
 `joinClause`  
 <span data-ttu-id="dc545-112">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="dc545-112">Optional.</span></span> <span data-ttu-id="dc545-113">하나 이상의 추가 `Join` 쿼리를 구체화 하는 절을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="dc545-113">One or more additional `Join` clauses to further refine the query.</span></span>  
  
 `groupJoinClause`  
 <span data-ttu-id="dc545-114">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="dc545-114">Optional.</span></span> <span data-ttu-id="dc545-115">하나 이상의 추가 `Group Join` 쿼리를 구체화 하는 절을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="dc545-115">One or more additional `Group Join` clauses to further refine the query.</span></span>  
  
 <span data-ttu-id="dc545-116">`key1` `Equals` `key2`</span><span class="sxs-lookup"><span data-stu-id="dc545-116">`key1` `Equals` `key2`</span></span>  
 <span data-ttu-id="dc545-117">필수.</span><span class="sxs-lookup"><span data-stu-id="dc545-117">Required.</span></span> <span data-ttu-id="dc545-118">조인 중인 컬렉션에 대 한 키를 식별 합니다.</span><span class="sxs-lookup"><span data-stu-id="dc545-118">Identifies keys for the collections being joined.</span></span> <span data-ttu-id="dc545-119">사용 해야는 `Equals` 조인 중인 컬렉션에서 키를 비교 하는 연산자입니다.</span><span class="sxs-lookup"><span data-stu-id="dc545-119">You must use the `Equals` operator to compare keys from the collections being joined.</span></span> <span data-ttu-id="dc545-120">조인 조건을 사용 하 여 결합할 수 있습니다는 `And` 여러 키를 식별 하는 연산자입니다.</span><span class="sxs-lookup"><span data-stu-id="dc545-120">You can combine join conditions by using the `And` operator to identify multiple keys.</span></span> <span data-ttu-id="dc545-121">`key1` 왼쪽에 있는 컬렉션에서 이어야 합니다는 `Join` 연산자입니다.</span><span class="sxs-lookup"><span data-stu-id="dc545-121">`key1` must be from the collection on the left side of the `Join` operator.</span></span> <span data-ttu-id="dc545-122">`key2` 오른쪽에 있는 컬렉션에서 이어야 합니다는 `Join` 연산자입니다.</span><span class="sxs-lookup"><span data-stu-id="dc545-122">`key2` must be from the collection on the right side of the `Join` operator.</span></span>  
  
 <span data-ttu-id="dc545-123">조인 조건에 사용 되는 키 컬렉션에서 둘 이상의 항목을 포함 하는 식을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dc545-123">The keys used in the join condition can be expressions that include more than one item from the collection.</span></span> <span data-ttu-id="dc545-124">그러나 각 키 식에는 해당 컬렉션의 항목만 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dc545-124">However, each key expression can contain only items from its respective collection.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="dc545-125">설명</span><span class="sxs-lookup"><span data-stu-id="dc545-125">Remarks</span></span>  
 <span data-ttu-id="dc545-126">`Join` 절 조인 중인 컬렉션에서 키 값을 일치를 기준으로 하는 두 개의 컬렉션을 결합 합니다.</span><span class="sxs-lookup"><span data-stu-id="dc545-126">The `Join` clause combines two collections based on matching key values from the collections being joined.</span></span> <span data-ttu-id="dc545-127">결과 컬렉션의 왼쪽에 식별 된 컬렉션에서 값의 조합을 포함할 수 있습니다 합니다 `Join` 연산자와에서 식별 된 컬렉션을 `Join` 절.</span><span class="sxs-lookup"><span data-stu-id="dc545-127">The resulting collection can contain any combination of values from the collection identified on the left side of the `Join` operator and the collection identified in the `Join` clause.</span></span> <span data-ttu-id="dc545-128">쿼리는 반환 하 여 지정 된 조건이 결과만 `Equals` 연산자 충족 됩니다.</span><span class="sxs-lookup"><span data-stu-id="dc545-128">The query will return only results for which the condition specified by the `Equals` operator is met.</span></span> <span data-ttu-id="dc545-129">이 해당 하는 `INNER JOIN` sql에서입니다.</span><span class="sxs-lookup"><span data-stu-id="dc545-129">This is equivalent to an `INNER JOIN` in SQL.</span></span>  
  
 <span data-ttu-id="dc545-130">여러 개 사용할 수 있습니다 `Join` 둘 이상의 컬렉션을 단일 컬렉션으로 조인 하는 쿼리 절.</span><span class="sxs-lookup"><span data-stu-id="dc545-130">You can use multiple `Join` clauses in a query to join two or more collections into a single collection.</span></span>  
  
 <span data-ttu-id="dc545-131">없는 컬렉션을 결합 하는 암시적 조인을 수행할 수 있습니다는 `Join` 절.</span><span class="sxs-lookup"><span data-stu-id="dc545-131">You can perform an implicit join to combine collections without the `Join` clause.</span></span> <span data-ttu-id="dc545-132">이렇게 하려면 여러 개 포함 `In` 절에 `From` 절 지정을 `Where` 조인에 사용 하려는 키를 식별 하는 절.</span><span class="sxs-lookup"><span data-stu-id="dc545-132">To do this, include multiple `In` clauses in your `From` clause and specify a `Where` clause that identifies the keys that you want to use for the join.</span></span>  
  
 <span data-ttu-id="dc545-133">사용할 수는 `Group Join` 절을 단일 계층 구조 컬렉션으로 결합할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dc545-133">You can use the `Group Join` clause to combine collections into a single hierarchical collection.</span></span> <span data-ttu-id="dc545-134">비슷합니다는 `LEFT OUTER JOIN` sql에서입니다.</span><span class="sxs-lookup"><span data-stu-id="dc545-134">This is like a `LEFT OUTER JOIN` in SQL.</span></span>  
  
## <a name="example"></a><span data-ttu-id="dc545-135">예제</span><span class="sxs-lookup"><span data-stu-id="dc545-135">Example</span></span>  
 <span data-ttu-id="dc545-136">다음 코드 예제에서는 고객 목록을 고객의 주문을 결합할 암시적 조인을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="dc545-136">The following code example performs an implicit join to combine a list of customers with their orders.</span></span>  
  
 [!code-vb[VbSimpleQuerySamples#13](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/join-clause_1.vb)]  
  
## <a name="example"></a><span data-ttu-id="dc545-137">예제</span><span class="sxs-lookup"><span data-stu-id="dc545-137">Example</span></span>  
 <span data-ttu-id="dc545-138">다음 코드 예제를 사용 하 여 두 컬렉션 조인 된 `Join` 절.</span><span class="sxs-lookup"><span data-stu-id="dc545-138">The following code example joins two collections by using the `Join` clause.</span></span>  
  
 [!code-vb[VbSimpleQuerySamples#12](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/join-clause_2.vb)]  
  
 <span data-ttu-id="dc545-139">이 예제는 다음과 유사한 출력을 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="dc545-139">This example will produce output similar to the following:</span></span>  
  
 `winlogon (968), Windows Logon`  
  
 `explorer (2424), File Explorer`  
  
 `cmd (5136), Command Window`  
  
## <a name="example"></a><span data-ttu-id="dc545-140">예제</span><span class="sxs-lookup"><span data-stu-id="dc545-140">Example</span></span>  
 <span data-ttu-id="dc545-141">다음 코드 예제를 사용 하 여 두 컬렉션 조인 된 `Join` 두 개의 키 열을 사용 하 여 절.</span><span class="sxs-lookup"><span data-stu-id="dc545-141">The following code example joins two collections by using the `Join` clause with two key columns.</span></span>  
  
 [!code-vb[VbSimpleQuerySamples#17](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/join-clause_3.vb)]  
  
 <span data-ttu-id="dc545-142">이 예제에서는 다음과 유사한 출력을 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="dc545-142">The example will produce output similar to the following:</span></span>  
  
 `winlogon (968), Windows Logon, Priority = 13`  
  
 `cmd (700), Command Window, Priority = 8`  
  
 `explorer (2424), File Explorer, Priority = 8`  
  
## <a name="see-also"></a><span data-ttu-id="dc545-143">참고 항목</span><span class="sxs-lookup"><span data-stu-id="dc545-143">See Also</span></span>  
 [<span data-ttu-id="dc545-144">Visual Basic의 LINQ 소개</span><span class="sxs-lookup"><span data-stu-id="dc545-144">Introduction to LINQ in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)  
 [<span data-ttu-id="dc545-145">쿼리</span><span class="sxs-lookup"><span data-stu-id="dc545-145">Queries</span></span>](../../../visual-basic/language-reference/queries/index.md)  
 [<span data-ttu-id="dc545-146">Select 절</span><span class="sxs-lookup"><span data-stu-id="dc545-146">Select Clause</span></span>](../../../visual-basic/language-reference/queries/select-clause.md)  
 [<span data-ttu-id="dc545-147">From 절</span><span class="sxs-lookup"><span data-stu-id="dc545-147">From Clause</span></span>](../../../visual-basic/language-reference/queries/from-clause.md)  
 [<span data-ttu-id="dc545-148">Group Join 절</span><span class="sxs-lookup"><span data-stu-id="dc545-148">Group Join Clause</span></span>](../../../visual-basic/language-reference/queries/group-join-clause.md)  
 [<span data-ttu-id="dc545-149">Where 절</span><span class="sxs-lookup"><span data-stu-id="dc545-149">Where Clause</span></span>](../../../visual-basic/language-reference/queries/where-clause.md)
