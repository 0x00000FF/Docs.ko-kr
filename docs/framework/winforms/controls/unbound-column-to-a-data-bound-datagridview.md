---
title: '방법: 데이터 바인딩된 Windows Forms DataGridView 컨트롤에 바인딩되지 않은 열을 추가 합니다.'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- columns [Windows Forms], unbound data
- data grids [Windows Forms], adding unbound columns
- DataGridView control [Windows Forms], unbound data
ms.assetid: f7bdc4d8-ba8e-421b-ad62-82d936f01372
ms.openlocfilehash: e877545f93fb57b636fd2e1559f52b4ad70a0b4e
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54722766"
---
# <a name="how-to-add-an-unbound-column-to-a-data-bound-windows-forms-datagridview-control"></a><span data-ttu-id="e4c45-102">방법: 데이터 바인딩된 Windows Forms DataGridView 컨트롤에 바인딩되지 않은 열을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="e4c45-102">How to: Add an Unbound Column to a Data-Bound Windows Forms DataGridView Control</span></span>
<span data-ttu-id="e4c45-103"><xref:System.Windows.Forms.DataGridView> 컨트롤에서 표시하는 데이터는 대개 일종의 데이터 소스에서 가져오지만 데이터 소스에서 가져오지 않는 데이터 열을 표시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e4c45-103">The data you display in the <xref:System.Windows.Forms.DataGridView> control will normally come from a data source of some kind, but you might want to display a column of data that does not come from the data source.</span></span> <span data-ttu-id="e4c45-104">이 열 유형을 바인딩되지 않은 열이라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="e4c45-104">This kind of column is called an unbound column.</span></span> <span data-ttu-id="e4c45-105">바인딩되지 않은 열에서는 대부분 폼을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e4c45-105">Unbound columns can take many forms.</span></span> <span data-ttu-id="e4c45-106">대부분 경우에 바인딩되지 않은 열은 데이터 행의 세부 정보에 액세스하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="e4c45-106">Frequently, they are used to provide access to the details of a data row.</span></span>  
  
 <span data-ttu-id="e4c45-107">다음 코드 예제에는의 바인딩되지 않은 열을 만드는 방법을 보여 줍니다 **세부 정보** 마스터/세부 시나리오를 구현 하는 경우 부모 테이블의 특정 행에 관련 된 자식 테이블에 표시할 단추입니다.</span><span class="sxs-lookup"><span data-stu-id="e4c45-107">The following code example demonstrates how to create an unbound column of **Details** buttons to display a child table related to a particular row in a parent table when you implement a master/detail scenario.</span></span> <span data-ttu-id="e4c45-108">단추 클릭에 응답하려면 자식 테이블이 포함된 폼을 표시하는 <xref:System.Windows.Forms.DataGridView.CellClick?displayProperty=nameWithType> 이벤트 처리기를 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="e4c45-108">To respond to button clicks, implement a <xref:System.Windows.Forms.DataGridView.CellClick?displayProperty=nameWithType> event handler that displays a form containing the child table.</span></span>  
  
 <span data-ttu-id="e4c45-109">Visual Studio에서는 이 작업이 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="e4c45-109">There is support for this task in Visual Studio.</span></span>  <span data-ttu-id="e4c45-110">또한 참조 [방법: 추가 하 고 디자이너를 사용 하 여 Windows Forms DataGridView 컨트롤에서 열을 제거 합니다.](https://msdn.microsoft.com/library/dyyesckz\(v=vs.110\))</span><span class="sxs-lookup"><span data-stu-id="e4c45-110">Also see [How to: Add and Remove Columns in the Windows Forms DataGridView Control Using the Designer](https://msdn.microsoft.com/library/dyyesckz\(v=vs.110\))</span></span>  
  
## <a name="example"></a><span data-ttu-id="e4c45-111">예제</span><span class="sxs-lookup"><span data-stu-id="e4c45-111">Example</span></span>  
 [!code-csharp[System.Windows.Forms.DataGridViewMisc#010](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#010)]
 [!code-vb[System.Windows.Forms.DataGridViewMisc#010](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#010)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="e4c45-112">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="e4c45-112">Compiling the Code</span></span>  
 <span data-ttu-id="e4c45-113">이 예제에는 다음 사항이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="e4c45-113">This example requires:</span></span>  
  
-   <span data-ttu-id="e4c45-114">`dataGridView1`이라는 <xref:System.Windows.Forms.DataGridView> 컨트롤</span><span class="sxs-lookup"><span data-stu-id="e4c45-114">A <xref:System.Windows.Forms.DataGridView> control named `dataGridView1`.</span></span>  
  
-   <span data-ttu-id="e4c45-115"><xref:System?displayProperty=nameWithType> 및 <xref:System.Windows.Forms?displayProperty=nameWithType> 어셈블리에 대한 참조</span><span class="sxs-lookup"><span data-stu-id="e4c45-115">References to the <xref:System?displayProperty=nameWithType> and <xref:System.Windows.Forms?displayProperty=nameWithType> assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e4c45-116">참고자료</span><span class="sxs-lookup"><span data-stu-id="e4c45-116">See also</span></span>
- <xref:System.Windows.Forms.DataGridView>
- [<span data-ttu-id="e4c45-117">Windows Forms DataGridView 컨트롤에서 데이터 표시</span><span class="sxs-lookup"><span data-stu-id="e4c45-117">Displaying Data in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/displaying-data-in-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="e4c45-118">Windows Forms DataGridView 컨트롤의 데이터 디스플레이 모드</span><span class="sxs-lookup"><span data-stu-id="e4c45-118">Data Display Modes in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/data-display-modes-in-the-windows-forms-datagridview-control.md)
