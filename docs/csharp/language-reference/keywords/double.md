---
title: double 키워드(C# 참조)
ms.date: 07/20/2015
f1_keywords:
- double
- double_CSharpKeyword
helpviewer_keywords:
- double data type [C#]
ms.assetid: 0980e11b-6004-4102-abcf-cfc280fc6991
ms.openlocfilehash: 4c11065d9354d44c1da8354c6f7b4f52d7b84c10
ms.sourcegitcommit: 4b6490b2529707627ad77c3a43fbe64120397175
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/10/2018
ms.locfileid: "44275394"
---
# <a name="double-c-reference"></a><span data-ttu-id="8ae1f-102">double(C# 참조)</span><span class="sxs-lookup"><span data-stu-id="8ae1f-102">double (C# Reference)</span></span>

<span data-ttu-id="8ae1f-103">`double` 키워드는 64비트 부동 소수점 값을 저장하는 단순 형식을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="8ae1f-103">The `double` keyword signifies a simple type that stores 64-bit floating-point values.</span></span> <span data-ttu-id="8ae1f-104">다음 표에서는 `double` 형식의 전체 자릿수와 근사 범위를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="8ae1f-104">The following table shows the precision and approximate range for the `double` type.</span></span>

|<span data-ttu-id="8ae1f-105">형식</span><span class="sxs-lookup"><span data-stu-id="8ae1f-105">Type</span></span>|<span data-ttu-id="8ae1f-106">근사 범위</span><span class="sxs-lookup"><span data-stu-id="8ae1f-106">Approximate range</span></span>|<span data-ttu-id="8ae1f-107">전체 자릿수</span><span class="sxs-lookup"><span data-stu-id="8ae1f-107">Precision</span></span>|<span data-ttu-id="8ae1f-108">.NET 형식</span><span class="sxs-lookup"><span data-stu-id="8ae1f-108">.NET type</span></span>|
|----------|-----------------------|---------------|-------------------------|
|`double`|<span data-ttu-id="8ae1f-109">±5.0 × 10<sup>−324</sup> ~ ±1.7 × 10<sup>308</sup></span><span class="sxs-lookup"><span data-stu-id="8ae1f-109">±5.0 × 10<sup>−324</sup> to ±1.7 × 10<sup>308</sup></span></span>|<span data-ttu-id="8ae1f-110">15-16자리</span><span class="sxs-lookup"><span data-stu-id="8ae1f-110">15-16 digits</span></span>|<xref:System.Double?displayProperty=nameWithType>|

## <a name="literals"></a><span data-ttu-id="8ae1f-111">리터럴</span><span class="sxs-lookup"><span data-stu-id="8ae1f-111">Literals</span></span>

<span data-ttu-id="8ae1f-112">기본적으로 대입 연산자 오른쪽의 실수 리터럴은 `double`로 처리됩니다.</span><span class="sxs-lookup"><span data-stu-id="8ae1f-112">By default, a real numeric literal on the right side of the assignment operator is treated as `double`.</span></span> <span data-ttu-id="8ae1f-113">그러나 정수가 `double`로 처리되도록 하려면 접미사 d 또는 D를 사용하세요. 예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="8ae1f-113">However, if you want an integer number to be treated as `double`, use the suffix d or D, for example:</span></span>

```csharp
double x = 3D;
```

## <a name="conversions"></a><span data-ttu-id="8ae1f-114">변환</span><span class="sxs-lookup"><span data-stu-id="8ae1f-114">Conversions</span></span>

<span data-ttu-id="8ae1f-115">식에서 숫자 정수 형식과 부동 소수점 형식을 함께 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8ae1f-115">You can mix numeric integral types and floating-point types in an expression.</span></span> <span data-ttu-id="8ae1f-116">이 경우 정수 형식이 부동 소수점 형식으로 변환됩니다.</span><span class="sxs-lookup"><span data-stu-id="8ae1f-116">In this case, the integral types are converted to floating-point types.</span></span> <span data-ttu-id="8ae1f-117">식의 계산은 다음 규칙에 따라 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="8ae1f-117">The evaluation of the expression is performed according to the following rules:</span></span>

- <span data-ttu-id="8ae1f-118">부동 소수점 형식 중 하나가 `double`이면 식은 관계형 비교 및 같음에 대한 비교에서 `double` 또는 [bool](../../../csharp/language-reference/keywords/bool.md)로 계산됩니다.</span><span class="sxs-lookup"><span data-stu-id="8ae1f-118">If one of the floating-point types is `double`, the expression evaluates to `double`, or to [bool](../../../csharp/language-reference/keywords/bool.md) in relational comparisons and comparisons for equality.</span></span>

- <span data-ttu-id="8ae1f-119">식에 `double` 유형이 없으면 관계형 비교 및 같음에 대한 비교에서 [float](../../../csharp/language-reference/keywords/float.md) 또는 [bool](../../../csharp/language-reference/keywords/bool.md)로 계산됩니다.</span><span class="sxs-lookup"><span data-stu-id="8ae1f-119">If there is no `double` type in the expression, it evaluates to [float](../../../csharp/language-reference/keywords/float.md), or to [bool](../../../csharp/language-reference/keywords/bool.md) in relational comparisons and comparisons for equality.</span></span>

 <span data-ttu-id="8ae1f-120">부동 소수점 식에는 다음과 같은 값 집합이 포함될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8ae1f-120">A floating-point expression can contain the following sets of values:</span></span>

- <span data-ttu-id="8ae1f-121">양수 및 음수 0.</span><span class="sxs-lookup"><span data-stu-id="8ae1f-121">Positive and negative zero.</span></span>

- <span data-ttu-id="8ae1f-122">양수 및 음수 무한대.</span><span class="sxs-lookup"><span data-stu-id="8ae1f-122">Positive and negative infinity.</span></span>

- <span data-ttu-id="8ae1f-123">NaN(Not-a-Number) 값.</span><span class="sxs-lookup"><span data-stu-id="8ae1f-123">Not-a-Number value (NaN).</span></span>

- <span data-ttu-id="8ae1f-124">한정된 0이 아닌 값의 집합.</span><span class="sxs-lookup"><span data-stu-id="8ae1f-124">The finite set of nonzero values.</span></span>

<span data-ttu-id="8ae1f-125">이러한 값에 대한 자세한 내용은 [IEEE](https://www.ieee.org) 웹 사이트에서 제공되는 이진 부동 소수점 연산에 대한 IEEE 표준을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="8ae1f-125">For more information about these values, see IEEE Standard for Binary Floating-Point Arithmetic, available on the [IEEE](https://www.ieee.org) Web site.</span></span>

## <a name="example"></a><span data-ttu-id="8ae1f-126">예</span><span class="sxs-lookup"><span data-stu-id="8ae1f-126">Example</span></span>

<span data-ttu-id="8ae1f-127">다음 예제에서는 [int](../../../csharp/language-reference/keywords/int.md), [short](../../../csharp/language-reference/keywords/short.md), [float](../../../csharp/language-reference/keywords/float.md) 및 `double`을 함께 더하여 `double` 결과를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="8ae1f-127">In the following example, an [int](../../../csharp/language-reference/keywords/int.md), a [short](../../../csharp/language-reference/keywords/short.md), a [float](../../../csharp/language-reference/keywords/float.md), and a `double` are added together giving a `double` result.</span></span>

[!code-csharp[csrefKeywordsTypes#9](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsTypes/CS/keywordsTypes.cs#9)]

## <a name="c-language-specification"></a><span data-ttu-id="8ae1f-128">C# 언어 사양</span><span class="sxs-lookup"><span data-stu-id="8ae1f-128">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="8ae1f-129">참고 항목</span><span class="sxs-lookup"><span data-stu-id="8ae1f-129">See Also</span></span>

- [<span data-ttu-id="8ae1f-130">C# 참조</span><span class="sxs-lookup"><span data-stu-id="8ae1f-130">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
- [<span data-ttu-id="8ae1f-131">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="8ae1f-131">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="8ae1f-132">C# 키워드</span><span class="sxs-lookup"><span data-stu-id="8ae1f-132">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
- [<span data-ttu-id="8ae1f-133">기본값 표</span><span class="sxs-lookup"><span data-stu-id="8ae1f-133">Default Values Table</span></span>](../../../csharp/language-reference/keywords/default-values-table.md)  
- [<span data-ttu-id="8ae1f-134">기본 제공 형식 표</span><span class="sxs-lookup"><span data-stu-id="8ae1f-134">Built-In Types Table</span></span>](../../../csharp/language-reference/keywords/built-in-types-table.md)  
- [<span data-ttu-id="8ae1f-135">부동 소수점 형식 표</span><span class="sxs-lookup"><span data-stu-id="8ae1f-135">Floating-Point Types Table</span></span>](../../../csharp/language-reference/keywords/floating-point-types-table.md)  
- [<span data-ttu-id="8ae1f-136">암시적 숫자 변환 표</span><span class="sxs-lookup"><span data-stu-id="8ae1f-136">Implicit Numeric Conversions Table</span></span>](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md)  
- [<span data-ttu-id="8ae1f-137">명시적 숫자 변환 표</span><span class="sxs-lookup"><span data-stu-id="8ae1f-137">Explicit Numeric Conversions Table</span></span>](../../../csharp/language-reference/keywords/explicit-numeric-conversions-table.md)  
