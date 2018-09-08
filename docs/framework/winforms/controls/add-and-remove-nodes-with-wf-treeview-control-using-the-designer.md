---
title: '방법: 디자이너를 사용하여 Windows Forms TreeView 컨트롤에서 노드 추가 및 제거'
ms.date: 03/30/2017
helpviewer_keywords:
- examples [Windows Forms], TreeView control
- TreeView control [Windows Forms], removing nodes
- tree nodes in TreeView control
- TreeView control [Windows Forms], adding nodes
ms.assetid: 35bf1750-045e-4ec5-97cb-b47b0dbdaa2c
ms.openlocfilehash: 95f3f097d8e01828f2727bac742c752b656019e5
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/08/2018
ms.locfileid: "44211881"
---
# <a name="how-to-add-and-remove-nodes-with-the-windows-forms-treeview-control-using-the-designer"></a>방법: 디자이너를 사용하여 Windows Forms TreeView 컨트롤에서 노드 추가 및 제거
Windows Forms 있으므로 <xref:System.Windows.Forms.TreeView> 해당 부모 노드를 주의 기울여야 하는 노드를 추가 하는 경우 컨트롤이 계층적 방식으로 노드를 표시 합니다.  
  
 다음 절차를 수행 하려면을 **Windows 응용 프로그램** 포함 하는 양식을 사용 하 여 프로젝트를 <xref:System.Windows.Forms.TreeView> 제어 합니다. 이러한 프로젝트 설정에 대 한 자세한 내용은 [방법: Windows 응용 프로그램 프로젝트를 만듭니다](https://msdn.microsoft.com/library/b2f93fed-c635-4705-8d0e-cf079a264efa) 및 [방법: Windows Forms에 컨트롤 추가](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md)합니다.  
  
> [!NOTE]
>  표시되는 대화 상자와 메뉴 명령은 활성 설정이나 버전에 따라 도움말에서 설명하는 것과 다를 수 있습니다. 설정을 변경하려면 **도구** 메뉴에서 **설정 가져오기 및 내보내기** 를 선택합니다. 자세한 내용은 [Visual Studio IDE 개인 설정](/visualstudio/ide/personalizing-the-visual-studio-ide)을 참조하세요.  
  
### <a name="to-add-or-remove-nodes-in-the-designer"></a>추가 하거나 디자이너에서 노드를 제거 하려면  
  
1.  <xref:System.Windows.Forms.TreeView> 컨트롤을 선택합니다.  
  
2.  에 **속성** 창에서 클릭 합니다 **줄임표** (![VisualStudioEllipsesButton 스크린 샷](../../../../docs/framework/winforms/media/vbellipsesbutton.png "vbEllipsesButton")) 단추 옆에 <xref:System.Windows.Forms.TreeView.Nodes%2A> 속성입니다.  
  
     합니다 **트리 노드 편집기** 나타납니다.  
  
3.  노드를 추가 하려면 루트 노드가 있어야 합니다. 클릭 하 여 루트를 먼저 추가 해야 하나 존재 하지 않는 경우는 **루트 추가** 단추입니다. 루트 또는 다른 노드를 선택 하 고 클릭 한 다음 자식 노드를 추가할 수 있습니다 합니다 **자식 추가** 단추입니다.  
  
4.  노드를 삭제 하려면 삭제 한 다음 클릭 노드를 선택 합니다 **삭제** 단추입니다.  
  
## <a name="see-also"></a>참고 항목  
 [TreeView 컨트롤](../../../../docs/framework/winforms/controls/treeview-control-windows-forms.md)  
 [TreeView 컨트롤 개요](../../../../docs/framework/winforms/controls/treeview-control-overview-windows-forms.md)  
 [방법: Windows Forms TreeView 컨트롤의 아이콘 설정](../../../../docs/framework/winforms/controls/how-to-set-icons-for-the-windows-forms-treeview-control.md)  
 [방법: Windows Forms TreeView 컨트롤의 노드 전체 반복](../../../../docs/framework/winforms/controls/how-to-iterate-through-all-nodes-of-a-windows-forms-treeview-control.md)  
 [방법: 클릭한 TreeView 노드 확인](../../../../docs/framework/winforms/controls/how-to-determine-which-treeview-node-was-clicked-windows-forms.md)  
 [방법: TreeView 또는 ListView 컨트롤에 사용자 지정 정보 추가(Windows Forms)](../../../../docs/framework/winforms/controls/add-custom-information-to-a-treeview-or-listview-control-wf.md)
