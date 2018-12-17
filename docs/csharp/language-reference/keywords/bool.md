---
title: bool 키워드(C# 참조)
ms.date: 07/20/2015
f1_keywords:
- bool_CSharpKeyword
- bool
helpviewer_keywords:
- bool keyword [C#]
ms.assetid: 551cfe35-2632-4343-af49-33ad12da08e2
ms.openlocfilehash: a5a5fa37905df9fb9369e9c0c26a2e39d03353f2
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/10/2018
ms.locfileid: "53128325"
---
# <a name="bool-c-reference"></a>bool(C# 참조)

`bool` 키워드는 <xref:System.Boolean?displayProperty=nameWithType>의 별칭입니다. 부울 값 [true](true-literal.md) 및 [false](false-literal.md)를 저장할 변수를 선언하는 데 사용됩니다.

> [!NOTE]
> `null` 값을 가질 수 있는 부울 변수가 필요한 경우 `bool?`를 사용합니다. 자세한 내용은 [nullable 형식 사용](../../programming-guide/nullable-types/using-nullable-types.md) 문서의 [bool? 형식](../../programming-guide/nullable-types/using-nullable-types.md#the-bool-type) 섹션을 참조하세요.

## <a name="literals"></a>리터럴

`bool` 변수에 부울 값을 할당할 수 있습니다. `bool`로 계산되는 식을 `bool` 변수에 할당할 수도 있습니다.

[!code-csharp[csrefKeywordsTypes#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsTypes/CS/keywordsTypes.cs#1)]

`bool` 변수의 기본값은 `false`입니다. `bool?` 변수의 기본값은 `null`입니다.

## <a name="conversions"></a>변환

C++에서 `bool` 형식의 값은 `int` 형식의 값으로 변환될 수 있습니다. 즉, `false`는 0과 같고 `true`는 0이 아닌 값과 같습니다. C#에는 `bool` 형식과 다른 형식 간의 변환이 없습니다. 예를 들어 다음 `if` 문은 C#에서 유효하지 않습니다.

[!code-csharp[csrefKeywordsTypes#2](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsTypes/CS/keywordsTypes.cs#2)]

`int` 형식의 변수를 테스트하려면 다음과 같이 0과 같은 값에 변수를 명시적으로 비교해야 합니다.

[!code-csharp[csrefKeywordsTypes#3](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsTypes/CS/keywordsTypes.cs#3)]

## <a name="example"></a>예

이 예제에서는 키보드에서 문자를 입력하면 프로그램에서 입력 문자가 문자인지 확인합니다. 문자인 경우 소문자 또는 대문자인지 확인합니다. 이러한 검사는 <xref:System.Char.IsLetter%2A> 및 <xref:System.Char.IsLower%2A>를 사용하여 수행되며, 둘 다 `bool` 형식을 반환합니다.

[!code-csharp[csrefKeywordsTypes#4](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsTypes/CS/keywordsTypes.cs#4)]

## <a name="c-language-specification"></a>C# 언어 사양

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a>참고 항목

- [C# 참조](../../../csharp/language-reference/index.md)  
- [C# 프로그래밍 가이드](../../../csharp/programming-guide/index.md)  
- [C# 키워드](../../../csharp/language-reference/keywords/index.md)  
- [정수 계열 형식 표](../../../csharp/language-reference/keywords/integral-types-table.md)  
- [기본 제공 형식 표](../../../csharp/language-reference/keywords/built-in-types-table.md)  
- [암시적 숫자 변환 표](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md)  
- [명시적 숫자 변환 표](../../../csharp/language-reference/keywords/explicit-numeric-conversions-table.md)  