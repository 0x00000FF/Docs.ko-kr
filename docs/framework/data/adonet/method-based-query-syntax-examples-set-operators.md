---
title: '메서드 기반 쿼리 구문 예제: 집합 연산자(LINQ to DataSet)'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: fa93af15-28af-4b5e-846b-897308410edb
ms.openlocfilehash: 48aa6044f39be93f144b6c4af5137b131dda0b30
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59085820"
---
# <a name="method-based-query-syntax-examples-set-operators-linq-to-dataset"></a>메서드 기반 쿼리 구문 예제: 집합 연산자(LINQ to DataSet)
이 항목의 예제에 사용 하는 방법을 보여 줍니다 합니다 <xref:System.Linq.Enumerable.Distinct%2A>, <xref:System.Linq.Enumerable.Except%2A>를 <xref:System.Linq.Enumerable.Intersect%2A>, 및 <xref:System.Linq.Enumerable.Union%2A> 데이터 행 집합에 대해 값 기반 비교 연산을 수행 하는 연산자입니다.[ 데이터에는 데이터 집합 로드](../../../../docs/framework/data/adonet/loading-data-into-a-dataset.md) 참조 [Datarow 비교](../../../../docs/framework/data/adonet/comparing-datarows-linq-to-dataset.md) 대 한 자세한 내용은 <xref:System.Data.DataRowComparer>합니다.  
  
 합니다 `FillDataSet` 에이 예제에서 사용 하는 방법이 지정 되어 [는 DataSet에 데이터 로드](../../../../docs/framework/data/adonet/loading-data-into-a-dataset.md)합니다.  
  
 이 항목의 예제에서는 AdventureWorks 샘플 데이터베이스의 Contact, Address, Product, SalesOrderHeader 및 SalesOrderDetail 테이블을 사용합니다.  
  
 이 항목의 예제에서는 다음을 사용 `using` / `Imports` 문:  
  
 [!code-csharp[DP LINQ to DataSet Examples#ImportsUsing](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#importsusing)]
 [!code-vb[DP LINQ to DataSet Examples#ImportsUsing](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#importsusing)]  
  
 자세한 내용은 [방법: Visual Studio에서 LINQ to DataSet 프로젝트 만들기](../../../../docs/framework/data/adonet/how-to-create-a-linq-to-dataset-project-in-vs.md)합니다.  
  
## <a name="distinct"></a>Distinct  
  
### <a name="example"></a>예제  
 이 예제에서는 <xref:System.Linq.Enumerable.Distinct%2A> 메서드를 사용하여 시퀀스의 중복 요소를 제거합니다.  
  
 [!code-csharp[DP LINQ to DataSet Examples#DistinctRows](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#distinctrows)]
 [!code-vb[DP LINQ to DataSet Examples#DistinctRows](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#distinctrows)]  
  
## <a name="except"></a>Except  
  
### <a name="example"></a>예제  
 이 예제에서는 <xref:System.Linq.Enumerable.Except%2A> 메서드를 사용하여 첫 번째 테이블에만 있고 두 번째 테이블에는 없는 연락처를 반환합니다.  
  
 [!code-csharp[DP LINQ to DataSet Examples#Except2](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#except2)]
 [!code-vb[DP LINQ to DataSet Examples#Except2](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#except2)]  
  
## <a name="intersect"></a>Intersect  
  
### <a name="example"></a>예제  
 이 예제에서는 <xref:System.Linq.Enumerable.Intersect%2A> 메서드를 사용하여 두 테이블 모두에 있는 연락처를 반환합니다.  
  
 [!code-csharp[DP LINQ to DataSet Examples#Intersect2](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#intersect2)]
 [!code-vb[DP LINQ to DataSet Examples#Intersect2](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#intersect2)]  
  
## <a name="union"></a>Union  
  
### <a name="example"></a>예제  
 이 예제에서는 <xref:System.Linq.Enumerable.Union%2A> 메서드를 사용하여 두 테이블 중 한 테이블에만 있는 고유 연락처를 반환합니다.  
  
 [!code-csharp[DP LINQ to DataSet Examples#Union2](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#union2)]
 [!code-vb[DP LINQ to DataSet Examples#Union2](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#union2)]  
  
## <a name="see-also"></a>참고자료

- [데이터를 데이터 집합에 로드](../../../../docs/framework/data/adonet/loading-data-into-a-dataset.md)
- [LINQ to DataSet 예제](../../../../docs/framework/data/adonet/linq-to-dataset-examples.md)
- [표준 쿼리 연산자 개요(C#)](../../../csharp/programming-guide/concepts/linq/standard-query-operators-overview.md)
- [표준 쿼리 연산자 개요 (Visual Basic)](../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md)
