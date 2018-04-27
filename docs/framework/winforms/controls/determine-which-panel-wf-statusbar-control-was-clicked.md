---
title: '방법: Windows Forms StatusBar 컨트롤에서 클릭한 패널 확인'
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-winforms
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- status bars [Windows Forms], determining panel clicked
- panels [Windows Forms], determining clicked
- StatusBar control [Windows Forms], coding panel click events
- StatusBar control [Windows Forms], determining panel clicked
- PanelClick event [Windows Forms], determining panel clicked
- Panel control [Windows Forms], determining click
ms.assetid: d14c6092-04b2-4a07-8ddf-0dd11277ff5f
caps.latest.revision: 16
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 35dc392ed95a5dbe8182b1adbd05affea55d0baa
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/26/2018
---
# <a name="how-to-determine-which-panel-in-the-windows-forms-statusbar-control-was-clicked"></a><span data-ttu-id="067b2-102">방법: Windows Forms StatusBar 컨트롤에서 클릭한 패널 확인</span><span class="sxs-lookup"><span data-stu-id="067b2-102">How to: Determine Which Panel in the Windows Forms StatusBar Control Was Clicked</span></span>
> [!IMPORTANT]
>  <span data-ttu-id="067b2-103"><xref:System.Windows.Forms.StatusStrip> 및 <xref:System.Windows.Forms.ToolStripStatusLabel> 컨트롤 교체 및 기능을 추가 <xref:System.Windows.Forms.StatusBar> 및 <xref:System.Windows.Forms.StatusBarPanel> 제어; 그러나는 <xref:System.Windows.Forms.StatusBar> 및 <xref:System.Windows.Forms.StatusBarPanel> 버전과 호환성 및 이후 사용에 대 한 컨트롤이 유지 되는 경우 있습니다 이 옵션을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="067b2-103">The <xref:System.Windows.Forms.StatusStrip> and <xref:System.Windows.Forms.ToolStripStatusLabel> controls replace and add functionality to the <xref:System.Windows.Forms.StatusBar> and <xref:System.Windows.Forms.StatusBarPanel> controls; however, the <xref:System.Windows.Forms.StatusBar> and <xref:System.Windows.Forms.StatusBarPanel> controls are retained for both backward compatibility and future use, if you choose.</span></span>  
  
 <span data-ttu-id="067b2-104">프로그램에는 [StatusBar 컨트롤](../../../../docs/framework/winforms/controls/statusbar-control-windows-forms.md) 컨트롤 내에서 case 문을 사용 하 여, 사용자가 클릭에 응답을 <xref:System.Windows.Forms.StatusBar.PanelClick> 이벤트입니다.</span><span class="sxs-lookup"><span data-stu-id="067b2-104">To program the [StatusBar Control](../../../../docs/framework/winforms/controls/statusbar-control-windows-forms.md) control to respond to user clicks, use a case statement within the <xref:System.Windows.Forms.StatusBar.PanelClick> event.</span></span> <span data-ttu-id="067b2-105">이벤트는 클릭에 대 한 참조를 포함 하는 인수 (패널 인수)을 포함 <xref:System.Windows.Forms.StatusBarPanel>합니다.</span><span class="sxs-lookup"><span data-stu-id="067b2-105">The event contains an argument (the panel argument), which contains a reference to the clicked <xref:System.Windows.Forms.StatusBarPanel>.</span></span> <span data-ttu-id="067b2-106">이 참조를 사용 하 여 클릭 한 패널의 인덱스를 확인할 수 있으며 그에 따라 프로그래밍할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="067b2-106">Using this reference, you can determine the index of the clicked panel, and program accordingly.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="067b2-107">확인 된 <xref:System.Windows.Forms.StatusBar> 컨트롤의 <xref:System.Windows.Forms.StatusBar.ShowPanels%2A> 속성이로 설정 되어 `true`합니다.</span><span class="sxs-lookup"><span data-stu-id="067b2-107">Ensure that the <xref:System.Windows.Forms.StatusBar> control's <xref:System.Windows.Forms.StatusBar.ShowPanels%2A> property is set to `true`.</span></span>  
  
### <a name="to-determine-which-panel-was-clicked"></a><span data-ttu-id="067b2-108">클릭 한 패널을 확인 하려면</span><span class="sxs-lookup"><span data-stu-id="067b2-108">To determine which panel was clicked</span></span>  
  
1.  <span data-ttu-id="067b2-109">에 <xref:System.Windows.Forms.StatusBar.PanelClick> 이벤트 처리기를 사용 하 여 한 `Select Case` (Visual Basic)에서는 또는 `switch case` (Visual C# 또는 [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)]) 문에를 이벤트 인수에 클릭 한 패널의 인덱스를 검사 하 여 클릭 한 패널을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="067b2-109">In the <xref:System.Windows.Forms.StatusBar.PanelClick> event handler, use a `Select Case` (in Visual Basic) or `switch case` (Visual C# or [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)]) statement to determine which panel was clicked by examining the index of the clicked panel in the event arguments.</span></span>  
  
     <span data-ttu-id="067b2-110">다음 코드 예제에서는의 현재 상태, 폼에 필요는 <xref:System.Windows.Forms.StatusBar> 컨트롤 `StatusBar1`와 두 개의 <xref:System.Windows.Forms.StatusBarPanel> 개체 `StatusBarPanel1` 및 `StatusBarPanel2`합니다.</span><span class="sxs-lookup"><span data-stu-id="067b2-110">The following code example requires the presence, on the form, of a <xref:System.Windows.Forms.StatusBar> control, `StatusBar1`, and two <xref:System.Windows.Forms.StatusBarPanel> objects, `StatusBarPanel1` and `StatusBarPanel2`.</span></span>  
  
    ```vb  
    Private Sub StatusBar1_PanelClick(ByVal sender As System.Object, ByVal e As System.Windows.Forms.StatusBarPanelClickEventArgs) Handles StatusBar1.PanelClick  
       Select Case StatusBar1.Panels.IndexOf(e.StatusBarPanel)  
         Case 0  
           MessageBox.Show("You have clicked Panel One.")  
         Case 1  
           MessageBox.Show("You have clicked Panel Two.")  
       End Select  
    End Sub  
    ```  
  
    ```csharp  
    private void statusBar1_PanelClick(object sender,   
    System.Windows.Forms.StatusBarPanelClickEventArgs e)  
    {  
       switch (statusBar1.Panels.IndexOf(e.StatusBarPanel))  
       {  
          case 0 :  
             MessageBox.Show("You have clicked Panel One.");  
             break;  
          case 1 :  
             MessageBox.Show("You have clicked Panel Two.");  
             break;  
       }  
    }  
    ```  
  
    ```cpp  
    private:  
       void statusBar1_PanelClick(System::Object ^  sender,  
          System::Windows::Forms::StatusBarPanelClickEventArgs ^  e)  
       {  
          switch (statusBar1->Panels->IndexOf(e->StatusBarPanel))  
          {  
             case 0 :  
                MessageBox::Show("You have clicked Panel One.");  
                break;  
             case 1 :  
                MessageBox::Show("You have clicked Panel Two.");  
                break;  
          }  
       }  
    ```  
  
     <span data-ttu-id="067b2-111">(Visual C# [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)]) 이벤트 처리기를 등록 하려면 폼의 생성자에 다음 코드를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="067b2-111">(Visual C#, [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)]) Place the following code in the form's constructor to register the event handler.</span></span>  
  
    ```csharp  
    this.statusBar1.PanelClick += new   
       System.Windows.Forms.StatusBarPanelClickEventHandler   
       (this.statusBar1_PanelClick);  
    ```  
  
    ```cpp  
    this->statusBar1->PanelClick += gcnew  
       System::Windows::Forms::StatusBarPanelClickEventHandler  
       (this, &Form1::statusBar1_PanelClick);  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="067b2-112">참고 항목</span><span class="sxs-lookup"><span data-stu-id="067b2-112">See Also</span></span>  
 <xref:System.Windows.Forms.StatusBar>  
 <xref:System.Windows.Forms.ToolStripStatusLabel>  
 [<span data-ttu-id="067b2-113">방법: 상태 표시줄 패널의 크기 설정</span><span class="sxs-lookup"><span data-stu-id="067b2-113">How to: Set the Size of Status-Bar Panels</span></span>](../../../../docs/framework/winforms/controls/how-to-set-the-size-of-status-bar-panels.md)  
 [<span data-ttu-id="067b2-114">연습: 런타임에 상태 표시줄 정보 업데이트</span><span class="sxs-lookup"><span data-stu-id="067b2-114">Walkthrough: Updating Status Bar Information at Run Time</span></span>](../../../../docs/framework/winforms/controls/walkthrough-updating-status-bar-information-at-run-time.md)  
 [<span data-ttu-id="067b2-115">StatusBar 컨트롤 개요</span><span class="sxs-lookup"><span data-stu-id="067b2-115">StatusBar Control Overview</span></span>](../../../../docs/framework/winforms/controls/statusbar-control-overview-windows-forms.md)
