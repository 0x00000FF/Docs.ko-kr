---
title: "방법: Windows Forms DataGridView 컨트롤에서 열 조작"
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
- cpp
helpviewer_keywords:
- DataGridView control [Windows Forms], manipulatiing columns
- columns [Windows Forms], manipulating
- data grids [Windows Forms], manipulating columns
ms.assetid: d8cfe6b3-bbab-4182-bec2-0517d9f1eaf6
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 213cf8df3694ec3020057de65006ff6351961cc0
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-manipulate-columns-in-the-windows-forms-datagridview-control"></a><span data-ttu-id="c6bf3-102">방법: Windows Forms DataGridView 컨트롤에서 열 조작</span><span class="sxs-lookup"><span data-stu-id="c6bf3-102">How to: Manipulate Columns in the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="c6bf3-103">다음 코드 예제에서는 <xref:System.Windows.Forms.DataGridViewColumn> 클래스의 속성을 사용하여 <xref:System.Windows.Forms.DataGridView> 열을 조작하는 다양한 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="c6bf3-103">The following code example shows the various ways to manipulate <xref:System.Windows.Forms.DataGridView> columns using properties of the <xref:System.Windows.Forms.DataGridViewColumn> class.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c6bf3-104">예</span><span class="sxs-lookup"><span data-stu-id="c6bf3-104">Example</span></span>  
 [!code-cpp[System.Windows.Forms.DataGridView.ButtonDemos#100](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.ButtonDemos/CPP/DataGridViewColumnDemo.cpp#100)]
 [!code-csharp[System.Windows.Forms.DataGridView.ButtonDemos#100](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.ButtonDemos/CS/DataGridViewColumnDemo.cs#100)]
 [!code-vb[System.Windows.Forms.DataGridView.ButtonDemos#100](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.ButtonDemos/VB/datagridviewcolumndemo.vb#100)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="c6bf3-105">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="c6bf3-105">Compiling the Code</span></span>  
 <span data-ttu-id="c6bf3-106">이 예제에는 다음 사항이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="c6bf3-106">This example requires:</span></span>  
  
-   <span data-ttu-id="c6bf3-107">System, System.Drawing 및 System.Windows.Forms 어셈블리에 대한 참조</span><span class="sxs-lookup"><span data-stu-id="c6bf3-107">References to the System, System.Drawing, and System.Windows.Forms assemblies.</span></span>  
  
 <span data-ttu-id="c6bf3-108">[!INCLUDE[vbprvb](../../../../includes/vbprvb-md.md)] 또는 [!INCLUDE[csprcs](../../../../includes/csprcs-md.md)]의 명령줄에서 이 예제를 빌드하는 방법에 대한 자세한 내용은 [명령줄에서 빌드](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) 또는 [csc.exe를 사용한 명령줄 빌드](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c6bf3-108">For information about building this example from the command line for [!INCLUDE[vbprvb](../../../../includes/vbprvb-md.md)] or [!INCLUDE[csprcs](../../../../includes/csprcs-md.md)], see [Building from the Command Line](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) or [Command-line Building With csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span></span> <span data-ttu-id="c6bf3-109">[!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)]에서 코드를 새 프로젝트에 붙여넣어 이 예제를 빌드할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c6bf3-109">You can also build this example in [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)] by pasting the code into a new project.</span></span>  <span data-ttu-id="c6bf3-110">[방법: Visual Studio를 사용하여 전체 Windows Forms 코드 예제 컴파일 및 실행](http://msdn.microsoft.com/library/Bb129228\(v=vs.110\))을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c6bf3-110">Also see [How to: Compile and Run a Complete Windows Forms Code Example Using Visual Studio](http://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c6bf3-111">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c6bf3-111">See Also</span></span>  
 <xref:System.Windows.Forms.DataGridView>  
 <xref:System.Windows.Forms.DataGridViewBand>  
 <xref:System.Windows.Forms.DataGridViewRow>  
 <xref:System.Windows.Forms.DataGridViewColumn>  
 [<span data-ttu-id="c6bf3-112">Windows Forms DataGridView 컨트롤에서 셀, 행 및 열 프로그래밍</span><span class="sxs-lookup"><span data-stu-id="c6bf3-112">Programming with Cells, Rows, and Columns in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/programming-with-cells-rows-and-columns-in-the-datagrid.md)
