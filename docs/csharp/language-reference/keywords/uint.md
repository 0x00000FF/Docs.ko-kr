---
title: "uint(C# 참조) | Microsoft 문서"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- uint
- uint_CSharpKeyword
dev_langs:
- CSharp
helpviewer_keywords:
- uint keyword [C#]
ms.assetid: e93e42c6-ec72-4b0b-89df-2fd8d36f7a7b
caps.latest.revision: 18
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Human Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: fe4f7fcbbadee600e0ba6de70508312173d098ff
ms.lasthandoff: 03/13/2017

---
# <a name="uint-c-reference"></a>uint(C# 참조)
`uint` 키워드는 다음 표에 나와 있는 크기와 범위에 따라 값을 저장하는 정수 형식을 지정합니다.  
  
|형식|범위|크기|.NET Framework 형식|  
|----------|-----------|----------|-------------------------|  
|`uint`|0 ~ 4,294,967,295|부호 없는 32비트 정수|<xref:System.UInt32?displayProperty=fullName>|  
  
 **참고** `uint` 형식은 CLS 규격이 아닙니다. 가능한 경우 항상 `int`를 사용합니다.  
  
## <a name="literals"></a>리터럴  
 다음 예제와 같이 `uint` 형식의 변수를 선언하고 초기화할 수 있습니다.  
  
```  
  
uint myUint = 4294967290;  
```  
  
 정수 리터럴에 접미사가 없는 경우 해당 형식은 [int](../../../csharp/language-reference/keywords/int.md), `uint`, [long](../../../csharp/language-reference/keywords/long.md), [ulong](../../../csharp/language-reference/keywords/ulong.md) 등 값이 표현될 수 있는 형식의 첫 번째입니다. 이 예제에서는 `uint`입니다.  
  
```  
  
uint uInt1 = 123;  
```  
  
 다음과 같이 u 또는 U 접미사를 사용할 수도 있습니다.  
  
```  
  
uint uInt2 = 123U;  
```  
  
 `U` 또는 `u` 접미사를 사용하는 경우 리터럴 형식은 리터럴의 숫자 값에 따라 `uint` 또는 `ulong`인지 결정됩니다. 예:  
  
```  
Console.WriteLine(44U.GetType());  
Console.WriteLine(323442434344U.GetType());  
```  
  
 이 코드는 두 번째 리터럴이 너무 커서 `uint` 형식에 저장할 수 없기 때문에 `System.UInt32` 뒤에 `System.UInt64`(각각 `uint` 및 `ulong`의 기본 형식)를 표시합니다.  
  
## <a name="conversions"></a>변환  
 `uint`에서 [long](../../../csharp/language-reference/keywords/long.md), [ulong](../../../csharp/language-reference/keywords/ulong.md), [float](../../../csharp/language-reference/keywords/float.md), [double](../../../csharp/language-reference/keywords/double.md) 또는 [decimal](../../../csharp/language-reference/keywords/decimal.md)로 미리 정의된 암시적 변환이 있습니다. 예:  
  
```  
float myFloat = 4294967290;   // OK: implicit conversion to float  
```  
  
 [byte](../../../csharp/language-reference/keywords/byte.md), [ushort](../../../csharp/language-reference/keywords/ushort.md) 또는 [char](../../../csharp/language-reference/keywords/char.md)에서 `uint`로 미리 정의된 암시적 변환이 있습니다. 그렇지 않으면 캐스트를 사용해야 합니다. 예를 들어 다음 대입문은 캐스트 없이 컴파일 오류를 생성합니다.  
  
```  
long aLong = 22;  
// Error -- no implicit conversion from long:  
uint uInt1 = aLong;   
// OK -- explicit conversion:  
uint uInt2 = (uint)aLong;  
```  
  
 부동 소수점 형식에서 `uint`로의 암시적 변환은 없습니다. 예를 들어 명시적 캐스트를 사용하지 않는 경우 다음 문은 컴파일러 오류를 일으킵니다.  
  
```  
// Error -- no implicit conversion from double:  
uint x = 3.0;  
// OK -- explicit conversion:  
uint y = (uint)3.0;   
```  
  
 부동 소수점 형식 및 정수 형식이 혼합된 산술 식에 대한 자세한 내용은 [float](../../../csharp/language-reference/keywords/float.md) 및 [double](../../../csharp/language-reference/keywords/double.md)을 참조하세요.  
  
 암시적 숫자 변환 규칙에 대한 자세한 내용은 [암시적 숫자 변환 표](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md)를 참조하세요.  
  
## <a name="c-language-specification"></a>C# 언어 사양  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec_md.md)]  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.UInt32>   
 [C# 참조](../../../csharp/language-reference/index.md)   
 [C# 프로그래밍 가이드](../../../csharp/programming-guide/index.md)   
 [C# 키워드](../../../csharp/language-reference/keywords/index.md)   
 [정수 형식 표](../../../csharp/language-reference/keywords/integral-types-table.md)   
 [기본 제공 형식 표](../../../csharp/language-reference/keywords/built-in-types-table.md)   
 [암시적 숫자 변환 표](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md)   
 [명시적 숫자 변환 표](../../../csharp/language-reference/keywords/explicit-numeric-conversions-table.md)
