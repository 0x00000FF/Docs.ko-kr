---
title: RaiseEvent 문 (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.RaiseEventMethod
- vb.RaiseEvent
- RaiseEvent
helpviewer_keywords:
- raising events [Visual Basic], RaiseEvent statement
- RaiseEvent statement [Visual Basic]
- event handlers, connecting events to
ms.assetid: f82e380a-1e6b-4047-bea8-c853f4d2c742
ms.openlocfilehash: 5d8fd6adf33c992341324e07bcd2ad12986bbdf2
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61783970"
---
# <a name="raiseevent-statement"></a>RaiseEvent 문
클래스, 폼 또는 문서의 모듈 수준에서 선언한 이벤트를 트리거합니다.  
  
## <a name="syntax"></a>구문  
  
```  
RaiseEvent eventname[( argumentlist )]  
```  
  
## <a name="parts"></a>요소  
 `eventname`  
 필수 요소. 트리거할 이벤트의 이름입니다.  
  
 `argumentlist`  
 선택 사항입니다. 변수, 배열 또는 식의 쉼표로 구분 된 목록입니다. `argumentlist` 인수를 괄호로 묶어야 합니다. 인수가 없는 경우에 괄호를 생략 되어야 합니다.  
  
## <a name="remarks"></a>설명  
 필수 `eventname` 은 모듈 내에서 선언 된 이벤트의 이름입니다. Visual Basic의 변수 명명 규칙을 따릅니다.  
  
 이벤트가 발생 하는 모듈 내에서 선언 되지 않은, 경우 오류가 발생 했습니다. 다음 코드 조각에는 이벤트 선언 및 이벤트는 이벤트가 발생 하는 프로시저를 보여 줍니다.  
  
 [!code-vb[VbVbalrEvents#37](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrEvents/VB/Class1.vb#37)]  
  
 사용할 수 없습니다 `RaiseEvent` 모듈에서 명시적으로 선언 되지 않은 이벤트를 발생 시킵니다. 폼을 모두 상속 하는 예를 들어를 <xref:System.Windows.Forms.Control.Click> 에서 이벤트 <xref:System.Windows.Forms.Form?displayProperty=nameWithType>를 사용 하 여 높일 수 없습니다 `RaiseEvent` 파생된 폼에서. 선언 하는 경우는 `Click` 이벤트 폼 자체의 폼 모듈에 숨겨집니다 <xref:System.Windows.Forms.Control.Click> 이벤트입니다. 양식의 여전히 호출할 수 있습니다 <xref:System.Windows.Forms.Control.Click> 를 호출 하 여 이벤트를 <xref:System.Windows.Forms.Control.OnClick%2A> 메서드.  
  
 기본적으로 Visual Basic에서 정의 된 이벤트의 이벤트 처리기는 연결이 설정 된 순서 대로 발생 합니다. 이벤트를 가질 수 있으므로 `ByRef` 매개 변수를 나중에 연결 하는 프로세스는 이전 이벤트 처리기에 의해 변경 된 매개 변수를 받을 수 있습니다. 이벤트 처리기가 실행 후 이벤트를 발생 시킨 서브루틴에 컨트롤이 반환 됩니다.  
  
> [!NOTE]
>  비공유 이벤트가 선언 되는 클래스의 생성자 내에서 발생 하지 해야 합니다. 이러한 이벤트를 런타임 오류 발생 지는 않지만 연결 된 이벤트 처리기에서 포착 하지 못할 수 있습니다. 사용 된 `Shared` 한정자를 생성자에서 이벤트를 발생 하는 경우 공유 이벤트를 만듭니다.  
  
> [!NOTE]
>  사용자 지정 이벤트를 정의 하 여 이벤트의 기본 동작을 변경할 수 있습니다. 사용자 지정 이벤트에 대 한 합니다 `RaiseEvent` 문은 호출 이벤트의 `RaiseEvent` 접근자입니다. 사용자 지정 이벤트에 대 한 자세한 내용은 참조 하세요. [이벤트 연결 문으로](../../../visual-basic/language-reference/statements/event-statement.md)합니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 이벤트를 사용하여 10초부터 0초까지 카운트 다운합니다. 코드는 다양 한 이벤트 관련 메서드, 속성 및 포함 하 여 문을 보여 줍니다는 `RaiseEvent` 문입니다.  
  
 이벤트를 발생시키는 클래스는 이벤트 소스이고 이벤트를 처리하는 메서드는 이벤트 처리기입니다. 이벤트 소스는 생성되는 이벤트에 대해 여러 개의 처리기를 사용할 수 있습니다. 클래스에서 이벤트를 발생시키면 해당 이벤트는 개체의 해당 인스턴스에 대해 이벤트를 처리하도록 선택한 모든 클래스에서 발생됩니다.  
  
 또한 이 예제에서는 단추(`Button1`)와 텍스트 상자(`TextBox1`)가 있는 폼(`Form1`)을 사용합니다. 단추를 클릭하면 첫 번째 텍스트 상자에 10초부터 0초까지의 카운트 다운이 표시됩니다. 전체 시간(10초)이 경과되면 첫 번째 텍스트 상자에 "Done"이 표시됩니다.  
  
 `Form1`에 대한 코드는 폼의 초기 상태 및 최종 상태를 지정합니다. 또한 이벤트가 발생될 때 실행될 코드도 포함됩니다.  
  
 이 예제를 사용 하려면 새 Windows 응용 프로그램 프로젝트를 열고 라는 단추를 추가 `Button1` 고 이라는 입력란 `TextBox1` 이라는 기본 폼에 `Form1`합니다. 그런 다음 폼을 마우스 오른쪽 단추로 클릭 하 고 클릭 **코드 보기** 코드 편집기를 엽니다.  
  
 추가 된 `WithEvents` 의 선언 섹션에 변수를 `Form1` 클래스입니다.  
  
 [!code-vb[VbVbalrEvents#14](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrEvents/VB/Class1.vb#14)]  
  
## <a name="example"></a>예제  
 `Form1`에 대한 코드에 다음 코드를 추가합니다. 같은 존재할 수 있는 모든 중복 프로시저 바꿉니다 `Form_Load`, 또는 `Button_Click`합니다.  
  
 [!code-vb[VbVbalrEvents#15](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrEvents/VB/Class1.vb#15)]  
  
 F5 키를 눌러 앞의 예제를 실행 하 고 레이블이 붙은 단추를 클릭 **시작**합니다. 첫 번째 텍스트 상자에서 초를 카운트 다운하기 시작합니다. 전체 시간(10초)이 경과되면 첫 번째 텍스트 상자에 "Done"이 표시됩니다.  
  
> [!NOTE]
>  `My.Application.DoEvents` 메서드 이벤트를 처리 하지 동일한 방식으로 폼 마찬가지로 합니다. 폼에 직접 이벤트를 처리할 수 있도록을 따르면 다중 스레딩 합니다. 자세한 내용은 [관리 되는 스레딩](../../../standard/threading/index.md)합니다.  
  
## <a name="see-also"></a>참고자료

- [이벤트](../../../visual-basic/programming-guide/language-features/events/index.md)
- [Event 문](../../../visual-basic/language-reference/statements/event-statement.md)
- [AddHandler 문](../../../visual-basic/language-reference/statements/addhandler-statement.md)
- [RemoveHandler 문](../../../visual-basic/language-reference/statements/removehandler-statement.md)
- [Handles](../../../visual-basic/language-reference/statements/handles-clause.md)
