---
title: 네임스페이스 키워드 - C# 참조
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- namespace_CSharpKeyword
- namespace
helpviewer_keywords:
- namespace keyword [C#]
- scope [C#]
ms.assetid: 0a788423-9110-42e0-97d9-bda41ca4870f
ms.openlocfilehash: b5c6b8081c188d5b184930222d54ad8f4b5d7a71
ms.sourcegitcommit: bdd930b5df20a45c29483d905526a2a3e4d17c5b
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/11/2018
ms.locfileid: "53242765"
---
# <a name="namespace-c-reference"></a>namespace(C# 참조)

`namespace` 키워드는 관련 개체 집합을 포함하는 범위를 선언하는 데 사용됩니다. 네임스페이스를 사용하여 코드 요소를 구성하고 전역적으로 고유한 형식을 만들 수 있습니다.

[!code-csharp[csrefKeywordsNamespace#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsNamespace/CS/csrefKeywordsNamespace.cs#1)]

## <a name="remarks"></a>설명

네임스페이스 내에서 다음 형식 중 0개 이상을 선언할 수 있습니다.

- 다른 네임스페이스

- [class](class.md)

- [interface](interface.md)

- [struct](struct.md)

- [enum](enum.md)

- [delegate](delegate.md)

C# 소스 파일에서 네임스페이스를 명시적으로 선언하는지 여부에 관계없이 컴파일러는 기본 네임스페이스를 추가합니다. 전역 네임스페이스라고도 하는 이 명명되지 않은 네임스페이스는 모든 파일에 있습니다. 전역 네임스페이스의 모든 식별자는 명명된 네임스페이스에서 사용할 수 있습니다.

네임스페이스는 암시적으로 공용 액세스를 사용하며 이 설정은 수정할 수 없습니다. 네임스페이스의 요소에 할당할 수 있는 액세스 한정자에 대한 설명은 [액세스 한정자](access-modifiers.md)를 참조하세요.

둘 이상의 선언에서 네임스페이스를 정의할 수 있습니다. 예를 들어 다음 예제에서는 `MyCompany` 네임스페이스의 일부로 두 클래스를 정의합니다.

[!code-csharp[csrefKeywordsNamespace#2](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsNamespace/CS/csrefKeywordsNamespace.cs#2)]

## <a name="example"></a>예

다음 예제에서는 중첩된 네임스페이스에서 정적 메서드를 호출하는 방법을 보여 줍니다.

[!code-csharp[csrefKeywordsNamespace#3](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsNamespace/CS/csrefKeywordsNamespace.cs#3)]

## <a name="related-resources"></a>관련 참고 자료

네임스페이스를 사용하는 방법에 대한 자세한 내용은 다음 항목을 참조하세요.

- [네임스페이스](../../programming-guide/namespaces/index.md)

- [네임스페이스 사용](../../programming-guide/namespaces/using-namespaces.md)

- [방법: 전역 네임스페이스 별칭 사용](../../programming-guide/namespaces/how-to-use-the-global-namespace-alias.md)

## <a name="c-language-specification"></a>C# 언어 사양

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a>참고 항목

- [C# 참조](../../language-reference/index.md)
- [C# 프로그래밍 가이드](../../programming-guide/index.md)
- [C# 키워드](index.md)
- [네임스페이스 키워드](namespace-keywords.md)
- [using](using.md)