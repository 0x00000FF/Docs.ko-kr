---
title: 지원되지 않는 식(Entity SQL)
ms.date: 03/30/2017
ms.assetid: 5e79da7e-e78a-413c-8fb0-f3f9cd84f579
dev_langs:
- sql
ms.openlocfilehash: a47ff46ca99a84500bc5dfecc19bb31652e9b4b6
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54628023"
---
# <a name="unsupported-expressions"></a>지원 되지 않는 식

이 항목에서는 [!INCLUDE[tsql](../../../../../../includes/tsql-md.md)]에서 지원되지 않는 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] 식에 대해 설명합니다. 자세한 내용은 [Entity SQL 차이점 TRANSACT-SQL에서](../../../../../../docs/framework/data/adonet/ef/language-reference/how-entity-sql-differs-from-transact-sql.md)합니다.

## <a name="quantified-predicates"></a>정량화 된 조건자

[!INCLUDE[tsql](../../../../../../includes/tsql-md.md)]에서는 다음 폼을 생성할 수 있습니다.

```sql
sal > all (select salary from employees)
sal > any (select salary from employees)
```

이와 달리 [!INCLUDE[esql](../../../../../../includes/esql-md.md)]에서는 이러한 생성이 지원되지 않습니다. 대신 이와 동등한 식을 [!INCLUDE[esql](../../../../../../includes/esql-md.md)]에서 다음과 같이 쓸 수 있습니다.

```sql
not exists(select 0 from employees as e where sal <= e.salary)
exists(select 0 from employees as e where sal > e.salary)
```

## <a name="-operator"></a>* 연산자

[!INCLUDE[tsql](../../../../../../includes/tsql-md.md)]에서는 모든 열이 프로젝션되어야 함을 나타내도록 SELECT 절에서 * 연산자를 사용하도록 지원합니다. 이는 [!INCLUDE[esql](../../../../../../includes/esql-md.md)]에서는 지원되지 않습니다.

## <a name="see-also"></a>참고자료

- [Entity SQL 개요](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-overview.md)
- [Entity SQL과 Transact-SQL의 차이점](../../../../../../docs/framework/data/adonet/ef/language-reference/how-entity-sql-differs-from-transact-sql.md)
