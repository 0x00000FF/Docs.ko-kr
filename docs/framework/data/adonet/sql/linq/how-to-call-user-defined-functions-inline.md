---
title: "방법: 사용자 정의 함수를 인라인으로 호출 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: f80d4327-b6a5-4aa8-a743-e95d09a2a02e
caps.latest.revision: 2
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 2
---
# 방법: 사용자 정의 함수를 인라인으로 호출
사용자 정의 함수를 인라인으로 호출할 수 있지만 실행이 지연된 쿼리에 포함된 함수는 쿼리가 실행될 때까지 실행되지 않습니다.  자세한 내용은 [Introduction to LINQ Queries \(C\#\)](../Topic/Introduction%20to%20LINQ%20Queries%20\(C%23\).md)을 참조하세요.  
  
 쿼리 외부에 있는 동일한 함수를 호출할 경우 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]에서는 메서드 호출 식에서 단순한 쿼리를 만듭니다.  다음은 전달된 상수에 매개 변수 `@p0`가 바인딩되는 SQL 구문입니다.  
  
```  
SELECT dbo.ReverseCustName(@p0)  
```  
  
 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]에서는 다음을 만듭니다.  
  
 [!code-csharp[DLinqUDFS#4](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqUDFS/cs/Program.cs#4)]
 [!code-vb[DLinqUDFS#4](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqUDFS/vb/Module1.vb#4)]  
  
## 예제  
 다음 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] 쿼리에서 생성된 사용자 정의 함수 메서드 `ReverseCustName`에 대한 인라인 호출을 볼 수 있습니다.  쿼리 실행이 지연되었기에 함수는 즉시 실행되지 않습니다.  이 쿼리에 대해 빌드된 SQL은 데이터베이스에서 사용자 정의 함수에 대한 호출로 변환됩니다. 다음 쿼리의 SQL 코드를 참조하세요.  
  
 [!code-csharp[DLinqUDFS#5](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqUDFS/cs/Program.cs#5)]
 [!code-vb[DLinqUDFS#5](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqUDFS/vb/Module1.vb#5)]  
  
```  
SELECT [t0].[ContactName],  
    dbo.ReverseCustName([t0].[ContactTitle]) AS [Title]  
FROM [Customers] AS [t0]  
```  
  
## 참고 항목  
 [사용자 정의 함수](../../../../../../docs/framework/data/adonet/sql/linq/user-defined-functions.md)