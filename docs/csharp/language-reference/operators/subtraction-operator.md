---
title: '- 연산자 - C# 참조'
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- -_CSharpKeyword
helpviewer_keywords:
- '- operator [C#]'
- subtraction operator (-) [C#]
ms.assetid: 4de7a4fa-c69d-48e6-aff1-3130af970b2d
ms.openlocfilehash: 8cf6e8871a88e2b37b9531ecbd616289523473c7
ms.sourcegitcommit: 5c36aaa8299a2437c155700c810585aff19edbec
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/16/2019
ms.locfileid: "54333761"
---
# <a name="--operator-c-reference"></a>- 연산자(C# 참조)

`-` 연산자는 단항 또는 이항 연산자로 작동할 수 있습니다.

## <a name="remarks"></a>주의

단항 `-` 연산자는 모든 숫자 형식에 대해 미리 정의됩니다. 숫자 형식에 대한 단항 `-` 연산의 결과는 피연산자의 숫자 부정입니다.

이항 `-` 연산자는 첫 번째 피연산자에서 두 번째 피연산자를 빼도록 모든 숫자 및 열거형 형식에 대해 미리 정의되어 있습니다.

대리자 형식도 대리자 제거를 수행하는 이항 `-` 연산자를 제공합니다.

사용자 정의 형식은 단항 `-` 및 이항 `-` 연산자를 오버로드할 수 있습니다. 자세한 내용은 [operator 키워드](../keywords/operator.md)를 참조하세요.

## <a name="example"></a>예제

[!code-csharp[csRefOperators#40](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefOperators/CS/csrefOperators.cs#40)]

## <a name="see-also"></a>참고 항목

- [C# 참조](../index.md)
- [C# 프로그래밍 가이드](../../programming-guide/index.md)
- [C# 연산자](index.md)