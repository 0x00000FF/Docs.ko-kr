---
title: "지원되지 않는 식(Entity SQL)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 5e79da7e-e78a-413c-8fb0-f3f9cd84f579
caps.latest.revision: "2"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: a7dde3d88b5b21df99be64cedc92d6aa06b00d3b
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/17/2018
---
# <a name="unsupported-expressions-entity-sql"></a><span data-ttu-id="5f468-102">지원되지 않는 식(Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="5f468-102">Unsupported Expressions (Entity SQL)</span></span>
<span data-ttu-id="5f468-103">이 항목에서는 [!INCLUDE[tsql](../../../../../../includes/tsql-md.md)]에서 지원되지 않는 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] 식에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="5f468-103">This topic describes [!INCLUDE[tsql](../../../../../../includes/tsql-md.md)] expressions that are not supported in [!INCLUDE[esql](../../../../../../includes/esql-md.md)].</span></span> <span data-ttu-id="5f468-104">자세한 내용은 참조 [Entity SQL 차이점 transact-sql에서](../../../../../../docs/framework/data/adonet/ef/language-reference/how-entity-sql-differs-from-transact-sql.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="5f468-104">For more information, see [How Entity SQL Differs from Transact-SQL](../../../../../../docs/framework/data/adonet/ef/language-reference/how-entity-sql-differs-from-transact-sql.md).</span></span>  
  
## <a name="quantified-predicates"></a><span data-ttu-id="5f468-105">정규화된 조건자</span><span class="sxs-lookup"><span data-stu-id="5f468-105">Quantified Predicates</span></span>  
 [!INCLUDE[tsql](../../../../../../includes/tsql-md.md)]<span data-ttu-id="5f468-106">에서는 다음 폼을 생성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5f468-106"> allows constructs of the following form:</span></span>  
  
```  
sal > all (select salary from employees)  
sal > any (select salary from employees)  
```  
  
 <span data-ttu-id="5f468-107">이와 달리 [!INCLUDE[esql](../../../../../../includes/esql-md.md)]에서는 이러한 생성이 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5f468-107">[!INCLUDE[esql](../../../../../../includes/esql-md.md)], however, does not support such constructs.</span></span> <span data-ttu-id="5f468-108">대신 이와 동등한 식을 [!INCLUDE[esql](../../../../../../includes/esql-md.md)]에서 다음과 같이 쓸 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5f468-108">Equivalent expressions can be written in [!INCLUDE[esql](../../../../../../includes/esql-md.md)] as follows:</span></span>  
  
```  
not exists(select 0 from employees as e where sal > e.salary)  
exists(select 0 from employees as e where sal > e.salary)  
```  
  
## <a name="-operator"></a><span data-ttu-id="5f468-109">\* 연산자</span><span class="sxs-lookup"><span data-stu-id="5f468-109">\* Operator</span></span>  
 [!INCLUDE[tsql](../../../../../../includes/tsql-md.md)]<span data-ttu-id="5f468-110">에서는 모든 열이 프로젝션되어야 함을 나타내도록 SELECT 절에서 \* 연산자를 사용하도록 지원합니다. 이는 [!INCLUDE[esql](../../../../../../includes/esql-md.md)]에서는 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5f468-110"> supports the use of the \* operator in the SELECT clause to indicate that all columns should be projected out. This is not supported in [!INCLUDE[esql](../../../../../../includes/esql-md.md)].</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5f468-111">참고 항목</span><span class="sxs-lookup"><span data-stu-id="5f468-111">See Also</span></span>  
 [<span data-ttu-id="5f468-112">Entity SQL 개요</span><span class="sxs-lookup"><span data-stu-id="5f468-112">Entity SQL Overview</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-overview.md)  
 [<span data-ttu-id="5f468-113">Entity SQL과 Transact-SQL의 차이점</span><span class="sxs-lookup"><span data-stu-id="5f468-113">How Entity SQL Differs from Transact-SQL</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/how-entity-sql-differs-from-transact-sql.md)
