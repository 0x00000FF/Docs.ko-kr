---
title: byte - C# 참조
ms.custom: seodec18
ms.date: 03/14/2017
f1_keywords:
- byte
- byte_CSharpKeyword
helpviewer_keywords:
- byte keyword [C#]
ms.assetid: 111f1db9-ca32-4f0e-b497-4783517eda47
ms.openlocfilehash: fe2ef272c77b1af3a5b5a7f5bf3efb4836edcf23
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54691530"
---
# <a name="byte-c-reference"></a>byte(C# 참조)

`byte`는 다음 표에 나와 있는 값을 저장하는 정수 형식을 나타냅니다.  
  
|형식|범위|크기|.NET 형식|  
|----------|-----------|----------|-------------------------|  
|`byte`|0 ~ 255|부호 없는 8비트 정수|<xref:System.Byte?displayProperty=nameWithType>|  
  
## <a name="literals"></a>리터럴  

 10진수 리터럴, 16진수 리터럴 또는 (C# 7.0부터) 이진 리터럴을 할당하여 `byte` 변수를 선언하고 초기화할 수 있습니다. 정수 리터럴이 `byte` 범위를 벗어나는 경우(즉 <xref:System.Byte.MinValue?displayProperty=nameWithType>보다 작거나 <xref:System.Byte.MaxValue?displayProperty=nameWithType>보다 큰 경우) 컴파일 오류가 발생합니다.

다음 예제에서는 10진수, 16진수 및 이진 리터럴로 표현된 201과 같은 정수가 [int](../../../csharp/language-reference/keywords/int.md)에서 `byte` 값으로 암시적으로 변환됩니다.    
  
[!code-csharp[Byte](../../../../samples/snippets/csharp/language-reference/keywords/numeric-literals.cs#Byte)]  

> [!NOTE] 
> `0x` 또는 `0X` 접두사를 사용하여 16진수 리터럴을 나타내고, `0b` 또는 `0B` 접두사를 사용하여 이진 리터럴을 나타냅니다. 10진수 리터럴에는 접두사가 없습니다.

C# 7.0부터 가독성 향상을 위해 몇 가지 기능이 추가됐습니다. 
 - C# 7.0은 숫자 구분 기호로 밑줄 문자 `_`를 사용할 수 있습니다.
 - C# 7.2는 접두사 뒤에 이진 또는 16진수 리터럴에 대한 자리 구분 기호로 `_`을 사용할 수 있습니다. 10진수 리터럴에 선행 밑줄이 있는 것이 허용되지 않습니다.

일부 예제는 다음과 같습니다.

[!code-csharp[Byte](../../../../samples/snippets/csharp/language-reference/keywords/numeric-literals.cs#ByteS)]  
 
## <a name="conversions"></a>변환  
 `byte`에서 [short](../../../csharp/language-reference/keywords/short.md), [ushort](../../../csharp/language-reference/keywords/ushort.md), [int](../../../csharp/language-reference/keywords/int.md), [uint](../../../csharp/language-reference/keywords/uint.md), [long](../../../csharp/language-reference/keywords/long.md), [ulong](../../../csharp/language-reference/keywords/ulong.md), [float](../../../csharp/language-reference/keywords/float.md), [double](../../../csharp/language-reference/keywords/double.md) 또는 [decimal](../../../csharp/language-reference/keywords/decimal.md)로의 미리 정의된 암시적 변환이 있습니다.  
  
 더 큰 스토리지 크기의 비리터럴 숫자 형식을 `byte`로 암시적으로 변환할 수는 없습니다. 정수 형식의 스토리지 크기에 대한 자세한 내용은 [정수 형식 표](../../../csharp/language-reference/keywords/integral-types-table.md)를 참조하세요. 예를 들어 다음 두 가지 `byte` 변수 `x` 및 `y`를 고려해 보세요.  
  
```csharp  
byte x = 10, y = 20;  
```  
  
 다음 대입문은 대입 연산자의 오른쪽에 있는 산술 식이 기본적으로 `int`로 계산되므로 컴파일 오류를 생성합니다.  
  
```csharp  
// Error: conversion from int to byte:  
byte z = x + y;  
```  
  
 이 문제를 해결하려면 다음 캐스트를 사용합니다.  
  
```csharp  
// OK: explicit conversion:  
byte z = (byte)(x + y);  
```  
  
 그러나 대상 변수에 동일한 스토리지 크기 또는 더 큰 스토리지 크기가 있는 다음 명령문을 사용할 수 있습니다.  
  
```csharp  
int x = 10, y = 20;  
int m = x + y;  
long n = x + y;  
```  
  
 또한 부동 소수점 형식에서 `byte`로의 암시적 변환은 없습니다. 예를 들어 명시적 캐스트를 사용하지 않는 경우 다음 문은 컴파일러 오류를 일으킵니다.  
  
```csharp  
// Error: no implicit conversion from double:  
byte x = 3.0;   
// OK: explicit conversion:  
byte y = (byte)3.0;  
```  
  
 오버로드된 메서드를 호출할 때 캐스트를 사용해야 합니다. 예를 들어 `byte` 및 [int](../../../csharp/language-reference/keywords/int.md) 매개 변수를 사용하는 다음의 오버로드된 메서드를 살펴보세요.  
  
```csharp  
public static void SampleMethod(int i) {}  
public static void SampleMethod(byte b) {}  
```  
  
 `byte` 캐스트를 사용하면 올바른 형식이 호출됩니다. 예를 들면 다음과 같습니다.  
  
```csharp  
// Calling the method with the int parameter:  
SampleMethod(5);  
// Calling the method with the byte parameter:  
SampleMethod((byte)5);  
```  
  
 부동 소수점 형식 및 정수 형식이 혼합된 산술 식에 대한 자세한 내용은 [float](../../../csharp/language-reference/keywords/float.md) 및 [double](../../../csharp/language-reference/keywords/double.md)을 참조하세요.  
  
 암시적 숫자 변환 규칙에 대한 자세한 내용은 [암시적 숫자 변환 표](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md)를 참조하세요.  
  
## <a name="c-language-specification"></a>C# 언어 사양  

자세한 내용은 [C# 언어 사양](../language-specification/index.md)의 [정수 형식](~/_csharplang/spec/types.md#integral-types)을 참조하세요. C# 언어 사양은 C# 구문 및 사용법에 대한 신뢰할 수 있는 소스입니다.
  
## <a name="see-also"></a>참고 항목

- <xref:System.Byte>
- [C# 참조](../../../csharp/language-reference/index.md)
- [C# 프로그래밍 가이드](../../../csharp/programming-guide/index.md)
- [C# 키워드](../../../csharp/language-reference/keywords/index.md)
- [정수 계열 형식 표](../../../csharp/language-reference/keywords/integral-types-table.md)
- [기본 제공 형식 표](../../../csharp/language-reference/keywords/built-in-types-table.md)
- [암시적 숫자 변환 표](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md)
- [명시적 숫자 변환 표](../../../csharp/language-reference/keywords/explicit-numeric-conversions-table.md)
