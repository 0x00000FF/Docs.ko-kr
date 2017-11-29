---
title: "람다 식: fun 키워드(F#)"
description: "F # 'fun' 키워드를 사용 하 여 익명 함수는 람다 식을 정의 하는 방법에 알아봅니다."
keywords: "visual f#, f#, 함수형 프로그래밍"
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: e5d3565c-d7cc-433f-a619-886ed92523a7
ms.openlocfilehash: 09f1c1787bbb4b86ec40f9e973e08104919631aa
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="lambda-expressions-the-fun-keyword-f"></a><span data-ttu-id="d8eb4-104">람다 식: fun 키워드(F#)</span><span class="sxs-lookup"><span data-stu-id="d8eb4-104">Lambda Expressions: The fun Keyword (F#)</span></span>

<span data-ttu-id="d8eb4-105">`fun` 키워드를 사용 하는 람다 식, 즉, 익명 함수를 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="d8eb4-105">The `fun` keyword is used to define a lambda expression, that is, an anonymous function.</span></span>


## <a name="syntax"></a><span data-ttu-id="d8eb4-106">구문</span><span class="sxs-lookup"><span data-stu-id="d8eb4-106">Syntax</span></span>

```fsharp
fun parameter-list -> expression
```

## <a name="remarks"></a><span data-ttu-id="d8eb4-107">설명</span><span class="sxs-lookup"><span data-stu-id="d8eb4-107">Remarks</span></span>
<span data-ttu-id="d8eb4-108">*매개 변수 목록* 일반적으로 이름 및 필요에 따라 유형의 매개 변수 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="d8eb4-108">The *parameter-list* typically consists of names and, optionally, types of parameters.</span></span> <span data-ttu-id="d8eb4-109">보다 일반적으로 *매개 변수 목록* F # 패턴 구성 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d8eb4-109">More generally, the *parameter-list* can be composed of any F# patterns.</span></span> <span data-ttu-id="d8eb4-110">가능한 패턴의 전체 목록을 참조 하십시오. [패턴 일치](../pattern-matching.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="d8eb4-110">For a full list of possible patterns, see [Pattern Matching](../pattern-matching.md).</span></span> <span data-ttu-id="d8eb4-111">올바른 매개 변수 목록에는 다음 예제에서는 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="d8eb4-111">Lists of valid parameters include the following examples.</span></span>

```fsharp
// Lambda expressions with parameter lists.
fun a b c -> ...
fun (a: int) b c -> ...
fun (a : int) (b : string) (c:float) -> ...

// A lambda expression with a tuple pattern.
fun (a, b) -> …

// A lambda expression with a list pattern.
fun head :: tail -> …
```

<span data-ttu-id="d8eb4-112">*식* 마지막 식의 반환 값을 생성 하는 함수 본문입니다.</span><span class="sxs-lookup"><span data-stu-id="d8eb4-112">The *expression* is the body of the function, the last expression of which generates a return value.</span></span> <span data-ttu-id="d8eb4-113">유효한 람다 식의 예는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="d8eb4-113">Examples of valid lambda expressions include the following:</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet301.fs)]
    
## <a name="using-lambda-expressions"></a><span data-ttu-id="d8eb4-114">람다 식 사용</span><span class="sxs-lookup"><span data-stu-id="d8eb4-114">Using Lambda Expressions</span></span>
<span data-ttu-id="d8eb4-115">람다 식 목록이 나 다른 컬렉션에 대 한 작업을 수행 하 고 함수를 정의 하는 추가 작업을 차단 하려면 하려는 경우 특히 유용 합니다.</span><span class="sxs-lookup"><span data-stu-id="d8eb4-115">Lambda expressions are especially useful when you want to perform operations on a list or other collection and want to avoid the extra work of defining a function.</span></span> <span data-ttu-id="d8eb4-116">여러 F # 라이브러리 함수를 인수로 함수 값 걸리며, 이러한 경우에는 람다 식을 사용 하 여 특히 편리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d8eb4-116">Many F# library functions take function values as arguments, and it can be especially convenient to use a lambda expression in those cases.</span></span> <span data-ttu-id="d8eb4-117">다음 코드에는 목록의 요소에는 람다 식을 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d8eb4-117">The following code applies a lambda expression to elements of a list.</span></span> <span data-ttu-id="d8eb4-118">이 경우에 익명 함수 목록의 모든 요소에 1을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="d8eb4-118">In this case, the anonymous function adds 1 to every element of a list.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet302.fs)]
    
## <a name="see-also"></a><span data-ttu-id="d8eb4-119">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d8eb4-119">See Also</span></span>
[<span data-ttu-id="d8eb4-120">함수</span><span class="sxs-lookup"><span data-stu-id="d8eb4-120">Functions</span></span>](index.md)
