---
title: 캐스팅 및 변환(F#)
description: 'F # 프로그래밍 언어로 제공 하는 방법을 변환 연산자 다양 한 기본 형식 간의 산술 변환에 알아봅니다.'
keywords: visual f#, f#, 함수형 프로그래밍
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: db30db67-da21-4206-bf0c-9211bd3cb22f
ms.openlocfilehash: df8352b0dd8651f1480515311454a218ea79b971
ms.sourcegitcommit: b750a8e3979749b214e7e10c82efb0a0524dfcb1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/09/2018
---
# <a name="casting-and-conversions-f"></a>캐스팅 및 변환(F#)

이 항목에서는 F #의 형식 변환에 대 한 지원을 설명 합니다.

## <a name="arithmetic-types"></a>산술 형식
F #은 변환 연산자 다양 한 기본 형식 사이의 변환의 산술와 같은 정수 및 부동 소수점 형식 간의 합니다. 변환 연산자는 정수 계열 및 char를 얻게 하 고 선택 되지 않은 형식을 연산자는 부동 소수점 및 `enum` 변환 연산자는 그렇지 않습니다. 선택 되지 않은 형식에 정의 된 `Microsoft.FSharp.Core.Operators` checked 형식은에 정의 된 및 `Microsoft.FSharp.Core.Operators.Checked`합니다. Checked 형식은 오버플로 검사 하 고 결과 값은 대상 유형의 제한을 초과 하면 런타임 예외를 생성 합니다.

이러한 연산자의 각 대상 형식의 이름으로 동일한 이름을 있습니다. 예를 들어 다음 코드를 있는 형식을 명시적으로 주석을에서 `byte` 두 가지 의미를 표시 합니다. 맨 처음 발견 되는 형식이 고 두 번째는 변환 연산자.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4401.fs)]

다음 표에서 F #에 정의 된 변환 연산자를 보여 줍니다.

|연산자|설명|
|--------|-----------|
|`byte`|부터 최상위에 이르는 8 비트 부호 없는 형식으로 변환 합니다.|
|`sbyte`|부호 있는 바이트를 변환 합니다.|
|`int16`|16 비트 부호 있는 정수로 변환 합니다.|
|`uint16`|16 비트 부호 없는 정수로 변환 합니다.|
|`int32, int`|32 비트 부호 있는 정수로 변환 합니다.|
|`uint32`|32 비트 부호 없는 정수로 변환 합니다.|
|`int64`|64 비트 부호 있는 정수로 변환 합니다.|
|`uint64`|64 비트 부호 없는 정수로 변환 합니다.|
|`nativeint`|네이티브 정수로 변환 합니다.|
|`unativeint`|네이티브 부호 없는 정수로 변환 합니다.|
|`float, double`|64 비트 배정밀 IEEE 부동 소수점 숫자로 변환 합니다.|
|`float32, single`|32 비트 단 정밀도 IEEE 부동 소수점 숫자로 변환 합니다.|
|`decimal`|변환할 `System.Decimal`합니다.|
|`char`|변환할 `System.Char`, 유니코드 문자입니다.|
|`enum`|열거 형식으로 변환 합니다.|
기본 제공 기본 유형 외에도 이러한 연산자를 구현 하는 형식과 함께 사용할 수 있습니다 `op_Explicit` 또는 `op_Implicit` 적절 한 시그니처가 메서드. 예를 들어는 `int` 변환 연산자를 정적 메서드를 제공 하는 모든 형식을 사용할 `op_Explicit` 형식을 매개 변수로 사용 하 고 반환 하는 `int`합니다. 반환 형식 그 메서드를 오버 로드할 수 없는 일반 규칙에 특별 한 예외로 이렇게 하려면에 대 한 `op_Explicit` 및 `op_Implicit`합니다.

## <a name="enumerated-types"></a>열거 형식
`enum` 연산자의 유형을 나타내는 하나의 형식 매개 변수를 사용 하는 일반 연산자는는 `enum` 변환할 수 있습니다. 열거 형식으로 변환 하는 경우 입력의 형식을 확인 하려고 하는 유추는 `enum` 를 변환 합니다. 다음 예에서 변수 `col1` 명시적으로 주석을 달지 않으면 되지만 해당 형식은 나오는 같음 테스트에서 유추 됩니다. 따라서 컴파일러는 변환 하는 추론할 수는 `Color` 열거형입니다. 형식 주석을 입력할 수 있습니다와 마찬가지로 `col2` 다음 예에서 합니다.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4402.fs)]
    
다음 코드 처럼 형식 매개 변수와 대상 열거형 형식을 명시적으로 지정할 수도 있습니다.

```fsharp
let col3 = enum<Color> 3
```

Note 열거형의 내부 형식이 변환 되는 형식의와 호환 되는 경우에 열거 작업을 캐스팅 합니다. 다음 코드에서 변환이 간에 일치 하지 않아 컴파일하는 데 실패 `int32` 및 `uint32`합니다.

```fsharp
// Error: types are incompatible
let col4 : Color = enum 2u
```

자세한 내용은 참조 [열거형](enumerations.md)합니다.

## <a name="casting-object-types"></a>개체 형식 캐스팅
개체 계층에서 형식 간의 변환 개체 지향 프로그래밍 기본입니다. 변환의 기본 유형에: (업 캐스트)을 캐스팅 하 고 (좋기는) 아래로 캐스팅 합니다. 계층 구조 위로 캐스팅은 기본 개체 참조에 대 한 파생 된 개체 참조에서 캐스팅을 의미합니다. 이러한 캐스트는 기본 클래스는 파생된 클래스의 상속 계층 구조에서 정상적으로 작동 하도록 보장 됩니다. 파생 된 개체 참조에 대 한 기준 개체 참조는 계층 구조 아래로 캐스팅 개체가 실제로 올바른 대상 (파생) 형식 또는 대상 형식에서 파생 되는 형식 인스턴스의 경우에 성공 합니다.

F #에서는 이러한 유형의 변환에 대 한 연산자를 제공 합니다. `:>` 연산자는 계층 구조 위로 캐스팅 및 `:?>` 연산자는 계층 구조 아래로 캐스팅 합니다.

### <a name="upcasting"></a>업 캐스트
대부분의 개체 지향 언어 업 캐스트는 암시적; F #에서 규칙은 약간 다릅니다. 업 캐스트는 개체 형식에 메서드를 인수를 전달 하는 경우 자동으로 적용 됩니다. 그러나 모듈의 let 바인딩 함수에 대 한 업캐스팅 자동이 아니면 유연한 형식으로 매개 변수 형식을 선언 하지 않는 한 합니다. 자세한 내용은 참조 [유연한 형식](flexible-Types.md)합니다.

`:>` 연산자로 수행 된 정적 캐스팅, 캐스트의 성공 컴파일 타임에 결정 됩니다. 사용 하는 캐스팅이 `:>` 성공적으로 컴파일되면 유효한 캐스팅 하 고 실행 시 오류가 발생할 가능성이 없습니다 있어서 합니다.

사용할 수도 있습니다는 `upcast` 이러한 변환을 수행 하는 연산자입니다. 다음 식은 계층 구조 변환을 지정합니다.

```fsharp
upcast expression
```

Upcast 연산자를 사용 하면 컴파일러는 컨텍스트에서 변환 하는 형식을 유추 하려고 합니다. 컴파일러가 대상 형식을 확인할 수 없는 경우 컴파일러는 오류를 보고 합니다.

### <a name="downcasting"></a>좋기
`:?>` 연산자로 수행 동적 캐스팅을 캐스팅 성공 런타임에 결정 됩니다. 사용 하는 캐스트는 `:?>` ; 컴파일 타임에 연산자를 선택 하지 않으면 하지만 런타임 시 지정된 된 형식으로 캐스팅 하는 시도가 이루어집니다. 개체가 대상 형식과 호환 이면 캐스팅에 성공 합니다. 런타임에서 발생 하는 개체가 대상 형식과 호환 되지 않으면는 `InvalidCastException`합니다.

사용할 수도 있습니다는 `downcast` 동적 형식 변환을 수행 하는 연산자입니다. 다음 식은 프로그램 컨텍스트를 통해 유추 된 형식으로의 계층 구조 아래로 변환을 지정 합니다.

```fsharp
downcast expression
```

에 대 한는 `upcast` 연산자를 컴파일러에서 컨텍스트를 특정 대상 형식을 유추할 수 없습니다 경우 오류를 보고 합니다.

다음 코드에서는 사용 된 `:>` 및 `:?>` 연산자입니다. 코드를 보면는 `:?>` 연산자 가장 잘 알고 있는 경우 변환 성공할 지 throw 하기 때문에 사용 되는 `InvalidCastException` 경우 변환이 실패 합니다. 변환이 성공할 지를 사용 하는 형식 테스트 알 수 없는 경우는 `match` 예외를 생성 하는 오버 헤드를 방지 하기 때문에 식은 것이 좋습니다.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4403.fs)]

때문에 제네릭 연산자 `downcast` 및 `upcast` 인수 및 반환 형식을 위의 코드에서 형식 유추를 사용 하 여 바꿀 수 있습니다,

```fsharp
let base1 = d1 :> Base1
```

다음 문자열로 바꾸세요.

```fsharp
let base1 = upcast d1
```

이전 코드에서 형식 인수 및 반환 형식은 `Derived1` 및 `Base1`각각.

형식 테스트에 대 한 자세한 내용은 참조 [일치 식](match-Expressions.md)합니다.

## <a name="see-also"></a>참고 항목
[F# 언어 참조](index.md)
