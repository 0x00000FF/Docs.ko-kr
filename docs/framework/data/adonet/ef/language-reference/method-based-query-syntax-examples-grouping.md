---
title: '메서드 기반 쿼리 구문 예제: 그룹화'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: cb23c25c-1075-4cc3-a8ff-4db72e536c0d
ms.openlocfilehash: 7ade24ecee5a69403f3264a62fbdffdcd9decd3a
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54634478"
---
# <a name="method-based-query-syntax-examples-grouping"></a><span data-ttu-id="0e281-102">메서드 기반 쿼리 구문 예제: 그룹화</span><span class="sxs-lookup"><span data-stu-id="0e281-102">Method-Based Query Syntax Examples: Grouping</span></span>
<span data-ttu-id="0e281-103">이 항목의 예제를 사용 하는 방법을 보여 줍니다.는 `GroupBy` 쿼리 메서드는 [AdventureWorks Sales 모델](https://msdn.microsoft.com/library/f16cd988-673f-4376-b034-129ca93c7832) 메서드 기반 쿼리 구문을 사용 하 여 합니다.</span><span class="sxs-lookup"><span data-stu-id="0e281-103">The examples in this topic show you how to use the `GroupBy` method to query the [AdventureWorks Sales Model](https://msdn.microsoft.com/library/f16cd988-673f-4376-b034-129ca93c7832) using method-based query syntax.</span></span> <span data-ttu-id="0e281-104">이 예제에서 사용하는 AdventureWorks Sales 모델에서는 AdventureWorks 샘플 데이터베이스의 Contact, Address, Product, SalesOrderHeader 및 SalesOrderDetail 테이블을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="0e281-104">The AdventureWorks Sales Model that is used in these examples is built from the Contact, Address, Product, SalesOrderHeader, and SalesOrderDetail tables in the AdventureWorks sample database.</span></span>  
  
 <span data-ttu-id="0e281-105">이 항목의 예제에서는 다음을 사용 `using` / `Imports` 문:</span><span class="sxs-lookup"><span data-stu-id="0e281-105">The examples in this topic use the following `using`/`Imports` statements:</span></span>  
  
 [!code-csharp[DP L2E Examples#ImportsUsing](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#importsusing)]
 [!code-vb[DP L2E Examples#ImportsUsing](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#importsusing)]  
  
## <a name="example"></a><span data-ttu-id="0e281-106">예제</span><span class="sxs-lookup"><span data-stu-id="0e281-106">Example</span></span>  
 <span data-ttu-id="0e281-107">다음 예제에서는 `GroupBy` 메서드를 사용하여 우편 번호별로 그룹화된 `Address` 개체를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="0e281-107">The following example uses the `GroupBy` method to return `Address` objects that are grouped by postal code.</span></span> <span data-ttu-id="0e281-108">결과는 익명 형식으로 프로젝션됩니다.</span><span class="sxs-lookup"><span data-stu-id="0e281-108">The results are projected into an anonymous type.</span></span>  
  
 [!code-csharp[DP L2E Examples#GroupBySimple3_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#groupbysimple3_mq)]
 [!code-vb[DP L2E Examples#GroupBySimple3_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#groupbysimple3_mq)]  
  
## <a name="example"></a><span data-ttu-id="0e281-109">예제</span><span class="sxs-lookup"><span data-stu-id="0e281-109">Example</span></span>  
 <span data-ttu-id="0e281-110">다음 예제에서는 `GroupBy` 메서드를 사용하여 연락처 성의 첫 번째 문자로 그룹화된 `Contact` 개체를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="0e281-110">The following example uses the `GroupBy` method to return `Contact` objects that are grouped by the first letter of the contact's last name.</span></span> <span data-ttu-id="0e281-111">또한 결과는 성의 첫 번째 문자별로 정렬되며 익명 형식으로 프로젝션됩니다.</span><span class="sxs-lookup"><span data-stu-id="0e281-111">The results are also sorted by the first letter of the last name and projected into an anonymous type.</span></span>  
  
 [!code-csharp[DP L2E Examples#GroupBySimple2_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#groupbysimple2_mq)]
 [!code-vb[DP L2E Examples#GroupBySimple2_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#groupbysimple2_mq)]  
  
## <a name="example"></a><span data-ttu-id="0e281-112">예제</span><span class="sxs-lookup"><span data-stu-id="0e281-112">Example</span></span>  
 <span data-ttu-id="0e281-113">다음 예제에서는 `GroupBy` 메서드를 사용하여 고객 ID별로 그룹화된 `SalesOrderHeader` 개체를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="0e281-113">The following example uses the `GroupBy` method to return `SalesOrderHeader` objects that are grouped by customer ID.</span></span> <span data-ttu-id="0e281-114">또한 고객별 판매 수량도 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="0e281-114">The number of sales for each customer is also returned.</span></span>  
  
 [!code-csharp[DP L2E Examples#GroupByCount_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#groupbycount_mq)]
 [!code-vb[DP L2E Examples#GroupByCount_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#groupbycount_mq)]  
  
## <a name="see-also"></a><span data-ttu-id="0e281-115">참고자료</span><span class="sxs-lookup"><span data-stu-id="0e281-115">See also</span></span>
- [<span data-ttu-id="0e281-116">LINQ to Entities에서 쿼리</span><span class="sxs-lookup"><span data-stu-id="0e281-116">Queries in LINQ to Entities</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/queries-in-linq-to-entities.md)
