---
title: "do(C# 참조)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- do_CSharpKeyword
- do
helpviewer_keywords:
- do keyword [C#]
ms.assetid: 50725f79-9ba6-4898-aa78-6e331568a1bb
caps.latest.revision: 
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: d24078d3fb985f643fb66aa456900d03d2ff3fce
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="do-c-reference"></a><span data-ttu-id="03124-102">do(C# 참조)</span><span class="sxs-lookup"><span data-stu-id="03124-102">do (C# Reference)</span></span>
<span data-ttu-id="03124-103">`do` 문은 지정된 식이 `false`로 계산될 때까지 문 또는 문의 블록을 반복해서 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="03124-103">The `do` statement executes a statement or a block of statements repeatedly until a specified expression evaluates to `false`.</span></span> <span data-ttu-id="03124-104">루프의 본문이 단일 문으로 구성되지 않은 경우 중괄호(`{}`)로 묶어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="03124-104">The body of the loop must be enclosed in braces, `{}`, unless it consists of a single statement.</span></span> <span data-ttu-id="03124-105">이 경우 중괄호는 선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="03124-105">In that case, the braces are optional.</span></span>  
  
## <a name="example"></a><span data-ttu-id="03124-106">예제</span><span class="sxs-lookup"><span data-stu-id="03124-106">Example</span></span>  
 <span data-ttu-id="03124-107">다음 예제에서는 `x` 변수가 5보다 작은 한 `do-while` 루프 문이 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="03124-107">In the following example, the `do-while` loop statements execute as long as the variable `x` is less than 5.</span></span>  
  
 [!code-csharp[csrefKeywordsIteration#1](../../../csharp/language-reference/keywords/codesnippet/CSharp/do_1.cs)]  
  
 <span data-ttu-id="03124-108">[while](../../../csharp/language-reference/keywords/while.md) 문과 달리 `do-while` 루프는 조건식이 계산되기 전에 한 번 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="03124-108">Unlike the [while](../../../csharp/language-reference/keywords/while.md) statement, a `do-while` loop is executed one time before the conditional expression is evaluated.</span></span>  
  
 <span data-ttu-id="03124-109">`do-while` 블록의 어느 지점에서나 [break](../../../csharp/language-reference/keywords/break.md) 문을 사용하여 루프를 중단할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="03124-109">At any point in the `do-while` block, you can break out of the loop using the [break](../../../csharp/language-reference/keywords/break.md) statement.</span></span> <span data-ttu-id="03124-110">[continue](../../../csharp/language-reference/keywords/continue.md) 문을 사용하여 `while` 식 계산 문을 직접 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="03124-110">You can step directly to the `while` expression evaluation statement by using the [continue](../../../csharp/language-reference/keywords/continue.md) statement.</span></span> <span data-ttu-id="03124-111">`while` 식이 true로 계산될 경우 루프의 첫 번째 문에서 계속 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="03124-111">If the `while` expression evaluates to true, execution continues at the first statement in the loop.</span></span> <span data-ttu-id="03124-112">식이 false로 계산될 경우 `do-while` 루프 다음의 첫 번째 문에서 계속 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="03124-112">If the expression evaluates to false, execution continues at the first statement after the `do-while` loop.</span></span>  
  
 <span data-ttu-id="03124-113">또한 `do-while` 루프는 [goto](../../../csharp/language-reference/keywords/goto.md), [return](../../../csharp/language-reference/keywords/return.md) 또는 [throw](../../../csharp/language-reference/keywords/throw.md) 문으로 종료할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="03124-113">A `do-while` loop can also be exited by the [goto](../../../csharp/language-reference/keywords/goto.md), [return](../../../csharp/language-reference/keywords/return.md), or [throw](../../../csharp/language-reference/keywords/throw.md) statements.</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="03124-114">C# 언어 사양</span><span class="sxs-lookup"><span data-stu-id="03124-114">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="03124-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="03124-115">See Also</span></span>  
 [<span data-ttu-id="03124-116">C# 참조</span><span class="sxs-lookup"><span data-stu-id="03124-116">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="03124-117">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="03124-117">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="03124-118">C# 키워드</span><span class="sxs-lookup"><span data-stu-id="03124-118">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
 [<span data-ttu-id="03124-119">do-while 문(C++)</span><span class="sxs-lookup"><span data-stu-id="03124-119">do-while Statement (C++)</span></span>](/cpp/cpp/do-while-statement-cpp)  
 [<span data-ttu-id="03124-120">반복 문</span><span class="sxs-lookup"><span data-stu-id="03124-120">Iteration Statements</span></span>](../../../csharp/language-reference/keywords/iteration-statements.md)
