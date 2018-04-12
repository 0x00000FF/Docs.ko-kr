---
title: /= 연산자(Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb./=
helpviewer_keywords:
- assignment statements [Visual Basic], compound
- statements [Visual Basic], compound assignment
- /= operator [Visual Basic]
- operator /=
- compound assignment statements [Visual Basic]
ms.assetid: a1e22d0e-8380-4761-9da1-84fb51c34821
caps.latest.revision: 23
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 94448856072a949582e64577287134c4b975bfec
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="-operator-visual-basic"></a><span data-ttu-id="2e845-102">/= 연산자(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="2e845-102">/= Operator (Visual Basic)</span></span>
<span data-ttu-id="2e845-103">변수 또는 속성의 값 식의 값으로 나누고 부동 소수점 결과 변수 또는 속성에 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="2e845-103">Divides the value of a variable or property by the value of an expression and assigns the floating-point result to the variable or property.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2e845-104">구문</span><span class="sxs-lookup"><span data-stu-id="2e845-104">Syntax</span></span>  
  
```  
variableorproperty /= expression  
```  
  
## <a name="parts"></a><span data-ttu-id="2e845-105">요소</span><span class="sxs-lookup"><span data-stu-id="2e845-105">Parts</span></span>  
 `variableorproperty`  
 <span data-ttu-id="2e845-106">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="2e845-106">Required.</span></span> <span data-ttu-id="2e845-107">숫자 변수 또는 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="2e845-107">Any numeric variable or property.</span></span>  
  
 `expression`  
 <span data-ttu-id="2e845-108">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="2e845-108">Required.</span></span> <span data-ttu-id="2e845-109">임의의 숫자 식입니다.</span><span class="sxs-lookup"><span data-stu-id="2e845-109">Any numeric expression.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2e845-110">설명</span><span class="sxs-lookup"><span data-stu-id="2e845-110">Remarks</span></span>  
 <span data-ttu-id="2e845-111">왼쪽에 요소는 `/=` 연산자는 간단한 스칼라 변수, 속성 또는 배열의 요소 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2e845-111">The element on the left side of the `/=` operator can be a simple scalar variable, a property, or an element of an array.</span></span> <span data-ttu-id="2e845-112">변수 또는 속성 수 없습니다 [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="2e845-112">The variable or property cannot be [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md).</span></span>  
  
 <span data-ttu-id="2e845-113">`/=` 연산자 (연산자의 오른쪽)에 식의 값으로 변수 또는 연산자의 왼쪽) (에 속성의 값을 먼저 나눕니다.</span><span class="sxs-lookup"><span data-stu-id="2e845-113">The `/=` operator first divides the value of the variable or property (on the left-hand side of the operator) by the value of the expression (on the right-hand side of the operator).</span></span> <span data-ttu-id="2e845-114">다음 연산자는 변수 또는 속성에 해당 작업의 부동 소수점 결과 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="2e845-114">The operator then assigns the floating-point result of that operation to the variable or property.</span></span>  
  
 <span data-ttu-id="2e845-115">이 문은 할당 한 `Double` 변수 또는 왼쪽에는 속성 값입니다.</span><span class="sxs-lookup"><span data-stu-id="2e845-115">This statement assigns a `Double` value to the variable or property on the left.</span></span> <span data-ttu-id="2e845-116">경우 `Option Strict` 은 `On`, `variableorproperty` 이어야 합니다는 `Double`합니다.</span><span class="sxs-lookup"><span data-stu-id="2e845-116">If `Option Strict` is `On`, `variableorproperty` must be a `Double`.</span></span> <span data-ttu-id="2e845-117">경우 `Option Strict` 은 `Off`, Visual Basic 암시적 변환을 수행 하 고 결과 값을 할당 `variableorproperty`, 실행 시 가능한 오류를 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="2e845-117">If `Option Strict` is `Off`, Visual Basic performs an implicit conversion and assigns the resulting value to `variableorproperty`, with a possible error at run time.</span></span> <span data-ttu-id="2e845-118">자세한 내용은 참조 [확장 변환과 축소 변환](../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md) 및 [Option Strict 문](../../../visual-basic/language-reference/statements/option-strict-statement.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="2e845-118">For more information, see [Widening and Narrowing Conversions](../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md) and [Option Strict Statement](../../../visual-basic/language-reference/statements/option-strict-statement.md).</span></span>  
  
## <a name="overloading"></a><span data-ttu-id="2e845-119">오버로딩</span><span class="sxs-lookup"><span data-stu-id="2e845-119">Overloading</span></span>  
 <span data-ttu-id="2e845-120">[/ 연산자 (Visual Basic)](../../../visual-basic/language-reference/operators/floating-point-division-operator.md) 수 *오버 로드 된*, 클래스 또는 구조체 수 할의 동작에 해당 클래스 또는 구조체의 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="2e845-120">The [/ Operator (Visual Basic)](../../../visual-basic/language-reference/operators/floating-point-division-operator.md) can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="2e845-121">오버 로드는 `/` 연산자의 동작에 영향을 줍니다는 `/=` 연산자입니다.</span><span class="sxs-lookup"><span data-stu-id="2e845-121">Overloading the `/` operator affects the behavior of the `/=` operator.</span></span> <span data-ttu-id="2e845-122">코드에서 `/=` 클래스 또는 구조체에 오버 로드에서 `/`, 다시 정의 된 동작을 이해 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2e845-122">If your code uses `/=` on a class or structure that overloads `/`, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="2e845-123">자세한 내용은 참조 [연산자 프로시저](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="2e845-123">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="2e845-124">예제</span><span class="sxs-lookup"><span data-stu-id="2e845-124">Example</span></span>  
 <span data-ttu-id="2e845-125">다음 예제에서는 `/=` 연산자 하나를 `Integer` 변수를 두 번째 및 quotient 첫 번째 변수에 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="2e845-125">The following example uses the `/=` operator to divide one `Integer` variable by a second and assign the quotient to the first variable.</span></span>  
  
 [!code-vb[VbVbalrOperators#17](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/floating-point-division-assignment-operator_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="2e845-126">참고 항목</span><span class="sxs-lookup"><span data-stu-id="2e845-126">See Also</span></span>  
 [<span data-ttu-id="2e845-127">/ 연산자 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="2e845-127">/ Operator (Visual Basic)</span></span>](../../../visual-basic/language-reference/operators/floating-point-division-operator.md)  
 [<span data-ttu-id="2e845-128">\\= 연산자</span><span class="sxs-lookup"><span data-stu-id="2e845-128">\\= Operator</span></span>](../../../visual-basic/language-reference/operators/integer-division-assignment-operator.md)  
 [<span data-ttu-id="2e845-129">할당 연산자</span><span class="sxs-lookup"><span data-stu-id="2e845-129">Assignment Operators</span></span>](../../../visual-basic/language-reference/operators/assignment-operators.md)  
 [<span data-ttu-id="2e845-130">산술 연산자</span><span class="sxs-lookup"><span data-stu-id="2e845-130">Arithmetic Operators</span></span>](../../../visual-basic/language-reference/operators/arithmetic-operators.md)  
 [<span data-ttu-id="2e845-131">Visual Basic에서의 연산자 우선 순위</span><span class="sxs-lookup"><span data-stu-id="2e845-131">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)  
 [<span data-ttu-id="2e845-132">기능별 연산자 목록</span><span class="sxs-lookup"><span data-stu-id="2e845-132">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)  
 [<span data-ttu-id="2e845-133">문</span><span class="sxs-lookup"><span data-stu-id="2e845-133">Statements</span></span>](../../../visual-basic/programming-guide/language-features/statements.md)
