---
title: 익명 함수(C# 프로그래밍 가이드)
ms.date: 07/20/2015
helpviewer_keywords:
- lambda expressions [C#], as anonymus functions
- anonymous functions [C#]
- anonymous methods [C#]
ms.assetid: 6ce3f04d-0c71-4728-9127-634c7e9a8365
ms.openlocfilehash: 90a5a71f83a7117a7468bab0d9fe9d013685ebbe
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/04/2018
ms.locfileid: "43515241"
---
# <a name="anonymous-functions-c-programming-guide"></a>익명 함수(C# 프로그래밍 가이드)
익명 함수는 대리자 형식이 예상되는 곳에서 항상 사용할 수 있는 “인라인” 문 또는 식입니다. 이를 사용하여 명명된 대리자를 초기화하거나 명명된 대리자 형식 대신 이를 메서드 매개 변수로 전달할 수 있습니다.  
  
 익명 함수에는 두 가지가 있고 각각 다음 항목에서 설명합니다.  
  
-   [람다 식](../../../csharp/programming-guide/statements-expressions-operators/lambda-expressions.md).  
  
-   [무명 메서드](../../../csharp/programming-guide/statements-expressions-operators/anonymous-methods.md)  
  
    > [!NOTE]
    >  람다 식은 식 트리 및 대리자에 바인딩될 수 있습니다.  
  
## <a name="the-evolution-of-delegates-in-c"></a>C#에서 대리자의 발전  
 C# 1.0에서는 코드의 다른 위치에 정의된 메서드를 사용하여 명시적으로 초기화하는 방식으로 대리자의 인스턴스를 만들었습니다. C# 2.0에서는 대리자 호출에서 실행될 수 있는 이름 없는 인라인 문 블록을 작성하는 방법으로 무명 메서드의 개념을 소개했습니다. C# 3.0에서는 개념적으로 무명 메서드와 비슷하지만 더 간결하고 표현이 다양한 람다 식을 소개했습니다. 이러한 두 기능을 함께 *익명 함수*라고 합니다. 일반적으로 [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)]의 버전 3.5 이상을 대상으로 하는 응용 프로그램은 람다 식을 사용해야 합니다.  
  
 다음 예제에서는 C# 1.0에서 C# 3.0까지 대리자 만들기의 발전을 보여 줍니다.  
  
 [!code-csharp[csProgGuideLINQ#65](../../../csharp/programming-guide/arrays/codesnippet/CSharp/anonymous-functions_1.cs)]  
  
## <a name="c-language-specification"></a>C# 언어 사양  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [문, 식, 연산자](../../../csharp/programming-guide/statements-expressions-operators/index.md)  
- [람다 식](../../../csharp/programming-guide/statements-expressions-operators/lambda-expressions.md)  
- [대리자](../../../csharp/programming-guide/delegates/index.md)  
- [식 트리(C#)](../concepts/expression-trees/index.md)  
