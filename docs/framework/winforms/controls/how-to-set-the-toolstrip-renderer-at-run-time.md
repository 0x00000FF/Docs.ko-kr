---
title: "방법: 런타임에 ToolStrip 렌더러 설정"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- toolbars [Windows Forms]
- ToolStripManager class [Windows Forms]
- ToolStripProfessionalRenderer class [Windows Forms]
- ToolStrip control [Windows Forms]
- MenuStrip control [Windows Forms]
ms.assetid: 525e2347-0804-49aa-b9a3-9b2cabbf1c35
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 4a7cde7e4ee81f6fdcb14e87d720b8578fd40c20
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-set-the-toolstrip-renderer-at-run-time"></a><span data-ttu-id="7efe3-102">방법: 런타임에 ToolStrip 렌더러 설정</span><span class="sxs-lookup"><span data-stu-id="7efe3-102">How to: Set the ToolStrip Renderer at Run Time</span></span>
<span data-ttu-id="7efe3-103">사용자 지정 `ProfessionalColorTable` 클래스를 만들어 <xref:System.Windows.Forms.ToolStrip> 컨트롤의 모양을 사용자 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7efe3-103">You can customize the appearance of your <xref:System.Windows.Forms.ToolStrip> control by creating a custom `ProfessionalColorTable` class.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7efe3-104">예제</span><span class="sxs-lookup"><span data-stu-id="7efe3-104">Example</span></span>  
 <span data-ttu-id="7efe3-105">다음 코드 예제에서는 사용자 지정 `ProfessionalColorTable` 클래스를 만드는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="7efe3-105">The following code example demonstrates how to create a custom `ProfessionalColorTable` class.</span></span> <span data-ttu-id="7efe3-106">이 클래스는 <xref:System.Windows.Forms.MenuStrip> 및 <xref:System.Windows.Forms.ToolStrip> 컨트롤에 대한 그라데이션을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="7efe3-106">This class defines gradients for a <xref:System.Windows.Forms.MenuStrip> and a <xref:System.Windows.Forms.ToolStrip> control.</span></span>  
  
 <span data-ttu-id="7efe3-107">이 코드 예제를 사용하려면 응용 프로그램을 컴파일 및 실행한 다음 **색 변경**을 클릭하여 사용자 지정 `ProfessionalColorTable` 클래스에서 정의된 그라데이션을 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="7efe3-107">To use this code example, compile and run the application, and then click **Change Colors** to apply the gradients defined in the custom `ProfessionalColorTable` class.</span></span>  
  
 [!code-csharp[System.Windows.Forms.ToolStrip.Misc#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/CS/Program.cs#1)]
 [!code-vb[System.Windows.Forms.ToolStrip.Misc#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/VB/Program.vb#1)]  
[!code-csharp[System.Windows.Forms.ToolStrip.Misc#20](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/CS/Program.cs#20)]
[!code-vb[System.Windows.Forms.ToolStrip.Misc#20](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/VB/Program.vb#20)]  
  
## <a name="defining-a-custom-professionalcolortable-class"></a><span data-ttu-id="7efe3-108">사용자 지정 ProfessionalColorTable 클래스 정의</span><span class="sxs-lookup"><span data-stu-id="7efe3-108">Defining a Custom ProfessionalColorTable class</span></span>  
 <span data-ttu-id="7efe3-109">사용자 지정 그라데이션은 `CustomProfessionalColors` 클래스에서 정의됩니다.</span><span class="sxs-lookup"><span data-stu-id="7efe3-109">The custom gradients are defined in the `CustomProfessionalColors` class.</span></span>  
  
 [!code-csharp[System.Windows.Forms.ToolStrip.Misc#30](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/CS/Program.cs#30)]
 [!code-vb[System.Windows.Forms.ToolStrip.Misc#30](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/VB/Program.vb#30)]  
  
## <a name="assigning-a-custom-renderer"></a><span data-ttu-id="7efe3-110">사용자 지정 렌더러 할당</span><span class="sxs-lookup"><span data-stu-id="7efe3-110">Assigning a Custom Renderer</span></span>  
 <span data-ttu-id="7efe3-111">`CustomProfessionalColors` 클래스를 사용하여 새 `ToolStripProfessionalRenderer`를 만들고 <xref:System.Windows.Forms.ToolStripManager.Renderer%2A?displayProperty=nameWithType> 속성에 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="7efe3-111">Create a new `ToolStripProfessionalRenderer` with a `CustomProfessionalColors` class, and assign it to the <xref:System.Windows.Forms.ToolStripManager.Renderer%2A?displayProperty=nameWithType> property.</span></span>  
  
 [!code-csharp[System.Windows.Forms.ToolStrip.Misc#22](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/CS/Program.cs#22)]
 [!code-vb[System.Windows.Forms.ToolStrip.Misc#22](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/VB/Program.vb#22)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="7efe3-112">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="7efe3-112">Compiling the Code</span></span>  
 <span data-ttu-id="7efe3-113">이 예제에는 다음 사항이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="7efe3-113">This example requires:</span></span>  
  
-   <span data-ttu-id="7efe3-114">System.Design, System.Drawing 및 System.Windows.Forms 어셈블리에 대한 참조</span><span class="sxs-lookup"><span data-stu-id="7efe3-114">References to the System.Design, System.Drawing, and System.Windows.Forms assemblies.</span></span>  
  
 <span data-ttu-id="7efe3-115">[!INCLUDE[vbprvb](../../../../includes/vbprvb-md.md)] 또는 [!INCLUDE[csprcs](../../../../includes/csprcs-md.md)]의 명령줄에서 이 예제를 빌드하는 방법에 대한 자세한 내용은 [명령줄에서 빌드](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) 또는 [csc.exe를 사용한 명령줄 빌드](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="7efe3-115">For information about building this example from the command line for [!INCLUDE[vbprvb](../../../../includes/vbprvb-md.md)] or [!INCLUDE[csprcs](../../../../includes/csprcs-md.md)], see [Building from the Command Line](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) or [Command-line Building With csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span></span> <span data-ttu-id="7efe3-116">[!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)]에서 코드를 새 프로젝트에 붙여넣어 이 예제를 빌드할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7efe3-116">You can also build this example in [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)] by pasting the code into a new project.</span></span>  <span data-ttu-id="7efe3-117">[방법: Visual Studio를 사용하여 전체 Windows Forms 코드 예제 컴파일 및 실행](http://msdn.microsoft.com/library/Bb129228\(v=vs.110\))을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="7efe3-117">Also see [How to: Compile and Run a Complete Windows Forms Code Example Using Visual Studio](http://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7efe3-118">참고 항목</span><span class="sxs-lookup"><span data-stu-id="7efe3-118">See Also</span></span>  
 <xref:System.Windows.Forms.ToolStripManager>  
 <xref:System.Windows.Forms.ProfessionalColorTable>  
 <xref:System.Windows.Forms.MenuStrip>  
 <xref:System.Windows.Forms.ToolStrip>  
 <xref:System.Windows.Forms.ToolStripProfessionalRenderer>  
 [<span data-ttu-id="7efe3-119">ToolStrip 컨트롤</span><span class="sxs-lookup"><span data-stu-id="7efe3-119">ToolStrip Control</span></span>](../../../../docs/framework/winforms/controls/toolstrip-control-windows-forms.md)
