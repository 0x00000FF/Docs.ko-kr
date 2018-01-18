---
title: "방법: 조인 및 교차곱 쿼리 작성"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: d8072ede-0521-4670-9bec-1778ceeb875b
caps.latest.revision: "2"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: 5f652f25d04480afb3df1f623347eee23d3ed258
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/17/2018
---
# <a name="formulate-joins-and-cross-product-queries"></a><span data-ttu-id="5c1a6-102">방법: 조인 및 교차곱 쿼리 작성</span><span class="sxs-lookup"><span data-stu-id="5c1a6-102">Formulate Joins and Cross-Product Queries</span></span>
<span data-ttu-id="5c1a6-103">다음 예제에서는 여러 테이블의 결과를 결합하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="5c1a6-103">The following examples show how to combine results from multiple tables.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5c1a6-104">예</span><span class="sxs-lookup"><span data-stu-id="5c1a6-104">Example</span></span>  
 <span data-ttu-id="5c1a6-105">다음 예제에서는 `From`의 [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)] 절(C#에서는 `from` 절)에서 외래 키 탐색을 사용하여 London에 있는 고객에 대한 모든 주문을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="5c1a6-105">The following example uses foreign key navigation in the `From` clause in [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)] (`from` clause in C#) to select all orders for customers in London.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#47](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#47)]
 [!code-vb[DLinqQueryExamples#47](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#47)]  
  
## <a name="example"></a><span data-ttu-id="5c1a6-106">예</span><span class="sxs-lookup"><span data-stu-id="5c1a6-106">Example</span></span>  
 <span data-ttu-id="5c1a6-107">다음 예제에서는 `Where`의 [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)] 절(C#에서는 `where` 절)에서 외래 키 탐색을 사용하여 `Products`가 미국에 있는 품절된 `Supplier`를 필터링합니다.</span><span class="sxs-lookup"><span data-stu-id="5c1a6-107">The following example uses foreign key navigation in the `Where` clause in [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)] (`where` clause in C#) to filter for out-of-stock `Products` whose `Supplier` is in the United States.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#48](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#48)]
 [!code-vb[DLinqQueryExamples#48](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#48)]  
  
## <a name="example"></a><span data-ttu-id="5c1a6-108">예</span><span class="sxs-lookup"><span data-stu-id="5c1a6-108">Example</span></span>  
 <span data-ttu-id="5c1a6-109">다음 예제에서는 `From`의 [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)] 절(C#에서는 `from` 절)에서 외래 키 탐색을 사용하여 시애틀에 있는 직원과 그들의 지역을 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="5c1a6-109">The following example uses foreign key navigation in the `From` clause in [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)] (`from` clause in C#) to filter for employees in Seattle and to list their territories.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#49](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#49)]  
  
## <a name="example"></a><span data-ttu-id="5c1a6-110">예</span><span class="sxs-lookup"><span data-stu-id="5c1a6-110">Example</span></span>  
 <span data-ttu-id="5c1a6-111">다음 예제에서는 `Select`의 [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)] 절(C#에서는 `select` 절)에서 외래 키 탐색을 사용하여 한 직원이 다른 직원에게 보고하는 직원 쌍과 같은 `City` 출신의 직원 쌍을 필터링합니다.</span><span class="sxs-lookup"><span data-stu-id="5c1a6-111">The following example uses foreign key navigation in the `Select` clause in [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)] (`select` clause in C#) to filter for pairs of employees where one employee reports to the other and where both employees are from the same `City`.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#50](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#50)]
 [!code-vb[DLinqQueryExamples#50](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#50)]  
  
## <a name="example"></a><span data-ttu-id="5c1a6-112">예</span><span class="sxs-lookup"><span data-stu-id="5c1a6-112">Example</span></span>  
 <span data-ttu-id="5c1a6-113">다음 [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)] 예제에서는 모든 고객과 주문을 검색하고 주문이 고객과 일치하도록 하며 해당 목록의 모든 고객에 대한 연락처 이름이 제공되도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="5c1a6-113">The following [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)] example looks for all customers and orders, makes sure that the orders are matched to customers, and guarantees that for every customer in that list, a contact name is provided.</span></span>  
  
 [!code-vb[DLinqQueryExamples#50v](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#50v)]  
  
## <a name="example"></a><span data-ttu-id="5c1a6-114">예</span><span class="sxs-lookup"><span data-stu-id="5c1a6-114">Example</span></span>  
 <span data-ttu-id="5c1a6-115">다음 예제에서는 두 테이블과 두 테이블에서 가져온 프로젝트 결과를 명시적으로 조인합니다.</span><span class="sxs-lookup"><span data-stu-id="5c1a6-115">The following example explicitly joins two tables and projects results from both tables.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#51](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#51)]
 [!code-vb[DLinqQueryExamples#51](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#51)]  
  
## <a name="example"></a><span data-ttu-id="5c1a6-116">예</span><span class="sxs-lookup"><span data-stu-id="5c1a6-116">Example</span></span>  
 <span data-ttu-id="5c1a6-117">다음 예제에서는 세 테이블과 각 테이블에서 가져온 프로젝트 결과를 명시적으로 조인합니다.</span><span class="sxs-lookup"><span data-stu-id="5c1a6-117">The following example explicitly joins three tables and projects results from each of them.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#52](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#52)]
 [!code-vb[DLinqQueryExamples#52](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#52)]  
  
## <a name="example"></a><span data-ttu-id="5c1a6-118">예</span><span class="sxs-lookup"><span data-stu-id="5c1a6-118">Example</span></span>  
 <span data-ttu-id="5c1a6-119">다음 예제에서는 `LEFT OUTER JOIN`를 사용하여 `DefaultIfEmpty()`을 얻는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="5c1a6-119">The following example shows how to achieve a `LEFT OUTER JOIN` by using `DefaultIfEmpty()`.</span></span> <span data-ttu-id="5c1a6-120">`DefaultIfEmpty()`에 `Order`가 없는 경우 `Employee` 메서드는 null을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="5c1a6-120">The `DefaultIfEmpty()` method returns null when there is no `Order` for the `Employee`.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#53](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#53)]
 [!code-vb[DLinqQueryExamples#53](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#53)]  
  
## <a name="example"></a><span data-ttu-id="5c1a6-121">예</span><span class="sxs-lookup"><span data-stu-id="5c1a6-121">Example</span></span>  
 <span data-ttu-id="5c1a6-122">다음 예제에서는 조인으로 인해 생성된 `let` 식을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="5c1a6-122">The following example projects a `let` expression resulting from a join.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#54](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#54)]
 [!code-vb[DLinqQueryExamples#54](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#54)]  
  
## <a name="example"></a><span data-ttu-id="5c1a6-123">예</span><span class="sxs-lookup"><span data-stu-id="5c1a6-123">Example</span></span>  
 <span data-ttu-id="5c1a6-124">다음 예제에서는 복합 키와 함께 사용된 `join`을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="5c1a6-124">The following example shows a `join` with a composite key.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#55](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#55)]
 [!code-vb[DLinqQueryExamples#55](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#55)]  
  
## <a name="example"></a><span data-ttu-id="5c1a6-125">예</span><span class="sxs-lookup"><span data-stu-id="5c1a6-125">Example</span></span>  
 <span data-ttu-id="5c1a6-126">다음 예제에서는 한 면이 nullable이고 다른 면은 nullable이 아닌 `join`을 생성하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="5c1a6-126">The following example shows how to construct a `join` where one side is nullable and the other is not.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#56](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#56)]
 [!code-vb[DLinqQueryExamples#56](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#56)]  
  
## <a name="see-also"></a><span data-ttu-id="5c1a6-127">참고 항목</span><span class="sxs-lookup"><span data-stu-id="5c1a6-127">See Also</span></span>  
 [<span data-ttu-id="5c1a6-128">쿼리 예제</span><span class="sxs-lookup"><span data-stu-id="5c1a6-128">Query Examples</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/query-examples.md)
