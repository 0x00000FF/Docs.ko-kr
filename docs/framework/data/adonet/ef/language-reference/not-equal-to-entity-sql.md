---
title: '!= (같지 않음)(Entity SQL)'
ms.date: 03/30/2017
ms.assetid: 3b4a02ad-ddfc-4c42-8dfa-676234461312
ms.openlocfilehash: f5fdbbf2892781ce44dfe73e8cd80fbe0f74cf1c
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61760339"
---
# <a name="-not-equal-to-entity-sql"></a><span data-ttu-id="c86a0-102">!= (같지 않음)(Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="c86a0-102">!= (Not Equal To) (Entity SQL)</span></span>
<span data-ttu-id="c86a0-103">두 식을 비교하여 왼쪽 식의 값이 오른쪽 식의 값과 다른지 여부를 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="c86a0-103">Compares two expressions to determine whether the left expression is not equal to the right expression.</span></span> <span data-ttu-id="c86a0-104">!=(같지 않음) 연산자는 기능이 <> 연산자와 동일합니다.</span><span class="sxs-lookup"><span data-stu-id="c86a0-104">The != (Not Equal To) operator is functionally equivalent to the <> operator.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c86a0-105">구문</span><span class="sxs-lookup"><span data-stu-id="c86a0-105">Syntax</span></span>  
  
```  
expression != expression  
or  
expression <> expression  
```  
  
## <a name="arguments"></a><span data-ttu-id="c86a0-106">인수</span><span class="sxs-lookup"><span data-stu-id="c86a0-106">Arguments</span></span>  
 `expression`  
 <span data-ttu-id="c86a0-107">모든 유효한 식입니다.</span><span class="sxs-lookup"><span data-stu-id="c86a0-107">Any valid expression.</span></span> <span data-ttu-id="c86a0-108">비교할 두 식 모두 데이터 형식이 암시적으로 변환 가능해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c86a0-108">Both expressions must have implicitly convertible data types.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="c86a0-109">결과 형식</span><span class="sxs-lookup"><span data-stu-id="c86a0-109">Result Types</span></span>  
 <span data-ttu-id="c86a0-110">왼쪽 식의 값이 오른쪽 식의 값과 다르면`true` 이고, 그렇지 않으면 `false`입니다.</span><span class="sxs-lookup"><span data-stu-id="c86a0-110">`true` if the left expression is not equal to the right expression; otherwise, `false`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c86a0-111">예제</span><span class="sxs-lookup"><span data-stu-id="c86a0-111">Example</span></span>  
 <span data-ttu-id="c86a0-112">다음 Entity SQL 쿼리는 != 연산자를 통해 두 식을 비교하여 왼쪽 식의 값이 오른쪽 식의 값과 다른지 여부를 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="c86a0-112">The following Entity SQL query uses the != operator to compare two expressions to determine whether the left expression is not equal to the right expression.</span></span> <span data-ttu-id="c86a0-113">쿼리는 AdventureWorks Sales 모델을 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="c86a0-113">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="c86a0-114">이 쿼리를 컴파일하고 실행하려면 다음 단계를 수행하세요.</span><span class="sxs-lookup"><span data-stu-id="c86a0-114">To compile and run this query, follow these steps:</span></span>  
  
1. <span data-ttu-id="c86a0-115">절차에 따라 [방법: StructuralType 결과 반환 하는 쿼리 실행](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="c86a0-115">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2. <span data-ttu-id="c86a0-116">다음 쿼리를 `ExecuteStructuralTypeQuery` 메서드에 인수로 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="c86a0-116">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#NOT_EQUALS](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#not_equals)]  
  
## <a name="see-also"></a><span data-ttu-id="c86a0-117">참고자료</span><span class="sxs-lookup"><span data-stu-id="c86a0-117">See also</span></span>

- [<span data-ttu-id="c86a0-118">엔터티 SQL 참조</span><span class="sxs-lookup"><span data-stu-id="c86a0-118">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
