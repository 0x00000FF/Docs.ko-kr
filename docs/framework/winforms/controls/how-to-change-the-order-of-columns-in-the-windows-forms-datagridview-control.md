---
title: '방법: Windows Forms DataGridView 컨트롤에서 열 순서 변경'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- columns [Windows Forms], changing order
- DataGridView control [Windows Forms], column order
- data grids [Windows Forms], changing column order
ms.assetid: 5e9ac3bc-b0f0-48cb-a3d5-b005af905395
ms.openlocfilehash: 4b3859579814f4a10f38fd47df6fe933e2722cb2
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/28/2019
ms.locfileid: "64643349"
---
# <a name="how-to-change-the-order-of-columns-in-the-windows-forms-datagridview-control"></a><span data-ttu-id="b0d60-102">방법: Windows Forms DataGridView 컨트롤에서 열 순서 변경</span><span class="sxs-lookup"><span data-stu-id="b0d60-102">How to: Change the Order of Columns in the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="b0d60-103"><xref:System.Windows.Forms.DataGridView>를 사용하여 데이터 소스의 데이터를 표시할 때 데이터 소스의 스키마에 있는 열이 표시하려는 순서대로 나타나지 않는 경우가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b0d60-103">When you use a <xref:System.Windows.Forms.DataGridView> to display data from a data source, the columns in the data source's schema sometimes do not appear in the order you would like to display them.</span></span> <span data-ttu-id="b0d60-104"><xref:System.Windows.Forms.DataGridViewColumn> 클래스의 <xref:System.Windows.Forms.DataGridViewColumn.DisplayIndex%2A> 속성을 사용하여 열의 표시 순서를 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b0d60-104">You can change the displayed order of the columns by using the <xref:System.Windows.Forms.DataGridViewColumn.DisplayIndex%2A> property of the <xref:System.Windows.Forms.DataGridViewColumn> class.</span></span>  
  
 <span data-ttu-id="b0d60-105">다음 코드 예제에서는 Northwind 샘플 데이터베이스의 Customers 테이블에 바인딩할 때 자동으로 생성되는 일부 열의 위치를 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="b0d60-105">The following code example repositions some of the columns automatically generated when binding to the Customers table in the Northwind sample database.</span></span> <span data-ttu-id="b0d60-106">바인딩하는 방법에 대 한 자세한 내용은 합니다 <xref:System.Windows.Forms.DataGridView> 컨트롤을 데이터베이스 테이블을 참조 하십시오 [방법: 바인딩 데이터는 Windows Forms DataGridView 컨트롤](how-to-bind-data-to-the-windows-forms-datagridview-control.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="b0d60-106">For more information about how to bind the <xref:System.Windows.Forms.DataGridView> control to a database table, see [How to: Bind Data to the Windows Forms DataGridView Control](how-to-bind-data-to-the-windows-forms-datagridview-control.md).</span></span>  
  
 <span data-ttu-id="b0d60-107">Visual Studio에서는 이 작업이 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="b0d60-107">There is support for this task in Visual Studio.</span></span>  <span data-ttu-id="b0d60-108">또한 참조 [방법: 디자이너를 사용 하 여 Windows Forms DataGridView 컨트롤에서 열 순서 변경](change-the-order-of-columns-in-the-datagrid-using-the-designer.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="b0d60-108">Also see [How to: Change the Order of Columns in the Windows Forms DataGridView Control Using the Designer](change-the-order-of-columns-in-the-datagrid-using-the-designer.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="b0d60-109">예제</span><span class="sxs-lookup"><span data-stu-id="b0d60-109">Example</span></span>  
 [!code-csharp[System.Windows.Forms.DataGridViewMisc#040](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#040)]
 [!code-vb[System.Windows.Forms.DataGridViewMisc#040](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#040)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="b0d60-110">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="b0d60-110">Compiling the Code</span></span>  
 <span data-ttu-id="b0d60-111">이 예제에는 다음 사항이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="b0d60-111">This example requires:</span></span>  
  
- <span data-ttu-id="b0d60-112">Northwind 샘플 데이터베이스의 `Customers` 테이블과 같은 표시된 열 이름을 포함하는 테이블에 바인딩된 `customersDataGridView`라는 <xref:System.Windows.Forms.DataGridView> 컨트롤</span><span class="sxs-lookup"><span data-stu-id="b0d60-112">A <xref:System.Windows.Forms.DataGridView> control named `customersDataGridView` that is bound to a table with the indicated column names, such as the `Customers` table in the Northwind sample database.</span></span>  
  
- <span data-ttu-id="b0d60-113"><xref:System?displayProperty=nameWithType>, <xref:System.Windows.Forms?displayProperty=nameWithType>, <xref:System.Data?displayProperty=nameWithType> 및 <xref:System.Xml?displayProperty=nameWithType> 어셈블리에 대한 참조</span><span class="sxs-lookup"><span data-stu-id="b0d60-113">References to the <xref:System?displayProperty=nameWithType>, <xref:System.Windows.Forms?displayProperty=nameWithType>, <xref:System.Data?displayProperty=nameWithType>, and <xref:System.Xml?displayProperty=nameWithType> assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b0d60-114">참고자료</span><span class="sxs-lookup"><span data-stu-id="b0d60-114">See also</span></span>

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridViewColumn>
- <xref:System.Windows.Forms.DataGridViewColumn.DisplayIndex%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridViewColumn.Visible%2A?displayProperty=nameWithType>
- [<span data-ttu-id="b0d60-115">Windows Forms DataGridView 컨트롤에서 데이터 표시</span><span class="sxs-lookup"><span data-stu-id="b0d60-115">Displaying Data in the Windows Forms DataGridView Control</span></span>](displaying-data-in-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="b0d60-116">방법: Windows Forms DataGridView 컨트롤에 데이터 바인딩</span><span class="sxs-lookup"><span data-stu-id="b0d60-116">How to: Bind Data to the Windows Forms DataGridView Control</span></span>](how-to-bind-data-to-the-windows-forms-datagridview-control.md)
