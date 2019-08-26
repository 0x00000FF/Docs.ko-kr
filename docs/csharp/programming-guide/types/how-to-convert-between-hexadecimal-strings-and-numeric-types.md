---
title: '방법: 16진수 문자열과 숫자 형식 간 변환 - C# 프로그래밍 가이드'
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- hexadecimal strings [C#], converting to numeric type
- conversions [C#], hexidecimal strings
- strings [C#], converting hexadecimal strings
- hexadecimal strings [C#]
ms.assetid: 7115c49f-7d1d-40c3-8bd9-aae0cc1d46b6
ms.openlocfilehash: a7109945192fe1577cd1b96c8b4d6c05270d54e8
ms.sourcegitcommit: 986f836f72ef10876878bd6217174e41464c145a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/19/2019
ms.locfileid: "69588378"
---
# <a name="how-to-convert-between-hexadecimal-strings-and-numeric-types-c-programming-guide"></a><span data-ttu-id="754de-102">방법: 16진수 문자열과 숫자 형식 간 변환(C# 프로그래밍 가이드)</span><span class="sxs-lookup"><span data-stu-id="754de-102">How to: Convert Between Hexadecimal Strings and Numeric Types (C# Programming Guide)</span></span>
<span data-ttu-id="754de-103">이 예제에서는 다음 작업을 수행하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="754de-103">These examples show you how to perform the following tasks:</span></span>  
  
- <span data-ttu-id="754de-104">[string](../../language-reference/keywords/string.md)에 있는 각 문자의 16진수 값을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="754de-104">Obtain the hexadecimal value of each character in a [string](../../language-reference/keywords/string.md).</span></span>  
  
- <span data-ttu-id="754de-105">16진수 문자열의 각 값에 해당하는 [char](../../language-reference/keywords/char.md)을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="754de-105">Obtain the [char](../../language-reference/keywords/char.md) that corresponds to each value in a hexadecimal string.</span></span>  
  
- <span data-ttu-id="754de-106">16진수 `string`을 [int](../../language-reference/builtin-types/integral-numeric-types.md)로 변환합니다.</span><span class="sxs-lookup"><span data-stu-id="754de-106">Convert a hexadecimal `string` to an [int](../../language-reference/builtin-types/integral-numeric-types.md).</span></span>  
  
- <span data-ttu-id="754de-107">16진수 `string`을 [float](../../language-reference/builtin-types/floating-point-numeric-types.md)로 변환합니다.</span><span class="sxs-lookup"><span data-stu-id="754de-107">Convert a hexadecimal `string` to a [float](../../language-reference/builtin-types/floating-point-numeric-types.md).</span></span>  
  
- <span data-ttu-id="754de-108">[byte](../../language-reference/builtin-types/integral-numeric-types.md) 배열을 16진수 `string`으로 변환합니다.</span><span class="sxs-lookup"><span data-stu-id="754de-108">Convert a [byte](../../language-reference/builtin-types/integral-numeric-types.md) array to a hexadecimal `string`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="754de-109">예</span><span class="sxs-lookup"><span data-stu-id="754de-109">Example</span></span>  
 <span data-ttu-id="754de-110">이 예제에서는 `string`에 있는 각 문자의 16진수 값을 출력합니다.</span><span class="sxs-lookup"><span data-stu-id="754de-110">This example outputs the hexadecimal value of each character in a `string`.</span></span> <span data-ttu-id="754de-111">먼저 `string`을 문자 배열로 구문 분석합니다.</span><span class="sxs-lookup"><span data-stu-id="754de-111">First it parses the `string` to an array of characters.</span></span> <span data-ttu-id="754de-112">그런 다음 각 문자에서 <xref:System.Convert.ToInt32%28System.Char%29>를 호출하여 해당 숫자 값을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="754de-112">Then it calls <xref:System.Convert.ToInt32%28System.Char%29> on each character to obtain its numeric value.</span></span> <span data-ttu-id="754de-113">마지막으로, `string`에서 숫자의 형식을 16진수 표현으로 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="754de-113">Finally, it formats the number as its hexadecimal representation in a `string`.</span></span>  
  
 [!code-csharp[csProgGuideTypes#30](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsProgGuideTypes/CS/Class1.cs#30)]  
  
## <a name="example"></a><span data-ttu-id="754de-114">예</span><span class="sxs-lookup"><span data-stu-id="754de-114">Example</span></span>  
 <span data-ttu-id="754de-115">이 예제에서는 16진수 값의 `string`을 구문 분석하고 각 16진수 값에 해당하는 문자를 출력합니다.</span><span class="sxs-lookup"><span data-stu-id="754de-115">This example parses a `string` of hexadecimal values and outputs the character corresponding to each hexadecimal value.</span></span> <span data-ttu-id="754de-116">먼저 [Split(Char\[\])](xref:System.String.Split(System.Char[])) 메서드를 호출하여 각 16진수 값을 배열의 개별 `string`으로 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="754de-116">First it calls the [Split(Char\[\])](xref:System.String.Split(System.Char[])) method to obtain each hexadecimal value as an individual `string` in an array.</span></span> <span data-ttu-id="754de-117">그런 다음 <xref:System.Convert.ToInt32%28System.String%2CSystem.Int32%29>를 호출하여 16진수 값을 [int](../../language-reference/builtin-types/integral-numeric-types.md)로 표현된 10진수 값으로 변환합니다. 다음은 문자 코드에 해당하는 문자를 가져오는 두 가지 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="754de-117">Then it calls <xref:System.Convert.ToInt32%28System.String%2CSystem.Int32%29> to convert the hexadecimal value to a decimal value represented as an [int](../../language-reference/builtin-types/integral-numeric-types.md). It shows two different ways to obtain the character corresponding to that character code.</span></span> <span data-ttu-id="754de-118">첫 번째 방법은 정수 인수에 해당하는 문자를 `string`으로 반환하는 <xref:System.Char.ConvertFromUtf32%28System.Int32%29>를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="754de-118">The first technique uses <xref:System.Char.ConvertFromUtf32%28System.Int32%29>, which returns the character corresponding to the integer argument as a `string`.</span></span> <span data-ttu-id="754de-119">두 번째 방법은 `int`를 [char](../../language-reference/keywords/char.md)로 명시적으로 캐스팅합니다.</span><span class="sxs-lookup"><span data-stu-id="754de-119">The second technique explicitly casts the `int` to a [char](../../language-reference/keywords/char.md).</span></span>  
  
 [!code-csharp[csProgGuideTypes#31](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsProgGuideTypes/CS/Class1.cs#31)]  
  
## <a name="example"></a><span data-ttu-id="754de-120">예</span><span class="sxs-lookup"><span data-stu-id="754de-120">Example</span></span>  
 <span data-ttu-id="754de-121">이 예제에서는 <xref:System.Int32.Parse%28System.String%2CSystem.Globalization.NumberStyles%29> 메서드를 호출하여 16진수 `string`을 정수로 변환하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="754de-121">This example shows another way to convert a hexadecimal `string` to an integer, by calling the <xref:System.Int32.Parse%28System.String%2CSystem.Globalization.NumberStyles%29> method.</span></span>  
  
 [!code-csharp[csProgGuideTypes#32](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsProgGuideTypes/CS/Class1.cs#32)]  
  
## <a name="example"></a><span data-ttu-id="754de-122">예</span><span class="sxs-lookup"><span data-stu-id="754de-122">Example</span></span>  
 <span data-ttu-id="754de-123">다음 예제에서는 <xref:System.BitConverter?displayProperty=nameWithType> 클래스 및 <xref:System.UInt32.Parse%2A?displayProperty=nameWithType> 메서드를 사용하여 16진수 `string`을 [float](../../language-reference/builtin-types/floating-point-numeric-types.md)로 변환하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="754de-123">The following example shows how to convert a hexadecimal `string` to a [float](../../language-reference/builtin-types/floating-point-numeric-types.md) by using the <xref:System.BitConverter?displayProperty=nameWithType> class and the <xref:System.UInt32.Parse%2A?displayProperty=nameWithType> method.</span></span>  
  
 [!code-csharp[csProgGuideTypes#39](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsProgGuideTypes/CS/Class1.cs#39)]  
  
## <a name="example"></a><span data-ttu-id="754de-124">예</span><span class="sxs-lookup"><span data-stu-id="754de-124">Example</span></span>  
 <span data-ttu-id="754de-125">다음 예제에서는 <xref:System.BitConverter?displayProperty=nameWithType> 클래스를 사용하여 [byte](../../language-reference/builtin-types/integral-numeric-types.md) 배열을 16진수 문자열로 변환하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="754de-125">The following example shows how to convert a [byte](../../language-reference/builtin-types/integral-numeric-types.md) array to a hexadecimal string by using the <xref:System.BitConverter?displayProperty=nameWithType> class.</span></span>  
  
 [!code-csharp[csProgGuideTypes#38](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsProgGuideTypes/CS/Class1.cs#38)]  
  
## <a name="see-also"></a><span data-ttu-id="754de-126">참고 항목</span><span class="sxs-lookup"><span data-stu-id="754de-126">See also</span></span>

- [<span data-ttu-id="754de-127">Standard Numeric Format Strings</span><span class="sxs-lookup"><span data-stu-id="754de-127">Standard Numeric Format Strings</span></span>](../../../standard/base-types/standard-numeric-format-strings.md)
- [<span data-ttu-id="754de-128">유형</span><span class="sxs-lookup"><span data-stu-id="754de-128">Types</span></span>](./index.md)
- [<span data-ttu-id="754de-129">방법: 문자열이 숫자 값을 나타내는지 확인</span><span class="sxs-lookup"><span data-stu-id="754de-129">How to: Determine Whether a String Represents a Numeric Value</span></span>](../strings/how-to-determine-whether-a-string-represents-a-numeric-value.md)
