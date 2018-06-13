---
title: '방법: Windows Forms TreeView 컨트롤을 사용하여 노드 추가 및 제거'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- examples [Windows Forms], TreeView control
- TreeView control [Windows Forms], removing nodes
- tree nodes in TreeView control
- TreeView control [Windows Forms], adding nodes
ms.assetid: de1b82db-4905-449a-9f59-af271a6b6673
ms.openlocfilehash: 2491f4d4c40ea412ee42f8cd99c4c8682baa94a0
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33525940"
---
# <a name="how-to-add-and-remove-nodes-with-the-windows-forms-treeview-control"></a><span data-ttu-id="c3c40-102">방법: Windows Forms TreeView 컨트롤을 사용하여 노드 추가 및 제거</span><span class="sxs-lookup"><span data-stu-id="c3c40-102">How to: Add and Remove Nodes with the Windows Forms TreeView Control</span></span>
<span data-ttu-id="c3c40-103">Windows Forms <xref:System.Windows.Forms.TreeView> 컨트롤의 최상위 노드를 저장 합니다. 해당 <xref:System.Windows.Forms.TreeView.Nodes%2A> 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="c3c40-103">The Windows Forms <xref:System.Windows.Forms.TreeView> control stores the top-level nodes in its <xref:System.Windows.Forms.TreeView.Nodes%2A> collection.</span></span> <span data-ttu-id="c3c40-104">각 <xref:System.Windows.Forms.TreeNode> 역시 자체 <xref:System.Windows.Forms.TreeNode.Nodes%2A> 해당 자식 노드를 저장 하는 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="c3c40-104">Each <xref:System.Windows.Forms.TreeNode> also has its own <xref:System.Windows.Forms.TreeNode.Nodes%2A> collection to store its child nodes.</span></span> <span data-ttu-id="c3c40-105">두 컬렉션 속성은 형식의 <xref:System.Windows.Forms.TreeNodeCollection>, 추가, 사용할 수 있는 표준 컬렉션 멤버를 제거 및 노드 계층의 단일 수준에서 노드를 다시 정렬를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="c3c40-105">Both collection properties are of type <xref:System.Windows.Forms.TreeNodeCollection>, which provides standard collection members that enable you to add, remove, and rearrange the nodes at a single level of the node hierarchy.</span></span>  
  
### <a name="to-add-nodes-programmatically"></a><span data-ttu-id="c3c40-106">프로그래밍 방식으로 노드를 추가 하려면</span><span class="sxs-lookup"><span data-stu-id="c3c40-106">To add nodes programmatically</span></span>  
  
1.  <span data-ttu-id="c3c40-107">사용 하 여는 <xref:System.Windows.Forms.TreeNodeCollection.Add%2A> 트리 보기의 메서드 <xref:System.Windows.Forms.TreeView.Nodes%2A> 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="c3c40-107">Use the <xref:System.Windows.Forms.TreeNodeCollection.Add%2A> method of the tree view's <xref:System.Windows.Forms.TreeView.Nodes%2A> property.</span></span>  
  
    ```vb  
    ' Adds new node as a child node of the currently selected node.  
    Dim newNode As TreeNode = New TreeNode("Text for new node")  
    TreeView1.SelectedNode.Nodes.Add(newNode)  
    ```  
  
    ```csharp  
    // Adds new node as a child node of the currently selected node.  
    TreeNode newNode = new TreeNode("Text for new node");  
    treeView1.SelectedNode.Nodes.Add(newNode);  
    ```  
  
    ```cpp  
    // Adds new node as a child node of the currently selected node.  
    TreeNode ^ newNode = new TreeNode("Text for new node");  
    treeView1->SelectedNode->Nodes->Add(newNode);  
    ```  
  
### <a name="to-remove-nodes-programmatically"></a><span data-ttu-id="c3c40-108">프로그래밍 방식으로 노드를 제거 하려면</span><span class="sxs-lookup"><span data-stu-id="c3c40-108">To remove nodes programmatically</span></span>  
  
1.  <span data-ttu-id="c3c40-109">사용 하 여는 <xref:System.Windows.Forms.TreeNodeCollection.Remove%2A> 메서드 트리 보기의 <xref:System.Windows.Forms.TreeView.Nodes%2A> 단일 노드를 제거 하려면 속성 또는 <xref:System.Windows.Forms.TreeNodeCollection.Clear%2A> 메서드 모든 노드를 선택 취소 합니다.</span><span class="sxs-lookup"><span data-stu-id="c3c40-109">Use the <xref:System.Windows.Forms.TreeNodeCollection.Remove%2A> method of the tree view's <xref:System.Windows.Forms.TreeView.Nodes%2A> property to remove a single node, or the <xref:System.Windows.Forms.TreeNodeCollection.Clear%2A> method to clear all nodes.</span></span>  
  
    ```vb  
    ' Removes currently selected node, or root if nothing is selected.  
    TreeView1.Nodes.Remove(TreeView1.SelectedNode)  
    ' Clears all nodes.  
    TreeView1.Nodes.Clear()  
    ```  
  
    ```csharp  
    // Removes currently selected node, or root if nothing   
    // is selected.  
    treeView1.Nodes.Remove(treeView1.SelectedNode);  
    // Clears all nodes.  
    TreeView1.Nodes.Clear();  
    ```  
  
    ```cpp  
    // Removes currently selected node, or root if nothing  
    // is selected.  
    treeView1->Nodes->Remove(treeView1->SelectedNode);  
    // Clears all nodes.  
    treeView1->Nodes->Clear();  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="c3c40-110">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c3c40-110">See Also</span></span>  
 [<span data-ttu-id="c3c40-111">TreeView 컨트롤</span><span class="sxs-lookup"><span data-stu-id="c3c40-111">TreeView Control</span></span>](../../../../docs/framework/winforms/controls/treeview-control-windows-forms.md)  
 [<span data-ttu-id="c3c40-112">TreeView 컨트롤 개요</span><span class="sxs-lookup"><span data-stu-id="c3c40-112">TreeView Control Overview</span></span>](../../../../docs/framework/winforms/controls/treeview-control-overview-windows-forms.md)  
 [<span data-ttu-id="c3c40-113">방법: Windows Forms TreeView 컨트롤의 아이콘 설정</span><span class="sxs-lookup"><span data-stu-id="c3c40-113">How to: Set Icons for the Windows Forms TreeView Control</span></span>](../../../../docs/framework/winforms/controls/how-to-set-icons-for-the-windows-forms-treeview-control.md)  
 [<span data-ttu-id="c3c40-114">방법: Windows Forms TreeView 컨트롤의 노드 전체 반복</span><span class="sxs-lookup"><span data-stu-id="c3c40-114">How to: Iterate Through All Nodes of a Windows Forms TreeView Control</span></span>](../../../../docs/framework/winforms/controls/how-to-iterate-through-all-nodes-of-a-windows-forms-treeview-control.md)  
 [<span data-ttu-id="c3c40-115">방법: 클릭한 TreeView 노드 확인</span><span class="sxs-lookup"><span data-stu-id="c3c40-115">How to: Determine Which TreeView Node Was Clicked</span></span>](../../../../docs/framework/winforms/controls/how-to-determine-which-treeview-node-was-clicked-windows-forms.md)  
 [<span data-ttu-id="c3c40-116">방법: TreeView 또는 ListView 컨트롤에 사용자 지정 정보 추가(Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="c3c40-116">How to: Add Custom Information to a TreeView or ListView Control (Windows Forms)</span></span>](../../../../docs/framework/winforms/controls/add-custom-information-to-a-treeview-or-listview-control-wf.md)
