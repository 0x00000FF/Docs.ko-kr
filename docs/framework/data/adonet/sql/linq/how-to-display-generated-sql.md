---
title: '방법: 생성된 SQL 표시'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 626492c0-5ee3-4675-88e8-8c40379510b6
ms.openlocfilehash: 15fc6a50d232ea12b229b7b2790c0398bc1c370d
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/07/2019
ms.locfileid: "72002972"
---
# <a name="how-to-display-generated-sql"></a><span data-ttu-id="22325-102">방법: 생성된 SQL 표시</span><span class="sxs-lookup"><span data-stu-id="22325-102">How to: Display Generated SQL</span></span>
<span data-ttu-id="22325-103"><xref:System.Data.Linq.DataContext.Log%2A> 속성을 사용하여 쿼리에 대해 생성된 SQL 코드를 보고 프로세스를 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="22325-103">You can view the SQL code generated for queries and change processing by using the <xref:System.Data.Linq.DataContext.Log%2A> property.</span></span> <span data-ttu-id="22325-104">이러한 접근 방식은 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] 기능을 이해하고 특정 문제를 디버깅하는 데 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="22325-104">This approach can be useful for understanding [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] functionality and for debugging specific problems.</span></span>  
  
## <a name="example"></a><span data-ttu-id="22325-105">예제</span><span class="sxs-lookup"><span data-stu-id="22325-105">Example</span></span>  
 <span data-ttu-id="22325-106">다음 예제에서는 <xref:System.Data.Linq.DataContext.Log%2A> 속성을 사용하여 코드를 실행하기 전에 콘솔 창에 SQL 코드를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="22325-106">The following example uses the <xref:System.Data.Linq.DataContext.Log%2A> property to display SQL code in the console window before the code is executed.</span></span>  <span data-ttu-id="22325-107">이 속성은 쿼리, 삽입, 업데이트 및 삭제 명령과 함께 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="22325-107">You can use this property with query, insert, update, and delete commands.</span></span>  
  
 <span data-ttu-id="22325-108">콘솔 창의 줄은 다음에 나오는 Visual Basic 또는 C# 코드를 실행할 때 표시 되는 내용입니다.</span><span class="sxs-lookup"><span data-stu-id="22325-108">The lines from the console window are what you see when you execute the Visual Basic or C# code that follows.</span></span>  
  
```console  
SELECT [t0].[CustomerID], [t0].[CompanyName], [t0].[ContactName], [t0].[ContactT  
itle], [t0].[Address], [t0].[City], [t0].[Region], [t0].[PostalCode], [t0].[Coun  
try], [t0].[Phone], [t0].[Fax]  
FROM [dbo].[Customers] AS [t0]  
WHERE [t0].[City] = @p0  
-- @p0: Input String (Size = 6; Prec = 0; Scale = 0) [London]  
-- Context: SqlProvider(Sql2005) Model: AttributedMetaModel Build: 3.5.20810.0  
```  
  
```console  
AROUT  
BSBEV  
CONSH  
EASTC  
NORTS  
SEVES  
```  
  
 [!code-csharp[DLinqDebuggingSupport#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqDebuggingSupport/cs/Program.cs#1)]
 [!code-vb[DLinqDebuggingSupport#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqDebuggingSupport/vb/Module1.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="22325-109">참조</span><span class="sxs-lookup"><span data-stu-id="22325-109">See also</span></span>

- [<span data-ttu-id="22325-110">디버깅 지원</span><span class="sxs-lookup"><span data-stu-id="22325-110">Debugging Support</span></span>](debugging-support.md)
