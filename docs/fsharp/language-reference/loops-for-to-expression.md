---
title: '루프: for...to 식(F#)'
description: '참조 하는 방법을 F # 하십시오... 식으로 루프 변수 값의 범위에 대해 루프를 반복에 사용 됩니다.'
ms.date: 05/16/2016
ms.openlocfilehash: 8160fd30c4f3afe8bb6b58f468802ef1c0ef32ee
ms.sourcegitcommit: 3c1c3ba79895335ff3737934e39372555ca7d6d0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/06/2018
ms.locfileid: "43800471"
---
# <a name="loops-forto-expression"></a><span data-ttu-id="0b149-103">루프: for...to 식</span><span class="sxs-lookup"><span data-stu-id="0b149-103">Loops: for...to Expression</span></span>

<span data-ttu-id="0b149-104">`for...to` 식은 루프 변수 값의 범위에 대해 루프를 반복 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0b149-104">The `for...to` expression is used to iterate in a loop over a range of values of a loop variable.</span></span>

## <a name="syntax"></a><span data-ttu-id="0b149-105">구문</span><span class="sxs-lookup"><span data-stu-id="0b149-105">Syntax</span></span>

```fsharp
for identifier = start [ to | downto ] finish do
    body-expression
```

## <a name="remarks"></a><span data-ttu-id="0b149-106">설명</span><span class="sxs-lookup"><span data-stu-id="0b149-106">Remarks</span></span>

<span data-ttu-id="0b149-107">식별자의 형식은 형식에서 유추 됩니다 합니다 *시작* 하 고 *마침* 식입니다.</span><span class="sxs-lookup"><span data-stu-id="0b149-107">The type of the identifier is inferred from the type of the *start* and *finish* expressions.</span></span> <span data-ttu-id="0b149-108">이러한 식에 대 한 형식에는 32 비트 정수 여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0b149-108">Types for these expressions must be 32-bit integers.</span></span>

<span data-ttu-id="0b149-109">하지만 식을 기술적 `for...to` 명령형 프로그래밍 언어에서 일반적인 문에 같습니다.</span><span class="sxs-lookup"><span data-stu-id="0b149-109">Although technically an expression, `for...to` is more like a traditional statement in an imperative programming language.</span></span> <span data-ttu-id="0b149-110">반환 형식은 합니다 *식 본문* 이어야 합니다 `unit`합니다.</span><span class="sxs-lookup"><span data-stu-id="0b149-110">The return type for the *body-expression* must be `unit`.</span></span> <span data-ttu-id="0b149-111">다음 예제에서는 표시의 다양 한 용도 `for...to` 식입니다.</span><span class="sxs-lookup"><span data-stu-id="0b149-111">The following examples show various uses of the `for...to` expression.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet5101.fs)]

<span data-ttu-id="0b149-112">위 코드는 다음과 같이 출력됩니다.</span><span class="sxs-lookup"><span data-stu-id="0b149-112">The output of the previous code is as follows.</span></span>

```
1 2 3 4 5 6 7 8 9 10
10 9 8 7 6 5 4 3 2 1
2 3 4 5 6 7 8 9 10 11 12 13 14 15 16 17 18
```

## <a name="see-also"></a><span data-ttu-id="0b149-113">참고자료</span><span class="sxs-lookup"><span data-stu-id="0b149-113">See also</span></span>

- [<span data-ttu-id="0b149-114">F# 언어 참조</span><span class="sxs-lookup"><span data-stu-id="0b149-114">F# Language Reference</span></span>](index.md)
- [<span data-ttu-id="0b149-115">루프: `for...in` 식</span><span class="sxs-lookup"><span data-stu-id="0b149-115">Loops: `for...in` Expression</span></span>](loops-for-in-expression.md)
- [<span data-ttu-id="0b149-116">루프: `while...do` 식</span><span class="sxs-lookup"><span data-stu-id="0b149-116">Loops: `while...do` Expression</span></span>](loops-while-do-expression.md)
