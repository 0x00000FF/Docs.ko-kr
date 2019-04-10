---
title: SET(Entity SQL)
ms.date: 03/30/2017
ms.assetid: 28b4deac-c7e4-4f09-b428-4d352ef2dc94
ms.openlocfilehash: 4e2a387cf400a881dfd91c61b36ee3ce0f5a4431
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/09/2019
ms.locfileid: "59309435"
---
# <a name="set-entity-sql"></a>SET(Entity SQL)
SET 식은 중복 요소가 모두 제거된 새 컬렉션을 생성하여 개체 컬렉션을 집합으로 변환하는 데 사용됩니다.  
  
## <a name="syntax"></a>구문  
  
```  
SET ( expression )  
```  
  
## <a name="arguments"></a>인수  
 `expression`  
 컬렉션을 반환하는 모든 유효한 쿼리 식입니다.  
  
## <a name="remarks"></a>설명  
 집합 식 `SET(c)` 는 다음 select 문과 논리적으로 같습니다.  
  
```  
SELECT VALUE DISTINCT c FROM c  
```  
  
 `SET` 중 하나인는 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] 연산자를 설정 합니다. 모든 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] 집합 연산자는 왼쪽에서 오른쪽으로 계산됩니다. 참조 [EXCEPT](../../../../../../docs/framework/data/adonet/ef/language-reference/except-entity-sql.md) 에 대 한 우선 순위 정보는 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] 집합 연산자입니다.  
  
## <a name="example"></a>예제  
 다음 Entity SQL 쿼리에서는 SET 식을 사용하여 개체의 컬렉션을 집합으로 변환합니다. 쿼리는 AdventureWorks Sales 모델을 기반으로 합니다. 이 쿼리를 컴파일하고 실행하려면 다음 단계를 수행하세요.  
  
1. 절차에 따라 [방법: PrimitiveType 결과 반환 하는 쿼리 실행](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-primitivetype-results.md)합니다.  
  
2. 다음 쿼리를 `ExecutePrimitiveTypeQuery` 메서드에 인수로 전달합니다.  
  
 [!code-csharp[DP EntityServices Concepts 2#SET](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#set)]  
  
## <a name="see-also"></a>참고자료

- [엔터티 SQL 참조](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
