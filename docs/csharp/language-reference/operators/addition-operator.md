---
title: + 연산자(C# 참조)
ms.date: 07/20/2015
f1_keywords:
- +_CSharpKeyword
helpviewer_keywords:
- + operator [C#]
- concatenation operator [C#]
- addition operator [C#]
ms.assetid: 93e56486-bb42-43c1-bd43-60af11e64e67
ms.openlocfilehash: d4a269c07e0d6dc2ac6a6a101f200653c6ea7a29
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33267409"
---
# <a name="-operator-c-reference"></a>+ 연산자(C# 참조)
`+` 연산자는 단항 또는 이항 연산자로 작동할 수 있습니다.  
  
## <a name="remarks"></a>설명  
 단항 `+` 연산자는 모든 숫자 형식에 대해 미리 정의됩니다. 숫자 형식에 대한 단항 `+` 연산의 결과는 피연산자의 값입니다.  
  
 이항 `+` 연산자는 숫자 및 문자열 형식에 대해 미리 정의됩니다. 숫자 형식의 경우 +는 두 피연산자의 합계를 계산합니다. 피연산자 중 하나 또는 둘 다가 문자열 형식이면 +는 피연산자의 문자열 표현을 연결합니다.  
  
 대리자 형식도 대리자 연결을 수행하는 이항 `+` 연산자를 제공합니다.  
  
 사용자 정의 형식은 단항 `+` 및 이항 `+` 연산자를 오버로드할 수 있습니다. 정수 형식에 대한 연산은 일반적으로 열거형에서 허용됩니다. 자세한 내용은 [연산자(C# 참조)](../../../csharp/language-reference/keywords/operator.md)를 참조하세요.  
  
## <a name="example"></a>예  
 [!code-csharp[csRefOperators#28](../../../csharp/language-reference/operators/codesnippet/CSharp/addition-operator_1.cs)]  
  
## <a name="c-language-specification"></a>C# 언어 사양  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [C# 참조](../../../csharp/language-reference/index.md)  
 [C# 프로그래밍 가이드](../../../csharp/programming-guide/index.md)  
 [C# 연산자](../../../csharp/language-reference/operators/index.md)  
 [연산자(C# 참조)](../../../csharp/language-reference/keywords/operator.md)
