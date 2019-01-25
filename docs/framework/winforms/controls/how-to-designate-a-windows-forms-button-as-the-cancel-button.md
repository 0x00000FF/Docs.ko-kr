---
title: '방법: Windows Forms 단추를 취소 단추로 지정'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- buttons [Windows Forms], cancel buttons
- Button control [Windows Forms], designating as cancel button
ms.assetid: 252f0834-e54b-44d9-96f7-ee5f50e94f2c
ms.openlocfilehash: 74d025677682735fc7f1c68116b2364887f0519c
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54701471"
---
# <a name="how-to-designate-a-windows-forms-button-as-the-cancel-button"></a>방법: Windows Forms 단추를 취소 단추로 지정
모든 Windows Form에 지정할 수 있습니다는 <xref:System.Windows.Forms.Button> 취소 단추를 제어 합니다. 사용자에 관계 없이 폼에서 다른 컨트롤에 포커스가 ESC 키를 누를 때마다 취소 단추를 클릭 합니다. 신속 하 게 조치를 커밋하지 않고 작업을 종료할 수 있도록 프로그래밍할 때 일반적으로 이러한 단추를 사용 합니다.  
  
### <a name="to-designate-the-cancel-button"></a>취소 단추를 지정 하려면  
  
1.  폼의 설정 <xref:System.Windows.Forms.Form.CancelButton%2A> 속성을 적절 한 <xref:System.Windows.Forms.Button> 제어 합니다.  
  
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
  
## <a name="see-also"></a>참고자료
- <xref:System.Windows.Forms.Form.CancelButton%2A>
- [Button 컨트롤 개요](../../../../docs/framework/winforms/controls/button-control-overview-windows-forms.md)
- [Windows Forms Button 컨트롤 선택 방법](../../../../docs/framework/winforms/controls/ways-to-select-a-windows-forms-button-control.md)
- [방법: Windows Forms 단추 클릭에 응답](../../../../docs/framework/winforms/controls/how-to-respond-to-windows-forms-button-clicks.md)
- [방법: Windows Forms 단추를 적용 단추로 지정](../../../../docs/framework/winforms/controls/how-to-designate-a-windows-forms-button-as-the-accept-button.md)
- [Button 컨트롤](../../../../docs/framework/winforms/controls/button-control-windows-forms.md)
