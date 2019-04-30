---
title: 지원되지 않는 식(Entity SQL)
ms.date: 03/30/2017
ms.assetid: 5e79da7e-e78a-413c-8fb0-f3f9cd84f579
dev_langs:
- sql
ms.openlocfilehash: a47ff46ca99a84500bc5dfecc19bb31652e9b4b6
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62034075"
---
# <a name="unsupported-expressions"></a><span data-ttu-id="02a0d-102">지원 되지 않는 식</span><span class="sxs-lookup"><span data-stu-id="02a0d-102">Unsupported expressions</span></span>

<span data-ttu-id="02a0d-103">이 항목에서는 [!INCLUDE[tsql](../../../../../../includes/tsql-md.md)]에서 지원되지 않는 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] 식에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="02a0d-103">This topic describes [!INCLUDE[tsql](../../../../../../includes/tsql-md.md)] expressions that are not supported in [!INCLUDE[esql](../../../../../../includes/esql-md.md)].</span></span> <span data-ttu-id="02a0d-104">자세한 내용은 [Entity SQL 차이점 TRANSACT-SQL에서](../../../../../../docs/framework/data/adonet/ef/language-reference/how-entity-sql-differs-from-transact-sql.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="02a0d-104">For more information, see [How Entity SQL Differs from Transact-SQL](../../../../../../docs/framework/data/adonet/ef/language-reference/how-entity-sql-differs-from-transact-sql.md).</span></span>

## <a name="quantified-predicates"></a><span data-ttu-id="02a0d-105">정량화 된 조건자</span><span class="sxs-lookup"><span data-stu-id="02a0d-105">Quantified predicates</span></span>

[!INCLUDE[tsql](../../../../../../includes/tsql-md.md)]<span data-ttu-id="02a0d-106">에서는 다음 폼을 생성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="02a0d-106">allows constructs of the following form:</span></span>

```sql
sal > all (select salary from employees)
sal > any (select salary from employees)
```

<span data-ttu-id="02a0d-107">이와 달리 [!INCLUDE[esql](../../../../../../includes/esql-md.md)]에서는 이러한 생성이 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="02a0d-107">[!INCLUDE[esql](../../../../../../includes/esql-md.md)], however, does not support such constructs.</span></span> <span data-ttu-id="02a0d-108">대신 이와 동등한 식을 [!INCLUDE[esql](../../../../../../includes/esql-md.md)]에서 다음과 같이 쓸 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="02a0d-108">Equivalent expressions can be written in [!INCLUDE[esql](../../../../../../includes/esql-md.md)] as follows:</span></span>

```sql
not exists(select 0 from employees as e where sal <= e.salary)
exists(select 0 from employees as e where sal > e.salary)
```

## <a name="-operator"></a><span data-ttu-id="02a0d-109">\* 연산자</span><span class="sxs-lookup"><span data-stu-id="02a0d-109">\* operator</span></span>

[!INCLUDE[tsql](../../../../../../includes/tsql-md.md)]<span data-ttu-id="02a0d-110">에서는 모든 열이 프로젝션되어야 함을 나타내도록 SELECT 절에서 \* 연산자를 사용하도록 지원합니다. 이는 [!INCLUDE[esql](../../../../../../includes/esql-md.md)]에서는 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="02a0d-110">supports the use of the \* operator in the SELECT clause to indicate that all columns should be projected out. This is not supported in [!INCLUDE[esql](../../../../../../includes/esql-md.md)].</span></span>

## <a name="see-also"></a><span data-ttu-id="02a0d-111">참고자료</span><span class="sxs-lookup"><span data-stu-id="02a0d-111">See also</span></span>

- [<span data-ttu-id="02a0d-112">Entity SQL 개요</span><span class="sxs-lookup"><span data-stu-id="02a0d-112">Entity SQL Overview</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-overview.md)
- [<span data-ttu-id="02a0d-113">Entity SQL과 Transact-SQL의 차이점</span><span class="sxs-lookup"><span data-stu-id="02a0d-113">How Entity SQL Differs from Transact-SQL</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/how-entity-sql-differs-from-transact-sql.md)
