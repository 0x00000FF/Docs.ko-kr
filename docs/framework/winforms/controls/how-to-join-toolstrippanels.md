---
title: '방법: ToolStripPanels 조인'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- toolbars [Windows Forms], joining together
- ToolStripPanel control [Windows Forms], joining together
ms.assetid: 4eadda6d-e3b8-4151-aaf2-a8d564fbe6b3
ms.openlocfilehash: 5e1688fb00e6eefa4873284e1ea1ba29536d3227
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/05/2018
ms.locfileid: "43723628"
---
# <a name="how-to-join-toolstrippanels"></a><span data-ttu-id="7d59f-102">방법: ToolStripPanels 조인</span><span class="sxs-lookup"><span data-stu-id="7d59f-102">How to: Join ToolStripPanels</span></span>
<span data-ttu-id="7d59f-103">런타임에 <xref:System.Windows.Forms.ToolStrip> 컨트롤을 <xref:System.Windows.Forms.ToolStripPanel>에 연결하여 MDI(다중 문서 인터페이스) 응용 프로그램의 유연성을 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7d59f-103">You can join <xref:System.Windows.Forms.ToolStrip> controls to a <xref:System.Windows.Forms.ToolStripPanel> at run time, which provides the flexibility of multiple-document interface (MDI) applications.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7d59f-104">예제</span><span class="sxs-lookup"><span data-stu-id="7d59f-104">Example</span></span>  
 <span data-ttu-id="7d59f-105">다음 코드 예제에서는 <xref:System.Windows.Forms.ToolStrip> 컨트롤을 <xref:System.Windows.Forms.ToolStripPanel>에 연결하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="7d59f-105">The following code example demonstrates how to join <xref:System.Windows.Forms.ToolStrip> controls to a <xref:System.Windows.Forms.ToolStripPanel>.</span></span>  
  
 [!code-csharp[System.Windows.Forms.ToolStrip.Misc#11](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/CS/Program.cs#11)]
 [!code-vb[System.Windows.Forms.ToolStrip.Misc#11](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/VB/Program.vb#11)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="7d59f-106">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="7d59f-106">Compiling the Code</span></span>  
 <span data-ttu-id="7d59f-107">이 예제에는 다음 사항이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="7d59f-107">This example requires:</span></span>  
  
-   <span data-ttu-id="7d59f-108">System.Design, System.Drawing 및 System.Windows.Forms 어셈블리에 대한 참조</span><span class="sxs-lookup"><span data-stu-id="7d59f-108">References to the System.Design, System.Drawing, and System.Windows.Forms assemblies.</span></span>  
  
 <span data-ttu-id="7d59f-109">Visual Basic 또는 Visual C#에 대 한 명령줄에서이 예제를 빌드하는 방법에 대 한 내용은 [명령줄에서 빌드](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) 하거나 [csc.exe를 사용한 명령줄 빌드](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="7d59f-109">For information about building this example from the command line for visual Basic or Visual C#, see [Building from the Command Line](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) or [Command-line Building With csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span></span> <span data-ttu-id="7d59f-110">또한 새 프로젝트에 코드를 붙여 넣어 Visual Studio에서이 예제를 빌드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7d59f-110">You can also build this example in Visual Studio by pasting the code into a new project.</span></span>  <span data-ttu-id="7d59f-111">[방법: Visual Studio를 사용하여 전체 Windows Forms 코드 예제 컴파일 및 실행](https://msdn.microsoft.com/library/Bb129228\(v=vs.110\))을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="7d59f-111">Also see [How to: Compile and Run a Complete Windows Forms Code Example Using Visual Studio](https://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7d59f-112">참고 항목</span><span class="sxs-lookup"><span data-stu-id="7d59f-112">See Also</span></span>  
 <xref:System.Windows.Forms.ToolStrip>  
 <xref:System.Windows.Forms.ToolStripPanel>  
 [<span data-ttu-id="7d59f-113">방법: MDI에 ToolStripPanels 사용</span><span class="sxs-lookup"><span data-stu-id="7d59f-113">How to: Use ToolStripPanels for MDI</span></span>](../../../../docs/framework/winforms/controls/how-to-use-toolstrippanels-for-mdi.md)
