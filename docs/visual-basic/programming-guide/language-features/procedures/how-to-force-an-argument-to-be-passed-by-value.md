---
title: '방법: (Visual Basic) 값으로 전달 될 인수가 설정'
ms.date: 07/20/2015
helpviewer_keywords:
- procedures [Visual Basic], arguments
- procedures [Visual Basic], parameters
- procedure arguments
- Visual Basic code, procedures
- arguments [Visual Basic], ByVal
- arguments [Visual Basic], passing by value
- procedure parameters
- procedures [Visual Basic], calling
- arguments [Visual Basic], in parentheses
- procedure arguments [Visual Basic], in parentheses
- arguments [Visual Basic], changing value
ms.assetid: 77b4f2d2-1055-4c2f-a521-874d1db86946
ms.openlocfilehash: 7bd78772b35e3f336f49c1d39b5f56a3a2076c30
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/28/2019
ms.locfileid: "56970287"
---
# <a name="how-to-force-an-argument-to-be-passed-by-value-visual-basic"></a><span data-ttu-id="ffafd-102">방법: (Visual Basic) 값으로 전달 될 인수가 설정</span><span class="sxs-lookup"><span data-stu-id="ffafd-102">How to: Force an Argument to Be Passed by Value (Visual Basic)</span></span>
<span data-ttu-id="ffafd-103">프로시저 선언 전달 메커니즘을 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="ffafd-103">The procedure declaration determines the passing mechanism.</span></span> <span data-ttu-id="ffafd-104">매개 변수 선언 되 면 [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md), Visual Basic는 해당 인수가 참조로 전달 하려면 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="ffafd-104">If a parameter is declared [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md), Visual Basic expects to pass the corresponding argument by reference.</span></span> <span data-ttu-id="ffafd-105">이렇게 하면 인수의 기반이 되는 호출 코드에서 프로그래밍 요소의 값을 변경 하는 절차입니다.</span><span class="sxs-lookup"><span data-stu-id="ffafd-105">This allows the procedure to change the value of the programming element underlying the argument in the calling code.</span></span> <span data-ttu-id="ffafd-106">이러한 변경에 대 한 내부 요소를 보호 하려는 경우 재정의할 수 있습니다는 `ByRef` 인수 이름을 괄호로 묶어 전달 메커니즘 프로시저에서 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="ffafd-106">If you wish to protect the underlying element against such change, you can override the `ByRef` passing mechanism in the procedure call by enclosing the argument name in parentheses.</span></span> <span data-ttu-id="ffafd-107">이 괄호는 호출의 인수 목록을 묶는 괄호는 별개입니다.</span><span class="sxs-lookup"><span data-stu-id="ffafd-107">These parentheses are in addition to the parentheses enclosing the argument list in the call.</span></span>  
  
 <span data-ttu-id="ffafd-108">호출 코드를 재정의할 수 없습니다는 [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md) 메커니즘입니다.</span><span class="sxs-lookup"><span data-stu-id="ffafd-108">The calling code cannot override a [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md) mechanism.</span></span>  
  
### <a name="to-force-an-argument-to-be-passed-by-value"></a><span data-ttu-id="ffafd-109">인수가 값으로 전달 되도록 설정 하려면</span><span class="sxs-lookup"><span data-stu-id="ffafd-109">To force an argument to be passed by value</span></span>  
  
-   <span data-ttu-id="ffafd-110">해당 매개 변수가 선언 된 경우 `ByVal` 절차에서는 않아도 모든 추가 단계를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="ffafd-110">If the corresponding parameter is declared `ByVal` in the procedure, you do not need to take any additional steps.</span></span> <span data-ttu-id="ffafd-111">Visual Basic은 이미 인수를 값별로 전달 하려면 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="ffafd-111">Visual Basic already expects to pass the argument by value.</span></span>  
  
-   <span data-ttu-id="ffafd-112">해당 매개 변수가 선언 된 경우 `ByRef` 절차에서는 프로시저 호출에서 괄호 안에 인수를 묶습니다.</span><span class="sxs-lookup"><span data-stu-id="ffafd-112">If the corresponding parameter is declared `ByRef` in the procedure, enclose the argument in parentheses in the procedure call.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ffafd-113">예제</span><span class="sxs-lookup"><span data-stu-id="ffafd-113">Example</span></span>  
 <span data-ttu-id="ffafd-114">다음 예제에서는 재정의 `ByRef` 매개 변수를 선언 합니다.</span><span class="sxs-lookup"><span data-stu-id="ffafd-114">The following example overrides a `ByRef` parameter declaration.</span></span> <span data-ttu-id="ffafd-115">인하도록 강제 하는 호출에서 `ByVal`를 중첩 괄호 유의 합니다.</span><span class="sxs-lookup"><span data-stu-id="ffafd-115">In the call that forces `ByVal`, note the two levels of parentheses.</span></span>  
  
 [!code-vb[VbVbcnProcedures#39](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#39)]  
  
 [!code-vb[VbVbcnProcedures#40](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#40)]  
  
 <span data-ttu-id="ffafd-116">때 `str` 인수 목록에 추가 괄호로 묶인 합니다 `setNewString` 프로시저가 호출 코드에서 해당 값을 변경할 수 없습니다 및 `MsgBox` "바꿀 수 없습니다 byval로 전달 하는 경우"를 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="ffafd-116">When `str` is enclosed in extra parentheses within the argument list, the `setNewString` procedure cannot change its value in the calling code, and `MsgBox` displays "Cannot be replaced if passed ByVal".</span></span> <span data-ttu-id="ffafd-117">때 `str` 묶여 있지 않은 추가 괄호 안의 프로시저를 변경할 수 및 `MsgBox` "inString 인수에 대 한 새 값입니다."를 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="ffafd-117">When `str` is not enclosed in extra parentheses, the procedure can change it, and `MsgBox` displays "This is a new value for the inString argument."</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="ffafd-118">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="ffafd-118">Compiling the Code</span></span>  
 <span data-ttu-id="ffafd-119">참조로 변수를 전달 하는 경우 사용 해야는 `ByRef` 키워드가이 메커니즘을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="ffafd-119">When you pass a variable by reference, you must use the `ByRef` keyword to specify this mechanism.</span></span>  
  
 <span data-ttu-id="ffafd-120">Visual Basic의 기본값인 값으로 인수 전달 합니다.</span><span class="sxs-lookup"><span data-stu-id="ffafd-120">The default in Visual Basic is to pass arguments by value.</span></span> <span data-ttu-id="ffafd-121">그러나는 것이 좋은 프로그래밍 방법 중 하나를 포함 하는 [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md) 또는 [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md) 키워드 선언 된 모든 매개 변수를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="ffafd-121">However, it is good programming practice to include either the [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md) or [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md) keyword with every declared parameter.</span></span> <span data-ttu-id="ffafd-122">이렇게 하면 코드를 쉽게 읽을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ffafd-122">This makes your code easier to read.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="ffafd-123">강력한 프로그래밍</span><span class="sxs-lookup"><span data-stu-id="ffafd-123">Robust Programming</span></span>  
 <span data-ttu-id="ffafd-124">프로시저 매개 변수를 선언 하는 경우 [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md)를 올바르게 실행 되는 코드의 호출 코드의 내부 요소를 변경할 수 있는지에 따라 달라질 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ffafd-124">If a procedure declares a parameter [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md), the correct execution of the code might depend on being able to change the underlying element in the calling code.</span></span> <span data-ttu-id="ffafd-125">호출 코드에서 인수를 괄호로 묶어이 호출 하는 메커니즘을 재정의 하거나 수정할 수 없는 인수를 전달 하는 경우 프로시저는 내부 요소를 변경할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ffafd-125">If the calling code overrides this calling mechanism by enclosing the argument in parentheses, or if it passes a nonmodifiable argument, the procedure cannot change the underlying element.</span></span> <span data-ttu-id="ffafd-126">이 호출 코드에서 예기치 않은 결과가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ffafd-126">This might produce unexpected results in the calling code.</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="ffafd-127">.NET Framework 보안</span><span class="sxs-lookup"><span data-stu-id="ffafd-127">.NET Framework Security</span></span>  
 <span data-ttu-id="ffafd-128">호출 코드에서 인수를 기본 값을 변경 하는 절차를 허용할 위험할은 항상 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ffafd-128">There is always a potential risk in allowing a procedure to change the value underlying an argument in the calling code.</span></span> <span data-ttu-id="ffafd-129">원하는이 값이 변경 되 고 사용 하기 전에 유효성을 검사할 준비가 되어 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="ffafd-129">Make sure you expect this value to be changed, and be prepared to check it for validity before using it.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ffafd-130">참고자료</span><span class="sxs-lookup"><span data-stu-id="ffafd-130">See also</span></span>
- [<span data-ttu-id="ffafd-131">절차</span><span class="sxs-lookup"><span data-stu-id="ffafd-131">Procedures</span></span>](./index.md)
- [<span data-ttu-id="ffafd-132">프로시저 매개 변수 및 인수</span><span class="sxs-lookup"><span data-stu-id="ffafd-132">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)
- [<span data-ttu-id="ffafd-133">방법: 프로시저에 인수 전달</span><span class="sxs-lookup"><span data-stu-id="ffafd-133">How to: Pass Arguments to a Procedure</span></span>](./how-to-pass-arguments-to-a-procedure.md)
- [<span data-ttu-id="ffafd-134">값 또는 참조로 인수 전달</span><span class="sxs-lookup"><span data-stu-id="ffafd-134">Passing Arguments by Value and by Reference</span></span>](./passing-arguments-by-value-and-by-reference.md)
- [<span data-ttu-id="ffafd-135">수정할 수 있는 인수와 수정할 수 없는 인수 사이의 차이점</span><span class="sxs-lookup"><span data-stu-id="ffafd-135">Differences Between Modifiable and Nonmodifiable Arguments</span></span>](./differences-between-modifiable-and-nonmodifiable-arguments.md)
- [<span data-ttu-id="ffafd-136">인수를 값으로 전달할 때와 참조로 전달할 때의 차이점</span><span class="sxs-lookup"><span data-stu-id="ffafd-136">Differences Between Passing an Argument By Value and By Reference</span></span>](./differences-between-passing-an-argument-by-value-and-by-reference.md)
- [<span data-ttu-id="ffafd-137">방법: 프로시저 인수의 값 변경</span><span class="sxs-lookup"><span data-stu-id="ffafd-137">How to: Change the Value of a Procedure Argument</span></span>](./how-to-change-the-value-of-a-procedure-argument.md)
- [<span data-ttu-id="ffafd-138">방법: 값 변경에 대해 프로시저 인수 보호</span><span class="sxs-lookup"><span data-stu-id="ffafd-138">How to: Protect a Procedure Argument Against Value Changes</span></span>](./how-to-protect-a-procedure-argument-against-value-changes.md)
- [<span data-ttu-id="ffafd-139">위치 및 이름으로 인수 전달</span><span class="sxs-lookup"><span data-stu-id="ffafd-139">Passing Arguments by Position and by Name</span></span>](./passing-arguments-by-position-and-by-name.md)
- [<span data-ttu-id="ffafd-140">Value Types and Reference Types</span><span class="sxs-lookup"><span data-stu-id="ffafd-140">Value Types and Reference Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)
