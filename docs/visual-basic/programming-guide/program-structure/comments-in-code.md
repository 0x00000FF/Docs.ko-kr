---
title: 코드 주석(Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- Uncomment button
- REM statement [Visual Basic]
- comments [Visual Basic], in code
- comments [Visual Basic], Visual Basic code
- Comment button
- buttons [Visual Basic], Uncomment
- buttons [Visual Basic], Comment
- code comments [Visual Basic], Visual Basic
- Visual Basic code, comments
- comments
- code comments
ms.assetid: 90136fba-22eb-49f9-ba81-63db629b4a47
ms.openlocfilehash: fafc80cc4847e9ec05f19fc7f3d31d2d5b11197a
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/04/2018
ms.locfileid: "43661154"
---
# <a name="comments-in-code-visual-basic"></a>코드 주석(Visual Basic)
코드 예제를 읽다 보면 종종 주석 기호(`'`)를 보게 됩니다. 다음에 텍스트를 무시 하려면 Visual Basic 컴파일러에서는이 기호 또는 *주석*합니다. 주석이란 해당 코드를 읽을 사람의 편의를 위해 코드에 추가되는 간단한 설명입니다.  
  
 모든 프로시저를 시작할 때 프로시저의 기능적 특징, 즉 해당 프로시저가 수행하는 작업에 대한 간단한 주석을 사용하는 것이 좋습니다. 이는 사용자 자신이나 코드를 보게 될 다른 사용자를 위한 것입니다. 프로시저의 구현 방식 등 구현에 대한 자세한 정보는 기능적 특징을 설명하는 주석과 분리되어야 합니다. 이 정보를 설명하는 부분에 포함시킨 경우에는 함수를 업데이트할 때 이 정보도 업데이트해야 합니다.  
  
 주석은 문과 같은 줄에서 문 다음에 나올 수도 있고 한 줄을 차지할 수도 있습니다. 다음 코드에서는 이 두 가지 경우를 모두 보여 줍니다.  
  
 [!code-vb[VbVbcnConventions#16](../../../visual-basic/programming-guide/language-features/codesnippet/VisualBasic/comments-in-code_1.vb)]  
  
 주석에 둘 이상의 줄이 필요하면 다음 예제와 같이 각 줄에 주석 기호를 사용합니다.  
  
 [!code-vb[VbVbcnConventions#17](../../../visual-basic/programming-guide/language-features/codesnippet/VisualBasic/comments-in-code_2.vb)]  
  
## <a name="commenting-guidelines"></a>주석 지침  
 다음 표에서는 코드 부분의 앞에 올 수 있는 주석의 종류에 대한 일반적인 지침을 보여 줍니다. 다음은 제안; Visual Basic에서 주석을 추가 하는 것에 대 한 규칙을 적용 하지 않습니다. 사용자 자신이나 해당 코드를 읽을 다른 모든 사용자에게 적합하도록 주석을 쓰면 됩니다.  
  
|||  
|---|---|  
|주석 형식|주석 설명|  
|용도|프로시저의 작업 수행 방식이 아니라 해당 프로시저에서 수행하는 작업에 대해 설명합니다.|  
|Assumptions|프로시저에서 액세스하는 외부 변수, 컨트롤, 열린 파일 또는 기타 요소를 나열합니다.|  
|효과|영향을 받은 외부 변수, 컨트롤 또는 파일을 나열하고, 분명하지 않은 경우에는 그 효과를 나열합니다.|  
|Inputs|인수의 용도를 지정합니다.|  
|반환 값|프로시저에 의해 반환된 값에 대해 설명합니다.|  
  
 다음은 주의해야 할 사항입니다.  
  
-   중요한 모든 변수 선언에는 선언되는 변수의 용도에 대해 설명하는 주석이 앞에 와야 합니다.  
  
-   변수, 컨트롤 및 프로시저의 이름은 쉽게 알 수 있는 이름으로 지정하며, 복잡한 구현에 대해 자세히 설명하는 경우에만 주석을 사용합니다.  
  
-   줄 연속 시퀀스를 사용한 후에는 같은 줄에 주석을 쓸 수 없습니다.  
  
 추가 하거나 코드 줄을 하나 이상 선택 하 여 코드 블록에 대 한 주석 기호를 제거할 수 있습니다 합니다 **주석** (![VisualBasicWinAppCodeEditorCommentButton](../../../visual-basic/programming-guide/program-structure/media/vacommentbutton.gif "vaCommentButton ")) 및 **주석** (![VisualStudioWinAppProjectUncommentButton](../../../visual-basic/programming-guide/program-structure/media/vauncommentbutton.gif "vaUncommentButton")) 단추를 **편집**  도구 모음입니다.  
  
> [!NOTE]
>  `REM` 키워드로 텍스트를 시작하여 코드에 주석을 추가할 수도 있습니다. 그러나 합니다 `'` 기호 및 **주석**/**주석** 단추는 쉽게 사용 하 고 필요한 공간 및 메모리도 절약할 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [XML 주석 사용 하 여 코드 문서화](https://msdn.microsoft.com/magazine/dd722812.aspx)  
 [방법: XML 문서 만들기](../../../visual-basic/programming-guide/program-structure/how-to-create-xml-documentation.md)  
 [XML 주석 태그](../../../visual-basic/language-reference/xmldoc/index.md)  
 [프로그램 구조 및 코드 규칙](../../../visual-basic/programming-guide/program-structure/program-structure-and-code-conventions.md)  
 [REM 문](../../../visual-basic/language-reference/statements/rem-statement.md)
