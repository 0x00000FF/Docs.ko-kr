---
title: C# 8.0의 새로운 기능 - C# 가이드
description: C# 8.0의 새로운 기능을 살펴봅니다. 이 문서는 미리 보기 2가 반영된 최신 내용을 담고 있습니다.
ms.date: 02/12/2019
ms.openlocfilehash: 874420775215502ebdacb8420b3fe0e027d6660f
ms.sourcegitcommit: 8f95d3a37e591963ebbb9af6e90686fd5f3b8707
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/23/2019
ms.locfileid: "56747624"
---
# <a name="whats-new-in-c-80"></a><span data-ttu-id="6c331-104">C# 8.0의 새로운 기능</span><span class="sxs-lookup"><span data-stu-id="6c331-104">What's new in C# 8.0</span></span>

<span data-ttu-id="6c331-105">C# 언어에는 여러 개선된 기능이 포함되어 있습니다. 이러한 기능은 미리 보기 2에서 직접 사용해 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6c331-105">There are many enhancements to the C# language that you can try out already with preview 2.</span></span> <span data-ttu-id="6c331-106">미리 보기 2에 추가된 새로운 기능은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="6c331-106">The new features added in preview 2 are:</span></span>

- <span data-ttu-id="6c331-107">[패턴 일치 개선 사항](#more-patterns-in-more-places):</span><span class="sxs-lookup"><span data-stu-id="6c331-107">[Pattern matching enhancements](#more-patterns-in-more-places):</span></span>
  * [<span data-ttu-id="6c331-108">Switch 식</span><span class="sxs-lookup"><span data-stu-id="6c331-108">Switch expressions</span></span>](#switch-expressions)
  * [<span data-ttu-id="6c331-109">속성 패턴</span><span class="sxs-lookup"><span data-stu-id="6c331-109">Property patterns</span></span>](#property-patterns)
  * [<span data-ttu-id="6c331-110">튜플 패턴</span><span class="sxs-lookup"><span data-stu-id="6c331-110">Tuple patterns</span></span>](#tuple-patterns)
  * [<span data-ttu-id="6c331-111">위치 패턴</span><span class="sxs-lookup"><span data-stu-id="6c331-111">Positional patterns</span></span>](#positional-patterns)
- [<span data-ttu-id="6c331-112">using 선언</span><span class="sxs-lookup"><span data-stu-id="6c331-112">Using declarations</span></span>](#using-declarations)
- [<span data-ttu-id="6c331-113">정적 로컬 함수</span><span class="sxs-lookup"><span data-stu-id="6c331-113">Static local functions</span></span>](#static-local-functions)
- [<span data-ttu-id="6c331-114">삭제 가능한 ref struct</span><span class="sxs-lookup"><span data-stu-id="6c331-114">Disposable ref structs</span></span>](#disposable-ref-structs)

<span data-ttu-id="6c331-115">다음은 C# 8.0 미리 보기 1부터 적용된 언어 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="6c331-115">The following language features first appeared in C# 8.0 preview 1:</span></span>

- [<span data-ttu-id="6c331-116">nullable 참조 형식</span><span class="sxs-lookup"><span data-stu-id="6c331-116">Nullable reference types</span></span>](#nullable-reference-types)
- [<span data-ttu-id="6c331-117">비동기 스트림</span><span class="sxs-lookup"><span data-stu-id="6c331-117">Asynchronous streams</span></span>](#asynchronous-streams)
- [<span data-ttu-id="6c331-118">인덱스 및 범위</span><span class="sxs-lookup"><span data-stu-id="6c331-118">Indices and ranges</span></span>](#indices-and-ranges)

> [!NOTE]
> <span data-ttu-id="6c331-119">이 문서는 C# 8.0 미리 보기 2를 반영하여 업데이트되었습니다.</span><span class="sxs-lookup"><span data-stu-id="6c331-119">This article was last updated for C# 8.0 preview 2.</span></span>

<span data-ttu-id="6c331-120">이 문서의 나머지 부분에서는 이러한 기능에 대해 간략하게 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="6c331-120">The remainder of this article briefly describes these features.</span></span> <span data-ttu-id="6c331-121">심화 문서가 공개되면 해당 자습서에 대한 링크 및 개요가 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="6c331-121">Where in-depth articles are available, links to those tutorials and overviews are provided.</span></span>

## <a name="more-patterns-in-more-places"></a><span data-ttu-id="6c331-122">더 많은 곳에서 더 많은 패턴 사용</span><span class="sxs-lookup"><span data-stu-id="6c331-122">More patterns in more places</span></span>

<span data-ttu-id="6c331-123">**패턴 일치**는 관련이 있으나 유형이 다른 데이터에서 셰이프 종속 기능을 사용할 수 있도록 지원하는 도구를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="6c331-123">**Pattern matching** gives tools to provide shape-dependent functionality across related but different kinds of data.</span></span> <span data-ttu-id="6c331-124">C# 7.0부터 [`is`](../language-reference/keywords/is.md) 식과 [`switch`](../language-reference/keywords/switch.md) 문을 사용하는 형식 패턴 및 상수 패턴을 위한 구문이 추가되었습니다.</span><span class="sxs-lookup"><span data-stu-id="6c331-124">C# 7.0 introduced syntax for type patterns and constant patterns by using the [`is`](../language-reference/keywords/is.md) expression and the [`switch`](../language-reference/keywords/switch.md) statement.</span></span> <span data-ttu-id="6c331-125">이 기능은 데이터와 기능을 각각 별도로 구분하는 프로그래밍 패러다임을 지원하기 위한 조심스러운 첫 번째 단계입니다.</span><span class="sxs-lookup"><span data-stu-id="6c331-125">These features represented the first tentative steps toward supporting programming paradigms where data and functionality live apart.</span></span> <span data-ttu-id="6c331-126">업계에서 마이크로 서비스와 기타 클라우드 기반 아키텍처를 도입하는 사례가 늘어남에 따라 다른 언어 도구에 대한 요구가 높아졌습니다.</span><span class="sxs-lookup"><span data-stu-id="6c331-126">As the industry moves toward more microservices and other cloud-based architectures, other language tools are needed.</span></span>

<span data-ttu-id="6c331-127">C# 8.0은 코드의 더 많은 곳에서 더 많은 패턴 식을 사용할 수 있도록 이 용어를 확대합니다.</span><span class="sxs-lookup"><span data-stu-id="6c331-127">C# 8.0 expands this vocabulary so you can use more pattern expressions in more places in your code.</span></span> <span data-ttu-id="6c331-128">데이터와 기능을 각각 별도로 구분하는 경우 이러한 기능을 고려해 보시기 바랍니다.</span><span class="sxs-lookup"><span data-stu-id="6c331-128">Consider these features when your data and functionality are separate.</span></span> <span data-ttu-id="6c331-129">알고리즘이 개체의 런타임 형식이 아닌 다른 요소에 종속되는 경우 패턴 일치를 고려해 보시기 바랍니다.</span><span class="sxs-lookup"><span data-stu-id="6c331-129">Consider pattern matching when your algorithms depend on a fact other than the runtime type of an object.</span></span> <span data-ttu-id="6c331-130">이러한 기법은 디자인을 표현할 추가적인 방법을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="6c331-130">These techniques provide another way to express designs.</span></span>

<span data-ttu-id="6c331-131">C# 8.0에는 더 많은 곳에서 패턴을 사용할 수 있도록 지원하는 기능에 더해 **재귀 패턴**도 추가되었습니다.</span><span class="sxs-lookup"><span data-stu-id="6c331-131">In addition to new patterns in new places, C# 8.0 adds **recursive patterns**.</span></span> <span data-ttu-id="6c331-132">패턴 식의 결과는 식입니다.</span><span class="sxs-lookup"><span data-stu-id="6c331-132">The result of any pattern expression is an expression.</span></span> <span data-ttu-id="6c331-133">재귀 패턴은 다른 패턴 식의 출력에 적용된 패턴 식입니다.</span><span class="sxs-lookup"><span data-stu-id="6c331-133">A recursive pattern is simply a pattern expression applied to the output of another pattern expression.</span></span>

### <a name="switch-expressions"></a><span data-ttu-id="6c331-134">Switch 식</span><span class="sxs-lookup"><span data-stu-id="6c331-134">switch expressions</span></span>

<span data-ttu-id="6c331-135">[`switch`](../language-reference/keywords/switch.md) 문의 결과 각각의 `case` 블록에서 값이 생성되는 경우가 종종 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6c331-135">Often, a [`switch`](../language-reference/keywords/switch.md) statement produces a value in each of its `case` blocks.</span></span> <span data-ttu-id="6c331-136">**Switch 식**을 사용하면 더욱더 간결한 식 구문을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6c331-136">**Switch expressions** enable you to use more concise expression syntax.</span></span> <span data-ttu-id="6c331-137">`case` 및 `break` 키워드를 반복적으로 사용하고 중괄호를 적용해야 하는 경우가 줄어듭니다.</span><span class="sxs-lookup"><span data-stu-id="6c331-137">There are fewer repetitive `case` and `break` keywords, and fewer curly braces.</span></span>  <span data-ttu-id="6c331-138">다음과 같이 무지개의 색을 나열하는 enum 예를 살펴보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="6c331-138">As an example, consider the following enum that lists the colors of the rainbow:</span></span>

```csharp
public enum Rainbow
{
    Red,
    Orange,
    Yellow,
    Blue,
    Indigo,
    Violet
}
```

<span data-ttu-id="6c331-139">다음과 같이 switch 식을 포함하는 메서드를 사용하여 `Rainbow` 값을 RGB 값으로 변환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6c331-139">You could convert a `Rainbow` value to its RGB values using the following method containing a switch expression:</span></span>

```csharp
public static RGBColor FromRainbow(Rainbow colorBand) =>
    colorBand switch
    {
        Rainbow.Red    => new RGBColor(0xFF, 0x00, 0x00),
        Rainbow.Orange => new RGBColor(0xFF, 0x7F, 0x00),
        Rainbow.Yellow => new RGBColor(0xFF, 0xFF, 0x00),
        Rainbow.Blue   => new RGBColor(0x00, 0x00, 0xFF),
        Rainbow.Indigo => new RGBColor(0x4B, 0x00, 0x82),
        Rainbow.Violet => new RGBColor(0x94, 0x00, 0xD3),
        _              => throw new ArgumentException(message: "invalid enum value", paramName: nameof(colorBand)),
    };
```

<span data-ttu-id="6c331-140">여기에서 몇 가지 구문 개선 사항을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6c331-140">There are several syntax improvements here:</span></span>

- <span data-ttu-id="6c331-141">변수가 `switch` 키워드 앞에 옵니다.</span><span class="sxs-lookup"><span data-stu-id="6c331-141">The variable comes before the `switch` keyword.</span></span> <span data-ttu-id="6c331-142">이처럼 순서가 변경된 결과 switch 식과 switch 문을 눈으로 구분하기가 쉬워졌습니다.</span><span class="sxs-lookup"><span data-stu-id="6c331-142">The different order makes it visually easy to distinguish the switch expression from the switch statement.</span></span>
- <span data-ttu-id="6c331-143">`case` 및 `:` 요소가 `=>`으로 대체되어</span><span class="sxs-lookup"><span data-stu-id="6c331-143">The `case` and `:` elements are replaced with `=>`.</span></span> <span data-ttu-id="6c331-144">간결성과 직관성이 향상되었습니다.</span><span class="sxs-lookup"><span data-stu-id="6c331-144">It's more concise and intuitive.</span></span>
- <span data-ttu-id="6c331-145">`default` 케이스가 `_` 무시 항목으로 대체되었습니다.</span><span class="sxs-lookup"><span data-stu-id="6c331-145">The `default` case is replaced with a `_` discard.</span></span>
- <span data-ttu-id="6c331-146">본문이 문이 아닌 식입니다.</span><span class="sxs-lookup"><span data-stu-id="6c331-146">The bodies are expressions, not statements.</span></span>

<span data-ttu-id="6c331-147">기존의 `switch` 문을 사용하는 동일한 코드와 비교해 보세요.</span><span class="sxs-lookup"><span data-stu-id="6c331-147">Contrast that with the equivalent code using the classic `switch` statement:</span></span>

```csharp
public static RGBColor fromRainbowClassic(Rainbow colorBand)
{
    switch (colorBand)
    {
        case Rainbow.Red:
            return new RGBColor(0xFF, 0x00, 0x00);
        case Rainbow.Orange:
            return new RGBColor(0xFF, 0x7F, 0x00);
        case Rainbow.Yellow:
            return new RGBColor(0xFF, 0xFF, 0x00);
        case Rainbow.Blue:
            return new RGBColor(0x00, 0x00, 0xFF);
        case Rainbow.Indigo:
            return new RGBColor(0x4B, 0x00, 0x82);
        case Rainbow.Violet:
            return new RGBColor(0x94, 0x00, 0xD3);
        default:
            throw new ArgumentException(message: "invalid enum value", paramName: nameof(colorBand));
    };
}
```

### <a name="property-patterns"></a><span data-ttu-id="6c331-148">속성 패턴</span><span class="sxs-lookup"><span data-stu-id="6c331-148">Property patterns</span></span>

<span data-ttu-id="6c331-149">**속성 패턴**을 사용하면 검사 대상 개체의 속성을 일치시킬 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6c331-149">The **property pattern** enables you to match on properties of the object examined.</span></span> <span data-ttu-id="6c331-150">구매자의 주소를 기준으로 판매세를 계산하는 전자상거래 사이트를 예로 들어 보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="6c331-150">Consider an eCommerce site that must compute sales tax based on the buyer's address.</span></span> <span data-ttu-id="6c331-151">판매세 계산은 `Address` 클래스의 주요 임무가 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="6c331-151">That computation is not a core responsibility of an `Address` class.</span></span> <span data-ttu-id="6c331-152">판매세는 시간이 흐름에 따라 주소 형식이 변경되는 빈도보다 자주 변경될 가능성이 큽니다.</span><span class="sxs-lookup"><span data-stu-id="6c331-152">It will change over time, likely more often than address format changes.</span></span> <span data-ttu-id="6c331-153">판매세의 금액은 주소의 `State` 속성에 종속됩니다.</span><span class="sxs-lookup"><span data-stu-id="6c331-153">The amount of sales tax depends on the `State` property of the address.</span></span> <span data-ttu-id="6c331-154">다음 메서드는 속성 패턴을 사용하여 주소 및 가격으로부터 판매세를 계산합니다.</span><span class="sxs-lookup"><span data-stu-id="6c331-154">The following method uses the property pattern to compute the sales tax from the address and the price:</span></span>

```csharp
public static decimal ComputeSalesTax(Address location, decimal salePrice) =>
    location switch
    {
        { State: "WA" } => salePrice * 0.06M,
        { State: "MN" } => salePrice * 0.75M,
        { State: "MI" } => salePrice * 0.05M,
        // other cases removed for brevity...
        _ => 0M
    };
    ```

Pattern matching creates a concise syntax for expressing this algorithm.

### Tuple patterns

Some algorithms depend on multiple inputs. **Tuple patterns** allow you to switch based on multiple values expressed as a [tuple](../tuples.md).  The following code shows a switch expression for the game *rock, paper, scissors*:

```csharp
public static string RockPaperScissors(string first, string second)
    => (first, second) switch
    {
        ("rock", "paper") => "rock is covered by paper. Paper wins.",
        ("rock", "scissors") => "rock breaks scissors. Rock wins.",
        ("paper", "rock") => "paper covers rock. Paper wins.",
        ("paper", "scissors") => "paper is cut by scissors. Scissors wins.",
        ("scissors", "rock") => "scissors is broken by rock. Rock wins.",
        ("scissors", "paper") => "scissors cuts paper. Scissors wins.",
        (_, _) => "tie"
    };
    ```

The messages indicate the winner. The discard case represents the three combinations for ties, or other text inputs.

### Positional patterns

Some types include a `Deconstruct` method that deconstructs its properties into discrete variables. When a `Deconstruct` method is accessible, you can use **positional patterns** to inspect properties of the object and use those properties for a pattern.  Consider the following `Point` class that includes a `Deconstruct` method to create discrete variables for `X` and `Y`:

```csharp
public class Point
{
    public int X { get; }
    public int Y { get; }

    public Point(int x, int y) => (X, Y) = (x, y);

    public void Deconstruct(out int x, out int y) =>
        (x, y) = (X, Y);
}
```

<span data-ttu-id="6c331-155">다음 메서드는 **위치 패턴**을 사용하여 `x`와 `y`의 값을 추출합니다.</span><span class="sxs-lookup"><span data-stu-id="6c331-155">The following method uses the **positional pattern** to extract the values of `x` and `y`.</span></span> <span data-ttu-id="6c331-156">그런 다음, `when` 절을 사용하여 점의 사분면을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="6c331-156">Then, it uses a `when` clause to determine the quadrant of the point:</span></span>

```csharp
static string Quadrant(Point p) => p switch
{
    (0, 0) => "origin",
    (var x, var y) when x > 0 && y > 0 => "Quadrant 1",
    (var x, var y) when x < 0 && y > 0 => "Quadrant 2",
    (var x, var y) when x < 0 && y < 0 => "Quadrant 3",
    (var x, var y) when x > 0 && y < 0 => "Quadrant 4",
    (var x, var y) => "on a border",
    _ => "unknown"
};
```

<span data-ttu-id="6c331-157">switch의 무시 패턴은 `x`나 `y` 둘 중 하나만 0인 경우에 일치합니다.</span><span class="sxs-lookup"><span data-stu-id="6c331-157">The discard pattern in the preceding switch matches when either `x` or `y`, but not both, is 0.</span></span> <span data-ttu-id="6c331-158">expression 식은 항상 값을 생성하거나 예외를 throw해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6c331-158">A switch expression must either produce a value or throw an exception.</span></span> <span data-ttu-id="6c331-159">일치하는 케이스가 없으면 switch 식이 예외를 throw합니다.</span><span class="sxs-lookup"><span data-stu-id="6c331-159">If none of the cases match, the switch expression throws an exception.</span></span> <span data-ttu-id="6c331-160">switch 식이 가능한 모든 케이스를 포함하지 않으면 컴파일러에서 경고가 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="6c331-160">The compiler generates a warning for you if you do not cover all possible cases in your switch expression.</span></span>

## <a name="using-declarations"></a><span data-ttu-id="6c331-161">using 선언</span><span class="sxs-lookup"><span data-stu-id="6c331-161">using declarations</span></span>

<span data-ttu-id="6c331-162">**using 선언**은 `using` 키워드 뒤에 오는 변수 선언입니다.</span><span class="sxs-lookup"><span data-stu-id="6c331-162">A **using declaration** is a variable declaration preceded by the `using` keyword.</span></span> <span data-ttu-id="6c331-163">using 선언은 선언되는 변수를 바깥쪽 범위의 끝에서 삭제하라고 컴파일러에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="6c331-163">It tells the compiler that the variable being declared should be disposed at the end of the enclosing scope.</span></span> <span data-ttu-id="6c331-164">텍스트 파일을 쓰는 다음 코드를 예로 들어 보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="6c331-164">For example, consider the following code that writes a text file:</span></span>

```csharp
static void WriteLinesToFile(IEnumerable<string> lines)
{
    using var file = new System.IO.StreamWriter("WriteLines2.txt");
    foreach (string line in lines)
    {
        // If the line doesn't contain the word 'Second', write the line to the file.
        if (!line.Contains("Second"))
        {
            file.WriteLine(line);
        }
    }
// file is disposed here
}
```

<span data-ttu-id="6c331-165">위 예에서 메서드의 닫는 중괄호에 도달하면 파일이 삭제됩니다.</span><span class="sxs-lookup"><span data-stu-id="6c331-165">In the preceding example, the file is disposed when the closing brace for the method is reached.</span></span> <span data-ttu-id="6c331-166">이 지점이 바로 `file`이 선언된 범위의 끝입니다.</span><span class="sxs-lookup"><span data-stu-id="6c331-166">That's the end of the scope in which `file` is declared.</span></span> <span data-ttu-id="6c331-167">위 코드는 기존의 [using 문](../language-reference/keywords/using-statement.md) 문을 사용하는 다음 코드와 동일합니다.</span><span class="sxs-lookup"><span data-stu-id="6c331-167">The preceding code is equivalent to the following code using the classic [using statements](../language-reference/keywords/using-statement.md) statement:</span></span>


```csharp
static void WriteLinesToFile(IEnumerable<string> lines)
{
    using (var file = new System.IO.StreamWriter("WriteLines2.txt"))
    {
        foreach (string line in lines)
        {
            // If the line doesn't contain the word 'Second', write the line to the file.
            if (!line.Contains("Second"))
            {
                file.WriteLine(line);
            }
        }
    } // file is disposed here
}
```

<span data-ttu-id="6c331-168">위 예에서 `using` 문의 닫는 중괄호에 도달하면 파일이 삭제됩니다.</span><span class="sxs-lookup"><span data-stu-id="6c331-168">In the preceding example, the file is disposed when the closing brace associated with the `using` statement is reached.</span></span>

<span data-ttu-id="6c331-169">두 경우 모두 컴파일러가 `Dispose()`를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="6c331-169">In both cases, the compiler generates the call to `Dispose()`.</span></span> <span data-ttu-id="6c331-170">using 문의 식을 삭제할 수 없는 경우 컴파일러에서 오류를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="6c331-170">The compiler generates an error if the expression in the using statement is not disposable.</span></span>

## <a name="static-local-functions"></a><span data-ttu-id="6c331-171">정적 로컬 함수</span><span class="sxs-lookup"><span data-stu-id="6c331-171">Static local functions</span></span>

<span data-ttu-id="6c331-172">이제 로컬 함수가 바깥쪽 범위의 변수를 참조하는 경우가 없도록 로컬 함수에 `static` 한정자를 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6c331-172">You can now add the `static` modifier to local functions to ensure that local function doesn't capture (reference) any variables from the enclosing scope.</span></span> <span data-ttu-id="6c331-173">이렇게 하면 `CS8421`, “A static local function can't contain a reference to <variable>”(정적 로컬 함수는 <variable> 참조를 포함할 수 없습니다.)이(가) 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="6c331-173">Doing so generates `CS8421`, "A static local function can't contain a reference to <variable>."</span></span> 

<span data-ttu-id="6c331-174">다음과 같은 코드를 생각해 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6c331-174">Consider the following code.</span></span> <span data-ttu-id="6c331-175">여기서 로컬 함수 `LocalFunction`은 바깥쪽 범위(메서드 `M`)에서 선언된 변수 `y`에 액세스합니다.</span><span class="sxs-lookup"><span data-stu-id="6c331-175">The local function `LocalFunction` accesses the variable `y`, declared in the enclosing scope (the method `M`).</span></span> <span data-ttu-id="6c331-176">따라서 `LocalFunction`을 `static` 한정자와 함께 선언할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="6c331-176">Therefore, `LocalFunction` can't be declared with the `static` modifier:</span></span>

```csharp
int M()
{
    int y;
    LocalFunction();
    return y;

    void LocalFunction() => y = 0;
}
```

<span data-ttu-id="6c331-177">다음 코드에는 정적 로컬 함수가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6c331-177">The following code contains a static local function.</span></span> <span data-ttu-id="6c331-178">여기서 로컬 함수는 바깥쪽 범위의 변수에 액세스하지 않으므로 정적이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6c331-178">It can be static because it doesn't access any variables in the enclosing scope:</span></span>

```csharp
int M()
{
    int y = 5;
    int x = 7;
    return Add(x, y);

    static int Add(int left, int right) => left + right;
}
```

## <a name="disposable-ref-structs"></a><span data-ttu-id="6c331-179">삭제 가능한 ref struct</span><span class="sxs-lookup"><span data-stu-id="6c331-179">Disposable ref structs</span></span>

<span data-ttu-id="6c331-180">`ref` 한정자와 함께 선언된 `struct`는 인터페이스를 구현할 수 없으므로 <xref:System.IDisposable>을 구현할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="6c331-180">A `struct` declared with the `ref` modifier may not implement any interfaces and so cannot implement <xref:System.IDisposable>.</span></span> <span data-ttu-id="6c331-181">따라서 `ref struct`가 삭제 가능해지려면 액세스 가능한 `void Dispose()` 메서드를 가져야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6c331-181">Therefore, to enable a `ref struct` to be disposed, it must have an accessible `void Dispose()` method.</span></span> <span data-ttu-id="6c331-182">이것은 `readonly ref struct` 선언에도 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="6c331-182">This also applies to `readonly ref struct` declarations.</span></span>

## <a name="nullable-reference-types"></a><span data-ttu-id="6c331-183">nullable 참조 형식</span><span class="sxs-lookup"><span data-stu-id="6c331-183">Nullable reference types</span></span>

<span data-ttu-id="6c331-184">nullable 주석 컨텍스트에서 참조 형식의 변수는 모두 **nullable이 아닌 참조 형식**으로 간주됩니다.</span><span class="sxs-lookup"><span data-stu-id="6c331-184">Inside a nullable annotation context, any variable of a reference type is considered to be a **nonnullable reference type**.</span></span> <span data-ttu-id="6c331-185">변수가 null이 될 수 있음을 나타내려면 형식 이름 뒤에 `?`를 추가하여 해당 변수를 **nullable 참조 형식**으로 선언해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6c331-185">If you want to indicate that a variable may be null, you must append the type name with the `?` to declare the variable as a **nullable reference type**.</span></span>

<span data-ttu-id="6c331-186">nullable이 아닌 참조 형식의 경우, 로컬 변수가 선언될 때 null이 아닌 값으로 초기화되도록 컴파일러가 흐름 분석을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="6c331-186">For nonnullable reference types, the compiler uses flow analysis to ensure that local variables are initialized to a non-null value when declared.</span></span> <span data-ttu-id="6c331-187">필드는 생성 시점에 초기화되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6c331-187">Fields must be initialized during construction.</span></span> <span data-ttu-id="6c331-188">생성자(있는 경우)를 호출함으로써 또는 이니셜라이저에 의해 변수가 설정되지 않으면 컴파일러에서 경고를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="6c331-188">The compiler generates a warning if the variable is not set by a call to any of the available constructors or by an initializer.</span></span> <span data-ttu-id="6c331-189">또한, nullable이 아닌 참조 형식은 null이 될 수 있는 값에 할당할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="6c331-189">Furthermore, nonnullable reference types can't be assigned a value that could be null.</span></span>

<span data-ttu-id="6c331-190">nullable 참조 형식은 할당되지 않았는지 또는 null로 초기화되었는지 검사되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6c331-190">Nullable reference types aren't checked to ensure they aren't assigned or initialized to null.</span></span> <span data-ttu-id="6c331-191">단, nullable 참조 형식의 변수가 액세스되거나 nullable이 아닌 참조 형식에 할당되기 전에 null에 대해 검사되도록 컴파일러가 흐름 분석을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="6c331-191">However, the compiler uses flow analysis to ensure that any variable of a nullable reference type is checked against null before it's accessed or assigned to a nonnullable reference type.</span></span>

<span data-ttu-id="6c331-192">[nullable 참조 형식](../nullable-references.md) 개요에서 이 기능에 대해 자세히 알아볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6c331-192">You can learn more about the feature in the overview of [nullable reference types](../nullable-references.md).</span></span> <span data-ttu-id="6c331-193">[nullable 참조 형식 자습서](../tutorials/nullable-reference-types.md)를 활용하여 새 애플리케이션에서 직접 사용해 보세요.</span><span class="sxs-lookup"><span data-stu-id="6c331-193">Try it yourself in a new application in this [nullable reference types tutorial](../tutorials/nullable-reference-types.md).</span></span> <span data-ttu-id="6c331-194">[migrating an application to use nullable reference types tutorial](../tutorials/upgrade-to-nullable-references.md)(nullable 참조 형식을 사용할 수 있도록 애플리케이션 마이그레이션 자습서)에서는 nullable 참조 형식을 사용할 수 있도록 기존 코드베이스를 마이그레이션하는 방법을 알아볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6c331-194">Learn about the steps to migrate an existing codebase to make use of nullable reference types in the [migrating an application to use nullable reference types tutorial](../tutorials/upgrade-to-nullable-references.md).</span></span>

## <a name="asynchronous-streams"></a><span data-ttu-id="6c331-195">비동기 스트림</span><span class="sxs-lookup"><span data-stu-id="6c331-195">Asynchronous streams</span></span>

<span data-ttu-id="6c331-196">C# 8.0부터 스트림을 비동기식으로 만들고 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6c331-196">Starting with C# 8.0, you can create and consume streams asynchronously.</span></span> <span data-ttu-id="6c331-197">비동기 스트림을 반환하는 메서드는 다음과 같은 세 가지 속성을 갖습니다.</span><span class="sxs-lookup"><span data-stu-id="6c331-197">A method that returns an asynchronous stream has three properties:</span></span>

1. <span data-ttu-id="6c331-198">`async` 한정자를 사용하여 선언되었습니다.</span><span class="sxs-lookup"><span data-stu-id="6c331-198">It was declared with the `async` modifier.</span></span>
1. <span data-ttu-id="6c331-199"><xref:System.Collections.Generic.IAsyncEnumerable%601>를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="6c331-199">It returns an <xref:System.Collections.Generic.IAsyncEnumerable%601>.</span></span>
1. <span data-ttu-id="6c331-200">비동기 스트림의 연속적인 요소를 반환하기 위해 메서드가 `yield return` 문을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="6c331-200">The method contains `yield return` statements to return successive elements in the asynchronous stream.</span></span>

<span data-ttu-id="6c331-201">비동기 스트림을 사용하려면 스트림의 요소를 열거할 때 `foreach` 키워드 앞에 `await` 키워드를 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6c331-201">Consuming an asynchronous stream requires you to add the `await` keyword before the `foreach` keyword when you enumerate the elements of the stream.</span></span> <span data-ttu-id="6c331-202">`await` 키워드를 추가하려면 비동기 스트림을 열거하는 메서드가 `async` 한정자와 함께 선언되어야 하며, 이 메서드가 `async` 메서드를 허용하는 형식을 반환해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6c331-202">Adding the `await` keyword requires the method that enumerates the asynchronous stream to be declared with the `async` modifier and to return a type allowed for an `async` method.</span></span> <span data-ttu-id="6c331-203">일반적으로 이는 <xref:System.Threading.Tasks.Task> 또는 <xref:System.Threading.Tasks.Task%601> 형식을 반환해야 함을 의미합니다.</span><span class="sxs-lookup"><span data-stu-id="6c331-203">Typically that means returning a <xref:System.Threading.Tasks.Task> or <xref:System.Threading.Tasks.Task%601>.</span></span> <span data-ttu-id="6c331-204"><xref:System.Threading.Tasks.ValueTask> 또는 <xref:System.Threading.Tasks.ValueTask%601> 형식도 가능합니다.</span><span class="sxs-lookup"><span data-stu-id="6c331-204">It can also be a <xref:System.Threading.Tasks.ValueTask> or <xref:System.Threading.Tasks.ValueTask%601>.</span></span> <span data-ttu-id="6c331-205">메서드는 비동기 스트림을 사용할 수도 있고 생성할 수 있습니다. 비동기 스트림을 생성한다는 것은 메서드가 <xref:System.Collections.Generic.IAsyncEnumerable%601>를 반환한다는 것을 의미합니다.</span><span class="sxs-lookup"><span data-stu-id="6c331-205">A method can both consume and produce an asynchronous stream, which means it would return an <xref:System.Collections.Generic.IAsyncEnumerable%601>.</span></span> <span data-ttu-id="6c331-206">다음 코드는 1에서 20까지의 시퀀스를 생성합니다. 숫자가 생성되는 각 시점 사이에는 100ms의 대기 시간이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6c331-206">The following code generates a sequence from 1 to 20, waiting 100 ms between generating each number:</span></span>

```csharp
public static async System.Collections.Generic.IAsyncEnumerable<int> GenerateSequence()
{
    for (int i = 0; i < 20; i++)
    {
        await Task.Delay(100);
        yield return i;
    }
}
```

<span data-ttu-id="6c331-207">`await foreach` 문을 사용하여 시퀀스를 열거합니다.</span><span class="sxs-lookup"><span data-stu-id="6c331-207">You would enumerate the sequence using the `await foreach` statement:</span></span>

```csharp
await foreach (var number in GenerateSequence())
{
    Console.WriteLine(number);
}
```

<span data-ttu-id="6c331-208">[비동기 스트림 생성 및 사용](../tutorials/generate-consume-asynchronous-stream.md) 자습서에서 직접 비동기 스트림을 사용해 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6c331-208">You can try asynchronous streams yourself in our tutorial on [creating and consuming async streams](../tutorials/generate-consume-asynchronous-stream.md).</span></span>

## <a name="indices-and-ranges"></a><span data-ttu-id="6c331-209">인덱스 및 범위</span><span class="sxs-lookup"><span data-stu-id="6c331-209">Indices and ranges</span></span>

<span data-ttu-id="6c331-210">범위와 인덱스는 배열, <xref:System.Span%601> 또는 <xref:System.ReadOnlySpan%601>에서 하위 범위를 지정하는 간결한 구문을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="6c331-210">Ranges and indices provide a succinct syntax for specifying subranges in an array, <xref:System.Span%601>, or <xref:System.ReadOnlySpan%601>.</span></span>

<span data-ttu-id="6c331-211">인덱스를 **뒤에서부터** 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6c331-211">You can specify an index **from the end**.</span></span> <span data-ttu-id="6c331-212">**뒤에서부터** 지정하려면 `^` 연산자를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="6c331-212">You specify **from the end** using the `^` operator.</span></span> <span data-ttu-id="6c331-213">`array[2]`가 “앞에서부터 2번째” 요소를 의미한다는 것은 이미 잘 알고 계실 것입니다.</span><span class="sxs-lookup"><span data-stu-id="6c331-213">You are familiar with `array[2]` meaning the element "2 from the start".</span></span> <span data-ttu-id="6c331-214">`array[^2]`는 “뒤에서부터 2번째” 요소를 의미합니다.</span><span class="sxs-lookup"><span data-stu-id="6c331-214">Now, `array[^2]` means the element "2 from the end".</span></span> <span data-ttu-id="6c331-215">인덱스 `^0`은 “끝”, 즉 마지막 요소 뒤에 오는 인덱스를 의미합니다.</span><span class="sxs-lookup"><span data-stu-id="6c331-215">The index `^0` means "the end", or the index that follows the last element.</span></span>

<span data-ttu-id="6c331-216">**범위**는 **범위 연산자** `..`를 사용하여 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6c331-216">You can specify a **range** with the **range operator**: `..`.</span></span> <span data-ttu-id="6c331-217">예를 들어, `0..^0`은 배열의 전체 범위를 지정하는데, 앞에서부터 인덱스 0에서 뒤에서부터 인덱스 1까지(즉, ^0 인덱스는 은 포함되지 않음)를 의미합니다.</span><span class="sxs-lookup"><span data-stu-id="6c331-217">For example, `0..^0` specifies the entire range of the array: 0 from the start up to, but not including 0 from the end.</span></span> <span data-ttu-id="6c331-218">피연산자 둘 다 “앞에서부터” 또는 “뒤에서부터”를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6c331-218">Either operand may use "from the start" or "from the end".</span></span> <span data-ttu-id="6c331-219">피연산자 둘 다 생략하는 것도 가능합니다.</span><span class="sxs-lookup"><span data-stu-id="6c331-219">Furthermore, either operand may be omitted.</span></span> <span data-ttu-id="6c331-220">시작 인덱스의 기본값은 `0`, 끝 인덱스의 기본값은 `^0`입니다.</span><span class="sxs-lookup"><span data-stu-id="6c331-220">The defaults are `0` for the start index, and `^0` for the end index.</span></span>

<span data-ttu-id="6c331-221">몇 가지 예를 살펴보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="6c331-221">Let's look at a few examples.</span></span> <span data-ttu-id="6c331-222">다음과 같은 배열이 있습니다. 앞에서부터의 인덱스와 뒤에서부터의 인덱스가 주석으로 처리되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6c331-222">Consider the following array, annotated with its index from the start and from the end:</span></span>

```csharp
var words = new string[]
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
};
```

<span data-ttu-id="6c331-223">각 요소의 인덱스는 “앞에서부터”라는 개념과 “뒤에서부터”라는 개념과 범위에는 해당 범위의 끝은 포함되지 않음을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="6c331-223">The index of each element reinforces the concept of "from the start", and "from the end", and that ranges are exclusive of the end of the range.</span></span> <span data-ttu-id="6c331-224">전체 배열의 “시작”은 첫 번째 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="6c331-224">The "start" of the entire array is the first element.</span></span> <span data-ttu-id="6c331-225">전체 배열의 “끝”은 마지막 요소의 “뒤”에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6c331-225">The "end" of the entire array is *past* the last element.</span></span>

<span data-ttu-id="6c331-226">다음과 같이 `^1` 인덱스를 사용하여 마지막 단어를 가져올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6c331-226">You can retrieve the last word with the `^1` index:</span></span>

```csharp
Console.WriteLine($"The last word is {words[^1]}");
// writes "dog"
```

<span data-ttu-id="6c331-227">다음 코드는 “quick”, “brown”, “fox”라는 단어를 포함하는 하위 범위를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="6c331-227">The following code creates a subrange with the words "quick", "brown", and "fox".</span></span> <span data-ttu-id="6c331-228">이 하위 범위에는 `words[1]`부터 `words[3]`까지 포함되며,</span><span class="sxs-lookup"><span data-stu-id="6c331-228">It includes `words[1]` through `words[3]`.</span></span> <span data-ttu-id="6c331-229">`words[4]` 요소는 포함되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6c331-229">The element `words[4]` is not in the range.</span></span>

```csharp
var brownFox = words[1..4];
```

<span data-ttu-id="6c331-230">다음 코드는 “lazy”와 “dog”를 포함하는 하위 범위를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="6c331-230">The following code creates a subrange with "lazy" and "dog".</span></span> <span data-ttu-id="6c331-231">이 하위 범위에는 `words[^2]`과 `words[^1]`이 포함되며.</span><span class="sxs-lookup"><span data-stu-id="6c331-231">It includes `words[^2]` and `words[^1]`.</span></span> <span data-ttu-id="6c331-232">끝 인덱스 `words[^0]`는 포함되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6c331-232">The end index `words[^0]` is not included:</span></span>

```csharp
var lazyDog = words[^2..^0];
```

<span data-ttu-id="6c331-233">다음 예제는 시작만, 끝만, 그리고 시작과 끝이 모두 열린 범위를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="6c331-233">The following examples create ranges that are open ended for the start, end, or both:</span></span>

```csharp
var allWords = words[..]; // contains "The" through "dog".
var firstPhrase = words[..4]; // contains "The" through "fox"
var lastPhrase = words[6..]; // contains "the, "lazy" and "dog"
```

<span data-ttu-id="6c331-234">범위를 변수로 선언할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6c331-234">You can also declare ranges as variables:</span></span>

```csharp
Range phrase = 1..4;
```

<span data-ttu-id="6c331-235">이렇게 변수로 선언된 범위는 `[` 문자와 `]` 문자 사이에 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6c331-235">The range can then be used inside the `[` and `]` characters:</span></span>

```csharp
var text = words[phrase];
```
