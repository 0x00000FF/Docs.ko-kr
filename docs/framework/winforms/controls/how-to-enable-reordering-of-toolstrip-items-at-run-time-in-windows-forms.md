---
title: "방법: Windows Forms에서 런타임에 ToolStrip 항목 다시 정렬 활성화"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ToolStrip control [Windows Forms], examples
- examples [Windows Forms], toolbars
- toolbars [Windows Forms], rearranging controls
- ToolStrip control [Windows Forms], reordering items
ms.assetid: 8480b69a-379f-4dc2-8dcf-365ed93692b2
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 73ea6d3615780c8def31b7dbdcf870020a106e80
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-enable-reordering-of-toolstrip-items-at-run-time-in-windows-forms"></a>방법: Windows Forms에서 런타임에 ToolStrip 항목 다시 정렬 활성화
다시 정렬 하려면 사용자가 수행할 수 있습니다 <xref:System.Windows.Forms.ToolStripItem> 컨트롤에 <xref:System.Windows.Forms.ToolStrip>합니다.  
  
### <a name="to-enable-toolstripitem-rearrangement-at-run-time"></a>런타임 시 다시 정렬이 ToolStripItem을 사용 하도록 설정 하려면  
  
-   <xref:System.Windows.Forms.ToolStrip.AllowItemReorder%2A> 속성을 `true`으로 설정합니다. 기본적으로 <xref:System.Windows.Forms.ToolStrip.AllowItemReorder%2A> 은 `false`합니다.  
  
     런타임 시 ALT 키와 끌어 마우스 왼쪽된 단추를 누르고 있는 <xref:System.Windows.Forms.ToolStripItem> 다른 위치에 <xref:System.Windows.Forms.ToolStrip>합니다.  
  
    ```vb  
    toolStrip1.AllowItemReorder = True  
    ```  
  
    ```csharp  
    toolStrip1.AllowItemReorder = true;  
    ```  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Windows.Forms.ToolStrip>  
 <xref:System.Windows.Forms.ToolStrip.AllowItemReorder%2A>  
 [ToolStrip 컨트롤 개요](../../../../docs/framework/winforms/controls/toolstrip-control-overview-windows-forms.md)  
 [ToolStrip 컨트롤 아키텍처](../../../../docs/framework/winforms/controls/toolstrip-control-architecture.md)  
 [ToolStrip 기술 요약](../../../../docs/framework/winforms/controls/toolstrip-technology-summary.md)
