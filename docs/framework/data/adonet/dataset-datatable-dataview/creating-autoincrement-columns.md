---
title: AutoIncrement 열 만들기
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: cf09732a-ab54-4d98-89e2-4d0a1f28fbce
ms.openlocfilehash: 9c6b5393e1928828bca001ba1d2336f09e64c22c
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/04/2018
ms.locfileid: "43536617"
---
# <a name="creating-autoincrement-columns"></a>AutoIncrement 열 만들기
열에 고유 값을 지정하려면 테이블에 새 행을 추가할 때 열 값이 자동으로 증가하도록 설정합니다. 자동 증분 만들려는 <xref:System.Data.DataColumn>로 설정 합니다 <xref:System.Data.DataColumn.AutoIncrement%2A> 열의 속성 **true**합니다. <xref:System.Data.DataColumn> 정의 된 값을 사용 하 여 시작한를 <xref:System.Data.DataColumn.AutoIncrementSeed%2A> 속성을 각 행의 값을 추가 하 고는 **AutoIncrement** 열에 정의 된 값으로 증가 <xref:System.Data.DataColumn.AutoIncrementStep%2A> 열의 속성.  
  
 에 대 한 **AutoIncrement** 좋습니다 열 합니다 <xref:System.Data.DataColumn.ReadOnly%2A> 의 속성을 **DataColumn** 로 설정 **true**.  
  
 다음 예제에서는 200으로 시작하여 3씩 증가하여 추가되는 열을 만드는 방법을 보여 줍니다.  
  
```vb  
Dim workColumn As DataColumn = workTable.Columns.Add( _  
    "CustomerID", typeof(Int32))  
workColumn.AutoIncrement = true  
workColumn.AutoIncrementSeed = 200  
workColumn.AutoIncrementStep = 3  
```  
  
```csharp  
DataColumn workColumn = workTable.Columns.Add(  
    "CustomerID", typeof(Int32));  
workColumn.AutoIncrement = true;  
workColumn.AutoIncrementSeed = 200;  
workColumn.AutoIncrementStep = 3;  
```  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Data.DataColumn>  
 [DataTable 스키마 정의](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/datatable-schema-definition.md)  
 [DataTable](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/datatables.md)  
 [ADO.NET 관리되는 공급자 및 데이터 집합 개발자 센터](https://go.microsoft.com/fwlink/?LinkId=217917)
