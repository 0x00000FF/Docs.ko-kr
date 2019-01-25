---
title: '방법: 사용자 정의 함수 인라인 호출'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: f80d4327-b6a5-4aa8-a743-e95d09a2a02e
ms.openlocfilehash: 76a41ded52ac29b4a8b597188171333a888be5cd
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54692771"
---
# <a name="how-to-call-user-defined-functions-inline"></a><span data-ttu-id="1501d-102">방법: 사용자 정의 함수 인라인 호출</span><span class="sxs-lookup"><span data-stu-id="1501d-102">How to: Call User-Defined Functions Inline</span></span>
<span data-ttu-id="1501d-103">사용자 정의 함수를 인라인으로 호출할 수 있지만 실행이 지연된 쿼리에 포함된 함수는 쿼리가 실행될 때까지 실행되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1501d-103">Although you can call user-defined functions inline, functions that are included in a query whose execution is deferred are not executed until the query is executed.</span></span> <span data-ttu-id="1501d-104">자세한 내용은 [LINQ 쿼리 소개(C#)](~/docs/csharp/programming-guide/concepts/linq/introduction-to-linq-queries.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="1501d-104">For more information, see [Introduction to LINQ Queries (C#)](~/docs/csharp/programming-guide/concepts/linq/introduction-to-linq-queries.md).</span></span>  
  
 <span data-ttu-id="1501d-105">쿼리 외부에 있는 동일한 함수를 호출할 경우 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]에서는 메서드 호출 식에서 단순한 쿼리를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="1501d-105">When you call the same function outside a query, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] creates a simple query from the method call expression.</span></span> <span data-ttu-id="1501d-106">다음은 전달된 상수에 매개 변수 `@p0`가 바인딩되는 SQL 구문입니다.</span><span class="sxs-lookup"><span data-stu-id="1501d-106">The following is the SQL syntax (the parameter `@p0` is bound to the constant passed in):</span></span>  
  
```  
SELECT dbo.ReverseCustName(@p0)  
```  
  
 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]<span data-ttu-id="1501d-107">에서는 다음을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="1501d-107">creates the following:</span></span>  
  
 [!code-csharp[DLinqUDFS#4](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqUDFS/cs/Program.cs#4)]
 [!code-vb[DLinqUDFS#4](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqUDFS/vb/Module1.vb#4)]  
  
## <a name="example"></a><span data-ttu-id="1501d-108">예제</span><span class="sxs-lookup"><span data-stu-id="1501d-108">Example</span></span>  
 <span data-ttu-id="1501d-109">다음 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] 쿼리에서 생성된 사용자 정의 함수 메서드 `ReverseCustName`에 대한 인라인 호출을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1501d-109">In the following [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] query, you can see an inline call to the generated user-defined function method `ReverseCustName`.</span></span> <span data-ttu-id="1501d-110">쿼리 실행이 지연되었기에 함수는 즉시 실행되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1501d-110">The function is not executed immediately because query execution is deferred.</span></span> <span data-ttu-id="1501d-111">이 쿼리에 대해 빌드된 SQL은 데이터베이스에서 사용자 정의 함수에 대한 호출로 변환됩니다. 다음 쿼리의 SQL 코드를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="1501d-111">The SQL built for this query translates to a call to the user-defined function in the database (see the SQL code following the query).</span></span>  
  
 [!code-csharp[DLinqUDFS#5](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqUDFS/cs/Program.cs#5)]
 [!code-vb[DLinqUDFS#5](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqUDFS/vb/Module1.vb#5)]  
  
```  
SELECT [t0].[ContactName],  
    dbo.ReverseCustName([t0].[ContactTitle]) AS [Title]  
FROM [Customers] AS [t0]  
```  
  
## <a name="see-also"></a><span data-ttu-id="1501d-112">참고자료</span><span class="sxs-lookup"><span data-stu-id="1501d-112">See also</span></span>
- [<span data-ttu-id="1501d-113">사용자 정의 함수</span><span class="sxs-lookup"><span data-stu-id="1501d-113">User-Defined Functions</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/user-defined-functions.md)
