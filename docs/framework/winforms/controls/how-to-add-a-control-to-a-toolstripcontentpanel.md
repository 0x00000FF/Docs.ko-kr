---
title: '방법: ToolStripContentPanel에 컨트롤 추가'
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
- ToolStripContentPanel [Windows Forms], adding controls
ms.assetid: fa410960-bf1a-42fc-80e8-f2e27fb3dbb8
caps.latest.revision: 10
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 5ab8e4e233457a7059d933e5109950a8928cd897
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/26/2018
---
# <a name="how-to-add-a-control-to-a-toolstripcontentpanel"></a><span data-ttu-id="54f45-102">방법: ToolStripContentPanel에 컨트롤 추가</span><span class="sxs-lookup"><span data-stu-id="54f45-102">How to: Add a Control to a ToolStripContentPanel</span></span>
<span data-ttu-id="54f45-103">컨트롤 하나 이상을 프로그래밍 방식으로 <xref:System.Windows.Forms.ToolStripContentPanel>에 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="54f45-103">You can programmatically add one or more controls to a <xref:System.Windows.Forms.ToolStripContentPanel>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="54f45-104">예제</span><span class="sxs-lookup"><span data-stu-id="54f45-104">Example</span></span>  
 <span data-ttu-id="54f45-105">다음 코드 예제에서는 <xref:System.Windows.Forms.RichTextBox>를 <xref:System.Windows.Forms.ToolStripContentPanel>에 추가하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="54f45-105">The following code example demonstrates how to add a <xref:System.Windows.Forms.RichTextBox> to a <xref:System.Windows.Forms.ToolStripContentPanel>.</span></span>  
  
 [!code-csharp[System.Windows.Forms.ToolStripContainer#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStripContainer/CS/Form1.cs#1)]
 [!code-vb[System.Windows.Forms.ToolStripContainer#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStripContainer/VB/Form1.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="54f45-106">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="54f45-106">Compiling the Code</span></span>  
 <span data-ttu-id="54f45-107">이 코드 예제에는 다음이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="54f45-107">This code example requires:</span></span>  
  
-   <span data-ttu-id="54f45-108">System, System.Data 및 System.Windows.Forms 어셈블리에 대한 참조</span><span class="sxs-lookup"><span data-stu-id="54f45-108">References to the System, System.Data and System.Windows.Forms assemblies.</span></span>  
  
 <span data-ttu-id="54f45-109">Visual Basic 또는 Visual C#에 대 한 명령줄에서이 예제를 빌드하는 방법에 대 한 정보를 참조 하십시오. [명령줄에서 빌드](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) 또는 [사용한 명령줄 빌드 csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="54f45-109">For information about building this example from the command line for Visual Basic or Visual C#, see [Building from the Command Line](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) or [Command-line Building With csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span></span> <span data-ttu-id="54f45-110">[!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)] 에서 코드를 새 프로젝트에 붙여넣어 이 예제를 빌드할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="54f45-110">You can also build this example in [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)] by pasting the code into a new project.</span></span>  <span data-ttu-id="54f45-111">또한 [방법: Visual Studio를 사용하여 전체 Windows Forms 코드 예제 컴파일 및 실행](http://msdn.microsoft.com/library/Bb129228\(v=vs.110\)) 또는 [ToolStripContainer 태스크 대화 상자](http://msdn.microsoft.com/library/ms233647\(v=vs.110\))를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="54f45-111">See also [How to: Compile and Run a Complete Windows Forms Code Example Using Visual Studio](http://msdn.microsoft.com/library/Bb129228\(v=vs.110\)) or [ToolStripContainer Tasks Dialog Box](http://msdn.microsoft.com/library/ms233647\(v=vs.110\)).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="54f45-112">참고 항목</span><span class="sxs-lookup"><span data-stu-id="54f45-112">See Also</span></span>  
 <xref:System.Windows.Forms.ToolStripContentPanel>  
 <xref:System.Windows.Forms.ToolStripContainer>  
 [<span data-ttu-id="54f45-113">ToolStripContainer 컨트롤</span><span class="sxs-lookup"><span data-stu-id="54f45-113">ToolStripContainer Control</span></span>](../../../../docs/framework/winforms/controls/toolstripcontainer-control.md)  
 [<span data-ttu-id="54f45-114">ToolStrip 컨트롤</span><span class="sxs-lookup"><span data-stu-id="54f45-114">ToolStrip Control</span></span>](../../../../docs/framework/winforms/controls/toolstrip-control-windows-forms.md)
