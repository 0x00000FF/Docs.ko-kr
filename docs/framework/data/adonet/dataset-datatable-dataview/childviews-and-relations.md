---
title: ChildView 및 관계
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: d475d356-6abb-4701-8fd1-2906fb93dfba
ms.openlocfilehash: e27ef72f0341524524a8f267eeeb13a6f46deb52
ms.sourcegitcommit: 700b9003ea6bdd83a53458bbc436c9b5778344f1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/03/2018
ms.locfileid: "48261169"
---
# <a name="childviews-and-relations"></a><span data-ttu-id="bdb66-102">ChildView 및 관계</span><span class="sxs-lookup"><span data-stu-id="bdb66-102">ChildViews and Relations</span></span>
<span data-ttu-id="bdb66-103"><xref:System.Data.DataSet>의 테이블 사이에 관계가 존재하는 경우 부모 테이블의 행에 대한 <xref:System.Data.DataView>의 <xref:System.Data.DataRowView.CreateChildView%2A> 메서드를 사용하여 관련 자식 테이블의 행이 포함된 <xref:System.Data.DataRowView>를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bdb66-103">If a relationship exists between tables in a <xref:System.Data.DataSet>, you can create a <xref:System.Data.DataView> containing rows from the related child table by using the <xref:System.Data.DataRowView.CreateChildView%2A> method of the <xref:System.Data.DataRowView> for the rows in the parent table.</span></span> <span data-ttu-id="bdb66-104">예를 들어, 다음 코드에서는 **범주** 및 해당 관련 **제품** 사전순으로 정렬 **CategoryName** 고 **ProductName** .</span><span class="sxs-lookup"><span data-stu-id="bdb66-104">For example, the following code displays **Categories** and their related **Products** in alphabetical order sorted by **CategoryName** and **ProductName**.</span></span>  
  
```vb  
Dim catTable As DataTable = catDS.Tables("Categories")  
Dim prodTable As DataTable = catDS.Tables("Products")  
  
' Create a relation between the Categories and Products tables.  
Dim relation As DataRelation = catDS.Relations.Add("CatProdRel", _  
  catTable.Columns("CategoryID"), _  
  prodTable.Columns("CategoryID"))  
  
' Create DataViews for the Categories and Products tables.  
Dim catView As DataView = New DataView(catTable, "", _  
  "CategoryName", DataViewRowState.CurrentRows)  
Dim prodView As DataView  
  
' Iterate through the Categories table.  
Dim catDRV, prodDRV As DataRowView  
  
For Each catDRV In catView  
  Console.WriteLine(catDRV("CategoryName"))  
  
  ' Create a DataView of the child product records.  
  prodView = catDRV.CreateChildView(relation)  
  prodView.Sort = "ProductName"  
  
  For Each prodDRV In prodView  
    Console.WriteLine(vbTab & prodDRV("ProductName"))  
  Next  
Next  
```  
  
```csharp  
DataTable catTable = catDS.Tables["Categories"];  
DataTable prodTable = catDS.Tables["Products"];  
  
// Create a relation between the Categories and Products tables.  
DataRelation relation = catDS.Relations.Add("CatProdRel",   
  catTable.Columns["CategoryID"],  
                                                            prodTable.Columns["CategoryID"]);  
  
// Create DataViews for the Categories and Products tables.  
DataView catView = new DataView(catTable, "", "CategoryName",   
  DataViewRowState.CurrentRows);  
DataView prodView;  
  
// Iterate through the Categories table.  
foreach (DataRowView catDRV in catView)  
{  
  Console.WriteLine(catDRV["CategoryName"]);  
  
  // Create a DataView of the child product records.  
  prodView = catDRV.CreateChildView(relation);  
  prodView.Sort = "ProductName";  
  
  foreach (DataRowView prodDRV in prodView)  
    Console.WriteLine("\t" + prodDRV["ProductName"]);  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="bdb66-105">참고 항목</span><span class="sxs-lookup"><span data-stu-id="bdb66-105">See Also</span></span>  
 <xref:System.Data.DataSet>  
 <xref:System.Data.DataView>  
 <xref:System.Data.DataRowView>  
 [<span data-ttu-id="bdb66-106">DataView</span><span class="sxs-lookup"><span data-stu-id="bdb66-106">DataViews</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/dataviews.md)  
 [<span data-ttu-id="bdb66-107">ADO.NET 관리되는 공급자 및 데이터 집합 개발자 센터</span><span class="sxs-lookup"><span data-stu-id="bdb66-107">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
