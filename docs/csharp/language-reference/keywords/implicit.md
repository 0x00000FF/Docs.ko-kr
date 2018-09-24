---
title: implicit(C# 참조)
ms.date: 07/20/2015
f1_keywords:
- implicit
- implicit_CSharpKeyword
helpviewer_keywords:
- implicit keyword [C#]
ms.assetid: 34db590e-eb3a-4f11-88d0-ffb3cd753dab
ms.openlocfilehash: 70379136fd4b14403eac919ac15590250b17b416
ms.sourcegitcommit: ad99773e5e45068ce03b99518008397e1299e0d1
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/23/2018
ms.locfileid: "46702699"
---
# <a name="implicit-c-reference"></a>implicit(C# 참조)

`implicit` 키워드는 암시적 사용자 정의 형식 변환 연산자를 선언하는 데 사용됩니다. 변환 시 데이터가 손실되지 않는 경우 이 키워드를 통해 사용자 정의 형식과 다른 형식 간에 암시적 변환을 사용할 수 있습니다.

## <a name="example"></a>예

[!code-csharp[csrefKeywordsConversion#5](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsConversion/CS/csrefKeywordsConversion.cs#5)]

암시적 변환은 불필요한 캐스트를 제거하여 소스 코드 가독성을 향상할 수 있습니다. 그러나 암시적 변환 시 프로그래머가 명시적으로 형식 간에 캐스팅할 필요가 없으므로 예기치 않은 결과를 방지하기 위해 주의해야 합니다. 일반적으로 암시적 변환 연산자는 예외를 throw하지 않고 정보가 손실되지 않으므로 프로그래머에게 알리지 않고 안전하게 사용할 수 있습니다. 변환 연산자가 이러한 조건에 맞지 않는 경우 `explicit`로 표시되어야 합니다. 자세한 내용은 [변환 연산자 사용](../../../csharp/programming-guide/statements-expressions-operators/using-conversion-operators.md)을 참조하세요.

## <a name="c-language-specification"></a>C# 언어 사양

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a>참고 항목

- [C# 참조](../index.md)  
- [C# 프로그래밍 가이드](../../programming-guide/index.md)  
- [C# 키워드](index.md)  
- [explicit](explicit.md)  
- [연산자(C# 참조)](operator.md)  
- [방법: 구조체 간의 사용자 정의 변환 구현](../../programming-guide/statements-expressions-operators/how-to-implement-user-defined-conversions-between-structs.md)
