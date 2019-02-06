---
title: < 연산자 - C# 참조
ms.custom: seodec18
ms.date: 12/18/2018
f1_keywords:
- <_CSharpKeyword
helpviewer_keywords:
- less than operator (<) [C#]
- < operator [C#]
ms.assetid: 38cb91e6-79a6-48ec-9c1e-7b71fd8d2b41
ms.openlocfilehash: ab21e32b7609bc0c8753b42ccf8b6091bf3ad57b
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/30/2019
ms.locfileid: "55286639"
---
# <a name="-operator-c-reference"></a>\< 연산자(C# 참조)

"작음" 관계 연산자 `<`은 첫 번째 피연산자가 두 번째 피연산자 보다 작으면 `true`를 반환하고, 그렇지 않으면 `false`를 반환합니다. 모든 숫자 및 열거형 형식은 `<` 연산자를 지원합니다. 동일한 [열거형](../keywords/enum.md) 형식의 피연산자의 경우 기본 정수 형식의 해당 값이 비교됩니다.

> [!NOTE]
> 관계형 연산자 `==`, `>`, `<`, `>=` 및 `<=`의 경우 피연산자 중 하나가 숫자(<xref:System.Double.NaN?displayProperty=nameWithType> 또는 <xref:System.Single.NaN?displayProperty=nameWithType>)가 아니s며 연산의 결과는 `false`입니다. 이는 `NaN` 값이 다른 `double`(또는 `float`) 값보다 크거나, 작거나, 같지 않음을 의미합니다. 자세한 내용과 예제는 <xref:System.Double.NaN?displayProperty=nameWithType> 또는 <xref:System.Single.NaN?displayProperty=nameWithType> 참조 문서를 참조하세요.

다음 예제에서는 `<` 연산자의 사용법을 보여 줍니다.

[!code-csharp-interactive[less than example](~/samples/snippets/csharp/language-reference/operators/GreaterAndLessOperatorsExamples.cs#Less)]

## <a name="operator-overloadability"></a>연산자 오버로드 가능성

사용자 정의 형식은 `<` 연산자를 [오버로드](../keywords/operator.md)할 수 있습니다. 형식이 "작음" 연산자 `<`을 오버로드하는 경우 ["큼" 연산자](greater-than-operator.md) `>`도 오버로드해야 합니다.

## <a name="c-language-specification"></a>C# 언어 사양

자세한 내용은 [C# 언어 사양](../language-specification/index.md)의 [관계형 및 형식 테스트 연산자](~/_csharplang/spec/expressions.md#relational-and-type-testing-operators) 섹션을 참조하세요.

## <a name="see-also"></a>참고 항목

- [C# 참조](../index.md)
- [C# 프로그래밍 가이드](../../programming-guide/index.md)
- [C# 연산자](index.md)
- [<= 연산자](less-than-equal-operator.md)
- <xref:System.IComparable%601?displayProperty=nameWithType>
