---
title: 기존 컨트롤에서 상속
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- inheritance [Windows Forms], Windows Forms custom controls
- custom controls [Windows Forms], inheritance
ms.assetid: 1e1fc8ea-c615-4cf0-a356-16d6df7444ab
author: jillre
ms.author: jillfra
manager: jillfra
ms.openlocfilehash: b0e0053816efde349c7e4d13d03bef5f8801c667
ms.sourcegitcommit: 515469828d0f040e01bde01df6b8e4eb43630b06
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/06/2020
ms.locfileid: "78849382"
---
# <a name="how-to-inherit-from-existing-windows-forms-controls"></a>방법: 기존 Windows Forms 컨트롤에서 상속

기존 컨트롤의 기능을 확장하려는 경우 상속을 통해 기존 컨트롤에서 파생된 컨트롤을 만들 수 있습니다. 기존 컨트롤에서 상속하는 경우 해당 컨트롤의 모든 기능 및 시각적 속성을 상속합니다. 예를 들어 <xref:System.Windows.Forms.Button>에서 상속된 컨트롤을 만드는 경우 새 컨트롤은 표준 <xref:System.Windows.Forms.Button> 컨트롤과 똑같이 보이고 작동합니다. 그런 다음 사용자 지정 메서드 및 속성의 구현을 통해 새 컨트롤의 기능을 확장하거나 수정할 수 있습니다. 일부 컨트롤에서는 메서드를 <xref:System.Windows.Forms.Control.OnPaint%2A> 재정의하여 상속된 컨트롤의 시각적 모양을 변경할 수도 있습니다.

## <a name="to-create-an-inherited-control"></a>상속된 컨트롤을 만들려면

1. Visual Studio에서 새 **Windows 양식 응용 프로그램** 프로젝트를 만듭니다.

1. **프로젝트** 메뉴에서 **새 항목 추가**를 선택합니다.

    **새 항목 추가** 대화 상자가 나타납니다.

1. **새 항목 추가** 대화 상자에서 **사용자 지정 컨트롤**을 두 번 클릭합니다.

    새 사용자 지정 컨트롤을 프로젝트에 추가합니다.

1. 사용 하는 경우:

    - **솔루션 탐색기**맨 위에 있는 시각적 기본, **모든 파일 표시를**클릭합니다. CustomControl1.vb를 확장한 다음 코드 편집기에서 CustomControl1.Designer.vb를 엽니다.
    - C #, 코드 편집기에서 CustomControl1.cs 엽니다.

1. <xref:System.Windows.Forms.Control>에서 상속되는 클래스 선언을 찾습니다.

1. 기본 클래스를 상속하려는 컨트롤로 변경합니다.

     예를 들어 <xref:System.Windows.Forms.Button>에서 상속하려는 경우 클래스 선언을 다음으로 변경합니다.

    ```vb
    Partial Class CustomControl1
        Inherits System.Windows.Forms.Button
    ```

    ```csharp
    public partial class CustomControl1 : System.Windows.Forms.Button
    ```

1. Visual Basic을 사용하는 경우 저장하고 CustomControl1.Designer.vb를 닫습니다. 코드 편집기에서 CustomControl1.vb를 엽니다.

1. 컨트롤이 통합하는 사용자 지정 메서드 또는 속성을 구현합니다.

1. 컨트롤의 그래픽 모양을 수정하려면 메서드를 재정의합니다. <xref:System.Windows.Forms.Control.OnPaint%2A>

    > [!NOTE]
    > 재정의를 <xref:System.Windows.Forms.Control.OnPaint%2A> 사용하면 모든 컨트롤의 모양을 수정할 수 없습니다. Windows에서 수행한 모든 페인팅(예:)이 <xref:System.Windows.Forms.TextBox>메서드를 <xref:System.Windows.Forms.Control.OnPaint%2A> 호출하지 않으므로 사용자 지정 코드를 사용하지 않는 모든 컨트롤이 있습니다. 수정하려는 특정 컨트롤에 대한 도움말 설명서를 참조하여 메서드를 <xref:System.Windows.Forms.Control.OnPaint%2A> 사용할 수 있는지 확인합니다. 모든 Windows Form 컨트롤의 목록은 [Windows Forms에서 사용할 컨트롤](controls-to-use-on-windows-forms.md)을 참조하세요. 컨트롤이 멤버 메서드로 <xref:System.Windows.Forms.Control.OnPaint%2A> 나열되지 않은 경우 이 메서드를 재정의하여 모양을 변경할 수 없습니다. 사용자 지정 그리기에 대한 자세한 내용은 [사용자 지정 컨트롤 그리기 및 렌더링](custom-control-painting-and-rendering.md)을 참조하세요.

    ```vb
    Protected Overrides Sub OnPaint(ByVal e As _
       System.Windows.Forms.PaintEventArgs)
       MyBase.OnPaint(e)
       ' Insert code to do custom painting.
       ' If you want to completely change the appearance of your control,
       ' do not call MyBase.OnPaint(e).
    End Sub
    ```

    ```csharp
    protected override void OnPaint(PaintEventArgs pe)
    {
       base.OnPaint(pe);
       // Insert code to do custom painting.
       // If you want to completely change the appearance of your control,
       // do not call base.OnPaint(pe).
    }
    ```

1. 컨트롤을 저장하고 테스트합니다.

## <a name="see-also"></a>참고 항목

- [사용자 지정 컨트롤의 종류](varieties-of-custom-controls.md)
- [방법: Control 클래스에서 상속](how-to-inherit-from-the-control-class.md)
- [방법: UserControl 클래스에서 상속](how-to-inherit-from-the-usercontrol-class.md)
- [방법: Windows Forms 컨트롤 작성](how-to-author-controls-for-windows-forms.md)
- [Visual Basic에서 상속된 이벤트 처리기 관련 문제 해결](~/docs/visual-basic/programming-guide/language-features/events/troubleshooting-inherited-event-handlers.md)
- [연습: Windows 양식 컨트롤에서 상속](walkthrough-inheriting-from-a-windows-forms-control-with-visual-csharp.md)
