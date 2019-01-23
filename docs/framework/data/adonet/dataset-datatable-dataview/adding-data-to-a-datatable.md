---
title: DataTable에 데이터 추가
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: d6aa8474-7bde-48f7-949d-20dc38a1625b
ms.openlocfilehash: adf2378cead054efcef10a73bfd00ef541940949
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54494122"
---
# <a name="adding-data-to-a-datatable"></a>DataTable에 데이터 추가
<xref:System.Data.DataTable>을 만들고 열 및 제약 조건을 사용하여 해당 테이블의 구조를 정의한 후에는 새 데이터 행을 테이블에 추가할 수 있습니다. 새 행을 추가하려면 새 변수의 형식을 <xref:System.Data.DataRow>로 선언합니다. 새 **DataRow** 를 호출 하면 개체가 반환 되는 <xref:System.Data.DataTable.NewRow%2A> 메서드. **DataTable** 만듭니다 합니다 **DataRow** 개체에 정의 된 대로 테이블의 구조를 기반 합니다 <xref:System.Data.DataColumnCollection>합니다.  
  
 다음 예제에서는 호출 하 여 새 행을 만들 하는 방법에 설명 합니다 **NewRow** 메서드.  
  
```vb  
Dim workRow As DataRow = workTable.NewRow()  
```  
  
```csharp  
DataRow workRow = workTable.NewRow();  
```  
  
 그러면 다음 예제와 같이 인덱스나 열 이름을 사용하여 새로 추가된 행을 조작할 수 있습니다.  
  
```vb  
workRow("CustLName") = "Smith"  
workRow(1) = "Smith"  
```  
  
```csharp  
workRow["CustLName"] = "Smith";  
workRow[1] = "Smith";  
```  
  
 데이터가 새 행을 삽입 한 후 합니다 **추가** 메서드는 행을 추가할 데는 <xref:System.Data.DataRowCollection>다음 코드에 표시 된 합니다.  
  
```vb  
workTable.Rows.Add(workRow)  
```  
  
```csharp  
workTable.Rows.Add(workRow);  
```  
  
 호출할 수도 있습니다는 **추가** 로 형식화 된 값의 배열 전달 하 여 새 행을 추가 하는 방법 <xref:System.Object>다음 예제에서와 같이 합니다.  
  
```vb  
workTable.Rows.Add(new Object() {1, "Smith"})  
```  
  
```csharp  
workTable.Rows.Add(new Object[] {1, "Smith"});  
```  
  
 형식의 값 배열을 전달 **개체**에 **추가** 메서드 테이블 내에서 새 행을 만들고 개체 배열 값에 해당 열 값을 설정 합니다. 배열 값은 테이블에 나타나는 순서에 따라 해당 열과 순서대로 대응합니다.  
  
 다음 예제에서는 새로 만든에 10 개의 행을 추가 **고객** 테이블입니다.  
  
```vb  
Dim workRow As DataRow  
Dim i As Integer  
  
For i = 0 To 9  
  workRow = workTable.NewRow()  
  workRow(0) = i  
  workRow(1) = "CustName" & I.ToString()  
  workTable.Rows.Add(workRow)  
Next  
```  
  
```csharp  
DataRow workRow;  
  
for (int i = 0; i <= 9; i++)   
{  
  workRow = workTable.NewRow();  
  workRow[0] = i;  
  workRow[1] = "CustName" + i.ToString();  
  workTable.Rows.Add(workRow);  
}  
```  
  
## <a name="see-also"></a>참고자료
- <xref:System.Data.DataColumnCollection>
- <xref:System.Data.DataRow>
- <xref:System.Data.DataRowCollection>
- <xref:System.Data.DataTable>
- [DataTable에서 데이터 조작](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/manipulating-data-in-a-datatable.md)
- [ADO.NET 관리되는 공급자 및 데이터 집합 개발자 센터](https://go.microsoft.com/fwlink/?LinkId=217917)
