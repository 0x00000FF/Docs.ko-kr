---
title: double 키워드 - C# 참조
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- double
- double_CSharpKeyword
helpviewer_keywords:
- double data type [C#]
ms.assetid: 0980e11b-6004-4102-abcf-cfc280fc6991
ms.openlocfilehash: f4d6bb4eb698e4afbda6571ba382e828a5f836a4
ms.sourcegitcommit: 9b1ac36b6c80176fd4e20eb5bfcbd9d56c3264cf
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/28/2019
ms.locfileid: "67424271"
---
# <a name="double-c-reference"></a>double(C# 참조)

`double` 키워드는 64비트 부동 소수점 값을 저장하는 단순 형식을 나타냅니다. 다음 표에서는 `double` 형식의 전체 자릿수와 근사 범위를 보여 줍니다.

|형식|근사 범위|전체 자릿수|.NET 형식|
|----------|-----------------------|---------------|-------------------------|
|`double`|±5.0 × 10<sup>−324</sup> ~ ±1.7 × 10<sup>308</sup>|~15-17개 자릿수|<xref:System.Double?displayProperty=nameWithType>|

## <a name="literals"></a>리터럴

기본적으로 대입 연산자 오른쪽의 실수 리터럴은 `double`로 처리됩니다. 그러나 정수가 `double`로 처리되도록 하려면 접미사 d 또는 D를 사용하세요. 예를 들면 다음과 같습니다.

```csharp
double x = 3D;
```

## <a name="conversions"></a>변환

식에서 숫자 정수 형식과 부동 소수점 형식을 함께 사용할 수 있습니다. 이 경우 정수 형식이 부동 소수점 형식으로 변환됩니다. 식의 계산은 다음 규칙에 따라 수행됩니다.

- 부동 소수점 형식 중 하나가 `double`이면 식은 관계형 비교 및 같음에 대한 비교에서 `double` 또는 [bool](../../../csharp/language-reference/keywords/bool.md)로 계산됩니다.

- 식에 `double` 유형이 없으면 관계형 비교 및 같음에 대한 비교에서 [float](../../../csharp/language-reference/keywords/float.md) 또는 [bool](../../../csharp/language-reference/keywords/bool.md)로 계산됩니다.

 부동 소수점 식에는 다음과 같은 값 집합이 포함될 수 있습니다.

- 양수 및 음수 0.

- 양수 및 음수 무한대.

- NaN(Not-a-Number) 값.

- 한정된 0이 아닌 값의 집합.

이러한 값에 대한 자세한 내용은 [IEEE](https://www.ieee.org) 웹 사이트에서 제공되는 이진 부동 소수점 연산에 대한 IEEE 표준을 참조하세요.

## <a name="example"></a>예

다음 예제에서는 [int](../builtin-types/integral-numeric-types.md), [short](../../../csharp/language-reference/builtin-types/integral-numeric-types.md), [float](../../../csharp/language-reference/keywords/float.md) 및 `double`을 함께 더하여 `double` 결과를 제공합니다.

[!code-csharp[csrefKeywordsTypes#9](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsTypes/CS/keywordsTypes.cs#9)]

## <a name="c-language-specification"></a>C# 언어 사양

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a>참고 항목

- [C# 참조](../../../csharp/language-reference/index.md)
- [C# 프로그래밍 가이드](../../../csharp/programming-guide/index.md)
- [C# 키워드](../../../csharp/language-reference/keywords/index.md)
- [기본값 표](../../../csharp/language-reference/keywords/default-values-table.md)
- [기본 제공 형식 표](../../../csharp/language-reference/keywords/built-in-types-table.md)
- [부동 소수점 형식 표](../../../csharp/language-reference/keywords/floating-point-types-table.md)
- [암시적 숫자 변환 표](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md)
- [명시적 숫자 변환 표](../../../csharp/language-reference/keywords/explicit-numeric-conversions-table.md)
