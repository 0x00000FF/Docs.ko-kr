---
title: "메서드 기반 쿼리 구문 예제: ELEMENT 연산자"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: 8438b995-bd07-4223-b22d-13adadef33fb
caps.latest.revision: 
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload:
- dotnet
ms.openlocfilehash: 87f5a12511a2a33e6a3d3321e69fa92fe6b1206d
ms.sourcegitcommit: cf22b29db780e532e1090c6e755aa52d28273fa6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/01/2018
---
# <a name="method-based-query-syntax-examples-element-operators"></a><span data-ttu-id="7c36d-102">메서드 기반 쿼리 구문 예제: ELEMENT 연산자</span><span class="sxs-lookup"><span data-stu-id="7c36d-102">Method-Based Query Syntax Examples: Element Operators</span></span>
<span data-ttu-id="7c36d-103">이 항목의 예제에 사용 하는 방법을 보여 주기는 <xref:System.Linq.Enumerable.First%2A> 메서드 쿼리를는 [AdventureWorks Sales 모델](http://msdn.microsoft.com/library/f16cd988-673f-4376-b034-129ca93c7832) 메서드 기반 쿼리 구문을 사용 하 여 합니다.</span><span class="sxs-lookup"><span data-stu-id="7c36d-103">The examples in this topic demonstrate how to use the <xref:System.Linq.Enumerable.First%2A> method to query the [AdventureWorks Sales Model](http://msdn.microsoft.com/library/f16cd988-673f-4376-b034-129ca93c7832) using method-based query syntax.</span></span> <span data-ttu-id="7c36d-104">이 예제에서 사용하는 AdventureWorks Sales 모델에서는 AdventureWorks 샘플 데이터베이스의 Contact, Address, Product, SalesOrderHeader 및 SalesOrderDetail 테이블을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="7c36d-104">The AdventureWorks Sales Model used in these examples is built from the Contact, Address, Product, SalesOrderHeader, and SalesOrderDetail tables in the AdventureWorks sample database.</span></span>  
  
 <span data-ttu-id="7c36d-105">이 항목의 예제에서는 다음 `using` / `Imports` 문:</span><span class="sxs-lookup"><span data-stu-id="7c36d-105">The example in this topic uses the following `using`/`Imports` statements:</span></span>  
  
 [!code-csharp[DP L2E Examples#ImportsUsing](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#importsusing)]
 [!code-vb[DP L2E Examples#ImportsUsing](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#importsusing)]  
  
## <a name="first"></a><span data-ttu-id="7c36d-106">First</span><span class="sxs-lookup"><span data-stu-id="7c36d-106">First</span></span>  
  
### <a name="example"></a><span data-ttu-id="7c36d-107">예</span><span class="sxs-lookup"><span data-stu-id="7c36d-107">Example</span></span>  
 <span data-ttu-id="7c36d-108">다음 예제에서는 <xref:System.Linq.Enumerable.First%2A> 'caroline'으로 시작 되는 첫 번째 전자 메일 주소를 찾으려면 메서드.</span><span class="sxs-lookup"><span data-stu-id="7c36d-108">The following example uses the <xref:System.Linq.Enumerable.First%2A> method to find the first email address that starts with 'caroline'.</span></span>  
  
 [!code-csharp[DP L2E Examples#FirstCondition_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#firstcondition_mq)]
 [!code-vb[DP L2E Examples#FirstCondition_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#firstcondition_mq)]  
  
## <a name="see-also"></a><span data-ttu-id="7c36d-109">참고 항목</span><span class="sxs-lookup"><span data-stu-id="7c36d-109">See Also</span></span>  
 [<span data-ttu-id="7c36d-110">LINQ to Entities에서 쿼리</span><span class="sxs-lookup"><span data-stu-id="7c36d-110">Queries in LINQ to Entities</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/queries-in-linq-to-entities.md)
