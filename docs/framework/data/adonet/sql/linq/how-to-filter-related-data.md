---
title: "방법: 관련 데이터 필터링"
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
ms.assetid: ec8b8f97-5d01-4f31-9b97-d1556df6a4bc
caps.latest.revision: "2"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 2f02b09cc5389a90ea42a0dd851579327972c20c
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-filter-related-data"></a><span data-ttu-id="d57dd-102">방법: 관련 데이터 필터링</span><span class="sxs-lookup"><span data-stu-id="d57dd-102">How to: Filter Related Data</span></span>
<span data-ttu-id="d57dd-103"><xref:System.Data.Linq.DataLoadOptions.AssociateWith%2A> 메서드를 사용하여 검색된 데이터의 양을 제한하기 위한 하위 쿼리를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="d57dd-103">Use the <xref:System.Data.Linq.DataLoadOptions.AssociateWith%2A> method to specify sub-queries to limit the amount of retrieved data.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d57dd-104">예제</span><span class="sxs-lookup"><span data-stu-id="d57dd-104">Example</span></span>  
 <span data-ttu-id="d57dd-105">다음 예제에서 <xref:System.Data.Linq.DataLoadOptions.AssociateWith%2A> 메서드는 `Orders`를 오늘 선적되지 되지 않은 것으로 제한합니다.</span><span class="sxs-lookup"><span data-stu-id="d57dd-105">In the following example, the <xref:System.Data.Linq.DataLoadOptions.AssociateWith%2A> method limits the `Orders` retrieved to those that have not been shipped today.</span></span> <span data-ttu-id="d57dd-106">이 방법을 사용하지 않을 경우 한 개의 하위 집합만 필요한 경우에도 모든 `Orders`가 검색됩니다.</span><span class="sxs-lookup"><span data-stu-id="d57dd-106">Without this approach, all `Orders` would have been retrieved even though only a subset is desired.</span></span>  
  
 [!code-csharp[System.Data.Linq.DataLoadOptions#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/system.data.linq.dataloadoptions/cs/program.cs#1)]
 [!code-vb[System.Data.Linq.DataLoadOptions#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/system.data.linq.dataloadoptions/vb/module1.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="d57dd-107">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d57dd-107">See Also</span></span>  
 [<span data-ttu-id="d57dd-108">데이터베이스 쿼리</span><span class="sxs-lookup"><span data-stu-id="d57dd-108">Querying the Database</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/querying-the-database.md)
