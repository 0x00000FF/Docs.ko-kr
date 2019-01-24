---
title: Select 절(Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.QuerySelect
helpviewer_keywords:
- Select statement [Visual Basic]
- Select clause [Visual Basic]
- queries [Visual Basic], Select
ms.assetid: 27a3f61c-5960-4692-9b91-4d0c4b6178fe
ms.openlocfilehash: 0890068d192a137689d06eb081e1a0fc128aabcd
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54519010"
---
# <a name="select-clause-visual-basic"></a><span data-ttu-id="d6db6-102">Select 절(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d6db6-102">Select Clause (Visual Basic)</span></span>
<span data-ttu-id="d6db6-103">쿼리 결과 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="d6db6-103">Defines the result of a query.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d6db6-104">구문</span><span class="sxs-lookup"><span data-stu-id="d6db6-104">Syntax</span></span>  
  
```  
Select [ var1 = ] fieldName1 [, [ var2 = ] fieldName2 [...] ]  
```  
  
## <a name="parts"></a><span data-ttu-id="d6db6-105">요소</span><span class="sxs-lookup"><span data-stu-id="d6db6-105">Parts</span></span>  
 `var1`  
 <span data-ttu-id="d6db6-106">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="d6db6-106">Optional.</span></span> <span data-ttu-id="d6db6-107">열 식의 결과 참조 하는 별칭입니다.</span><span class="sxs-lookup"><span data-stu-id="d6db6-107">An alias that can be used to reference the results of the column expression.</span></span>  
  
 `fieldName1`  
 <span data-ttu-id="d6db6-108">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="d6db6-108">Required.</span></span> <span data-ttu-id="d6db6-109">쿼리 결과에 반환할 필드의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="d6db6-109">The name of the field to return in the query result.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d6db6-110">설명</span><span class="sxs-lookup"><span data-stu-id="d6db6-110">Remarks</span></span>  
 <span data-ttu-id="d6db6-111">사용할 수는 `Select` 쿼리에서 반환할 결과 정의 하는 절.</span><span class="sxs-lookup"><span data-stu-id="d6db6-111">You can use the `Select` clause to define the results to return from a query.</span></span> <span data-ttu-id="d6db6-112">이렇게 하면 쿼리를 통해 만들어지는 새 익명 형식의 멤버를 정의 하거나 또는 쿼리에서 반환 되는 명명 된 형식의 멤버를 대상으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6db6-112">This enables you to either define the members of a new anonymous type that is created by a query, or to target the members of a named type that is returned by a query.</span></span> <span data-ttu-id="d6db6-113">`Select` 절을 쿼리에 대 한 필요 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d6db6-113">The `Select` clause is not required for a query.</span></span> <span data-ttu-id="d6db6-114">없으면 `Select` 절을 지정 하면 쿼리는 현재 범위에 대 한 식별 된 범위 변수의 모든 멤버를 기준으로 형식을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6db6-114">If no `Select` clause is specified, the query will return a type based on all members of the range variables identified for the current scope.</span></span> <span data-ttu-id="d6db6-115">자세한 내용은 [무명 형식](../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d6db6-115">For more information, see [Anonymous Types](../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md).</span></span> <span data-ttu-id="d6db6-116">쿼리는 명명 된 형식을 만들면 결과 유형이 반환 됩니다 <xref:System.Collections.Generic.IEnumerable%601> 여기서 `T` 만든된 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="d6db6-116">When a query creates a named type, it will return a result of type <xref:System.Collections.Generic.IEnumerable%601> where `T` is the created type.</span></span>  
  
 <span data-ttu-id="d6db6-117">`Select` 절 현재 범위에 있는 모든 변수를 참조할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d6db6-117">The `Select` clause can reference any variables in the current scope.</span></span> <span data-ttu-id="d6db6-118">여기에 나오는 범위 변수를 `From` 절 (또는 `From` 절).</span><span class="sxs-lookup"><span data-stu-id="d6db6-118">This includes range variables identified in the `From` clause (or `From` clauses).</span></span> <span data-ttu-id="d6db6-119">또한 하 여 별칭을 사용 하 여 만들어진 모든 새 변수를 `Aggregate`, `Let`를 `Group By`, 또는 `Group Join` 절 이나 변수를 이전 `Select` 쿼리 식 절.</span><span class="sxs-lookup"><span data-stu-id="d6db6-119">It also includes any new variables created with an alias by the `Aggregate`, `Let`, `Group By`, or `Group Join` clauses, or variables from a previous `Select` clause in the query expression.</span></span> <span data-ttu-id="d6db6-120">`Select` 절은 정적 값을 포함할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d6db6-120">The `Select` clause can also include static values.</span></span> <span data-ttu-id="d6db6-121">다음 코드 예제는 쿼리 식에 표시 하는 예를 들어 합니다 `Select` 절은 네 가지 멤버를 사용 하 여 새 익명 형식으로 쿼리 결과 정의: `ProductName`를 `Price`, `Discount`, 및 `DiscountedPrice`합니다.</span><span class="sxs-lookup"><span data-stu-id="d6db6-121">For example, the following code example shows a query expression in which the `Select` clause defines the query result as a new anonymous type with four members: `ProductName`, `Price`, `Discount`, and `DiscountedPrice`.</span></span> <span data-ttu-id="d6db6-122">합니다 `ProductName` 하 고 `Price` 에 정의 된 제품 범위 변수에서 멤버 값을 가져옵니다는 `From` 절.</span><span class="sxs-lookup"><span data-stu-id="d6db6-122">The `ProductName` and `Price` member values are taken from the product range variable that is defined in the `From` clause.</span></span> <span data-ttu-id="d6db6-123">합니다 `DiscountedPrice` 의 멤버 값이 계산 되는 `Let` 절.</span><span class="sxs-lookup"><span data-stu-id="d6db6-123">The `DiscountedPrice` member value is calculated in the `Let` clause.</span></span> <span data-ttu-id="d6db6-124">`Discount` 멤버는 정적 값입니다.</span><span class="sxs-lookup"><span data-stu-id="d6db6-124">The `Discount` member is a static value.</span></span>  
  
 [!code-vb[VbSimpleQuerySamples#27](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/select-clause_1.vb)]  
  
 <span data-ttu-id="d6db6-125">`Select` 절 후속 쿼리 절에 대 한 범위 변수는 새 집합을 소개 하 고 이전 범위 변수는 더 이상 범위입니다.</span><span class="sxs-lookup"><span data-stu-id="d6db6-125">The `Select` clause introduces a new set of range variables for subsequent query clauses, and previous range variables are no longer in scope.</span></span> <span data-ttu-id="d6db6-126">마지막 `Select` 쿼리 식의 절에 쿼리의 반환 값을 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6db6-126">The last `Select` clause in a query expression determines the return value of the query.</span></span> <span data-ttu-id="d6db6-127">예를 들어 다음 쿼리는 총 500을 초과 하는 모든 고객 주문에 대 한 이름 및 주문 ID는 회사를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6db6-127">For example, the following query returns the company name and order ID for every customer order for which the total exceeds 500.</span></span> <span data-ttu-id="d6db6-128">첫 번째 `Select` 절에 대 한 범위 변수를 식별 합니다 `Where` 절과 두 번째 `Select` 절.</span><span class="sxs-lookup"><span data-stu-id="d6db6-128">The first `Select` clause identifies the range variables for the `Where` clause and the second `Select` clause.</span></span> <span data-ttu-id="d6db6-129">두 번째 `Select` 절 새 익명 형식으로 쿼리에서 반환 된 값을 식별 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6db6-129">The second `Select` clause identifies the values returned by the query as a new anonymous type.</span></span>  
  
 [!code-vb[VbSimpleQuerySamples#28](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/select-clause_2.vb)]  
  
 <span data-ttu-id="d6db6-130">경우는 `Select` 반환할 단일 항목을 식별 하는 절, 쿼리 식 형식의 단일 항목의 컬렉션을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6db6-130">If the `Select` clause identifies a single item to return, the query expression returns a collection of the type of that single item.</span></span> <span data-ttu-id="d6db6-131">경우는 `Select` 반환할 여러 항목을 식별 하는 절, 쿼리 식 선택한 항목을 기반으로 한 새 익명 형식의 컬렉션을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6db6-131">If the `Select` clause identifies multiple items to return, the query expression returns a collection of a new anonymous type, based on the selected items.</span></span> <span data-ttu-id="d6db6-132">다음 두 쿼리를 기반으로 하는 두 가지 종류의 컬렉션을 반환 하는 예를 들어를 `Select` 절.</span><span class="sxs-lookup"><span data-stu-id="d6db6-132">For example, the following two queries return collections of two different types based on the `Select` clause.</span></span> <span data-ttu-id="d6db6-133">첫 번째 쿼리 문자열로 회사 이름의 컬렉션을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6db6-133">The first query returns a collection of company names as strings.</span></span> <span data-ttu-id="d6db6-134">컬렉션을 반환 하는 두 번째 쿼리 `Customer` 회사 이름 및 주소 정보로 채워진 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="d6db6-134">The second query returns a collection of `Customer` objects populated with the company names and address information.</span></span>  
  
 [!code-vb[VbSimpleQuerySamples#29](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/select-clause_3.vb)]  
  
## <a name="example"></a><span data-ttu-id="d6db6-135">예제</span><span class="sxs-lookup"><span data-stu-id="d6db6-135">Example</span></span>  
 <span data-ttu-id="d6db6-136">다음 쿼리 식에 사용 된 `From` 범위 변수를 선언 하는 절 `cust` 에 대 한를 `customers` 컬렉션.</span><span class="sxs-lookup"><span data-stu-id="d6db6-136">The following query expression uses a `From` clause to declare a range variable `cust` for the `customers` collection.</span></span> <span data-ttu-id="d6db6-137">합니다 `Select` 절 고객 이름 및 ID 값을 선택 하 고 채웁니다 합니다 `CompanyName` 및 `CustomerID` 새 범위 변수는 열입니다.</span><span class="sxs-lookup"><span data-stu-id="d6db6-137">The `Select` clause selects the customer name and ID value and populates the `CompanyName` and `CustomerID` columns of the new range variable.</span></span> <span data-ttu-id="d6db6-138">`For Each` 문을 반환 된 각 개체를 반복 하 고 표시 합니다 `CompanyName` 및 `CustomerID` 각 레코드에 대 한 열입니다.</span><span class="sxs-lookup"><span data-stu-id="d6db6-138">The `For Each` statement loops over each returned object and displays the `CompanyName` and `CustomerID` columns for each record.</span></span>  
  
 [!code-vb[VbSimpleQuerySamples#30](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/select-clause_4.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="d6db6-139">참고자료</span><span class="sxs-lookup"><span data-stu-id="d6db6-139">See also</span></span>
- [<span data-ttu-id="d6db6-140">Visual Basic의 LINQ 소개</span><span class="sxs-lookup"><span data-stu-id="d6db6-140">Introduction to LINQ in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)
- [<span data-ttu-id="d6db6-141">쿼리</span><span class="sxs-lookup"><span data-stu-id="d6db6-141">Queries</span></span>](../../../visual-basic/language-reference/queries/index.md)
- [<span data-ttu-id="d6db6-142">From 절</span><span class="sxs-lookup"><span data-stu-id="d6db6-142">From Clause</span></span>](../../../visual-basic/language-reference/queries/from-clause.md)
- [<span data-ttu-id="d6db6-143">Where 절</span><span class="sxs-lookup"><span data-stu-id="d6db6-143">Where Clause</span></span>](../../../visual-basic/language-reference/queries/where-clause.md)
- [<span data-ttu-id="d6db6-144">Order By 절</span><span class="sxs-lookup"><span data-stu-id="d6db6-144">Order By Clause</span></span>](../../../visual-basic/language-reference/queries/order-by-clause.md)
- [<span data-ttu-id="d6db6-145">익명 형식</span><span class="sxs-lookup"><span data-stu-id="d6db6-145">Anonymous Types</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md)
