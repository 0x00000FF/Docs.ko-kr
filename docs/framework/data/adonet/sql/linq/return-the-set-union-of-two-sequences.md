---
title: "두 시퀀스의 합집합 반환"
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
ms.assetid: 8b8bd3cb-86d4-4a3b-9906-61f68726dd1f
caps.latest.revision: "2"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: a9f1ba281c1c7bd6a6a0d96746caa512c6c208b1
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="return-the-set-union-of-two-sequences"></a><span data-ttu-id="39c7d-102">두 시퀀스의 합집합 반환</span><span class="sxs-lookup"><span data-stu-id="39c7d-102">Return the Set Union of Two Sequences</span></span>
<span data-ttu-id="39c7d-103"><xref:System.Linq.Queryable.Union%2A> 연산자를 사용하여 두 시퀀스의 합집합을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="39c7d-103">Use the <xref:System.Linq.Queryable.Union%2A> operator to return the set union of two sequences.</span></span>  
  
## <a name="example"></a><span data-ttu-id="39c7d-104">예</span><span class="sxs-lookup"><span data-stu-id="39c7d-104">Example</span></span>  
 <span data-ttu-id="39c7d-105">이 예제에서는 <xref:System.Linq.Queryable.Union%2A>을 사용하여 `Customers` 또는 `Employees`가 있는 모든 국가의 시퀀스를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="39c7d-105">This example uses <xref:System.Linq.Queryable.Union%2A> to return a sequence of all countries in which there are either `Customers` or `Employees`.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#43](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#43)]
 [!code-vb[DLinqQueryExamples#43](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#43)]  
  
 <span data-ttu-id="39c7d-106">[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]에서 <xref:System.Linq.Queryable.Union%2A> 연산자는 순서가 지정되지 않은 다중 집합의 연결(SQL `UNION ALL` 절의 효율적인 결과)로 다중 집합에 대해 정의되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="39c7d-106">In [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], the <xref:System.Linq.Queryable.Union%2A> operator is defined for multisets as the unordered concatenation of the multisets (effectively the result of the `UNION ALL` clause in SQL).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="39c7d-107">참고 항목</span><span class="sxs-lookup"><span data-stu-id="39c7d-107">See Also</span></span>  
 [<span data-ttu-id="39c7d-108">쿼리 예제</span><span class="sxs-lookup"><span data-stu-id="39c7d-108">Query Examples</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/query-examples.md)  
 [<span data-ttu-id="39c7d-109">표준 쿼리 연산자 변환</span><span class="sxs-lookup"><span data-stu-id="39c7d-109">Standard Query Operator Translation</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/standard-query-operator-translation.md)
