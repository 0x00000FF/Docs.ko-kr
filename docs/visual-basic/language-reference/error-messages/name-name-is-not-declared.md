---
title: 이름 &#39; &lt;이름&gt; &#39; 선언 되지 않았습니다
ms.date: 07/20/2015
f1_keywords:
- bc30451
- vbc30451
helpviewer_keywords:
- BC30451
ms.assetid: 765f099b-e21e-47c6-a906-a065444e56b3
ms.openlocfilehash: e17017e84720a2581abc5115338352aacc02d473
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="name-39ltnamegt39-is-not-declared"></a>이름 &#39; &lt;이름&gt; &#39; 선언 되지 않았습니다
문에서 프로그래밍 요소를 참조 하지만 컴파일러에서 정확한 해당 이름 가진 요소를 찾을 수 없습니다.  
  
 **오류 ID:** BC30451  
  
## <a name="to-correct-this-error"></a>이 오류를 해결하려면  
  
1.  참조하는 문에서 이름의 철자를 검사합니다. Visual Basic은 대/소문자를 구분 하지만 맞춤법 다르면 전혀 다른 이름으로 간주 됩니다. 밑줄(`_`)은 이름의 일부이므로 철자의 일부입니다.  
  
2.  멤버 액세스 연산자 있는지 확인 (`.`) 개체와 해당 멤버 사이입니다. 예를 들어 <xref:System.Windows.Forms.TextBox> 이라는 `TextBox1`컨트롤이 있는 경우 해당 <xref:System.Windows.Forms.TextBoxBase.Text%2A> 속성에 액세스하려면 `TextBox1.Text`를 입력해야 합니다. `TextBox1Text`를 대신 입력하면 다른 이름이 만들어집니다.  
  
3.  맞춤법이 올바른지 개체 멤버 액세스의 구문이 올바른지 요소가 선언 된 확인. 자세한 내용은 참조 [요소 선언](../../../visual-basic/programming-guide/language-features/declared-elements/index.md)합니다.  
  
4.  프로그래밍 요소가 선언 된 경우 범위에 있는지 확인 합니다. 참조 하는 문이 프로그래밍 요소를 선언 하는 영역 바깥에 있는 경우 요소 이름을 정규화 해야 합니다. 자세한 내용은 참조 [Visual Basic의 범위](../../../visual-basic/programming-guide/language-features/declared-elements/scope.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [선언 및 상수 요약](../../../visual-basic/language-reference/keywords/declarations-and-constants-summary.md)  
 [Visual Basic 명명 규칙](../../../visual-basic/programming-guide/program-structure/naming-conventions.md)  
 [선언 요소 이름](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md)  
 [선언된 요소 참조](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)
