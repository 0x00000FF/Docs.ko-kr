---
title: '방법: Windows Forms DataGrid 컨트롤을 사용 하 여 마스터-세부 목록 만들기'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- master-details lists
- DataGrid control [Windows Forms], master-details lists
- related tables [Windows Forms], displaying in DataGrid control
ms.assetid: 20388c6a-94f9-4d96-be18-8c200491247f
ms.openlocfilehash: 6ff13264709c4557d698435ac05b7759be58f1e8
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54712894"
---
# <a name="how-to-create-masterdetail-lists-with-the-windows-forms-datagrid-control"></a><span data-ttu-id="2be3a-102">방법: Windows Forms DataGrid 컨트롤을 사용 하 여 마스터/세부 목록 만들기</span><span class="sxs-lookup"><span data-stu-id="2be3a-102">How to: Create Master/Detail Lists with the Windows Forms DataGrid Control</span></span>
> [!NOTE]
>  <span data-ttu-id="2be3a-103"><xref:System.Windows.Forms.DataGridView> 컨트롤은 <xref:System.Windows.Forms.DataGrid> 컨트롤을 대체하고 여기에 다른 기능을 추가하여 새로 도입된 컨트롤이지만 이전 버전과의 호환성 및 이후 사용 가능성을 고려하여 <xref:System.Windows.Forms.DataGrid> 컨트롤을 계속 유지하도록 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2be3a-103">The <xref:System.Windows.Forms.DataGridView> control replaces and adds functionality to the <xref:System.Windows.Forms.DataGrid> control; however, the <xref:System.Windows.Forms.DataGrid> control is retained for both backward compatibility and future use, if you choose.</span></span> <span data-ttu-id="2be3a-104">자세한 내용은 [Windows Forms DataGridView 및 DataGrid 컨트롤의 차이점](../../../../docs/framework/winforms/controls/differences-between-the-windows-forms-datagridview-and-datagrid-controls.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="2be3a-104">For more information, see [Differences Between the Windows Forms DataGridView and DataGrid Controls](../../../../docs/framework/winforms/controls/differences-between-the-windows-forms-datagridview-and-datagrid-controls.md).</span></span>  
  
 <span data-ttu-id="2be3a-105">경우에 <xref:System.Data.DataSet> 계열이 관련된 테이블의 두 사용할 수 있습니다 <xref:System.Windows.Forms.DataGrid> 마스터/세부 정보 형식으로 데이터를 표시 하는 컨트롤입니다.</span><span class="sxs-lookup"><span data-stu-id="2be3a-105">If your <xref:System.Data.DataSet> contains a series of related tables, you can use two <xref:System.Windows.Forms.DataGrid> controls to display the data in a master/detail format.</span></span> <span data-ttu-id="2be3a-106">하나의 <xref:System.Windows.Forms.DataGrid> 는 마스터 데이터에 지정 된 두 번째 지정 된 세부 정보 표 및 합니다.</span><span class="sxs-lookup"><span data-stu-id="2be3a-106">One <xref:System.Windows.Forms.DataGrid> is designated to be the master grid, and the second is designated to be the details grid.</span></span> <span data-ttu-id="2be3a-107">목록에 항목을 선택 하면 관련된 자식 항목의 모든 세부 정보 목록에 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2be3a-107">When you select an entry in the master list, all of the related child entries are shown in the details list.</span></span> <span data-ttu-id="2be3a-108">예를 들어, 경우에 <xref:System.Data.DataSet> 고객 테이블 및 관련된 Orders 테이블에 포함 되어는 마스터 데이터를 Customers 테이블과 Orders 테이블 세부 정보 표에서을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="2be3a-108">For example, if your <xref:System.Data.DataSet> contains a Customers table and a related Orders table, you would specify the Customers table to be the master grid and the Orders table to be the details grid.</span></span> <span data-ttu-id="2be3a-109">마스터 그리드에서 고객을 선택 하면 모든 주문을 Orders 테이블의 해당 고객과 관련 된 세부 정보 창에 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2be3a-109">When a customer is selected from the master grid, all of the orders associated with that customer in the Orders table would be displayed in the details grid.</span></span>  
  
### <a name="to-set-a-masterdetail-relationship-programmatically"></a><span data-ttu-id="2be3a-110">마스터/세부 관계를 프로그래밍 방식으로 설정 하려면</span><span class="sxs-lookup"><span data-stu-id="2be3a-110">To set a master/detail relationship programmatically</span></span>  
  
1.  <span data-ttu-id="2be3a-111">두 개의 새 만들려면 <xref:System.Windows.Forms.DataGrid> 컨트롤과 해당 속성을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="2be3a-111">Create two new <xref:System.Windows.Forms.DataGrid> controls and set their properties.</span></span>  
  
2.  <span data-ttu-id="2be3a-112">데이터 집합에 테이블을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="2be3a-112">Add tables to the dataset.</span></span>  
  
3.  <span data-ttu-id="2be3a-113">형식의 변수 선언 <xref:System.Data.DataRelation> 만들려는 관계를 나타내는입니다.</span><span class="sxs-lookup"><span data-stu-id="2be3a-113">Declare a variable of type <xref:System.Data.DataRelation> to represent the relation you want to create.</span></span>  
  
4.  <span data-ttu-id="2be3a-114">테이블, 열 및 두 테이블을 연결 해 주는 항목 및 관계의 이름을 지정 하 여 관계를 인스턴스화하십시오.</span><span class="sxs-lookup"><span data-stu-id="2be3a-114">Instantiate the relationship by specifying a name for the relationship and specifying the table, column, and item that will tie the two tables.</span></span>  
  
5.  <span data-ttu-id="2be3a-115">에 대 한 관계를 추가 합니다 <xref:System.Data.DataSet> 개체의 <xref:System.Data.DataSet.Relations%2A> 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="2be3a-115">Add the relationship to the <xref:System.Data.DataSet> object's <xref:System.Data.DataSet.Relations%2A> collection.</span></span>  
  
6.  <span data-ttu-id="2be3a-116">사용 하 여는 <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> 메서드를 <xref:System.Windows.Forms.DataGrid> 각 표를 바인딩하는 <xref:System.Data.DataSet>합니다.</span><span class="sxs-lookup"><span data-stu-id="2be3a-116">Use the <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> method of the <xref:System.Windows.Forms.DataGrid> to bind each of the grids to the <xref:System.Data.DataSet>.</span></span>  
  
     <span data-ttu-id="2be3a-117">다음 예제에서는 이전에 생성 된의 Customers 및 Orders 테이블 간 마스터/세부 관계를 설정 하는 방법을 보여 줍니다 <xref:System.Data.DataSet> (`ds`).</span><span class="sxs-lookup"><span data-stu-id="2be3a-117">The following example shows how to set a master/detail relationship between the Customers and Orders tables in a previously generated <xref:System.Data.DataSet> (`ds`).</span></span>  
  
    ```vb  
    Dim myDataRelation As DataRelation  
    myDataRelation = New DataRelation _  
       ("CustOrd", ds.Tables("Customers").Columns("CustomerID"), _  
       ds.Tables("Orders").Columns("CustomerID"))  
    ' Add the relation to the DataSet.  
    ds.Relations.Add(myDataRelation)  
    GridOrders.SetDataBinding(ds, "Customers")  
    GridDetails.SetDataBinding(ds, "Customers.CustOrd")  
    ```  
  
    ```csharp  
    DataRelation myDataRelation;  
    myDataRelation = new DataRelation("CustOrd", ds.Tables["Customers"].Columns["CustomerID"], ds.Tables["Orders"].Columns["CustomerID"]);  
    // Add the relation to the DataSet.  
    ds.Relations.Add(myDataRelation);  
    GridOrders.SetDataBinding(ds,"Customers");  
    GridDetails.SetDataBinding(ds,"Customers.CustOrd");  
    ```  
  
    ```cpp  
    DataRelation^ myDataRelation;  
    myDataRelation = gcnew DataRelation("CustOrd",  
       ds->Tables["Customers"]->Columns["CustomerID"],  
       ds->Tables["Orders"]->Columns["CustomerID"]);  
    // Add the relation to the DataSet.  
    ds->Relations->Add(myDataRelation);  
    GridOrders->SetDataBinding(ds, "Customers");  
    GridDetails->SetDataBinding(ds, "Customers.CustOrd");  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="2be3a-118">참고자료</span><span class="sxs-lookup"><span data-stu-id="2be3a-118">See also</span></span>
- [<span data-ttu-id="2be3a-119">DataGrid 컨트롤</span><span class="sxs-lookup"><span data-stu-id="2be3a-119">DataGrid Control</span></span>](../../../../docs/framework/winforms/controls/datagrid-control-windows-forms.md)
- [<span data-ttu-id="2be3a-120">DataGrid 컨트롤 개요</span><span class="sxs-lookup"><span data-stu-id="2be3a-120">DataGrid Control Overview</span></span>](../../../../docs/framework/winforms/controls/datagrid-control-overview-windows-forms.md)
- [<span data-ttu-id="2be3a-121">방법: 데이터 소스에 Windows Forms DataGrid 컨트롤 바인딩</span><span class="sxs-lookup"><span data-stu-id="2be3a-121">How to: Bind the Windows Forms DataGrid Control to a Data Source</span></span>](../../../../docs/framework/winforms/controls/how-to-bind-the-windows-forms-datagrid-control-to-a-data-source.md)
