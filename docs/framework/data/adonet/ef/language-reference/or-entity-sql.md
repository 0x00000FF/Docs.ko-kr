---
title: '|| (OR) (Entity SQL)'
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-ado
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 8e649648-eb9a-4380-9d74-36e62260628c
caps.latest.revision: ''
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload:
- dotnet
ms.openlocfilehash: b44934aa0db73f872f0ab27a4c36c5c615855de1
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/17/2018
---
# <a name="-or-entity-sql"></a><span data-ttu-id="589c0-102">|| (OR) (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="589c0-102">|| (OR) (Entity SQL)</span></span>
<span data-ttu-id="589c0-103">두 `Boolean` 식을 결합합니다.</span><span class="sxs-lookup"><span data-stu-id="589c0-103">Combines two `Boolean` expressions.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="589c0-104">구문</span><span class="sxs-lookup"><span data-stu-id="589c0-104">Syntax</span></span>  
  
```  
boolean_expression OR boolean_expression  
or   
boolean_expression || boolean_expression  
```  
  
## <a name="arguments"></a><span data-ttu-id="589c0-105">인수</span><span class="sxs-lookup"><span data-stu-id="589c0-105">Arguments</span></span>  
 `boolean_expression`  
 <span data-ttu-id="589c0-106">`Boolean`을 반환하는 유효한 식입니다.</span><span class="sxs-lookup"><span data-stu-id="589c0-106">Any valid expression that returns a `Boolean`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="589c0-107">반환 값</span><span class="sxs-lookup"><span data-stu-id="589c0-107">Return Value</span></span>  
 <span data-ttu-id="589c0-108">조건 중 하나가`true` 이면 `true`이고 그렇지 않으면 `false`입니다.</span><span class="sxs-lookup"><span data-stu-id="589c0-108">`true` when either of the conditions is `true`; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="589c0-109">설명</span><span class="sxs-lookup"><span data-stu-id="589c0-109">Remarks</span></span>  
 <span data-ttu-id="589c0-110">OR는 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] 논리 연산자로</span><span class="sxs-lookup"><span data-stu-id="589c0-110">OR is an [!INCLUDE[esql](../../../../../../includes/esql-md.md)] logical operator.</span></span> <span data-ttu-id="589c0-111">두 조건을 결합할 때 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="589c0-111">It is used to combine two conditions.</span></span> <span data-ttu-id="589c0-112">한 문에 논리 연산자를 둘 이상 사용하는 경우 OR 연산자가 AND 연산자 다음에 계산됩니다.</span><span class="sxs-lookup"><span data-stu-id="589c0-112">When more than one logical operator is used in a statement, OR operators are evaluated after AND operators.</span></span> <span data-ttu-id="589c0-113">그러나 괄호를 사용하면 계산 순서를 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="589c0-113">However, you can change the order of evaluation by using parentheses.</span></span>  
  
 <span data-ttu-id="589c0-114">이중 세로 막대 (&#124; &#124;)는 OR 연산자와 동일한 기능을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="589c0-114">Double vertical bars (&#124;&#124;) have the same functionality as the OR operator.</span></span>  
  
 <span data-ttu-id="589c0-115">다음 표에서는 가능한 입력 값과 반환 형식을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="589c0-115">The following table shows possible input values and return types.</span></span>  
  
||`TRUE`|`FALSE`|`NULL`|  
|-|------------|-------------|------------|  
|`TRUE`|<span data-ttu-id="589c0-116">true</span><span class="sxs-lookup"><span data-stu-id="589c0-116">TRUE</span></span>|<span data-ttu-id="589c0-117">TRUE</span><span class="sxs-lookup"><span data-stu-id="589c0-117">TRUE</span></span>|<span data-ttu-id="589c0-118">TRUE</span><span class="sxs-lookup"><span data-stu-id="589c0-118">TRUE</span></span>|  
|`FALSE`|<span data-ttu-id="589c0-119">TRUE</span><span class="sxs-lookup"><span data-stu-id="589c0-119">TRUE</span></span>|<span data-ttu-id="589c0-120">FALSE</span><span class="sxs-lookup"><span data-stu-id="589c0-120">FALSE</span></span>|<span data-ttu-id="589c0-121">NULL</span><span class="sxs-lookup"><span data-stu-id="589c0-121">NULL</span></span>|  
|`NULL`|<span data-ttu-id="589c0-122">TRUE</span><span class="sxs-lookup"><span data-stu-id="589c0-122">TRUE</span></span>|<span data-ttu-id="589c0-123">NULL</span><span class="sxs-lookup"><span data-stu-id="589c0-123">NULL</span></span>|<span data-ttu-id="589c0-124">NULL</span><span class="sxs-lookup"><span data-stu-id="589c0-124">NULL</span></span>|  
  
## <a name="example"></a><span data-ttu-id="589c0-125">예</span><span class="sxs-lookup"><span data-stu-id="589c0-125">Example</span></span>  
 <span data-ttu-id="589c0-126">다음 Entity SQL 쿼리에서는 OR 연산자를 사용하여 두 `Boolean` 식을 결합합니다.</span><span class="sxs-lookup"><span data-stu-id="589c0-126">The following Entity SQL query uses the OR operator to combine two `Boolean` expressions.</span></span> <span data-ttu-id="589c0-127">쿼리는 AdventureWorks Sales 모델을 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="589c0-127">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="589c0-128">이 쿼리를 컴파일하고 실행하려면 다음 단계를 수행하세요.</span><span class="sxs-lookup"><span data-stu-id="589c0-128">To compile and run this query, follow these steps:</span></span>  
  
1.  <span data-ttu-id="589c0-129">[방법: StructuralType 결과를 반환하는 쿼리 실행](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md)의 절차를 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="589c0-129">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2.  <span data-ttu-id="589c0-130">다음 쿼리를 `ExecuteStructuralTypeQuery` 메서드에 인수로 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="589c0-130">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#OR](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#or)]  
  
## <a name="see-also"></a><span data-ttu-id="589c0-131">참고 항목</span><span class="sxs-lookup"><span data-stu-id="589c0-131">See Also</span></span>  
 [<span data-ttu-id="589c0-132">엔터티 SQL 참조</span><span class="sxs-lookup"><span data-stu-id="589c0-132">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
