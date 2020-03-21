---
title: '! (NOT)(Entity SQL)'
ms.date: 03/30/2017
ms.assetid: a1447a34-df06-4393-93c3-0612ebd41abc
ms.openlocfilehash: 0b69d4cb64adc1f9232631d50ec42af0d1ba47e3
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79150131"
---
# <a name="-not-entity-sql"></a><span data-ttu-id="cc7ed-103">!</span><span class="sxs-lookup"><span data-stu-id="cc7ed-103">!</span></span> <span data-ttu-id="cc7ed-104">(NOT)(Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="cc7ed-104">(NOT) (Entity SQL)</span></span>
<span data-ttu-id="cc7ed-105">`Boolean` 식을 부정합니다.</span><span class="sxs-lookup"><span data-stu-id="cc7ed-105">Negates a `Boolean` expression.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cc7ed-106">구문</span><span class="sxs-lookup"><span data-stu-id="cc7ed-106">Syntax</span></span>  
  
```sql  
NOT boolean_expression  
-- or  
! boolean_expression  
```
  
## <a name="arguments"></a><span data-ttu-id="cc7ed-107">인수</span><span class="sxs-lookup"><span data-stu-id="cc7ed-107">Arguments</span></span>  
 `boolean_expression`  
 <span data-ttu-id="cc7ed-108">부울을 반환하는 모든 유효한 식입니다.</span><span class="sxs-lookup"><span data-stu-id="cc7ed-108">Any valid expression that returns a Boolean.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="cc7ed-109">설명</span><span class="sxs-lookup"><span data-stu-id="cc7ed-109">Remarks</span></span>  
 <span data-ttu-id="cc7ed-110">느낌표(!)는 NOT 연산자와 같은 기능을 합니다.</span><span class="sxs-lookup"><span data-stu-id="cc7ed-110">The exclamation point (!) has the same functionality as the NOT operator.</span></span>  
  
## <a name="example"></a><span data-ttu-id="cc7ed-111">예제</span><span class="sxs-lookup"><span data-stu-id="cc7ed-111">Example</span></span>  
 <span data-ttu-id="cc7ed-112">다음 Entity SQL 쿼리에서는 NOT 연산자를 사용하여 `Boolean` 식을 부정합니다.</span><span class="sxs-lookup"><span data-stu-id="cc7ed-112">The following Entity SQL query uses the NOT operator to negates a `Boolean` expression.</span></span> <span data-ttu-id="cc7ed-113">쿼리는 AdventureWorks Sales 모델을 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="cc7ed-113">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="cc7ed-114">이 쿼리를 컴파일하고 실행하려면 다음 단계를 수행하세요.</span><span class="sxs-lookup"><span data-stu-id="cc7ed-114">To compile and run this query, follow these steps:</span></span>  
  
1. <span data-ttu-id="cc7ed-115">[How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md)의 절차를 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="cc7ed-115">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2. <span data-ttu-id="cc7ed-116">다음 쿼리를 `ExecuteStructuralTypeQuery` 메서드에 인수로 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="cc7ed-116">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-sql[DP EntityServices Concepts#NOT](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#not)]  
  
## <a name="see-also"></a><span data-ttu-id="cc7ed-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="cc7ed-117">See also</span></span>

- [<span data-ttu-id="cc7ed-118">엔터티 SQL 참조</span><span class="sxs-lookup"><span data-stu-id="cc7ed-118">Entity SQL Reference</span></span>](entity-sql-reference.md)
