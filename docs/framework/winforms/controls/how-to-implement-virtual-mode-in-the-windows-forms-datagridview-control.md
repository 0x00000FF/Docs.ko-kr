---
title: '방법: Windows Forms DataGridView 컨트롤에서 가상 모드 구현'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- data [Windows Forms], managing large data sets
- DataGridView control [Windows Forms], virtual mode
- virtual mode
- DataGridView control [Windows Forms], large data sets
ms.assetid: 98236267-f08e-4918-bcf9-77acf050a3ca
ms.openlocfilehash: d5b34f5c9d9e6db9c3fd06f2c09f62c196c96d0a
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59146247"
---
# <a name="how-to-implement-virtual-mode-in-the-windows-forms-datagridview-control"></a><span data-ttu-id="88c2c-102">방법: Windows Forms DataGridView 컨트롤에서 가상 모드 구현</span><span class="sxs-lookup"><span data-stu-id="88c2c-102">How to: Implement Virtual Mode in the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="88c2c-103">다음 코드 예제에서는 <xref:System.Windows.Forms.DataGridView.VirtualMode%2A> 속성이 `true`로 설정된 <xref:System.Windows.Forms.DataGridView> 컨트롤을 사용하여 큰 데이터 집합을 관리하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="88c2c-103">The following code example demonstrates how to manage large sets of data using a <xref:System.Windows.Forms.DataGridView> control with its <xref:System.Windows.Forms.DataGridView.VirtualMode%2A> property set to `true`.</span></span>  
  
 <span data-ttu-id="88c2c-104">에 대 한 전체 설명은이 코드 예제를 참조 하세요. [연습: Forms DataGridView 컨트롤의 Windows에서 가상 모드 구현](implementing-virtual-mode-wf-datagridview-control.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="88c2c-104">For a complete explanation of this code example, see [Walkthrough: Implementing Virtual Mode in the Windows Forms DataGridView Control](implementing-virtual-mode-wf-datagridview-control.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="88c2c-105">예제</span><span class="sxs-lookup"><span data-stu-id="88c2c-105">Example</span></span>  
 [!code-cpp[System.Windows.Forms.DataGridView.VirtualMode#000](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CPP/virtualmode.cpp#000)]
 [!code-csharp[System.Windows.Forms.DataGridView.VirtualMode#000](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CS/virtualmode.cs#000)]
 [!code-vb[System.Windows.Forms.DataGridView.VirtualMode#000](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/VB/virtualmode.vb#000)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="88c2c-106">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="88c2c-106">Compiling the Code</span></span>  
 <span data-ttu-id="88c2c-107">이 예제에는 다음 사항이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="88c2c-107">This example requires:</span></span>  
  
-   <span data-ttu-id="88c2c-108">System 및 System.Windows.Forms 어셈블리에 대한 참조</span><span class="sxs-lookup"><span data-stu-id="88c2c-108">References to the System and System.Windows.Forms assemblies.</span></span>  
  
 <span data-ttu-id="88c2c-109">Visual Basic 또는 Visual C#에 대 한 명령줄에서이 예제를 빌드하는 방법에 대 한 내용은 [명령줄에서 빌드](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md) 하거나 [csc.exe를 사용한 명령줄 빌드](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="88c2c-109">For information about building this example from the command line for Visual Basic or Visual C#, see [Building from the Command Line](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md) or [Command-line Building With csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span></span> <span data-ttu-id="88c2c-110">또한 새 프로젝트에 코드를 붙여 넣어 Visual Studio에서이 예제를 빌드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="88c2c-110">You can also build this example in Visual Studio by pasting the code into a new project.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="88c2c-111">참고자료</span><span class="sxs-lookup"><span data-stu-id="88c2c-111">See also</span></span>

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridView.VirtualMode%2A>
- <xref:System.Windows.Forms.DataGridView.CellValueNeeded>
- <xref:System.Windows.Forms.DataGridView.CellValuePushed>
- <xref:System.Windows.Forms.DataGridView.NewRowNeeded>
- <xref:System.Windows.Forms.DataGridView.RowValidated>
- <xref:System.Windows.Forms.DataGridView.RowDirtyStateNeeded>
- <xref:System.Windows.Forms.DataGridView.CancelRowEdit>
- <xref:System.Windows.Forms.DataGridView.UserDeletingRow>
- [<span data-ttu-id="88c2c-112">연습: Windows Forms DataGridView 컨트롤에서 가상 모드 구현</span><span class="sxs-lookup"><span data-stu-id="88c2c-112">Walkthrough: Implementing Virtual Mode in the Windows Forms DataGridView Control</span></span>](implementing-virtual-mode-wf-datagridview-control.md)
- [<span data-ttu-id="88c2c-113">Windows Forms DataGridView 컨트롤의 성능 조정</span><span class="sxs-lookup"><span data-stu-id="88c2c-113">Performance Tuning in the Windows Forms DataGridView Control</span></span>](performance-tuning-in-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="88c2c-114">Windows Forms DataGridView 컨트롤의 가상 모드</span><span class="sxs-lookup"><span data-stu-id="88c2c-114">Virtual Mode in the Windows Forms DataGridView Control</span></span>](virtual-mode-in-the-windows-forms-datagridview-control.md)
