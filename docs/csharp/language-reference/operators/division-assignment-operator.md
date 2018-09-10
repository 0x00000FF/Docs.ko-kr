---
title: /= 연산자(C# 참조)
ms.date: 07/20/2015
f1_keywords:
- /=_CSharpKeyword
helpviewer_keywords:
- division assignment operator (/=) [C#]
- /= (division assignment operator) [C#]
ms.assetid: 50fc02b0-ee9c-4c3e-b58d-d591282caf1c
ms.openlocfilehash: 8fff048cc441181aa3f0e3c0c638d501aaf9de3f
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/04/2018
ms.locfileid: "43526310"
---
# <a name="-operator-c-reference"></a>/= 연산자(C# 참조)
나누기 대입 연산자입니다.  
  
## <a name="remarks"></a>설명  
 다음과 같은 `/=` 대입 연산자를 사용하는 식의 경우  
  
```csharp  
x /= y  
```  
  
 위의 식은 아래의 식과 동일합니다.  
  
```csharp  
x = x / y  
```  
  
 단, `x`가 한 번만 계산됩니다. [/ 연산자](../../../csharp/language-reference/operators/division-operator.md)는 나누기를 수행할 숫자 형식에 대해 미리 정의되어 있습니다.  
  
 `/=` 연산자를 직접 오버로드할 수는 없지만 사용자 정의 형식은 [/ 연산자](../../../csharp/language-reference/operators/division-operator.md)를 오버로드할 수 있습니다([operator](../../../csharp/language-reference/keywords/operator.md) 참조). 모든 복합 대입 연산자에서 이진 연산자를 암시적으로 오버로드하면 해당하는 복합 대입 연산자가 오버로드됩니다.  
  
## <a name="example"></a>예  
 [!code-csharp[csRefOperators#5](codesnippet/CSharp/division-assignment-operator_1.cs)]  
  
## <a name="see-also"></a>참고 항목

- [C# 참조](../../../csharp/language-reference/index.md)  
- [C# 프로그래밍 가이드](../../../csharp/programming-guide/index.md)  
- [C# 연산자](../../../csharp/language-reference/operators/index.md)
