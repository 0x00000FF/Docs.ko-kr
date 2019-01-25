---
title: = (같음) (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 948eb588-7080-4046-bb48-633b007393bf
ms.openlocfilehash: 2791bc0940bad92208c5bdce3659534f237bd6e4
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54551880"
---
# <a name="-equals-entity-sql"></a><span data-ttu-id="7b0dc-102">= (같음) (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="7b0dc-102">= (Equals) (Entity SQL)</span></span>
<span data-ttu-id="7b0dc-103">두 식이 같은지 비교합니다.</span><span class="sxs-lookup"><span data-stu-id="7b0dc-103">Compares the equality of two expressions.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7b0dc-104">구문</span><span class="sxs-lookup"><span data-stu-id="7b0dc-104">Syntax</span></span>  
  
```  
expression = expression  
or   
expression == expression  
```  
  
## <a name="arguments"></a><span data-ttu-id="7b0dc-105">인수</span><span class="sxs-lookup"><span data-stu-id="7b0dc-105">Arguments</span></span>  
 `expression`  
 <span data-ttu-id="7b0dc-106">모든 유효한 식입니다.</span><span class="sxs-lookup"><span data-stu-id="7b0dc-106">Any valid expression.</span></span> <span data-ttu-id="7b0dc-107">비교할 두 식 모두 데이터 형식이 암시적으로 변환 가능해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7b0dc-107">Both expressions must have implicitly convertible data types.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="7b0dc-108">결과 형식</span><span class="sxs-lookup"><span data-stu-id="7b0dc-108">Result Types</span></span>  
 <span data-ttu-id="7b0dc-109">왼쪽 식의 값이 오른쪽 식의 값과 같으면`true` 이고, 그렇지 않으면 `false`입니다.</span><span class="sxs-lookup"><span data-stu-id="7b0dc-109">`true` if the left expression is equal to the right expression; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7b0dc-110">설명</span><span class="sxs-lookup"><span data-stu-id="7b0dc-110">Remarks</span></span>  
 <span data-ttu-id="7b0dc-111">== 연산자는 = 연산자와 동일합니다.</span><span class="sxs-lookup"><span data-stu-id="7b0dc-111">The == operator is equivalent to =.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7b0dc-112">예제</span><span class="sxs-lookup"><span data-stu-id="7b0dc-112">Example</span></span>  
 <span data-ttu-id="7b0dc-113">다음 Entity SQL 쿼리에서는 = 비교 연산자를 사용하여 두 식이 같은지 비교합니다.</span><span class="sxs-lookup"><span data-stu-id="7b0dc-113">The following Entity SQL query uses = comparison operator to compare the equality of two expressions.</span></span> <span data-ttu-id="7b0dc-114">쿼리는 AdventureWorks Sales 모델을 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="7b0dc-114">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="7b0dc-115">이 쿼리를 컴파일하고 실행하려면 다음 단계를 수행하세요.</span><span class="sxs-lookup"><span data-stu-id="7b0dc-115">To compile and run this query, follow these steps:</span></span>  
  
1.  <span data-ttu-id="7b0dc-116">절차에 따라 [방법: StructuralType 결과 반환 하는 쿼리 실행](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="7b0dc-116">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2.  <span data-ttu-id="7b0dc-117">다음 쿼리를 `ExecuteStructuralTypeQuery` 메서드에 인수로 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="7b0dc-117">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#EQUALS](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#equals)]  
  
## <a name="see-also"></a><span data-ttu-id="7b0dc-118">참고자료</span><span class="sxs-lookup"><span data-stu-id="7b0dc-118">See also</span></span>
- [<span data-ttu-id="7b0dc-119">엔터티 SQL 참조</span><span class="sxs-lookup"><span data-stu-id="7b0dc-119">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
