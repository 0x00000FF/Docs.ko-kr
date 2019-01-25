---
title: 집합 작업 (Visual Basic)
ms.date: 07/20/2015
ms.assetid: 2b06e822-e030-438f-9db7-ee402bd3a706
ms.openlocfilehash: b1b515c7eee11f7aadc1d34223dbb4ea1367842d
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54741878"
---
# <a name="set-operations-visual-basic"></a><span data-ttu-id="eb121-102">집합 작업 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="eb121-102">Set Operations (Visual Basic)</span></span>
<span data-ttu-id="eb121-103">LINQ의 집합 작업은 동일 컬렉션이나 별개 컬렉션(또는 집합)에 동등한 요소가 있는지 여부에 따라 결과 집합을 생성하는 쿼리 작업을 가리킵니다.</span><span class="sxs-lookup"><span data-stu-id="eb121-103">Set operations in LINQ refer to query operations that produce a result set that is based on the presence or absence of equivalent elements within the same or separate collections (or sets).</span></span>  
  
 <span data-ttu-id="eb121-104">다음 섹션에는 집합 작업을 수행하는 표준 쿼리 연산자 메서드가 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eb121-104">The standard query operator methods that perform set operations are listed in the following section.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="eb121-105">메서드</span><span class="sxs-lookup"><span data-stu-id="eb121-105">Methods</span></span>  
  
|<span data-ttu-id="eb121-106">메서드 이름</span><span class="sxs-lookup"><span data-stu-id="eb121-106">Method Name</span></span>|<span data-ttu-id="eb121-107">설명</span><span class="sxs-lookup"><span data-stu-id="eb121-107">Description</span></span>|<span data-ttu-id="eb121-108">Visual Basic 쿼리 식 구문</span><span class="sxs-lookup"><span data-stu-id="eb121-108">Visual Basic Query Expression Syntax</span></span>|<span data-ttu-id="eb121-109">추가 정보</span><span class="sxs-lookup"><span data-stu-id="eb121-109">More Information</span></span>|  
|-----------------|-----------------|------------------------------------------|----------------------|  
|<span data-ttu-id="eb121-110">Distinct</span><span class="sxs-lookup"><span data-stu-id="eb121-110">Distinct</span></span>|<span data-ttu-id="eb121-111">컬렉션에서 중복 값을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="eb121-111">Removes duplicate values from a collection.</span></span>|`Distinct`|<xref:System.Linq.Enumerable.Distinct%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Distinct%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="eb121-112">Except</span><span class="sxs-lookup"><span data-stu-id="eb121-112">Except</span></span>|<span data-ttu-id="eb121-113">두 번째 컬렉션에 표시되지 않는 한 컬렉션의 요소를 의미하는 차집합을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="eb121-113">Returns the set difference, which means the elements of one collection that do not appear in a second collection.</span></span>|<span data-ttu-id="eb121-114">해당 사항 없음.</span><span class="sxs-lookup"><span data-stu-id="eb121-114">Not applicable.</span></span>|<xref:System.Linq.Enumerable.Except%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Except%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="eb121-115">Intersect</span><span class="sxs-lookup"><span data-stu-id="eb121-115">Intersect</span></span>|<span data-ttu-id="eb121-116">두 컬렉션에 각각 표시되는 요소를 의미하는 교집합을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="eb121-116">Returns the set intersection, which means elements that appear in each of two collections.</span></span>|<span data-ttu-id="eb121-117">해당 사항 없음.</span><span class="sxs-lookup"><span data-stu-id="eb121-117">Not applicable.</span></span>|<xref:System.Linq.Enumerable.Intersect%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Intersect%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="eb121-118">Union</span><span class="sxs-lookup"><span data-stu-id="eb121-118">Union</span></span>|<span data-ttu-id="eb121-119">두 컬렉션 중 하나에 표시되는 고유한 요소를 의미하는 합집합을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="eb121-119">Returns the set union, which means unique elements that appear in either of two collections.</span></span>|<span data-ttu-id="eb121-120">해당 사항 없음.</span><span class="sxs-lookup"><span data-stu-id="eb121-120">Not applicable.</span></span>|<xref:System.Linq.Enumerable.Union%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Union%2A?displayProperty=nameWithType>|  
  
## <a name="comparison-of-set-operations"></a><span data-ttu-id="eb121-121">집합 작업 비교</span><span class="sxs-lookup"><span data-stu-id="eb121-121">Comparison of Set Operations</span></span>  
  
### <a name="distinct"></a><span data-ttu-id="eb121-122">Distinct</span><span class="sxs-lookup"><span data-stu-id="eb121-122">Distinct</span></span>  
 <span data-ttu-id="eb121-123">다음 그림에서는 문자 시퀀스에 대한 <xref:System.Linq.Enumerable.Distinct%2A?displayProperty=nameWithType> 메서드의 동작을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="eb121-123">The following illustration depicts the behavior of the <xref:System.Linq.Enumerable.Distinct%2A?displayProperty=nameWithType> method on a sequence of characters.</span></span> <span data-ttu-id="eb121-124">반환된 시퀀스에는 입력 시퀀스의 고유한 요소가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="eb121-124">The returned sequence contains the unique elements from the input sequence.</span></span>  
  
 <span data-ttu-id="eb121-125">![Distinct&#40;&#41;의 동작을 보여 주는 그래픽](../../../../csharp/programming-guide/concepts/linq/media/distinct.png "Distinct")</span><span class="sxs-lookup"><span data-stu-id="eb121-125">![Graphic showing the behavior of Distinct&#40;&#41;.](../../../../csharp/programming-guide/concepts/linq/media/distinct.png "Distinct")</span></span>  
  
### <a name="except"></a><span data-ttu-id="eb121-126">Except</span><span class="sxs-lookup"><span data-stu-id="eb121-126">Except</span></span>  
 <span data-ttu-id="eb121-127">다음 그림에서는 <xref:System.Linq.Enumerable.Except%2A?displayProperty=nameWithType>의 동작을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="eb121-127">The following illustration depicts the behavior of <xref:System.Linq.Enumerable.Except%2A?displayProperty=nameWithType>.</span></span> <span data-ttu-id="eb121-128">반환된 시퀀스에는 두 번째 입력 시퀀스에 없는 첫 번째 입력 시퀀스의 요소만 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="eb121-128">The returned sequence contains only the elements from the first input sequence that are not in the second input sequence.</span></span>  
  
 <span data-ttu-id="eb121-129">![Except&#40;&#41;의 작업을 보여 주는 그래픽](../../../../csharp/programming-guide/concepts/linq/media/except.png "Except")</span><span class="sxs-lookup"><span data-stu-id="eb121-129">![Graphic showing the action of Except&#40;&#41;.](../../../../csharp/programming-guide/concepts/linq/media/except.png "Except")</span></span>  
  
### <a name="intersect"></a><span data-ttu-id="eb121-130">Intersect</span><span class="sxs-lookup"><span data-stu-id="eb121-130">Intersect</span></span>  
 <span data-ttu-id="eb121-131">다음 그림에서는 <xref:System.Linq.Enumerable.Intersect%2A?displayProperty=nameWithType>의 동작을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="eb121-131">The following illustration depicts the behavior of <xref:System.Linq.Enumerable.Intersect%2A?displayProperty=nameWithType>.</span></span> <span data-ttu-id="eb121-132">반환된 시퀀스에는 입력 시퀀스 둘 다에 공통적으로 있는 요소가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="eb121-132">The returned sequence contains the elements that are common to both of the input sequences.</span></span>  
  
 <span data-ttu-id="eb121-133">![두 시퀀스의 교집합을 보여 주는 그래픽](../../../../csharp/programming-guide/concepts/linq/media/intersect.png "Intersect")</span><span class="sxs-lookup"><span data-stu-id="eb121-133">![Graphic showing the intersection of two sequences.](../../../../csharp/programming-guide/concepts/linq/media/intersect.png "Intersect")</span></span>  
  
### <a name="union"></a><span data-ttu-id="eb121-134">Union</span><span class="sxs-lookup"><span data-stu-id="eb121-134">Union</span></span>  
 <span data-ttu-id="eb121-135">다음 그림은 두 개의 문자 시퀀스에 대한 합집합을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="eb121-135">The following illustration depicts a union operation on two sequences of characters.</span></span> <span data-ttu-id="eb121-136">반환된 시퀀스에는 두 입력 시퀀스의 고유한 요소가 모두 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="eb121-136">The returned sequence contains the unique elements from both input sequences.</span></span>  
  
 <span data-ttu-id="eb121-137">![두 시퀀스의 합집합을 보여주는 그래픽](../../../../csharp/programming-guide/concepts/linq/media/union.png "Union")</span><span class="sxs-lookup"><span data-stu-id="eb121-137">![Graphic showing the union of two sequences.](../../../../csharp/programming-guide/concepts/linq/media/union.png "Union")</span></span>  
  
## <a name="query-expression-syntax-example"></a><span data-ttu-id="eb121-138">쿼리 식 구문 예제</span><span class="sxs-lookup"><span data-stu-id="eb121-138">Query Expression Syntax Example</span></span>  
 <span data-ttu-id="eb121-139">다음 예제에서는 `Distinct` 정수 목록에서 고유한 숫자를 반환 하는 LINQ 쿼리 절.</span><span class="sxs-lookup"><span data-stu-id="eb121-139">The following example uses the `Distinct` clause in a LINQ query to return the unique numbers from a list of integers.</span></span>  
  
 [!code-vb[CsLINQSetOps#1](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/set-operations_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="eb121-140">참고자료</span><span class="sxs-lookup"><span data-stu-id="eb121-140">See also</span></span>
- <xref:System.Linq>
- [<span data-ttu-id="eb121-141">표준 쿼리 연산자 개요(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="eb121-141">Standard Query Operators Overview (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md)
- [<span data-ttu-id="eb121-142">Distinct 절</span><span class="sxs-lookup"><span data-stu-id="eb121-142">Distinct Clause</span></span>](../../../../visual-basic/language-reference/queries/distinct-clause.md)
- [<span data-ttu-id="eb121-143">방법: (LINQ) (Visual Basic) 문자열 컬렉션 결합 및 비교</span><span class="sxs-lookup"><span data-stu-id="eb121-143">How to: Combine and Compare String Collections (LINQ) (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/how-to-combine-and-compare-string-collections-linq.md)
- [<span data-ttu-id="eb121-144">방법: (LINQ) (Visual Basic)의 두 목록 간의 차집합 구하기</span><span class="sxs-lookup"><span data-stu-id="eb121-144">How to: Find the Set Difference Between Two Lists (LINQ) (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/how-to-find-the-set-difference-between-two-lists-linq.md)
