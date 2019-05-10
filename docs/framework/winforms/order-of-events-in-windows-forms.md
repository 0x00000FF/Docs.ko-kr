---
title: Windows Forms에서의 이벤트 순서
ms.date: 03/30/2017
helpviewer_keywords:
- events [Windows Forms], order of
- focus event order
- application shutdown event order
- sequence [Windows Forms], of events
- validation events [Windows Forms], order of
- application startup event order
ms.assetid: e81db09b-4453-437f-b78a-62d7cd5c9829
ms.openlocfilehash: f581ca5ee1376251a593e7b8813ef4b0e0f41b64
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/28/2019
ms.locfileid: "64655590"
---
# <a name="order-of-events-in-windows-forms"></a>Windows Forms에서의 이벤트 순서
Windows Forms 응용 프로그램에서 이벤트가 발생하는 순서는 반대로 이러한 각 이벤트의 처리와 관련된 개발자에게 특히 관심 사항입니다. 폼 부분을 다시 그려야 하는 경우와 같이 이벤트를 세심하게 처리해야 하는 상황에서는 런타임에 이벤트가 발생한 정확한 순서를 알아야 합니다. 이 항목에서는 응용 프로그램 및 컨트롤 수명에서 여러 중요한 단계 중에 발생하는 이벤트 순서에 대한 세부 정보를 제공합니다. 마우스 입력된 이벤트의 순서에 대 한 특정 세부 정보를 참조 하세요 [Windows Forms의 마우스 이벤트](mouse-events-in-windows-forms.md)합니다. Windows Forms의 이벤트의 개요를 보려면 [이벤트 개요](events-overview-windows-forms.md)합니다. 이벤트 처리기 구성에 대 한 자세한 내용은 참조 하세요 [이벤트 처리기 개요](event-handlers-overview-windows-forms.md)합니다.  
  
## <a name="application-startup-and-shutdown-events"></a>응용 프로그램 시작 및 종료 이벤트  
 <xref:System.Windows.Forms.Form> 및 <xref:System.Windows.Forms.Control> 클래스는 응용 프로그램 시작 및 종료와 관련된 이벤트 집합을 노출합니다. Windows Forms 응용 프로그램이 시작되면 주 폼의 시작 이벤트가 다음 순서대로 발생합니다.  
  
- <xref:System.Windows.Forms.Control.HandleCreated?displayProperty=nameWithType>  
  
- <xref:System.Windows.Forms.Control.BindingContextChanged?displayProperty=nameWithType>  
  
- <xref:System.Windows.Forms.Form.Load?displayProperty=nameWithType>  
  
- <xref:System.Windows.Forms.Control.VisibleChanged?displayProperty=nameWithType>  
  
- <xref:System.Windows.Forms.Form.Activated?displayProperty=nameWithType>  
  
- <xref:System.Windows.Forms.Form.Shown?displayProperty=nameWithType>  
  
 응용 프로그램이 닫히면 주 폼의 종료 이벤트가 다음 순서대로 발생합니다.  
  
- <xref:System.Windows.Forms.Form.Closing?displayProperty=nameWithType>  
  
- <xref:System.Windows.Forms.Form.FormClosing?displayProperty=nameWithType>  
  
- <xref:System.Windows.Forms.Form.Closed?displayProperty=nameWithType>  
  
- <xref:System.Windows.Forms.Form.FormClosed?displayProperty=nameWithType>  
  
- <xref:System.Windows.Forms.Form.Deactivate?displayProperty=nameWithType>  
  
 <xref:System.Windows.Forms.Application> 클래스의 <xref:System.Windows.Forms.Application.ApplicationExit> 이벤트는 주 폼의 종료 이벤트 뒤에 발생합니다.  
  
> [!NOTE]
>  Visual Basic 2005에는 <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.Startup?displayProperty=nameWithType> 및 <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.Shutdown?displayProperty=nameWithType>과 같은 추가 응용 프로그램 이벤트가 포함됩니다.  
  
## <a name="focus-and-validation-events"></a>포커스 및 유효성 검사 이벤트  
 키보드(TAB, SHIFT+TAB 등)를 사용하거나, <xref:System.Windows.Forms.Control.Select%2A> 또는 <xref:System.Windows.Forms.Control.SelectNextControl%2A> 메서드를 호출하거나, <xref:System.Windows.Forms.ContainerControl.ActiveControl%2A> 속성을 현재 폼으로 설정하여 포커스를 변경하면 <xref:System.Windows.Forms.Control> 클래스의 포커스 이벤트가 다음 순서대로 발생합니다.  
  
- <xref:System.Windows.Forms.Control.Enter>  
  
- <xref:System.Windows.Forms.Control.GotFocus>  
  
- <xref:System.Windows.Forms.Control.Leave>  
  
- <xref:System.Windows.Forms.Control.Validating>  
  
- <xref:System.Windows.Forms.Control.Validated>  
  
- <xref:System.Windows.Forms.Control.LostFocus>  
  
 마우스를 사용하거나 <xref:System.Windows.Forms.Control.Focus%2A> 메서드를 호출하여 포커스를 변경하면 <xref:System.Windows.Forms.Control> 클래스의 포커스 이벤트가 다음 순서대로 발생합니다.  
  
- <xref:System.Windows.Forms.Control.Enter>  
  
- <xref:System.Windows.Forms.Control.GotFocus>  
  
- <xref:System.Windows.Forms.Control.LostFocus>  
  
- <xref:System.Windows.Forms.Control.Leave>  
  
- <xref:System.Windows.Forms.Control.Validating>  
  
- <xref:System.Windows.Forms.Control.Validated>  
  
## <a name="see-also"></a>참고자료

- [Windows Forms에서 이벤트 처리기 만들기](creating-event-handlers-in-windows-forms.md)
