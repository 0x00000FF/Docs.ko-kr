---
title: '방법: Windows Forms CheckBox 컨트롤을 사용하여 옵션 설정'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
f1_keywords:
- checked
helpviewer_keywords:
- CheckBox control [Windows Forms], checked state
- check boxes [Windows Forms], using to set options
- CheckBox control [Windows Forms], using to set options
ms.assetid: 2ac70498-7e3e-4e07-8901-ccabaeb5fd3e
ms.openlocfilehash: dc9e7b1aea74874c66bf9eb96a5b919ed9b4b73b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33534088"
---
# <a name="how-to-set-options-with-windows-forms-checkbox-controls"></a><span data-ttu-id="112ee-102">방법: Windows Forms CheckBox 컨트롤을 사용하여 옵션 설정</span><span class="sxs-lookup"><span data-stu-id="112ee-102">How to: Set Options with Windows Forms CheckBox Controls</span></span>
<span data-ttu-id="112ee-103">Windows Forms <xref:System.Windows.Forms.CheckBox> 컨트롤이 True/False 사용자에 게 부여 하는 데 사용 되 나 예/아니요 옵션입니다.</span><span class="sxs-lookup"><span data-stu-id="112ee-103">A Windows Forms <xref:System.Windows.Forms.CheckBox> control is used to give users True/False or Yes/No options.</span></span> <span data-ttu-id="112ee-104">컨트롤 선택 된 경우 확인 표시가 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="112ee-104">The control displays a check mark when it is selected.</span></span>  
  
### <a name="to-set-options-with-checkbox-controls"></a><span data-ttu-id="112ee-105">확인란 컨트롤을 사용할 옵션을 설정 하려면</span><span class="sxs-lookup"><span data-stu-id="112ee-105">To set options with CheckBox controls</span></span>  
  
1.  <span data-ttu-id="112ee-106">값을 검사는 <xref:System.Windows.Forms.CheckBox.Checked%2A> 속성의 상태를 확인 하는 옵션을 설정 하려면 해당 값을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="112ee-106">Examine the value of the <xref:System.Windows.Forms.CheckBox.Checked%2A> property to determine its state, and use that value to set an option.</span></span>  
  
     <span data-ttu-id="112ee-107">경우 아래의 코드 예제에는 <xref:System.Windows.Forms.CheckBox> 컨트롤의 <xref:System.Windows.Forms.CheckBox.CheckedChanged> 이벤트는 폼의 <xref:System.Windows.Forms.Control.AllowDrop%2A> 속성이로 설정 되어 `false` 는 확인란을 선택 하는 경우.</span><span class="sxs-lookup"><span data-stu-id="112ee-107">In the code sample below, when the <xref:System.Windows.Forms.CheckBox> control's <xref:System.Windows.Forms.CheckBox.CheckedChanged> event is raised, the form's <xref:System.Windows.Forms.Control.AllowDrop%2A> property is set to `false` if the check box is checked.</span></span> <span data-ttu-id="112ee-108">이 사용자 상호 작용을 제한 하려는 경우에 유용 합니다.</span><span class="sxs-lookup"><span data-stu-id="112ee-108">This is useful for situations where you want to restrict user interaction.</span></span>  
  
    ```vb  
    Private Sub CheckBox1_CheckedChanged(ByVal sender As System.Object, _  
       ByVal e As System.EventArgs) Handles CheckBox1.CheckedChanged  
       ' Determine the CheckState of the check box.  
       If CheckBox1.CheckState = CheckState.Checked Then  
          ' If checked, do not allow items to be dragged onto the form.  
          Me.AllowDrop = False  
       End If  
    End Sub  
    ```  
  
    ```csharp  
    private void checkBox1_CheckedChanged(object sender, System.EventArgs e)  
    {  
       // Determine the CheckState of the check box.  
       if (checkBox1.CheckState == CheckState.Checked)   
       {  
          // If checked, do not allow items to be dragged onto the form.  
          this.AllowDrop = false;  
       }  
    }  
    ```  
  
    ```cpp  
    private:  
       void checkBox1_CheckedChanged(System::Object ^ sender,  
          System::EventArgs ^ e)  
       {  
          // Determine the CheckState of the check box.  
          if (checkBox1->CheckState == CheckState::Checked)   
          {  
             // If checked, do not allow items to be dragged onto the form.  
             this->AllowDrop = false;  
          }  
       }  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="112ee-109">참고 항목</span><span class="sxs-lookup"><span data-stu-id="112ee-109">See Also</span></span>  
 <xref:System.Windows.Forms.CheckBox>  
 [<span data-ttu-id="112ee-110">CheckBox 컨트롤 개요</span><span class="sxs-lookup"><span data-stu-id="112ee-110">CheckBox Control Overview</span></span>](../../../../docs/framework/winforms/controls/checkbox-control-overview-windows-forms.md)  
 [<span data-ttu-id="112ee-111">방법: Windows Forms CheckBox 클릭에 응답</span><span class="sxs-lookup"><span data-stu-id="112ee-111">How to: Respond to Windows Forms CheckBox Clicks</span></span>](../../../../docs/framework/winforms/controls/how-to-respond-to-windows-forms-checkbox-clicks.md)  
 [<span data-ttu-id="112ee-112">CheckBox 컨트롤</span><span class="sxs-lookup"><span data-stu-id="112ee-112">CheckBox Control</span></span>](../../../../docs/framework/winforms/controls/checkbox-control-windows-forms.md)
