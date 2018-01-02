---
title: WHERE(Entity SQL)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a8e1061e-0028-4a6f-8f19-b9f48e96c4b8
caps.latest.revision: "2"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: 2ad170500770bc370eb67a04ab29d0c9f9dcaabd
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="where-entity-sql"></a><span data-ttu-id="c95c4-102">WHERE(Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="c95c4-102">WHERE (Entity SQL)</span></span>
<span data-ttu-id="c95c4-103">WHERE 절 뒤에 직접 적용 되는 [FROM](../../../../../../docs/framework/data/adonet/ef/language-reference/from-entity-sql.md) 절.</span><span class="sxs-lookup"><span data-stu-id="c95c4-103">The WHERE clause is applied directly after the [FROM](../../../../../../docs/framework/data/adonet/ef/language-reference/from-entity-sql.md) clause.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c95c4-104">구문</span><span class="sxs-lookup"><span data-stu-id="c95c4-104">Syntax</span></span>  
  
```  
[ WHERE expression ]  
```  
  
## <a name="arguments"></a><span data-ttu-id="c95c4-105">인수</span><span class="sxs-lookup"><span data-stu-id="c95c4-105">Arguments</span></span>  
 `expression`  
 <span data-ttu-id="c95c4-106">Boolean 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="c95c4-106">A Boolean type.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c95c4-107">설명</span><span class="sxs-lookup"><span data-stu-id="c95c4-107">Remarks</span></span>  
 <span data-ttu-id="c95c4-108">WHERE 절의 의미 체계는 [!INCLUDE[tsql](../../../../../../includes/tsql-md.md)]에 대해 설명한 의미 체계와 같습니다.</span><span class="sxs-lookup"><span data-stu-id="c95c4-108">The WHERE clause has the same semantics as described for [!INCLUDE[tsql](../../../../../../includes/tsql-md.md)].</span></span> <span data-ttu-id="c95c4-109">WHERE 절은 원본 컬렉션의 요소를 조건 전달 요소로 제한하는 방식으로 쿼리 식에 의해 생성되는 개체를 제한합니다.</span><span class="sxs-lookup"><span data-stu-id="c95c4-109">It restricts the objects produced by the query expression by limiting the elements of the source collections to those that pass the condition.</span></span>  
  
```  
select c from cs as c where e  
```  
  
 <span data-ttu-id="c95c4-110">식 `e`에는 부운 형식이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c95c4-110">The expression `e` must have the type Boolean.</span></span>  
  
 <span data-ttu-id="c95c4-111">WHERE 절은 FROM 절 바로 다음에, 모든 그룹화나 정렬 또는 프로젝션 이전에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="c95c4-111">The WHERE clause is applied directly after the FROM clause and before any grouping, ordering, or projection takes place.</span></span> <span data-ttu-id="c95c4-112">FROM 절에 정의된 모든 요소 이름은 WHERE 절 식에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="c95c4-112">All element names defined in the FROM clause are visible to the expression of the WHERE clause.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c95c4-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c95c4-113">See Also</span></span>  
 [<span data-ttu-id="c95c4-114">엔터티 SQL 참조</span><span class="sxs-lookup"><span data-stu-id="c95c4-114">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)  
 [<span data-ttu-id="c95c4-115">쿼리 식</span><span class="sxs-lookup"><span data-stu-id="c95c4-115">Query Expressions</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/query-expressions-entity-sql.md)
