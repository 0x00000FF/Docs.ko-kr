---
title: '방법: Windows Forms DataGridView 컨트롤에서 행 조작'
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
- cpp
helpviewer_keywords:
- DataGridView control [Windows Forms], manipulating rows
- data grids [Windows Forms], manipulating rows
- rows [Windows Forms], manipulating on Windows Forms
ms.assetid: 522d8944-e073-4488-9673-923f0a8d7214
caps.latest.revision: 9
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: fcafa6c7a2c8871aba7257cf1555f4d6f111f367
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/26/2018
---
# <a name="how-to-manipulate-rows-in-the-windows-forms-datagridview-control"></a><span data-ttu-id="898f6-102">방법: Windows Forms DataGridView 컨트롤에서 행 조작</span><span class="sxs-lookup"><span data-stu-id="898f6-102">How to: Manipulate Rows in the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="898f6-103">다음 코드 예제에서는 <xref:System.Windows.Forms.DataGridViewRow> 클래스의 속성을 사용하여 <xref:System.Windows.Forms.DataGridView> 행을 조작하는 다양한 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="898f6-103">The following code example shows the various ways to manipulate <xref:System.Windows.Forms.DataGridView> rows using properties of the <xref:System.Windows.Forms.DataGridViewRow> class.</span></span>  
  
## <a name="example"></a><span data-ttu-id="898f6-104">예제</span><span class="sxs-lookup"><span data-stu-id="898f6-104">Example</span></span>  
 [!code-cpp[System.Windows.Forms.DataGridView.ButtonDemos#200](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.ButtonDemos/CPP/DataGridViewRowDemo.cpp#200)]
 [!code-csharp[System.Windows.Forms.DataGridView.ButtonDemos#200](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.ButtonDemos/CS/DataGridViewRowDemo.cs#200)]
 [!code-vb[System.Windows.Forms.DataGridView.ButtonDemos#200](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.ButtonDemos/VB/datagridviewrowdemo.vb#200)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="898f6-105">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="898f6-105">Compiling the Code</span></span>  
 <span data-ttu-id="898f6-106">이 예제에는 다음 사항이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="898f6-106">This example requires:</span></span>  
  
-   <span data-ttu-id="898f6-107">System, System.Drawing 및 System.Windows.Forms 어셈블리에 대한 참조</span><span class="sxs-lookup"><span data-stu-id="898f6-107">References to the System, System.Drawing, and System.Windows.Forms assemblies.</span></span>  
  
 <span data-ttu-id="898f6-108">Visual Basic 또는 Visual C#에 대 한 명령줄에서이 예제를 빌드하는 방법에 대 한 정보를 참조 하십시오. [명령줄에서 빌드](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) 또는 [사용한 명령줄 빌드 csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="898f6-108">For information about building this example from the command line for Visual Basic or Visual C#, see [Building from the Command Line](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) or [Command-line Building With csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span></span> <span data-ttu-id="898f6-109">[!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)] 에서 코드를 새 프로젝트에 붙여넣어 이 예제를 빌드할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="898f6-109">You can also build this example in [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)] by pasting the code into a new project.</span></span>  <span data-ttu-id="898f6-110">[방법: Visual Studio를 사용하여 전체 Windows Forms 코드 예제 컴파일 및 실행](http://msdn.microsoft.com/library/Bb129228\(v=vs.110\))을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="898f6-110">Also see [How to: Compile and Run a Complete Windows Forms Code Example Using Visual Studio](http://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="898f6-111">참고 항목</span><span class="sxs-lookup"><span data-stu-id="898f6-111">See Also</span></span>  
 <xref:System.Windows.Forms.DataGridView>  
 <xref:System.Windows.Forms.DataGridViewBand>  
 <xref:System.Windows.Forms.DataGridViewRow>  
 <xref:System.Windows.Forms.DataGridViewColumn>  
 [<span data-ttu-id="898f6-112">Windows Forms DataGridView 컨트롤에서 셀, 행 및 열 프로그래밍</span><span class="sxs-lookup"><span data-stu-id="898f6-112">Programming with Cells, Rows, and Columns in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/programming-with-cells-rows-and-columns-in-the-datagrid.md)
