---
title: '방법: 디자이너를 사용하여 ToolStripMenuItems 숨기기'
ms.date: 03/30/2017
helpviewer_keywords:
- ToolStripMenuItems [Windows Forms], hiding menu items in designer
- MenuStrip control [Windows Forms], hiding menu items in designer
- menu items [Windows Forms], hiding
ms.assetid: 8f1b057e-3d8a-4f11-88df-935f7b29a836
ms.openlocfilehash: 37371269ef9db929573efff0a8e62c86a51b2c35
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/01/2018
ms.locfileid: "43423876"
---
# <a name="how-to-hide-toolstripmenuitems-using-the-designer"></a>방법: 디자이너를 사용하여 ToolStripMenuItems 숨기기
메뉴 항목 숨기기는 응용 프로그램의 사용자 인터페이스 (UI)를 제어 하 고 사용자 명령을 제한 하는 방법입니다. 종종 전체 메뉴에 메뉴 항목을 모두 사용할 수 없는 경우 숨기려면 해야 합니다. 이 사용자에 대해 더 적은 방해 요소를 표시합니다. 또한 하려는 숨기고 메뉴 또는 메뉴 항목을 사용 하지 않도록 설정으로 숨기는 것 만으로도 사용자 바로 가기 키를 사용 하 여 메뉴 명령에 액세스 하는 것을 금지 하지 않습니다. 메뉴 항목을 사용 하지 않도록 설정 하는 방법은 참조 하세요 [방법: 디자이너를 사용 하 여 ToolStripMenuItems 사용 안 함](../../../../docs/framework/winforms/controls/how-to-disable-toolstripmenuitems-using-the-designer.md)합니다.  
  
> [!NOTE]
>  표시되는 대화 상자와 메뉴 명령은 활성 설정이나 버전에 따라 도움말에서 설명하는 것과 다를 수 있습니다. 설정을 변경하려면 **도구** 메뉴에서 **설정 가져오기 및 내보내기** 를 선택합니다. 자세한 내용은 [Visual Studio IDE 개인 설정](/visualstudio/ide/personalizing-the-visual-studio-ide)을 참조하세요.  
  
### <a name="to-hide-a-top-level-menu-and-its-submenu-items"></a>최상위 메뉴와 해당 하위 메뉴 항목을 숨기려면  
  
1.  최상위 메뉴 항목을 선택 하 고 설정 해당 <xref:System.Windows.Forms.ToolStripItem.Visible%2A> 나 <xref:System.Windows.Forms.ToolStripItem.Available%2A> 속성을 `false`입니다.  
  
     최상위 메뉴 항목을 숨기려면 해당 메뉴에서 모든 메뉴 항목 숨겨집니다. 아닌 다른 위치를 클릭 하면 합니다 <xref:System.Windows.Forms.MenuStrip> 설정한 후 <xref:System.Windows.Forms.ToolStripItem.Visible%2A> 에 `false`, 전체 최상위 메뉴 항목 및 해당 하위 메뉴 항목 폼에 따라서 작업의 런타임 효과 보여주는에서 사라집니다. 디자인 타임에 숨겨진된 최상위 메뉴 항목을 표시 하려면 클릭 합니다 <xref:System.Windows.Forms.MenuStrip> 에 **구성 요소 트레이에**의 **문서 개요**, 또는 속성 표의 맨 위에 있는.  
  
> [!NOTE]
>  거의 전체 메뉴 병합 시나리오에서 여러 문서 MDI (인터페이스) 자식 메뉴를 제외 하 고 숨겨집니다.  
  
### <a name="to-hide-a-submenu-item"></a>하위 메뉴 항목을 숨기려면  
  
1.  하위 메뉴 항목을 선택 하 고 설정 해당 <xref:System.Windows.Forms.ToolStripItem.Visible%2A> 속성을 `false`입니다.  
  
     하위 메뉴 항목을 숨길 때 추가 작업을 위해 쉽게 선택할 수 있도록 디자인 타임에 폼에 표시 유지 합니다. 이 런타임 시 실제로 표시 되지 것입니다.  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Windows.Forms.ToolStripItem.Visible%2A>  
 <xref:System.Windows.Forms.MenuStrip>  
 <xref:System.Windows.Forms.ToolStripMenuItem.Enabled%2A>  
 <xref:System.Windows.Forms.ToolStripItem.Available%2A>  
 <xref:System.Windows.Forms.ToolStripMenuItem.Overflow%2A>  
 [MenuStrip 컨트롤 개요](../../../../docs/framework/winforms/controls/menustrip-control-overview-windows-forms.md)  
 [방법: 디자이너를 사용하여 ToolStripMenuItems를 사용하지 않도록 설정](../../../../docs/framework/winforms/controls/how-to-disable-toolstripmenuitems-using-the-designer.md)
