---
title: StatusBar 컨트롤 개요(Windows Forms)
ms.date: 03/30/2017
f1_keywords:
- StatusBar
helpviewer_keywords:
- StatusBar control [Windows Forms], about StatusBar control
- status bars
ms.assetid: b7b9852c-633d-4416-bb2e-94852b989c6c
ms.openlocfilehash: c3e52a91a31eb898d0176bc35a97cda7de9a8368
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54491352"
---
# <a name="statusbar-control-overview-windows-forms"></a><span data-ttu-id="a765a-102">StatusBar 컨트롤 개요(Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="a765a-102">StatusBar Control Overview (Windows Forms)</span></span>
> [!IMPORTANT]
>  <span data-ttu-id="a765a-103"><xref:System.Windows.Forms.StatusStrip> 및 <xref:System.Windows.Forms.ToolStripStatusLabel> 대체 컨트롤과 기능을 추가 합니다 <xref:System.Windows.Forms.StatusBar> 및 <xref:System.Windows.Forms.StatusBarPanel> 제어; 그러나를 <xref:System.Windows.Forms.StatusBar> 및 <xref:System.Windows.Forms.StatusBarPanel> 컨트롤 하는 경우 이전 버전과 호환성 및 향후 사용을 위해 유지 됩니다 있습니다 이 옵션을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="a765a-103">The <xref:System.Windows.Forms.StatusStrip> and <xref:System.Windows.Forms.ToolStripStatusLabel> controls replace and add functionality to the <xref:System.Windows.Forms.StatusBar> and <xref:System.Windows.Forms.StatusBarPanel> controls; however, the <xref:System.Windows.Forms.StatusBar> and <xref:System.Windows.Forms.StatusBarPanel> controls are retained for both backward compatibility and future use, if you choose.</span></span>  
  
 <span data-ttu-id="a765a-104">Windows Forms [StatusBar 컨트롤](../../../../docs/framework/winforms/controls/statusbar-control-windows-forms.md) 폼에서 일반적으로 응용 프로그램에는 다양 한 종류의 상태 정보를 표시할 수는 창의 맨 아래에 표시 하는 영역으로 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a765a-104">The Windows Forms [StatusBar Control](../../../../docs/framework/winforms/controls/statusbar-control-windows-forms.md) is used on forms as an area, usually displayed at the bottom of a window, in which an application can display various kinds of status information.</span></span> <span data-ttu-id="a765a-105"><xref:System.Windows.Forms.StatusBar> 컨트롤에 텍스트 또는 상태 또는 애니메이션에서 프로세스 중인; 나타내는 아이콘이 나타내는 아이콘을 표시 하는 상태 표시줄 패널에 있을 수 있습니다. 예를 들어 [!INCLUDE[ofprword](../../../../includes/ofprword-md.md)] 나타내는 문서를 저장 하는 중입니다.</span><span class="sxs-lookup"><span data-stu-id="a765a-105"><xref:System.Windows.Forms.StatusBar> controls can have status bar panels on them that display text or icons to indicate state, or a series of icons in an animation that indicate a process is working; for example, [!INCLUDE[ofprword](../../../../includes/ofprword-md.md)] indicating that the document is being saved.</span></span>  
  
## <a name="using-the-statusbar-control"></a><span data-ttu-id="a765a-106">StatusBar 컨트롤 사용</span><span class="sxs-lookup"><span data-stu-id="a765a-106">Using the StatusBar Control</span></span>  
 <span data-ttu-id="a765a-107">Internet Explorer는 하이퍼링크; 위로 마우스를 가져가면 페이지의 URL을 표시 하는 상태 표시줄 사용 [!INCLUDE[ofprword](../../../../includes/ofprword-md.md)] 페이지 위치, 섹션 위치 및 overtype 및 수정 버전을 추적 합니다; Visual Studio 상태 표시줄을 사용 하 여 도킹 가능한 창을 조작 하는 방법 등의 상황에 맞는 정보를 제공 하려면 같은 편집 모드에 대 한 정보 제공 으로 또는 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="a765a-107">Internet Explorer uses a status bar to indicate the URL of a page when the mouse rolls over the hyperlink; [!INCLUDE[ofprword](../../../../includes/ofprword-md.md)] gives you information on page location, section location, and editing modes such as overtype and revision tracking; and Visual Studio uses the status bar to give context-sensitive information, such as telling you how to manipulate dockable windows as either docked or floating.</span></span>  
  
 <span data-ttu-id="a765a-108">설정 하 여 상태 표시줄에 단일 메시지를 표시할 수 있습니다는 <xref:System.Windows.Forms.StatusBar.ShowPanels%2A> 속성을 `false` (기본값) 설정 하는 <xref:System.Windows.Forms.StatusBar.Text%2A> 상태 표시줄에 표시할 텍스트는 상태 표시줄의 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="a765a-108">You can display a single message on the status bar by setting the <xref:System.Windows.Forms.StatusBar.ShowPanels%2A> property to `false` (the default) and setting the <xref:System.Windows.Forms.StatusBar.Text%2A> property of the status bar to the text you want to appear in the status bar.</span></span> <span data-ttu-id="a765a-109">나눌 수 있습니다 상태 표시줄 패널을 설정 하 여 둘 이상의 유형의 정보를 표시 하는 <xref:System.Windows.Forms.StatusBar.ShowPanels%2A> 속성을 `true` 하 고 사용 하는 <xref:System.Windows.Forms.StatusBar.StatusBarPanelCollection.Add%2A> 메서드의 <xref:System.Windows.Forms.StatusBar.StatusBarPanelCollection>합니다.</span><span class="sxs-lookup"><span data-stu-id="a765a-109">You can divide the status bar into panels to display more than one type of information by setting the <xref:System.Windows.Forms.StatusBar.ShowPanels%2A> property to `true` and using the <xref:System.Windows.Forms.StatusBar.StatusBarPanelCollection.Add%2A> method of <xref:System.Windows.Forms.StatusBar.StatusBarPanelCollection>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a765a-110">참고자료</span><span class="sxs-lookup"><span data-stu-id="a765a-110">See also</span></span>
- <xref:System.Windows.Forms.StatusBar>
- <xref:System.Windows.Forms.ToolStripStatusLabel>
- [<span data-ttu-id="a765a-111">방법: Windows Forms StatusBar 컨트롤에서 패널 클릭 확인</span><span class="sxs-lookup"><span data-stu-id="a765a-111">How to: Determine Which Panel in the Windows Forms StatusBar Control Was Clicked</span></span>](../../../../docs/framework/winforms/controls/determine-which-panel-wf-statusbar-control-was-clicked.md)
