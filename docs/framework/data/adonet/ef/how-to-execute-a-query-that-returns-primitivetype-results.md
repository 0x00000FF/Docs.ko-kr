---
title: "방법: PrimitiveType 결과를 반환하는 쿼리 실행 | Microsoft Docs"
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
  - "jsharp"
ms.assetid: 7139d585-4034-4dfa-916f-2120a8b72792
caps.latest.revision: 4
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 2
---
# 방법: PrimitiveType 결과를 반환하는 쿼리 실행
이 항목에서는 <xref:System.Data.EntityClient.EntityCommand>를 사용하여 개념적 모델에 대해 명령을 실행하는 방법과 <xref:System.Data.EntityClient.EntityDataReader>를 사용하여 <xref:System.Data.Metadata.Edm.PrimitiveType> 결과를 검색하는 방법을 보여 줍니다.  
  
### 이 예제의 코드를 실행하려면  
  
1.  프로젝트에 [AdventureWorks Sales Model](http://msdn.microsoft.com/ko-kr/f16cd988-673f-4376-b034-129ca93c7832)을 추가하고 [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)]를 사용하도록 프로젝트를 구성합니다.  자세한 내용은 [How to: Use the Entity Data Model Wizard](http://msdn.microsoft.com/ko-kr/dadb058a-c5d9-4c5c-8b01-28044112231d)을 참조하세요.  
  
2.  응용 프로그램의 코드 페이지에서 다음 `using` 문\(Visual Basic에서는 `Imports`\)을 추가합니다.  
  
     [!code-csharp[DP EntityServices Concepts#Namespaces](../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/source.cs#namespaces)]
     [!code-vb[DP EntityServices Concepts#Namespaces](../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp entityservices concepts/vb/source.vb#namespaces)]  
  
## 예제  
 이 예제에서는 <xref:System.Data.Metadata.Edm.PrimitiveType> 결과를 반환하는 쿼리를 실행합니다.  다음 쿼리를 `ExecutePrimitiveTypeQuery` 함수에 인수로 전달하면 이 함수는 모든 `Products`의 평균 가격을 표시합니다.  
  
 [!code-csharp[DP EntityServices Concepts#EDM_AVG](../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#edm_avg)]
 [!code-sql[DP EntityServices Concepts#EDM_AVG](../../../../../samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#edm_avg)]  
  
 다음과 같은 매개 변수가 있는 쿼리를 전달하는 경우 <xref:System.Data.EntityClient.EntityParameter> 개체를 <xref:System.Data.EntityClient.EntityCommand> 개체의 <xref:System.Data.EntityClient.EntityCommand.Parameters%2A> 속성에 추가합니다.  
  
 [!code-csharp[DP EntityServices Concepts#CASE_WHEN_THEN_ELSE](../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#case_when_then_else)]
 [!code-sql[DP EntityServices Concepts#CASE_WHEN_THEN_ELSE](../../../../../samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#case_when_then_else)]  
  
 [!code-csharp[DP EntityServices Concepts#eSQLPrimitiveTypes](../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/source.cs#esqlprimitivetypes)]
 [!code-vb[DP EntityServices Concepts#eSQLPrimitiveTypes](../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp entityservices concepts/vb/source.vb#esqlprimitivetypes)]  
  
## 참고 항목  
 [Entity SQL 참조](../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)   
 [Entity Framework용 EntityClient 공급자](../../../../../docs/framework/data/adonet/ef/entityclient-provider-for-the-entity-framework.md)