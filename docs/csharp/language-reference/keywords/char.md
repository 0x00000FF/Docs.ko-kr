---
title: char 키워드 - C# 참조
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- char
- char_CSharpKeyword
helpviewer_keywords:
- char data type [C#]
ms.assetid: b51cf4fb-124c-4067-af48-afbac122b228
ms.openlocfilehash: b58730d945582ded7b76fcd5c4c65bc1dd9324da
ms.sourcegitcommit: d6e27023aeaffc4b5a3cb4b88685018d6284ada4
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/09/2019
ms.locfileid: "67661464"
---
# <a name="char-c-reference"></a><span data-ttu-id="d4cac-102">char(C# 참조)</span><span class="sxs-lookup"><span data-stu-id="d4cac-102">char (C# Reference)</span></span>

<span data-ttu-id="d4cac-103">`char` 키워드는 .NET Framework에서 유니코드 문자를 표현하는 데 사용하는 <xref:System.Char?displayProperty=nameWithType> 구조체의 인스턴스를 선언하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="d4cac-103">The `char` keyword is used to declare an instance of the <xref:System.Char?displayProperty=nameWithType> structure that the .NET Framework uses to represent a Unicode character.</span></span> <span data-ttu-id="d4cac-104">`Char` 개체의 값은 16비트 숫자(서수) 값입니다.</span><span class="sxs-lookup"><span data-stu-id="d4cac-104">The value of a `Char` object is a 16-bit numeric (ordinal) value.</span></span>

 <span data-ttu-id="d4cac-105">유니코드 문자는 전 세계에서 대부분의 문자 체계를 표현하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="d4cac-105">Unicode characters are used to represent most of the written languages throughout the world.</span></span>

|<span data-ttu-id="d4cac-106">형식</span><span class="sxs-lookup"><span data-stu-id="d4cac-106">Type</span></span>|<span data-ttu-id="d4cac-107">범위</span><span class="sxs-lookup"><span data-stu-id="d4cac-107">Range</span></span>|<span data-ttu-id="d4cac-108">크기</span><span class="sxs-lookup"><span data-stu-id="d4cac-108">Size</span></span>|<span data-ttu-id="d4cac-109">.NET 형식</span><span class="sxs-lookup"><span data-stu-id="d4cac-109">.NET type</span></span>|
|----------|-----------|----------|-------------------------|
|`char`|<span data-ttu-id="d4cac-110">U+0000~U+FFFF</span><span class="sxs-lookup"><span data-stu-id="d4cac-110">U+0000 to U+FFFF</span></span>|<span data-ttu-id="d4cac-111">유니코드 16비트 문자</span><span class="sxs-lookup"><span data-stu-id="d4cac-111">Unicode 16-bit character</span></span>|<xref:System.Char?displayProperty=nameWithType>|

## <a name="literals"></a><span data-ttu-id="d4cac-112">리터럴</span><span class="sxs-lookup"><span data-stu-id="d4cac-112">Literals</span></span>

<span data-ttu-id="d4cac-113">`char` 형식의 상수는 문자 리터럴, 16진수 이스케이프 시퀀스 또는 유니코드 표현으로 기록될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d4cac-113">Constants of the `char` type can be written as character literals, hexadecimal escape sequence, or Unicode representation.</span></span> <span data-ttu-id="d4cac-114">정수 문자 코드를 캐스트할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d4cac-114">You can also cast the integral character codes.</span></span> <span data-ttu-id="d4cac-115">다음 예제에서 `char` 변수 4개는 동일 문자 `X`를 사용하여 초기화됩니다.</span><span class="sxs-lookup"><span data-stu-id="d4cac-115">In the following example four `char` variables are initialized with the same character `X`:</span></span>

[!code-csharp[csrefKeywordsTypes#19](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsTypes/CS/keywordsTypes.cs#19)]

## <a name="conversions"></a><span data-ttu-id="d4cac-116">변환</span><span class="sxs-lookup"><span data-stu-id="d4cac-116">Conversions</span></span>

<span data-ttu-id="d4cac-117">`char`는 [ushort](../builtin-types/integral-numeric-types.md), [int](../builtin-types/integral-numeric-types.md), [uint](../builtin-types/integral-numeric-types.md), [double](../builtin-types/floating-point-numeric-types.md) 또는 [decimal](../builtin-types/floating-point-numeric-types.md)로 암시적으로 변환될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d4cac-117">A `char` can be implicitly converted to [ushort](../builtin-types/integral-numeric-types.md), [int](../builtin-types/integral-numeric-types.md), [uint](../builtin-types/integral-numeric-types.md), [double](../builtin-types/floating-point-numeric-types.md), or [decimal](../builtin-types/floating-point-numeric-types.md).</span></span> <span data-ttu-id="d4cac-118">그러나 기타 형식에서 `char` 형식으로의 암시적 변환은 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d4cac-118">However, there are no implicit conversions from other types to the `char` type.</span></span>

<span data-ttu-id="d4cac-119"><xref:System.Char?displayProperty=nameWithType> 형식은 `char` 값 작업을 위한 몇 가지 정적 메서드를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="d4cac-119">The <xref:System.Char?displayProperty=nameWithType> type provides several static methods for working with `char` values.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="d4cac-120">C# 언어 사양</span><span class="sxs-lookup"><span data-stu-id="d4cac-120">C# language specification</span></span>  

<span data-ttu-id="d4cac-121">자세한 내용은 [C# 언어 사양](../language-specification/index.md)의 [정수 형식](~/_csharplang/spec/types.md#integral-types)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d4cac-121">For more information, see [Integral types](~/_csharplang/spec/types.md#integral-types) in the [C# Language Specification](../language-specification/index.md).</span></span> <span data-ttu-id="d4cac-122">언어 사양은 C# 구문 및 사용법에 대 한 신뢰할 수 있는 소스 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d4cac-122">The language specification is the definitive source for C# syntax and usage.</span></span>

## <a name="see-also"></a><span data-ttu-id="d4cac-123">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d4cac-123">See also</span></span>

- <xref:System.Char>
- [<span data-ttu-id="d4cac-124">C# 참조</span><span class="sxs-lookup"><span data-stu-id="d4cac-124">C# Reference</span></span>](../../../csharp/language-reference/index.md)
- [<span data-ttu-id="d4cac-125">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="d4cac-125">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)
- [<span data-ttu-id="d4cac-126">C# 키워드</span><span class="sxs-lookup"><span data-stu-id="d4cac-126">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)
- [<span data-ttu-id="d4cac-127">정수 형식</span><span class="sxs-lookup"><span data-stu-id="d4cac-127">Integral types</span></span>](../../../csharp/language-reference/builtin-types/integral-numeric-types.md)
- [<span data-ttu-id="d4cac-128">기본 제공 형식 표</span><span class="sxs-lookup"><span data-stu-id="d4cac-128">Built-In Types Table</span></span>](../../../csharp/language-reference/keywords/built-in-types-table.md)
- [<span data-ttu-id="d4cac-129">암시적 숫자 변환 표</span><span class="sxs-lookup"><span data-stu-id="d4cac-129">Implicit Numeric Conversions Table</span></span>](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md)
- [<span data-ttu-id="d4cac-130">명시적 숫자 변환 표</span><span class="sxs-lookup"><span data-stu-id="d4cac-130">Explicit Numeric Conversions Table</span></span>](../../../csharp/language-reference/keywords/explicit-numeric-conversions-table.md)
- [<span data-ttu-id="d4cac-131">Nullable 형식</span><span class="sxs-lookup"><span data-stu-id="d4cac-131">Nullable Types</span></span>](../../../csharp/programming-guide/nullable-types/index.md)
- [<span data-ttu-id="d4cac-132">문자열</span><span class="sxs-lookup"><span data-stu-id="d4cac-132">Strings</span></span>](../../../csharp/programming-guide/strings/index.md)
