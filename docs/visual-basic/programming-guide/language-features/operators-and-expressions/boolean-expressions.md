---
title: 부울 식(Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- short-circuiting
- Boolean expressions
- logical operators [Visual Basic], Boolean expressions
- expressions [Visual Basic], Boolean
- expression evaluation [Visual Basic], Boolean expressions
- operators [Visual Basic], short-circuiting
- Visual Basic code, operators
- short-circuit evaluation
- logical operators [Visual Basic], short-circuiting
- operators [Visual Basic], Boolean
- Visual Basic code, expressions
ms.assetid: d3d90406-55c8-4404-8143-50fd7f0d0d1a
ms.openlocfilehash: a86df2734d315e5fed0784b0394bb305b15562a9
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54562754"
---
# <a name="boolean-expressions-visual-basic"></a><span data-ttu-id="f1d63-102">부울 식(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f1d63-102">Boolean Expressions (Visual Basic)</span></span>
<span data-ttu-id="f1d63-103">A *부울 식* 값으로 계산 되는 식의 [Boolean 데이터 형식](../../../../visual-basic/language-reference/data-types/boolean-data-type.md): `True` 또는 `False`합니다.</span><span class="sxs-lookup"><span data-stu-id="f1d63-103">A *Boolean expression* is an expression that evaluates to a value of the [Boolean Data Type](../../../../visual-basic/language-reference/data-types/boolean-data-type.md): `True` or `False`.</span></span> <span data-ttu-id="f1d63-104">`Boolean` 식에는 여러 가지 형식을 취할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f1d63-104">`Boolean` expressions can take several forms.</span></span> <span data-ttu-id="f1d63-105">가장 간단한 방법은 값에 대 한 직접 비교는 `Boolean` 변수를 `Boolean` 리터럴, 다음 예제에서와 같이 합니다.</span><span class="sxs-lookup"><span data-stu-id="f1d63-105">The simplest is the direct comparison of the value of a `Boolean` variable to a `Boolean` literal, as shown in the following example.</span></span>  
  
 [!code-vb[VbVbalrOperators#87](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/boolean-expressions_1.vb)]  
  
## <a name="two-meanings-of-the--operator"></a><span data-ttu-id="f1d63-106">두 가지 의미는 = 연산자</span><span class="sxs-lookup"><span data-stu-id="f1d63-106">Two Meanings of the = Operator</span></span>  
 <span data-ttu-id="f1d63-107">대입문은 `newCustomer = True` 앞의 예제에서 식과 동일 하지만 다른 함수를 수행 하 고 다르게 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f1d63-107">Notice that the assignment statement `newCustomer = True` looks the same as the expression in the preceding example, but it performs a different function and is used differently.</span></span> <span data-ttu-id="f1d63-108">이전 예제에서는 식 `newCustomer = True` 부울 값을 나타내는 및 `=` 기호는 비교 연산자로 해석 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f1d63-108">In the preceding example, the expression `newCustomer = True` represents a Boolean value, and the `=` sign is interpreted as a comparison operator.</span></span> <span data-ttu-id="f1d63-109">독립 실행형 문에 `=` 로그인 대입 연산자로 해석 되 고 왼쪽에 있는 변수에 오른쪽에 있는 값을 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="f1d63-109">In a stand-alone statement, the `=` sign is interpreted as an assignment operator and assigns the value on the right to the variable on the left.</span></span> <span data-ttu-id="f1d63-110">다음은 이에 대한 예입니다.</span><span class="sxs-lookup"><span data-stu-id="f1d63-110">The following example illustrates this.</span></span>  
  
 [!code-vb[VbVbalrOperators#88](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/boolean-expressions_2.vb)]  
  
 <span data-ttu-id="f1d63-111">자세한 내용은 참조 하세요. [값 비교](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/value-comparisons.md) 하 고 [문을](../../../../visual-basic/language-reference/statements/index.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="f1d63-111">For further information, see [Value Comparisons](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/value-comparisons.md) and [Statements](../../../../visual-basic/language-reference/statements/index.md).</span></span>  
  
## <a name="comparison-operators"></a><span data-ttu-id="f1d63-112">비교 연산자</span><span class="sxs-lookup"><span data-stu-id="f1d63-112">Comparison Operators</span></span>  
 <span data-ttu-id="f1d63-113">비교 연산자와 같은 `=`, `<`를 `>`를 `<>`를 `<=`, 및 `>=` 오른쪽에 있는 식에 연산자의 좌 변에 있는 식을 비교 하 여 부울 식을 생성 연산자 및 평가 결과 `True` 또는 `False`합니다.</span><span class="sxs-lookup"><span data-stu-id="f1d63-113">Comparison operators such as `=`, `<`, `>`, `<>`, `<=`, and `>=` produce Boolean expressions by comparing the expression on the left side of the operator to the expression on the right side of the operator and evaluating the result as `True` or `False`.</span></span> <span data-ttu-id="f1d63-114">다음은 이에 대한 예입니다.</span><span class="sxs-lookup"><span data-stu-id="f1d63-114">The following example illustrates this.</span></span>  
  
 `42 < 81`  
  
 <span data-ttu-id="f1d63-115">앞의 예제에서 부울 식으로 계산 되는 42 81 미만 이므로 `True`합니다.</span><span class="sxs-lookup"><span data-stu-id="f1d63-115">Because 42 is less than 81, the Boolean expression in the preceding example evaluates to `True`.</span></span> <span data-ttu-id="f1d63-116">이러한 종류의 식에 대 한 자세한 내용은 참조 하세요. [값 비교](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/value-comparisons.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="f1d63-116">For more information on this kind of expression, see [Value Comparisons](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/value-comparisons.md).</span></span>  
  
### <a name="comparison-operators-combined-with-logical-operators"></a><span data-ttu-id="f1d63-117">논리 연산자와 결합 하는 비교 연산자</span><span class="sxs-lookup"><span data-stu-id="f1d63-117">Comparison Operators Combined with Logical Operators</span></span>  
 <span data-ttu-id="f1d63-118">비교 식 논리 연산자를 사용 하 여 더 복잡 한 부울 식을 생성 하기 위해 조합할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f1d63-118">Comparison expressions can be combined using logical operators to produce more complex Boolean expressions.</span></span> <span data-ttu-id="f1d63-119">다음 예제에서는 논리 연산자를 사용 하 여 함께에서 비교 연산자의 사용을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="f1d63-119">The following example demonstrates the use of comparison operators in conjunction with a logical operator.</span></span>  
  
 `x > y And x < 1000`  
  
 <span data-ttu-id="f1d63-120">앞의 예제에서 전체 식의 값의 양쪽에 있는 식의 값에 종속 된 `And` 연산자입니다.</span><span class="sxs-lookup"><span data-stu-id="f1d63-120">In the preceding example, the value of the overall expression depends on the values of the expressions on each side of the `And` operator.</span></span> <span data-ttu-id="f1d63-121">두 식이 모두 `True`, 전체 식이 다음 `True`합니다.</span><span class="sxs-lookup"><span data-stu-id="f1d63-121">If both expressions are `True`, then the overall expression evaluates to `True`.</span></span> <span data-ttu-id="f1d63-122">식 중 하나가 `False`, 전체 식은 다음 `False`합니다.</span><span class="sxs-lookup"><span data-stu-id="f1d63-122">If either expression is `False`, then the entire expression evaluates to `False`.</span></span>  
  
## <a name="short-circuiting-operators"></a><span data-ttu-id="f1d63-123">연산자를 단락 (short-circuiting)</span><span class="sxs-lookup"><span data-stu-id="f1d63-123">Short-Circuiting Operators</span></span>  
 <span data-ttu-id="f1d63-124">논리 연산자 `AndAlso` 하 고 `OrElse` 동작이 라고도 *단락 (short-circuiting)* 합니다.</span><span class="sxs-lookup"><span data-stu-id="f1d63-124">The logical operators `AndAlso` and `OrElse` exhibit behavior known as *short-circuiting*.</span></span> <span data-ttu-id="f1d63-125">단락 연산자는 먼저 왼쪽된 피연산자를 계산 합니다.</span><span class="sxs-lookup"><span data-stu-id="f1d63-125">A short-circuiting operator evaluates the left operand first.</span></span> <span data-ttu-id="f1d63-126">경우 전체 식의 값을 결정 하는 왼쪽된 피연산자, 오른쪽 식의 계산 하지 않고 프로그램 실행이 계속 합니다.</span><span class="sxs-lookup"><span data-stu-id="f1d63-126">If the left operand determines the value of the entire expression, then program execution proceeds without evaluating the right expression.</span></span> <span data-ttu-id="f1d63-127">다음은 이에 대한 예입니다.</span><span class="sxs-lookup"><span data-stu-id="f1d63-127">The following example illustrates this.</span></span>  
  
 [!code-vb[VbVbalrOperators#89](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/boolean-expressions_3.vb)]  
  
 <span data-ttu-id="f1d63-128">앞의 예제는 연산자는 왼쪽된에 있는 식 계산 `45 < 12`합니다.</span><span class="sxs-lookup"><span data-stu-id="f1d63-128">In the preceding example, the operator evaluates the left expression, `45 < 12`.</span></span> <span data-ttu-id="f1d63-129">왼쪽에 있는 식이 때문 `False`, 전체 논리식 이어야 `False`합니다.</span><span class="sxs-lookup"><span data-stu-id="f1d63-129">Because the left expression evaluates to `False`, the entire logical expression must evaluate to `False`.</span></span> <span data-ttu-id="f1d63-130">프로그램 실행 내에서 코드 실행을 건너뜁니다 따라서 합니다 `If` 오른쪽에 있는 식을 계산 하지 않고 블록 `testFunction(3)`합니다.</span><span class="sxs-lookup"><span data-stu-id="f1d63-130">Program execution thus skips execution of the code within the `If` block without evaluating the right expression, `testFunction(3)`.</span></span> <span data-ttu-id="f1d63-131">이 예제를 호출 하지 않습니다 `testFunction()` 왼쪽된 식에는 전체 식을 falsifies 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="f1d63-131">This example does not call `testFunction()` because the left expression falsifies the entire expression.</span></span>  
  
 <span data-ttu-id="f1d63-132">마찬가지로, 경우 사용 하 여 논리 식 왼쪽된에 있는 식이 `OrElse` 로 `True`, 실행 코드의 다음 줄을 계산 하지 않고 계속 오른쪽 식의 왼쪽된 식의 전체 유효성 검사가 이미 있으므로 식입니다.</span><span class="sxs-lookup"><span data-stu-id="f1d63-132">Similarly, if the left expression in a logical expression using `OrElse` evaluates to `True`, execution proceeds to the next line of code without evaluating the right expression, because the left expression has already validated the entire expression.</span></span>  
  
### <a name="comparison-with-non-short-circuiting-operators"></a><span data-ttu-id="f1d63-133">비-단락-(short-circuit) 연산자를 사용 하 여 비교</span><span class="sxs-lookup"><span data-stu-id="f1d63-133">Comparison with Non-Short-Circuiting Operators</span></span>  
 <span data-ttu-id="f1d63-134">논리 연산자의 양쪽 모두 평가 되는 반면 때 논리 연산자 `And` 고 `Or` 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f1d63-134">By contrast, both sides of the logical operator are evaluated when the logical operators `And` and `Or` are used.</span></span> <span data-ttu-id="f1d63-135">다음은 이에 대한 예입니다.</span><span class="sxs-lookup"><span data-stu-id="f1d63-135">The following example illustrates this.</span></span>  
  
 [!code-vb[VbVbalrOperators#90](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/boolean-expressions_4.vb)]  
  
 <span data-ttu-id="f1d63-136">위의 예제에서는 호출 `testFunction()` 왼쪽에 있는 식이 `False`합니다.</span><span class="sxs-lookup"><span data-stu-id="f1d63-136">The preceding example calls `testFunction()` even though the left expression evaluates to `False`.</span></span>  
  
## <a name="parenthetical-expressions"></a><span data-ttu-id="f1d63-137">괄호 식</span><span class="sxs-lookup"><span data-stu-id="f1d63-137">Parenthetical Expressions</span></span>  
 <span data-ttu-id="f1d63-138">부울 식의 계산 순서를 제어 하려면 괄호를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f1d63-138">You can use parentheses to control the order of evaluation of Boolean expressions.</span></span> <span data-ttu-id="f1d63-139">괄호로 묶은 식을 먼저 평가 합니다.</span><span class="sxs-lookup"><span data-stu-id="f1d63-139">Expressions enclosed by parentheses evaluate first.</span></span> <span data-ttu-id="f1d63-140">여러 수준의 중첩을 가장 깊이 중첩 된 식에 우선 순위가 부여 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f1d63-140">For multiple levels of nesting, precedence is granted to the most deeply nested expressions.</span></span> <span data-ttu-id="f1d63-141">괄호 안에서 평가 연산자 우선 순위 규칙에 따라 진행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f1d63-141">Within parentheses, evaluation proceeds according to the rules of operator precedence.</span></span> <span data-ttu-id="f1d63-142">자세한 내용은 [Visual Basic의 연산자 우선 순위](../../../../visual-basic/language-reference/operators/operator-precedence.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="f1d63-142">For more information, see [Operator Precedence in Visual Basic](../../../../visual-basic/language-reference/operators/operator-precedence.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f1d63-143">참고자료</span><span class="sxs-lookup"><span data-stu-id="f1d63-143">See also</span></span>
- [<span data-ttu-id="f1d63-144">Visual Basic의 논리 및 비트 연산자</span><span class="sxs-lookup"><span data-stu-id="f1d63-144">Logical and Bitwise Operators in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md)
- [<span data-ttu-id="f1d63-145">값 비교</span><span class="sxs-lookup"><span data-stu-id="f1d63-145">Value Comparisons</span></span>](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/value-comparisons.md)
- [<span data-ttu-id="f1d63-146">문(C++)</span><span class="sxs-lookup"><span data-stu-id="f1d63-146">Statements</span></span>](../../../../visual-basic/programming-guide/language-features/statements.md)
- [<span data-ttu-id="f1d63-147">비교 연산자</span><span class="sxs-lookup"><span data-stu-id="f1d63-147">Comparison Operators</span></span>](../../../../visual-basic/language-reference/operators/comparison-operators.md)
- [<span data-ttu-id="f1d63-148">연산자의 효율적 결합</span><span class="sxs-lookup"><span data-stu-id="f1d63-148">Efficient Combination of Operators</span></span>](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/efficient-combination-of-operators.md)
- [<span data-ttu-id="f1d63-149">Visual Basic에서의 연산자 우선 순위</span><span class="sxs-lookup"><span data-stu-id="f1d63-149">Operator Precedence in Visual Basic</span></span>](../../../../visual-basic/language-reference/operators/operator-precedence.md)
- [<span data-ttu-id="f1d63-150">Boolean 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="f1d63-150">Boolean Data Type</span></span>](../../../../visual-basic/language-reference/data-types/boolean-data-type.md)
