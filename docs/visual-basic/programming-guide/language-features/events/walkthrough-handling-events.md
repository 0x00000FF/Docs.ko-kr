---
title: 이벤트 처리 (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- event handling [Visual Basic], walkthroughs
- walkthroughs [Visual Basic], event handling
- variables [Visual Basic], WithEvents
- events [Visual Basic], walkthroughs
- WithEvents keyword [Visual Basic], walkthroughs
- event handlers [Visual Basic], walkthroughs
ms.assetid: f145b3fc-5ae0-4509-a2aa-1ff6934706bd
ms.openlocfilehash: 2a8b515f500884d743b7dcca41ffe8c1607375a9
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/02/2019
ms.locfileid: "58840928"
---
# <a name="walkthrough-handling-events-visual-basic"></a>연습: 이벤트 처리 (Visual Basic)
이것이 이벤트로 작업 하는 방법을 보여 주는 두 항목 중 두 번째 숫자입니다. 첫 번째 항목인 [연습: 선언 및 발생 이벤트](../../../../visual-basic/programming-guide/language-features/events/walkthrough-declaring-and-raising-events.md)를 선언 하 고 이벤트를 발생 하는 방법을 보여 줍니다. 이 섹션에서는 다음 연습에서 클래스 및 형식을 사용 하 여 수행한 이벤트를 처리 하는 방법을 보여 줍니다.  
  
 `Widget` 클래스 예제에는 일반적인 이벤트 처리 문을 사용 합니다. Visual Basic 이벤트를 사용 하 여 작업 하기 위한 다른 기법을 제공 합니다. 연습으로 사용 하도록이 예제를 수정할 수 있습니다 합니다 `AddHandler` 고 `Handles` 문입니다.  
  
### <a name="to-handle-the-percentdone-event-of-the-widget-class"></a>위젯 클래스의 PercentDone 이벤트를 처리 하려면  
  
1.  다음 코드를 배치할 `Form1`:  
  
     [!code-vb[VbVbcnWalkthroughDeclaringAndRaisingEvents#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnWalkthroughDeclaringAndRaisingEvents/VB/Form1.vb#4)]  
  
     합니다 `WithEvents` 키워드를 지정 하는 변수의 `mWidget` 개체의 이벤트를 처리 하는 데 사용 됩니다. 개체를 만들 수는 클래스의 이름을 제공 하 여 개체의 종류를 지정 합니다.  
  
     변수의 `mWidget` 에 선언 된 `Form1` 있으므로 `WithEvents` 변수는 클래스 수준 이어야 합니다. 에 배치 되는 클래스의 형식에 관계 없이 마찬가지입니다.  
  
     변수의 `mblnCancel` 취소 하는 데 사용 되는 `LongTask` 메서드.  
  
## <a name="writing-code-to-handle-an-event"></a>이벤트를 처리 하는 코드 작성  
 사용 하는 변수를 선언 하는 즉시 `WithEvents`, 클래스의 왼쪽된 드롭다운 목록에서 변수 이름을 나타납니다 **코드 편집기**합니다. 선택 하면 `mWidget`, `Widget` 오른쪽 드롭다운 목록에서 클래스의 이벤트를 표시 합니다. 접두사를 사용 하 여 해당 이벤트 프로시저에서 이벤트를 선택 하면 표시 `mWidget` 및 밑줄. 연관 된 모든 이벤트 프로시저를 `WithEvents` 변수 접두사로 변수 이름이 지정 됩니다.  
  
#### <a name="to-handle-an-event"></a>이벤트를 처리 하려면  
  
1.  선택 `mWidget` 왼쪽된 드롭다운 목록에서 합니다 **코드 편집기**합니다.  
  
2.  선택 된 `PercentDone` 오른쪽 드롭다운 목록에서 이벤트입니다. 합니다 **코드 편집기** 열립니다는 `mWidget_PercentDone` 이벤트 프로시저입니다.  
  
    > [!NOTE]
    >  합니다 **코드 편집기** 유용 하지만 새 이벤트 처리기를 삽입에 필요 하지 않습니다. 이 연습에서는 이벤트 처리기 코드에 직접 복사 하는 보다 직접적인 것입니다.  
  
3.  다음 코드를 `mWidget_PercentDone` 이벤트 처리기에 추가합니다.  
  
     [!code-vb[VbVbcnWalkthroughDeclaringAndRaisingEvents#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnWalkthroughDeclaringAndRaisingEvents/VB/Form1.vb#5)]  
  
     때마다 합니다 `PercentDone` 이벤트가 발생 하면 이벤트 프로시저에서 완료 백분율을 표시는 `Label` 제어 합니다. 합니다 `DoEvents` 메서드를 사용 하면 다시 그리기를 위해 레이블을 사용자 클릭을 기회를 제공 하 고는 **취소** 단추입니다.  
  
4.  다음 코드를 추가 합니다 `Button2_Click` 이벤트 처리기:  
  
     [!code-vb[VbVbcnWalkthroughDeclaringAndRaisingEvents#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnWalkthroughDeclaringAndRaisingEvents/VB/Form1.vb#6)]  
  
 클릭할 경우는 **취소** 하는 동안 단추 `LongTask` 실행 되는 `Button2_Click` 이벤트가 실행 될 즉시는 `DoEvents` 문을 통해 되려면 이벤트가 처리 합니다. 클래스 수준 변수 `mblnCancel` 로 설정 된 `True`, 및 `mWidget_PercentDone` 이벤트에서 그런 다음 테스트 하 고 설정 합니다 `ByRef Cancel` 인수를 `True`입니다.  
  
## <a name="connecting-a-withevents-variable-to-an-object"></a>WithEvents 변수 개체에 연결  
 `Form1` 처리 하도록 설정 된 `Widget` 개체의 이벤트입니다. 에 찾으려는 `Widget` 위치 합니다.  
  
 변수를 선언 하는 경우 `WithEvents` 개체가 없습니다. 디자인 타임에 연관 됩니다. `WithEvents` 다른 개체 변수 처럼 변수가 있습니다. 개체를 만들고 사용 하 여 참조를 할당 해야 합니다 `WithEvents` 변수입니다.  
  
#### <a name="to-create-an-object-and-assign-a-reference-to-it"></a>개체를 만들고이에 대 한 참조를 할당 하려면  
  
1.  선택 **(Form1 이벤트)** 왼쪽된 드롭다운 목록에서 합니다 **코드 편집기**합니다.  
  
2.  선택 된 `Load` 오른쪽 드롭다운 목록에서 이벤트입니다. 합니다 **코드 편집기** 열립니다는 `Form1_Load` 이벤트 프로시저입니다.  
  
3.  다음 코드를 추가 합니다 `Form1_Load` 이벤트 프로시저를 만드는 `Widget`:  
  
     [!code-vb[VbVbcnWalkthroughDeclaringAndRaisingEvents#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnWalkthroughDeclaringAndRaisingEvents/VB/Form1.vb#7)]  
  
 이 코드를 실행 하는 경우에 Visual Basic 만듭니다는 `Widget` 개체 및 해당 이벤트와 관련 된 이벤트 절차 연결할 `mWidget`합니다. 점에서, 때마다 합니다 `Widget` 발생 시킵니다 해당 `PercentDone` 이벤트는 `mWidget_PercentDone` 이벤트 프로시저가 실행 됩니다.  
  
#### <a name="to-call-the-longtask-method"></a>LongTask 메서드를 호출 하려면  
  
-   다음 코드를 `Button1_Click` 이벤트 처리기에 추가합니다.  
  
     [!code-vb[VbVbcnWalkthroughDeclaringAndRaisingEvents#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnWalkthroughDeclaringAndRaisingEvents/VB/Form1.vb#8)]  
  
 전에 `LongTask` 메서드가 호출 되는 표시 된 완료율를 초기화 해야 레이블과 클래스 수준 `Boolean` 으로 설정 되어 있어야 해당 메서드를 취소에 대 한 플래그 `False`.  
  
 `LongTask` 작업 기간을 12.2 시간 (초)을 사용 하 여 호출 됩니다. `PercentDone` 이벤트가 발생 한 번 마다 1-3 초입니다. 이벤트가 발생 될 때마다는 `mWidget_PercentDone` 이벤트 프로시저가 실행 됩니다.  
  
 때 `LongTask` 완료 되 면 `mblnCancel` 하는지 테스트 `LongTask` 일반적으로 종료 하기 때문에 중지 된 경우 또는 `mblnCancel` 로 설정 된 `True`합니다. 완료율 전자의 경우에만 업데이트 됩니다.  
  
#### <a name="to-run-the-program"></a>프로그램을 실행하려면  
  
1.  F5 키를 눌러 프로젝트 실행 모드로 전환 합니다.  
  
2.  클릭 합니다 **작업 시작** 단추입니다. 각 시간을 `PercentDone` 이벤트가 발생 하면 완료 된 작업의 백분율을 사용 하 여 레이블이 업데이트 됩니다.  
  
3.  클릭 합니다 **취소** 작업을 중지 하려면 단추입니다. 모양의 합니다 **취소** 단추 클릭할 때 즉시 변경 되지 않습니다. 합니다 `Click` 이벤트가 발생할 수는 `My.Application.DoEvents` 문을 이벤트 처리를 허용 합니다.  
  
    > [!NOTE]
    >  `My.Application.DoEvents` 메서드 이벤트를 처리 하지 동일한 방식으로 폼 마찬가지로 합니다. 예를 들어이 연습에서는 클릭 해야 합니다 **취소** 단추를 두 번입니다. 폼에 직접 이벤트를 처리할 수 있도록을 따르면 다중 스레딩 합니다. 자세한 내용은 [관리 되는 스레딩](../../../../standard/threading/index.md)합니다.
  
 F11 키를 사용 하 여 프로그램을 실행 하 고 한 번에 한 줄을 코드를 단계별로 실행 하는 방법도 사용할 수 있습니다. 실행 중이 시작 하는 방법을 명확 하 게 볼 수 있습니다 `LongTask`, 간단 하 게 다시 진입할 `Form1` 때마다는 `PercentDone` 이벤트가 발생 합니다.  
  
 어떻게 될 경우 코드에서 다시 실행 되는 동안 `Form1`, `LongTask` 메서드가 다시 호출 된? 최악의 경우 스택 오버플로가 발생할 수 있습니다 `LongTask` 이벤트가 발생할 때마다 호출 되었습니다.  
  
 변수를 발생 시킬 수 있습니다 `mWidget` 다른 이벤트를 처리할 `Widget` 새에 대 한 참조를 할당 하 여 개체 `Widget` 에 `mWidget`입니다. 사실 코드 가능 `Button1_Click` 단추를 클릭할 때마다이 작업을 수행 합니다.  
  
#### <a name="to-handle-events-for-a-different-widget"></a>다른 장치에 대 한 이벤트를 처리 하려면  
  
-   코드의 다음 줄을 추가 합니다 `Button1_Click` 줄 바로 앞에 나오는 절차 `mWidget.LongTask(12.2, 0.33)`:  
  
     [!code-vb[VbVbcnWalkthroughDeclaringAndRaisingEvents#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnWalkthroughDeclaringAndRaisingEvents/VB/Form1.vb#9)]  
  
 위의 코드에서는 새 `Widget` 단추를 클릭할 때마다 합니다. 즉시 합니다 `LongTask` 메서드가 완료 되 면에 대 한 참조를 `Widget` 출시 되 면 및 `Widget` 소멸 됩니다.  
  
 A `WithEvents` 변수가 한 번에 하나의 개체만 참조를 포함할 수 없습니다 다른 할당 하는 경우 `Widget` 개체를 `mWidget`, 이전 `Widget` 개체의 이벤트를 처리할 수 없습니다. 하는 경우 `mWidget` 이전에 대 한 참조를 포함 하는 유일한 개체 변수는 `Widget`, 개체는 소멸 됩니다. 여러 이벤트를 처리 하려는 경우 `Widget` 개체를 사용 하 여는 `AddHandler` 문을 개별적으로 각 개체에서 이벤트를 처리 합니다.  
  
> [!NOTE]
>  만큼 선언할 수 있습니다 `WithEvents` 배열을 하지만 변수의 수 필요한 `WithEvents` 변수는 지원 되지 않습니다.  
  
## <a name="see-also"></a>참고자료

- [연습: 이벤트 선언 및 발생](../../../../visual-basic/programming-guide/language-features/events/walkthrough-declaring-and-raising-events.md)
- [이벤트](../../../../visual-basic/programming-guide/language-features/events/index.md)
