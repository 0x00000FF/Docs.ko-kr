---
title: "while(C# 참조) | Microsoft Docs"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- while_CSharpKeyword
- while
dev_langs:
- CSharp
helpviewer_keywords:
- while keyword [C#]
ms.assetid: 72a0765c-6852-4aca-b327-4a11cb7f5c59
caps.latest.revision: 22
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Human Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 744980f2dd55806062901d874a3137f5936e0888
ms.lasthandoff: 03/13/2017

---
# <a name="while-c-reference"></a>while(C# 참조)
`while` 문은 지정된 식이 `false`로 평가될 때까지 문 또는 문의 블록을 실행합니다.  
  
## <a name="example"></a>예제  
 [!code-cs[csrefKeywordsIteration#5](../../../csharp/language-reference/keywords/codesnippet/CSharp/while_1.cs)]  
  
## <a name="example"></a>예제  
 [!code-cs[csrefKeywordsIteration#6](../../../csharp/language-reference/keywords/codesnippet/CSharp/while_2.cs)]  
  
## <a name="example"></a>예제  
 루프의 각 실행 전에 `while` 식의 테스트가 수행되므로 `while` 루프는 0번 이상 실행됩니다. 이는 한 번 이상 실행되는 [do](../../../csharp/language-reference/keywords/do.md) 루프와 다릅니다.  
  
 `while` 루프는 [break](../../../csharp/language-reference/keywords/break.md), [goto](../../../csharp/language-reference/keywords/goto.md), [return](../../../csharp/language-reference/keywords/return.md) 또는 [throw](../../../csharp/language-reference/keywords/throw.md) 문이 루프 외부로 제어를 전송할 때 종료될 수 있습니다. 루프를 종료하지 않고 다음 반복으로 제어를 전달하려면 [continue](../../../csharp/language-reference/keywords/continue.md) 문을 사용합니다. `int n`의 증가에 따라 이전의 세 예제에서 출력이 달라지는 것을 확인하세요. 아래의 예제에서는 출력이 생성되지 않습니다.  
  
 [!code-cs[csrefKeywordsIteration#7](../../../csharp/language-reference/keywords/codesnippet/CSharp/while_3.cs)]  
  
## <a name="c-language-specification"></a>C# 언어 사양  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec_md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [C# 참조](../../../csharp/language-reference/index.md)   
 [C# 프로그래밍 가이드](../../../csharp/programming-guide/index.md)   
 [C# 키워드](../../../csharp/language-reference/keywords/index.md)   
 [while 문(C++)](https://docs.microsoft.com/cpp/cpp/while-statement-cpp)   
 [반복 문](../../../csharp/language-reference/keywords/iteration-statements.md)
