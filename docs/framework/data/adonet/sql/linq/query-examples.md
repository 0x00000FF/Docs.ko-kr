---
title: 쿼리 예제
ms.date: 03/30/2017
ms.assetid: 137f8677-494c-4d49-95ce-c17742f2d01f
ms.openlocfilehash: 38454890e05b00cd92bca909ce0c7975f5ef1f6e
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/08/2018
ms.locfileid: "44211868"
---
# <a name="query-examples"></a><span data-ttu-id="be5fd-102">쿼리 예제</span><span class="sxs-lookup"><span data-stu-id="be5fd-102">Query Examples</span></span>
<span data-ttu-id="be5fd-103">이 섹션에서는 일반적인 Visual Basic 및 C# 예제 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] 쿼리 합니다.</span><span class="sxs-lookup"><span data-stu-id="be5fd-103">This section provides Visual Basic and C# examples of typical [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] queries.</span></span> <span data-ttu-id="be5fd-104">Visual Studio를 사용 하는 개발자 샘플 섹션에 제공 하는 샘플 솔루션에서 더 많은 예제를 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="be5fd-104">Developers using Visual Studio can find many more examples in a sample solution available in the Samples section.</span></span> <span data-ttu-id="be5fd-105">자세한 내용은 [샘플](../../../../../../docs/framework/data/adonet/sql/linq/samples.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="be5fd-105">For more information, see [Samples](../../../../../../docs/framework/data/adonet/sql/linq/samples.md).</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="be5fd-106">*db* 의 코드 예제에서는 흔히 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] 설명서.</span><span class="sxs-lookup"><span data-stu-id="be5fd-106">*db* is often used in code examples in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] documentation.</span></span> <span data-ttu-id="be5fd-107">*db* 의 인스턴스로 간주 됩니다는 *Northwind* 클래스에서 상속 되는 <xref:System.Data.Linq.DataContext>합니다.</span><span class="sxs-lookup"><span data-stu-id="be5fd-107">*db* is assumed to be an instance of a *Northwind* class, which inherits from <xref:System.Data.Linq.DataContext>.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="be5fd-108">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="be5fd-108">In This Section</span></span>  
 [<span data-ttu-id="be5fd-109">집계 쿼리</span><span class="sxs-lookup"><span data-stu-id="be5fd-109">Aggregate Queries</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/aggregate-queries.md)  
 <span data-ttu-id="be5fd-110"><xref:System.Linq.Enumerable.Average%2A>, <xref:System.Linq.Enumerable.Count%2A> 등의 사용 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="be5fd-110">Describes how to use <xref:System.Linq.Enumerable.Average%2A>, <xref:System.Linq.Enumerable.Count%2A>, and so forth.</span></span>  
  
 [<span data-ttu-id="be5fd-111">시퀀스의 첫 번째 요소 반환</span><span class="sxs-lookup"><span data-stu-id="be5fd-111">Return the First Element in a Sequence</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/return-the-first-element-in-a-sequence.md)  
 <span data-ttu-id="be5fd-112"><xref:System.Linq.Enumerable.First%2A> 사용 예제를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="be5fd-112">Provides examples of using <xref:System.Linq.Enumerable.First%2A>.</span></span>  
  
 [<span data-ttu-id="be5fd-113">시퀀스에서 요소 반환 또는 건너뛰기</span><span class="sxs-lookup"><span data-stu-id="be5fd-113">Return Or Skip Elements in a Sequence</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/return-or-skip-elements-in-a-sequence.md)  
 <span data-ttu-id="be5fd-114"><xref:System.Linq.Enumerable.Take%2A> 및 <xref:System.Linq.Enumerable.Skip%2A> 사용 예제를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="be5fd-114">Provides examples of using <xref:System.Linq.Enumerable.Take%2A> and <xref:System.Linq.Enumerable.Skip%2A>.</span></span>  
  
 [<span data-ttu-id="be5fd-115">시퀀스의 요소 정렬</span><span class="sxs-lookup"><span data-stu-id="be5fd-115">Sort Elements in a Sequence</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/sort-elements-in-a-sequence.md)  
 <span data-ttu-id="be5fd-116"><xref:System.Linq.Enumerable.OrderBy%2A> 사용 예제를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="be5fd-116">Provides examples of using <xref:System.Linq.Enumerable.OrderBy%2A>.</span></span>  
  
 [<span data-ttu-id="be5fd-117">시퀀스의 요소 그룹화</span><span class="sxs-lookup"><span data-stu-id="be5fd-117">Group Elements in a Sequence</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/group-elements-in-a-sequence.md)  
 <span data-ttu-id="be5fd-118"><xref:System.Linq.Enumerable.GroupBy%2A> 사용 예제를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="be5fd-118">Provides examples of using <xref:System.Linq.Enumerable.GroupBy%2A>.</span></span>  
  
 [<span data-ttu-id="be5fd-119">시퀀스에서 중복 요소 제거</span><span class="sxs-lookup"><span data-stu-id="be5fd-119">Eliminate Duplicate Elements from a Sequence</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/eliminate-duplicate-elements-from-a-sequence.md)  
 <span data-ttu-id="be5fd-120"><xref:System.Linq.Enumerable.Distinct%2A> 사용 예제를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="be5fd-120">Provides examples of using <xref:System.Linq.Enumerable.Distinct%2A>.</span></span>  
  
 [<span data-ttu-id="be5fd-121">시퀀스에서 일부 또는 모든 요소가 조건을 만족하는지 확인</span><span class="sxs-lookup"><span data-stu-id="be5fd-121">Determine if Any or All Elements in a Sequence Satisfy a Condition</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/determine-if-any-or-all-elements-in-a-sequence-satisfy-a-condition.md)  
 <span data-ttu-id="be5fd-122"><xref:System.Linq.Enumerable.All%2A> 및 <xref:System.Linq.Enumerable.Any%2A> 사용 예제를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="be5fd-122">Provides examples of using <xref:System.Linq.Enumerable.All%2A> and <xref:System.Linq.Enumerable.Any%2A>.</span></span>  
  
 [<span data-ttu-id="be5fd-123">두 시퀀스 연결</span><span class="sxs-lookup"><span data-stu-id="be5fd-123">Concatenate Two Sequences</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/concatenate-two-sequences.md)  
 <span data-ttu-id="be5fd-124"><xref:System.Linq.Enumerable.Concat%2A> 사용 예제를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="be5fd-124">Provides examples of using <xref:System.Linq.Enumerable.Concat%2A>.</span></span>  
  
 [<span data-ttu-id="be5fd-125">두 시퀀스 간의 차집합 반환</span><span class="sxs-lookup"><span data-stu-id="be5fd-125">Return the Set Difference Between Two Sequences</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/return-the-set-difference-between-two-sequences.md)  
 <span data-ttu-id="be5fd-126"><xref:System.Linq.Enumerable.Except%2A> 사용 예제를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="be5fd-126">Provides examples of using <xref:System.Linq.Enumerable.Except%2A>.</span></span>  
  
 [<span data-ttu-id="be5fd-127">두 시퀀스의 교집합 반환</span><span class="sxs-lookup"><span data-stu-id="be5fd-127">Return the Set Intersection of Two Sequences</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/return-the-set-intersection-of-two-sequences.md)  
 <span data-ttu-id="be5fd-128"><xref:System.Linq.Enumerable.Intersect%2A> 사용 예제를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="be5fd-128">Provides examples of using <xref:System.Linq.Enumerable.Intersect%2A>.</span></span>  
  
 [<span data-ttu-id="be5fd-129">두 시퀀스의 합집합 반환</span><span class="sxs-lookup"><span data-stu-id="be5fd-129">Return the Set Union of Two Sequences</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/return-the-set-union-of-two-sequences.md)  
 <span data-ttu-id="be5fd-130"><xref:System.Linq.Enumerable.Union%2A> 사용 예제를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="be5fd-130">Provides examples of using <xref:System.Linq.Enumerable.Union%2A>.</span></span>  
  
 [<span data-ttu-id="be5fd-131">시퀀스를 배열로 변환</span><span class="sxs-lookup"><span data-stu-id="be5fd-131">Convert a Sequence to an Array</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/convert-a-sequence-to-an-array.md)  
 <span data-ttu-id="be5fd-132"><xref:System.Linq.Enumerable.ToArray%2A> 사용 예제를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="be5fd-132">Provides examples of using <xref:System.Linq.Enumerable.ToArray%2A>.</span></span>  
  
 [<span data-ttu-id="be5fd-133">제네릭 목록으로 시퀀스 변환</span><span class="sxs-lookup"><span data-stu-id="be5fd-133">Convert a Sequence to a Generic List</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/convert-a-sequence-to-a-generic-list.md)  
 <span data-ttu-id="be5fd-134"><xref:System.Linq.Enumerable.ToList%2A> 사용 예제를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="be5fd-134">Provides examples of using <xref:System.Linq.Enumerable.ToList%2A>.</span></span>  
  
 [<span data-ttu-id="be5fd-135">제네릭 IEnumerable로 형식 변환</span><span class="sxs-lookup"><span data-stu-id="be5fd-135">Convert a Type to a Generic IEnumerable</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/convert-a-type-to-a-generic-ienumerable.md)  
 <span data-ttu-id="be5fd-136"><xref:System.Linq.Enumerable.AsEnumerable%2A> 사용 예제를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="be5fd-136">Provides examples of using <xref:System.Linq.Enumerable.AsEnumerable%2A>.</span></span>  
  
 [<span data-ttu-id="be5fd-137">조인 및 교차곱 쿼리 작성</span><span class="sxs-lookup"><span data-stu-id="be5fd-137">Formulate Joins and Cross-Product Queries</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/formulate-joins-and-cross-product-queries.md)  
 <span data-ttu-id="be5fd-138">`from`, `where` 및 `select` 절에서 외래 키 탐색 사용 예제를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="be5fd-138">Provides examples of using foreign-key navigation in the `from`, `where`, and `select` clauses.</span></span>  
  
 [<span data-ttu-id="be5fd-139">프로젝션 작성</span><span class="sxs-lookup"><span data-stu-id="be5fd-139">Formulate Projections</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/formulate-projections.md)  
 <span data-ttu-id="be5fd-140">결합 예제를 제공 `select` 다른 기능과 함께 (예를 들어 *무명 형식을*) 쿼리 투영 합니다.</span><span class="sxs-lookup"><span data-stu-id="be5fd-140">Provides examples of combining `select` with other features (for example, *anonymous types*) to form query projections.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="be5fd-141">관련 단원</span><span class="sxs-lookup"><span data-stu-id="be5fd-141">Related Sections</span></span>  
 [<span data-ttu-id="be5fd-142">표준 쿼리 연산자 개요</span><span class="sxs-lookup"><span data-stu-id="be5fd-142">Standard Query Operators Overview</span></span>](https://msdn.microsoft.com/library/24cda21e-8af8-4632-b519-c404a839b9b2)  
 <span data-ttu-id="be5fd-143">표준 쿼리 연산자의 개념을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="be5fd-143">Explains the concept of standard query operators.</span></span>  
  
 [<span data-ttu-id="be5fd-144">쿼리 개념</span><span class="sxs-lookup"><span data-stu-id="be5fd-144">Query Concepts</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/query-concepts.md)  
 <span data-ttu-id="be5fd-145">[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] 사용 개념이 쿼리에 어떻게 적용되는지 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="be5fd-145">Explains how [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] uses concepts that apply to queries.</span></span>  
  
 [<span data-ttu-id="be5fd-146">프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="be5fd-146">Programming Guide</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/programming-guide.md)  
 <span data-ttu-id="be5fd-147">[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] 관련 프로그래밍 개념을 설명하는 항목에 대한 포털을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="be5fd-147">Provides a portal to topics that explain programming concepts related to [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span></span>
