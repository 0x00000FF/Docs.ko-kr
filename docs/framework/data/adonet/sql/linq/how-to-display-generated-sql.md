---
title: '방법: 생성된 SQL 표시'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 626492c0-5ee3-4675-88e8-8c40379510b6
ms.openlocfilehash: edc0f8fea2768391a47e12940cbe083e41852f1f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33361710"
---
# <a name="how-to-display-generated-sql"></a><span data-ttu-id="d2afc-102">방법: 생성된 SQL 표시</span><span class="sxs-lookup"><span data-stu-id="d2afc-102">How to: Display Generated SQL</span></span>
<span data-ttu-id="d2afc-103"><xref:System.Data.Linq.DataContext.Log%2A> 속성을 사용하여 쿼리에 대해 생성된 SQL 코드를 보고 프로세스를 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d2afc-103">You can view the SQL code generated for queries and change processing by using the <xref:System.Data.Linq.DataContext.Log%2A> property.</span></span> <span data-ttu-id="d2afc-104">이러한 접근 방식은 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] 기능을 이해하고 특정 문제를 디버깅하는 데 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="d2afc-104">This approach can be useful for understanding [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] functionality and for debugging specific problems.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d2afc-105">예제</span><span class="sxs-lookup"><span data-stu-id="d2afc-105">Example</span></span>  
 <span data-ttu-id="d2afc-106">다음 예제에서는 <xref:System.Data.Linq.DataContext.Log%2A> 속성을 사용하여 코드를 실행하기 전에 콘솔 창에 SQL 코드를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="d2afc-106">The following example uses the <xref:System.Data.Linq.DataContext.Log%2A> property to display SQL code in the console window before the code is executed.</span></span>  <span data-ttu-id="d2afc-107">이 속성은 쿼리, 삽입, 업데이트 및 삭제 명령과 함께 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d2afc-107">You can use this property with query, insert, update, and delete commands.</span></span>  
  
 <span data-ttu-id="d2afc-108">콘솔 창에서 선은 뒤에 Visual Basic 또는 C# 코드를 실행할 때 나타나는입니다.</span><span class="sxs-lookup"><span data-stu-id="d2afc-108">The lines from the console window are what you see when you execute the Visual Basic or C# code that follows.</span></span>  
  
```  
SELECT [t0].[CustomerID], [t0].[CompanyName], [t0].[ContactName], [t0].[ContactT  
itle], [t0].[Address], [t0].[City], [t0].[Region], [t0].[PostalCode], [t0].[Coun  
try], [t0].[Phone], [t0].[Fax]  
FROM [dbo].[Customers] AS [t0]  
WHERE [t0].[City] = @p0  
-- @p0: Input String (Size = 6; Prec = 0; Scale = 0) [London]  
-- Context: SqlProvider(Sql2005) Model: AttributedMetaModel Build: 3.5.20810.0  
```  
  
```  
AROUT  
BSBEV  
CONSH  
EASTC  
NORTS  
SEVES  
```  
  
 [!code-csharp[DLinqDebuggingSupport#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqDebuggingSupport/cs/Program.cs#1)]
 [!code-vb[DLinqDebuggingSupport#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqDebuggingSupport/vb/Module1.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="d2afc-109">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d2afc-109">See Also</span></span>  
 [<span data-ttu-id="d2afc-110">디버깅 지원</span><span class="sxs-lookup"><span data-stu-id="d2afc-110">Debugging Support</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/debugging-support.md)
