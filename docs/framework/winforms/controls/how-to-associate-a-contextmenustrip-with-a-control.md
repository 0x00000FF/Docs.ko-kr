---
title: '방법: ContextMenuStrip과 컨트롤 연결'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- context menus [Windows Forms], relating
- ContextMenuStrips [Windows Forms], associating with controls
- context menus [Windows Forms], associating with controls
- ContextMenuStrips [Windows Forms], relating
ms.assetid: 6fc40a42-5d69-427f-aa30-0a146193226b
ms.openlocfilehash: 4b61da8dc9f36e0a80807547e2049ef512c94747
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/09/2019
ms.locfileid: "57718339"
---
# <a name="how-to-associate-a-contextmenustrip-with-a-control"></a><span data-ttu-id="dad09-102">방법: ContextMenuStrip과 컨트롤 연결</span><span class="sxs-lookup"><span data-stu-id="dad09-102">How to: Associate a ContextMenuStrip with a Control</span></span>
<span data-ttu-id="dad09-103">컨트롤 및 바로 가기 메뉴를 만든 후 다음 절차를 따라 사용자가 컨트롤을 마우스 오른쪽 단추로 클릭할 때 지정된 바로 가기 메뉴를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="dad09-103">After creating your controls and shortcut menus, use the following procedures to display a given shortcut menu when the user right-clicks the control.</span></span> <span data-ttu-id="dad09-104">이러한 절차에서는 <xref:System.Windows.Forms.ContextMenuStrip>을 Windows Form 및 <xref:System.Windows.Forms.ToolStrip> 컨트롤과 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="dad09-104">These procedures associate a <xref:System.Windows.Forms.ContextMenuStrip> with a Windows Form and with a <xref:System.Windows.Forms.ToolStrip> control.</span></span>  
  
### <a name="to-associate-a-contextmenustrip-with-a-windows-form"></a><span data-ttu-id="dad09-105">ContextMenuStrip을 Windows Form과 연결하려면</span><span class="sxs-lookup"><span data-stu-id="dad09-105">To associate a ContextMenuStrip with a Windows Form</span></span>  
  
1.  <span data-ttu-id="dad09-106"><xref:System.Windows.Forms.Control.ContextMenuStrip%2A> 속성을 연결된 <xref:System.Windows.Forms.ContextMenuStrip>의 이름으로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="dad09-106">Set the <xref:System.Windows.Forms.Control.ContextMenuStrip%2A> property to the name of the associated <xref:System.Windows.Forms.ContextMenuStrip>.</span></span>  
  
### <a name="to-associate-a-contextmenustrip-with-a-toolstrip-control"></a><span data-ttu-id="dad09-107">ContextMenuStrip을 ToolStrip 컨트롤과 연결하려면</span><span class="sxs-lookup"><span data-stu-id="dad09-107">To associate a ContextMenuStrip with a ToolStrip control</span></span>  
  
1.  <span data-ttu-id="dad09-108">컨트롤의 <xref:System.Windows.Forms.Control.ContextMenuStrip%2A> 속성을 연결된 <xref:System.Windows.Forms.ContextMenuStrip>의 이름으로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="dad09-108">Set the control's <xref:System.Windows.Forms.Control.ContextMenuStrip%2A> property to the name of the associated <xref:System.Windows.Forms.ContextMenuStrip>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="dad09-109">예제</span><span class="sxs-lookup"><span data-stu-id="dad09-109">Example</span></span>  
 <span data-ttu-id="dad09-110">다음 코드 예제에서는 Windows Form 및 <xref:System.Windows.Forms.ToolStrip>을 만들고 다른 <xref:System.Windows.Forms.ContextMenuStrip> 컨트롤을 각각에 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="dad09-110">The following code example creates a Windows Form and a <xref:System.Windows.Forms.ToolStrip>, and associates a different <xref:System.Windows.Forms.ContextMenuStrip> control with each of them.</span></span>  
  
 [!code-csharp[System.Windows.Forms.ContextMenuStrip#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ContextMenuStrip/CS/form1.cs#1)]
 [!code-vb[System.Windows.Forms.ContextMenuStrip#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ContextMenuStrip/VB/form1.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="dad09-111">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="dad09-111">Compiling the Code</span></span>  
 <span data-ttu-id="dad09-112">이 예제에는 다음 사항이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="dad09-112">This example requires:</span></span>  
  
-   <span data-ttu-id="dad09-113">System, System.Data, System.Drawing 및 System.Windows.Forms 어셈블리에 대한 참조</span><span class="sxs-lookup"><span data-stu-id="dad09-113">References to the System, System.Data, System.Drawing and System.Windows.Forms assemblies.</span></span>  
  
 <span data-ttu-id="dad09-114">Visual Basic 또는 Visual C#에 대 한 명령줄에서이 예제를 빌드하는 방법에 대 한 내용은 [명령줄에서 빌드](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md) 하거나 [csc.exe를 사용한 명령줄 빌드](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="dad09-114">For information about building this example from the command line for Visual Basic or Visual C#, see [Building from the Command Line](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md) or [Command-line Building With csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span></span> <span data-ttu-id="dad09-115">또한 새 프로젝트에 코드를 붙여 넣어 Visual Studio에서이 예제를 빌드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dad09-115">You can also build this example in Visual Studio by pasting the code into a new project.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dad09-116">참고자료</span><span class="sxs-lookup"><span data-stu-id="dad09-116">See also</span></span>
- <xref:System.Windows.Forms.ContextMenuStrip>
- <xref:System.Windows.Forms.Control.ContextMenuStrip%2A>
- <xref:System.Windows.Forms.ToolStrip>
- [<span data-ttu-id="dad09-117">방법: ContextMenuStrip에 메뉴 항목 추가</span><span class="sxs-lookup"><span data-stu-id="dad09-117">How to: Add Menu Items to a ContextMenuStrip</span></span>](how-to-add-menu-items-to-a-contextmenustrip.md)
- [<span data-ttu-id="dad09-118">ContextMenuStrip 컨트롤</span><span class="sxs-lookup"><span data-stu-id="dad09-118">ContextMenuStrip Control</span></span>](contextmenustrip-control.md)
