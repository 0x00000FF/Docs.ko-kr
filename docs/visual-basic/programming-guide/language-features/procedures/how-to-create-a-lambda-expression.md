---
title: '방법: 람다 식 (Visual Basic) 만들기'
ms.date: 07/20/2015
helpviewer_keywords:
- lambda expressions [Visual Basic]
- expressions [Visual Basic], lambda
ms.assetid: 3279bd5c-80f7-410a-a7ba-f7085ed36aa5
ms.openlocfilehash: 35df64848c0506a1c0a97bd8cd34f158f9febcd7
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/28/2019
ms.locfileid: "56970170"
---
# <a name="how-to-create-a-lambda-expression-visual-basic"></a><span data-ttu-id="6b6f6-102">방법: 람다 식 (Visual Basic) 만들기</span><span class="sxs-lookup"><span data-stu-id="6b6f6-102">How to: Create a Lambda Expression (Visual Basic)</span></span>
<span data-ttu-id="6b6f6-103">A *람다 식* 은 함수 또는 서브루틴에 이름이 없습니다입니다.</span><span class="sxs-lookup"><span data-stu-id="6b6f6-103">A *lambda expression* is a function or subroutine that does not have a name.</span></span> <span data-ttu-id="6b6f6-104">람다 식은 대리자 형식이 유효한 모든 곳에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6b6f6-104">A lambda expression can be used wherever a delegate type is valid.</span></span>  
  
### <a name="to-create-a-single-line-lambda-expression-function"></a><span data-ttu-id="6b6f6-105">한 줄 람다 식 함수를 만들려면</span><span class="sxs-lookup"><span data-stu-id="6b6f6-105">To create a single-line lambda expression function</span></span>  
  
1.  <span data-ttu-id="6b6f6-106">대리자 형식을 사용할 수 있는 모든 상황에서 키워드를 입력 `Function`다음 예제와 같이:</span><span class="sxs-lookup"><span data-stu-id="6b6f6-106">In any situation where a delegate type could be used, type the keyword `Function`, as in the following example:</span></span>  
  
     <span data-ttu-id="6b6f6-107">`Dim add1 =`  `Function`</span><span class="sxs-lookup"><span data-stu-id="6b6f6-107">`Dim add1 =`   `Function`</span></span>  
  
2.  <span data-ttu-id="6b6f6-108">괄호로 직후 `Function`, 함수의 매개 변수를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="6b6f6-108">In parentheses, directly after `Function`, type the parameters of the function.</span></span> <span data-ttu-id="6b6f6-109">뒤에 이름을 지정 하지 않으면 확인 `Function`합니다.</span><span class="sxs-lookup"><span data-stu-id="6b6f6-109">Notice that you do not specify a name after `Function`.</span></span>  
  
     <span data-ttu-id="6b6f6-110">`Dim add1 = Function`  `(num As Integer)`</span><span class="sxs-lookup"><span data-stu-id="6b6f6-110">`Dim add1 = Function`   `(num As Integer)`</span></span>  
  
3.  <span data-ttu-id="6b6f6-111">매개 변수 목록 다음 함수의 본문으로 단일 식을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="6b6f6-111">Following the parameter list, type a single expression as the body of the function.</span></span> <span data-ttu-id="6b6f6-112">식이 계산 되는 값에는 함수가 반환한 값이입니다.</span><span class="sxs-lookup"><span data-stu-id="6b6f6-112">The value that the expression evaluates to is the value returned by the function.</span></span> <span data-ttu-id="6b6f6-113">사용 하지 않는 것을 `As` 반환 형식을 지정 하는 절.</span><span class="sxs-lookup"><span data-stu-id="6b6f6-113">You do not use an `As` clause to specify the return type.</span></span>  
  
     [!code-vb[VbVbalrLambdas#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#1)]  
  
     <span data-ttu-id="6b6f6-114">정수 인수에 전달 하 람다 식을 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="6b6f6-114">You call the lambda expression by passing in an integer argument.</span></span>  
  
     [!code-vb[VbVbalrLambdas#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#2)]  
  
4.  <span data-ttu-id="6b6f6-115">또는 동일한 결과 다음 예제에서 수행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6b6f6-115">Alternatively, the same result is accomplished by the following example:</span></span>  
  
     [!code-vb[VbVbalrLambdas#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#3)]  
  
### <a name="to-create-a-single-line-lambda-expression-subroutine"></a><span data-ttu-id="6b6f6-116">한 줄 람다 식 서브루틴을 만들려면</span><span class="sxs-lookup"><span data-stu-id="6b6f6-116">To create a single-line lambda expression subroutine</span></span>  
  
1.  <span data-ttu-id="6b6f6-117">대리자 형식을 사용할 수 있는 모든 상황에서 키워드를 입력 `Sub`다음 예제에서와 같이 합니다.</span><span class="sxs-lookup"><span data-stu-id="6b6f6-117">In any situation where a delegate type could be used, type the keyword `Sub`, as shown in the following example.</span></span>  
  
     <span data-ttu-id="6b6f6-118">`Dim add1 =`  `Sub`</span><span class="sxs-lookup"><span data-stu-id="6b6f6-118">`Dim add1 =`   `Sub`</span></span>  
  
2.  <span data-ttu-id="6b6f6-119">괄호로 직후 `Sub`, 서브루틴의 매개 변수를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="6b6f6-119">In parentheses, directly after `Sub`, type the parameters of the subroutine.</span></span> <span data-ttu-id="6b6f6-120">뒤에 이름을 지정 하지 않으면 확인 `Sub`합니다.</span><span class="sxs-lookup"><span data-stu-id="6b6f6-120">Notice that you do not specify a name after `Sub`.</span></span>  
  
     <span data-ttu-id="6b6f6-121">`Dim add1 = Sub`  `(msg As String)`</span><span class="sxs-lookup"><span data-stu-id="6b6f6-121">`Dim add1 = Sub`   `(msg As String)`</span></span>  
  
3.  <span data-ttu-id="6b6f6-122">매개 변수 목록에 다음 서브루틴의 본문으로 단일 문을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="6b6f6-122">Following the parameter list, type a single statement as the body of the subroutine.</span></span>  
  
     [!code-vb[VbVbalrLambdas#17](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#17)]  
  
     <span data-ttu-id="6b6f6-123">문자열 인수를 전달 하 람다 식을 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="6b6f6-123">You call the lambda expression by passing in a string argument.</span></span>  
  
     [!code-vb[VbVbalrLambdas#18](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#18)]  
  
### <a name="to-create-a-multiline-lambda-expression-function"></a><span data-ttu-id="6b6f6-124">여러 줄 람다 식 함수를 만들려면</span><span class="sxs-lookup"><span data-stu-id="6b6f6-124">To create a multiline lambda expression function</span></span>  
  
1.  <span data-ttu-id="6b6f6-125">대리자 형식을 사용할 수 있는 모든 상황에서 키워드를 입력 `Function`다음 예제에서와 같이 합니다.</span><span class="sxs-lookup"><span data-stu-id="6b6f6-125">In any situation where a delegate type could be used, type the keyword `Function`, as shown in the following example.</span></span>  
  
     <span data-ttu-id="6b6f6-126">`Dim add1 =`  `Function`</span><span class="sxs-lookup"><span data-stu-id="6b6f6-126">`Dim add1 =`   `Function`</span></span>  
  
2.  <span data-ttu-id="6b6f6-127">괄호로 직후 `Function`, 함수의 매개 변수를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="6b6f6-127">In parentheses, directly after `Function`, type the parameters of the function.</span></span> <span data-ttu-id="6b6f6-128">뒤에 이름을 지정 하지 않으면 확인 `Function`합니다.</span><span class="sxs-lookup"><span data-stu-id="6b6f6-128">Notice that you do not specify a name after `Function`.</span></span>  
  
     <span data-ttu-id="6b6f6-129">`Dim add1 = Function`  `(index As Integer)`</span><span class="sxs-lookup"><span data-stu-id="6b6f6-129">`Dim add1 = Function`   `(index As Integer)`</span></span>  
  
3.  <span data-ttu-id="6b6f6-130">Enter 키를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="6b6f6-130">Press ENTER.</span></span> <span data-ttu-id="6b6f6-131">`End Function` 문을 자동으로 추가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6b6f6-131">The `End Function` statement is automatically added.</span></span>  
  
4.  <span data-ttu-id="6b6f6-132">함수의 본문 내에서 식을 만들고 값을 반환 하려면 다음 코드를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="6b6f6-132">Within the body of the function, add the following code to create an expression and return the value.</span></span> <span data-ttu-id="6b6f6-133">사용 하지 않는 것을 `As` 반환 형식을 지정 하는 절.</span><span class="sxs-lookup"><span data-stu-id="6b6f6-133">You do not use an `As` clause to specify the return type.</span></span>  
  
     [!code-vb[VbVbalrLambdas#19](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#19)]  
  
     <span data-ttu-id="6b6f6-134">정수 인수에 전달 하 람다 식을 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="6b6f6-134">You call the lambda expression by passing in an integer argument.</span></span>  
  
     [!code-vb[VbVbalrLambdas#20](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#20)]  
  
### <a name="to-create-a-multiline-lambda-expression-subroutine"></a><span data-ttu-id="6b6f6-135">여러 줄 람다 식 서브루틴을 만들려면</span><span class="sxs-lookup"><span data-stu-id="6b6f6-135">To create a multiline lambda expression subroutine</span></span>  
  
1.  <span data-ttu-id="6b6f6-136">대리자 형식을 사용할 수 있는 모든 상황에서 키워드를 입력 `Sub`다음 예제에서와 같이:</span><span class="sxs-lookup"><span data-stu-id="6b6f6-136">In any situation where a delegate type could be used, type the keyword `Sub`, as shown in the following example:</span></span>  
  
     <span data-ttu-id="6b6f6-137">`Dim add1 =`  `Sub`</span><span class="sxs-lookup"><span data-stu-id="6b6f6-137">`Dim add1 =`   `Sub`</span></span>  
  
2.  <span data-ttu-id="6b6f6-138">괄호로 직후 `Sub`, 서브루틴의 매개 변수를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="6b6f6-138">In parentheses, directly after `Sub`, type the parameters of the subroutine.</span></span> <span data-ttu-id="6b6f6-139">뒤에 이름을 지정 하지 않으면 확인 `Sub`합니다.</span><span class="sxs-lookup"><span data-stu-id="6b6f6-139">Notice that you do not specify a name after `Sub`.</span></span>  
  
     <span data-ttu-id="6b6f6-140">`Dim add1 = Sub`  `(msg As String)`</span><span class="sxs-lookup"><span data-stu-id="6b6f6-140">`Dim add1 = Sub`  `(msg As String)`</span></span>  
  
3.  <span data-ttu-id="6b6f6-141">Enter 키를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="6b6f6-141">Press ENTER.</span></span> <span data-ttu-id="6b6f6-142">`End Sub` 문을 자동으로 추가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6b6f6-142">The `End Sub` statement is automatically added.</span></span>  
  
4.  <span data-ttu-id="6b6f6-143">함수의 본문 내에서 서브루틴 호출 될 때 실행한 다음 코드를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="6b6f6-143">Within the body of the function, add the following code to execute when the subroutine is invoked.</span></span>  
  
     [!code-vb[VbVbalrLambdas#21](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#21)]  
  
     <span data-ttu-id="6b6f6-144">문자열 인수를 전달 하 람다 식을 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="6b6f6-144">You call the lambda expression by passing in a string argument.</span></span>  
  
     [!code-vb[VbVbalrLambdas#22](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#22)]  
  
## <a name="example"></a><span data-ttu-id="6b6f6-145">예제</span><span class="sxs-lookup"><span data-stu-id="6b6f6-145">Example</span></span>  
 <span data-ttu-id="6b6f6-146">람다 식의 일반적인 용도 형식의 매개 변수에 대해 인수로 전달 될 수 있는 함수를 정의 하는 `Delegate`합니다.</span><span class="sxs-lookup"><span data-stu-id="6b6f6-146">A common use of lambda expressions is to define a function that can be passed in as the argument for a parameter whose type is `Delegate`.</span></span> <span data-ttu-id="6b6f6-147">다음 예제에서는 <xref:System.Diagnostics.Process.GetProcesses%2A> 로컬 컴퓨터에서 실행 중인 프로세스의 배열을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="6b6f6-147">In the following example, the <xref:System.Diagnostics.Process.GetProcesses%2A> method returns an array of the processes running on the local computer.</span></span> <span data-ttu-id="6b6f6-148"><xref:System.Linq.Enumerable.Where%2A> 메서드를 <xref:System.Linq.Enumerable> 클래스에 필요한를 `Boolean` 인수로 대리자입니다.</span><span class="sxs-lookup"><span data-stu-id="6b6f6-148">The <xref:System.Linq.Enumerable.Where%2A> method from the <xref:System.Linq.Enumerable> class requires a `Boolean` delegate as its argument.</span></span> <span data-ttu-id="6b6f6-149">예제에서 람다 식은 해당 용도로 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6b6f6-149">The lambda expression in the example is used for that purpose.</span></span> <span data-ttu-id="6b6f6-150">반환 `True` 에서 선택 됩니다 및 각 프로세스에 대해 스레드 한 개만 있는 `filteredList`합니다.</span><span class="sxs-lookup"><span data-stu-id="6b6f6-150">It returns `True` for each process that has only one thread, and those are selected in `filteredList`.</span></span>  
  
 [!code-vb[VbVbalrLambdas#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class4.vb#10)]  
  
 <span data-ttu-id="6b6f6-151">앞의 예제는 작성 된 다음 코드와 동일 [!INCLUDE[vbteclinqext](~/includes/vbteclinqext-md.md)] 구문:</span><span class="sxs-lookup"><span data-stu-id="6b6f6-151">The previous example is equivalent to the following code, which is written in [!INCLUDE[vbteclinqext](~/includes/vbteclinqext-md.md)] syntax:</span></span>  
  
 [!code-vb[VbVbalrLambdas#11](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class5.vb#11)]  
  
## <a name="see-also"></a><span data-ttu-id="6b6f6-152">참고자료</span><span class="sxs-lookup"><span data-stu-id="6b6f6-152">See also</span></span>
- <xref:System.Linq.Enumerable>
- [<span data-ttu-id="6b6f6-153">람다 식</span><span class="sxs-lookup"><span data-stu-id="6b6f6-153">Lambda Expressions</span></span>](./lambda-expressions.md)
- [<span data-ttu-id="6b6f6-154">Function 문</span><span class="sxs-lookup"><span data-stu-id="6b6f6-154">Function Statement</span></span>](../../../../visual-basic/language-reference/statements/function-statement.md)
- [<span data-ttu-id="6b6f6-155">Sub 문</span><span class="sxs-lookup"><span data-stu-id="6b6f6-155">Sub Statement</span></span>](../../../../visual-basic/language-reference/statements/sub-statement.md)
- [<span data-ttu-id="6b6f6-156">대리자</span><span class="sxs-lookup"><span data-stu-id="6b6f6-156">Delegates</span></span>](../../../../visual-basic/programming-guide/language-features/delegates/index.md)
- [<span data-ttu-id="6b6f6-157">방법: 프로시저에 Visual Basic에서 다른 프로시저 전달</span><span class="sxs-lookup"><span data-stu-id="6b6f6-157">How to: Pass Procedures to Another Procedure in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/delegates/how-to-pass-procedures-to-another-procedure.md)
- [<span data-ttu-id="6b6f6-158">Delegate 문</span><span class="sxs-lookup"><span data-stu-id="6b6f6-158">Delegate Statement</span></span>](../../../../visual-basic/language-reference/statements/delegate-statement.md)
- [<span data-ttu-id="6b6f6-159">Visual Basic의 LINQ 소개</span><span class="sxs-lookup"><span data-stu-id="6b6f6-159">Introduction to LINQ in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)
