---
title: EXISTS(Entity SQL)
ms.date: 03/30/2017
ms.assetid: d28ead43-4afb-4bdc-af64-efd2e05005d7
ms.openlocfilehash: 76be542c64f75f27d126d7dbb6bde2baea8f6016
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59078241"
---
# <a name="exists-entity-sql"></a><span data-ttu-id="ae327-102">EXISTS(Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="ae327-102">EXISTS (Entity SQL)</span></span>
<span data-ttu-id="ae327-103">컬렉션이 비어 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="ae327-103">Determines if a collection is empty.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ae327-104">구문</span><span class="sxs-lookup"><span data-stu-id="ae327-104">Syntax</span></span>  
  
```  
[NOT] EXISTS ( expression )  
```  
  
## <a name="arguments"></a><span data-ttu-id="ae327-105">인수</span><span class="sxs-lookup"><span data-stu-id="ae327-105">Arguments</span></span>  
 `expression`  
 <span data-ttu-id="ae327-106">컬렉션을 반환하는 모든 유효한 식입니다.</span><span class="sxs-lookup"><span data-stu-id="ae327-106">Any valid expression that returns a collection.</span></span>  
  
 <span data-ttu-id="ae327-107">NOT</span><span class="sxs-lookup"><span data-stu-id="ae327-107">NOT</span></span>  
 <span data-ttu-id="ae327-108">EXISTS의 결과를 부정하도록 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="ae327-108">Specifies that the result of EXISTS be negated.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ae327-109">반환 값</span><span class="sxs-lookup"><span data-stu-id="ae327-109">Return Value</span></span>  
 `true` <span data-ttu-id="ae327-110">컬렉션이 비어 있습니다. 그렇지 않으면 `false`합니다.</span><span class="sxs-lookup"><span data-stu-id="ae327-110">if the collection is not empty; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ae327-111">설명</span><span class="sxs-lookup"><span data-stu-id="ae327-111">Remarks</span></span>  
 <span data-ttu-id="ae327-112">EXISTS는 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] 집합 연산자 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="ae327-112">EXISTS is one of the [!INCLUDE[esql](../../../../../../includes/esql-md.md)] set operators.</span></span> <span data-ttu-id="ae327-113">모든 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] 집합 연산자는 왼쪽에서 오른쪽으로 계산됩니다.</span><span class="sxs-lookup"><span data-stu-id="ae327-113">All [!INCLUDE[esql](../../../../../../includes/esql-md.md)] set operators are evaluated from left to right.</span></span> <span data-ttu-id="ae327-114">우선 순위에 대 한 정보를 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] 집합 연산자를 참조 하십시오 [EXCEPT](../../../../../../docs/framework/data/adonet/ef/language-reference/except-entity-sql.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="ae327-114">For precedence information for the [!INCLUDE[esql](../../../../../../includes/esql-md.md)] set operators, see [EXCEPT](../../../../../../docs/framework/data/adonet/ef/language-reference/except-entity-sql.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="ae327-115">예제</span><span class="sxs-lookup"><span data-stu-id="ae327-115">Example</span></span>  
 <span data-ttu-id="ae327-116">다음 Entity SQL 쿼리에서는 EXISTS 연산자를 사용하여 컬렉션이 비어 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="ae327-116">The following Entity SQL query uses the EXISTS operator to determine whether the collection is empty.</span></span> <span data-ttu-id="ae327-117">쿼리는 AdventureWorks Sales 모델을 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="ae327-117">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="ae327-118">이 쿼리를 컴파일하고 실행하려면 다음 단계를 수행하세요.</span><span class="sxs-lookup"><span data-stu-id="ae327-118">To compile and run this query, follow these steps:</span></span>  
  
1.  <span data-ttu-id="ae327-119">절차에 따라 [방법: StructuralType 결과 반환 하는 쿼리 실행](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="ae327-119">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2.  <span data-ttu-id="ae327-120">다음 쿼리를 `ExecuteStructuralTypeQuery` 메서드에 인수로 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="ae327-120">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#EXISTS](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#exists)]  
  
## <a name="see-also"></a><span data-ttu-id="ae327-121">참고자료</span><span class="sxs-lookup"><span data-stu-id="ae327-121">See also</span></span>

- [<span data-ttu-id="ae327-122">엔터티 SQL 참조</span><span class="sxs-lookup"><span data-stu-id="ae327-122">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
