---
title: "메서드 기반 쿼리 예제(LINQ to DataSet) | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: d340775c-7f39-4087-a290-5cbec6cfa68e
caps.latest.revision: 2
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 2
---
# 메서드 기반 쿼리 예제(LINQ to DataSet)
이 단원에서는 표준 쿼리 연산자를 사용하는 메서드 기반 쿼리 구문으로 작성된 [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] 프로그래밍 예제를 제공합니다.  이러한 예제에 사용된 <xref:System.Data.DataSet>은 [DataSet에 데이터 로드](../../../../docs/framework/data/adonet/loading-data-into-a-dataset.md)에 설명된 `FillDataSet` 메서드를 사용하여 채웁니다.  자세한 내용은 [Standard Query Operators Overview](../../../../ocs/visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md)을 참조하세요.  
  
## 단원 내용  
 [프로젝션](../../../../docs/framework/data/adonet/method-based-query-syntax-examples-projection.md)  
 이 항목의 예제에서는 <xref:System.Linq.Enumerable.Select%2A> 및 <xref:System.Linq.Enumerable.SelectMany%2A> 메서드를 사용하여 <xref:System.Data.DataSet>을 쿼리하는 방법을 보여 줍니다.  
  
 [분할](../../../../docs/framework/data/adonet/method-based-query-syntax-examples-partitioning-linq.md)  
 이 항목의 예제에서는 <xref:System.Linq.Enumerable.Skip%2A> 및 <xref:System.Linq.Enumerable.Take%2A> 메서드를 사용하여 <xref:System.Data.DataSet>을 쿼리하고 결과를 분할하는 방법을 보여 줍니다.  
  
 [정렬](../../../../docs/framework/data/adonet/method-based-query-syntax-examples-ordering-linq-to-dataset.md)  
 이 항목의 예제에서는 <xref:System.Linq.Enumerable.OrderBy%2A>, <xref:System.Linq.Enumerable.OrderByDescending%2A>, <xref:System.Linq.Enumerable.Reverse%2A> 및 <xref:System.Linq.Enumerable.ThenByDescending%2A> 메서드를 사용하여 <xref:System.Data.DataSet>을 쿼리하고 결과를 정렬하는 방법을 보여 줍니다.  
  
 [집합 연산자](../../../../docs/framework/data/adonet/method-based-query-syntax-examples-set-operators.md)  
 이 항목의 예제에서는 <xref:System.Linq.Enumerable.Distinct%2A>, <xref:System.Linq.Enumerable.Except%2A>, <xref:System.Linq.Enumerable.Intersect%2A> 및 <xref:System.Linq.Enumerable.Union%2A> 연산자를 사용하여 데이터 행 집합에 대해 값 기반 비교 연산을 수행하는 방법을 보여 줍니다.  
  
 [변환 연산자](../../../../docs/framework/data/adonet/method-based-query-syntax-examples-conversion-operators.md)  
 이 항목의 예제에서는 <xref:System.Linq.Enumerable.ToArray%2A>, <xref:System.Linq.Enumerable.ToDictionary%2A> 및 <xref:System.Linq.Enumerable.ToList%2A> 메서드를 사용하여 쿼리 식을 즉시 실행하는 방법을 보여 줍니다.  
  
 [요소 연산자](../../../../docs/framework/data/adonet/method-based-query-syntax-examples-element-operators.md)  
 이 항목의 예제에서는 <xref:System.Linq.Enumerable.First%2A> 및 <xref:System.Linq.Enumerable.ElementAt%2A> 메서드를 사용하여 <xref:System.Data.DataSet>에서 <xref:System.Data.DataRow> 요소를 가져오는 방법을 보여 줍니다.  
  
 [집계 연산자](../../../../docs/framework/data/adonet/method-based-query-syntax-examples-aggregate-operators.md)  
 이 항목의 예제에서는 <xref:System.Linq.Enumerable.Average%2A>, <xref:System.Linq.Enumerable.Count%2A>, <xref:System.Linq.Enumerable.Max%2A>, <xref:System.Linq.Enumerable.Min%2A> 및 <xref:System.Linq.Enumerable.Sum%2A> 메서드를 사용하여 <xref:System.Data.DataSet>을 쿼리하고 데이터를 집계하는 방법을 보여 줍니다.  
  
 [조인](../../../../docs/framework/data/adonet/method-based-query-syntax-examples-join-linq-to-dataset.md)  
 이 항목의 예제에서는 <xref:System.Linq.Enumerable.GroupJoin%2A> 및 <xref:System.Linq.Enumerable.Join%2A> 메서드를 사용하여 <xref:System.Data.DataSet>을 쿼리하는 방법을 보여 줍니다.  
  
## 참고 항목  
 [쿼리 식 예제](../../../../docs/framework/data/adonet/query-expression-examples-linq-to-dataset.md)   
 [DataSet 관련 연산자 예제](../../../../docs/framework/data/adonet/dataset-specific-operator-examples-linq-to-dataset.md)   
 [LINQ to DataSet 예제](../../../../docs/framework/data/adonet/linq-to-dataset-examples.md)