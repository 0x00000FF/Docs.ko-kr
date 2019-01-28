---
title: '방법: 구조체 간의 사용자 정의 변환 구현 - C# 프로그래밍 가이드'
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- user-defined conversions [C#]
ms.assetid: 97839aef-8fbc-40d5-9769-6b569bc2710b
ms.openlocfilehash: 4b38271c1aaf582c8c58b7198765b679cdfe4881
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54499566"
---
# <a name="how-to-implement-user-defined-conversions-between-structs-c-programming-guide"></a>방법: 구조체 간의 사용자 정의 변환 구현(C# 프로그래밍 가이드)
이 예제에서는 두 개의 구조체 `RomanNumeral` 및 `BinaryNumeral`을 정의하고 두 구조체 간의 변환을 보여 줍니다.  
  
## <a name="example"></a>예제  
 [!code-csharp[csProgGuideStatements#13](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-implement-user-defined-conversions-between-structs_1.cs)]  
  
## <a name="robust-programming"></a>강력한 프로그래밍  
  
-   앞의 예제에는 아래 문이 있습니다.  
  
     [!code-csharp[csProgGuideStatements#14](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-implement-user-defined-conversions-between-structs_2.cs)]  
  
     위 문은 `RomanNumeral`에서 `BinaryNumeral`로의 변환을 수행합니다. `RomanNumeral`에서 `BinaryNumeral`로의 직접 변환이 없으므로 캐스트를 사용하여 `RomanNumeral`에서 `int`로 변환한 후 다른 캐스트를 사용하여 `int`에서 `BinaryNumeral`로 변환합니다.  
  
-   또한 아래 문이 있습니다.  
  
     [!code-csharp[csProgGuideStatements#15](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-implement-user-defined-conversions-between-structs_3.cs)]  
  
     위 문은 `BinaryNumeral`에서 `RomanNumeral`로의 변환을 수행합니다. `RomanNumeral`은 `BinaryNumeral`에서의 암시적 변환을 정의하기 때문에 캐스트가 필요 없습니다.  
  
## <a name="see-also"></a>참고 항목

- [C# 참조](../../../csharp/language-reference/index.md)
- [C# 프로그래밍 가이드](../../../csharp/programming-guide/index.md)
- [변환 연산자](../../../csharp/programming-guide/statements-expressions-operators/conversion-operators.md)
