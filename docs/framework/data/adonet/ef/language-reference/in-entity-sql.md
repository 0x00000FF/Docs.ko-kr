---
title: IN(Entity SQL)
ms.date: 03/30/2017
ms.assetid: 51662950-ee01-4857-b7b9-311dd8515966
ms.openlocfilehash: d88f79dbfcd27f0ca0d1e26815d7d2bbee731bcf
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/09/2019
ms.locfileid: "59331275"
---
# <a name="in-entity-sql"></a><span data-ttu-id="7884f-102">IN(Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="7884f-102">IN (Entity SQL)</span></span>
<span data-ttu-id="7884f-103">컬렉션에 일치하는 값이 있는지 여부를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="7884f-103">Determines whether a value matches any value in a collection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7884f-104">구문</span><span class="sxs-lookup"><span data-stu-id="7884f-104">Syntax</span></span>  
  
```  
value [ NOT ] IN expression  
```  
  
## <a name="arguments"></a><span data-ttu-id="7884f-105">인수</span><span class="sxs-lookup"><span data-stu-id="7884f-105">Arguments</span></span>  
 `value`  
 <span data-ttu-id="7884f-106">일치시킬 값을 반환하는 모든 유효한 식입니다.</span><span class="sxs-lookup"><span data-stu-id="7884f-106">Any valid expression that returns the value to match.</span></span>  
  
 <span data-ttu-id="7884f-107">[NOT]</span><span class="sxs-lookup"><span data-stu-id="7884f-107">[ NOT ]</span></span>  
 <span data-ttu-id="7884f-108">IN의 `Boolean` 결과를 부정하도록 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="7884f-108">Specifies that the `Boolean` result of IN be negated.</span></span>  
  
 `expression`  
 <span data-ttu-id="7884f-109">일치 여부를 테스트할 컬렉션을 반환하는 모든 유효한 식입니다.</span><span class="sxs-lookup"><span data-stu-id="7884f-109">Any valid expression that returns the collection to test for a match.</span></span> <span data-ttu-id="7884f-110">모든 식은 형식이 같거나 기본 형식 또는 파생 형식이 `value`이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7884f-110">All expressions must be of the same type or of a common base or derived type as `value`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="7884f-111">반환 값</span><span class="sxs-lookup"><span data-stu-id="7884f-111">Return Value</span></span>  
 `true` <span data-ttu-id="7884f-112">값이 컬렉션에 있으면 컬렉션 또는 null 값이 null 이면 null;입니다. 그렇지 않으면 `false`합니다.</span><span class="sxs-lookup"><span data-stu-id="7884f-112">if the value is found in the collection; null if the value is null or the collection is null; otherwise, `false`.</span></span> <span data-ttu-id="7884f-113">NOT IN을 사용하면 IN의 결과가 부정됩니다.</span><span class="sxs-lookup"><span data-stu-id="7884f-113">Using NOT IN negates the results of IN.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7884f-114">예제</span><span class="sxs-lookup"><span data-stu-id="7884f-114">Example</span></span>  
 <span data-ttu-id="7884f-115">다음 Entity SQL 쿼리에서는 IN 연산자를 사용하여 컬렉션에 일치하는 값이 있는지 여부를 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="7884f-115">The following Entity SQL query uses the IN operator to determine whether a value matches any value in a collection.</span></span> <span data-ttu-id="7884f-116">쿼리는 AdventureWorks Sales 모델을 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="7884f-116">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="7884f-117">이 쿼리를 컴파일하고 실행하려면 다음 단계를 수행하세요.</span><span class="sxs-lookup"><span data-stu-id="7884f-117">To compile and run this query, follow these steps:</span></span>  
  
1. <span data-ttu-id="7884f-118">절차에 따라 [방법: StructuralType 결과 반환 하는 쿼리 실행](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="7884f-118">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2. <span data-ttu-id="7884f-119">다음 쿼리를 `ExecuteStructuralTypeQuery` 메서드에 인수로 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="7884f-119">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#IN](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#in)]  
  
## <a name="see-also"></a><span data-ttu-id="7884f-120">참고자료</span><span class="sxs-lookup"><span data-stu-id="7884f-120">See also</span></span>

- [<span data-ttu-id="7884f-121">엔터티 SQL 참조</span><span class="sxs-lookup"><span data-stu-id="7884f-121">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
