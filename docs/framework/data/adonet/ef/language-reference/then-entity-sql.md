---
title: THEN(Entity SQL)
ms.date: 03/30/2017
ms.assetid: 54222642-23c6-4f61-9861-67caca53ac5f
ms.openlocfilehash: ea4e84ec1c09b0f315694f74f4dc9504672c3896
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54714947"
---
# <a name="then-entity-sql"></a><span data-ttu-id="a5613-102">THEN(Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="a5613-102">THEN (Entity SQL)</span></span>
<span data-ttu-id="a5613-103">WHEN 절이 `true`로 계산될 때의 결과입니다.</span><span class="sxs-lookup"><span data-stu-id="a5613-103">The result of a WHEN clause when it evaluates to `true`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a5613-104">구문</span><span class="sxs-lookup"><span data-stu-id="a5613-104">Syntax</span></span>  
  
```  
WHEN when_expression THEN then_expression  
```  
  
## <a name="arguments"></a><span data-ttu-id="a5613-105">인수</span><span class="sxs-lookup"><span data-stu-id="a5613-105">Arguments</span></span>  
 `when_expression`  
 <span data-ttu-id="a5613-106">모든 유효한 부울 식입니다.</span><span class="sxs-lookup"><span data-stu-id="a5613-106">Any valid Boolean expression.</span></span>  
  
 `then_expression`  
 <span data-ttu-id="a5613-107">컬렉션을 반환하는 모든 유효한 쿼리 식입니다.</span><span class="sxs-lookup"><span data-stu-id="a5613-107">Any valid query expression that returns a collection.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a5613-108">설명</span><span class="sxs-lookup"><span data-stu-id="a5613-108">Remarks</span></span>  
 <span data-ttu-id="a5613-109">`when_expression` 이 `true`값으로 계산되면 결과는 해당 `then-expression`입니다.</span><span class="sxs-lookup"><span data-stu-id="a5613-109">If `when_expression` evaluates to the value `true`, the result is the corresponding `then-expression`.</span></span> <span data-ttu-id="a5613-110">만족되는 WHEN 조건이 없으면 `else-expression` 이 계산됩니다.</span><span class="sxs-lookup"><span data-stu-id="a5613-110">If none of the WHEN conditions are satisfied, the `else-expression` is evaluated.</span></span> <span data-ttu-id="a5613-111">하지만 `else-expression`이 없으면 결과는 null입니다.</span><span class="sxs-lookup"><span data-stu-id="a5613-111">However, if there is no `else-expression`, the result is null.</span></span>  
  
 <span data-ttu-id="a5613-112">예를 들어 참조 [사례](../../../../../../docs/framework/data/adonet/ef/language-reference/case-entity-sql.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="a5613-112">For an example, see [CASE](../../../../../../docs/framework/data/adonet/ef/language-reference/case-entity-sql.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="a5613-113">예제</span><span class="sxs-lookup"><span data-stu-id="a5613-113">Example</span></span>  
 <span data-ttu-id="a5613-114">다음 Entity SQL 쿼리에서는 CASE 식을 사용하여 일련의 `Boolean` 식을 계산합니다.</span><span class="sxs-lookup"><span data-stu-id="a5613-114">The following Entity SQL query uses the CASE expression to evaluate a set of `Boolean` expressions.</span></span> <span data-ttu-id="a5613-115">쿼리는 AdventureWorks Sales 모델을 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="a5613-115">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="a5613-116">이 쿼리를 컴파일하고 실행하려면 다음 단계를 수행하세요.</span><span class="sxs-lookup"><span data-stu-id="a5613-116">To compile and run this query, follow these steps:</span></span>  
  
1.  <span data-ttu-id="a5613-117">절차에 따라 [방법: PrimitiveType 결과 반환 하는 쿼리 실행](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-primitivetype-results.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="a5613-117">Follow the procedure in [How to: Execute a Query that Returns PrimitiveType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-primitivetype-results.md).</span></span>  
  
2.  <span data-ttu-id="a5613-118">다음 쿼리를 `ExecutePrimitiveTypeQuery` 메서드에 인수로 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="a5613-118">Pass the following query as an argument to the `ExecutePrimitiveTypeQuery` method:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#CASE_WHEN_THEN_ELSE](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#case_when_then_else)]  
  
## <a name="see-also"></a><span data-ttu-id="a5613-119">참고자료</span><span class="sxs-lookup"><span data-stu-id="a5613-119">See also</span></span>
- [<span data-ttu-id="a5613-120">CASE</span><span class="sxs-lookup"><span data-stu-id="a5613-120">CASE</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/case-entity-sql.md)
- [<span data-ttu-id="a5613-121">엔터티 SQL 참조</span><span class="sxs-lookup"><span data-stu-id="a5613-121">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
