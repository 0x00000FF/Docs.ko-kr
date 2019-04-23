---
title: '방법: ToolStrip 컨트롤에서 설정/해제 단추 만들기'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- toggle buttons [Windows Forms], creating
- examples [Windows Forms], toolbars
- ToolStrip control [Windows Forms], creating toggle buttons
ms.assetid: d9c197df-4c65-43f2-beee-b68b52b2befc
ms.openlocfilehash: e688e9a220e6c82caa2d107589b5ca9a1e59e72b
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59091254"
---
# <a name="how-to-create-toggle-buttons-in-toolstrip-controls"></a>방법: ToolStrip 컨트롤에서 설정/해제 단추 만들기
사용자가 토글 단추를 클릭 하면 오목 하 게 표시 하 고 사용자가 단추를 다시 클릭 될 때까지 오목한 상태를 유지 합니다.  
  
### <a name="to-create-a-toggling-toolstripbutton"></a>토글 ToolStripButton를 만들려면  
  
-   다음 코드 예제와 같은 코드를 사용 합니다. 이 코드는 폼에 포함 되어 있다고 가정를 <xref:System.Windows.Forms.ToolStrip> 제어 및는 해당 <xref:System.Windows.Forms.ToolStrip.Items%2A> 컬렉션에는 <xref:System.Windows.Forms.ToolStripButton> 호출 `toolStripButton1`합니다. 또한 이벤트 처리기 호출 되었다고 가정 `toolStripButton1_CheckedChanged`합니다.  
  
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
  
## <a name="see-also"></a>참고자료

- <xref:System.Windows.Forms.ToolStripButton>
- [ToolStrip 컨트롤 개요](toolstrip-control-overview-windows-forms.md)
