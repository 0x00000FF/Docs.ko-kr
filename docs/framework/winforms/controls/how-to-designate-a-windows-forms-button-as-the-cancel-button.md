---
title: '방법: Windows Forms Button을 취소 단추로 지정'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- buttons [Windows Forms], cancel buttons
- Button control [Windows Forms], designating as cancel button
ms.assetid: 252f0834-e54b-44d9-96f7-ee5f50e94f2c
ms.openlocfilehash: ad95a527ea72858cc106c87d8712110e018e97b2
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59231437"
---
# <a name="how-to-designate-a-windows-forms-button-as-the-cancel-button"></a><span data-ttu-id="6de80-102">방법: Windows Forms Button을 취소 단추로 지정</span><span class="sxs-lookup"><span data-stu-id="6de80-102">How to: Designate a Windows Forms Button as the Cancel Button</span></span>
<span data-ttu-id="6de80-103">모든 Windows Form에 지정할 수 있습니다는 <xref:System.Windows.Forms.Button> 취소 단추를 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="6de80-103">On any Windows Form, you can designate a <xref:System.Windows.Forms.Button> control to be the cancel button.</span></span> <span data-ttu-id="6de80-104">사용자에 관계 없이 폼에서 다른 컨트롤에 포커스가 ESC 키를 누를 때마다 취소 단추를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="6de80-104">A cancel button is clicked whenever the user presses the ESC key, regardless of which other control on the form has the focus.</span></span> <span data-ttu-id="6de80-105">신속 하 게 조치를 커밋하지 않고 작업을 종료할 수 있도록 프로그래밍할 때 일반적으로 이러한 단추를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="6de80-105">Such a button is usually programmed to enable the user to quickly exit an operation without committing to any action.</span></span>  
  
### <a name="to-designate-the-cancel-button"></a><span data-ttu-id="6de80-106">취소 단추를 지정 하려면</span><span class="sxs-lookup"><span data-stu-id="6de80-106">To designate the cancel button</span></span>  
  
1.  <span data-ttu-id="6de80-107">폼의 설정 <xref:System.Windows.Forms.Form.CancelButton%2A> 속성을 적절 한 <xref:System.Windows.Forms.Button> 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="6de80-107">Set the form's <xref:System.Windows.Forms.Form.CancelButton%2A> property to the appropriate <xref:System.Windows.Forms.Button> control.</span></span>  
  
    ```vb  
    Private Sub SetCancelButton(ByVal myCancelBtn As Button)  
       Me.CancelButton = myCancelBtn  
    End Sub  
    ```  
  
    ```csharp  
    private void SetCancelButton(Button myCancelBtn)  
    {  
       this.CancelButton = myCancelBtn;  
    }  
    ```  
  
    ```cpp  
    private:  
       void SetCancelButton(Button ^ myCancelBtn)  
       {  
          this->CancelButton = myCancelBtn;  
       }  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="6de80-108">참고자료</span><span class="sxs-lookup"><span data-stu-id="6de80-108">See also</span></span>

- <xref:System.Windows.Forms.Form.CancelButton%2A>
- [<span data-ttu-id="6de80-109">Button 컨트롤 개요</span><span class="sxs-lookup"><span data-stu-id="6de80-109">Button Control Overview</span></span>](button-control-overview-windows-forms.md)
- [<span data-ttu-id="6de80-110">Windows Forms Button 컨트롤 선택 방법</span><span class="sxs-lookup"><span data-stu-id="6de80-110">Ways to Select a Windows Forms Button Control</span></span>](ways-to-select-a-windows-forms-button-control.md)
- [<span data-ttu-id="6de80-111">방법: Windows Forms 단추 클릭에 응답</span><span class="sxs-lookup"><span data-stu-id="6de80-111">How to: Respond to Windows Forms Button Clicks</span></span>](how-to-respond-to-windows-forms-button-clicks.md)
- [<span data-ttu-id="6de80-112">방법: Windows Forms 단추를 적용 단추로 지정</span><span class="sxs-lookup"><span data-stu-id="6de80-112">How to: Designate a Windows Forms Button as the Accept Button</span></span>](how-to-designate-a-windows-forms-button-as-the-accept-button.md)
- [<span data-ttu-id="6de80-113">Button 컨트롤</span><span class="sxs-lookup"><span data-stu-id="6de80-113">Button Control</span></span>](button-control-windows-forms.md)
