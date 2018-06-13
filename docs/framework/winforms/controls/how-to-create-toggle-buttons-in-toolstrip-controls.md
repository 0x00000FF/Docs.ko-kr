---
title: '방법: ToolStrip 컨트롤에 설정/해제 단추 만들기'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- toggle buttons [Windows Forms], creating
- examples [Windows Forms], toolbars
- ToolStrip control [Windows Forms], creating toggle buttons
ms.assetid: d9c197df-4c65-43f2-beee-b68b52b2befc
ms.openlocfilehash: a04d531433273328c2d8eb0c5ef614f08c33952a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33530383"
---
# <a name="how-to-create-toggle-buttons-in-toolstrip-controls"></a>방법: ToolStrip 컨트롤에 설정/해제 단추 만들기
사용자가 토글 단추를 클릭 하면 오목 하 게 표시 하 고 사용자가 단추를 다시 클릭할 때까지 모양이 유지 합니다.  
  
### <a name="to-create-a-toggling-toolstripbutton"></a>토글 ToolStripButton를 만들려면  
  
-   다음 코드 예제에서는 같은 코드를 사용 합니다. 이 코드는 폼에 포함 되어 있다고 가정는 <xref:System.Windows.Forms.ToolStrip> 컨트롤과 해당 <xref:System.Windows.Forms.ToolStrip.Items%2A> 컬렉션에 포함 되어는 <xref:System.Windows.Forms.ToolStripButton> 호출 `toolStripButton1`합니다. 또한 라는 이벤트 처리기 있다고 가정 `toolStripButton1_CheckedChanged`합니다.  
  
    ```vb  
    toolStripButton1.CheckOnClick = True  
    toolStripButton1.CheckedChanged AddressOf _  
    EventHandler(toolStripButton1_CheckedChanged);  
    ```  
  
    ```csharp  
    toolStripButton1.CheckOnClick = true;  
    toolStripButton1.CheckedChanged += new _  
    EventHandler(toolStripButton1_CheckedChanged);  
    ```  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Windows.Forms.ToolStripButton>  
 [ToolStrip 컨트롤 개요](../../../../docs/framework/winforms/controls/toolstrip-control-overview-windows-forms.md)
