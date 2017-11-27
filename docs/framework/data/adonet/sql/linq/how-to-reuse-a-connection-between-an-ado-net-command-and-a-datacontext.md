---
title: "방법: ADO.NET 명령 및 DataContext 사이에 연결 다시 사용"
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
ms.assetid: 7e26c7eb-c18a-43b5-a8f0-28fd8b04b0f0
caps.latest.revision: "2"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 483a97817162140af61df6a58c3e9ab003235c74
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-reuse-a-connection-between-an-adonet-command-and-a-datacontext"></a><span data-ttu-id="ff1fe-102">방법: ADO.NET 명령 및 DataContext 사이에 연결 다시 사용</span><span class="sxs-lookup"><span data-stu-id="ff1fe-102">How to: Reuse a Connection Between an ADO.NET Command and a DataContext</span></span>
<span data-ttu-id="ff1fe-103">때문에 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] 의 일부인는 [!INCLUDE[vstecado](../../../../../../includes/vstecado-md.md)] 기술 제품군의 제공 하는 서비스를 기반으로 하 고 [!INCLUDE[vstecado](../../../../../../includes/vstecado-md.md)], 사이의 연결을 다시 사용할 수는 [!INCLUDE[vstecado](../../../../../../includes/vstecado-md.md)] 명령 및 <xref:System.Data.Linq.DataContext>합니다.</span><span class="sxs-lookup"><span data-stu-id="ff1fe-103">Because [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] is a part of the [!INCLUDE[vstecado](../../../../../../includes/vstecado-md.md)] family of technologies and is based on services provided by [!INCLUDE[vstecado](../../../../../../includes/vstecado-md.md)], you can reuse a connection between an [!INCLUDE[vstecado](../../../../../../includes/vstecado-md.md)] command and a <xref:System.Data.Linq.DataContext>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ff1fe-104">예제</span><span class="sxs-lookup"><span data-stu-id="ff1fe-104">Example</span></span>  
 <span data-ttu-id="ff1fe-105">다음 예제에서는 [!INCLUDE[vstecado](../../../../../../includes/vstecado-md.md)] 명령과 <xref:System.Data.Linq.DataContext> 간에 동일한 연결을 다시 사용하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="ff1fe-105">The following example shows how to reuse the same connection between an [!INCLUDE[vstecado](../../../../../../includes/vstecado-md.md)] command and the <xref:System.Data.Linq.DataContext>.</span></span>  
  
 [!code-csharp[DLinqCommunicatingWithDatabase#4](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqCommunicatingWithDatabase/cs/Program.cs#4)]
 [!code-vb[DLinqCommunicatingWithDatabase#4](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqCommunicatingWithDatabase/vb/Module1.vb#4)]  
  
## <a name="see-also"></a><span data-ttu-id="ff1fe-106">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ff1fe-106">See Also</span></span>  
 [<span data-ttu-id="ff1fe-107">배경 정보</span><span class="sxs-lookup"><span data-stu-id="ff1fe-107">Background Information</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/background-information.md)  
 [<span data-ttu-id="ff1fe-108">ADO.NET 및 LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="ff1fe-108">ADO.NET and LINQ to SQL</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/ado-net-and-linq-to-sql.md)  
 [<span data-ttu-id="ff1fe-109">데이터베이스와 통신</span><span class="sxs-lookup"><span data-stu-id="ff1fe-109">Communicating with the Database</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/communicating-with-the-database.md)
