---
title: 기본 키 정의
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 2ea85959-e763-4669-8bd9-46a9dab894bd
ms.openlocfilehash: aecd16357857dca7393eac879159c916d8cf8ac7
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/04/2018
ms.locfileid: "43520220"
---
# <a name="defining-primary-keys"></a>기본 키 정의
일반적으로 데이터베이스 테이블에는 테이블의 각 행을 고유하게 식별하는 열 또는 열 그룹이 있습니다. 이 식별 열 또는 열 그룹을 기본 키라고 합니다.  
  
 단일 식별 되는 경우 <xref:System.Data.DataColumn> 으로 <xref:System.Data.DataTable.PrimaryKey%2A> 에 대 한를 <xref:System.Data.DataTable>, 테이블을 자동으로 설정 합니다 <xref:System.Data.DataColumn.AllowDBNull%2A> 열의 속성 **false** 및 <xref:System.Data.DataColumn.Unique%2A> 속성을  **true**합니다. 여러 개의 열 기본 키의 경우에 **AllowDBNull** 속성으로 자동 설정 됩니다 **false**합니다.  
  
 **PrimaryKey** 의 속성을 <xref:System.Data.DataTable> 하나 이상의 배열 값으로 받습니다 **DataColumn** 다음 예와에서 같이 개체입니다. 첫 번째 예제에서는 단일 열이 기본 키로 정의됩니다.  
  
```vb  
workTable.PrimaryKey = New DataColumn() {workTable.Columns("CustID")}  
  
' Or  
  
Dim columns(1) As DataColumn  
columns(0) = workTable.Columns("CustID")  
workTable.PrimaryKey = columns  
```  
  
```csharp  
workTable.PrimaryKey = new DataColumn[] {workTable.Columns["CustID"]};  
  
// Or  
  
DataColumn[] columns = new DataColumn[1];  
columns[0] = workTable.Columns["CustID"];  
workTable.PrimaryKey = columns;  
```  
  
 다음 예제에서는 두 열이 기본 키로 정의됩니다.  
  
```vb  
workTable.PrimaryKey = New DataColumn() {workTable.Columns("CustLName"), _  
                                         workTable.Columns("CustFName")}  
  
' Or  
  
Dim keyColumn(2) As DataColumn  
keyColumn(0) = workTable.Columns("CustLName")  
keyColumn(1) = workTable.Columns("CustFName")  
workTable.PrimaryKey = keyColumn  
```  
  
```csharp  
workTable.PrimaryKey = new DataColumn[] {workTable.Columns["CustLName"],   
                                         workTable.Columns["CustFName"]};  
  
// Or  
  
DataColumn[] keyColumn = new DataColumn[2];  
keyColumn[0] = workTable.Columns["CustLName"];  
keyColumn[1] = workTable.Columns["CustFName"];  
workTable.PrimaryKey = keyColumn;  
```  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Data.DataTable>  
 [DataTable 스키마 정의](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/datatable-schema-definition.md)  
 [DataTable](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/datatables.md)  
 [ADO.NET 관리되는 공급자 및 데이터 집합 개발자 센터](https://go.microsoft.com/fwlink/?LinkId=217917)
