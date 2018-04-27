---
title: '방법: TableLayoutPanel 컨트롤의 자식 컨트롤 고정 및 도킹'
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-winforms
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- csharp
- vb
f1_keywords:
- net.ComponentModel.StyleCollectionEditor.TLP.AnchorDock
helpviewer_keywords:
- layout [Windows Forms], child controls
- controls [Windows Forms], child
- child controls [Windows Forms], anchoring and docking
- TableLayoutPanel control [Windows Forms], child controls
ms.assetid: 0d267c35-25f1-49b8-8976-c64e8f0ddc0b
caps.latest.revision: 13
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 2469242f2a84800fa00f507dcec37ea1950076c5
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/26/2018
---
# <a name="how-to-anchor-and-dock-child-controls-in-a-tablelayoutpanel-control"></a><span data-ttu-id="ae5b9-102">방법: TableLayoutPanel 컨트롤의 자식 컨트롤 고정 및 도킹</span><span class="sxs-lookup"><span data-stu-id="ae5b9-102">How to: Anchor and Dock Child Controls in a TableLayoutPanel Control</span></span>
<span data-ttu-id="ae5b9-103"><xref:System.Windows.Forms.TableLayoutPanel> 컨트롤은 자식 컨트롤의 <xref:System.Windows.Forms.Control.Anchor%2A> 및 <xref:System.Windows.Forms.Control.Dock%2A> 속성을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="ae5b9-103">The <xref:System.Windows.Forms.TableLayoutPanel> control supports the <xref:System.Windows.Forms.Control.Anchor%2A> and <xref:System.Windows.Forms.Control.Dock%2A> properties in its child controls.</span></span>  
  
### <a name="to-align-a-child-control-in-a-tablelayoutpanel-cell"></a><span data-ttu-id="ae5b9-104">TableLayoutPanel 셀에서 자식 컨트롤을 맞추려면</span><span class="sxs-lookup"><span data-stu-id="ae5b9-104">To align a child control in a TableLayoutPanel cell</span></span>  
  
1.  <span data-ttu-id="ae5b9-105">폼에 <xref:System.Windows.Forms.TableLayoutPanel> 컨트롤을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="ae5b9-105">Create a <xref:System.Windows.Forms.TableLayoutPanel> control on your form.</span></span>  
  
2.  <span data-ttu-id="ae5b9-106">값으로 설정 된 <xref:System.Windows.Forms.TableLayoutPanel> 컨트롤의 <xref:System.Windows.Forms.TableLayoutPanel.ColumnCount%2A> 및 <xref:System.Windows.Forms.TableLayoutPanel.RowCount%2A> 속성을 **1**합니다.</span><span class="sxs-lookup"><span data-stu-id="ae5b9-106">Set the value of the <xref:System.Windows.Forms.TableLayoutPanel> control's <xref:System.Windows.Forms.TableLayoutPanel.ColumnCount%2A> and <xref:System.Windows.Forms.TableLayoutPanel.RowCount%2A> properties to **1**.</span></span>  
  
3.  <span data-ttu-id="ae5b9-107"><xref:System.Windows.Forms.TableLayoutPanel> 컨트롤에 <xref:System.Windows.Forms.Button> 컨트롤을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="ae5b9-107">Create a <xref:System.Windows.Forms.Button> control in the <xref:System.Windows.Forms.TableLayoutPanel> control.</span></span> <span data-ttu-id="ae5b9-108"><xref:System.Windows.Forms.Button>이 셀의 왼쪽 위 모퉁이에 배치됩니다.</span><span class="sxs-lookup"><span data-stu-id="ae5b9-108">The <xref:System.Windows.Forms.Button> occupies the upper-left corner of the cell.</span></span>  
  
4.  <span data-ttu-id="ae5b9-109"><xref:System.Windows.Forms.Button> 컨트롤의 <xref:System.Windows.Forms.Control.Anchor%2A> 속성 값을 `Left`로 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="ae5b9-109">Change the value of the <xref:System.Windows.Forms.Button> control's <xref:System.Windows.Forms.Control.Anchor%2A> property to `Left`.</span></span> <span data-ttu-id="ae5b9-110"><xref:System.Windows.Forms.Button>이 이동하여 셀의 왼쪽 테두리에 맞춰집니다.</span><span class="sxs-lookup"><span data-stu-id="ae5b9-110">The <xref:System.Windows.Forms.Button> control moves to align with the left border of the cell.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="ae5b9-111">이 동작은 다른 컨테이너 컨트롤의 동작과 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="ae5b9-111">This behavior differs from the behavior of other container controls.</span></span> <span data-ttu-id="ae5b9-112">다른 컨테이너 컨트롤에서는 <xref:System.Windows.Forms.Control.Anchor%2A> 속성을 설정할 때 자식 컨트롤이 이동하지 않고 고정된 컨트롤과 부모 컨테이너 경계 간의 거리가 <xref:System.Windows.Forms.Control.Anchor%2A> 속성을 설정할 때 고정됩니다.</span><span class="sxs-lookup"><span data-stu-id="ae5b9-112">In other container controls, the child control does not move when the <xref:System.Windows.Forms.Control.Anchor%2A> property is set, and the distance between the anchored control and the parent container's boundary is fixed at the time the <xref:System.Windows.Forms.Control.Anchor%2A> property is set.</span></span>  
  
5.  <span data-ttu-id="ae5b9-113"><xref:System.Windows.Forms.Button> 컨트롤의 <xref:System.Windows.Forms.Control.Anchor%2A> 속성 값을 `Top, Left`로 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="ae5b9-113">Change the value of the <xref:System.Windows.Forms.Button> control's <xref:System.Windows.Forms.Control.Anchor%2A> property to `Top, Left`.</span></span> <span data-ttu-id="ae5b9-114"><xref:System.Windows.Forms.Button> 컨트롤이 이동하여 셀의 왼쪽 위 모퉁이에 배치됩니다.</span><span class="sxs-lookup"><span data-stu-id="ae5b9-114">The <xref:System.Windows.Forms.Button> control moves to occupy the top-left corner of the cell.</span></span>  
  
6.  <span data-ttu-id="ae5b9-115">5 단계를 반복 값의 `Top, Right` 이동 하는 <xref:System.Windows.Forms.Button> 셀의 오른쪽 위 모퉁이를 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="ae5b9-115">Repeat step 5 with a value of `Top, Right` to move the <xref:System.Windows.Forms.Button> control to the top-right corner of the cell.</span></span> <span data-ttu-id="ae5b9-116">`Bottom, Left` 및 `Bottom, Right` 값으로 반복합니다.</span><span class="sxs-lookup"><span data-stu-id="ae5b9-116">Repeat with values of `Bottom, Left` and `Bottom, Right`.</span></span>  
  
### <a name="to-stretch-a-child-control-in-a-tablelayoutpanel-cell"></a><span data-ttu-id="ae5b9-117">TableLayoutPanel 셀에서 자식 컨트롤을 늘이려면</span><span class="sxs-lookup"><span data-stu-id="ae5b9-117">To stretch a child control in a TableLayoutPanel cell</span></span>  
  
1.  <span data-ttu-id="ae5b9-118"><xref:System.Windows.Forms.Button> 컨트롤의 <xref:System.Windows.Forms.Control.Anchor%2A> 속성 값을 `Left, Right`로 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="ae5b9-118">Change the value of the <xref:System.Windows.Forms.Button> control's <xref:System.Windows.Forms.Control.Anchor%2A> property to `Left, Right`.</span></span> <span data-ttu-id="ae5b9-119"><xref:System.Windows.Forms.Button> 컨트롤의 크기가 조정되어 셀에 가로로 늘여집니다.</span><span class="sxs-lookup"><span data-stu-id="ae5b9-119">The <xref:System.Windows.Forms.Button> control is resized to stretch across the cell.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="ae5b9-120">이 동작은 다른 컨테이너 컨트롤의 동작과 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="ae5b9-120">This behavior differs from the behavior of other container controls.</span></span> <span data-ttu-id="ae5b9-121">다른 컨테이너 컨트롤의 자식 컨트롤은 크기를 조정할 때는 <xref:System.Windows.Forms.Control.Anchor%2A> 속성이 `Left, Right` 또는 `Top, Bottom`합니다.</span><span class="sxs-lookup"><span data-stu-id="ae5b9-121">In other container controls, the child control is not resized when the <xref:System.Windows.Forms.Control.Anchor%2A> property is set to `Left, Right` or `Top, Bottom`.</span></span>  
  
2.  <span data-ttu-id="ae5b9-122"><xref:System.Windows.Forms.Button> 컨트롤의 <xref:System.Windows.Forms.Control.Anchor%2A> 속성 값을 `Top, Bottom`로 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="ae5b9-122">Change the value of the <xref:System.Windows.Forms.Button> control's <xref:System.Windows.Forms.Control.Anchor%2A> property to `Top, Bottom`.</span></span> <span data-ttu-id="ae5b9-123"><xref:System.Windows.Forms.Button> 컨트롤의 크기가 조정되어 셀의 맨 위에서 맨 아래까지 세로로 늘여집니다.</span><span class="sxs-lookup"><span data-stu-id="ae5b9-123">The <xref:System.Windows.Forms.Button> control is resized to stretch from the top to the bottom of the cell.</span></span>  
  
3.  <span data-ttu-id="ae5b9-124"><xref:System.Windows.Forms.Button> 컨트롤의 <xref:System.Windows.Forms.Control.Anchor%2A> 속성 값을 `Top, Bottom, Left, Right`로 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="ae5b9-124">Change the value of the <xref:System.Windows.Forms.Button> control's <xref:System.Windows.Forms.Control.Anchor%2A> property to `Top, Bottom, Left, Right`.</span></span> <span data-ttu-id="ae5b9-125"><xref:System.Windows.Forms.Button> 컨트롤의 크기가 조정되어 셀을 채웁니다.</span><span class="sxs-lookup"><span data-stu-id="ae5b9-125">The <xref:System.Windows.Forms.Button> control is resized to fill the cell.</span></span>  
  
4.  <span data-ttu-id="ae5b9-126"><xref:System.Windows.Forms.Button> 컨트롤의 <xref:System.Windows.Forms.Control.Anchor%2A> 속성 값을 `None`로 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="ae5b9-126">Change the value of the <xref:System.Windows.Forms.Button> control's <xref:System.Windows.Forms.Control.Anchor%2A> property to `None`.</span></span> <span data-ttu-id="ae5b9-127"><xref:System.Windows.Forms.Button> 컨트롤의 크기가 조정되고 셀의 가운데에 배치됩니다.</span><span class="sxs-lookup"><span data-stu-id="ae5b9-127">The <xref:System.Windows.Forms.Button> control is resized and centered in the cell.</span></span>  
  
5.  <span data-ttu-id="ae5b9-128"><xref:System.Windows.Forms.Button> 컨트롤의 <xref:System.Windows.Forms.Control.Dock%2A> 속성 값을 <xref:System.Windows.Forms.DockStyle.Left>로 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="ae5b9-128">Change the value of the <xref:System.Windows.Forms.Button> control's <xref:System.Windows.Forms.Control.Dock%2A> property to <xref:System.Windows.Forms.DockStyle.Left>.</span></span> <span data-ttu-id="ae5b9-129"><xref:System.Windows.Forms.Button>이 이동하여 셀의 왼쪽 테두리에 맞춰집니다.</span><span class="sxs-lookup"><span data-stu-id="ae5b9-129">The <xref:System.Windows.Forms.Button> control moves to align with the left border of the cell.</span></span> <span data-ttu-id="ae5b9-130"><xref:System.Windows.Forms.Button> 컨트롤의 너비는 유지되지만 높이가 조정되어 셀을 세로로 채웁니다.</span><span class="sxs-lookup"><span data-stu-id="ae5b9-130">The <xref:System.Windows.Forms.Button> control retains its width, but its height is resized to fill the cell vertically.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="ae5b9-131">이는 다른 컨테이너 컨트롤에서 발생하는 동작과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="ae5b9-131">This is the same behavior that occurs in other container controls.</span></span>  
  
6.  <span data-ttu-id="ae5b9-132"><xref:System.Windows.Forms.Button> 컨트롤의 <xref:System.Windows.Forms.Control.Dock%2A> 속성 값을 <xref:System.Windows.Forms.DockStyle.Fill>로 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="ae5b9-132">Change the value of the <xref:System.Windows.Forms.Button> control's <xref:System.Windows.Forms.Control.Dock%2A> property to <xref:System.Windows.Forms.DockStyle.Fill>.</span></span> <span data-ttu-id="ae5b9-133"><xref:System.Windows.Forms.Button> 컨트롤의 크기가 조정되어 셀을 채웁니다.</span><span class="sxs-lookup"><span data-stu-id="ae5b9-133">The <xref:System.Windows.Forms.Button> control is resized to fill the cell.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ae5b9-134">예제</span><span class="sxs-lookup"><span data-stu-id="ae5b9-134">Example</span></span>  
 <span data-ttu-id="ae5b9-135">다음 그림에서는 개별 <xref:System.Windows.Forms.TableLayoutPanel> 셀 5개에 고정된 단추 5개를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="ae5b9-135">The following illustration shows five buttons anchored in five separate <xref:System.Windows.Forms.TableLayoutPanel> cells.</span></span>  
  
 <span data-ttu-id="ae5b9-136">![TableLayoutPanel 고정](../../../../docs/framework/winforms/controls/media/vs-tlpanchor.gif "VS_TLPanchor")</span><span class="sxs-lookup"><span data-stu-id="ae5b9-136">![TableLayoutPanel Anchoring](../../../../docs/framework/winforms/controls/media/vs-tlpanchor.gif "VS_TLPanchor")</span></span>  
  
 <span data-ttu-id="ae5b9-137">다음 그림에서는 개별 <xref:System.Windows.Forms.TableLayoutPanel> 셀 4개의 모퉁이에 고정된 단추 4개를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="ae5b9-137">The following illustration shows four buttons anchored in the corners of four separate <xref:System.Windows.Forms.TableLayoutPanel> cells.</span></span>  
  
 <span data-ttu-id="ae5b9-138">![TableLayoutPanel 고정](../../../../docs/framework/winforms/controls/media/vs-tlpanchor2.gif "VS_TLPanchor2")</span><span class="sxs-lookup"><span data-stu-id="ae5b9-138">![TableLayoutPanel Anchoring](../../../../docs/framework/winforms/controls/media/vs-tlpanchor2.gif "VS_TLPanchor2")</span></span>  
  
 <span data-ttu-id="ae5b9-139">다음 그림에서는 개별 <xref:System.Windows.Forms.TableLayoutPanel> 셀 3에 고정하여 늘여진 단추 3개를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="ae5b9-139">The following illustration shows three buttons stretched by anchoring in three separate <xref:System.Windows.Forms.TableLayoutPanel> cells.</span></span>  
  
 <span data-ttu-id="ae5b9-140">![TableLayoutPanel 고정](../../../../docs/framework/winforms/controls/media/vs-tlpanchor3.gif "VS_TLPAnchor3")</span><span class="sxs-lookup"><span data-stu-id="ae5b9-140">![TableLayoutPanel Anchoring](../../../../docs/framework/winforms/controls/media/vs-tlpanchor3.gif "VS_TLPAnchor3")</span></span>  
  
 <span data-ttu-id="ae5b9-141">다음 코드 예제에서는 <xref:System.Windows.Forms.TableLayoutPanel> 컨트롤의 <xref:System.Windows.Forms.Button> 컨트롤에 대한 <xref:System.Windows.Forms.Control.Anchor%2A> 속성 값의 모든 조합을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="ae5b9-141">The following code example demonstrates all the combinations of <xref:System.Windows.Forms.Control.Anchor%2A> property values for a <xref:System.Windows.Forms.Button> control in a <xref:System.Windows.Forms.TableLayoutPanel> control.</span></span>  
  
 [!code-csharp[System.Windows.Forms.TableLayoutPanel.AnchorExampleForm#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.TableLayoutPanel.AnchorExampleForm/CS/TlpAnchorExampleForm.cs#1)]
 [!code-vb[System.Windows.Forms.TableLayoutPanel.AnchorExampleForm#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.TableLayoutPanel.AnchorExampleForm/VB/TlpAnchorExampleForm.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="ae5b9-142">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="ae5b9-142">Compiling the Code</span></span>  
 <span data-ttu-id="ae5b9-143">이 예제에는 다음 사항이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="ae5b9-143">This example requires:</span></span>  
  
-   <span data-ttu-id="ae5b9-144">System, System.Data, System.Drawing 및 System.Windows.Forms 어셈블리에 대한 참조</span><span class="sxs-lookup"><span data-stu-id="ae5b9-144">References to the System, System.Data, System.Drawing and System.Windows.Forms assemblies.</span></span>  
  
 <span data-ttu-id="ae5b9-145">Visual Basic 또는 Visual C#에 대 한 명령줄에서이 예제를 빌드하는 방법에 대 한 정보를 참조 하십시오. [명령줄에서 빌드](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) 또는 [사용한 명령줄 빌드 csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="ae5b9-145">For information about building this example from the command line for visual Basic or Visual C#, see [Building from the Command Line](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) or [Command-line Building With csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span></span> <span data-ttu-id="ae5b9-146">[!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)] 에서 코드를 새 프로젝트에 붙여넣어 이 예제를 빌드할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ae5b9-146">You can also build this example in [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)] by pasting the code into a new project.</span></span>  <span data-ttu-id="ae5b9-147">[방법: Visual Studio를 사용하여 전체 Windows Forms 코드 예제 컴파일 및 실행](http://msdn.microsoft.com/library/Bb129228\(v=vs.110\))을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ae5b9-147">Also see [How to: Compile and Run a Complete Windows Forms Code Example Using Visual Studio](http://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ae5b9-148">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ae5b9-148">See Also</span></span>  
 <xref:System.Windows.Forms.TableLayoutPanel>  
 [<span data-ttu-id="ae5b9-149">TableLayoutPanel 컨트롤</span><span class="sxs-lookup"><span data-stu-id="ae5b9-149">TableLayoutPanel Control</span></span>](../../../../docs/framework/winforms/controls/tablelayoutpanel-control-windows-forms.md)
