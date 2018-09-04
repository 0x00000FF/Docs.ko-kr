---
title: '방법: 디자이너를 사용하여 TreeNode에 바로 가기 메뉴 연결'
ms.date: 03/30/2017
helpviewer_keywords:
- shortcut menus [Windows Forms], attaching to TreeNodes
- TreeNode [Windows Forms], attaching a shortcut menu using Designer
ms.assetid: 8e45e184-1313-4f8f-90ff-2cd5789b2268
ms.openlocfilehash: 77c4b01100aec2df16d5eb844f73f7a2bfa115aa
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/04/2018
ms.locfileid: "43534780"
---
# <a name="how-to-attach-a-shortcut-menu-to-a-treenode-using-the-designer"></a><span data-ttu-id="290fd-102">방법: 디자이너를 사용하여 TreeNode에 바로 가기 메뉴 연결</span><span class="sxs-lookup"><span data-stu-id="290fd-102">How to: Attach a Shortcut Menu to a TreeNode Using the Designer</span></span>
<span data-ttu-id="290fd-103">Windows Forms <xref:System.Windows.Forms.TreeView> 제어 노드, 파일 및 Windows 운영 체제에서 Windows 탐색기 기능의 왼쪽된 창에서 표시 폴더와 유사한 계층 구조를 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="290fd-103">The Windows Forms <xref:System.Windows.Forms.TreeView> control displays a hierarchy of nodes, similar to the files and folders displayed in the left pane of the Windows Explorer feature in Windows operating systems.</span></span> <span data-ttu-id="290fd-104">설정 하 여 합니다 <xref:System.Windows.Forms.Control.ContextMenuStrip%2A> 속성을 제공할 수 있습니다 상황에 맞는 작업 사용자에 게는 마우스 오른쪽 단추로 클릭는 <xref:System.Windows.Forms.TreeView> 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="290fd-104">By setting the <xref:System.Windows.Forms.Control.ContextMenuStrip%2A> property, you can provide context-sensitive operations to the user when they right-click the <xref:System.Windows.Forms.TreeView> control.</span></span> <span data-ttu-id="290fd-105">연결 하 여는 <xref:System.Windows.Forms.ContextMenuStrip> 구성 요소를 개별 <xref:System.Windows.Forms.TreeNode> 항목을 사용자 지정된 된 바로 가기 메뉴 기능 수준을 추가할 수 있습니다 프로그램 <xref:System.Windows.Forms.TreeView> 컨트롤입니다.</span><span class="sxs-lookup"><span data-stu-id="290fd-105">By associating a <xref:System.Windows.Forms.ContextMenuStrip> component with individual <xref:System.Windows.Forms.TreeNode> items, you can add a customized level of shortcut menu functionality to your <xref:System.Windows.Forms.TreeView> controls.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="290fd-106">표시되는 대화 상자와 메뉴 명령은 활성 설정이나 버전에 따라 도움말에서 설명하는 것과 다를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="290fd-106">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="290fd-107">설정을 변경하려면 **도구** 메뉴에서 **설정 가져오기 및 내보내기** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="290fd-107">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="290fd-108">자세한 내용은 [Visual Studio IDE 개인 설정](/visualstudio/ide/personalizing-the-visual-studio-ide)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="290fd-108">For more information, see [Personalize the Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).</span></span>  
  
### <a name="to-associate-a-shortcut-menu-with-a-treenode-at-design-time"></a><span data-ttu-id="290fd-109">디자인 타임에는 트리 노드를 사용 하 여 바로 가기 메뉴를 연결 하려면</span><span class="sxs-lookup"><span data-stu-id="290fd-109">To associate a shortcut menu with a TreeNode at design time</span></span>  
  
1.  <span data-ttu-id="290fd-110">추가 된 <xref:System.Windows.Forms.TreeView> 폼에 컨트롤을 추가한 다음 노드를는 <xref:System.Windows.Forms.TreeView> 필요에 따라 합니다.</span><span class="sxs-lookup"><span data-stu-id="290fd-110">Add a <xref:System.Windows.Forms.TreeView> control to your form, and then add nodes to the <xref:System.Windows.Forms.TreeView> as needed.</span></span> <span data-ttu-id="290fd-111">자세한 내용은 [방법: Windows Forms TreeView 컨트롤을 사용 하 여 노드 추가 및 제거](../../../../docs/framework/winforms/controls/how-to-add-and-remove-nodes-with-the-windows-forms-treeview-control.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="290fd-111">For more information, see [How to: Add and Remove Nodes with the Windows Forms TreeView Control](../../../../docs/framework/winforms/controls/how-to-add-and-remove-nodes-with-the-windows-forms-treeview-control.md).</span></span>  
  
2.  <span data-ttu-id="290fd-112">추가 된 <xref:System.Windows.Forms.ContextMenuStrip> 구성 요소를 폼에 다음 런타임에 사용할 수 있도록 하려는 노드 수준의 작업을 나타내는 바로 가기 메뉴에 메뉴 항목을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="290fd-112">Add a <xref:System.Windows.Forms.ContextMenuStrip> component to your form, and then add menu items to the shortcut menu that represent node-level operations you wish to make available at run time.</span></span> <span data-ttu-id="290fd-113">자세한 내용은 [방법: ContextMenuStrip에 메뉴 항목 추가](../../../../docs/framework/winforms/controls/how-to-add-menu-items-to-a-contextmenustrip.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="290fd-113">For more information, see [How to: Add Menu Items to a ContextMenuStrip](../../../../docs/framework/winforms/controls/how-to-add-menu-items-to-a-contextmenustrip.md).</span></span>  
  
3.  <span data-ttu-id="290fd-114">다시를 **TreeNodeEditor** 대화 상자를 <xref:System.Windows.Forms.TreeView> 컨트롤을 편집 하 고 설정 하려면 노드를 선택 해당 <xref:System.Windows.Forms.ContextMenuStrip> 추가한 바로 가기 메뉴에는 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="290fd-114">Reopen the **TreeNodeEditor** dialog box for the <xref:System.Windows.Forms.TreeView> control, select the node to edit, and set its <xref:System.Windows.Forms.ContextMenuStrip> property to the shortcut menu that you added.</span></span>  
  
4.  <span data-ttu-id="290fd-115">이 속성을 설정 하는 경우 바로 가기 메뉴에서 노드를 마우스 오른쪽 단추로 클릭할 때 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="290fd-115">When this property is set, the shortcut menu will be displayed when you right-click the node.</span></span>  
  
     <span data-ttu-id="290fd-116">처리할 코드를 작성 하려고 또한는 <xref:System.Windows.Forms.ToolStripItem.Click> 이러한 메뉴 항목에 대 한 이벤트입니다.</span><span class="sxs-lookup"><span data-stu-id="290fd-116">Additionally, you will want to write code to handle the <xref:System.Windows.Forms.ToolStripItem.Click> events for these menu items.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="290fd-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="290fd-117">See Also</span></span>  
 [<span data-ttu-id="290fd-118">TreeView 컨트롤</span><span class="sxs-lookup"><span data-stu-id="290fd-118">TreeView Control</span></span>](../../../../docs/framework/winforms/controls/treeview-control-windows-forms.md)  
 [<span data-ttu-id="290fd-119">TreeView 컨트롤 개요</span><span class="sxs-lookup"><span data-stu-id="290fd-119">TreeView Control Overview</span></span>](../../../../docs/framework/winforms/controls/treeview-control-overview-windows-forms.md)  
 [<span data-ttu-id="290fd-120">ContextMenuStrip 컨트롤</span><span class="sxs-lookup"><span data-stu-id="290fd-120">ContextMenuStrip Control</span></span>](../../../../docs/framework/winforms/controls/contextmenustrip-control.md)
