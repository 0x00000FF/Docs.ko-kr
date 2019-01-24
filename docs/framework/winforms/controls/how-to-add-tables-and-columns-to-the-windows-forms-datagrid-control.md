---
title: '방법: Windows Forms DataGrid 컨트롤에 테이블과 열 추가'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- columns [Windows Forms], adding to DataGrid control
- tables [Windows Forms], adding to DataGrid control
- DataGrid control [Windows Forms], adding tables and columns
ms.assetid: 2fe661b9-aa06-49b9-a314-a0d3cbfdcb4d
ms.openlocfilehash: be0bb6d3d7b8d8b362653257139e83900dbb2780
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54717872"
---
# <a name="how-to-add-tables-and-columns-to-the-windows-forms-datagrid-control"></a><span data-ttu-id="53353-102">방법: Windows Forms DataGrid 컨트롤에 테이블과 열 추가</span><span class="sxs-lookup"><span data-stu-id="53353-102">How to: Add Tables and Columns to the Windows Forms DataGrid Control</span></span>
> [!NOTE]
>  <span data-ttu-id="53353-103"><xref:System.Windows.Forms.DataGridView> 컨트롤은 <xref:System.Windows.Forms.DataGrid> 컨트롤을 대체하고 여기에 다른 기능을 추가하여 새로 도입된 컨트롤이지만 이전 버전과의 호환성 및 이후 사용 가능성을 고려하여 <xref:System.Windows.Forms.DataGrid> 컨트롤을 계속 유지하도록 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="53353-103">The <xref:System.Windows.Forms.DataGridView> control replaces and adds functionality to the <xref:System.Windows.Forms.DataGrid> control; however, the <xref:System.Windows.Forms.DataGrid> control is retained for both backward compatibility and future use, if you choose.</span></span> <span data-ttu-id="53353-104">자세한 내용은 [Windows Forms DataGridView 및 DataGrid 컨트롤의 차이점](../../../../docs/framework/winforms/controls/differences-between-the-windows-forms-datagridview-and-datagrid-controls.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="53353-104">For more information, see [Differences Between the Windows Forms DataGridView and DataGrid Controls](../../../../docs/framework/winforms/controls/differences-between-the-windows-forms-datagridview-and-datagrid-controls.md).</span></span>  
  
 <span data-ttu-id="53353-105">Windows Forms에서 데이터를 표시할 수 있습니다 <xref:System.Windows.Forms.DataGrid> 컨트롤에 테이블과 열을 만들어 **DataGridTableStyle** 개체에 추가 하는 **GridTableStylesCollection** 개체 이며, 통해 액세스 합니다 <xref:System.Windows.Forms.DataGrid> 컨트롤의 **TableStyles** 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="53353-105">You can display data in the Windows Forms <xref:System.Windows.Forms.DataGrid> control in tables and columns by creating **DataGridTableStyle** objects and adding them to the **GridTableStylesCollection** object, which is accessed through the <xref:System.Windows.Forms.DataGrid> control's **TableStyles** property.</span></span> <span data-ttu-id="53353-106">각 테이블 스타일에 지정 된 모든 데이터 테이블의 내용을 표시 합니다 **DataGridTableStyle** 개체의 **MappingName** 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="53353-106">Each table style displays the contents of whatever data table is specified in the **DataGridTableStyle** object's **MappingName** property.</span></span> <span data-ttu-id="53353-107">기본적으로 테이블 스타일을 지정 된 열 스타일이 없는 사용 하 여 해당 데이터 테이블 안의 모든 열 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="53353-107">By default, a table style with no column styles specified will display all the columns within that data table.</span></span> <span data-ttu-id="53353-108">테이블에서 열 추가 하 여 표시를 제한할 수 있습니다 **DataGridColumnStyle** 개체를 **GridColumnStylesCollection** 개체를 통해 액세스할 수 있는  **GridColumnStyles** 속성을 각각 **DataGridTableStyle** 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="53353-108">You can restrict which columns from the table appear by adding **DataGridColumnStyle** objects to the **GridColumnStylesCollection** object, which is accessed through the **GridColumnStyles** property of each **DataGridTableStyle** object.</span></span>  
  
### <a name="to-add-a-table-and-column-to-a-datagrid-programmatically"></a><span data-ttu-id="53353-109">테이블 및 열을 DataGrid에 프로그래밍 방식으로 추가 하려면</span><span class="sxs-lookup"><span data-stu-id="53353-109">To add a table and column to a DataGrid programmatically</span></span>  
  
1.  <span data-ttu-id="53353-110">테이블의 데이터를 표시 하려면 먼저 바인딩해야 합니다 <xref:System.Windows.Forms.DataGrid> 데이터 집합에는 컨트롤입니다.</span><span class="sxs-lookup"><span data-stu-id="53353-110">In order to display data in the table, you must first bind the <xref:System.Windows.Forms.DataGrid> control to a dataset.</span></span> <span data-ttu-id="53353-111">자세한 내용은 [방법: 데이터 소스에 Windows Forms DataGrid 컨트롤 바인딩](../../../../docs/framework/winforms/controls/how-to-bind-the-windows-forms-datagrid-control-to-a-data-source.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="53353-111">For more information, see [How to: Bind the Windows Forms DataGrid Control to a Data Source](../../../../docs/framework/winforms/controls/how-to-bind-the-windows-forms-datagrid-control-to-a-data-source.md).</span></span>  
  
    > [!CAUTION]
    >  <span data-ttu-id="53353-112">열 스타일을 프로그래밍 방식으로 지정할 때 항상 만들기 **DataGridColumnStyle** 개체에 추가 하는 **GridColumnStylesCollection** 개체를 추가 하기 전에  **DataGridTableStyle** 개체를 **GridTableStylesCollection** 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="53353-112">When programmatically specifying column styles, always create **DataGridColumnStyle** objects and add them to the **GridColumnStylesCollection** object before adding **DataGridTableStyle** objects to the **GridTableStylesCollection** object.</span></span> <span data-ttu-id="53353-113">빈을 추가 하는 경우 **DataGridTableStyle** 개체를 컬렉션에 **DataGridColumnStyle** 개체를 자동으로 생성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="53353-113">When you add an empty **DataGridTableStyle** object to the collection, **DataGridColumnStyle** objects are automatically generated for you.</span></span> <span data-ttu-id="53353-114">새로 추가 하려고 하면 예외가 throw 될 따라서 **DataGridColumnStyle** 중복을 사용 하 여 개체 **MappingName** 값을 **GridColumnStylesCollection**개체입니다.</span><span class="sxs-lookup"><span data-stu-id="53353-114">Consequently, an exception will be thrown if you try to add new **DataGridColumnStyle** objects with duplicate **MappingName** values to the **GridColumnStylesCollection** object.</span></span>  
  
2.  <span data-ttu-id="53353-115">새 테이블 스타일을 선언 하 고 해당 매핑을 이름을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="53353-115">Declare a new table style and set its mapping name.</span></span>  
  
    ```vb  
    Dim ts1 As New DataGridTableStyle()  
    ts1.MappingName = "Customers"  
    ```  
  
    ```csharp  
    DataGridTableStyle ts1 = new DataGridTableStyle();  
    ts1.MappingName = "Customers";  
    ```  
  
    ```cpp  
    DataGridTableStyle* ts1 = new DataGridTableStyle();  
    ts1->MappingName = S"Customers";  
    ```  
  
3.  <span data-ttu-id="53353-116">새 열 스타일을 선언 하 고 해당 매핑 이름 및 기타 속성을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="53353-116">Declare a new column style and set its mapping name and other properties.</span></span>  
  
    ```vb  
    Dim myDataCol As New DataGridBoolColumn()  
    myDataCol.HeaderText = "My New Column"  
    myDataCol.MappingName = "Current"  
    ```  
  
    ```csharp  
    DataGridBoolColumn myDataCol = new DataGridBoolColumn();  
    myDataCol.HeaderText = "My New Column";  
    myDataCol.MappingName = "Current";  
    ```  
  
    ```cpp  
    DataGridBoolColumn^ myDataCol = gcnew DataGridBoolColumn();  
    myDataCol->HeaderText = "My New Column";  
    myDataCol->MappingName = "Current";  
    ```  
  
4.  <span data-ttu-id="53353-117">호출을 **추가** 메서드는 **GridColumnStylesCollection** 열 테이블 스타일을 추가 하는 개체</span><span class="sxs-lookup"><span data-stu-id="53353-117">Call the **Add** method of the **GridColumnStylesCollection** object to add the column to the table style</span></span>  
  
    ```vb  
    ts1.GridColumnStyles.Add(myDataCol)  
    ```  
  
    ```csharp  
    ts1.GridColumnStyles.Add(myDataCol);  
    ```  
  
    ```cpp  
    ts1->GridColumnStyles->Add(myDataCol);  
    ```  
  
5.  <span data-ttu-id="53353-118">호출을 **추가** 메서드는 **GridTableStylesCollection** 데이터 표에 테이블 스타일을 추가 하는 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="53353-118">Call the **Add** method of the **GridTableStylesCollection** object to add the table style to the data grid.</span></span>  
  
    ```vb  
    DataGrid1.TableStyles.Add(ts1)  
    ```  
  
    ```csharp  
    dataGrid1.TableStyles.Add(ts1);  
    ```  
  
    ```cpp  
    dataGrid1->TableStyles->Add(ts1);  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="53353-119">참고자료</span><span class="sxs-lookup"><span data-stu-id="53353-119">See also</span></span>
- [<span data-ttu-id="53353-120">DataGrid 컨트롤</span><span class="sxs-lookup"><span data-stu-id="53353-120">DataGrid Control</span></span>](../../../../docs/framework/winforms/controls/datagrid-control-windows-forms.md)
- [<span data-ttu-id="53353-121">방법: Windows Forms DataGrid 컨트롤에서 열 숨기기 또는 삭제</span><span class="sxs-lookup"><span data-stu-id="53353-121">How to: Delete or Hide Columns in the Windows Forms DataGrid Control</span></span>](../../../../docs/framework/winforms/controls/how-to-delete-or-hide-columns-in-the-windows-forms-datagrid-control.md)
