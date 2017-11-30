---
title: "ulong(C# 참조)"
ms.date: 03/14/2017
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
f1_keywords:
- ulong_CSharpKeyword
- ulong
helpviewer_keywords: ulong keyword [C#]
ms.assetid: f2ece624-837a-40cf-92c5-343e7f33397c
caps.latest.revision: "16"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 2058d9f6a228b13938fe08d7e2fb11e3b9f4600a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="ulong-c-reference"></a>ulong(C# 참조)

`ulong` 키워드는 다음 표에 나와 있는 크기와 범위에 따라 값을 저장하는 정수 형식을 나타냅니다.  
  
|형식|범위|크기|.NET Framework 형식|  
|----------|-----------|----------|-------------------------|  
|`ulong`|0 ~ 18,446,744,073,709,551,615|부호 없는 64비트 정수|<xref:System.UInt64?displayProperty=nameWithType>|  
  
## <a name="literals"></a>리터럴  

10진수 리터럴, 16진수 리터럴 또는 (C# 7부터) 이진 리터럴을 할당하여 `ulong` 변수를 선언하고 초기화할 수 있습니다.  정수 리터럴이 `ulong` 범위를 벗어나는 경우(즉 <xref:System.UInt64.MinValue?displayProperty=nameWithType>보다 작거나 <xref:System.UInt64.MaxValue?displayProperty=nameWithType>보다 큰 경우) 컴파일 오류가 발생합니다. 

다음 예제에서는 10진수, 16진수 및 이진 리터럴로 표현된 7,934,076,125와 같은 정수가 `ulong` 값에 할당됩니다.  
  
[!code-csharp[ulong](../../../../samples/snippets/csharp/language-reference/keywords/numeric-literals.cs#ULong)]  

> [!NOTE] 
> `0x` 또는 `0X` 접두사를 사용하여 16진수 리터럴을 나타내고, `0b` 또는 `0B` 접두사를 사용하여 이진 리터럴을 나타냅니다. 10진수 리터럴에는 접두사가 없습니다. 

부터 C# 7, 몇 가지 기능이 추가 된 가독성을 향상 시키기 합니다. 
 - C# 7.0 밑줄 문자를 사용할 수 있습니다. `_`,으로 숫자 구분 기호입니다.
 - C# 7.2 허용 `_` 접두사 뒤에 대 한 이진 또는 16 진수 리터럴, 자리 구분 기호로 사용할 수 있습니다. 10 진수 리터럴은 선행 밑줄이에 허용 되지 않습니다.

몇 가지 예는 다음과 같습니다.

[!code-csharp[long](../../../../samples/snippets/csharp/language-reference/keywords/numeric-literals.cs#LongS)]  
 
 형식을 나타내는 접미사가 정수 리터럴에 포함되어 있을 수도 있습니다. `UL` 또는 `ul` 접미사는 숫자 리터럴을 `ulong` 값으로 명확하게 식별합니다. 리터럴 값이 <xref:System.Int64.MaxValue?displayProperty=nameWithType>를 초과할 경우 `L` 접미사는 `ulong`을 나타냅니다. 또한 리터럴 값이 <xref:System.UInt32.MaxValue?displayProperty=nameWithType>를 초과할 경우 `U` 또는 `ulong` 접미사는 `u`을 나타냅니다. 다음 예제에서는 `ul` 접미사를 사용하여 정수(long)를 나타냅니다.
 
[!code-csharp[ulsuffix](../../../../samples/snippets/csharp/language-reference/keywords/numeric-suffixes.cs#2)]

정수 리터럴에 접미사가 없는 경우 해당 형식은 값이 표현될 수 있는 다음 형식 중 첫 번째 형식입니다. 

1. [int](int.md)
2. [uint](../../../csharp/language-reference/keywords/uint.md)
3. [long](long.md)
4. `ulong`

## <a name="compiler-overload-resolution"></a>컴파일러 오버로드 확인
  
 접미사는 일반적으로 오버로드된 메서드를 호출할 때 사용됩니다. 예를 들어 `ulong` 및 [int](../../../csharp/language-reference/keywords/int.md) 매개 변수를 사용하는 다음의 오버로드된 메서드를 살펴보세요.  
  
```csharp  
public static void SampleMethod(int i) {}  
public static void SampleMethod(ulong l) {}  
```  
  
 `ulong` 매개 변수와 함께 접미사를 사용하면 올바른 형식이 호출됩니다. 예를 들면 다음과 같습니다.  
  
```csharp  
SampleMethod(5);    // Calling the method with the int parameter  
SampleMethod(5UL);  // Calling the method with the ulong parameter  
```  
  
## <a name="conversions"></a>변환  
 `ulong`에서 [float](../../../csharp/language-reference/keywords/float.md), [double](../../../csharp/language-reference/keywords/double.md) 또는 [decimal](../../../csharp/language-reference/keywords/decimal.md)로 미리 정의된 암시적 변환이 있습니다.  
  
 `ulong`에서 정수 형식으로의 암시적 변환은 없습니다. 예를 들어 다음 문은 명시적 캐스트 없이 컴파일 오류를 생성합니다.  
  
```csharp  
long long1 = 8UL;   // Error: no implicit conversion from ulong  
```  
  
 [byte](../../../csharp/language-reference/keywords/byte.md), [ushort](../../../csharp/language-reference/keywords/ushort.md), [uint](../../../csharp/language-reference/keywords/uint.md) 또는 [char](../../../csharp/language-reference/keywords/char.md)에서 `ulong`으로 미리 정의된 암시적 변환이 있습니다.  
  
 또한 부동 소수점 형식에서 `ulong`로의 암시적 변환은 없습니다. 예를 들어 명시적 캐스트를 사용하지 않는 경우 다음 문은 컴파일러 오류를 일으킵니다.  
  
```csharp  
// Error -- no implicit conversion from double:  
ulong x = 3.0;  
// OK -- explicit conversion:  
ulong y = (ulong)3.0;    
```  
  
 부동 소수점 형식 및 정수 형식이 혼합된 산술 식에 대한 자세한 내용은 [float](../../../csharp/language-reference/keywords/float.md) 및 [double](../../../csharp/language-reference/keywords/double.md)을 참조하세요.  
  
 암시적 숫자 변환 규칙에 대한 자세한 내용은 [암시적 숫자 변환 표](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md)를 참조하세요.  
  
## <a name="c-language-specification"></a>C# 언어 사양  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.UInt64>  
 [C# 참조](../../../csharp/language-reference/index.md)  
 [C# 프로그래밍 가이드](../../../csharp/programming-guide/index.md)  
 [C# 키워드](../../../csharp/language-reference/keywords/index.md)  
 [정수 계열 형식 표](../../../csharp/language-reference/keywords/integral-types-table.md)  
 [기본 제공 형식 표](../../../csharp/language-reference/keywords/built-in-types-table.md)  
 [암시적 숫자 변환 표](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md)  
 [명시적 숫자 변환 표](../../../csharp/language-reference/keywords/explicit-numeric-conversions-table.md)
