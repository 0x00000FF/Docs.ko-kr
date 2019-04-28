---
title: 데이터 보기 관리
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 0b67fab5-1722-4d2b-bfc1-247a75f0f1ee
ms.openlocfilehash: df03c68193a1068b4bdf0b6ed0923b3bbb8a046a
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61785413"
---
# <a name="managing-dataviews"></a><span data-ttu-id="0e6ce-102">데이터 보기 관리</span><span class="sxs-lookup"><span data-stu-id="0e6ce-102">Managing DataViews</span></span>
<span data-ttu-id="0e6ce-103"><xref:System.Data.DataViewManager>를 사용하여 <xref:System.Data.DataView>의 모든 테이블에 대한 뷰 설정을 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0e6ce-103">You can use a <xref:System.Data.DataViewManager> to manage view settings for all the tables in a <xref:System.Data.DataView>.</span></span> <span data-ttu-id="0e6ce-104">여러 테이블에 바인딩하려는 컨트롤에 있는 경우 그리드와 같은 관계를 탐색 하는 **DataViewManager** 적합 합니다.</span><span class="sxs-lookup"><span data-stu-id="0e6ce-104">If you have a control that you want to bind to multiple tables, such as a grid that navigates relationships, a **DataViewManager** is ideal.</span></span>  
  
 <span data-ttu-id="0e6ce-105">합니다 **DataViewManager** 의 컬렉션을 포함 <xref:System.Data.DataViewSetting> 의 테이블 뷰를 설정 하는 데 사용 되는 개체는 <xref:System.Data.DataSet>합니다.</span><span class="sxs-lookup"><span data-stu-id="0e6ce-105">The **DataViewManager** contains a collection of <xref:System.Data.DataViewSetting> objects that are used to set the view setting of the tables in the <xref:System.Data.DataSet>.</span></span> <span data-ttu-id="0e6ce-106">합니다 <xref:System.Data.DataViewSettingCollection> 하나가 포함 되어 있습니다 <xref:System.Data.DataViewSetting> 의 각 테이블에 대 한 개체를 **데이터 집합**합니다.</span><span class="sxs-lookup"><span data-stu-id="0e6ce-106">The <xref:System.Data.DataViewSettingCollection> contains one <xref:System.Data.DataViewSetting> object for each table in a **DataSet**.</span></span> <span data-ttu-id="0e6ce-107">기본값을 설정할 수 있습니다 **ApplyDefaultSort**를 **정렬**합니다 **RowFilter**, 및 **RowStateFilter** 하면 참조 된 테이블의 속성 사용 하 여 해당 **DataViewSetting**합니다.</span><span class="sxs-lookup"><span data-stu-id="0e6ce-107">You can set the default **ApplyDefaultSort**, **Sort**, **RowFilter**, and **RowStateFilter** properties of the referenced table by using its **DataViewSetting**.</span></span> <span data-ttu-id="0e6ce-108">참조할 수 있습니다 합니다 **DataViewSetting** 이름 또는 서 수 참조 또는 해당 특정 테이블 개체에 대 한 참조를 전달 하 여 특정 테이블에 대 한 합니다.</span><span class="sxs-lookup"><span data-stu-id="0e6ce-108">You can reference the **DataViewSetting** for a particular table by name or ordinal reference, or by passing a reference to that specific table object.</span></span> <span data-ttu-id="0e6ce-109">컬렉션에 액세스할 수 있습니다 **DataViewSetting** 개체를 **DataViewManager** 사용 하 여 합니다 **Dataviewsetting** 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="0e6ce-109">You can access the collection of **DataViewSetting** objects in a **DataViewManager** by using the **DataViewSettings** property.</span></span>  
  
 <span data-ttu-id="0e6ce-110">다음 코드 예에서는 채우기는 **데이터 집합** SQL Server를 사용 하 여 **Northwind** 데이터베이스 테이블 **고객**를 **주문**, 및  **Order Details**테이블 간의 관계를 생성, 사용 하는 **DataViewManager** 기본 설정 하 **DataView** 설정과 바인딩을 **DataGrid**  에 **DataViewManager**합니다.</span><span class="sxs-lookup"><span data-stu-id="0e6ce-110">The following code example fills a **DataSet** with the SQL Server **Northwind** database tables **Customers**, **Orders**, and **Order Details**, creates the relationships between the tables, uses a **DataViewManager** to set default **DataView** settings, and binds a **DataGrid** to the **DataViewManager**.</span></span> <span data-ttu-id="0e6ce-111">기본값을 설정 하는 예제 **DataView** 의 모든 테이블에 대 한 설정을 합니다 **데이터 집합** 테이블의 기본 키로 정렬 (**ApplyDefaultSort**  =  **true**)의 정렬 순서를 수정 하는 **고객** 기준으로 정렬 하려면 테이블 **CompanyName**합니다.</span><span class="sxs-lookup"><span data-stu-id="0e6ce-111">The example sets the default **DataView** settings for all tables in the **DataSet** to sort by the primary key of the table (**ApplyDefaultSort** = **true**), and then modifies the sort order of the **Customers** table to sort by **CompanyName**.</span></span>  
  
```vb  
' Assumes connection is a valid SqlConnection to Northwind.  
' Create a Connection, DataAdapters, and a DataSet.  
Dim custDA As SqlDataAdapter = New SqlDataAdapter( _  
  "SELECT CustomerID, CompanyName FROM Customers", connection)  
Dim orderDA As SqlDataAdapter = New SqlDataAdapter( _  
  "SELECT OrderID, CustomerID FROM Orders", connection)  
Dim ordDetDA As SqlDataAdapter = New SqlDataAdapter( _  
  "SELECT OrderID, ProductID, Quantity FROM [Order Details]", connection)  
  
Dim custDS As DataSet = New DataSet()  
  
' Open the Connection.  
connection.Open()  
  
    ' Fill the DataSet with schema information and data.  
    custDA.MissingSchemaAction = MissingSchemaAction.AddWithKey  
    orderDA.MissingSchemaAction = MissingSchemaAction.AddWithKey  
    ordDetDA.MissingSchemaAction = MissingSchemaAction.AddWithKey  
  
    custDA.Fill(custDS, "Customers")  
    orderDA.Fill(custDS, "Orders")  
    ordDetDA.Fill(custDS, "OrderDetails")  
  
    ' Close the Connection.  
    connection.Close()  
  
    ' Create relationships.  
    custDS.Relations.Add("CustomerOrders", _  
          custDS.Tables("Customers").Columns("CustomerID"), _  
          custDS.Tables("Orders").Columns("CustomerID"))  
  
    custDS.Relations.Add("OrderDetails", _  
          custDS.Tables("Orders").Columns("OrderID"), _  
          custDS.Tables("OrderDetails").Columns("OrderID"))  
  
' Create default DataView settings.  
Dim viewManager As DataViewManager = New DataViewManager(custDS)  
  
Dim viewSetting As DataViewSetting  
For Each viewSetting In viewManager.DataViewSettings  
  viewSetting.ApplyDefaultSort = True  
Next  
  
viewManager.DataViewSettings("Customers").Sort = "CompanyName"  
  
' Bind to a DataGrid.  
Dim grid As System.Windows.Forms.DataGrid = New System.Windows.Forms.DataGrid()  
grid.SetDataBinding(viewManager, "Customers")  
```  
  
```csharp  
// Assumes connection is a valid SqlConnection to Northwind.  
// Create a Connection, DataAdapters, and a DataSet.  
SqlDataAdapter custDA = new SqlDataAdapter(  
  "SELECT CustomerID, CompanyName FROM Customers", connection);  
SqlDataAdapter orderDA = new SqlDataAdapter(  
  "SELECT OrderID, CustomerID FROM Orders", connection);  
SqlDataAdapter ordDetDA = new SqlDataAdapter(  
  "SELECT OrderID, ProductID, Quantity FROM [Order Details]", connection);  
  
DataSet custDS = new DataSet();  
  
// Open the Connection.  
connection.Open();  
  
    // Fill the DataSet with schema information and data.  
    custDA.MissingSchemaAction = MissingSchemaAction.AddWithKey;  
    orderDA.MissingSchemaAction = MissingSchemaAction.AddWithKey;  
    ordDetDA.MissingSchemaAction = MissingSchemaAction.AddWithKey;  
  
    custDA.Fill(custDS, "Customers");  
    orderDA.Fill(custDS, "Orders");  
    ordDetDA.Fill(custDS, "OrderDetails");  
  
    // Close the Connection.  
    connection.Close();  
  
    // Create relationships.  
    custDS.Relations.Add("CustomerOrders",  
          custDS.Tables["Customers"].Columns["CustomerID"],  
          custDS.Tables["Orders"].Columns["CustomerID"]);  
  
    custDS.Relations.Add("OrderDetails",  
          custDS.Tables["Orders"].Columns["OrderID"],  
          custDS.Tables["OrderDetails"].Columns["OrderID"]);  
  
// Create default DataView settings.  
DataViewManager viewManager = new DataViewManager(custDS);  
  
foreach (DataViewSetting viewSetting in viewManager.DataViewSettings)  
  viewSetting.ApplyDefaultSort = true;  
  
viewManager.DataViewSettings["Customers"].Sort = "CompanyName";  
  
// Bind to a DataGrid.  
System.Windows.Forms.DataGrid grid = new System.Windows.Forms.DataGrid();  
grid.SetDataBinding(viewManager, "Customers");  
```  
  
## <a name="see-also"></a><span data-ttu-id="0e6ce-112">참고자료</span><span class="sxs-lookup"><span data-stu-id="0e6ce-112">See also</span></span>

- <xref:System.Data.DataSet>
- <xref:System.Data.DataViewManager>
- <xref:System.Data.DataViewSetting>
- <xref:System.Data.DataViewSettingCollection>
- [<span data-ttu-id="0e6ce-113">DataView</span><span class="sxs-lookup"><span data-stu-id="0e6ce-113">DataViews</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/dataviews.md)
- [<span data-ttu-id="0e6ce-114">ADO.NET 관리되는 공급자 및 데이터 집합 개발자 센터</span><span class="sxs-lookup"><span data-stu-id="0e6ce-114">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
