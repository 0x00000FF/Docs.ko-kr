---
title: "비교 의미 체계(Entity SQL) | Microsoft Docs"
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
ms.assetid: b36ce28a-2fe4-4236-b782-e5f7c054deae
caps.latest.revision: 2
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 2
---
# 비교 의미 체계(Entity SQL)
다음 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] 연산자를 수행하면 형식 인스턴스 비교가 수반됩니다.  
  
## 명시적 비교  
 같음 연산:  
  
-   \=  
  
-   \!\=  
  
 정렬 연산:  
  
-   \<  
  
-   \<\=  
  
-   \>  
  
-   \>\=  
  
 Null 허용 여부 연산:  
  
-   IS NULL  
  
-   IS NOT NULL  
  
## 명시적 구분  
 같음 구분:  
  
-   DISTINCT  
  
-   GROUP BY  
  
 정렬 구분:  
  
-   ORDER BY  
  
## 암시적 구분  
 Set 작업 및 조건자\(같음\):  
  
-   UNION  
  
-   INTERSECT  
  
-   EXCEPT  
  
-   SET  
  
-   OVERLAPS  
  
 항목 조건자\(같음\):  
  
-   IN  
  
## 지원되는 조합  
 다음 표에서는 각 종류의 형식에 대해 지원되는 비교 연산자의 조합을 모두 보여 줍니다.  
  
|||||||||  
|-|-|-|-|-|-|-|-|  
|**형식**|**\=**<br /><br /> **\!\=**|**GROUP BY**<br /><br /> **DISTINCT**|**UNION**<br /><br /> **INTERSECT**<br /><br /> **EXCEPT**<br /><br /> **SET**<br /><br /> **OVERLAPS**|**IN**|**\<   \<\=**<br /><br /> **\>   \>\=**|**ORDER BY**|**IS NULL**<br /><br /> **IS NOT NULL**|  
|엔터티 형식|참조<sup>1</sup>|모든 속성<sup>2</sup>|모든 속성<sup>2</sup>|모든 속성<sup>2</sup>|Throw<sup>3</sup>|Throw<sup>3</sup>|참조<sup>1</sup>|  
|복합 형식|Throw<sup>3</sup>|Throw<sup>3</sup>|Throw<sup>3</sup>|Throw<sup>3</sup>|Throw<sup>3</sup>|Throw<sup>3</sup>|Throw<sup>3</sup>|  
|행|모든 속성<sup>4</sup>|모든 속성<sup>4</sup>|모든 속성<sup>4</sup>|Throw<sup>3</sup>|Throw<sup>3</sup>|모든 속성<sup>4</sup>|Throw<sup>3</sup>|  
|기본 형식|@FSHO2@공급자 고유|@FSHO2@공급자 고유|@FSHO2@공급자 고유|@FSHO2@공급자 고유|@FSHO2@공급자 고유|@FSHO2@공급자 고유|@FSHO2@공급자 고유|  
|Multiset|Throw<sup>3</sup>|Throw<sup>3</sup>|Throw<sup>3</sup>|Throw<sup>3</sup>|Throw<sup>3</sup>|Throw<sup>3</sup>|Throw<sup>3</sup>|  
|Ref|예 <sup>5</sup>|예 <sup>5</sup>|예 <sup>5</sup>|예 <sup>5</sup>|Throw|Throw|예 <sup>5</sup>|  
|연결<br /><br /> 형식|Throw<sup>3</sup>|Throw|Throw|Throw|Throw<sup>3</sup>|Throw<sup>3</sup>|Throw<sup>3</sup>|  
  
 <sup>1</sup>해당 엔터티 형식 인스턴스의 참조는 다음 예제와 같이 암시적으로 비교됩니다.  
  
```  
SELECT p1, p2   
FROM AdventureWorksEntities.Product AS p1   
     JOIN AdventureWorksEntities.Product AS p2   
WHERE p1 != p2 OR p1 IS NULL  
```  
  
 엔터티 인스턴스는 명시적 참조와 비교할 수 없습니다.  비교를 시도하면 예외가 throw됩니다.  예를 들어, 다음 쿼리는 예외를 throw합니다.  
  
```  
SELECT p1, p2   
FROM AdventureWorksEntities.Product AS p1   
     JOIN AdventureWorksEntities.Product AS p2   
WHERE p1 != REF(p2)  
```  
  
 <sup>2</sup>복합 형식의 속성이 저장소로 전송되기 전에 결합되므로 비교할 수 있는 상태가 됩니다\(해당 속성이 모두 비교 가능한 경우\).  아래 <sup>4</sup>를 참조하세요.  
  
 <sup>3</sup>Entity Framework 런타임에서는 지원되지 않는 경우를 감지하여 공급자\/저장소의 개입 없이도 의미 있는 예외를 throw합니다.  
  
 <sup>4</sup>모든 속성을 비교합니다.  텍스트, ntext, 이미지와 같이 비교할 수 없는 형식의 속성이 있는 경우 서버 예외가 throw될 수 있습니다.  
  
 <sup>5</sup>참조의 모든 개별 요소가 비교되며, 여기에는 엔터티 형식의 엔터티 집합 이름과 모든 키 속성이 포함됩니다.  
  
## 참고 항목  
 [Entity SQL 개요](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-overview.md)