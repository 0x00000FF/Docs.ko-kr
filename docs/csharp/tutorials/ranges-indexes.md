---
title: 인덱스 및 범위를 사용하여 데이터 범위 탐색
description: 이 고급 자습서에서는 인덱스 및 범위를 사용하여 순차적 데이터 세트를 검사하는 데이터 탐색을 살펴봅니다.
ms.date: 04/19/2019
ms.custom: mvc
ms.openlocfilehash: d0eeadfff9732ced22e045536a88ed49cd98bbaa
ms.sourcegitcommit: a4b10e1f2a8bb4e8ff902630855474a0c4f1b37a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/19/2019
ms.locfileid: "71117833"
---
# <a name="indices-and-ranges"></a><span data-ttu-id="a229c-103">인덱스 및 범위</span><span class="sxs-lookup"><span data-stu-id="a229c-103">Indices and ranges</span></span>

<span data-ttu-id="a229c-104">범위와 인덱스는 <xref:System.Array>, <xref:System.String>, <xref:System.Span%601> 또는 <xref:System.ReadOnlySpan%601>에서 단일 요소 또는 범위에 액세스하기 위한 간결한 구문을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="a229c-104">Ranges and indices provide a succinct syntax for accessing single elements or ranges in an <xref:System.Array>, <xref:System.String>, <xref:System.Span%601>, or <xref:System.ReadOnlySpan%601>.</span></span> <span data-ttu-id="a229c-105">이러한 기능을 통해 더 간결하고 분명한 구문으로 시퀀스의 단일 요소 또는 요소 범위에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a229c-105">These features enable more concise, clear syntax to access single elements or ranges of elements in a sequence.</span></span>

<span data-ttu-id="a229c-106">이 자습서에서는 다음과 같은 작업을 수행하는 방법을 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="a229c-106">In this tutorial, you'll learn how to:</span></span>

> [!div class="checklist"]
>
> - <span data-ttu-id="a229c-107">시퀀스에서 범위에 구문을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="a229c-107">Use the syntax for ranges in a sequence.</span></span>
> - <span data-ttu-id="a229c-108">각 시퀀스의 시작 및 끝에 대한 설계 의사 결정을 이해합니다.</span><span class="sxs-lookup"><span data-stu-id="a229c-108">Understand the design decisions for the start and end of each sequence.</span></span>
> - <span data-ttu-id="a229c-109"><xref:System.Index> 및 <xref:System.Range> 형식에 대한 시나리오를 살펴봅니다.</span><span class="sxs-lookup"><span data-stu-id="a229c-109">Learn scenarios for the <xref:System.Index> and <xref:System.Range> types.</span></span>

## <a name="language-support-for-indices-and-ranges"></a><span data-ttu-id="a229c-110">인덱스 및 범위에 대한 언어 지원</span><span class="sxs-lookup"><span data-stu-id="a229c-110">Language support for indices and ranges</span></span>

<span data-ttu-id="a229c-111">이 언어 지원은 다음과 같은 두 가지 새 형식 및 두 가지 새 연산자를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="a229c-111">This language support relies on two new types and two new operators:</span></span>

- <span data-ttu-id="a229c-112"><xref:System.Index?displayProperty=nameWithType>는 인덱스를 시퀀스로 표현합니다.</span><span class="sxs-lookup"><span data-stu-id="a229c-112"><xref:System.Index?displayProperty=nameWithType> represents an index into a sequence.</span></span>
- <span data-ttu-id="a229c-113">인덱스가 시퀀스의 끝을 기준으로 하도록 지정하는 끝부터 인덱스 연산자 `^`입니다.</span><span class="sxs-lookup"><span data-stu-id="a229c-113">The index from end operator `^`, which specifies that an index is relative to the end of a sequence.</span></span>
- <span data-ttu-id="a229c-114"><xref:System.Range?displayProperty=nameWithType>는 시퀀스의 하위 범위를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="a229c-114"><xref:System.Range?displayProperty=nameWithType> represents a sub range of a sequence.</span></span>
- <span data-ttu-id="a229c-115">범위의 시작과 끝을 피연산자로 지정하는 범위 연산자 `..`입니다.</span><span class="sxs-lookup"><span data-stu-id="a229c-115">The range operator `..`, which specifies the start and end of a range as its operands.</span></span>

<span data-ttu-id="a229c-116">인덱스에 대한 규칙을 사용하여 시작하겠습니다.</span><span class="sxs-lookup"><span data-stu-id="a229c-116">Let's start with the rules for indices.</span></span> <span data-ttu-id="a229c-117">`sequence`배열을 고려합니다.</span><span class="sxs-lookup"><span data-stu-id="a229c-117">Consider an array `sequence`.</span></span> <span data-ttu-id="a229c-118">`0` 인덱스는 `sequence[0]`과 동일합니다.</span><span class="sxs-lookup"><span data-stu-id="a229c-118">The `0` index is the same as `sequence[0]`.</span></span> <span data-ttu-id="a229c-119">`^0` 인덱스는 `sequence[sequence.Length]`와 동일합니다.</span><span class="sxs-lookup"><span data-stu-id="a229c-119">The `^0` index is the same as `sequence[sequence.Length]`.</span></span> <span data-ttu-id="a229c-120">`sequence[^0]`은 `sequence[sequence.Length]`처럼 예외를 throw합니다.</span><span class="sxs-lookup"><span data-stu-id="a229c-120">Note that `sequence[^0]` does throw an exception, just as `sequence[sequence.Length]` does.</span></span> <span data-ttu-id="a229c-121">`n`이 어떤 숫자이든, 인덱스 `^n`은 `sequence[sequence.Length - n]`과 동일합니다.</span><span class="sxs-lookup"><span data-stu-id="a229c-121">For any number `n`, the index `^n` is the same as `sequence[sequence.Length - n]`.</span></span>

```csharp-interactive
string[] words = new string[]
{
                // index from start    index from end
    "The",      // 0                   ^9
    "quick",    // 1                   ^8
    "brown",    // 2                   ^7
    "fox",      // 3                   ^6
    "jumped",   // 4                   ^5
    "over",     // 5                   ^4
    "the",      // 6                   ^3
    "lazy",     // 7                   ^2
    "dog"       // 8                   ^1
};              // 9 (or words.Length) ^0
```

<span data-ttu-id="a229c-122">다음과 같이 `^1` 인덱스를 사용하여 마지막 단어를 가져올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a229c-122">You can retrieve the last word with the `^1` index.</span></span> <span data-ttu-id="a229c-123">초기화 아래에 다음 코드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="a229c-123">Add the following code below the initialization:</span></span>

[!code-csharp[LastIndex](~/samples/csharp/tutorials/RangesIndexes/IndicesAndRanges.cs#IndicesAndRanges_LastIndex)]

<span data-ttu-id="a229c-124">한 범위는 어떤 범위의 *시작* 및 *끝*을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="a229c-124">A range specifies the *start* and *end* of a range.</span></span> <span data-ttu-id="a229c-125">여러 범위는 배타적입니다. 즉, *끝*이 범위에 포함되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a229c-125">Ranges are exclusive, meaning the *end* is not included in the range.</span></span> <span data-ttu-id="a229c-126">`[0..sequence.Length]`가 전체 범위를 나타내는 것처럼 `[0..^0]` 범위는 전체 범위를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="a229c-126">The range `[0..^0]` represents the entire range, just as `[0..sequence.Length]` represents the entire range.</span></span> 

<span data-ttu-id="a229c-127">다음 코드는 “quick”, “brown”, “fox”라는 단어를 포함하는 하위 범위를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="a229c-127">The following code creates a subrange with the words "quick", "brown", and "fox".</span></span> <span data-ttu-id="a229c-128">이 하위 범위에는 `words[1]`부터 `words[3]`까지 포함되며,</span><span class="sxs-lookup"><span data-stu-id="a229c-128">It includes `words[1]` through `words[3]`.</span></span> <span data-ttu-id="a229c-129">`words[4]` 요소가 범위에 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a229c-129">The element `words[4]` isn't in the range.</span></span> <span data-ttu-id="a229c-130">다음 코드를 같은 메서드에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="a229c-130">Add the following code to the same method.</span></span> <span data-ttu-id="a229c-131">대화형 창의 맨 아래에 다음 코드를 복사하여 붙여넣습니다.</span><span class="sxs-lookup"><span data-stu-id="a229c-131">Copy and paste it at the bottom of the interactive window.</span></span>

[!code-csharp[Range](~/samples/csharp/tutorials/RangesIndexes/IndicesAndRanges.cs#IndicesAndRanges_Range)]

<span data-ttu-id="a229c-132">다음 코드는 “lazy”와 “dog”를 포함하는 하위 범위를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="a229c-132">The following code creates a subrange with "lazy" and "dog".</span></span> <span data-ttu-id="a229c-133">이 하위 범위에는 `words[^2]`과 `words[^1]`이 포함되며.</span><span class="sxs-lookup"><span data-stu-id="a229c-133">It includes `words[^2]` and `words[^1]`.</span></span> <span data-ttu-id="a229c-134">끝 인덱스 `words[^0]`는 포함되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a229c-134">The end index `words[^0]` isn't included.</span></span> <span data-ttu-id="a229c-135">다음 코드도 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="a229c-135">Add the following code as well:</span></span>

[!code-csharp[LastRange](~/samples/csharp/tutorials/RangesIndexes/IndicesAndRanges.cs#IndicesAndRanges_LastRange)]

<span data-ttu-id="a229c-136">다음 예제는 시작만, 끝만, 그리고 시작과 끝이 모두 열린 범위를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="a229c-136">The following examples create ranges that are open ended for the start, end, or both:</span></span>

[!code-csharp[PartialRange](~/samples/csharp/tutorials/RangesIndexes/IndicesAndRanges.cs#IndicesAndRanges_PartialRanges)]

<span data-ttu-id="a229c-137">범위나 인덱스를 변수로 선언할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a229c-137">You can also declare ranges or indices as variables.</span></span> <span data-ttu-id="a229c-138">그러면 이 변수를 `[` 및 `]` 문자 사이에 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a229c-138">The variable can then be used inside the `[` and `]` characters:</span></span>

[!code-csharp[IndexRangeTypes](~/samples/csharp/tutorials/RangesIndexes/IndicesAndRanges.cs#IndicesAndRanges_RangeIndexTypes)]

<span data-ttu-id="a229c-139">다음 샘플에서는 이러한 선택에 대한 여러 이유를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="a229c-139">The following sample shows many of the reasons for those choices.</span></span> <span data-ttu-id="a229c-140">`x`, `y` 및 `z`를 수정하여 다양한 조합을 시도해 봅니다.</span><span class="sxs-lookup"><span data-stu-id="a229c-140">Modify `x`, `y`, and `z` to try different combinations.</span></span> <span data-ttu-id="a229c-141">실험할 때는 올바른 조합을 위해 `x`가 `y`보다 작고 `y`가 `z`보다 작은 값을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="a229c-141">When you experiment, use values where `x` is less than `y`, and `y` is less than `z` for valid combinations.</span></span> <span data-ttu-id="a229c-142">새 메서드에 다음 코드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="a229c-142">Add the following code in a new method.</span></span> <span data-ttu-id="a229c-143">다양한 조합을 시도해 봅니다.</span><span class="sxs-lookup"><span data-stu-id="a229c-143">Try different combinations:</span></span>

[!code-csharp[SemanticsExamples](~/samples/csharp/tutorials/RangesIndexes/IndicesAndRanges.cs#IndicesAndRanges_Semantics)]

## <a name="scenarios-for-indices-and-ranges"></a><span data-ttu-id="a229c-144">인덱스 및 범위에 대한 시나리오</span><span class="sxs-lookup"><span data-stu-id="a229c-144">Scenarios for Indices and Ranges</span></span>

<span data-ttu-id="a229c-145">전체 시퀀스의 하위 범위에 대한 특정 분석을 수행할 때 범위와 인덱스를 사용하게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a229c-145">You'll often use ranges and indices when you want to perform some analysis on subrange of an entire sequence.</span></span> <span data-ttu-id="a229c-146">새 구문에서는 어떤 하위 범위가 관련되었는지 더 명확히 이해할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a229c-146">The new syntax is clearer in reading exactly what subrange is involved.</span></span> <span data-ttu-id="a229c-147">로컬 함수 `MovingAverage`는 <xref:System.Range>를 인수로 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="a229c-147">The local function `MovingAverage` takes a <xref:System.Range> as its argument.</span></span> <span data-ttu-id="a229c-148">그러면 메서드가 최솟값, 최댓값, 평균을 계산할 때 이 범위만 열거합니다.</span><span class="sxs-lookup"><span data-stu-id="a229c-148">The method then enumerates just that range when calculating the min, max, and average.</span></span> <span data-ttu-id="a229c-149">프로젝트에 다음 코드를 시도해 봅니다.</span><span class="sxs-lookup"><span data-stu-id="a229c-149">Try the following code in your project:</span></span>

[!code-csharp[MovingAverages](~/samples/csharp/tutorials/RangesIndexes/IndicesAndRanges.cs#IndicesAndRanges_MovingAverage)]

<span data-ttu-id="a229c-150">완료된 코드는 [dotnet/samples](https://github.com/dotnet/samples/tree/master/csharp/tutorials/RangesIndexes) 리포지토리에서 다운로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a229c-150">You can download the completed code from the [dotnet/samples](https://github.com/dotnet/samples/tree/master/csharp/tutorials/RangesIndexes) repository.</span></span>
