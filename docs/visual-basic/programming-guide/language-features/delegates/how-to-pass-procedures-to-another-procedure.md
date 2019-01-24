---
title: '방법: 프로시저에 Visual Basic에서 다른 프로시저 전달'
ms.date: 07/20/2015
helpviewer_keywords:
- AddressOf operator [Visual Basic]
- delegates [Visual Basic], passing procedures
ms.assetid: 5adbba15-5a1d-413f-ab3e-3ff6cc0a4669
ms.openlocfilehash: cf5a8447cbedcd8071da98ac6763ff06eb608199
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54506760"
---
# <a name="how-to-pass-procedures-to-another-procedure-in-visual-basic"></a><span data-ttu-id="ba04d-102">방법: 프로시저에 Visual Basic에서 다른 프로시저 전달</span><span class="sxs-lookup"><span data-stu-id="ba04d-102">How to: Pass Procedures to Another Procedure in Visual Basic</span></span>
<span data-ttu-id="ba04d-103">이 예제에서는 대리자를 사용 하 여 프로시저에 다른 프로시저 전달 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="ba04d-103">This example shows how to use delegates to pass a procedure to another procedure.</span></span>  
  
 <span data-ttu-id="ba04d-104">대리자 형식이 Visual Basic에서 다른 형식 처럼 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ba04d-104">A delegate is a type that you can use like any other type in Visual Basic.</span></span> <span data-ttu-id="ba04d-105">`AddressOf` 연산자 프로시저 이름에 적용 될 때 대리자 개체를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="ba04d-105">The `AddressOf` operator returns a delegate object when applied to a procedure name.</span></span>  
  
 <span data-ttu-id="ba04d-106">이 예제에 사용 하 여 얻은 다른 프로시저에 대 한 참조를 사용할 수 있는 대리자 매개 변수를 사용 하 여 프로시저를 `AddressOf` 연산자입니다.</span><span class="sxs-lookup"><span data-stu-id="ba04d-106">This example has a procedure with a delegate parameter that can take a reference to another procedure, obtained with the `AddressOf` operator.</span></span>  
  
### <a name="create-the-delegate-and-matching-procedures"></a><span data-ttu-id="ba04d-107">대리자 및 일치 하는 프로시저 만들기</span><span class="sxs-lookup"><span data-stu-id="ba04d-107">Create the delegate and matching procedures</span></span>  
  
1.  <span data-ttu-id="ba04d-108">명명 된 대리자를 만드는 `MathOperator`합니다.</span><span class="sxs-lookup"><span data-stu-id="ba04d-108">Create a delegate named `MathOperator`.</span></span>  
  
     [!code-vb[VbVbalrDelegates#1](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-pass-procedures-to-another-procedure_1.vb)]  
  
2.  <span data-ttu-id="ba04d-109">라는 프로시저를 만듭니다 `AddNumbers` 매개 변수 및 반환 값의 일치 하는 `MathOperator`서명이 일치 되도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="ba04d-109">Create a procedure named `AddNumbers` with parameters and return value that match those of `MathOperator`, so that the signatures match.</span></span>  
  
     [!code-vb[VbVbalrDelegates#2](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-pass-procedures-to-another-procedure_2.vb)]  
  
3.  <span data-ttu-id="ba04d-110">라는 프로시저를 만듭니다 `SubtractNumbers` 일치 하는 서명을 사용 하 여 `MathOperator`입니다.</span><span class="sxs-lookup"><span data-stu-id="ba04d-110">Create a procedure named `SubtractNumbers` with a signature that matches `MathOperator`.</span></span>  
  
     [!code-vb[VbVbalrDelegates#3](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-pass-procedures-to-another-procedure_3.vb)]  
  
4.  <span data-ttu-id="ba04d-111">라는 프로시저를 만들어 `DelegateTest` 대리자를 매개 변수로 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="ba04d-111">Create a procedure named `DelegateTest` that takes a delegate as a parameter.</span></span>  
  
     <span data-ttu-id="ba04d-112">이 절차에 대 한 참조를 사용할 수 있습니다 `AddNumbers` 또는 `SubtractNumbers`이므로 해당 서명이 일치는 `MathOperator` 서명 합니다.</span><span class="sxs-lookup"><span data-stu-id="ba04d-112">This procedure can accept a reference to `AddNumbers` or `SubtractNumbers`, because their signatures match the `MathOperator` signature.</span></span>  
  
     [!code-vb[VbVbalrDelegates#4](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-pass-procedures-to-another-procedure_4.vb)]  
  
5.  <span data-ttu-id="ba04d-113">라는 프로시저를 만듭니다 `Test` 를 호출 하는 `DelegateTest` 에 대 한 대리자를 사용 하 여 한 번 `AddNumbers` 매개 변수로 사용 하 여 대리자를 다시 `SubtractNumbers` 매개 변수로 합니다.</span><span class="sxs-lookup"><span data-stu-id="ba04d-113">Create a procedure named `Test` that calls `DelegateTest` once with the delegate for `AddNumbers` as a parameter, and again with the delegate for `SubtractNumbers` as a parameter.</span></span>  
  
     [!code-vb[VbVbalrDelegates#5](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-pass-procedures-to-another-procedure_5.vb)]  
  
     <span data-ttu-id="ba04d-114">때 `Test` 는 호출 처음 표시 하면 `AddNumbers` 에서 작동 하 `5` 및 `3`, 8 인 합니다.</span><span class="sxs-lookup"><span data-stu-id="ba04d-114">When `Test` is called, it first displays the result of `AddNumbers` acting on `5` and `3`, which is 8.</span></span> <span data-ttu-id="ba04d-115">결과 `SubtractNumbers` 역할을 하 `9` 및 `3` 표시 되 면 6이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ba04d-115">Then the result of `SubtractNumbers` acting on `9` and `3` is displayed, which is 6.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ba04d-116">참고자료</span><span class="sxs-lookup"><span data-stu-id="ba04d-116">See also</span></span>
- [<span data-ttu-id="ba04d-117">대리자</span><span class="sxs-lookup"><span data-stu-id="ba04d-117">Delegates</span></span>](../../../../visual-basic/programming-guide/language-features/delegates/index.md)
- [<span data-ttu-id="ba04d-118">AddressOf 연산자</span><span class="sxs-lookup"><span data-stu-id="ba04d-118">AddressOf Operator</span></span>](../../../../visual-basic/language-reference/operators/addressof-operator.md)
- [<span data-ttu-id="ba04d-119">Delegate 문</span><span class="sxs-lookup"><span data-stu-id="ba04d-119">Delegate Statement</span></span>](../../../../visual-basic/language-reference/statements/delegate-statement.md)
- [<span data-ttu-id="ba04d-120">방법: 대리자 메서드 호출</span><span class="sxs-lookup"><span data-stu-id="ba04d-120">How to: Invoke a Delegate Method</span></span>](../../../../visual-basic/programming-guide/language-features/delegates/how-to-invoke-a-delegate-method.md)
