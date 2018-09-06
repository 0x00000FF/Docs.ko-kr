---
title: '방법: 조인을 사용하여 데이터와 LINQ 결합(Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- queries [LINQ in Visual Basic], joins
- joins [LINQ in Visual Basic]
- Join clause [LINQ in Visual Basic]
- Group Join clause [Visual Basic]
- joining [LINQ in Visual Basic]
- queries [LINQ in Visual Basic], how-to topics
ms.assetid: 5b00a478-035b-41c6-8918-be1a97728396
ms.openlocfilehash: 4db5d288d79379b677bb19b2eba0d094e0d71bc8
ms.sourcegitcommit: 3c1c3ba79895335ff3737934e39372555ca7d6d0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/05/2018
ms.locfileid: "43748406"
---
# <a name="how-to-combine-data-with-linq-by-using-joins-visual-basic"></a><span data-ttu-id="99fd1-102">방법: 조인을 사용하여 데이터와 LINQ 결합(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="99fd1-102">How to: Combine Data with LINQ by Using Joins (Visual Basic)</span></span>
<span data-ttu-id="99fd1-103">Visual Basic에서 제공 합니다 `Join` 고 `Group Join` 쿼리 절을 사용 하면 컬렉션 간의 공통 값을 기반으로 하는 여러 컬렉션의 콘텐츠를 결합할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="99fd1-103">Visual Basic provides the `Join` and `Group Join` query clauses to enable you to combine the contents of multiple collections based on common values between the collections.</span></span> <span data-ttu-id="99fd1-104">이러한 값 이라고 *키* 값입니다.</span><span class="sxs-lookup"><span data-stu-id="99fd1-104">These values are known as *key* values.</span></span> <span data-ttu-id="99fd1-105">관계형 데이터베이스 개념에 익숙한 개발자는 `Join` INNER JOIN으로 절 및 `Group Join` 으로 효과적으로 LEFT OUTER JOIN 절.</span><span class="sxs-lookup"><span data-stu-id="99fd1-105">Developers familiar with relational database concepts will recognize the `Join` clause as an INNER JOIN and the `Group Join` clause as, effectively, a LEFT OUTER JOIN.</span></span>  
  
 <span data-ttu-id="99fd1-106">이 항목의 예제를 사용 하 여 데이터를 결합 하는 몇 가지 방법을 설명 합니다 `Join` 및 `Group Join` 쿼리 절.</span><span class="sxs-lookup"><span data-stu-id="99fd1-106">The examples in this topic demonstrate a few ways to combine data by using the `Join` and `Group Join` query clauses.</span></span>  
  
## <a name="create-a-project-and-add-sample-data"></a><span data-ttu-id="99fd1-107">프로젝트를 만들고 샘플 데이터 추가</span><span class="sxs-lookup"><span data-stu-id="99fd1-107">Create a Project and Add Sample Data</span></span>  
  
#### <a name="to-create-a-project-that-contains-sample-data-and-types"></a><span data-ttu-id="99fd1-108">샘플 데이터 및 유형을 포함 하는 프로젝트를 만들려면</span><span class="sxs-lookup"><span data-stu-id="99fd1-108">To create a project that contains sample data and types</span></span>  
  
1.  <span data-ttu-id="99fd1-109">이 항목의 샘플을 실행 하려면 Visual Studio를 열고 새 Visual Basic 콘솔 응용 프로그램 프로젝트를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="99fd1-109">To run the samples in this topic, open Visual Studio and add a new Visual Basic Console Application project.</span></span> <span data-ttu-id="99fd1-110">Visual Basic에서 생성 된 Module1.vb 파일을 두 번 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="99fd1-110">Double-click the Module1.vb file created by Visual Basic.</span></span>  
  
2.  <span data-ttu-id="99fd1-111">이 항목에서는 사용 샘플은 `Person` 및 `Pet` 유형 및 다음 코드 예제에서 데이터입니다.</span><span class="sxs-lookup"><span data-stu-id="99fd1-111">The samples in this topic use the `Person` and `Pet` types and data from the following code example.</span></span> <span data-ttu-id="99fd1-112">이 코드는 기본 복사 `Module1` Visual Basic에서 생성 하는 모듈입니다.</span><span class="sxs-lookup"><span data-stu-id="99fd1-112">Copy this code into the default `Module1` module created by Visual Basic.</span></span>  
  
     [!code-vb[VbLINQHowTos#1](../../../../visual-basic/programming-guide/language-features/linq/codesnippet/VisualBasic/how-to-combine-data-with-linq-by-using-joins_1.vb)]  
    [!code-vb[VbLINQHowTos#2](../../../../visual-basic/programming-guide/language-features/linq/codesnippet/VisualBasic/how-to-combine-data-with-linq-by-using-joins_2.vb)]  
  
## <a name="perform-an-inner-join-by-using-the-join-clause"></a><span data-ttu-id="99fd1-113">Join 절을 사용 하 여 내부 조인 수행</span><span class="sxs-lookup"><span data-stu-id="99fd1-113">Perform an Inner Join by Using the Join Clause</span></span>  
 <span data-ttu-id="99fd1-114">INNER JOIN 두 컬렉션에서 데이터를 결합합니다.</span><span class="sxs-lookup"><span data-stu-id="99fd1-114">An INNER JOIN combines data from two collections.</span></span> <span data-ttu-id="99fd1-115">지정된 된 키 값과 일치 하는 항목이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="99fd1-115">Items for which the specified key values match are included.</span></span> <span data-ttu-id="99fd1-116">다른 컬렉션에 일치 하는 항목이 없는 두 컬렉션에서 모든 항목은 제외 됩니다.</span><span class="sxs-lookup"><span data-stu-id="99fd1-116">Any items from either collection that do not have a matching item in the other collection are excluded.</span></span>  
  
 <span data-ttu-id="99fd1-117">Visual Basic의 LINQ 내부 조인을 수행 하는 것에 대 한 두 가지 옵션을 제공 합니다: 암시적 조인 및 명시적 조인을 합니다.</span><span class="sxs-lookup"><span data-stu-id="99fd1-117">In Visual Basic, LINQ provides two options for performing an INNER JOIN: an implicit join and an explicit join.</span></span>  
  
 <span data-ttu-id="99fd1-118">암시적 조인을 지정 조인할 컬렉션을 `From` 절에서 일치 하는 키 필드를 식별 하 고는 `Where` 절.</span><span class="sxs-lookup"><span data-stu-id="99fd1-118">An implicit join specifies the collections to be joined in a `From` clause and identifies the matching key fields in a `Where` clause.</span></span> <span data-ttu-id="99fd1-119">Visual Basic에는 암시적으로 지정 된 키 필드를 기반으로 두 컬렉션 조인 합니다.</span><span class="sxs-lookup"><span data-stu-id="99fd1-119">Visual Basic implicitly joins the two collections based on the specified key fields.</span></span>  
  
 <span data-ttu-id="99fd1-120">명시적 조인을 사용 하 여 지정할 수 있습니다는 `Join` 절에 조인에 사용 하는 키 필드에 대 한 정확 하 게 하려는 경우.</span><span class="sxs-lookup"><span data-stu-id="99fd1-120">You can specify an explicit join by using the `Join` clause when you want to be specific about which key fields to use in the join.</span></span> <span data-ttu-id="99fd1-121">이 경우에 `Where` 절을 사용 하 여 쿼리 결과 필터링 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="99fd1-121">In this case, a `Where` clause can still be used to filter the query results.</span></span>  
  
#### <a name="to-perform-an-inner-join-by-using-the-join-clause"></a><span data-ttu-id="99fd1-122">Join 절을 사용 하 여 Inner Join을 수행 하려면</span><span class="sxs-lookup"><span data-stu-id="99fd1-122">To perform an Inner Join by using the Join clause</span></span>  
  
1.  <span data-ttu-id="99fd1-123">다음 코드를 추가 합니다 `Module1` 모두 암시적 및 명시적 내부 조인 예제를 볼 프로젝트에서 모듈입니다.</span><span class="sxs-lookup"><span data-stu-id="99fd1-123">Add the following code to the `Module1` module in your project to see examples of both an implicit and explicit inner join.</span></span>  
  
     [!code-vb[VbLINQHowTos#4](../../../../visual-basic/programming-guide/language-features/linq/codesnippet/VisualBasic/how-to-combine-data-with-linq-by-using-joins_3.vb)]  
  
## <a name="perform-a-left-outer-join-by-using-the-group-join-clause"></a><span data-ttu-id="99fd1-124">Group Join 절을 사용 하 여 왼쪽된 우선 외부 조인 수행</span><span class="sxs-lookup"><span data-stu-id="99fd1-124">Perform a Left Outer Join by Using the Group Join Clause</span></span>  
 <span data-ttu-id="99fd1-125">LEFT OUTER JOIN 조인 및 값 조인의 오른쪽에 있는 컬렉션에서 일치 하는 왼쪽 컬렉션에서 모든 항목을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="99fd1-125">A LEFT OUTER JOIN includes all the items from the left-side collection of the join and only matching values from the right-side collection of the join.</span></span> <span data-ttu-id="99fd1-126">왼쪽 컬렉션의 일치 하는 항목이 없는 조인의 오른쪽에 있는 컬렉션에서 모든 항목은 쿼리 결과에서 제외 됩니다.</span><span class="sxs-lookup"><span data-stu-id="99fd1-126">Any items from the right-side collection of the join that do not have a matching item in the left-side collection are excluded from the query result.</span></span>  
  
 <span data-ttu-id="99fd1-127">`Group Join` 절 수행, 실제로 LEFT OUTER JOIN입니다.</span><span class="sxs-lookup"><span data-stu-id="99fd1-127">The `Group Join` clause performs, in effect, a LEFT OUTER JOIN.</span></span> <span data-ttu-id="99fd1-128">일반적으로 라고 LEFT OUTER JOIN 및 간의 차이 `Group Join` 절은 반환는 `Group Join` 왼쪽 컬렉션의 각 항목에 대 한 조인의 오른쪽에 있는 컬렉션에서 절 그룹 결과.</span><span class="sxs-lookup"><span data-stu-id="99fd1-128">The difference between what is typically known as a LEFT OUTER JOIN and what the `Group Join` clause returns is that the `Group Join` clause groups results from the right-side collection of the join for each item in the left-side collection.</span></span> <span data-ttu-id="99fd1-129">관계형 데이터베이스, LEFT OUTER JOIN 조인에 두 컬렉션에서 일치 하는 항목을 포함 하는 쿼리의 각 항목에는 결과 그룹화 되지 않은 결과 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="99fd1-129">In a relational database, a LEFT OUTER JOIN returns an ungrouped result in which each item in the query result contains matching items from both collections in the join.</span></span> <span data-ttu-id="99fd1-130">이 경우 조인 왼쪽 컬렉션의 항목 오른쪽에 있는 컬렉션에서 일치 하는 각 항목에 대해 반복 됩니다.</span><span class="sxs-lookup"><span data-stu-id="99fd1-130">In this case, the items from the left-side collection of the join are repeated for each matching item from the right-side collection.</span></span> <span data-ttu-id="99fd1-131">이 내용을 다음 절차를 완료 하는 것이 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="99fd1-131">You will see what this looks like when you complete the next procedure.</span></span>  
  
 <span data-ttu-id="99fd1-132">결과 검색할 수는 `Group Join` 각 그룹화 된 쿼리 결과 대 한 항목을 반환 하려면 쿼리를 확장 하 여 그룹화 되지 않은 결과 쿼리 합니다.</span><span class="sxs-lookup"><span data-stu-id="99fd1-132">You can retrieve the results of a `Group Join` query as an ungrouped result by extending your query to return an item for each grouped query result.</span></span> <span data-ttu-id="99fd1-133">이렇게 하려면에서 쿼리를 확인 해야 합니다 `DefaultIfEmpty` 그룹화 된 컬렉션의 메서드.</span><span class="sxs-lookup"><span data-stu-id="99fd1-133">To accomplish this, you have to ensure that you query on the `DefaultIfEmpty` method of the grouped collection.</span></span> <span data-ttu-id="99fd1-134">이렇게 하면 있다면 오른쪽 컬렉션에서 일치 하는 아무 것도 조인의 왼쪽 컬렉션의 항목이 쿼리 결과에 포함 계속 됩니다.</span><span class="sxs-lookup"><span data-stu-id="99fd1-134">This ensures that items from the left-side collection of the join are still included in the query result even if they have no matching results from the right-side collection.</span></span> <span data-ttu-id="99fd1-135">조인의 오른쪽에 있는 컬렉션에서 일치 하는 값이 없을 때 기본 결과 값을 제공 하 여 쿼리 코드를 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="99fd1-135">You can add code to your query to provide a default result value when there is no matching value from the right-side collection of the join.</span></span>  
  
#### <a name="to-perform-a-left-outer-join-by-using-the-group-join-clause"></a><span data-ttu-id="99fd1-136">Group Join 절을 사용 하 여 Left Outer Join을 수행 하려면</span><span class="sxs-lookup"><span data-stu-id="99fd1-136">To perform a Left Outer Join by using the Group Join clause</span></span>  
  
1.  <span data-ttu-id="99fd1-137">다음 코드를 추가 합니다 `Module1` 그룹화 된 왼쪽된 외부 조인 및 그룹화 되지 않은 왼쪽된 외부 조인을 둘 다의 예제를 보려면 프로젝트에서 모듈입니다.</span><span class="sxs-lookup"><span data-stu-id="99fd1-137">Add the following code to the `Module1` module in your project to see examples of both a grouped left outer join and an ungrouped left outer join.</span></span>  
  
     [!code-vb[VbLINQHowTos#3](../../../../visual-basic/programming-guide/language-features/linq/codesnippet/VisualBasic/how-to-combine-data-with-linq-by-using-joins_4.vb)]  
  
## <a name="perform-a-join-by-using-a-composite-key"></a><span data-ttu-id="99fd1-138">복합 키를 사용 하 여 조인 수행</span><span class="sxs-lookup"><span data-stu-id="99fd1-138">Perform a Join by Using a Composite Key</span></span>  
 <span data-ttu-id="99fd1-139">사용할 수는 `And` 키워드를 `Join` 또는 `Group Join` 조인 중인 컬렉션에서 일치 시킬 때 사용 하는 여러 키 필드를 식별 하는 절 값입니다.</span><span class="sxs-lookup"><span data-stu-id="99fd1-139">You can use the `And` keyword in a `Join` or `Group Join` clause to identify multiple key fields to use when matching values from the collections being joined.</span></span> <span data-ttu-id="99fd1-140">`And` 키워드 지정는 모든 조인할 수는 항목에 대 한 키 필드와 일치 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="99fd1-140">The `And` keyword specifies that all specified key fields must match for items to be joined.</span></span>  
  
#### <a name="to-perform-a-join-by-using-a-composite-key"></a><span data-ttu-id="99fd1-141">복합 키를 사용 하 여 조인 수행</span><span class="sxs-lookup"><span data-stu-id="99fd1-141">To perform a Join by using a composite key</span></span>  
  
1.  <span data-ttu-id="99fd1-142">다음 코드를 추가 합니다 `Module1` 의 복합 키를 사용 하는 조인 예제를 보려면 프로젝트에서 모듈입니다.</span><span class="sxs-lookup"><span data-stu-id="99fd1-142">Add the following code to the `Module1` module in your project to see examples of a join that uses a composite key.</span></span>  
  
     [!code-vb[VbLINQHowTos#5](../../../../visual-basic/programming-guide/language-features/linq/codesnippet/VisualBasic/how-to-combine-data-with-linq-by-using-joins_5.vb)]  
  
## <a name="run-the-code"></a><span data-ttu-id="99fd1-143">코드를 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="99fd1-143">Run the Code</span></span>  
  
#### <a name="to-add-code-to-run-the-examples"></a><span data-ttu-id="99fd1-144">예제를 실행 하는 코드를 추가 하려면</span><span class="sxs-lookup"><span data-stu-id="99fd1-144">To add code to run the examples</span></span>  
  
1.  <span data-ttu-id="99fd1-145">대체는 `Sub Main` 에 `Module1` 이 항목의 예제를 실행 하려면 다음 코드를 사용 하 여 프로젝트에서 모듈입니다.</span><span class="sxs-lookup"><span data-stu-id="99fd1-145">Replace the `Sub Main` in the `Module1` module in your project with the following code to run the examples in this topic.</span></span>  
  
     [!code-vb[VbLINQHowTos#6](../../../../visual-basic/programming-guide/language-features/linq/codesnippet/VisualBasic/how-to-combine-data-with-linq-by-using-joins_6.vb)]  
  
2.  <span data-ttu-id="99fd1-146">F5 키를 눌러 예제를 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="99fd1-146">Press F5 to run the examples.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="99fd1-147">참고 항목</span><span class="sxs-lookup"><span data-stu-id="99fd1-147">See Also</span></span>  
 [<span data-ttu-id="99fd1-148">LINQ</span><span class="sxs-lookup"><span data-stu-id="99fd1-148">LINQ</span></span>](../../../../visual-basic/programming-guide/language-features/linq/index.md)  
 [<span data-ttu-id="99fd1-149">Visual Basic의 LINQ 소개</span><span class="sxs-lookup"><span data-stu-id="99fd1-149">Introduction to LINQ in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)  
 [<span data-ttu-id="99fd1-150">Join 절</span><span class="sxs-lookup"><span data-stu-id="99fd1-150">Join Clause</span></span>](../../../../visual-basic/language-reference/queries/join-clause.md)  
 [<span data-ttu-id="99fd1-151">Group Join 절</span><span class="sxs-lookup"><span data-stu-id="99fd1-151">Group Join Clause</span></span>](../../../../visual-basic/language-reference/queries/group-join-clause.md)  
 [<span data-ttu-id="99fd1-152">From 절</span><span class="sxs-lookup"><span data-stu-id="99fd1-152">From Clause</span></span>](../../../../visual-basic/language-reference/queries/from-clause.md)  
 [<span data-ttu-id="99fd1-153">Where 절</span><span class="sxs-lookup"><span data-stu-id="99fd1-153">Where Clause</span></span>](../../../../visual-basic/language-reference/queries/where-clause.md)  
 [<span data-ttu-id="99fd1-154">쿼리</span><span class="sxs-lookup"><span data-stu-id="99fd1-154">Queries</span></span>](../../../../visual-basic/language-reference/queries/index.md)  
 [<span data-ttu-id="99fd1-155">LINQ를 통한 데이터 변환(C#)</span><span class="sxs-lookup"><span data-stu-id="99fd1-155">Data Transformations with LINQ (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/data-transformations-with-linq.md)
