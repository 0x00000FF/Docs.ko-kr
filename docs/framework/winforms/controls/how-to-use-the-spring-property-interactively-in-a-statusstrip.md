---
title: '방법: StatusStrip에서 대화형으로 Spring 속성 사용'
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
helpviewer_keywords:
- StatusStrip control [Windows Forms]
- ToolStrip control [Windows Forms]
- status bars [Windows Forms], examples
- Spring property [Windows Forms]
ms.assetid: 18bde842-a93c-48dd-9db3-15738a1775ce
caps.latest.revision: 9
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 1dfe3f3f7de15573c9d41fb6dc3e447ea6785e41
ms.sourcegitcommit: 2042de78fcdceebb6b8ac4b7a292b93e8782cbf5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/27/2018
---
# <a name="how-to-use-the-spring-property-interactively-in-a-statusstrip"></a><span data-ttu-id="a7645-102">방법: StatusStrip에서 대화형으로 Spring 속성 사용</span><span class="sxs-lookup"><span data-stu-id="a7645-102">How to: Use the Spring Property Interactively in a StatusStrip</span></span>
<span data-ttu-id="a7645-103"><xref:System.Windows.Forms.ToolStripStatusLabel.Spring%2A> 속성을 사용하여 <xref:System.Windows.Forms.ToolStripStatusLabel> 컨트롤을 <xref:System.Windows.Forms.StatusStrip> 컨트롤에 배치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a7645-103">You can use the <xref:System.Windows.Forms.ToolStripStatusLabel.Spring%2A> property to position a <xref:System.Windows.Forms.ToolStripStatusLabel> control in a <xref:System.Windows.Forms.StatusStrip> control.</span></span> <span data-ttu-id="a7645-104"><xref:System.Windows.Forms.ToolStripStatusLabel.Spring%2A> 속성은 <xref:System.Windows.Forms.ToolStripStatusLabel> 컨트롤이 <xref:System.Windows.Forms.StatusStrip> 컨트롤에서 사용 가능한 공간을 자동으로 채울지 여부를 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="a7645-104">The <xref:System.Windows.Forms.ToolStripStatusLabel.Spring%2A> property determines whether the <xref:System.Windows.Forms.ToolStripStatusLabel> control automatically fills the available space on the <xref:System.Windows.Forms.StatusStrip> control.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a7645-105">예제</span><span class="sxs-lookup"><span data-stu-id="a7645-105">Example</span></span>  
 <span data-ttu-id="a7645-106">다음 코드 예제에서는 <xref:System.Windows.Forms.ToolStripStatusLabel.Spring%2A> 속성을 사용하여 <xref:System.Windows.Forms.ToolStripStatusLabel> 컨트롤을 <xref:System.Windows.Forms.StatusStrip> 컨트롤에 배치하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="a7645-106">The following code example demonstrates how to use the <xref:System.Windows.Forms.ToolStripStatusLabel.Spring%2A> property to position a <xref:System.Windows.Forms.ToolStripStatusLabel> control in a <xref:System.Windows.Forms.StatusStrip> control.</span></span> <span data-ttu-id="a7645-107"><xref:System.Windows.Forms.ToolStripItem.Click> 이벤트 처리기는 XOR(배타적 OR) 연산을 수행하여 <xref:System.Windows.Forms.ToolStripStatusLabel.Spring%2A> 속성의 값을 전환합니다.</span><span class="sxs-lookup"><span data-stu-id="a7645-107">The <xref:System.Windows.Forms.ToolStripItem.Click> event handler performs an exclusive-or (XOR) operation to switch the value of the <xref:System.Windows.Forms.ToolStripStatusLabel.Spring%2A> property.</span></span>  
  
 <span data-ttu-id="a7645-108">이 코드 예제를 사용 하려면 컴파일하고 응용 프로그램을 실행 한 다음 클릭 **Middle (Spring)** 에 <xref:System.Windows.Forms.StatusStrip> 컨트롤의 값을 전환는 <xref:System.Windows.Forms.ToolStripStatusLabel.Spring%2A> 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="a7645-108">To use this code example, compile and run the application, and then click **Middle (Spring)** on the <xref:System.Windows.Forms.StatusStrip> control to switch the value of the <xref:System.Windows.Forms.ToolStripStatusLabel.Spring%2A> property.</span></span>  
  
 [!code-csharp[System.Windows.Forms.ToolStrip.Misc#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/CS/Program.cs#1)]
 [!code-vb[System.Windows.Forms.ToolStrip.Misc#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/VB/Program.vb#1)]  
[!code-csharp[System.Windows.Forms.ToolStrip.Misc#50](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/CS/Program.cs#50)]
[!code-vb[System.Windows.Forms.ToolStrip.Misc#50](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/VB/Program.vb#50)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="a7645-109">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="a7645-109">Compiling the Code</span></span>  
 <span data-ttu-id="a7645-110">이 예제에는 다음 사항이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="a7645-110">This example requires:</span></span>  
  
-   <span data-ttu-id="a7645-111">System.Design, System.Drawing 및 System.Windows.Forms 어셈블리에 대한 참조</span><span class="sxs-lookup"><span data-stu-id="a7645-111">References to the System.Design, System.Drawing, and System.Windows.Forms assemblies.</span></span>  
  
 <span data-ttu-id="a7645-112">Visual Basic 또는 Visual C#에 대 한 명령줄에서이 예제를 빌드하는 방법에 대 한 정보를 참조 하십시오. [명령줄에서 빌드](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) 또는 [사용한 명령줄 빌드 csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="a7645-112">For information about building this example from the command line for visual Basic or Visual C#, see [Building from the Command Line](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) or [Command-line Building With csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span></span> <span data-ttu-id="a7645-113">새 프로젝트에 코드를 붙여 넣어 Visual Studio에서이 예제를 빌드할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a7645-113">You can also build this example in Visual Studio by pasting the code into a new project.</span></span>  <span data-ttu-id="a7645-114">[방법: Visual Studio를 사용하여 전체 Windows Forms 코드 예제 컴파일 및 실행](http://msdn.microsoft.com/library/Bb129228\(v=vs.110\))을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="a7645-114">Also see [How to: Compile and Run a Complete Windows Forms Code Example Using Visual Studio](http://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a7645-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a7645-115">See Also</span></span>  
 <xref:System.Windows.Forms.ToolStripStatusLabel>  
 <xref:System.Windows.Forms.StatusStrip>  
 <xref:System.Windows.Forms.ToolStrip>  
 <xref:System.Windows.Forms.ToolStripItem>  
 <xref:System.Windows.Forms.ToolStripMenuItem>  
 [<span data-ttu-id="a7645-116">ToolStrip 컨트롤</span><span class="sxs-lookup"><span data-stu-id="a7645-116">ToolStrip Control</span></span>](../../../../docs/framework/winforms/controls/toolstrip-control-windows-forms.md)
