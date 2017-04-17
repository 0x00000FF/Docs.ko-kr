---
title: "TOP(Entity SQL) | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "ESQL"
ms.assetid: 4a4a0954-82e2-4eae-bcaf-7c4552f3532d
caps.latest.revision: 3
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 3
---
# TOP(Entity SQL)
SELECT 절에는 선택적인 TOP 하위 절과 선택적인 ALL\/DISTINCT 한정자를 차례로 사용할 수 있습니다. TOP 하위 절은 쿼리 결과에 첫 번째 행 집합만 반환되도록 지정합니다.  
  
## 구문  
  
```  
  
[ TOP (n) ]  
```  
  
## 인수  
 `n`  
 반환할 행의 수를 지정하는 숫자 식입니다.`n`은 단일 숫자 리터럴 또는 단일 매개 변수일 수 있습니다.  
  
## 설명  
 TOP 식은 단일 숫자 리터럴이거나 단일 매개 변수여야 합니다. 상수 리터럴이 사용되는 경우, 리터럴 형식은 Edm.Int64\(바이트. int16, int32, int64이거나 Edm.Int64로 확장 가능한 형식으로 매핑되는 모든 공급자 형식\)로의 암시적 확장이 가능해야 하며 그 값이 0이거나 0보다 커야 합니다. 그렇지 않으면 예외가 발생합니다. 매개 변수가 식으로 사용되는 경우에는 매개 변수 형식도 역시 암시적으로 Edm.Int64로 확장할 수 있어야 합니다. 하지만 매개 변수 값은 런타임에 바인딩되므로 컴파일 과정에서 실제 매개 변수 값에 대한 확인은 이루어지지 않습니다.  
  
 다음은 상수 TOP 식의 예입니다.  
  
 `select distinct top(10) c.a1, c.a2 from T as a`  
  
 다음은 매개 변수가 있는 TOP 식의 예입니다.  
  
 `select distinct top(@topParam) c.a1, c.a2 from T as a`  
  
 쿼리가 정렬되지 않는 한 TOP은 결정적이지 않습니다. 결정적인 결과가 필요한 경우에는 [ORDER BY](../../../../../../docs/framework/data/adonet/ef/language-reference/skip-entity-sql.md) 절의 [SKIP](../../../../../../docs/framework/data/adonet/ef/language-reference/limit-entity-sql.md) 및 [LIMIT](../../../../../../docs/framework/data/adonet/ef/language-reference/order-by-entity-sql.md) 하위 절을 사용합니다. TOP과 SKIP\/LIMIT는 함께 사용할 수 없습니다.  
  
## 예제  
 다음 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] 쿼리에서는 TOP을 사용하여 쿼리 결과에서 반환할 상위 행 하나를 지정합니다. 쿼리는 AdventureWorks Sales 모델을 기반으로 합니다. 이 쿼리를 컴파일하고 실행하려면 다음 단계를 수행하세요.  
  
1.  [방법: StructuralType 결과를 반환하는 쿼리 실행](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md)의 절차를 따릅니다.  
  
2.  다음 쿼리를 `ExecuteStructuralTypeQuery` 메서드에 인수로 전달합니다.  
  
 [!code-csharp[DP EntityServices Concepts 2#TOP](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#top)]  
  
## 참고 항목  
 [SELECT](../../../../../../docs/framework/data/adonet/ef/language-reference/select-entity-sql.md)   
 [SKIP](../../../../../../docs/framework/data/adonet/ef/language-reference/skip-entity-sql.md)   
 [LIMIT](../../../../../../docs/framework/data/adonet/ef/language-reference/limit-entity-sql.md)   
 [ORDER BY](../../../../../../docs/framework/data/adonet/ef/language-reference/order-by-entity-sql.md)   
 [Entity SQL 참조](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)