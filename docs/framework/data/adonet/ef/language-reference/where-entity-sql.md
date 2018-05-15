---
title: WHERE(Entity SQL)
ms.date: 03/30/2017
ms.assetid: a8e1061e-0028-4a6f-8f19-b9f48e96c4b8
ms.openlocfilehash: 43c038e9ff0acfdeff88492aa2ca34fbf4ada94a
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
---
# <a name="where-entity-sql"></a><span data-ttu-id="8b723-102">WHERE(Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="8b723-102">WHERE (Entity SQL)</span></span>
<span data-ttu-id="8b723-103">WHERE 절 뒤에 직접 적용 되는 [FROM](../../../../../../docs/framework/data/adonet/ef/language-reference/from-entity-sql.md) 절.</span><span class="sxs-lookup"><span data-stu-id="8b723-103">The WHERE clause is applied directly after the [FROM](../../../../../../docs/framework/data/adonet/ef/language-reference/from-entity-sql.md) clause.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8b723-104">구문</span><span class="sxs-lookup"><span data-stu-id="8b723-104">Syntax</span></span>  
  
```  
[ WHERE expression ]  
```  
  
## <a name="arguments"></a><span data-ttu-id="8b723-105">인수</span><span class="sxs-lookup"><span data-stu-id="8b723-105">Arguments</span></span>  
 `expression`  
 <span data-ttu-id="8b723-106">Boolean 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="8b723-106">A Boolean type.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8b723-107">설명</span><span class="sxs-lookup"><span data-stu-id="8b723-107">Remarks</span></span>  
 <span data-ttu-id="8b723-108">WHERE 절의 의미 체계는 [!INCLUDE[tsql](../../../../../../includes/tsql-md.md)]에 대해 설명한 의미 체계와 같습니다.</span><span class="sxs-lookup"><span data-stu-id="8b723-108">The WHERE clause has the same semantics as described for [!INCLUDE[tsql](../../../../../../includes/tsql-md.md)].</span></span> <span data-ttu-id="8b723-109">WHERE 절은 원본 컬렉션의 요소를 조건 전달 요소로 제한하는 방식으로 쿼리 식에 의해 생성되는 개체를 제한합니다.</span><span class="sxs-lookup"><span data-stu-id="8b723-109">It restricts the objects produced by the query expression by limiting the elements of the source collections to those that pass the condition.</span></span>  
  
```  
select c from cs as c where e  
```  
  
 <span data-ttu-id="8b723-110">식 `e`에는 부운 형식이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8b723-110">The expression `e` must have the type Boolean.</span></span>  
  
 <span data-ttu-id="8b723-111">WHERE 절은 FROM 절 바로 다음에, 모든 그룹화나 정렬 또는 프로젝션 이전에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="8b723-111">The WHERE clause is applied directly after the FROM clause and before any grouping, ordering, or projection takes place.</span></span> <span data-ttu-id="8b723-112">FROM 절에 정의된 모든 요소 이름은 WHERE 절 식에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="8b723-112">All element names defined in the FROM clause are visible to the expression of the WHERE clause.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8b723-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="8b723-113">See Also</span></span>  
 [<span data-ttu-id="8b723-114">엔터티 SQL 참조</span><span class="sxs-lookup"><span data-stu-id="8b723-114">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)  
 [<span data-ttu-id="8b723-115">쿼리 식</span><span class="sxs-lookup"><span data-stu-id="8b723-115">Query Expressions</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/query-expressions-entity-sql.md)
