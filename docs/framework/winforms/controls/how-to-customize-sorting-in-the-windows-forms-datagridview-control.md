---
title: '방법: Windows Forms DataGridView 컨트롤에서 정렬 사용자 지정'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- sorting [Windows Forms], DataGridView control
- DataGridView control [Windows Forms], sorting
- data grids [Windows Forms], customizing sorting
ms.assetid: 92fb5c14-afab-4cf5-a97e-924fd9cb99f5
ms.openlocfilehash: 34a92af246e1145e8d0d1d6874b2d64d7dee7846
ms.sourcegitcommit: 76a304c79a32aa13889ebcf4b9789a4542b48e3e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/13/2018
ms.locfileid: "45513718"
---
# <a name="how-to-customize-sorting-in-the-windows-forms-datagridview-control"></a><span data-ttu-id="1a8f5-102">방법: Windows Forms DataGridView 컨트롤에서 정렬 사용자 지정</span><span class="sxs-lookup"><span data-stu-id="1a8f5-102">How to: Customize Sorting in the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="1a8f5-103"><xref:System.Windows.Forms.DataGridView> 컨트롤은 자동 정렬을 제공하지만 필요에 따라 정렬 작업을 사용자 지정해야 할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1a8f5-103">The <xref:System.Windows.Forms.DataGridView> control provides automatic sorting but, depending on your needs, you might need to customize sort operations.</span></span> <span data-ttu-id="1a8f5-104">예를 들어 프로그래밍 방식의 정렬을 사용하여 대체 UI(사용자 인터페이스)를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1a8f5-104">For example, you can use programmatic sorting to create an alternate user interface (UI).</span></span> <span data-ttu-id="1a8f5-105">또는 다중 열 정렬과 같은 정렬 유연성 향상을 위해 <xref:System.Windows.Forms.DataGridView.SortCompare> 이벤트를 처리하거나 <xref:System.Windows.Forms.DataGridView.Sort%2A> 메서드의 `Sort(IComparer)` 오버로드를 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1a8f5-105">Alternatively, you can handle the <xref:System.Windows.Forms.DataGridView.SortCompare> event or call the `Sort(IComparer)` overload of the <xref:System.Windows.Forms.DataGridView.Sort%2A> method for greater sorting flexibility, such as sorting multiple columns.</span></span>  
  
 <span data-ttu-id="1a8f5-106">다음 코드 예제에서는 사용자 지정 정렬에 대한 이 세 가지 접근 방식을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="1a8f5-106">The following code examples demonstrate these three approaches to custom sorting.</span></span> <span data-ttu-id="1a8f5-107">자세한 내용은 [Windows Forms DataGridView 컨트롤의 열 정렬 모드](../../../../docs/framework/winforms/controls/column-sort-modes-in-the-windows-forms-datagridview-control.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="1a8f5-107">For more information, see [Column Sort Modes in the Windows Forms DataGridView Control](../../../../docs/framework/winforms/controls/column-sort-modes-in-the-windows-forms-datagridview-control.md).</span></span>  
  
## <a name="programmatic-sorting"></a><span data-ttu-id="1a8f5-108">프로그래밍 방식 정렬</span><span class="sxs-lookup"><span data-stu-id="1a8f5-108">Programmatic Sorting</span></span>  
 <span data-ttu-id="1a8f5-109">다음 코드 예제에서는 <xref:System.Windows.Forms.DataGridView.SortOrder%2A> 및 <xref:System.Windows.Forms.DataGridView.SortedColumn%2A> 속성을 사용하여 정렬 방향을 결정하고 <xref:System.Windows.Forms.DataGridViewColumnHeaderCell.SortGlyphDirection%2A> 속성을 사용하여 정렬 문자를 수동으로 설정하는 프로그래밍 방식 정렬을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="1a8f5-109">The following code example demonstrates a programmatic sort using the <xref:System.Windows.Forms.DataGridView.SortOrder%2A> and <xref:System.Windows.Forms.DataGridView.SortedColumn%2A> properties to determine the direction of the sort, and the <xref:System.Windows.Forms.DataGridViewColumnHeaderCell.SortGlyphDirection%2A> property to manually set the sort glyph.</span></span> <span data-ttu-id="1a8f5-110"><xref:System.Windows.Forms.DataGridView.Sort%2A> 메서드의 `Sort(DataGridViewColumn,ListSortDirection)` 오버로드는 단일 열의 데이터만 정렬하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="1a8f5-110">The `Sort(DataGridViewColumn,ListSortDirection)` overload of the <xref:System.Windows.Forms.DataGridView.Sort%2A> method is used to sort data only in a single column.</span></span>  
  
 [!code-csharp[System.Windows.Forms.DataGridViewProgrammaticSort#00](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewProgrammaticSort/CS/form1.cs#00)]
 [!code-vb[System.Windows.Forms.DataGridViewProgrammaticSort#00](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewProgrammaticSort/VB/form1.vb#00)]  
  
## <a name="custom-sorting-using-the-sortcompare-event"></a><span data-ttu-id="1a8f5-111">SortCompare 이벤트를 사용한 사용자 지정 정렬</span><span class="sxs-lookup"><span data-stu-id="1a8f5-111">Custom Sorting Using the SortCompare Event</span></span>  
 <span data-ttu-id="1a8f5-112">다음 코드 예제에서는 <xref:System.Windows.Forms.DataGridView.SortCompare> 이벤트 처리기를 사용한 사용자 지정 정렬을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="1a8f5-112">The following code example demonstrates custom sorting using a <xref:System.Windows.Forms.DataGridView.SortCompare> event handler.</span></span> <span data-ttu-id="1a8f5-113">선택한 <xref:System.Windows.Forms.DataGridViewColumn>이 정렬되고, 열에 중복 값이 있는 경우 ID 열을 사용하여 최종 순서를 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="1a8f5-113">The selected <xref:System.Windows.Forms.DataGridViewColumn> is sorted and, if there are duplicate values in the column, the ID column is used to determine the final order.</span></span>  
  
 [!code-csharp[System.Windows.Forms.DataGridView.SortCompare#00](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.SortCompare/CS/form1.cs#00)]
 [!code-vb[System.Windows.Forms.DataGridView.SortCompare#00](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.SortCompare/VB/form1.vb#00)]  
  
## <a name="custom-sorting-using-the-icomparer-interface"></a><span data-ttu-id="1a8f5-114">IComparer 인터페이스를 사용한 사용자 지정 정렬</span><span class="sxs-lookup"><span data-stu-id="1a8f5-114">Custom Sorting Using the IComparer Interface</span></span>  
 <span data-ttu-id="1a8f5-115">다음 코드 예제에서는 <xref:System.Collections.IComparer> 인터페이스 구현을 받아서 다중 열 정렬을 수행하는 <xref:System.Windows.Forms.DataGridView.Sort%2A> 메서드의 `Sort(IComparer)` 오버로드를 사용한 사용자 지정 정렬을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="1a8f5-115">The following code example demonstrates custom sorting using the `Sort(IComparer)` overload of the <xref:System.Windows.Forms.DataGridView.Sort%2A> method, which takes an implementation of the <xref:System.Collections.IComparer> interface to perform a multiple-column sort.</span></span>  
  
 [!code-csharp[System.Windows.Forms.DataGridViewIComparerSort#00](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewIComparerSort/CS/form1.cs#00)]
 [!code-vb[System.Windows.Forms.DataGridViewIComparerSort#00](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewIComparerSort/VB/form1.vb#00)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="1a8f5-116">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="1a8f5-116">Compiling the Code</span></span>  
 <span data-ttu-id="1a8f5-117">이러한 예제에는 다음이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="1a8f5-117">These examples require:</span></span>  
  
-   <span data-ttu-id="1a8f5-118">System, System.Drawing 및 System.Windows.Forms 어셈블리에 대한 참조</span><span class="sxs-lookup"><span data-stu-id="1a8f5-118">References to the System, System.Drawing, and System.Windows.Forms assemblies.</span></span>  
  
 <span data-ttu-id="1a8f5-119">Visual Basic 또는 Visual C#에 대 한 명령줄에서 이러한 예제를 빌드하는 방법에 대 한 내용은 [명령줄에서 빌드](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) 하거나 [csc.exe를 사용한 명령줄 빌드](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="1a8f5-119">For information about building these examples from the command line for Visual Basic or Visual C#, see [Building from the Command Line](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) or [Command-line Building With csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span></span> <span data-ttu-id="1a8f5-120">또한 새 프로젝트에 코드를 붙여 넣어 Visual Studio에서이 예제를 빌드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1a8f5-120">You can also build this example in Visual Studio by pasting the code into a new project.</span></span>  <span data-ttu-id="1a8f5-121">[방법: Visual Studio를 사용하여 전체 Windows Forms 코드 예제 컴파일 및 실행](https://msdn.microsoft.com/library/Bb129228\(v=vs.110\))을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="1a8f5-121">Also see [How to: Compile and Run a Complete Windows Forms Code Example Using Visual Studio](https://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1a8f5-122">참고 항목</span><span class="sxs-lookup"><span data-stu-id="1a8f5-122">See Also</span></span>  
 <xref:System.Windows.Forms.DataGridView>  
 [<span data-ttu-id="1a8f5-123">Windows Forms DataGridView 컨트롤의 데이터 정렬</span><span class="sxs-lookup"><span data-stu-id="1a8f5-123">Sorting Data in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/sorting-data-in-the-windows-forms-datagridview-control.md)  
 [<span data-ttu-id="1a8f5-124">Windows Forms DataGridView 컨트롤의 열 정렬 모드</span><span class="sxs-lookup"><span data-stu-id="1a8f5-124">Column Sort Modes in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/column-sort-modes-in-the-windows-forms-datagridview-control.md)  
 [<span data-ttu-id="1a8f5-125">방법: Windows Forms DataGridView 컨트롤의 열 정렬 모드 설정</span><span class="sxs-lookup"><span data-stu-id="1a8f5-125">How to: Set the Sort Modes for Columns in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/set-the-sort-modes-for-columns-wf-datagridview-control.md)
