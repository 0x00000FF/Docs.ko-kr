---
title: "방법: DataContext 수준에서 필터링"
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
ms.assetid: 15505cd7-0df2-427a-9f86-e0f96f60ee2e
caps.latest.revision: "2"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: e7ff6bf048b5303565cd8c6c1c7448a47a89fc22
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/17/2018
---
# <a name="how-to-filter-at-the-datacontext-level"></a><span data-ttu-id="138e9-102">방법: DataContext 수준에서 필터링</span><span class="sxs-lookup"><span data-stu-id="138e9-102">How to: Filter at the DataContext Level</span></span>
<span data-ttu-id="138e9-103">`EntitySets` 수준에서 `DataContext`를 필터링할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="138e9-103">You can filter `EntitySets` at the `DataContext` level.</span></span> <span data-ttu-id="138e9-104">이러한 필터는 <xref:System.Data.Linq.DataContext> 인스턴스로 수행되는 모든 쿼리에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="138e9-104">Such filters apply to all queries done with that <xref:System.Data.Linq.DataContext> instance.</span></span>  
  
## <a name="example"></a><span data-ttu-id="138e9-105">예</span><span class="sxs-lookup"><span data-stu-id="138e9-105">Example</span></span>  
 <span data-ttu-id="138e9-106">다음 예제에서는 <xref:System.Data.Linq.DataLoadOptions.AssociateWith%28System.Linq.Expressions.LambdaExpression%29?displayProperty=nameWithType> 기준으로 고객의 미리 로드된 주문을 필터링하기 위해 `ShippedDate`가 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="138e9-106">In the following example, <xref:System.Data.Linq.DataLoadOptions.AssociateWith%28System.Linq.Expressions.LambdaExpression%29?displayProperty=nameWithType> is used to filter the pre-loaded orders for customers by `ShippedDate`.</span></span>  
  
 [!code-csharp[DLinqQueryConcepts#10](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryConcepts/cs/Program.cs#10)]
 [!code-vb[DLinqQueryConcepts#10](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryConcepts/vb/Module1.vb#10)]  
  
## <a name="see-also"></a><span data-ttu-id="138e9-107">참고 항목</span><span class="sxs-lookup"><span data-stu-id="138e9-107">See Also</span></span>  
 [<span data-ttu-id="138e9-108">쿼리 개념</span><span class="sxs-lookup"><span data-stu-id="138e9-108">Query Concepts</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/query-concepts.md)
