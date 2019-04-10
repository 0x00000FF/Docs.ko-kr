---
title: '방법: Windows Forms RichTextBox 컨트롤에서 서식 특성의 변경 시기 확인'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- examples [Windows Forms], text boxes
- RichTextBox control [Windows Forms], determining font changes
- text boxes [Windows Forms], determining font changes
- SelChange event
ms.assetid: bdfed015-f77a-41e5-b38f-f8629b2fa166
ms.openlocfilehash: e35ebb7c90be00a814d465af3546de2bcd11c5de
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59183948"
---
# <a name="how-to-determine-when-formatting-attributes-change-in-the-windows-forms-richtextbox-control"></a><span data-ttu-id="46c0f-102">방법: Windows Forms RichTextBox 컨트롤에서 서식 특성의 변경 시기 확인</span><span class="sxs-lookup"><span data-stu-id="46c0f-102">How to: Determine When Formatting Attributes Change in the Windows Forms RichTextBox Control</span></span>
<span data-ttu-id="46c0f-103">Windows Forms의 일반적인 용도 <xref:System.Windows.Forms.RichTextBox> 글꼴 옵션 등 단락 스타일 특성을 사용 하 여 텍스트 서식을 제어 하는 합니다.</span><span class="sxs-lookup"><span data-stu-id="46c0f-103">A common use of the Windows Forms <xref:System.Windows.Forms.RichTextBox> control is formatting text with attributes such as font options or paragraph styles.</span></span> <span data-ttu-id="46c0f-104">응용 프로그램 대부분의 워드프로세싱 응용 프로그램과 마찬가지로 도구 모음을 표시 하기 위해 서식 지정 하는 텍스트의 모든 변경 내용을 추적할 수 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="46c0f-104">Your application may need to keep track of any changes in text formatting for the purpose of displaying a toolbar, as in many word-processing applications.</span></span>  
  
### <a name="to-respond-to-changes-in-formatting-attributes"></a><span data-ttu-id="46c0f-105">서식 특성의 변경 내용에 응답</span><span class="sxs-lookup"><span data-stu-id="46c0f-105">To respond to changes in formatting attributes</span></span>  
  
1.  <span data-ttu-id="46c0f-106">코드를 작성 합니다 <xref:System.Windows.Forms.RichTextBox.SelectionChanged> 특성의 값에 따라 적절 한 작업을 수행 하려면 이벤트 처리기입니다.</span><span class="sxs-lookup"><span data-stu-id="46c0f-106">Write code in the <xref:System.Windows.Forms.RichTextBox.SelectionChanged> event handler to perform an appropriate action depending on the value of the attribute.</span></span> <span data-ttu-id="46c0f-107">다음 예제에서는 값에 따라 도구 모음 단추의 모양을 변경 합니다 <xref:System.Windows.Forms.RichTextBox.SelectionBullet%2A> 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="46c0f-107">The following example changes the appearance of a toolbar button depending on the value of the <xref:System.Windows.Forms.RichTextBox.SelectionBullet%2A> property.</span></span> <span data-ttu-id="46c0f-108">도구 모음 단추 컨트롤에서 삽입 지점을 이동 하는 경우에 업데이트 됩니다.</span><span class="sxs-lookup"><span data-stu-id="46c0f-108">The toolbar button will only be updated when the insertion point is moved in the control.</span></span>  
  
     <span data-ttu-id="46c0f-109">아래 예제에서는 가정 된 폼을 <xref:System.Windows.Forms.RichTextBox> 컨트롤 및 <xref:System.Windows.Forms.ToolBar> 도구 모음 단추를 포함 하는 컨트롤입니다.</span><span class="sxs-lookup"><span data-stu-id="46c0f-109">The example below assumes a form with a <xref:System.Windows.Forms.RichTextBox> control and a <xref:System.Windows.Forms.ToolBar> control that contains a toolbar button.</span></span> <span data-ttu-id="46c0f-110">도구 모음 및 도구 모음 단추에 대 한 자세한 내용은 참조 하세요. [방법: ToolBar 컨트롤에 단추 추가](how-to-add-buttons-to-a-toolbar-control.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="46c0f-110">For more information about toolbars and toolbar buttons, see [How to: Add Buttons to a ToolBar Control](how-to-add-buttons-to-a-toolbar-control.md).</span></span>  
  
    ```vb  
    ' The following code assumes the existence of a toolbar control  
    ' with at least one toolbar button.  
    Private Sub RichTextBox1_SelectionChanged(ByVal sender As Object, ByVal e As System.EventArgs) Handles RichTextBox1.SelectionChanged  
       If RichTextBox1.SelectionBullet = True Then  
          ' Bullet button on toolbar should appear pressed  
          ToolBarButton1.Pushed = True  
       Else  
           ' Bullet button on toolbar should appear unpressed  
           ToolBarButton1.Pushed = False  
       End If  
    End Sub  
    ```  
  
    ```csharp  
    // The following code assumes the existence of a toolbar control  
    // with at least one toolbar button.  
    private void richTextBox1_SelectionChanged(object sender,  
    System.EventArgs e)  
    {  
       if (richTextBox1.SelectionBullet == true)   
       {  
          // Bullet button on toolbar should appear pressed  
          toolBarButton1.Pushed = true;  
       }  
       else   
       {  
          // Bullet button on toolbar should appear unpressed  
          toolBarButton1.Pushed = false;  
       }  
    }  
    ```  
  
    ```cpp  
    // The following code assumes the existence of a toolbar control  
    // with at least one toolbar button.  
    private:  
       System::Void richTextBox1_SelectionChanged(  
          System::Object ^  sender, System::EventArgs ^  e)  
       {  
          if (richTextBox1->SelectionBullet == true)  
          {  
             // Bullet button on toolbar should appear pressed  
             toolBarButton1->Pushed = true;  
          }  
          else  
          {  
             // Bullet button on toolbar should appear unpressed  
             toolBarButton1->Pushed = false;  
          }  
       }  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="46c0f-111">참고자료</span><span class="sxs-lookup"><span data-stu-id="46c0f-111">See also</span></span>

- <xref:System.Windows.Forms.RichTextBox.SelectionChanged>
- <xref:System.Windows.Forms.RichTextBox>
- [<span data-ttu-id="46c0f-112">RichTextBox 컨트롤</span><span class="sxs-lookup"><span data-stu-id="46c0f-112">RichTextBox Control</span></span>](richtextbox-control-windows-forms.md)
- [<span data-ttu-id="46c0f-113">Windows Forms에 사용할 수 있는 컨트롤</span><span class="sxs-lookup"><span data-stu-id="46c0f-113">Controls to Use on Windows Forms</span></span>](controls-to-use-on-windows-forms.md)
