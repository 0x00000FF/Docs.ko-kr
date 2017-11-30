---
title: "방법: ToolStripMenuItems 사용 안 함"
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
- cpp
helpviewer_keywords:
- ToolStripMenuItems [Windows Forms], enabling
- ToolStripMenuItems [Windows Forms], disabling
- menu items [Windows Forms], disabling
- disabling menu items
- menu items [Windows Forms], enabling
- menus [Windows Forms], disabling menu items
ms.assetid: bcc1da84-50fd-41d2-8475-103b581d5654
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: e3307da3e0810ea775c799a4b065e1f7484b5779
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-disable-toolstripmenuitems"></a>방법: ToolStripMenuItems 사용 안 함
제한 하거나 사용자의 동작에 대 한 응답으로 메뉴 항목을 설정 하거나 해제 하 여 사용자가 수행 하는 명령을 넓힐 수 있습니다. 메뉴 항목은 기본적으로 활성화 만들어질 때 통해 조정할 수 있습니다는 <xref:System.Windows.Forms.ToolStripMenuItem.Enabled%2A> 속성입니다. 디자인 타임에이 속성을 조작할 수 있습니다는 **속성** 창 또는 코드에서 설정 하 여 프로그래밍 방식으로 합니다.  
  
### <a name="to-disable-a-menu-item-programmatically"></a>메뉴 항목을 프로그래밍 방식으로 사용 하지 않도록 설정 하려면  
  
-   메뉴 항목의 속성을 설정 하는 메서드를 추가 설정 하는 코드는 <xref:System.Windows.Forms.ToolStripMenuItem.Enabled%2A> 속성을 `false`합니다.  
  
    ```vb  
    MenuItem1.Enabled = False  
    ```  
  
    ```csharp  
    menuItem1.Enabled = false;  
    ```  
  
    ```cpp  
    menuItem1->Enabled = false;  
    ```  
  
    > [!TIP]
    >  메뉴의 첫 번째 또는 최상위 메뉴 항목을 사용 하지 않도록 설정 메뉴에서 내에 포함 된 모든 메뉴 항목 숨겨지지만 비활성화 되지 않습니다. 마찬가지로, 하위 메뉴 항목이 포함 된 메뉴 항목을 비활성화 하면 하위 메뉴 항목을 숨깁니다 하지만 비활성화 하지 않습니다. 메뉴의 모든 명령을 사용자에 게 사용할 수 없을 경우이 인해 사용자 인터페이스를 명확 하는 대로 숨기고 전체 메뉴를 사용 하지 않도록 설정 하는 바람직한 프로그래밍 관행을 간주 됩니다. 숨기기 및 메뉴를 사용 하지 않도록 설정 하 고 숨기기만 하더라도 사용자는 바로 가기 키를 통해 메뉴 명령에 액세스 하기 때문에 모든 항목과 하위 메뉴 항목 메뉴를 사용 하지 않도록 해야 합니다. 설정의 <xref:System.Windows.Forms.ToolStripItem.Visible%2A> 에 최상위 메뉴 항목의 `false` 전체 메뉴를 숨기 합니다.  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Windows.Forms.MenuStrip>  
 <xref:System.Windows.Forms.ToolStripMenuItem>  
 [방법: ToolStripMenuItems 숨기기](../../../../docs/framework/winforms/controls/how-to-hide-toolstripmenuitems.md)  
 [MenuStrip 컨트롤 개요](../../../../docs/framework/winforms/controls/menustrip-control-overview-windows-forms.md)
