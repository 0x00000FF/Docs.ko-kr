---
title: Order By 절(Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.QueryOrderBy
- vb.QueryAscending
- vb.QueryDescending
helpviewer_keywords:
- queries [Visual Basic], Order By
- Order By clause [Visual Basic]
- Order By statement [Visual Basic]
ms.assetid: fa911282-6b81-44c7-acfa-46b5bb93df75
ms.openlocfilehash: d4abb5f0b75ae4069c1dbe695a5c810b1f7aa6e1
ms.sourcegitcommit: 5bbfe34a9a14e4ccb22367e57b57585c208cf757
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46004284"
---
# <a name="order-by-clause-visual-basic"></a><span data-ttu-id="bd58b-102">Order By 절(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="bd58b-102">Order By Clause (Visual Basic)</span></span>
<span data-ttu-id="bd58b-103">쿼리 결과 대 한 정렬 순서를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="bd58b-103">Specifies the sort order for a query result.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bd58b-104">구문</span><span class="sxs-lookup"><span data-stu-id="bd58b-104">Syntax</span></span>  
  
```  
Order By orderExp1 [ Ascending | Descending ] [, orderExp2 [...] ]  
```  
  
## <a name="parts"></a><span data-ttu-id="bd58b-105">요소</span><span class="sxs-lookup"><span data-stu-id="bd58b-105">Parts</span></span>  
 `orderExp1`  
 <span data-ttu-id="bd58b-106">필수.</span><span class="sxs-lookup"><span data-stu-id="bd58b-106">Required.</span></span> <span data-ttu-id="bd58b-107">하나 이상의 필드는 현재 쿼리 결과에서 반환 된 값을 정렬 하는 방법을 식별 하는입니다.</span><span class="sxs-lookup"><span data-stu-id="bd58b-107">One or more fields from the current query result that identify how to order the returned values.</span></span> <span data-ttu-id="bd58b-108">필드 이름은 쉼표 (,)로 구분 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bd58b-108">The field names must be separated by commas (,).</span></span> <span data-ttu-id="bd58b-109">오름차순 또는 내림차순으로 사용 하 여 정렬 된 것으로 각 필드를 식별할 수 있습니다 합니다 `Ascending` 또는 `Descending` 키워드입니다.</span><span class="sxs-lookup"><span data-stu-id="bd58b-109">You can identify each field as sorted in ascending or descending order by using the `Ascending` or `Descending` keywords.</span></span> <span data-ttu-id="bd58b-110">없으면 `Ascending` 또는 `Descending` 키워드를 지정한 경우 기본 정렬 순서는 오름차순입니다.</span><span class="sxs-lookup"><span data-stu-id="bd58b-110">If no `Ascending` or `Descending` keyword is specified, the default sort order is ascending.</span></span> <span data-ttu-id="bd58b-111">정렬 순서 필드에는 우선 순위가 왼쪽에서 오른쪽으로 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="bd58b-111">The sort order fields are given precedence from left to right.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="bd58b-112">설명</span><span class="sxs-lookup"><span data-stu-id="bd58b-112">Remarks</span></span>  
 <span data-ttu-id="bd58b-113">사용할 수는 `Order By` 절을 쿼리의 결과 정렬 합니다.</span><span class="sxs-lookup"><span data-stu-id="bd58b-113">You can use the `Order By` clause to sort the results of a query.</span></span> <span data-ttu-id="bd58b-114">`Order By` 절 에서만 현재 범위에 대 한 범위 변수를 기반으로 결과 정렬할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bd58b-114">The `Order By` clause can only sort a result based on the range variable for the current scope.</span></span> <span data-ttu-id="bd58b-115">예를 들어를 `Select` 절에서는 해당 범위에 대 한 새 반복 변수를 사용 하 여 쿼리 식에 새 범위를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="bd58b-115">For example, the `Select` clause introduces a new scope in a query expression with new iteration variables for that scope.</span></span> <span data-ttu-id="bd58b-116">범위 변수 앞에 정의 `Select` 쿼리의 절 뒤에 사용할 수 없는 `Select` 절.</span><span class="sxs-lookup"><span data-stu-id="bd58b-116">Range variables defined before a `Select` clause in a query are not available after the `Select` clause.</span></span> <span data-ttu-id="bd58b-117">따라서에서 사용할 수 없는 필드를 기준으로 결과 정렬 하려는 경우는 `Select` 두어야 절을 `Order By` 하기 전에 절은 `Select` 절.</span><span class="sxs-lookup"><span data-stu-id="bd58b-117">Therefore, if you want to order your results by a field that is not available in the `Select` clause, you must put the `Order By` clause before the `Select` clause.</span></span> <span data-ttu-id="bd58b-118">하나의 쿼리 결과의 일부로 반환 되지 않습니다 필드로 정렬 하려는 경우이 작업을 수행 해야 하는 경우의 예입니다.</span><span class="sxs-lookup"><span data-stu-id="bd58b-118">One example of when you would have to do this is when you want to sort your query by fields that are not returned as part of the result.</span></span>  
  
 <span data-ttu-id="bd58b-119">오름차순 또는 내림차순 키를 누른 채 필드의 구현에 의해 결정 됩니다는 <xref:System.IComparable> 필드의 데이터 형식에 대 한 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="bd58b-119">Ascending and descending order for a field is determined by the implementation of the <xref:System.IComparable> interface for the data type of the field.</span></span> <span data-ttu-id="bd58b-120">데이터 형식을 구현 하지 않는 경우는 <xref:System.IComparable> 인터페이스, 정렬 순서는 무시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="bd58b-120">If the data type does not implement the <xref:System.IComparable> interface, the sort order is ignored.</span></span>  
  
## <a name="example"></a><span data-ttu-id="bd58b-121">예제</span><span class="sxs-lookup"><span data-stu-id="bd58b-121">Example</span></span>  
 <span data-ttu-id="bd58b-122">다음 쿼리 식에 사용 된 `From` 범위 변수를 선언 하는 절 `book` 에 대 한를 `books` 컬렉션.</span><span class="sxs-lookup"><span data-stu-id="bd58b-122">The following query expression uses a `From` clause to declare a range variable `book` for the `books` collection.</span></span> <span data-ttu-id="bd58b-123">`Order By` 절 오름차순 (기본값) 가격으로 쿼리 결과 정렬 합니다.</span><span class="sxs-lookup"><span data-stu-id="bd58b-123">The `Order By` clause sorts the query result by price in ascending order (the default).</span></span> <span data-ttu-id="bd58b-124">동일한 가격 책 제목 오름차순으로 정렬 됩니다.</span><span class="sxs-lookup"><span data-stu-id="bd58b-124">Books with the same price are sorted by title in ascending order.</span></span> <span data-ttu-id="bd58b-125">합니다 `Select` 절을 선택 합니다 `Title` 및 `Price` 쿼리에서 반환 된 값으로 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="bd58b-125">The `Select` clause selects the `Title` and `Price` properties as the values returned by the query.</span></span>  
  
 [!code-vb[VbSimpleQuerySamples#24](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/order-by-clause_1.vb)]  
  
## <a name="example"></a><span data-ttu-id="bd58b-126">예제</span><span class="sxs-lookup"><span data-stu-id="bd58b-126">Example</span></span>  
 <span data-ttu-id="bd58b-127">다음 쿼리 식에 사용 된 `Order By` 가격을 내림차순으로 쿼리 결과 정렬 하는 절.</span><span class="sxs-lookup"><span data-stu-id="bd58b-127">The following query expression uses the `Order By` clause to sort the query result by price in descending order.</span></span> <span data-ttu-id="bd58b-128">동일한 가격 책 제목 오름차순으로 정렬 됩니다.</span><span class="sxs-lookup"><span data-stu-id="bd58b-128">Books with the same price are sorted by title in ascending order.</span></span>  
  
 [!code-vb[VbSimpleQuerySamples#25](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/order-by-clause_2.vb)]  
  
## <a name="example"></a><span data-ttu-id="bd58b-129">예제</span><span class="sxs-lookup"><span data-stu-id="bd58b-129">Example</span></span>  
 <span data-ttu-id="bd58b-130">다음 쿼리 식에 사용 된 `Select` 책 제목을 선택, 가격, 날짜, 게시 및 제작 하는 절.</span><span class="sxs-lookup"><span data-stu-id="bd58b-130">The following query expression uses a `Select` clause to select the book title, price, publish date, and author.</span></span> <span data-ttu-id="bd58b-131">다음 채웁니다 합니다 `Title`, `Price`, `PublishDate`, 및 `Author` 새 범위에 대 한 범위 변수 필드입니다.</span><span class="sxs-lookup"><span data-stu-id="bd58b-131">It then populates the `Title`, `Price`, `PublishDate`, and `Author` fields of the range variable for the new scope.</span></span> <span data-ttu-id="bd58b-132">`Order By` 절 작성자 이름, 책 제목 및 가격에서 새 범위 변수를 정렬 합니다.</span><span class="sxs-lookup"><span data-stu-id="bd58b-132">The `Order By` clause orders the new range variable by author name, book title, and then price.</span></span> <span data-ttu-id="bd58b-133">각 열 (오름차순) 기본 순서로 정렬 됩니다.</span><span class="sxs-lookup"><span data-stu-id="bd58b-133">Each column is sorted in the default order (ascending).</span></span>  
  
 [!code-vb[VbSimpleQuerySamples#26](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/order-by-clause_3.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="bd58b-134">참고 항목</span><span class="sxs-lookup"><span data-stu-id="bd58b-134">See Also</span></span>  
 [<span data-ttu-id="bd58b-135">Visual Basic의 LINQ 소개</span><span class="sxs-lookup"><span data-stu-id="bd58b-135">Introduction to LINQ in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)  
 [<span data-ttu-id="bd58b-136">쿼리</span><span class="sxs-lookup"><span data-stu-id="bd58b-136">Queries</span></span>](../../../visual-basic/language-reference/queries/index.md)  
 [<span data-ttu-id="bd58b-137">Select 절</span><span class="sxs-lookup"><span data-stu-id="bd58b-137">Select Clause</span></span>](../../../visual-basic/language-reference/queries/select-clause.md)  
 [<span data-ttu-id="bd58b-138">From 절</span><span class="sxs-lookup"><span data-stu-id="bd58b-138">From Clause</span></span>](../../../visual-basic/language-reference/queries/from-clause.md)
