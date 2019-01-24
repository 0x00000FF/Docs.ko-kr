---
title: 이진 파일의 첫 번째 피연산자 &#39;경우&#39; 형식에 대 한 참조 또는 식이 null을 허용 해야 합니다.
ms.date: 07/20/2015
f1_keywords:
- bc33107
- vbc33107
helpviewer_keywords:
- BC33107
ms.assetid: 493c8899-3f6b-4471-8eb6-9284e8492768
ms.openlocfilehash: 85094ba6d6a44bf2e6cc4fba7946598c286a08a2
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54668276"
---
# <a name="first-operand-in-a-binary-39if39-expression-must-be-nullable-or-a-reference-type"></a>이진 파일의 첫 번째 피연산자 &#39;경우&#39; 형식에 대 한 참조 또는 식이 null을 허용 해야 합니다.
`If` 식 2 또는 3 개의 인수를 사용할 수 있습니다. 두 개의 인수를 보낼 때 첫 번째 인수는 참조 형식 또는 nullable 형식 이어야 합니다. 첫 번째 인수 이외의 값으로 계산 하는 경우 `Nothing`, 해당 값이 반환 됩니다. 첫 번째 인수를 평가 하는 경우 `Nothing`, 두 번째 인수가 평가 되 고 반환 합니다.  
  
 예를 들어, 다음 코드에는 두 개의 `If` 식, 세 개의 인수를 사용 하 여 하나 및 두 개의 인수를 사용 하 여 하나입니다. 식을 계산 하 고 동일한 값을 반환 합니다.  
  
```vb  
' firstChoice is a nullable value type.  
Dim firstChoice? As Integer = Nothing  
Dim secondChoice As Integer = 1128  
' If expression with three arguments.  
Console.WriteLine(If(firstChoice IsNot Nothing, firstChoice, secondChoice))  
' If expression with two arguments.  
Console.WriteLine(If(firstChoice, secondChoice))  
```  
  
 다음 식에는이 오류가 발생합니다.  
  
```vb  
Dim choice1 = 4  
Dim choice2 = 5  
Dim booleanVar = True  
  
' Not valid.  
'Console.WriteLine(If(choice1 < choice2, 1))  
' Not valid.  
'Console.WriteLine(If(booleanVar, "Test returns True."))  
```  
  
 **오류 ID:** BC33107  
  
## <a name="to-correct-this-error"></a>이 오류를 해결하려면  
  
-   첫 번째 인수는 nullable 형식 또는 참조 형식이 되도록 코드를 변경할 수 없습니다, 하는 경우 고려 세 개의 인수를 변환할 `If` 식 또는 `If...Then...Else` 문입니다.  
  
```vb  
Console.WriteLine(If(choice1 < choice2, 1, 2))  
Console.WriteLine(If(booleanVar, "Test returns True.", "Test returns False."))  
```  
  
## <a name="see-also"></a>참고자료
- [If 연산자](../../../visual-basic/language-reference/operators/if-operator.md)
- [If...Then...Else 문](../../../visual-basic/language-reference/statements/if-then-else-statement.md)
- [Nullable 값 형식](../../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md)
