---
title: 함수 식(Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- Function expression [Visual Basic]
- functions [Visual Basic], function expressions
- lambda expressions [Visual Basic], function expression
ms.assetid: e8a47a45-4b8a-4f45-a623-7653625dffbc
ms.openlocfilehash: cfdd17f6f4ee6c4ddb3fa73ab3ec9c5ce46a162f
ms.sourcegitcommit: ba5c189bf44d44204a3e8838e59ec378a62d82f3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/12/2018
ms.locfileid: "44709677"
---
# <a name="function-expression-visual-basic"></a><span data-ttu-id="aff03-102">함수 식(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="aff03-102">Function Expression (Visual Basic)</span></span>
<span data-ttu-id="aff03-103">매개 변수 및 함수가 람다 식을 정의 하는 코드를 선언 합니다.</span><span class="sxs-lookup"><span data-stu-id="aff03-103">Declares the parameters and code that define a function lambda expression.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="aff03-104">구문</span><span class="sxs-lookup"><span data-stu-id="aff03-104">Syntax</span></span>  
  
```  
Function ( [ parameterlist ] ) expression  
- or -  
Function ( [ parameterlist ] )  
  [ statements ]  
End Function  
```  
  
## <a name="parts"></a><span data-ttu-id="aff03-105">요소</span><span class="sxs-lookup"><span data-stu-id="aff03-105">Parts</span></span>  
  
|<span data-ttu-id="aff03-106">용어</span><span class="sxs-lookup"><span data-stu-id="aff03-106">Term</span></span>|<span data-ttu-id="aff03-107">정의</span><span class="sxs-lookup"><span data-stu-id="aff03-107">Definition</span></span>|  
|---|---|  
|`parameterlist`|<span data-ttu-id="aff03-108">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="aff03-108">Optional.</span></span> <span data-ttu-id="aff03-109">이 절차의 매개 변수를 나타내는 로컬 변수 이름의 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="aff03-109">A list of local variable names that represent the parameters of this procedure.</span></span> <span data-ttu-id="aff03-110">괄호는 목록이 비어 있는 경우에 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="aff03-110">The parentheses must be present even when the list is empty.</span></span> <span data-ttu-id="aff03-111">참조 [매개 변수 목록](../../../visual-basic/language-reference/statements/parameter-list.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="aff03-111">See [Parameter List](../../../visual-basic/language-reference/statements/parameter-list.md).</span></span>|  
|`expression`|<span data-ttu-id="aff03-112">필수.</span><span class="sxs-lookup"><span data-stu-id="aff03-112">Required.</span></span> <span data-ttu-id="aff03-113">단일 식입니다.</span><span class="sxs-lookup"><span data-stu-id="aff03-113">A single expression.</span></span> <span data-ttu-id="aff03-114">식의 형식이 함수 반환 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="aff03-114">The type of the expression is the return type of the function.</span></span>|  
|`statements`|<span data-ttu-id="aff03-115">필수.</span><span class="sxs-lookup"><span data-stu-id="aff03-115">Required.</span></span> <span data-ttu-id="aff03-116">사용 하 여 값을 반환 하는 문의 목록은 `Return` 문입니다.</span><span class="sxs-lookup"><span data-stu-id="aff03-116">A list of statements that returns a value by using the `Return` statement.</span></span> <span data-ttu-id="aff03-117">(참조 [Return 문](../../../visual-basic/language-reference/statements/return-statement.md).) 반환 값의 유형 함수의 반환 형식이입니다.</span><span class="sxs-lookup"><span data-stu-id="aff03-117">(See [Return Statement](../../../visual-basic/language-reference/statements/return-statement.md).) The type of the value returned is the return type of the function.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="aff03-118">설명</span><span class="sxs-lookup"><span data-stu-id="aff03-118">Remarks</span></span>  
 <span data-ttu-id="aff03-119">A *람다 식* 계산한 값을 반환 하는 이름이 없는 함수입니다.</span><span class="sxs-lookup"><span data-stu-id="aff03-119">A *lambda expression* is a function without a name that calculates and returns a value.</span></span> <span data-ttu-id="aff03-120">람다 식을 사용할 수 있습니다 어디서 나 사용할 수 대리자 형식을 제외 하 고 인수로 `RemoveHandler`합니다.</span><span class="sxs-lookup"><span data-stu-id="aff03-120">You can use a lambda expression anywhere you can use a delegate type, except as an argument to `RemoveHandler`.</span></span> <span data-ttu-id="aff03-121">대리자 및 람다 식 대리자를 사용 하 여 사용 하는 방법에 대 한 자세한 내용은 참조 하세요. [대리자 문](../../../visual-basic/language-reference/statements/delegate-statement.md) 하 고 [완화 된 대리자 변환](../../../visual-basic/programming-guide/language-features/delegates/relaxed-delegate-conversion.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="aff03-121">For more information about delegates, and the use of lambda expressions with delegates, see [Delegate Statement](../../../visual-basic/language-reference/statements/delegate-statement.md) and [Relaxed Delegate Conversion](../../../visual-basic/programming-guide/language-features/delegates/relaxed-delegate-conversion.md).</span></span>  
  
## <a name="lambda-expression-syntax"></a><span data-ttu-id="aff03-122">람다 식 구문</span><span class="sxs-lookup"><span data-stu-id="aff03-122">Lambda Expression Syntax</span></span>  
 <span data-ttu-id="aff03-123">람다 식의 구문은 유사 표준 함수의 합니다.</span><span class="sxs-lookup"><span data-stu-id="aff03-123">The syntax of a lambda expression resembles that of a standard function.</span></span> <span data-ttu-id="aff03-124">차이점은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="aff03-124">The differences are as follows:</span></span>  
  
-   <span data-ttu-id="aff03-125">람다 식에 이름이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="aff03-125">A lambda expression does not have a name.</span></span>  
  
-   <span data-ttu-id="aff03-126">람다 식은와 같은 한정자를 사용할 수 없습니다 `Overloads` 또는 `Overrides`합니다.</span><span class="sxs-lookup"><span data-stu-id="aff03-126">Lambda expressions cannot have modifiers, such as `Overloads` or `Overrides`.</span></span>  
  
-   <span data-ttu-id="aff03-127">람다 식 사용 하지 마십시오는 `As` 절 함수의 반환 형식을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="aff03-127">Lambda expressions do not use an `As` clause to designate the return type of the function.</span></span> <span data-ttu-id="aff03-128">대신 형식은 한 줄 람다 식의 본문으로 계산 되는 값 또는 여러 줄 람다 식의 반환 값에서 유추 됩니다.</span><span class="sxs-lookup"><span data-stu-id="aff03-128">Instead, the type is inferred from the value that the body of a single-line lambda expression evaluates to, or the return value of a multiline lambda expression.</span></span> <span data-ttu-id="aff03-129">예를 들어 한 줄 람다 식의 본문이 `Where cust.City = "London"`, 해당 반환 형식은 `Boolean`합니다.</span><span class="sxs-lookup"><span data-stu-id="aff03-129">For example, if the body of a single-line lambda expression is `Where cust.City = "London"`, its return type is `Boolean`.</span></span>  
  
-   <span data-ttu-id="aff03-130">한 줄 람다 식의 본문에는 문이 아닌 식 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="aff03-130">The body of a single-line lambda expression must be an expression, not a statement.</span></span> <span data-ttu-id="aff03-131">Function 프로시저를 호출 하지만 sub 프로시저를 호출 하지 본문 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aff03-131">The body can consist of a call to a function procedure, but not a call to a sub procedure.</span></span>  
  
-   <span data-ttu-id="aff03-132">데이터 형식 중 하나 또는 모두를 유추할 수 해야 모든 매개 변수에 지정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="aff03-132">Either all parameters must have specified data types or all must be inferred.</span></span>  
  
-   <span data-ttu-id="aff03-133">선택 사항 및 Paramarray 매개 변수는 허용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="aff03-133">Optional and Paramarray parameters are not permitted.</span></span>  
  
-   <span data-ttu-id="aff03-134">제네릭 매개 변수가 허용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="aff03-134">Generic parameters are not permitted.</span></span>  
  
## <a name="example"></a><span data-ttu-id="aff03-135">예제</span><span class="sxs-lookup"><span data-stu-id="aff03-135">Example</span></span>  
 <span data-ttu-id="aff03-136">다음 예제에서는 간단한 람다 식을 만드는 두 가지 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="aff03-136">The following examples show two ways to create simple lambda expressions.</span></span> <span data-ttu-id="aff03-137">첫 번째 예제에서는 한 `Dim` 함수에 대 한 이름을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="aff03-137">The first uses a `Dim` to provide a name for the function.</span></span> <span data-ttu-id="aff03-138">함수를 호출 하려면 매개 변수 값에 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="aff03-138">To call the function, you send in a value for the parameter.</span></span>  
  
 [!code-vb[VbVbalrLambdas#1](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/function-expression_1.vb)]  
  
 [!code-vb[VbVbalrLambdas#2](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/function-expression_2.vb)]  
  
## <a name="example"></a><span data-ttu-id="aff03-139">예제</span><span class="sxs-lookup"><span data-stu-id="aff03-139">Example</span></span>  
 <span data-ttu-id="aff03-140">또는 선언 하 고 동시에 함수를 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aff03-140">Alternatively, you can declare and run the function at the same time.</span></span>  
  
 [!code-vb[VbVbalrLambdas#3](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/function-expression_3.vb)]  
  
## <a name="example"></a><span data-ttu-id="aff03-141">예제</span><span class="sxs-lookup"><span data-stu-id="aff03-141">Example</span></span>  
 <span data-ttu-id="aff03-142">다음은 해당 인수를 증가 시키고 값을 반환 하는 람다 식의 예입니다.</span><span class="sxs-lookup"><span data-stu-id="aff03-142">Following is an example of a lambda expression that increments its argument and returns the value.</span></span> <span data-ttu-id="aff03-143">함수에 대 한 모두를 한 줄 및 여러 줄 람다 식 구문을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="aff03-143">The example shows both the single-line and multiline lambda expression syntax for a function.</span></span> <span data-ttu-id="aff03-144">더 많은 예제를 참조 하세요 [람다 식](../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="aff03-144">For more examples, see [Lambda Expressions](../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md).</span></span>  
  
 [!code-vb[VbVbalrLambdas#14](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/function-expression_4.vb)]  
  
## <a name="example"></a><span data-ttu-id="aff03-145">예제</span><span class="sxs-lookup"><span data-stu-id="aff03-145">Example</span></span>  
 <span data-ttu-id="aff03-146">람다 식의 기반이 되는 쿼리 연산자에서 많은 [!INCLUDE[vbteclinqext](~/includes/vbteclinqext-md.md)], 메서드 기반 쿼리에 명시적으로 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aff03-146">Lambda expressions underlie many of the query operators in [!INCLUDE[vbteclinqext](~/includes/vbteclinqext-md.md)], and can be used explicitly in method-based queries.</span></span> <span data-ttu-id="aff03-147">다음 예제에서는 일반적인 [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] 쿼리의 번역 뒤에 메서드 형식으로 쿼리 합니다.</span><span class="sxs-lookup"><span data-stu-id="aff03-147">The following example shows a typical [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] query, followed by the translation of the query into method format.</span></span>  
  
```vb  
Dim londonCusts = From cust In db.Customers  
                       Where cust.City = "London"  
                       Select cust  
  
' This query is compiled to the following code:  
Dim londonCusts = db.Customers.  
                  Where(Function(cust) cust.City = "London").  
                  Select(Function(cust) cust)  
```  
  
 <span data-ttu-id="aff03-148">쿼리 메서드에 대 한 자세한 내용은 참조 하세요. [쿼리](../../../visual-basic/language-reference/queries/index.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="aff03-148">For more information about query methods, see [Queries](../../../visual-basic/language-reference/queries/index.md).</span></span> <span data-ttu-id="aff03-149">표준 쿼리 연산자에 대 한 자세한 내용은 참조 하세요. [표준 쿼리 연산자 개요](../../programming-guide/concepts/linq/standard-query-operators-overview.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="aff03-149">For more information about standard query operators, see [Standard Query Operators Overview](../../programming-guide/concepts/linq/standard-query-operators-overview.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aff03-150">참고 항목</span><span class="sxs-lookup"><span data-stu-id="aff03-150">See Also</span></span>  
 [<span data-ttu-id="aff03-151">Function 문</span><span class="sxs-lookup"><span data-stu-id="aff03-151">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)  
 [<span data-ttu-id="aff03-152">람다 식</span><span class="sxs-lookup"><span data-stu-id="aff03-152">Lambda Expressions</span></span>](../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md)  
 [<span data-ttu-id="aff03-153">연산자 및 식</span><span class="sxs-lookup"><span data-stu-id="aff03-153">Operators and Expressions</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/index.md)  
 [<span data-ttu-id="aff03-154">문</span><span class="sxs-lookup"><span data-stu-id="aff03-154">Statements</span></span>](../../../visual-basic/programming-guide/language-features/statements.md)  
 [<span data-ttu-id="aff03-155">값 비교</span><span class="sxs-lookup"><span data-stu-id="aff03-155">Value Comparisons</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/value-comparisons.md)  
 [<span data-ttu-id="aff03-156">부울 식</span><span class="sxs-lookup"><span data-stu-id="aff03-156">Boolean Expressions</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/boolean-expressions.md)  
 [<span data-ttu-id="aff03-157">If 연산자</span><span class="sxs-lookup"><span data-stu-id="aff03-157">If Operator</span></span>](../../../visual-basic/language-reference/operators/if-operator.md)  
 [<span data-ttu-id="aff03-158">완화된 대리자 변환</span><span class="sxs-lookup"><span data-stu-id="aff03-158">Relaxed Delegate Conversion</span></span>](../../../visual-basic/programming-guide/language-features/delegates/relaxed-delegate-conversion.md)
