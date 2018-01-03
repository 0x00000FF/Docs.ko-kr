---
title: "&amp;&amp;(및) (Entity SQL)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e7d24213-471d-4807-b85e-570375df89b5
caps.latest.revision: "3"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: e7255110a9118c3a31c84e3262fd5b1490d546e7
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="ampamp-and-entity-sql"></a><span data-ttu-id="d1d3d-102">&amp;&amp;(및) (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="d1d3d-102">&amp;&amp; (AND) (Entity SQL)</span></span>
<span data-ttu-id="d1d3d-103">두 식이 `true` 이면 `true`를 반환하고, 그렇지 않으면 `false` 또는 `NULL`을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="d1d3d-103">Returns `true` if both expressions are `true`; otherwise, `false` or `NULL`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d1d3d-104">구문</span><span class="sxs-lookup"><span data-stu-id="d1d3d-104">Syntax</span></span>  
  
```  
boolean_expression AND boolean_expression  
or  
boolean_expression && boolean_expression  
```  
  
## <a name="arguments"></a><span data-ttu-id="d1d3d-105">인수</span><span class="sxs-lookup"><span data-stu-id="d1d3d-105">Arguments</span></span>  
 `boolean_expression`  
 <span data-ttu-id="d1d3d-106">부울을 반환하는 모든 유효한 식입니다.</span><span class="sxs-lookup"><span data-stu-id="d1d3d-106">Any valid expression that returns a Boolean.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d1d3d-107">설명</span><span class="sxs-lookup"><span data-stu-id="d1d3d-107">Remarks</span></span>  
 <span data-ttu-id="d1d3d-108">이중 앰퍼샌드(&&)는 AND 연산자와 같은 기능을 합니다.</span><span class="sxs-lookup"><span data-stu-id="d1d3d-108">Double ampersands (&&) have the same functionality as the AND operator.</span></span>  
  
 <span data-ttu-id="d1d3d-109">다음 표에서는 가능한 입력 값과 반환 형식을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="d1d3d-109">The following table shows possible input values and return types.</span></span>  
  
||`TRUE`|`FALSE`|`NULL`|  
|-|------------|-------------|------------|  
|`TRUE`|<span data-ttu-id="d1d3d-110">TRUE</span><span class="sxs-lookup"><span data-stu-id="d1d3d-110">TRUE</span></span>|<span data-ttu-id="d1d3d-111">FALSE</span><span class="sxs-lookup"><span data-stu-id="d1d3d-111">FALSE</span></span>|<span data-ttu-id="d1d3d-112">NULL</span><span class="sxs-lookup"><span data-stu-id="d1d3d-112">NULL</span></span>|  
|`FALSE`|<span data-ttu-id="d1d3d-113">FALSE</span><span class="sxs-lookup"><span data-stu-id="d1d3d-113">FALSE</span></span>|<span data-ttu-id="d1d3d-114">FALSE</span><span class="sxs-lookup"><span data-stu-id="d1d3d-114">FALSE</span></span>|<span data-ttu-id="d1d3d-115">FALSE</span><span class="sxs-lookup"><span data-stu-id="d1d3d-115">FALSE</span></span>|  
|`NULL`|<span data-ttu-id="d1d3d-116">NULL</span><span class="sxs-lookup"><span data-stu-id="d1d3d-116">NULL</span></span>|<span data-ttu-id="d1d3d-117">false</span><span class="sxs-lookup"><span data-stu-id="d1d3d-117">FALSE</span></span>|<span data-ttu-id="d1d3d-118">NULL</span><span class="sxs-lookup"><span data-stu-id="d1d3d-118">NULL</span></span>|  
  
## <a name="example"></a><span data-ttu-id="d1d3d-119">예</span><span class="sxs-lookup"><span data-stu-id="d1d3d-119">Example</span></span>  
 <span data-ttu-id="d1d3d-120">다음 Entity SQL 쿼리에서는 AND 연산자를 사용하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="d1d3d-120">The following Entity SQL query demonstrates how to use the AND operator.</span></span> <span data-ttu-id="d1d3d-121">쿼리는 AdventureWorks Sales 모델을 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="d1d3d-121">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="d1d3d-122">이 쿼리를 컴파일하고 실행하려면 다음 단계를 수행하세요.</span><span class="sxs-lookup"><span data-stu-id="d1d3d-122">To compile and run this query, follow these steps:</span></span>  
  
1.  <span data-ttu-id="d1d3d-123">[How to: Execute a Query that Returns StructuralType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md)의 절차를 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="d1d3d-123">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2.  <span data-ttu-id="d1d3d-124">다음 쿼리를 `ExecuteStructuralTypeQuery` 메서드에 인수로 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="d1d3d-124">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#AND](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#and)]  
  
## <a name="see-also"></a><span data-ttu-id="d1d3d-125">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d1d3d-125">See Also</span></span>  
 [<span data-ttu-id="d1d3d-126">엔터티 SQL 참조</span><span class="sxs-lookup"><span data-stu-id="d1d3d-126">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
