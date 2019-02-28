---
title: Where 절(Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.QueryWhere
helpviewer_keywords:
- Where statement [Visual Basic]
- queries [Visual Basic], Where
- Where clause [Visual Basic]
ms.assetid: 48b5c2c5-3181-429c-8545-894296798c89
ms.openlocfilehash: 3d8f17c54d6a7767cc7a694ddb2508ae9ca4df60
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/28/2019
ms.locfileid: "56971394"
---
# <a name="where-clause-visual-basic"></a><span data-ttu-id="100a0-102">Where 절(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="100a0-102">Where Clause (Visual Basic)</span></span>
<span data-ttu-id="100a0-103">쿼리에 대 한 필터링 조건을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="100a0-103">Specifies the filtering condition for a query.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="100a0-104">구문</span><span class="sxs-lookup"><span data-stu-id="100a0-104">Syntax</span></span>  
  
```  
Where condition  
```  
  
## <a name="parts"></a><span data-ttu-id="100a0-105">요소</span><span class="sxs-lookup"><span data-stu-id="100a0-105">Parts</span></span>  
 `condition`  
 <span data-ttu-id="100a0-106">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="100a0-106">Required.</span></span> <span data-ttu-id="100a0-107">컬렉션의 현재 항목에 대 한 값을 출력 컬렉션에 포함 되는지 여부를 결정 하는 식입니다.</span><span class="sxs-lookup"><span data-stu-id="100a0-107">An expression that determines whether the values for the current item in the collection are included in the output collection.</span></span> <span data-ttu-id="100a0-108">식은 해야 합니다는 `Boolean` 값 또는 해당을 `Boolean` 값입니다.</span><span class="sxs-lookup"><span data-stu-id="100a0-108">The expression must evaluate to a `Boolean` value or the equivalent of a `Boolean` value.</span></span> <span data-ttu-id="100a0-109">조건이 평가 되는 경우 `True`요소가 고 그렇지 않으면 쿼리 결과에 포함 된, 쿼리 결과에서 요소 제외 됩니다.</span><span class="sxs-lookup"><span data-stu-id="100a0-109">If the condition evaluates to `True`, the element is included in the query result; otherwise, the element is excluded from the query result.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="100a0-110">설명</span><span class="sxs-lookup"><span data-stu-id="100a0-110">Remarks</span></span>  
 <span data-ttu-id="100a0-111">`Where` 절 특정 조건을 충족 하는 요소만 선택 하 여 쿼리 데이터를 필터링 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="100a0-111">The `Where` clause enables you to filter query data by selecting only elements that meet certain criteria.</span></span> <span data-ttu-id="100a0-112">값이 해당 요소는 `Where` 절을 평가 하 `True` ; 쿼리 결과에 포함 된 다른 요소는 제외 됩니다.</span><span class="sxs-lookup"><span data-stu-id="100a0-112">Elements whose values cause the `Where` clause to evaluate to `True` are included in the query result; other elements are excluded.</span></span> <span data-ttu-id="100a0-113">에 사용 되는 식을 `Where` 절을 평가 해야 합니다는 `Boolean` 또는 해당 하는 `Boolean`, 등으로 계산 되는 정수 `False` 경우 해당 값은 0입니다.</span><span class="sxs-lookup"><span data-stu-id="100a0-113">The expression that is used in a `Where` clause must evaluate to a `Boolean` or the equivalent of a `Boolean`, such as an Integer that evaluates to `False` when its value is zero.</span></span> <span data-ttu-id="100a0-114">여러 식을 결합할 수 있습니다는 `Where` 와 같은 논리 연산자를 사용 하 여 절 `And`, `Or`, `AndAlso`, `OrElse`를 `Is`, 및 `IsNot`합니다.</span><span class="sxs-lookup"><span data-stu-id="100a0-114">You can combine multiple expressions in a `Where` clause by using logical operators such as `And`, `Or`, `AndAlso`, `OrElse`, `Is`, and `IsNot`.</span></span>  
  
 <span data-ttu-id="100a0-115">기본적으로 쿼리 식은 계산 되지 않습니다 액세스 될 때까지-예를 들어 있을 때 데이터 바인딩된 또는의 통해 반복을 `For` 루프입니다.</span><span class="sxs-lookup"><span data-stu-id="100a0-115">By default, query expressions are not evaluated until they are accessed—for example, when they are data-bound or iterated through in a `For` loop.</span></span> <span data-ttu-id="100a0-116">결과적으로 `Where` 절 쿼리 액세스 될 때까지 평가 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="100a0-116">As a result, the `Where` clause is not evaluated until the query is accessed.</span></span> <span data-ttu-id="100a0-117">외부에서 사용 되는 쿼리에 값이 있는 경우는 `Where` 절에서 적절 한 값을 사용 합니다 `Where` 쿼리가 실행 될 시점에는 절.</span><span class="sxs-lookup"><span data-stu-id="100a0-117">If you have values external to the query that are used in the `Where` clause, ensure that the appropriate value is used in the `Where` clause at the time the query is executed.</span></span> <span data-ttu-id="100a0-118">쿼리 실행에 대 한 자세한 내용은 참조 하세요. [Your 첫 번째 LINQ 쿼리를 작성 하도록](../../../visual-basic/programming-guide/concepts/linq/writing-your-first-linq-query.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="100a0-118">For more information about query execution, see [Writing Your First LINQ Query](../../../visual-basic/programming-guide/concepts/linq/writing-your-first-linq-query.md).</span></span>  
  
 <span data-ttu-id="100a0-119">내에서 함수를 호출할 수는 `Where` 컬렉션의 현재 요소에서 계산 또는 값에 대 한 작업을 수행 하는 절.</span><span class="sxs-lookup"><span data-stu-id="100a0-119">You can call functions within a `Where` clause to perform a calculation or operation on a value from the current element in the collection.</span></span> <span data-ttu-id="100a0-120">함수 호출을 `Where` 절이 정의 된 경우 대신 액세스할 때 즉시 실행 될 쿼리를 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="100a0-120">Calling a function in a `Where` clause can cause the query to be executed immediately when it is defined instead of when it is accessed.</span></span> <span data-ttu-id="100a0-121">쿼리 실행에 대 한 자세한 내용은 참조 하세요. [Your 첫 번째 LINQ 쿼리를 작성 하도록](../../../visual-basic/programming-guide/concepts/linq/writing-your-first-linq-query.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="100a0-121">For more information about query execution, see [Writing Your First LINQ Query](../../../visual-basic/programming-guide/concepts/linq/writing-your-first-linq-query.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="100a0-122">예제</span><span class="sxs-lookup"><span data-stu-id="100a0-122">Example</span></span>  
 <span data-ttu-id="100a0-123">다음 쿼리 식에 사용을 `From` 범위 변수를 선언 하는 절 `cust` 각각에 대해 `Customer` 개체는 `customers` 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="100a0-123">The following query expression uses a `From` clause to declare a range variable `cust` for each `Customer` object in the `customers` collection.</span></span> <span data-ttu-id="100a0-124">`Where` 절 범위 변수를 사용 하 여 지정된 된 지역에서 고객에 게 출력을 제한 합니다.</span><span class="sxs-lookup"><span data-stu-id="100a0-124">The `Where` clause uses the range variable to restrict the output to customers from the specified region.</span></span> <span data-ttu-id="100a0-125">`For Each` 루프는 쿼리 결과에서 각 고객의 회사 이름을 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="100a0-125">The `For Each` loop displays the company name for each customer in the query result.</span></span>  
  
 [!code-vb[VbSimpleQuerySamples#23](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#23)]  
  
## <a name="example"></a><span data-ttu-id="100a0-126">예제</span><span class="sxs-lookup"><span data-stu-id="100a0-126">Example</span></span>  
 <span data-ttu-id="100a0-127">다음 예제에서는 `And` 하 고 `Or` 의 논리 연산자는 `Where` 절.</span><span class="sxs-lookup"><span data-stu-id="100a0-127">The following example uses `And` and `Or` logical operators in the `Where` clause.</span></span>  
  
 [!code-vb[VbSimpleQuerySamples#31](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#31)]  
  
## <a name="see-also"></a><span data-ttu-id="100a0-128">참고자료</span><span class="sxs-lookup"><span data-stu-id="100a0-128">See also</span></span>
- [<span data-ttu-id="100a0-129">Visual Basic의 LINQ 소개</span><span class="sxs-lookup"><span data-stu-id="100a0-129">Introduction to LINQ in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)
- [<span data-ttu-id="100a0-130">쿼리</span><span class="sxs-lookup"><span data-stu-id="100a0-130">Queries</span></span>](../../../visual-basic/language-reference/queries/index.md)
- [<span data-ttu-id="100a0-131">From 절</span><span class="sxs-lookup"><span data-stu-id="100a0-131">From Clause</span></span>](../../../visual-basic/language-reference/queries/from-clause.md)
- [<span data-ttu-id="100a0-132">Select 절</span><span class="sxs-lookup"><span data-stu-id="100a0-132">Select Clause</span></span>](../../../visual-basic/language-reference/queries/select-clause.md)
- [<span data-ttu-id="100a0-133">For Each...Next 문</span><span class="sxs-lookup"><span data-stu-id="100a0-133">For Each...Next Statement</span></span>](../../../visual-basic/language-reference/statements/for-each-next-statement.md)
