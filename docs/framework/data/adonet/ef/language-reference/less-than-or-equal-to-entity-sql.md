---
title: "&lt;=(보다 작거나 같음)(Entity SQL)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 7c46da5c-fa09-4d90-adcc-c7e1b769d8e6
caps.latest.revision: "3"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 6b3e6054233074010f46d28e1c5b15d456ae41bf
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="lt-less-than-or-equal-to-entity-sql"></a>&lt;=(보다 작거나 같음)(Entity SQL)
두 식을 비교하여 왼쪽 식의 값이 오른쪽 식의 값보다 작거나 같은지 여부를 결정합니다.  
  
## <a name="syntax"></a>구문  
  
```  
expression <= expression  
```  
  
## <a name="arguments"></a>인수  
 `expression`  
 모든 유효한 식입니다. 비교할 두 식 모두 데이터 형식이 암시적으로 변환 가능해야 합니다.  
  
## <a name="result-types"></a>결과 형식  
 왼쪽 식의 값이 오른쪽 식의 값보다 작거나 같으면`true` 이고, 그렇지 않으면 `false`입니다.  
  
## <a name="example"></a>예제  
 다음 Entity SQL 쿼리는 <= 비교 연산자를 통해 두 식을 비교하여 왼쪽 식의 값이 오른쪽 식의 값보다 작거나 같은지 여부를 결정합니다. 쿼리는 AdventureWorks Sales 모델을 기반으로 합니다. 이 쿼리를 컴파일하고 실행하려면 다음 단계를 수행하세요.  
  
1.  [How to: Execute a Query that Returns StructuralType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md)의 절차를 따릅니다.  
  
2.  다음 쿼리를 `ExecuteStructuralTypeQuery` 메서드에 인수로 전달합니다.  
  
 [!code-csharp[DP EntityServices Concepts 2#LESS_OR_EQUALS](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#less_or_equals)]  
  
## <a name="see-also"></a>참고 항목  
 [엔터티 SQL 참조](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
