---
title: '&amp; 연산자(C# 참조)'
ms.date: 04/04/2018
f1_keywords:
- '&_CSharpKeyword'
helpviewer_keywords:
- bitwise AND operator [C#]
- ampersand operator (&) [C#]
- '& operator [C#]'
- AND operator (&) [C#]
ms.assetid: afa346d5-90ec-4b1f-a2c8-3881f018741d
ms.openlocfilehash: b257c7d41618464e26ab3b54bcfb1f1e2c2e420e
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/02/2018
ms.locfileid: "43467376"
---
# <a name="amp-operator-c-reference"></a>&amp; 연산자(C# 참조)
`&` 연산자는 단항 또는 이항 연산자로 작동할 수 있습니다.  
  
## <a name="remarks"></a>설명  
 단항 `&` 연산자는 해당 피연산자의 주소를 반환합니다([안전하지 않은](../../../csharp/language-reference/keywords/unsafe.md) 컨텍스트 필요).  
  
 이항 `&` 연산자는 정수 형식 및 `bool`에 대해 미리 정의되어 있습니다. 정수 형식의 경우 & 연산자는 해당 피연산자의 논리적 비트 AND를 계산합니다. `bool` 피연산자의 경우 & 연산자는 해당 피연산자의 논리적 AND 연산을 계산합니다. 즉, 피연산자가 둘 다 `true`일 경우에만 결과가 `true`입니다.  
  
 이진 `&` 연산자는 [기존 AND 연산자](../../../csharp/language-reference/operators/conditional-and-operator.md) `&&`와 달리 첫 번째 연산자의 값에 상관없이 두 피연산자를 모두 계산합니다. 예:  
  
 [!code-csharp[csRefOperators#37](../../../csharp/language-reference/operators/codesnippet/CSharp/and-operator_1.cs)]  
  
 사용자 정의 형식으로 이항 `&` 연산자를 오버로드할 수 있습니다([operator](../../../csharp/language-reference/keywords/operator.md) 참조). 정수 계열 형식에 대한 연산은 일반적으로 열거형에서 허용됩니다. 이항 연산자가 오버로드되면 해당 대입 연산자도 암시적으로 오버로드됩니다.  
  
## <a name="example"></a>예  
 [!code-csharp[csRefOperators#38](../../../csharp/language-reference/operators/codesnippet/CSharp/and-operator_2.cs)]  
  
## <a name="see-also"></a>참고 항목

- [C# 참조](../../../csharp/language-reference/index.md)  
- [C# 프로그래밍 가이드](../../../csharp/programming-guide/index.md)  
- [C# 연산자](../../../csharp/language-reference/operators/index.md)
