---
title: "&gt;=(보다 크거나 같음)(Entity SQL)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 70780ac4-0123-4da8-b731-8af856daffe3
caps.latest.revision: "3"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: b176e1efdc17b58083234d0437033bd43775f604
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/17/2018
---
# <a name="gt-greater-than-or-equal-to-entity-sql"></a><span data-ttu-id="04971-102">&gt;=(보다 크거나 같음)(Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="04971-102">&gt;= (Greater Than or Equal To) (Entity SQL)</span></span>
<span data-ttu-id="04971-103">두 식을 비교하여 왼쪽 식의 값이 오른쪽 식의 값보다 크거나 같은지 여부를 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="04971-103">Compares two expressions to determine whether the left expression has a value greater than or equal to the right expression.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="04971-104">구문</span><span class="sxs-lookup"><span data-stu-id="04971-104">Syntax</span></span>  
  
```  
expression >= expression  
```  
  
## <a name="arguments"></a><span data-ttu-id="04971-105">인수</span><span class="sxs-lookup"><span data-stu-id="04971-105">Arguments</span></span>  
 `expression`  
 <span data-ttu-id="04971-106">모든 유효한 식입니다.</span><span class="sxs-lookup"><span data-stu-id="04971-106">Any valid expression.</span></span> <span data-ttu-id="04971-107">비교할 두 식 모두 데이터 형식이 암시적으로 변환 가능해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="04971-107">Both expressions must have implicitly convertible data types.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="04971-108">결과 형식</span><span class="sxs-lookup"><span data-stu-id="04971-108">Result Types</span></span>  
 <span data-ttu-id="04971-109">왼쪽 식의 값이 오른쪽 식의 값보다 크거나 같으면`true` 이고, 그렇지 않으면 `false`입니다.</span><span class="sxs-lookup"><span data-stu-id="04971-109">`true` if the left expression has a value greater than or equal to the right expression; otherwise, `false`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="04971-110">예</span><span class="sxs-lookup"><span data-stu-id="04971-110">Example</span></span>  
 <span data-ttu-id="04971-111">다음 Entity SQL 쿼리는 >= 비교 연산자를 통해 두 식을 비교하여 왼쪽 식의 값이 오른쪽 식의 값보다 크거나 같은지 여부를 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="04971-111">The following Entity SQL query uses >= comparison operator to compare two expressions to determine whether the left expression has a value greater than or equal to the right expression.</span></span> <span data-ttu-id="04971-112">쿼리는 AdventureWorks Sales 모델을 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="04971-112">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="04971-113">이 쿼리를 컴파일하고 실행하려면 다음 단계를 수행하세요.</span><span class="sxs-lookup"><span data-stu-id="04971-113">To compile and run this query, follow these steps:</span></span>  
  
1.  <span data-ttu-id="04971-114">[How to: Execute a Query that Returns StructuralType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md)의 절차를 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="04971-114">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2.  <span data-ttu-id="04971-115">다음 쿼리를 `ExecuteStructuralTypeQuery` 메서드에 인수로 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="04971-115">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#GREATER_OR_EQUALS](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#greater_or_equals)]  
  
## <a name="see-also"></a><span data-ttu-id="04971-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="04971-116">See Also</span></span>  
 [<span data-ttu-id="04971-117">엔터티 SQL 참조</span><span class="sxs-lookup"><span data-stu-id="04971-117">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
