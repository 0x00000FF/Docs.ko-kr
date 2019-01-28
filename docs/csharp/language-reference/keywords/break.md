---
title: break 문 - C# 참조
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- break
- break_CSharpKeyword
helpviewer_keywords:
- break keyword [C#]
ms.assetid: be2571ed-efb0-4965-b122-81e5b09db0b9
ms.openlocfilehash: 18be5171329dd43c419e977a1799e2e72c32404d
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54727575"
---
# <a name="break-c-reference"></a><span data-ttu-id="66191-102">break(C# 참조)</span><span class="sxs-lookup"><span data-stu-id="66191-102">break (C# Reference)</span></span>

<span data-ttu-id="66191-103">`break` 문은 배치된 지점에서 가장 가까운 바깥쪽 루프 또는 [switch](../../../csharp/language-reference/keywords/switch.md) 문을 종료합니다.</span><span class="sxs-lookup"><span data-stu-id="66191-103">The `break` statement terminates the closest enclosing loop or [switch](../../../csharp/language-reference/keywords/switch.md) statement in which it appears.</span></span> <span data-ttu-id="66191-104">제어는 종료된 문 뒤의 문으로 전달됩니다(있는 경우).</span><span class="sxs-lookup"><span data-stu-id="66191-104">Control is passed to the statement that follows the terminated statement, if any.</span></span>

## <a name="example"></a><span data-ttu-id="66191-105">예제</span><span class="sxs-lookup"><span data-stu-id="66191-105">Example</span></span>

<span data-ttu-id="66191-106">이 예제의 조건문에는 1부터 100까지 개수를 계산하는 카운터가 포함되지만 `break` 문은 4회 계산 후에 루프를 종료합니다.</span><span class="sxs-lookup"><span data-stu-id="66191-106">In this example, the conditional statement contains a counter that is supposed to count from 1 to 100; however, the `break` statement terminates the loop after 4 counts.</span></span>

[!code-csharp[csrefKeywordsJump#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsJump/CS/csrefKeywordsJump.cs#1)]

## <a name="example"></a><span data-ttu-id="66191-107">예제</span><span class="sxs-lookup"><span data-stu-id="66191-107">Example</span></span>

<span data-ttu-id="66191-108">이 예제에서 `break` 문은 내부 중첩 루프를 중단하고 제어를 외부 루프에 반환하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="66191-108">In this example, the `break` statement is used to break out of an inner nested loop, and return control to the outer loop.</span></span>

[!code-csharp[csrefKeywordsJump#7](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsJump/CS/csrefKeywordsJump.cs#7)]

## <a name="example"></a><span data-ttu-id="66191-109">예제</span><span class="sxs-lookup"><span data-stu-id="66191-109">Example</span></span>

<span data-ttu-id="66191-110">이 예제에서는 [switch](../../../csharp/language-reference/keywords/switch.md) 문에서 `break`의 사용을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="66191-110">This example demonstrates the use of `break` in a [switch](../../../csharp/language-reference/keywords/switch.md) statement.</span></span>

[!code-csharp[csrefKeywordsJump#2](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsJump/CS/csrefKeywordsJump.cs#2)]

<span data-ttu-id="66191-111">`4`를 입력하면 다음과 같이 출력됩니다.</span><span class="sxs-lookup"><span data-stu-id="66191-111">If you entered `4`, the output would be:</span></span>

```console
Enter your selection (1, 2, or 3): 4
Sorry, invalid selection.
```

## <a name="c-language-specification"></a><span data-ttu-id="66191-112">C# 언어 사양</span><span class="sxs-lookup"><span data-stu-id="66191-112">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="66191-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="66191-113">See also</span></span>

- [<span data-ttu-id="66191-114">C# 참조</span><span class="sxs-lookup"><span data-stu-id="66191-114">C# Reference</span></span>](../../../csharp/language-reference/index.md)
- [<span data-ttu-id="66191-115">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="66191-115">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)
- [<span data-ttu-id="66191-116">C# 키워드</span><span class="sxs-lookup"><span data-stu-id="66191-116">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)
- [<span data-ttu-id="66191-117">switch</span><span class="sxs-lookup"><span data-stu-id="66191-117">switch</span></span>](../../../csharp/language-reference/keywords/switch.md)
- [<span data-ttu-id="66191-118">점프 문</span><span class="sxs-lookup"><span data-stu-id="66191-118">Jump Statements</span></span>](../../../csharp/language-reference/keywords/jump-statements.md)
- [<span data-ttu-id="66191-119">반복 문</span><span class="sxs-lookup"><span data-stu-id="66191-119">Iteration Statements</span></span>](../../../csharp/language-reference/keywords/iteration-statements.md)
