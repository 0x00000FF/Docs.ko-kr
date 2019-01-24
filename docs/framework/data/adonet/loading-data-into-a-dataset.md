---
title: 데이터를 데이터 집합에 로드
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: a53e5dc1-9669-49d4-828d-efa633237066
ms.openlocfilehash: 0f50638beb50220d06daef7bbd6002b319a92476
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54622964"
---
# <a name="loading-data-into-a-dataset"></a>데이터를 데이터 집합에 로드
<xref:System.Data.DataSet> 개체를 먼저 채워야 [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)]을 사용하여 해당 개체를 쿼리할 수 있습니다. <xref:System.Data.DataSet>은 여러 방법으로 채울 수 있습니다. 예를 들어, [!INCLUDE[vbtecdlinq](../../../../includes/vbtecdlinq-md.md)]를 사용하여 데이터베이스를 쿼리한 다음 그 결과를 <xref:System.Data.DataSet>에 로드할 수 있습니다. 자세한 내용은 [LINQ to SQL](../../../../docs/framework/data/adonet/sql/linq/index.md)을 참조하세요.  
  
 <xref:System.Data.DataSet>에 데이터를 로드하는 일반적인 방법 중에는 <xref:System.Data.Common.DataAdapter> 클래스를 사용하여 데이터베이스에서 데이터를 검색하는 방법도 있습니다. 다음 예제에서 이 방법을 보여 줍니다.  
  
## <a name="example"></a>예제  
 이 예제에서는 <xref:System.Data.Common.DataAdapter>를 사용하여 AdventureWorks 데이터베이스에서 2002년 판매 정보를 쿼리한 다음 그 결과를 <xref:System.Data.DataSet>에 로드합니다. <xref:System.Data.DataSet>이 채워지면 [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)]을 사용하여 쿼리를 다시 작성할 수 있습니다. 합니다 `FillDataSet` 의 예제에서는 쿼리에서이 예제의 메서드를 사용 하는 [LINQ to DataSet 예제](../../../../docs/framework/data/adonet/linq-to-dataset-examples.md)합니다. 자세한 내용은 [데이터 집합 쿼리](../../../../docs/framework/data/adonet/querying-datasets-linq-to-dataset.md)합니다.  
  
 [!code-csharp[DP LINQ to DataSet Examples#FillDataSet](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#filldataset)]
 [!code-vb[DP LINQ to DataSet Examples#FillDataSet](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#filldataset)]  
  
## <a name="see-also"></a>참고자료
- [LINQ to DataSet 개요](../../../../docs/framework/data/adonet/linq-to-dataset-overview.md)
- [데이터 집합 쿼리](../../../../docs/framework/data/adonet/querying-datasets-linq-to-dataset.md)
- [LINQ to DataSet 예제](../../../../docs/framework/data/adonet/linq-to-dataset-examples.md)
