---
title: "int(C# 참조)"
ms.date: 03/14/2017
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- int_CSharpKeyword
- int
helpviewer_keywords:
- int keyword [C#]
ms.assetid: 212447b4-5d2a-41aa-88ab-84fe710bdb52
caps.latest.revision: 
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: e7acb8bb482ebf8f5c2b508e7cfd45b5b64aae3b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="int-c-reference"></a><span data-ttu-id="fb8b6-102">int(C# 참조)</span><span class="sxs-lookup"><span data-stu-id="fb8b6-102">int (C# Reference)</span></span>

<span data-ttu-id="fb8b6-103">`int`는 다음 표에 나와 있는 크기와 범위에 따라 값을 저장하는 정수 형식을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="fb8b6-103">`int` denotes an integral type that stores values according to the size and range shown in the following table.</span></span>  
  
|<span data-ttu-id="fb8b6-104">형식</span><span class="sxs-lookup"><span data-stu-id="fb8b6-104">Type</span></span>|<span data-ttu-id="fb8b6-105">범위</span><span class="sxs-lookup"><span data-stu-id="fb8b6-105">Range</span></span>|<span data-ttu-id="fb8b6-106">크기</span><span class="sxs-lookup"><span data-stu-id="fb8b6-106">Size</span></span>|<span data-ttu-id="fb8b6-107">.NET Framework 형식</span><span class="sxs-lookup"><span data-stu-id="fb8b6-107">.NET Framework type</span></span>|<span data-ttu-id="fb8b6-108">기본값</span><span class="sxs-lookup"><span data-stu-id="fb8b6-108">Default Value</span></span>|  
|----------|-----------|----------|-------------------------|-------------------|  
|`int`|<span data-ttu-id="fb8b6-109">–2,147,483,648 ~ 2,147,483,647</span><span class="sxs-lookup"><span data-stu-id="fb8b6-109">-2,147,483,648 to 2,147,483,647</span></span>|<span data-ttu-id="fb8b6-110">부호 있는 32비트 정수</span><span class="sxs-lookup"><span data-stu-id="fb8b6-110">Signed 32-bit integer</span></span>|<xref:System.Int32?displayProperty=nameWithType>|<span data-ttu-id="fb8b6-111">0</span><span class="sxs-lookup"><span data-stu-id="fb8b6-111">0</span></span>|  
  
## <a name="literals"></a><span data-ttu-id="fb8b6-112">리터럴</span><span class="sxs-lookup"><span data-stu-id="fb8b6-112">Literals</span></span>  
 
<span data-ttu-id="fb8b6-113">10진수 리터럴, 16진수 리터럴 또는 (C# 7부터) 이진 리터럴을 할당하여 `int` 변수를 선언하고 초기화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fb8b6-113">You can declare and initialize an `int` variable by assigning a decimal literal, a hexadecimal literal, or (starting with C# 7) a binary literal to it.</span></span>  <span data-ttu-id="fb8b6-114">정수 리터럴이 `int` 범위를 벗어나는 경우(즉 <xref:System.Int32.MinValue?displayProperty=nameWithType>보다 작거나 <xref:System.Int32.MaxValue?displayProperty=nameWithType>보다 큰 경우) 컴파일 오류가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="fb8b6-114">If the integer literal is outside the range of `int` (that is, if it is less than <xref:System.Int32.MinValue?displayProperty=nameWithType> or greater than <xref:System.Int32.MaxValue?displayProperty=nameWithType>), a compilation error occurs.</span></span> 

<span data-ttu-id="fb8b6-115">다음 예제에서는 10진수, 16진수 및 이진 리터럴로 표현된 90,946와 같은 정수가 `int` 값에 할당됩니다.</span><span class="sxs-lookup"><span data-stu-id="fb8b6-115">In the following example, integers equal to 90,946 that are represented as decimal, hexadecimal, and binary literals are assigned to `int` values.</span></span>  
  
[!code-csharp[int](../../../../samples/snippets/csharp/language-reference/keywords/numeric-literals.cs#Int)]  

> [!NOTE] 
> <span data-ttu-id="fb8b6-116">`0x` 또는 `0X` 접두사를 사용하여 16진수 리터럴을 나타내고, `0b` 또는 `0B` 접두사를 사용하여 이진 리터럴을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="fb8b6-116">You use the prefix `0x` or `0X` to denote a hexadecimal literal and the prefix `0b` or `0B` to denote a binary literal.</span></span> <span data-ttu-id="fb8b6-117">10진수 리터럴에는 접두사가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="fb8b6-117">Decimal literals have no prefix.</span></span> 

<span data-ttu-id="fb8b6-118">부터 C# 7, 몇 가지 기능이 추가 된 가독성을 향상 시키기 합니다.</span><span class="sxs-lookup"><span data-stu-id="fb8b6-118">Starting with C# 7, a couple of features have been added to enhance readability.</span></span> 
 - <span data-ttu-id="fb8b6-119">C# 7.0 밑줄 문자를 사용할 수 있습니다. `_`,으로 숫자 구분 기호입니다.</span><span class="sxs-lookup"><span data-stu-id="fb8b6-119">C# 7.0 allows the usage of the underscore character, `_`, as a digit separator.</span></span>
 - <span data-ttu-id="fb8b6-120">C# 7.2 허용 `_` 접두사 뒤에 대 한 이진 또는 16 진수 리터럴, 자리 구분 기호로 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fb8b6-120">C# 7.2 allows `_` to be used as a digit separator for a binary or hexadecimal literal, after the prefix.</span></span> <span data-ttu-id="fb8b6-121">10 진수 리터럴은 선행 밑줄이에 허용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="fb8b6-121">A decimal literal isn't permitted to have a leading underscore.</span></span>

<span data-ttu-id="fb8b6-122">몇 가지 예는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="fb8b6-122">Some examples are shown below.</span></span>

[!code-csharp[int](../../../../samples/snippets/csharp/language-reference/keywords/numeric-literals.cs#IntS)]  
 
 <span data-ttu-id="fb8b6-123">`int` 형식을 나타내는 접미사는 없어도 형식을 나타내는 접미사가 정수 리터럴에 포함되어 있을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fb8b6-123">Integer literals can also include a suffix that denotes the type, although there is no suffix that denotes the `int` type.</span></span> <span data-ttu-id="fb8b6-124">정수 리터럴에 접미사가 없는 경우 해당 형식은 값이 표현될 수 있는 다음 형식 중 첫 번째 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="fb8b6-124">If an integer literal has no suffix, its type is the first of the following types in which its value can be represented:</span></span> 

1. `int`
2. [<span data-ttu-id="fb8b6-125">uint</span><span class="sxs-lookup"><span data-stu-id="fb8b6-125">uint</span></span>](../../../csharp/language-reference/keywords/uint.md)
3. [<span data-ttu-id="fb8b6-126">long</span><span class="sxs-lookup"><span data-stu-id="fb8b6-126">long</span></span>](../../../csharp/language-reference/keywords/long.md)
4. [<span data-ttu-id="fb8b6-127">ulong</span><span class="sxs-lookup"><span data-stu-id="fb8b6-127">ulong</span></span>](../../../csharp/language-reference/keywords/ulong.md) 
 
<span data-ttu-id="fb8b6-128">이 예제에서 리터럴 90946은 `int` 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="fb8b6-128">In these examples, the literal 90946 is of type `int`.</span></span>
  
## <a name="conversions"></a><span data-ttu-id="fb8b6-129">변환</span><span class="sxs-lookup"><span data-stu-id="fb8b6-129">Conversions</span></span>  
 <span data-ttu-id="fb8b6-130">`int`에서 [long](../../../csharp/language-reference/keywords/long.md), [float](../../../csharp/language-reference/keywords/float.md), [double](../../../csharp/language-reference/keywords/double.md) 또는 [decimal](../../../csharp/language-reference/keywords/decimal.md)로 미리 정의된 암시적 변환이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fb8b6-130">There is a predefined implicit conversion from `int` to [long](../../../csharp/language-reference/keywords/long.md), [float](../../../csharp/language-reference/keywords/float.md), [double](../../../csharp/language-reference/keywords/double.md), or [decimal](../../../csharp/language-reference/keywords/decimal.md).</span></span> <span data-ttu-id="fb8b6-131">예:</span><span class="sxs-lookup"><span data-stu-id="fb8b6-131">For example:</span></span>  
  
```csharp  
// '123' is an int, so an implicit conversion takes place here:  
float f = 123;  
```  
  
 <span data-ttu-id="fb8b6-132">[sbyte](../../../csharp/language-reference/keywords/sbyte.md), [byte](../../../csharp/language-reference/keywords/byte.md), [short](../../../csharp/language-reference/keywords/short.md), [ushort](../../../csharp/language-reference/keywords/ushort.md) 또는 [char](../../../csharp/language-reference/keywords/char.md)에서 `int`로 미리 정의된 암시적 변환이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fb8b6-132">There is a predefined implicit conversion from [sbyte](../../../csharp/language-reference/keywords/sbyte.md), [byte](../../../csharp/language-reference/keywords/byte.md), [short](../../../csharp/language-reference/keywords/short.md), [ushort](../../../csharp/language-reference/keywords/ushort.md), or [char](../../../csharp/language-reference/keywords/char.md) to `int`.</span></span> <span data-ttu-id="fb8b6-133">예를 들어 다음 대입문은 캐스트 없이 컴파일 오류를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="fb8b6-133">For example, the following assignment statement will produce a compilation error without a cast:</span></span>  
  
```csharp  
long aLong = 22;  
int i1 = aLong;       // Error: no implicit conversion from long.  
int i2 = (int)aLong;  // OK: explicit conversion.  
```  
  
 <span data-ttu-id="fb8b6-134">부동 소수점 형식에서 `int`로의 암시적 변환은 없습니다.</span><span class="sxs-lookup"><span data-stu-id="fb8b6-134">Notice also that there is no implicit conversion from floating-point types to `int`.</span></span> <span data-ttu-id="fb8b6-135">예를 들어 명시적 캐스트를 사용하지 않는 경우 다음 문은 컴파일러 오류를 일으킵니다.</span><span class="sxs-lookup"><span data-stu-id="fb8b6-135">For example, the following statement generates a compiler error unless an explicit cast is used:</span></span>  
  
```csharp  
int x = 3.0;         // Error: no implicit conversion from double.  
int y = (int)3.0;    // OK: explicit conversion.  
```  
  
 <span data-ttu-id="fb8b6-136">부동 소수점 형식 및 정수 형식이 혼합된 산술 식에 대한 자세한 내용은 [float](../../../csharp/language-reference/keywords/float.md) 및 [double](../../../csharp/language-reference/keywords/double.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="fb8b6-136">For more information on arithmetic expressions with mixed floating-point types and integral types, see [float](../../../csharp/language-reference/keywords/float.md) and [double](../../../csharp/language-reference/keywords/double.md).</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="fb8b6-137">C# 언어 사양</span><span class="sxs-lookup"><span data-stu-id="fb8b6-137">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="fb8b6-138">참고 항목</span><span class="sxs-lookup"><span data-stu-id="fb8b6-138">See Also</span></span>  
 <xref:System.Int32>  
 [<span data-ttu-id="fb8b6-139">C# 참조</span><span class="sxs-lookup"><span data-stu-id="fb8b6-139">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="fb8b6-140">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="fb8b6-140">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="fb8b6-141">C# 키워드</span><span class="sxs-lookup"><span data-stu-id="fb8b6-141">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
 [<span data-ttu-id="fb8b6-142">정수 계열 형식 표</span><span class="sxs-lookup"><span data-stu-id="fb8b6-142">Integral Types Table</span></span>](../../../csharp/language-reference/keywords/integral-types-table.md)  
 [<span data-ttu-id="fb8b6-143">기본 제공 형식 표</span><span class="sxs-lookup"><span data-stu-id="fb8b6-143">Built-In Types Table</span></span>](../../../csharp/language-reference/keywords/built-in-types-table.md)  
 [<span data-ttu-id="fb8b6-144">암시적 숫자 변환 표</span><span class="sxs-lookup"><span data-stu-id="fb8b6-144">Implicit Numeric Conversions Table</span></span>](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md)  
 [<span data-ttu-id="fb8b6-145">명시적 숫자 변환 표</span><span class="sxs-lookup"><span data-stu-id="fb8b6-145">Explicit Numeric Conversions Table</span></span>](../../../csharp/language-reference/keywords/explicit-numeric-conversions-table.md)
