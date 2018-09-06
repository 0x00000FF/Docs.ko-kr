---
title: '방법: Windows Forms DataGridView 컨트롤에 기본 셀 스타일 설정'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DataGridView control [Windows Forms], cell styles
- cells [Windows Forms], styles
- data grids [Windows Forms], cell styles
ms.assetid: 1aaaca43-5340-447e-99c0-9177d9776aa1
ms.openlocfilehash: 072a9ce7e28983683ac1104b70c160cf5eea12b7
ms.sourcegitcommit: a885cc8c3e444ca6471348893d5373c6e9e49a47
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/06/2018
ms.locfileid: "43877338"
---
# <a name="how-to-set-default-cell-styles-for-the-windows-forms-datagridview-control"></a><span data-ttu-id="cf876-102">방법: Windows Forms DataGridView 컨트롤에 기본 셀 스타일 설정</span><span class="sxs-lookup"><span data-stu-id="cf876-102">How to: Set Default Cell Styles for the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="cf876-103"><xref:System.Windows.Forms.DataGridView> 컨트롤을 사용하여 전체 컨트롤과 특정 열 및 행에 대한 기본 셀 스타일을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cf876-103">With the <xref:System.Windows.Forms.DataGridView> control, you can specify default cell styles for the entire control and for specific columns and rows.</span></span> <span data-ttu-id="cf876-104">이러한 기본값은 컨트롤 수준에서 열 수준, 행 수준 및 셀 수준에 이르기까지 필터링합니다.</span><span class="sxs-lookup"><span data-stu-id="cf876-104">These defaults filter down from the control level to the column level, then to the row level, then to the cell level.</span></span> <span data-ttu-id="cf876-105">특정 <xref:System.Windows.Forms.DataGridViewCellStyle> 속성이 셀 수준에서 설정되지 않은 경우 행 수준의 기본 속성 설정이 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="cf876-105">If a particular <xref:System.Windows.Forms.DataGridViewCellStyle> property is not set at the cell level, the default property setting at the row level is used.</span></span> <span data-ttu-id="cf876-106">행 수준에서도 속성이 설정되지 않은 경우 기본 열 설정이 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="cf876-106">If the property is also not set at the row level, the default column setting is used.</span></span> <span data-ttu-id="cf876-107">끝으로, 열 수준에서도 속성이 설정되지 않은 경우 기본 <xref:System.Windows.Forms.DataGridView> 설정이 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="cf876-107">Finally, if the property is also not set at the column level, the default <xref:System.Windows.Forms.DataGridView> setting is used.</span></span> <span data-ttu-id="cf876-108">이 설정을 사용하면 여러 수준에서 속성 설정을 복제할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="cf876-108">With this setting, you can avoid having to duplicate the property settings at multiple levels.</span></span> <span data-ttu-id="cf876-109">각 수준에서 상위 수준과 다른 스타일을 지정하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="cf876-109">At each level, simply specify the styles that differ from the levels above it.</span></span> <span data-ttu-id="cf876-110">자세한 내용은 [Windows Forms DataGridView 컨트롤의 셀 스타일](../../../../docs/framework/winforms/controls/cell-styles-in-the-windows-forms-datagridview-control.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="cf876-110">For more information, see [Cell Styles in the Windows Forms DataGridView Control](../../../../docs/framework/winforms/controls/cell-styles-in-the-windows-forms-datagridview-control.md).</span></span>  
  
 <span data-ttu-id="cf876-111">Visual Studio에서는 이 작업이 광범위하게 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="cf876-111">There is extensive support for this task in Visual Studio.</span></span>  <span data-ttu-id="cf876-112">도 참조 하세요 [방법: 기본 셀 스타일 설정 및 데이터를 Windows Forms DataGridView 컨트롤 디자이너를 사용 하는 형식](https://msdn.microsoft.com/library/95y5fz2x\(v=vs.110\))합니다.</span><span class="sxs-lookup"><span data-stu-id="cf876-112">Also see [How to: Set Default Cell Styles and Data Formats for the Windows Forms DataGridView Control Using the Designer](https://msdn.microsoft.com/library/95y5fz2x\(v=vs.110\)).</span></span>  
  
### <a name="to-set-the-default-cell-styles-programmatically"></a><span data-ttu-id="cf876-113">프로그래밍 방식으로 기본 셀 스타일을 설정하려면</span><span class="sxs-lookup"><span data-stu-id="cf876-113">To set the default cell styles programmatically</span></span>  
  
1.  <span data-ttu-id="cf876-114"><xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A?displayProperty=nameWithType> 속성을 통해 검색된 <xref:System.Windows.Forms.DataGridViewCellStyle>의 속성을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="cf876-114">Set the properties of the <xref:System.Windows.Forms.DataGridViewCellStyle> retrieved through the <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A?displayProperty=nameWithType> property.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#141](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#141)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#141](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#141)]  
  
2.  <span data-ttu-id="cf876-115">여러 행과 열에서 사용할 새로운 <xref:System.Windows.Forms.DataGridViewCellStyle> 개체를 만들고 초기화합니다.</span><span class="sxs-lookup"><span data-stu-id="cf876-115">Create and initialize new <xref:System.Windows.Forms.DataGridViewCellStyle> objects for use by multiple rows and columns.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#142](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#142)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#142](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#142)]  
  
3.  <span data-ttu-id="cf876-116">특정 행과 열의 `DefaultCellStyle` 속성을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="cf876-116">Set the `DefaultCellStyle` property of specific rows and columns.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#143](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#143)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#143](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#143)]  
  
## <a name="example"></a><span data-ttu-id="cf876-117">예제</span><span class="sxs-lookup"><span data-stu-id="cf876-117">Example</span></span>  
 [!code-csharp[System.Windows.Forms.DataGridViewMisc#140](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#140)]
 [!code-vb[System.Windows.Forms.DataGridViewMisc#140](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#140)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="cf876-118">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="cf876-118">Compiling the Code</span></span>  
 <span data-ttu-id="cf876-119">이 예제에는 다음 사항이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="cf876-119">This example requires:</span></span>  
  
-   <span data-ttu-id="cf876-120">`dataGridView1`이라는 <xref:System.Windows.Forms.DataGridView> 컨트롤</span><span class="sxs-lookup"><span data-stu-id="cf876-120">A <xref:System.Windows.Forms.DataGridView> control named `dataGridView1`.</span></span>  
  
-   <span data-ttu-id="cf876-121"><xref:System?displayProperty=nameWithType>, <xref:System.Drawing?displayProperty=nameWithType> 및 <xref:System.Windows.Forms?displayProperty=nameWithType> 어셈블리에 대한 참조</span><span class="sxs-lookup"><span data-stu-id="cf876-121">References to the <xref:System?displayProperty=nameWithType>, <xref:System.Drawing?displayProperty=nameWithType>, and <xref:System.Windows.Forms?displayProperty=nameWithType> assemblies.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="cf876-122">강력한 프로그래밍</span><span class="sxs-lookup"><span data-stu-id="cf876-122">Robust Programming</span></span>  
 <span data-ttu-id="cf876-123">큰 데이터 집합으로 작업할 때 최대 확장성을 얻으려면 개별 요소에 대한 스타일 속성을 별도로 설정하는 대신 동일한 스타일을 사용하는 여러 행, 열 또는 셀에서 <xref:System.Windows.Forms.DataGridViewCellStyle> 개체를 공유해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf876-123">To achieve maximum scalability when you work with very large data sets, you should share <xref:System.Windows.Forms.DataGridViewCellStyle> objects across multiple rows, columns, or cells that use the same styles, rather than set the style properties for individual elements separately.</span></span> <span data-ttu-id="cf876-124">또한 공유 행을 만들고 <xref:System.Windows.Forms.DataGridViewRowCollection.SharedRow%2A?displayProperty=nameWithType> 속성을 통해 액세스해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf876-124">Additionally, you should create shared rows and access them by using the <xref:System.Windows.Forms.DataGridViewRowCollection.SharedRow%2A?displayProperty=nameWithType> property.</span></span> <span data-ttu-id="cf876-125">자세한 내용은 [Windows Forms DataGridView 컨트롤의 크기 조정에 대 한 모범 사례](../../../../docs/framework/winforms/controls/best-practices-for-scaling-the-windows-forms-datagridview-control.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="cf876-125">For more information, see [Best Practices for Scaling the Windows Forms DataGridView Control](../../../../docs/framework/winforms/controls/best-practices-for-scaling-the-windows-forms-datagridview-control.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cf876-126">참고 항목</span><span class="sxs-lookup"><span data-stu-id="cf876-126">See Also</span></span>  
 <xref:System.Windows.Forms.DataGridView>  
 <xref:System.Windows.Forms.DataGridViewCellStyle>  
 <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.DataGridViewBand.DefaultCellStyle%2A?displayProperty=nameWithType>  
 [<span data-ttu-id="cf876-127">Windows Forms DataGridView 컨트롤의 기본 형식 및 스타일 지정</span><span class="sxs-lookup"><span data-stu-id="cf876-127">Basic Formatting and Styling in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/basic-formatting-and-styling-in-the-windows-forms-datagridview-control.md)  
 [<span data-ttu-id="cf876-128">Windows Forms DataGridView 컨트롤의 셀 스타일</span><span class="sxs-lookup"><span data-stu-id="cf876-128">Cell Styles in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/cell-styles-in-the-windows-forms-datagridview-control.md)  
 [<span data-ttu-id="cf876-129">Windows Forms DataGridView 컨트롤의 크기를 조정하는 최선의 방법</span><span class="sxs-lookup"><span data-stu-id="cf876-129">Best Practices for Scaling the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/best-practices-for-scaling-the-windows-forms-datagridview-control.md)  
 [<span data-ttu-id="cf876-130">방법: Windows Forms DataGridView 컨트롤에 교대로 반복되는 행 스타일 설정</span><span class="sxs-lookup"><span data-stu-id="cf876-130">How to: Set Alternating Row Styles for the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/how-to-set-alternating-row-styles-for-the-windows-forms-datagridview-control.md)
