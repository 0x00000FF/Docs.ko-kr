---
title: '방법: MenuStrip 선택 여백 및 이미지 여백 구성'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- margins [Windows Forms], setting in MenuStrip controls
- menus [Windows Forms], setting margins
- MenuStrip control [Windows Forms], configuring check and image margins
ms.assetid: 45a9075d-4bea-4ce2-9b2c-7619aa39f8ce
ms.openlocfilehash: 872139fd234bafb303168d906c6ec96ce7b1611c
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/04/2018
ms.locfileid: "43529611"
---
# <a name="how-to-configure-menustrip-check-margins-and-image-margins"></a><span data-ttu-id="f1bed-102">방법: MenuStrip 선택 여백 및 이미지 여백 구성</span><span class="sxs-lookup"><span data-stu-id="f1bed-102">How to: Configure MenuStrip Check Margins and Image Margins</span></span>
<span data-ttu-id="f1bed-103"><xref:System.Windows.Forms.ToolStripDropDownMenu.ShowImageMargin%2A> 및 <xref:System.Windows.Forms.ToolStripDropDownMenu.ShowCheckMargin%2A> 속성을 다양한 조합으로 설정하여 <xref:System.Windows.Forms.MenuStrip>을 사용자 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f1bed-103">You can customize a <xref:System.Windows.Forms.MenuStrip> by setting the <xref:System.Windows.Forms.ToolStripDropDownMenu.ShowImageMargin%2A> and <xref:System.Windows.Forms.ToolStripDropDownMenu.ShowCheckMargin%2A> properties in various combinations.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f1bed-104">예제</span><span class="sxs-lookup"><span data-stu-id="f1bed-104">Example</span></span>  
 <span data-ttu-id="f1bed-105">다음 코드 예제에서는 <xref:System.Windows.Forms.ContextMenuStrip> 검사 여백 및 이미지 여백을 설정하고 사용자 지정하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="f1bed-105">The following code example demonstrates how to set and customize the <xref:System.Windows.Forms.ContextMenuStrip> check margins and image margins.</span></span> <span data-ttu-id="f1bed-106">절차는 <xref:System.Windows.Forms.ContextMenuStrip> 또는 <xref:System.Windows.Forms.MenuStrip>에서 동일합니다.</span><span class="sxs-lookup"><span data-stu-id="f1bed-106">The procedure is the same for a <xref:System.Windows.Forms.ContextMenuStrip> or a <xref:System.Windows.Forms.MenuStrip>.</span></span>  
  
 [!code-csharp[System.Windows.Forms.ToolStrip.Misc#60](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/CS/Program.cs#60)]
 [!code-vb[System.Windows.Forms.ToolStrip.Misc#60](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/VB/Program.vb#60)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="f1bed-107">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="f1bed-107">Compiling the Code</span></span>  
 <span data-ttu-id="f1bed-108">이 예제에는 다음 사항이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="f1bed-108">This example requires:</span></span>  
  
-   <span data-ttu-id="f1bed-109">System, System.Drawing 및 System.Windows.Forms 어셈블리에 대한 참조</span><span class="sxs-lookup"><span data-stu-id="f1bed-109">References to the System, System.Drawing and System.Windows.Forms assemblies.</span></span>  
  
 <span data-ttu-id="f1bed-110">Visual Basic 또는 Visual C#에 대 한 명령줄에서이 예제를 빌드하는 방법에 대 한 내용은 [명령줄에서 빌드](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) 하거나 [csc.exe를 사용한 명령줄 빌드](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="f1bed-110">For information about building this example from the command line for Visual Basic or Visual C#, see [Building from the Command Line](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) or [Command-line Building With csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span></span> <span data-ttu-id="f1bed-111">또한 새 프로젝트에 코드를 붙여 넣어 Visual Studio에서이 예제를 빌드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f1bed-111">You can also build this example in Visual Studio by pasting the code into a new project.</span></span>  <span data-ttu-id="f1bed-112">[방법: Visual Studio를 사용하여 전체 Windows Forms 코드 예제 컴파일 및 실행](https://msdn.microsoft.com/library/Bb129228\(v=vs.110\))을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f1bed-112">Also see [How to: Compile and Run a Complete Windows Forms Code Example Using Visual Studio](https://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f1bed-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="f1bed-113">See Also</span></span>  
 <xref:System.Windows.Forms.MenuStrip>  
 <xref:System.Windows.Forms.ContextMenuStrip>  
 <xref:System.Windows.Forms.ToolStripDropDown>  
 [<span data-ttu-id="f1bed-114">ToolStrip 컨트롤</span><span class="sxs-lookup"><span data-stu-id="f1bed-114">ToolStrip Control</span></span>](../../../../docs/framework/winforms/controls/toolstrip-control-windows-forms.md)  
 [<span data-ttu-id="f1bed-115">방법: ContextMenuStrip 컨트롤에서 선택 여백 및 이미지 여백 사용</span><span class="sxs-lookup"><span data-stu-id="f1bed-115">How to: Enable Check Margins and Image Margins in ContextMenuStrip Controls</span></span>](../../../../docs/framework/winforms/controls/how-to-enable-check-margins-and-image-margins-in-contextmenustrip-controls.md)
