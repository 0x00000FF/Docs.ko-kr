---
title: () 연산자(C# 참조)
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- ()_CSharpKeyword
helpviewer_keywords:
- type conversion [C#], () operator
- cast operator [C#]
- () operator [C#]
ms.assetid: 846e1f94-8a8c-42fc-a42c-fbd38e70d8cc
caps.latest.revision: 22
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 6d62e6c93dcc69c892d4ca96ace3806cb1c8d989
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="-operator-c-reference"></a>() 연산자(C# 참조)
괄호는 식에서 연산의 순서를 지정하는 데 사용될 뿐만 아니라 다음 작업을 수행하는 데도 사용됩니다.  
  
1.  캐스트 또는 형식 변환을 지정합니다.  
  
     [!code-csharp[csRefOperators#1](../../../csharp/language-reference/operators/codesnippet/CSharp/invocation-operator_1.cs)]  
  
2.  메서드 또는 대리자를 호출합니다.  
  
     [!code-csharp[csRefOperators#2](../../../csharp/language-reference/operators/codesnippet/CSharp/invocation-operator_2.cs)]  
  
## <a name="remarks"></a>설명  
 캐스트는 한 형식에서 다른 형식으로의 변환 연산자를 명시적으로 호출합니다. 이러한 변환 연산자가 정의되지 않은 경우 캐스트가 실패합니다. 변환 연산자를 정의하려면 [explicit](../../../csharp/language-reference/keywords/explicit.md) 및 [implicit](../../../csharp/language-reference/keywords/implicit.md)를 참조하세요.  
  
 `()` 연산자를 오버로드할 수 없습니다.  
  
 자세한 내용은 [캐스팅 및 형식 변환](../../../csharp/programming-guide/types/casting-and-type-conversions.md)을 참조하세요.  
  
 캐스트 식은 모호한 구문이 될 수 있습니다. 예를 들어 `(x)–y` 식은 캐스트 식(-y를 형식 x로 캐스트) 또는 괄호로 묶은 식과 결합된 더하기 식으로 해석될 수 있습니다.  
  
 메서드 호출에 대한 자세한 내용은 [메서드](../../../csharp/programming-guide/classes-and-structs/methods.md)를 참조하세요.  
  
## <a name="c-language-specification"></a>C# 언어 사양  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [C# 참조](../../../csharp/language-reference/index.md)  
 [C# 프로그래밍 가이드](../../../csharp/programming-guide/index.md)  
 [C# 연산자](../../../csharp/language-reference/operators/index.md)
