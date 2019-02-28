---
title: TryCast 연산자(Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.trycast
- trycast
helpviewer_keywords:
- TryCast keyword [Visual Basic]
ms.assetid: d1ef5d47-fef4-491e-b014-1d910628f65c
ms.openlocfilehash: dd50a23f09fa5dd49b86eefe163cea20430e2360
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/28/2019
ms.locfileid: "56981285"
---
# <a name="trycast-operator-visual-basic"></a><span data-ttu-id="c5e64-102">TryCast 연산자(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c5e64-102">TryCast Operator (Visual Basic)</span></span>
<span data-ttu-id="c5e64-103">예외를 throw 하지 않는 형식 변환 작업을 소개 합니다.</span><span class="sxs-lookup"><span data-stu-id="c5e64-103">Introduces a type conversion operation that does not throw an exception.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c5e64-104">설명</span><span class="sxs-lookup"><span data-stu-id="c5e64-104">Remarks</span></span>  
 <span data-ttu-id="c5e64-105">변환에 실패 하면 `CType` 하 고 `DirectCast` 둘 다 throw는 <xref:System.InvalidCastException> 오류입니다.</span><span class="sxs-lookup"><span data-stu-id="c5e64-105">If an attempted conversion fails, `CType` and `DirectCast` both throw an <xref:System.InvalidCastException> error.</span></span> <span data-ttu-id="c5e64-106">이 응용 프로그램의 성능을 저하 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c5e64-106">This can adversely affect the performance of your application.</span></span> <span data-ttu-id="c5e64-107">`TryCast` 반환 [아무](../../../visual-basic/language-reference/nothing.md)가능한 예외를 처리 하는 대신 테스트 하기만 하면에 대 한 결과가 반환된 되도록 `Nothing`합니다.</span><span class="sxs-lookup"><span data-stu-id="c5e64-107">`TryCast` returns [Nothing](../../../visual-basic/language-reference/nothing.md), so that instead of having to handle a possible exception, you need only test the returned result against `Nothing`.</span></span>  
  
 <span data-ttu-id="c5e64-108">사용할 합니다 `TryCast` 키워드를 동일한 방식 합니다 [CType Function](../../../visual-basic/language-reference/functions/ctype-function.md) 및 [DirectCast 연산자](../../../visual-basic/language-reference/operators/directcast-operator.md) 키워드.</span><span class="sxs-lookup"><span data-stu-id="c5e64-108">You use the `TryCast` keyword the same way you use the [CType Function](../../../visual-basic/language-reference/functions/ctype-function.md) and the [DirectCast Operator](../../../visual-basic/language-reference/operators/directcast-operator.md) keyword.</span></span> <span data-ttu-id="c5e64-109">첫 번째 인수와 두 번째 인수로 변환 하는 형식으로 식을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="c5e64-109">You supply an expression as the first argument and a type to convert it to as the second argument.</span></span> <span data-ttu-id="c5e64-110">`TryCast` 클래스 및 인터페이스와 같은 참조 형식에만 작동합니다.</span><span class="sxs-lookup"><span data-stu-id="c5e64-110">`TryCast` operates only on reference types, such as classes and interfaces.</span></span> <span data-ttu-id="c5e64-111">두 형식 간의 상속 또는 구현 관계를 해야합니다.</span><span class="sxs-lookup"><span data-stu-id="c5e64-111">It requires an inheritance or implementation relationship between the two types.</span></span> <span data-ttu-id="c5e64-112">즉, 한 형식에서 상속 하거나 다른 구현 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c5e64-112">This means that one type must inherit from or implement the other.</span></span>  
  
## <a name="errors-and-failures"></a><span data-ttu-id="c5e64-113">오류 및 실패</span><span class="sxs-lookup"><span data-stu-id="c5e64-113">Errors and Failures</span></span>  
 <span data-ttu-id="c5e64-114">`TryCast` 상속 또는 구현 관계 없는 있는지 검색 하는 경우 컴파일러 오류를 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="c5e64-114">`TryCast` generates a compiler error if it detects that no inheritance or implementation relationship exists.</span></span> <span data-ttu-id="c5e64-115">하지만 컴파일러 오류가 없다고 성공적인 변환을 보장 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c5e64-115">But the lack of a compiler error does not guarantee a successful conversion.</span></span> <span data-ttu-id="c5e64-116">원하는 변환에 축소 하는 경우에 런타임에 실패할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c5e64-116">If the desired conversion is narrowing, it could fail at run time.</span></span> <span data-ttu-id="c5e64-117">이 경우 `TryCast` 반환 [Nothing](../../../visual-basic/language-reference/nothing.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="c5e64-117">If this happens, `TryCast` returns [Nothing](../../../visual-basic/language-reference/nothing.md).</span></span>  
  
## <a name="conversion-keywords"></a><span data-ttu-id="c5e64-118">변환 키워드</span><span class="sxs-lookup"><span data-stu-id="c5e64-118">Conversion Keywords</span></span>  
 <span data-ttu-id="c5e64-119">형식 변환 키워드의 비교는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="c5e64-119">A comparison of the type conversion keywords is as follows.</span></span>  
  
|<span data-ttu-id="c5e64-120">키워드</span><span class="sxs-lookup"><span data-stu-id="c5e64-120">Keyword</span></span>|<span data-ttu-id="c5e64-121">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="c5e64-121">Data types</span></span>|<span data-ttu-id="c5e64-122">인수가 관계</span><span class="sxs-lookup"><span data-stu-id="c5e64-122">Argument relationship</span></span>|<span data-ttu-id="c5e64-123">런타임 오류</span><span class="sxs-lookup"><span data-stu-id="c5e64-123">Run-time failure</span></span>|  
|---|---|---|---|  
|[<span data-ttu-id="c5e64-124">CType 함수</span><span class="sxs-lookup"><span data-stu-id="c5e64-124">CType Function</span></span>](../../../visual-basic/language-reference/functions/ctype-function.md)|<span data-ttu-id="c5e64-125">모든 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="c5e64-125">Any data types</span></span>|<span data-ttu-id="c5e64-126">두 데이터 형식 간에 확대 또는 축소 변환을 정의 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c5e64-126">Widening or narrowing conversion must be defined between the two data types</span></span>|<span data-ttu-id="c5e64-127">Throw <xref:System.InvalidCastException></span><span class="sxs-lookup"><span data-stu-id="c5e64-127">Throws <xref:System.InvalidCastException></span></span>|  
|[<span data-ttu-id="c5e64-128">DirectCast 연산자</span><span class="sxs-lookup"><span data-stu-id="c5e64-128">DirectCast Operator</span></span>](../../../visual-basic/language-reference/operators/directcast-operator.md)|<span data-ttu-id="c5e64-129">모든 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="c5e64-129">Any data types</span></span>|<span data-ttu-id="c5e64-130">형식에서 상속 하거나 다른 형식을 구현 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c5e64-130">One type must inherit from or implement the other type</span></span>|<span data-ttu-id="c5e64-131">Throw <xref:System.InvalidCastException></span><span class="sxs-lookup"><span data-stu-id="c5e64-131">Throws <xref:System.InvalidCastException></span></span>|  
|`TryCast`|<span data-ttu-id="c5e64-132">참조 형식에만</span><span class="sxs-lookup"><span data-stu-id="c5e64-132">Reference types only</span></span>|<span data-ttu-id="c5e64-133">형식에서 상속 하거나 다른 형식을 구현 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c5e64-133">One type must inherit from or implement the other type</span></span>|<span data-ttu-id="c5e64-134">반환 [Nothing](../../../visual-basic/language-reference/nothing.md)</span><span class="sxs-lookup"><span data-stu-id="c5e64-134">Returns [Nothing](../../../visual-basic/language-reference/nothing.md)</span></span>|  
  
## <a name="example"></a><span data-ttu-id="c5e64-135">예제</span><span class="sxs-lookup"><span data-stu-id="c5e64-135">Example</span></span>  
 <span data-ttu-id="c5e64-136">다음 예제에서는 `TryCast`을 사용하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="c5e64-136">The following example shows how to use `TryCast`.</span></span>  
  
 [!code-vb[VbVbalrKeywords#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrKeywords/VB/Class1.vb#6)]  
  
## <a name="see-also"></a><span data-ttu-id="c5e64-137">참고자료</span><span class="sxs-lookup"><span data-stu-id="c5e64-137">See also</span></span>
- [<span data-ttu-id="c5e64-138">확대 변환과 축소 변환</span><span class="sxs-lookup"><span data-stu-id="c5e64-138">Widening and Narrowing Conversions</span></span>](../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)
- [<span data-ttu-id="c5e64-139">암시적 변환과 명시적 변환</span><span class="sxs-lookup"><span data-stu-id="c5e64-139">Implicit and Explicit Conversions</span></span>](../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)
