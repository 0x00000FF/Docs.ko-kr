---
title: '메서드 기반 쿼리 구문 예제: 정렬'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 5d21b178-d731-471a-8534-1f8184a2ef06
ms.openlocfilehash: c059bd771667c23bb9aeb78b548e7036e4b8a73a
ms.sourcegitcommit: 3c1c3ba79895335ff3737934e39372555ca7d6d0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/05/2018
ms.locfileid: "43725022"
---
# <a name="method-based-query-syntax-examples-ordering"></a><span data-ttu-id="090fd-102">메서드 기반 쿼리 구문 예제: 정렬</span><span class="sxs-lookup"><span data-stu-id="090fd-102">Method-Based Query Syntax Examples: Ordering</span></span>
<span data-ttu-id="090fd-103">이 항목의 예제에 사용 하는 방법을 보여 줍니다 합니다 <xref:System.Linq.Enumerable.ThenBy%2A> 쿼리 메서드는 [AdventureWorks Sales 모델](https://msdn.microsoft.com/library/f16cd988-673f-4376-b034-129ca93c7832) 메서드 기반 쿼리 구문을 사용 하 여 합니다.</span><span class="sxs-lookup"><span data-stu-id="090fd-103">The examples in this topic demonstrate how to use the <xref:System.Linq.Enumerable.ThenBy%2A> method to query the [AdventureWorks Sales Model](https://msdn.microsoft.com/library/f16cd988-673f-4376-b034-129ca93c7832) using method-based query syntax.</span></span> <span data-ttu-id="090fd-104">이 예제에서 사용하는 AdventureWorks Sales 모델에서는 AdventureWorks 샘플 데이터베이스의 Contact, Address, Product, SalesOrderHeader 및 SalesOrderDetail 테이블을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="090fd-104">The AdventureWorks Sales Model used in these examples is built from the Contact, Address, Product, SalesOrderHeader, and SalesOrderDetail tables in the AdventureWorks sample database.</span></span>  
  
 <span data-ttu-id="090fd-105">이 항목의 예제에서는 다음을 사용 `using` / `Imports` 문:</span><span class="sxs-lookup"><span data-stu-id="090fd-105">The examples in this topic use the following `using`/`Imports` statements:</span></span>  
  
 [!code-csharp[DP L2E Examples#ImportsUsing](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#importsusing)]
 [!code-vb[DP L2E Examples#ImportsUsing](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#importsusing)]  
  
## <a name="thenby"></a><span data-ttu-id="090fd-106">ThenBy</span><span class="sxs-lookup"><span data-stu-id="090fd-106">ThenBy</span></span>  
  
### <a name="example"></a><span data-ttu-id="090fd-107">예제</span><span class="sxs-lookup"><span data-stu-id="090fd-107">Example</span></span>  
 <span data-ttu-id="090fd-108">다음 메서드 기반 쿼리 구문 예제에서는 <xref:System.Linq.Queryable.OrderBy%2A> 및 <xref:System.Linq.Queryable.ThenBy%2A>를 사용하여 연락처 목록을 성을 기준으로 정렬한 다음 이름을 기준으로 정렬하여 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="090fd-108">The following example in method-based query syntax uses <xref:System.Linq.Queryable.OrderBy%2A> and <xref:System.Linq.Queryable.ThenBy%2A> to return a list of contacts ordered by last name and then by first name.</span></span>  
  
 [!code-csharp[DP L2E Examples#OrderByThenBy_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#orderbythenby_mq)]
 [!code-vb[DP L2E Examples#OrderByThenBy_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#orderbythenby_mq)]  
  
## <a name="thenbydescending"></a><span data-ttu-id="090fd-109">ThenByDescending</span><span class="sxs-lookup"><span data-stu-id="090fd-109">ThenByDescending</span></span>  
  
### <a name="example"></a><span data-ttu-id="090fd-110">예제</span><span class="sxs-lookup"><span data-stu-id="090fd-110">Example</span></span>  
 <span data-ttu-id="090fd-111">다음 예제에서는 <xref:System.Linq.Queryable.OrderBy%2A> 및 <xref:System.Linq.Queryable.ThenByDescending%2A> 메서드를 사용하여 먼저 가격을 기준으로 정렬한 다음 제품 이름을 내림차순으로 정렬합니다.</span><span class="sxs-lookup"><span data-stu-id="090fd-111">The following example uses the <xref:System.Linq.Queryable.OrderBy%2A> and <xref:System.Linq.Queryable.ThenByDescending%2A> methods to first sort by list price, and then perform a descending sort of the product names.</span></span>  
  
 [!code-csharp[DP L2E Examples#ThenByDescending_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#thenbydescending_mq)]
 [!code-vb[DP L2E Examples#ThenByDescending_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#thenbydescending_mq)]  
  
## <a name="see-also"></a><span data-ttu-id="090fd-112">참고 항목</span><span class="sxs-lookup"><span data-stu-id="090fd-112">See Also</span></span>  
 [<span data-ttu-id="090fd-113">LINQ to Entities에서 쿼리</span><span class="sxs-lookup"><span data-stu-id="090fd-113">Queries in LINQ to Entities</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/queries-in-linq-to-entities.md)
