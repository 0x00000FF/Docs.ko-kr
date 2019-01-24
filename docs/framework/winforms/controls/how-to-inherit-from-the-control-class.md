---
title: '방법: Control 클래스에서 상속'
ms.date: 03/30/2017
helpviewer_keywords:
- inheritance [Windows Forms], Windows Forms custom controls
- Control class [Windows Forms], inheriting from
- custom controls [Windows Forms], inheritance
- OnPaint method [Windows Forms]
- custom controls [Windows Forms], creating
ms.assetid: 46ba0df3-5cf7-443c-a3b4-a72660172476
ms.openlocfilehash: 11856152b3bf3bb256f44a0571c467072e545206
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54532645"
---
# <a name="how-to-inherit-from-the-control-class"></a>방법: Control 클래스에서 상속
Windows Form에 사용 하 여 완전 한 사용자 지정 컨트롤을 만들려는 경우에서 상속 해야 하는 <xref:System.Windows.Forms.Control> 클래스입니다. 상속 하는 동안는 <xref:System.Windows.Forms.Control> 클래스는 수행한 자세한 계획 및 구현, 광범위 한 옵션을 사용 하 여도 제공 해야 합니다. 상속할 때 <xref:System.Windows.Forms.Control>, 컨트롤이 작동 되도록 하는 기본적인 기능을 상속 합니다. 고유한 기능은 <xref:System.Windows.Forms.Control> 클래스 키보드 및 마우스를 통해 사용자 입력 처리, 컨트롤의 크기와 범위를 정의 창 핸들을 제공 및 메시지 처리 및 보안을 제공 합니다. 이 경우에는 컨트롤의 그래픽 인터페이스의 실제 렌더링인 그리기를 통합하거나 특정 사용자 상호 작용 기능을 통합하지 않습니다. 사용자 지정 코드를 통해 이러한 모든 사항을 제공해야 합니다.  
  
> [!NOTE]
>  표시되는 대화 상자와 메뉴 명령은 활성 설정이나 버전에 따라 도움말에서 설명하는 것과 다를 수 있습니다. 설정을 변경하려면 **도구** 메뉴에서 **설정 가져오기 및 내보내기** 를 선택합니다. 자세한 내용은 [Visual Studio IDE 개인 설정](/visualstudio/ide/personalizing-the-visual-studio-ide)을 참조하세요.  
  
### <a name="to-create-a-custom-control"></a>사용자 지정 컨트롤을 만들려면  
  
1.  새 **Windows 애플리케이션** 또는 **Windows 컨트롤 라이브러리** 프로젝트를 만듭니다.  
  
2.  **프로젝트** 메뉴에서 **클래스 추가**를 선택합니다.  
  
3.  **새 항목 추가** 대화 상자에서 **사용자 지정 컨트롤**을 클릭합니다.  
  
     새 사용자 지정 컨트롤을 프로젝트에 추가합니다.  
  
4.  F7 키를 눌러 사용자 지정 컨트롤의 **코드 편집기**를 엽니다.  
  
5.  찾을 합니다 <xref:System.Windows.Forms.Control.OnPaint%2A> 메서드 호출을 제외 하 고 비어 있는 <xref:System.Windows.Forms.Control.OnPaint%2A> 기본 클래스의 메서드.  
  
6.  코드를 수정하여 컨트롤에 원하는 사용자 지정 그리기를 통합합니다.  
  
     컨트롤의 그래픽을 렌더링하는 코드를 작성하는 방법에 대한 정보는 [사용자 지정 컨트롤 그리기 및 렌더링](../../../../docs/framework/winforms/controls/custom-control-painting-and-rendering.md)을 참조하세요.  
  
7.  컨트롤이 통합하는 사용자 지정 메서드, 속성 또는 이벤트를 구현합니다.  
  
8.  컨트롤을 저장하고 테스트합니다.  
  
## <a name="see-also"></a>참고자료
- [사용자 지정 컨트롤의 종류](../../../../docs/framework/winforms/controls/varieties-of-custom-controls.md)
- [방법: UserControl 클래스에서 상속](../../../../docs/framework/winforms/controls/how-to-inherit-from-the-usercontrol-class.md)
- [방법: 에서 상속 하는 기존 Windows Forms 컨트롤](../../../../docs/framework/winforms/controls/how-to-inherit-from-existing-windows-forms-controls.md)
- [방법: Windows forms 컨트롤 작성](../../../../docs/framework/winforms/controls/how-to-author-controls-for-windows-forms.md)
- [Visual Basic에서 상속된 이벤트 처리기 관련 문제 해결](~/docs/visual-basic/programming-guide/language-features/events/troubleshooting-inherited-event-handlers.md)
- [디자인 타임에 Windows Forms 컨트롤 개발](../../../../docs/framework/winforms/controls/developing-windows-forms-controls-at-design-time.md)
