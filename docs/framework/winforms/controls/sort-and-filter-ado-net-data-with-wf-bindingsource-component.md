---
title: '방법: Windows Forms BindingSource 구성 요소를 사용하여 ADO.NET 데이터 정렬 및 필터링'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- sorting data
- data sorting [Windows Forms], ADO.NET
- data [Windows Forms], filtering
- BindingSource component [Windows Forms], sorting and filtering data
- filtering [Windows Forms], ADO.NET
- data [Windows Forms], sorting
- ADO.NET [Windows Forms]
ms.assetid: 6c206daf-d706-4602-9dbe-435343052063
ms.openlocfilehash: ae331ca9e3fd2aed654659e11434454874eff8fa
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2019
ms.locfileid: "69960424"
---
# <a name="how-to-sort-and-filter-adonet-data-with-the-windows-forms-bindingsource-component"></a><span data-ttu-id="79637-102">방법: Windows Forms BindingSource 구성 요소를 사용하여 ADO.NET 데이터 정렬 및 필터링</span><span class="sxs-lookup"><span data-stu-id="79637-102">How to: Sort and Filter ADO.NET Data with the Windows Forms BindingSource Component</span></span>
<span data-ttu-id="79637-103"><xref:System.Windows.Forms.BindingSource.Sort%2A> <xref:System.Windows.Forms.BindingSource> 및<xref:System.Windows.Forms.BindingSource.Filter%2A> 속성을 통해 제어의 정렬 및 필터링 기능을 노출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="79637-103">You can expose the sorting and filtering capability of <xref:System.Windows.Forms.BindingSource> control through the <xref:System.Windows.Forms.BindingSource.Sort%2A> and <xref:System.Windows.Forms.BindingSource.Filter%2A> properties.</span></span> <span data-ttu-id="79637-104">기본 데이터 원본이 <xref:System.ComponentModel.IBindingList>인 경우 간단한 정렬을 적용할 수 있으며, 데이터 원본이 <xref:System.ComponentModel.IBindingListView>인 경우 필터링 및 고급 정렬을 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="79637-104">You can apply simple sorting when the underlying data source is an <xref:System.ComponentModel.IBindingList>, and you can apply filtering and advanced sorting when the data source is an <xref:System.ComponentModel.IBindingListView>.</span></span> <span data-ttu-id="79637-105">속성 <xref:System.Windows.Forms.BindingSource.Sort%2A> 에는 표준 ADO.NET 구문이 필요 합니다. 데이터 원본 `ASC` 에 있는 데이터 열의 이름을 나타내는 문자열 이거나 `DESC` , 오름차순 이나 내림차순으로 정렬 해야 하는지 여부를 나타내는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="79637-105">The <xref:System.Windows.Forms.BindingSource.Sort%2A> property requires standard ADO.NET syntax: a string representing the name of a column of data in the data source followed by `ASC` or `DESC` to indicate whether the list should be sorted in ascending or descending order.</span></span> <span data-ttu-id="79637-106">쉼표 구분 기호를 사용 하 여 각 열을 구분 하 여 고급 정렬 또는 다중 열 정렬을 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="79637-106">You can set advanced sorting or multiple-column sorting by separating each column with a comma separator.</span></span> <span data-ttu-id="79637-107">속성 <xref:System.Windows.Forms.BindingSource.Filter%2A> 은 문자열 식을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="79637-107">The <xref:System.Windows.Forms.BindingSource.Filter%2A> property takes a string expression.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="79637-108">암호와 같은 중요한 정보를 연결 문자열 내에 저장하면 애플리케이션 보안 문제가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="79637-108">Storing sensitive information, such as a password, within the connection string can affect the security of your application.</span></span> <span data-ttu-id="79637-109">데이터베이스 액세스를 제어할 경우에는 통합 보안이라고도 하는 Windows 인증을 사용하는 방법이 더 안전합니다.</span><span class="sxs-lookup"><span data-stu-id="79637-109">Using Windows Authentication (also known as integrated security) is a more secure way to control access to a database.</span></span> <span data-ttu-id="79637-110">자세한 내용은 [연결 정보 보호](../../data/adonet/protecting-connection-information.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="79637-110">For more information, see [Protecting Connection Information](../../data/adonet/protecting-connection-information.md).</span></span>  
  
### <a name="to-filter-data-with-the-bindingsource"></a><span data-ttu-id="79637-111">BindingSource를 사용 하 여 데이터를 필터링 하려면</span><span class="sxs-lookup"><span data-stu-id="79637-111">To filter data with the BindingSource</span></span>  
  
- <span data-ttu-id="79637-112"><xref:System.Windows.Forms.BindingSource.Filter%2A> 속성을 원하는 식으로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="79637-112">Set the <xref:System.Windows.Forms.BindingSource.Filter%2A> property to expression that you want.</span></span>  
  
     <span data-ttu-id="79637-113">다음 코드 예제에서 식은 열 이름 뒤에 열에 대해 원하는 값을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="79637-113">In the following code example, the expression is a column name followed by value that you want for the column.</span></span>  
  
 [!code-csharp[System.Windows.Forms.DataConnectorFilterAndSort#11](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorFilterAndSort/CS/form1.cs#11)]
 [!code-vb[System.Windows.Forms.DataConnectorFilterAndSort#11](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorFilterAndSort/VB/form1.vb#11)]  
  
### <a name="to-sort-data-with-the-bindingsource"></a><span data-ttu-id="79637-114">BindingSource를 사용 하 여 데이터를 정렬 하려면</span><span class="sxs-lookup"><span data-stu-id="79637-114">To sort data with the BindingSource</span></span>  
  
1. <span data-ttu-id="79637-115">속성을 뒤에 표시 되는 열 이름으로 설정 `DESC` 하거나오름차순이나내림차순으로설정합니다.`ASC` <xref:System.Windows.Forms.BindingSource.Sort%2A></span><span class="sxs-lookup"><span data-stu-id="79637-115">Set the <xref:System.Windows.Forms.BindingSource.Sort%2A> property to the column name that you want followed by `ASC` or `DESC` to indicate the ascending or descending order.</span></span>  
  
2. <span data-ttu-id="79637-116">여러 열을 쉼표로 구분 합니다.</span><span class="sxs-lookup"><span data-stu-id="79637-116">Separate multiple columns with a comma.</span></span>  
  
 [!code-csharp[System.Windows.Forms.DataConnectorFilterAndSort#12](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorFilterAndSort/CS/form1.cs#12)]
 [!code-vb[System.Windows.Forms.DataConnectorFilterAndSort#12](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorFilterAndSort/VB/form1.vb#12)]  
  
## <a name="example"></a><span data-ttu-id="79637-117">예제</span><span class="sxs-lookup"><span data-stu-id="79637-117">Example</span></span>  
 <span data-ttu-id="79637-118">다음 코드 예제에서는 Northwind 샘플 데이터베이스 <xref:System.Windows.Forms.DataGridView> 의 Customers 테이블에서 컨트롤로 데이터를 로드 하 고 표시 된 데이터를 필터링 및 정렬 합니다.</span><span class="sxs-lookup"><span data-stu-id="79637-118">The following code example loads data from the Customers table of the Northwind sample database into a <xref:System.Windows.Forms.DataGridView> control, and filters and sorts the displayed data.</span></span>  
  
 [!code-csharp[System.Windows.Forms.DataConnectorFilterAndSort#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorFilterAndSort/CS/form1.cs#1)]
 [!code-vb[System.Windows.Forms.DataConnectorFilterAndSort#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorFilterAndSort/VB/form1.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="79637-119">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="79637-119">Compiling the Code</span></span>  
 <span data-ttu-id="79637-120">이 예제를 실행 <xref:System.Windows.Forms.BindingSource> 하려면 라는 `BindingSource1` 와 <xref:System.Windows.Forms.DataGridView> `dataGridView1`라는를 포함 하는 폼에 코드를 붙여넣습니다.</span><span class="sxs-lookup"><span data-stu-id="79637-120">To run this example, paste the code into a form that contains a <xref:System.Windows.Forms.BindingSource> named `BindingSource1` and a <xref:System.Windows.Forms.DataGridView> named `dataGridView1`.</span></span> <span data-ttu-id="79637-121">폼에 <xref:System.Windows.Forms.Form.Load> 대 한 이벤트를 처리 하 `InitializeSortedFilteredBindingSource` 고 load 이벤트 처리기 메서드에서를 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="79637-121">Handle the <xref:System.Windows.Forms.Form.Load> event for the form and call `InitializeSortedFilteredBindingSource` in the load event handler method.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="79637-122">참고자료</span><span class="sxs-lookup"><span data-stu-id="79637-122">See also</span></span>

- <xref:System.Windows.Forms.BindingSource.Sort%2A>
- <xref:System.Windows.Forms.BindingSource.Filter%2A>
- <span data-ttu-id="79637-123">[방법: 예제 데이터베이스 설치](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/8b6y4c7s(v=vs.120))</span><span class="sxs-lookup"><span data-stu-id="79637-123">[How to: Install Sample Databases](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/8b6y4c7s(v=vs.120))</span></span>
- [<span data-ttu-id="79637-124">BindingSource 구성 요소</span><span class="sxs-lookup"><span data-stu-id="79637-124">BindingSource Component</span></span>](bindingsource-component.md)
