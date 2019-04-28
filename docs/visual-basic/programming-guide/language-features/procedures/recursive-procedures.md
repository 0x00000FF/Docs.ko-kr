---
title: 재귀 프로시저(Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- Visual Basic code, procedures
- procedures [Visual Basic], that call themselves
- procedures [Visual Basic], recursive
- procedures [Visual Basic], calling
- recursive procedures
- functions [Visual Basic], calling recursively
- recursion
ms.assetid: ba1d3962-b4c3-48d3-875e-96fdb4198327
ms.openlocfilehash: de9a2af9fc3cd78879b6525245727a6f52d51c63
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61791848"
---
# <a name="recursive-procedures-visual-basic"></a><span data-ttu-id="00def-102">재귀 프로시저(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="00def-102">Recursive Procedures (Visual Basic)</span></span>
<span data-ttu-id="00def-103">A *재귀* 절차는 자신을 호출 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="00def-103">A *recursive* procedure is one that calls itself.</span></span> <span data-ttu-id="00def-104">일반적으로이 Visual Basic 코드를 작성 하는 가장 효과적인 방법은 없습니다.</span><span class="sxs-lookup"><span data-stu-id="00def-104">In general, this is not the most effective way to write Visual Basic code.</span></span>  
  
 <span data-ttu-id="00def-105">다음 절차는 재귀를 사용 하 여 원래 인수로의 계승을 계산 합니다.</span><span class="sxs-lookup"><span data-stu-id="00def-105">The following procedure uses recursion to calculate the factorial of its original argument.</span></span>  
  
 [!code-vb[VbVbcnProcedures#51](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#51)]  
  
## <a name="considerations-with-recursive-procedures"></a><span data-ttu-id="00def-106">재귀 프로시저를 사용 하 여 고려 사항</span><span class="sxs-lookup"><span data-stu-id="00def-106">Considerations with Recursive Procedures</span></span>  
 <span data-ttu-id="00def-107">**제한 조건**합니다.</span><span class="sxs-lookup"><span data-stu-id="00def-107">**Limiting Conditions**.</span></span> <span data-ttu-id="00def-108">재귀를 종료할 수 있는 하나 이상의 조건에 대해 테스트 하는 재귀 프로시저를 디자인 해야 하 고 적절 한 수의 재귀 호출 내에서 이러한 조건이 충족 되는 있는 경우도 처리 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="00def-108">You must design a recursive procedure to test for at least one condition that can terminate the recursion, and you must also handle the case where no such condition is satisfied within a reasonable number of recursive calls.</span></span> <span data-ttu-id="00def-109">오류 없이 충족 될 수 있는 하나 이상의 조건 없이 프로시저 무한 루프로 실행 하는 위험 수준이 높은 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="00def-109">Without at least one condition that can be met without fail, your procedure runs a high risk of executing in an infinite loop.</span></span>  
  
 <span data-ttu-id="00def-110">**메모리 사용량**.</span><span class="sxs-lookup"><span data-stu-id="00def-110">**Memory Usage**.</span></span> <span data-ttu-id="00def-111">응용 프로그램에 제한 된 지역 변수의 공간.</span><span class="sxs-lookup"><span data-stu-id="00def-111">Your application has a limited amount of space for local variables.</span></span> <span data-ttu-id="00def-112">프로시저가 자신을 호출할 때마다 사용 공간에 많은 지역 변수의 복사본을 더 합니다.</span><span class="sxs-lookup"><span data-stu-id="00def-112">Each time a procedure calls itself, it uses more of that space for additional copies of its local variables.</span></span> <span data-ttu-id="00def-113">결과적으로 인해이 프로세스는 무기한 계속 되 면을 <xref:System.StackOverflowException> 오류입니다.</span><span class="sxs-lookup"><span data-stu-id="00def-113">If this process continues indefinitely, it eventually causes a <xref:System.StackOverflowException> error.</span></span>  
  
 <span data-ttu-id="00def-114">**효율성**-</span><span class="sxs-lookup"><span data-stu-id="00def-114">**Efficiency**.</span></span> <span data-ttu-id="00def-115">거의 항상 재귀 루프를 대체할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="00def-115">You can almost always substitute a loop for recursion.</span></span> <span data-ttu-id="00def-116">루프는 전달 인수를 추가 저장소를 초기화 하 고 값을 반환 하는 오버 헤드는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="00def-116">A loop does not have the overhead of passing arguments, initializing additional storage, and returning values.</span></span> <span data-ttu-id="00def-117">성능 재귀 호출 없이 훨씬 더 나은 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="00def-117">Your performance can be much better without recursive calls.</span></span>  
  
 <span data-ttu-id="00def-118">**상호 재귀**합니다.</span><span class="sxs-lookup"><span data-stu-id="00def-118">**Mutual Recursion**.</span></span> <span data-ttu-id="00def-119">서로 다른 두 프로시저 호출 하는 경우 성능이 매우 저하 또는 무한 루프도 알 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="00def-119">You might observe very poor performance, or even an infinite loop, if two procedures call each other.</span></span> <span data-ttu-id="00def-120">이러한 설계는 단일 재귀 프로시저와 같은 문제를 표시 하지만 발견 하 여 디버깅 하기가 더 어렵습니다.</span><span class="sxs-lookup"><span data-stu-id="00def-120">Such a design presents the same problems as a single recursive procedure, but can be harder to detect and debug.</span></span>  
  
 <span data-ttu-id="00def-121">**괄호를 사용 하 여 호출**합니다.</span><span class="sxs-lookup"><span data-stu-id="00def-121">**Calling with Parentheses**.</span></span> <span data-ttu-id="00def-122">경우는 `Function` 프로시저가 자신을 재귀적으로 호출, 인수 목록이 없는 경우에 프로시저 이름 뒤에 괄호를 따라야 합니다.</span><span class="sxs-lookup"><span data-stu-id="00def-122">When a `Function` procedure calls itself recursively, you must follow the procedure name with parentheses, even if there is no argument list.</span></span> <span data-ttu-id="00def-123">함수 이름이 사용 중이 고, 그렇지 함수의 반환 값을 나타내는 것으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="00def-123">Otherwise, the function name is taken as representing the return value of the function.</span></span>  
  
 <span data-ttu-id="00def-124">**테스트**합니다.</span><span class="sxs-lookup"><span data-stu-id="00def-124">**Testing**.</span></span> <span data-ttu-id="00def-125">재귀 프로시저를 작성 하는 경우 일부 제한 조건이 항상 충족 하는지 확인 하려면 매우 신중 하 게 테스트 해야 있습니다.</span><span class="sxs-lookup"><span data-stu-id="00def-125">If you write a recursive procedure, you should test it very carefully to make sure it always meets some limiting condition.</span></span> <span data-ttu-id="00def-126">또한 재귀 호출이 너무 많아서 인해 메모리에서 실행할 수 없음을 확인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="00def-126">You should also ensure that you cannot run out of memory due to having too many recursive calls.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="00def-127">참고자료</span><span class="sxs-lookup"><span data-stu-id="00def-127">See also</span></span>

- <xref:System.StackOverflowException>
- [<span data-ttu-id="00def-128">절차</span><span class="sxs-lookup"><span data-stu-id="00def-128">Procedures</span></span>](./index.md)
- [<span data-ttu-id="00def-129">Sub 프로시저</span><span class="sxs-lookup"><span data-stu-id="00def-129">Sub Procedures</span></span>](./sub-procedures.md)
- [<span data-ttu-id="00def-130">Function 프로시저</span><span class="sxs-lookup"><span data-stu-id="00def-130">Function Procedures</span></span>](./function-procedures.md)
- [<span data-ttu-id="00def-131">속성 프로시저</span><span class="sxs-lookup"><span data-stu-id="00def-131">Property Procedures</span></span>](./property-procedures.md)
- [<span data-ttu-id="00def-132">연산자 프로시저</span><span class="sxs-lookup"><span data-stu-id="00def-132">Operator Procedures</span></span>](./operator-procedures.md)
- [<span data-ttu-id="00def-133">프로시저 매개 변수 및 인수</span><span class="sxs-lookup"><span data-stu-id="00def-133">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)
- [<span data-ttu-id="00def-134">프로시저 오버로딩</span><span class="sxs-lookup"><span data-stu-id="00def-134">Procedure Overloading</span></span>](./procedure-overloading.md)
- [<span data-ttu-id="00def-135">프로시저 문제 해결</span><span class="sxs-lookup"><span data-stu-id="00def-135">Troubleshooting Procedures</span></span>](./troubleshooting-procedures.md)
- [<span data-ttu-id="00def-136">루프 구조</span><span class="sxs-lookup"><span data-stu-id="00def-136">Loop Structures</span></span>](../../../../visual-basic/programming-guide/language-features/control-flow/loop-structures.md)
