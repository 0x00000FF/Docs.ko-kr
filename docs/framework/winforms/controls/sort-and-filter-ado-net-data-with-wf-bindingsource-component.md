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
ms.openlocfilehash: 932d30d356225d88d7ef149561cc4c5cc8ac4dd0
ms.sourcegitcommit: 6eac9a01ff5d70c6d18460324c016a3612c5e268
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/14/2018
ms.locfileid: "45592112"
---
# <a name="how-to-sort-and-filter-adonet-data-with-the-windows-forms-bindingsource-component"></a><span data-ttu-id="98aae-102">방법: Windows Forms BindingSource 구성 요소를 사용하여 ADO.NET 데이터 정렬 및 필터링</span><span class="sxs-lookup"><span data-stu-id="98aae-102">How to: Sort and Filter ADO.NET Data with the Windows Forms BindingSource Component</span></span>
<span data-ttu-id="98aae-103">정렬 및 필터링 기능을 노출할 수 있습니다 <xref:System.Windows.Forms.BindingSource> 를 통해 제어 합니다 <xref:System.Windows.Forms.BindingSource.Sort%2A> 및 <xref:System.Windows.Forms.BindingSource.Filter%2A> 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="98aae-103">You can expose the sorting and filtering capability of <xref:System.Windows.Forms.BindingSource> control through the <xref:System.Windows.Forms.BindingSource.Sort%2A> and <xref:System.Windows.Forms.BindingSource.Filter%2A> properties.</span></span> <span data-ttu-id="98aae-104">데이터 원본의 경우에 간단한 정렬을 적용할 수 있습니다는 <xref:System.ComponentModel.IBindingList>, 및 고급 데이터 원본의 경우 정렬 및 필터링을 적용할 수 있습니다는 <xref:System.ComponentModel.IBindingListView>합니다.</span><span class="sxs-lookup"><span data-stu-id="98aae-104">You can apply simple sorting when the underlying data source is an <xref:System.ComponentModel.IBindingList>, and you can apply filtering and advanced sorting when the data source is an <xref:System.ComponentModel.IBindingListView>.</span></span> <span data-ttu-id="98aae-105">합니다 <xref:System.Windows.Forms.BindingSource.Sort%2A> 속성을 사용 하려면 표준 [!INCLUDE[vstecado](../../../../includes/vstecado-md.md)] 구문: 뒤에 데이터 원본에서 데이터의 열 이름을 나타내는 문자열입니다 `ASC` 또는 `DESC` 목록을 오름차순 또는 내림차순으로 정렬할지 여부를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="98aae-105">The <xref:System.Windows.Forms.BindingSource.Sort%2A> property requires standard [!INCLUDE[vstecado](../../../../includes/vstecado-md.md)] syntax: a string representing the name of a column of data in the data source followed by `ASC` or `DESC` to indicate whether the list should be sorted in ascending or descending order.</span></span> <span data-ttu-id="98aae-106">고급 정렬 또는 쉼표 구분 기호를 사용 하 여 각 열을 구분 하 여 여러 열 정렬을 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="98aae-106">You can set advanced sorting or multiple-column sorting by separating each column with a comma separator.</span></span> <span data-ttu-id="98aae-107"><xref:System.Windows.Forms.BindingSource.Filter%2A> 속성은 문자열 식을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="98aae-107">The <xref:System.Windows.Forms.BindingSource.Filter%2A> property takes a string expression.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="98aae-108">암호와 같은 중요한 정보를 연결 문자열 내에 저장하면 응용 프로그램 보안 문제가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="98aae-108">Storing sensitive information, such as a password, within the connection string can affect the security of your application.</span></span> <span data-ttu-id="98aae-109">데이터베이스 액세스를 제어할 경우에는 통합 보안이라고도 하는 Windows 인증을 사용하는 방법이 더 안전합니다.</span><span class="sxs-lookup"><span data-stu-id="98aae-109">Using Windows Authentication (also known as integrated security) is a more secure way to control access to a database.</span></span> <span data-ttu-id="98aae-110">자세한 내용은 [연결 정보 보호](../../../../docs/framework/data/adonet/protecting-connection-information.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="98aae-110">For more information, see [Protecting Connection Information](../../../../docs/framework/data/adonet/protecting-connection-information.md).</span></span>  
  
### <a name="to-filter-data-with-the-bindingsource"></a><span data-ttu-id="98aae-111">BindingSource 사용 하 여 데이터를 필터링 하려면</span><span class="sxs-lookup"><span data-stu-id="98aae-111">To filter data with the BindingSource</span></span>  
  
-   <span data-ttu-id="98aae-112">설정 된 <xref:System.Windows.Forms.BindingSource.Filter%2A> 속성을 원하는 식입니다.</span><span class="sxs-lookup"><span data-stu-id="98aae-112">Set the <xref:System.Windows.Forms.BindingSource.Filter%2A> property to expression that you want.</span></span>  
  
     <span data-ttu-id="98aae-113">다음 코드 예제에서는 식에는 다음 열에 대해 원하는 값 열 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="98aae-113">In the following code example, the expression is a column name followed by value that you want for the column.</span></span>  
  
 [!code-csharp[System.Windows.Forms.DataConnectorFilterAndSort#11](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorFilterAndSort/CS/form1.cs#11)]
 [!code-vb[System.Windows.Forms.DataConnectorFilterAndSort#11](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorFilterAndSort/VB/form1.vb#11)]  
  
### <a name="to-sort-data-with-the-bindingsource"></a><span data-ttu-id="98aae-114">BindingSource 사용 하 여 데이터를 정렬 하려면</span><span class="sxs-lookup"><span data-stu-id="98aae-114">To sort data with the BindingSource</span></span>  
  
1.  <span data-ttu-id="98aae-115">설정 합니다 <xref:System.Windows.Forms.BindingSource.Sort%2A> 속성을 원하는 열 이름 뒤에 `ASC` 또는 `DESC` 를 오름차순 또는 내림차순을 나타내는입니다.</span><span class="sxs-lookup"><span data-stu-id="98aae-115">Set the <xref:System.Windows.Forms.BindingSource.Sort%2A> property to the column name that you want followed by `ASC` or `DESC` to indicate the ascending or descending order.</span></span>  
  
2.  <span data-ttu-id="98aae-116">여러 열을 쉼표로 구분 합니다.</span><span class="sxs-lookup"><span data-stu-id="98aae-116">Separate multiple columns with a comma.</span></span>  
  
 [!code-csharp[System.Windows.Forms.DataConnectorFilterAndSort#12](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorFilterAndSort/CS/form1.cs#12)]
 [!code-vb[System.Windows.Forms.DataConnectorFilterAndSort#12](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorFilterAndSort/VB/form1.vb#12)]  
  
## <a name="example"></a><span data-ttu-id="98aae-117">예제</span><span class="sxs-lookup"><span data-stu-id="98aae-117">Example</span></span>  
 <span data-ttu-id="98aae-118">다음 코드 예제에 Northwind 샘플 데이터베이스의 Customers 테이블에서 데이터를 로드는 <xref:System.Windows.Forms.DataGridView> 컨트롤을 필터링 하 고 표시 된 데이터를 정렬 합니다.</span><span class="sxs-lookup"><span data-stu-id="98aae-118">The following code example loads data from the Customers table of the Northwind sample database into a <xref:System.Windows.Forms.DataGridView> control, and filters and sorts the displayed data.</span></span>  
  
 [!code-csharp[System.Windows.Forms.DataConnectorFilterAndSort#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorFilterAndSort/CS/form1.cs#1)]
 [!code-vb[System.Windows.Forms.DataConnectorFilterAndSort#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorFilterAndSort/VB/form1.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="98aae-119">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="98aae-119">Compiling the Code</span></span>  
 <span data-ttu-id="98aae-120">이 예제를 실행 하려면 코드를 포함 하는 폼에 붙여 넣습니다를 <xref:System.Windows.Forms.BindingSource> 라는 `BindingSource1` 와 <xref:System.Windows.Forms.DataGridView> 라는 `dataGridView1`합니다.</span><span class="sxs-lookup"><span data-stu-id="98aae-120">To run this example, paste the code into a form that contains a <xref:System.Windows.Forms.BindingSource> named `BindingSource1` and a <xref:System.Windows.Forms.DataGridView> named `dataGridView1`.</span></span> <span data-ttu-id="98aae-121">처리를 <xref:System.Windows.Forms.Form.Load> 양식과 호출에 대 한 이벤트 `InitializeSortedFilteredBindingSource` load 이벤트 처리기 메서드에서 합니다.</span><span class="sxs-lookup"><span data-stu-id="98aae-121">Handle the <xref:System.Windows.Forms.Form.Load> event for the form and call `InitializeSortedFilteredBindingSource` in the load event handler method.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="98aae-122">참고 항목</span><span class="sxs-lookup"><span data-stu-id="98aae-122">See Also</span></span>  
 <xref:System.Windows.Forms.BindingSource.Sort%2A>  
 <xref:System.Windows.Forms.BindingSource.Filter%2A>  
 [<span data-ttu-id="98aae-123">방법: 샘플 데이터베이스 설치</span><span class="sxs-lookup"><span data-stu-id="98aae-123">How to: Install Sample Databases</span></span>](https://msdn.microsoft.com/library/ed1291f6-604c-4972-ae22-0345c6dea12e)  
 [<span data-ttu-id="98aae-124">BindingSource 구성 요소</span><span class="sxs-lookup"><span data-stu-id="98aae-124">BindingSource Component</span></span>](../../../../docs/framework/winforms/controls/bindingsource-component.md)
