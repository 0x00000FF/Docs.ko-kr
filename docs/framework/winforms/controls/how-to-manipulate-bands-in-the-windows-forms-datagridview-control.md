---
title: '방법: Windows Forms DataGridView 컨트롤에서 밴드 조작'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- data grids [Windows Forms], manipulating bands
- bands [Windows Forms], manipulating in Windows Forms
- DataGridView control [Windows Forms], manipulating bands
ms.assetid: 1ea3470e-480f-4edc-bcbd-51373eca3856
ms.openlocfilehash: 5e62f5d31b9d24469455ab31f9771ebc81f74967
ms.sourcegitcommit: c7a7e1468bf0fa7f7065de951d60dfc8d5ba89f5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/14/2019
ms.locfileid: "65592348"
---
# <a name="how-to-manipulate-bands-in-the-windows-forms-datagridview-control"></a><span data-ttu-id="69f2d-102">방법: Windows Forms DataGridView 컨트롤에서 밴드 조작</span><span class="sxs-lookup"><span data-stu-id="69f2d-102">How to: Manipulate Bands in the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="69f2d-103">다음 코드 예제에서는 <xref:System.Windows.Forms.DataGridViewRow> 및 <xref:System.Windows.Forms.DataGridViewColumn> 클래스가 파생되는 <xref:System.Windows.Forms.DataGridViewBand> 클래스의 속성을 사용하여 <xref:System.Windows.Forms.DataGridView> 행과 열을 조작하는 다양한 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="69f2d-103">The following code example shows various ways to manipulate <xref:System.Windows.Forms.DataGridView> rows and columns using properties of the <xref:System.Windows.Forms.DataGridViewBand> class from which the <xref:System.Windows.Forms.DataGridViewRow> and <xref:System.Windows.Forms.DataGridViewColumn> classes derive.</span></span>  
  
## <a name="example"></a><span data-ttu-id="69f2d-104">예제</span><span class="sxs-lookup"><span data-stu-id="69f2d-104">Example</span></span>  
 [!code-cpp[System.Windows.Forms.DataGridView.ButtonDemos#0](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.ButtonDemos/CPP/DataGridViewBandDemo.cpp#0)]
 [!code-csharp[System.Windows.Forms.DataGridView.ButtonDemos#0](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.ButtonDemos/CS/DataGridViewBandDemo.cs#0)]
 [!code-vb[System.Windows.Forms.DataGridView.ButtonDemos#0](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.ButtonDemos/VB/datagridviewbanddemo.vb#0)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="69f2d-105">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="69f2d-105">Compiling the Code</span></span>  
 <span data-ttu-id="69f2d-106">이 예제에는 다음 사항이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="69f2d-106">This example requires:</span></span>  
  
- <span data-ttu-id="69f2d-107">System, System.Drawing 및 System.Windows.Forms 어셈블리에 대한 참조</span><span class="sxs-lookup"><span data-stu-id="69f2d-107">References to the System, System.Drawing, and System.Windows.Forms assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="69f2d-108">참고자료</span><span class="sxs-lookup"><span data-stu-id="69f2d-108">See also</span></span>

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridViewBand>
- <xref:System.Windows.Forms.DataGridViewRow>
- <xref:System.Windows.Forms.DataGridViewColumn>
- [<span data-ttu-id="69f2d-109">Windows Forms DataGridView 컨트롤에서 셀, 행 및 열 프로그래밍</span><span class="sxs-lookup"><span data-stu-id="69f2d-109">Programming with Cells, Rows, and Columns in the Windows Forms DataGridView Control</span></span>](programming-with-cells-rows-and-columns-in-the-datagrid.md)
