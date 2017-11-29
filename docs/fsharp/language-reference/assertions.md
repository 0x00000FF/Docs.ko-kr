---
title: "어설션(F#)"
description: "F # 프로그래밍 언어에서 식 테스트에 대 한 디버깅 기능으로 'assert' 식을 사용 하는 방법에 알아봅니다."
keywords: "visual f#, f#, 함수형 프로그래밍"
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: 2badaad7-f086-47e7-99c1-91f35117da83
ms.openlocfilehash: 56891769602afaa765ebfe7e7822a179c7a22968
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="assertions"></a><span data-ttu-id="5824d-104">어설션</span><span class="sxs-lookup"><span data-stu-id="5824d-104">Assertions</span></span>

<span data-ttu-id="5824d-105">`assert` 식은 식을 테스트 하는 데 사용할 수 있는 디버깅 기능이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5824d-105">The `assert` expression is a debugging feature that you can use to test an expression.</span></span> <span data-ttu-id="5824d-106">디버그 모드에서 실패 시 어설션에서 시스템 오류 대화 상자를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="5824d-106">Upon failure in Debug mode, an assertion generates a system error dialog box.</span></span>

## <a name="syntax"></a><span data-ttu-id="5824d-107">구문</span><span class="sxs-lookup"><span data-stu-id="5824d-107">Syntax</span></span>

```fsharp
assert condition
```

## <a name="remarks"></a><span data-ttu-id="5824d-108">설명</span><span class="sxs-lookup"><span data-stu-id="5824d-108">Remarks</span></span>

<span data-ttu-id="5824d-109">`assert` 식에는 형식이 `bool -> unit`합니다.</span><span class="sxs-lookup"><span data-stu-id="5824d-109">The `assert` expression has type `bool -> unit`.</span></span>

<span data-ttu-id="5824d-110">위 구문에서 *조건* 테스트할 하는 부울 식을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="5824d-110">In the previous syntax, *condition* represents a Boolean expression that is to be tested.</span></span> <span data-ttu-id="5824d-111">식이 계산 되는 경우 `true`, 실행이 계속 영향을 주지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5824d-111">If the expression evaluates to `true`, execution continues unaffected.</span></span> <span data-ttu-id="5824d-112">로 평가 되 면 `false`, 시스템 오류 대화 상자가 열립니다.</span><span class="sxs-lookup"><span data-stu-id="5824d-112">If it evaluates to `false`, a system error dialog box is generated.</span></span> <span data-ttu-id="5824d-113">오류 대화 상자에 문자열을 포함 하는 캡션을 **어설션 오류**합니다.</span><span class="sxs-lookup"><span data-stu-id="5824d-113">The error dialog box has a caption that contains the string **Assertion Failed**.</span></span> <span data-ttu-id="5824d-114">대화 상자에 어설션 오류가 발생 한을 나타내는 스택 추적을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="5824d-114">The dialog box contains a stack trace that indicates where the assertion failure occurred.</span></span>

<span data-ttu-id="5824d-115">디버그 모드에서 컴파일할 때에 사용할 수는 어설션 검사 즉, 경우 상수 `DEBUG` 정의 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5824d-115">Assertion checking is enabled only when you compile in Debug mode; that is, if the constant `DEBUG` is defined.</span></span> <span data-ttu-id="5824d-116">기본적으로 프로젝트 시스템에서의 `DEBUG` 상수 릴리스 구성에 없습니다. 디버그 구성에서 정의 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5824d-116">In the project system, by default, the `DEBUG` constant is defined in the Debug configuration but not in the Release configuration.</span></span>

<span data-ttu-id="5824d-117">F # 예외 처리를 사용 하 여 어설션 실패 오류를 낼 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="5824d-117">The assertion failure error cannot be caught by using F# exception handling.</span></span>

>[!NOTE]
<span data-ttu-id="5824d-118">`assert` 함수는 <xref:System.Diagnostics.Debug.Assert*?displayProperty=nameWithType>합니다.</span><span class="sxs-lookup"><span data-stu-id="5824d-118">The `assert` function resolves to <xref:System.Diagnostics.Debug.Assert*?displayProperty=nameWithType>.</span></span>

## <a name="example"></a><span data-ttu-id="5824d-119">예제</span><span class="sxs-lookup"><span data-stu-id="5824d-119">Example</span></span>

<span data-ttu-id="5824d-120">다음 코드 예제에서는 `assert` 식입니다.</span><span class="sxs-lookup"><span data-stu-id="5824d-120">The following code example illustrates the use of the `assert` expression.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet5401.fs)]
    
## <a name="see-also"></a><span data-ttu-id="5824d-121">참고 항목</span><span class="sxs-lookup"><span data-stu-id="5824d-121">See Also</span></span>

[<span data-ttu-id="5824d-122">F# 언어 참조</span><span class="sxs-lookup"><span data-stu-id="5824d-122">F# Language Reference</span></span>](index.md)
