---
title: '방법: TableLayoutPanel 컨트롤에서 자식 컨트롤 고정 및 도킹'
ms.date: 03/30/2017
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
ms.openlocfilehash: a84b00e93354a9aaff074a570cee931591816161
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/09/2019
ms.locfileid: "59329923"
---
# <a name="how-to-anchor-and-dock-child-controls-in-a-tablelayoutpanel-control"></a><span data-ttu-id="51e13-102">방법: TableLayoutPanel 컨트롤에서 자식 컨트롤 고정 및 도킹</span><span class="sxs-lookup"><span data-stu-id="51e13-102">How to: Anchor and Dock Child Controls in a TableLayoutPanel Control</span></span>
<span data-ttu-id="51e13-103"><xref:System.Windows.Forms.TableLayoutPanel> 컨트롤은 자식 컨트롤의 <xref:System.Windows.Forms.Control.Anchor%2A> 및 <xref:System.Windows.Forms.Control.Dock%2A> 속성을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="51e13-103">The <xref:System.Windows.Forms.TableLayoutPanel> control supports the <xref:System.Windows.Forms.Control.Anchor%2A> and <xref:System.Windows.Forms.Control.Dock%2A> properties in its child controls.</span></span>  
  
### <a name="to-align-a-child-control-in-a-tablelayoutpanel-cell"></a><span data-ttu-id="51e13-104">TableLayoutPanel 셀에서 자식 컨트롤을 맞추려면</span><span class="sxs-lookup"><span data-stu-id="51e13-104">To align a child control in a TableLayoutPanel cell</span></span>  
  
1. <span data-ttu-id="51e13-105">폼에 <xref:System.Windows.Forms.TableLayoutPanel> 컨트롤을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="51e13-105">Create a <xref:System.Windows.Forms.TableLayoutPanel> control on your form.</span></span>  
  
2. <span data-ttu-id="51e13-106">값을 설정 합니다 <xref:System.Windows.Forms.TableLayoutPanel> 컨트롤의 <xref:System.Windows.Forms.TableLayoutPanel.ColumnCount%2A> 하 고 <xref:System.Windows.Forms.TableLayoutPanel.RowCount%2A> 속성을 **1**합니다.</span><span class="sxs-lookup"><span data-stu-id="51e13-106">Set the value of the <xref:System.Windows.Forms.TableLayoutPanel> control's <xref:System.Windows.Forms.TableLayoutPanel.ColumnCount%2A> and <xref:System.Windows.Forms.TableLayoutPanel.RowCount%2A> properties to **1**.</span></span>  
  
3. <span data-ttu-id="51e13-107"><xref:System.Windows.Forms.TableLayoutPanel> 컨트롤에 <xref:System.Windows.Forms.Button> 컨트롤을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="51e13-107">Create a <xref:System.Windows.Forms.Button> control in the <xref:System.Windows.Forms.TableLayoutPanel> control.</span></span> <span data-ttu-id="51e13-108"><xref:System.Windows.Forms.Button>이 셀의 왼쪽 위 모퉁이에 배치됩니다.</span><span class="sxs-lookup"><span data-stu-id="51e13-108">The <xref:System.Windows.Forms.Button> occupies the upper-left corner of the cell.</span></span>  
  
4. <span data-ttu-id="51e13-109"><xref:System.Windows.Forms.Button> 컨트롤의 <xref:System.Windows.Forms.Control.Anchor%2A> 속성 값을 `Left`로 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="51e13-109">Change the value of the <xref:System.Windows.Forms.Button> control's <xref:System.Windows.Forms.Control.Anchor%2A> property to `Left`.</span></span> <span data-ttu-id="51e13-110"><xref:System.Windows.Forms.Button>이 이동하여 셀의 왼쪽 테두리에 맞춰집니다.</span><span class="sxs-lookup"><span data-stu-id="51e13-110">The <xref:System.Windows.Forms.Button> control moves to align with the left border of the cell.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="51e13-111">이 동작은 다른 컨테이너 컨트롤의 동작과 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="51e13-111">This behavior differs from the behavior of other container controls.</span></span> <span data-ttu-id="51e13-112">다른 컨테이너 컨트롤에서는 <xref:System.Windows.Forms.Control.Anchor%2A> 속성을 설정할 때 자식 컨트롤이 이동하지 않고 고정된 컨트롤과 부모 컨테이너 경계 간의 거리가 <xref:System.Windows.Forms.Control.Anchor%2A> 속성을 설정할 때 고정됩니다.</span><span class="sxs-lookup"><span data-stu-id="51e13-112">In other container controls, the child control does not move when the <xref:System.Windows.Forms.Control.Anchor%2A> property is set, and the distance between the anchored control and the parent container's boundary is fixed at the time the <xref:System.Windows.Forms.Control.Anchor%2A> property is set.</span></span>  
  
5. <span data-ttu-id="51e13-113"><xref:System.Windows.Forms.Button> 컨트롤의 <xref:System.Windows.Forms.Control.Anchor%2A> 속성 값을 `Top, Left`로 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="51e13-113">Change the value of the <xref:System.Windows.Forms.Button> control's <xref:System.Windows.Forms.Control.Anchor%2A> property to `Top, Left`.</span></span> <span data-ttu-id="51e13-114"><xref:System.Windows.Forms.Button> 컨트롤이 이동하여 셀의 왼쪽 위 모퉁이에 배치됩니다.</span><span class="sxs-lookup"><span data-stu-id="51e13-114">The <xref:System.Windows.Forms.Button> control moves to occupy the top-left corner of the cell.</span></span>  
  
6. <span data-ttu-id="51e13-115">5 단계를 반복 값의 `Top, Right` 이동 하는 <xref:System.Windows.Forms.Button> 셀의 오른쪽 위 모퉁이에 컨트롤입니다.</span><span class="sxs-lookup"><span data-stu-id="51e13-115">Repeat step 5 with a value of `Top, Right` to move the <xref:System.Windows.Forms.Button> control to the top-right corner of the cell.</span></span> <span data-ttu-id="51e13-116">`Bottom, Left` 및 `Bottom, Right` 값으로 반복합니다.</span><span class="sxs-lookup"><span data-stu-id="51e13-116">Repeat with values of `Bottom, Left` and `Bottom, Right`.</span></span>  
  
### <a name="to-stretch-a-child-control-in-a-tablelayoutpanel-cell"></a><span data-ttu-id="51e13-117">TableLayoutPanel 셀에서 자식 컨트롤을 늘이려면</span><span class="sxs-lookup"><span data-stu-id="51e13-117">To stretch a child control in a TableLayoutPanel cell</span></span>  
  
1. <span data-ttu-id="51e13-118"><xref:System.Windows.Forms.Button> 컨트롤의 <xref:System.Windows.Forms.Control.Anchor%2A> 속성 값을 `Left, Right`로 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="51e13-118">Change the value of the <xref:System.Windows.Forms.Button> control's <xref:System.Windows.Forms.Control.Anchor%2A> property to `Left, Right`.</span></span> <span data-ttu-id="51e13-119"><xref:System.Windows.Forms.Button> 컨트롤의 크기가 조정되어 셀에 가로로 늘여집니다.</span><span class="sxs-lookup"><span data-stu-id="51e13-119">The <xref:System.Windows.Forms.Button> control is resized to stretch across the cell.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="51e13-120">이 동작은 다른 컨테이너 컨트롤의 동작과 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="51e13-120">This behavior differs from the behavior of other container controls.</span></span> <span data-ttu-id="51e13-121">다른 컨테이너 컨트롤의 자식 컨트롤이 아닙니다 경우 크기를 조정 합니다 <xref:System.Windows.Forms.Control.Anchor%2A> 속성이로 설정 되어 `Left, Right` 또는 `Top, Bottom`.</span><span class="sxs-lookup"><span data-stu-id="51e13-121">In other container controls, the child control is not resized when the <xref:System.Windows.Forms.Control.Anchor%2A> property is set to `Left, Right` or `Top, Bottom`.</span></span>  
  
2. <span data-ttu-id="51e13-122"><xref:System.Windows.Forms.Button> 컨트롤의 <xref:System.Windows.Forms.Control.Anchor%2A> 속성 값을 `Top, Bottom`로 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="51e13-122">Change the value of the <xref:System.Windows.Forms.Button> control's <xref:System.Windows.Forms.Control.Anchor%2A> property to `Top, Bottom`.</span></span> <span data-ttu-id="51e13-123"><xref:System.Windows.Forms.Button> 컨트롤의 크기가 조정되어 셀의 맨 위에서 맨 아래까지 세로로 늘여집니다.</span><span class="sxs-lookup"><span data-stu-id="51e13-123">The <xref:System.Windows.Forms.Button> control is resized to stretch from the top to the bottom of the cell.</span></span>  
  
3. <span data-ttu-id="51e13-124"><xref:System.Windows.Forms.Button> 컨트롤의 <xref:System.Windows.Forms.Control.Anchor%2A> 속성 값을 `Top, Bottom, Left, Right`로 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="51e13-124">Change the value of the <xref:System.Windows.Forms.Button> control's <xref:System.Windows.Forms.Control.Anchor%2A> property to `Top, Bottom, Left, Right`.</span></span> <span data-ttu-id="51e13-125"><xref:System.Windows.Forms.Button> 컨트롤의 크기가 조정되어 셀을 채웁니다.</span><span class="sxs-lookup"><span data-stu-id="51e13-125">The <xref:System.Windows.Forms.Button> control is resized to fill the cell.</span></span>  
  
4. <span data-ttu-id="51e13-126"><xref:System.Windows.Forms.Button> 컨트롤의 <xref:System.Windows.Forms.Control.Anchor%2A> 속성 값을 `None`로 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="51e13-126">Change the value of the <xref:System.Windows.Forms.Button> control's <xref:System.Windows.Forms.Control.Anchor%2A> property to `None`.</span></span> <span data-ttu-id="51e13-127"><xref:System.Windows.Forms.Button> 컨트롤의 크기가 조정되고 셀의 가운데에 배치됩니다.</span><span class="sxs-lookup"><span data-stu-id="51e13-127">The <xref:System.Windows.Forms.Button> control is resized and centered in the cell.</span></span>  
  
5. <span data-ttu-id="51e13-128"><xref:System.Windows.Forms.Button> 컨트롤의 <xref:System.Windows.Forms.Control.Dock%2A> 속성 값을 <xref:System.Windows.Forms.DockStyle.Left>로 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="51e13-128">Change the value of the <xref:System.Windows.Forms.Button> control's <xref:System.Windows.Forms.Control.Dock%2A> property to <xref:System.Windows.Forms.DockStyle.Left>.</span></span> <span data-ttu-id="51e13-129"><xref:System.Windows.Forms.Button>이 이동하여 셀의 왼쪽 테두리에 맞춰집니다.</span><span class="sxs-lookup"><span data-stu-id="51e13-129">The <xref:System.Windows.Forms.Button> control moves to align with the left border of the cell.</span></span> <span data-ttu-id="51e13-130"><xref:System.Windows.Forms.Button> 컨트롤의 너비는 유지되지만 높이가 조정되어 셀을 세로로 채웁니다.</span><span class="sxs-lookup"><span data-stu-id="51e13-130">The <xref:System.Windows.Forms.Button> control retains its width, but its height is resized to fill the cell vertically.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="51e13-131">이는 다른 컨테이너 컨트롤에서 발생하는 동작과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="51e13-131">This is the same behavior that occurs in other container controls.</span></span>  
  
6. <span data-ttu-id="51e13-132"><xref:System.Windows.Forms.Button> 컨트롤의 <xref:System.Windows.Forms.Control.Dock%2A> 속성 값을 <xref:System.Windows.Forms.DockStyle.Fill>로 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="51e13-132">Change the value of the <xref:System.Windows.Forms.Button> control's <xref:System.Windows.Forms.Control.Dock%2A> property to <xref:System.Windows.Forms.DockStyle.Fill>.</span></span> <span data-ttu-id="51e13-133"><xref:System.Windows.Forms.Button> 컨트롤의 크기가 조정되어 셀을 채웁니다.</span><span class="sxs-lookup"><span data-stu-id="51e13-133">The <xref:System.Windows.Forms.Button> control is resized to fill the cell.</span></span>  
  
## <a name="example"></a><span data-ttu-id="51e13-134">예제</span><span class="sxs-lookup"><span data-stu-id="51e13-134">Example</span></span>  
 <span data-ttu-id="51e13-135">다음 그림에서는 개별 <xref:System.Windows.Forms.TableLayoutPanel> 셀 5개에 고정된 단추 5개를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="51e13-135">The following illustration shows five buttons anchored in five separate <xref:System.Windows.Forms.TableLayoutPanel> cells.</span></span>  
  
 <span data-ttu-id="51e13-136">![TableLayoutPanel 고정](./media/vs-tlpanchor.gif "VS_TLPanchor")</span><span class="sxs-lookup"><span data-stu-id="51e13-136">![TableLayoutPanel Anchoring](./media/vs-tlpanchor.gif "VS_TLPanchor")</span></span>  
  
 <span data-ttu-id="51e13-137">다음 그림에서는 개별 <xref:System.Windows.Forms.TableLayoutPanel> 셀 4개의 모퉁이에 고정된 단추 4개를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="51e13-137">The following illustration shows four buttons anchored in the corners of four separate <xref:System.Windows.Forms.TableLayoutPanel> cells.</span></span>  
  
 <span data-ttu-id="51e13-138">![TableLayoutPanel 고정](./media/vs-tlpanchor2.gif "VS_TLPanchor2")</span><span class="sxs-lookup"><span data-stu-id="51e13-138">![TableLayoutPanel Anchoring](./media/vs-tlpanchor2.gif "VS_TLPanchor2")</span></span>  
  
 <span data-ttu-id="51e13-139">다음 그림에서는 개별 <xref:System.Windows.Forms.TableLayoutPanel> 셀 3에 고정하여 늘여진 단추 3개를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="51e13-139">The following illustration shows three buttons stretched by anchoring in three separate <xref:System.Windows.Forms.TableLayoutPanel> cells.</span></span>  
  
 <span data-ttu-id="51e13-140">![TableLayoutPanel 고정](./media/vs-tlpanchor3.gif "VS_TLPAnchor3")</span><span class="sxs-lookup"><span data-stu-id="51e13-140">![TableLayoutPanel Anchoring](./media/vs-tlpanchor3.gif "VS_TLPAnchor3")</span></span>  
  
 <span data-ttu-id="51e13-141">다음 코드 예제에서는 <xref:System.Windows.Forms.TableLayoutPanel> 컨트롤의 <xref:System.Windows.Forms.Button> 컨트롤에 대한 <xref:System.Windows.Forms.Control.Anchor%2A> 속성 값의 모든 조합을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="51e13-141">The following code example demonstrates all the combinations of <xref:System.Windows.Forms.Control.Anchor%2A> property values for a <xref:System.Windows.Forms.Button> control in a <xref:System.Windows.Forms.TableLayoutPanel> control.</span></span>  
  
 [!code-csharp[System.Windows.Forms.TableLayoutPanel.AnchorExampleForm#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.TableLayoutPanel.AnchorExampleForm/CS/TlpAnchorExampleForm.cs#1)]
 [!code-vb[System.Windows.Forms.TableLayoutPanel.AnchorExampleForm#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.TableLayoutPanel.AnchorExampleForm/VB/TlpAnchorExampleForm.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="51e13-142">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="51e13-142">Compiling the Code</span></span>  
 <span data-ttu-id="51e13-143">이 예제에는 다음 사항이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="51e13-143">This example requires:</span></span>  
  
-   <span data-ttu-id="51e13-144">System, System.Data, System.Drawing 및 System.Windows.Forms 어셈블리에 대한 참조</span><span class="sxs-lookup"><span data-stu-id="51e13-144">References to the System, System.Data, System.Drawing and System.Windows.Forms assemblies.</span></span>  
  
 <span data-ttu-id="51e13-145">Visual Basic 또는 Visual C#에 대 한 명령줄에서이 예제를 빌드하는 방법에 대 한 내용은 [명령줄에서 빌드](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md) 하거나 [csc.exe를 사용한 명령줄 빌드](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="51e13-145">For information about building this example from the command line for Visual Basic or Visual C#, see [Building from the Command Line](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md) or [Command-line Building With csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span></span> <span data-ttu-id="51e13-146">또한 새 프로젝트에 코드를 붙여 넣어 Visual Studio에서이 예제를 빌드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="51e13-146">You can also build this example in Visual Studio by pasting the code into a new project.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="51e13-147">참고자료</span><span class="sxs-lookup"><span data-stu-id="51e13-147">See also</span></span>

- <xref:System.Windows.Forms.TableLayoutPanel>
- [<span data-ttu-id="51e13-148">TableLayoutPanel 컨트롤</span><span class="sxs-lookup"><span data-stu-id="51e13-148">TableLayoutPanel Control</span></span>](tablelayoutpanel-control-windows-forms.md)
