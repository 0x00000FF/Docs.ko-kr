---
title: 숫자 결과 형식 지정 표 - C# 참조
ms.custom: seodec18
description: C# 표준 숫자 형식 문자열에 대한 자세한 정보
ms.date: 09/20/2018
helpviewer_keywords:
- formatting [C#]
- numeric formatting [C#]
- String.Format method
ms.assetid: 120ba537-4448-4c62-8676-7a8fdd98f496
ms.openlocfilehash: 0f2b5bc54a0e9055d64a95dc229eaadf66687b43
ms.sourcegitcommit: 10986410e59ff29f2ec55c6759bde3eb4d1a00cb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/31/2019
ms.locfileid: "66421960"
---
# <a name="formatting-numeric-results-table-c-reference"></a><span data-ttu-id="a83d7-103">숫자 결과 형식 지정 표(C# 참조)</span><span class="sxs-lookup"><span data-stu-id="a83d7-103">Formatting numeric results table (C# Reference)</span></span>

<span data-ttu-id="a83d7-104">다음 표에서는 숫자 결과 형식 지정에 대해 지원되는 형식 지정자를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="a83d7-104">The following table shows supported format specifiers for formatting numeric results.</span></span> <span data-ttu-id="a83d7-105">마지막 열의 형식 지정 결과는 “en-US” <xref:System.Globalization.CultureInfo>에 해당합니다.</span><span class="sxs-lookup"><span data-stu-id="a83d7-105">The formatted result in the last column corresponds to the "en-US" <xref:System.Globalization.CultureInfo>.</span></span>

|<span data-ttu-id="a83d7-106">형식 지정자</span><span class="sxs-lookup"><span data-stu-id="a83d7-106">Format specifier</span></span>|<span data-ttu-id="a83d7-107">설명</span><span class="sxs-lookup"><span data-stu-id="a83d7-107">Description</span></span>|<span data-ttu-id="a83d7-108">예제</span><span class="sxs-lookup"><span data-stu-id="a83d7-108">Examples</span></span>|<span data-ttu-id="a83d7-109">결과</span><span class="sxs-lookup"><span data-stu-id="a83d7-109">Result</span></span>|  
|----------------------|-----------------|--------------|------------|  
|<span data-ttu-id="a83d7-110">C 또는 c</span><span class="sxs-lookup"><span data-stu-id="a83d7-110">C or c</span></span>|<span data-ttu-id="a83d7-111">통화</span><span class="sxs-lookup"><span data-stu-id="a83d7-111">Currency</span></span>|`string s = $"{2.5:C}";`<br /><br /> `string s = $"{-2.5:C}";`|<span data-ttu-id="a83d7-112">$2.50</span><span class="sxs-lookup"><span data-stu-id="a83d7-112">$2.50</span></span><br /><br /> <span data-ttu-id="a83d7-113">($2.50)</span><span class="sxs-lookup"><span data-stu-id="a83d7-113">($2.50)</span></span>|  
|<span data-ttu-id="a83d7-114">D 또는 d</span><span class="sxs-lookup"><span data-stu-id="a83d7-114">D or d</span></span>|<span data-ttu-id="a83d7-115">Decimal</span><span class="sxs-lookup"><span data-stu-id="a83d7-115">Decimal</span></span>|`string s = $"{25:D5}";`|<span data-ttu-id="a83d7-116">00025</span><span class="sxs-lookup"><span data-stu-id="a83d7-116">00025</span></span>|  
|<span data-ttu-id="a83d7-117">E 또는 e</span><span class="sxs-lookup"><span data-stu-id="a83d7-117">E or e</span></span>|<span data-ttu-id="a83d7-118">지수</span><span class="sxs-lookup"><span data-stu-id="a83d7-118">Exponential</span></span>|`string s = $"{250000:E2}";`|<span data-ttu-id="a83d7-119">2.50E+005</span><span class="sxs-lookup"><span data-stu-id="a83d7-119">2.50E+005</span></span>|  
|<span data-ttu-id="a83d7-120">F 또는 f</span><span class="sxs-lookup"><span data-stu-id="a83d7-120">F or f</span></span>|<span data-ttu-id="a83d7-121">고정 소수점</span><span class="sxs-lookup"><span data-stu-id="a83d7-121">Fixed-point</span></span>|`string s = $"{2.5:F2}";`<br /><br /> `string s = $"{2.5:F0}";`|<span data-ttu-id="a83d7-122">2.50</span><span class="sxs-lookup"><span data-stu-id="a83d7-122">2.50</span></span><br /><br /> <span data-ttu-id="a83d7-123">3</span><span class="sxs-lookup"><span data-stu-id="a83d7-123">3</span></span>|  
|<span data-ttu-id="a83d7-124">G 또는 g</span><span class="sxs-lookup"><span data-stu-id="a83d7-124">G or g</span></span>|<span data-ttu-id="a83d7-125">일반</span><span class="sxs-lookup"><span data-stu-id="a83d7-125">General</span></span>|`string s = $"{2.5:G}";`|<span data-ttu-id="a83d7-126">2.5</span><span class="sxs-lookup"><span data-stu-id="a83d7-126">2.5</span></span>|  
|<span data-ttu-id="a83d7-127">N 또는 n</span><span class="sxs-lookup"><span data-stu-id="a83d7-127">N or n</span></span>|<span data-ttu-id="a83d7-128">Numeric</span><span class="sxs-lookup"><span data-stu-id="a83d7-128">Numeric</span></span>|`string s = $"{2500000:N}";`|<span data-ttu-id="a83d7-129">2,500,000.00</span><span class="sxs-lookup"><span data-stu-id="a83d7-129">2,500,000.00</span></span>|  
|<span data-ttu-id="a83d7-130">P 또는 p</span><span class="sxs-lookup"><span data-stu-id="a83d7-130">P or p</span></span>|<span data-ttu-id="a83d7-131">백분율</span><span class="sxs-lookup"><span data-stu-id="a83d7-131">Percent</span></span>|`string s = $"{0.25:P}";`|<span data-ttu-id="a83d7-132">25.00%</span><span class="sxs-lookup"><span data-stu-id="a83d7-132">25.00%</span></span>|  
|<span data-ttu-id="a83d7-133">R 또는 r</span><span class="sxs-lookup"><span data-stu-id="a83d7-133">R or r</span></span>|<span data-ttu-id="a83d7-134">라운드트립</span><span class="sxs-lookup"><span data-stu-id="a83d7-134">Round-trip</span></span>|`string s = $"{2.5:R}";`|<span data-ttu-id="a83d7-135">2.5</span><span class="sxs-lookup"><span data-stu-id="a83d7-135">2.5</span></span>|  
|<span data-ttu-id="a83d7-136">X 또는 x</span><span class="sxs-lookup"><span data-stu-id="a83d7-136">X or x</span></span>|<span data-ttu-id="a83d7-137">16진수</span><span class="sxs-lookup"><span data-stu-id="a83d7-137">Hexadecimal</span></span>|`string s = $"{250:X}";`<br /><br /> `string s = $"{0xffff:X}";`|<span data-ttu-id="a83d7-138">FA</span><span class="sxs-lookup"><span data-stu-id="a83d7-138">FA</span></span><br /><br /> <span data-ttu-id="a83d7-139">FFFF</span><span class="sxs-lookup"><span data-stu-id="a83d7-139">FFFF</span></span>|  

## <a name="remarks"></a><span data-ttu-id="a83d7-140">주의</span><span class="sxs-lookup"><span data-stu-id="a83d7-140">Remarks</span></span>

<span data-ttu-id="a83d7-141">형식 지정자를 사용하여 형식 문자열을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="a83d7-141">You use a format specifier to create a format string.</span></span> <span data-ttu-id="a83d7-142">형식 문자열은 `Axx` 형식입니다. 여기서 각 요소는 다음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="a83d7-142">The format string is of the following form: `Axx`, where</span></span>

- <span data-ttu-id="a83d7-143">`A`는 숫자 값에 적용되는 형식 지정의 유형을 제어하는 형식 지정자입니다.</span><span class="sxs-lookup"><span data-stu-id="a83d7-143">`A` is the format specifier, which controls the type of formatting applied to the numeric value.</span></span>
- <span data-ttu-id="a83d7-144">`xx`는 형식 지정 결과의 자릿수에 영향을 주는 전체 자릿수 지정자입니다.</span><span class="sxs-lookup"><span data-stu-id="a83d7-144">`xx` is the precision specifier, which affects the number of digits in the formatted output.</span></span> <span data-ttu-id="a83d7-145">전체 자릿수 지정자의 값은 0에서 99 사이입니다.</span><span class="sxs-lookup"><span data-stu-id="a83d7-145">The value of the precision specifier ranges from 0 to 99.</span></span>

<span data-ttu-id="a83d7-146">10진수(“D” 또는 “d”) 및 16진수(“X” 또는 “x”) 형식 지정자는 정수 형식에만 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="a83d7-146">The decimal ("D" or "d") and hexadecimal ("X" or "x") format specifiers are supported only for integral types.</span></span> <span data-ttu-id="a83d7-147">왕복(“R” 또는 “r”) 형식 지정자는 <xref:System.Single>, <xref:System.Double> 및 <xref:System.Numerics.BigInteger> 형식에만 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="a83d7-147">The round-trip ("R" or "r") format specifier is supported only for <xref:System.Single>, <xref:System.Double>, and <xref:System.Numerics.BigInteger> types.</span></span>

<span data-ttu-id="a83d7-148">표준 숫자 형식 문자열은 다음에 의해 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="a83d7-148">Standard numeric format strings are supported by:</span></span>

- <span data-ttu-id="a83d7-149">모든 숫자 형식의 `ToString` 메서드 중 일부 오버로드.</span><span class="sxs-lookup"><span data-stu-id="a83d7-149">Some overloads of the `ToString` method of all numeric types.</span></span> <span data-ttu-id="a83d7-150">예를 들어 <xref:System.Int32.ToString%28System.String%29?displayProperty=nameWithType> 및 <xref:System.Int32.ToString%28System.String%2CSystem.IFormatProvider%29?displayProperty=nameWithType> 메서드에 숫자 형식 문자열을 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a83d7-150">For example, you can supply a numeric format string to the <xref:System.Int32.ToString%28System.String%29?displayProperty=nameWithType> and <xref:System.Int32.ToString%28System.String%2CSystem.IFormatProvider%29?displayProperty=nameWithType> methods.</span></span>

- <span data-ttu-id="a83d7-151">예를 들어 <xref:System.String.Format%2A?displayProperty=nameWithType> 메서드에서 지원하는 .NET [복합 형식 지정 기능](../../../standard/base-types/composite-formatting.md)입니다.</span><span class="sxs-lookup"><span data-stu-id="a83d7-151">The .NET [composite formatting feature](../../../standard/base-types/composite-formatting.md), which is supported by the <xref:System.String.Format%2A?displayProperty=nameWithType> method, for example.</span></span>

- <span data-ttu-id="a83d7-152">[보간된 문자열](../tokens/interpolated.md).</span><span class="sxs-lookup"><span data-stu-id="a83d7-152">[Interpolated strings](../tokens/interpolated.md).</span></span>

<span data-ttu-id="a83d7-153">자세한 내용은 [표준 숫자 형식 문자열](../../../standard/base-types/standard-numeric-format-strings.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="a83d7-153">For more information, see [Standard Numeric Format Strings](../../../standard/base-types/standard-numeric-format-strings.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="a83d7-154">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a83d7-154">See also</span></span>

- [<span data-ttu-id="a83d7-155">C# 참조</span><span class="sxs-lookup"><span data-stu-id="a83d7-155">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="a83d7-156">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="a83d7-156">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="a83d7-157">형식 서식 지정</span><span class="sxs-lookup"><span data-stu-id="a83d7-157">Formatting types</span></span>](../../../standard/base-types/formatting-types.md)
- [<span data-ttu-id="a83d7-158">복합 형식 지정</span><span class="sxs-lookup"><span data-stu-id="a83d7-158">Composite formatting</span></span>](../../../standard/base-types/composite-formatting.md)
- [<span data-ttu-id="a83d7-159">문자열 보간</span><span class="sxs-lookup"><span data-stu-id="a83d7-159">String interpolation</span></span>](../tokens/interpolated.md)
- [<span data-ttu-id="a83d7-160">string</span><span class="sxs-lookup"><span data-stu-id="a83d7-160">string</span></span>](string.md)
