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
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 69b711802d04e005095167db7df544e0f00d0b19
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-filter-at-the-datacontext-level"></a>방법: DataContext 수준에서 필터링
`EntitySets` 수준에서 `DataContext`를 필터링할 수 있습니다. 이러한 필터는 <xref:System.Data.Linq.DataContext> 인스턴스로 수행되는 모든 쿼리에 적용됩니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 <xref:System.Data.Linq.DataLoadOptions.AssociateWith%28System.Linq.Expressions.LambdaExpression%29?displayProperty=nameWithType> 기준으로 고객의 미리 로드된 주문을 필터링하기 위해 `ShippedDate`가 사용됩니다.  
  
 [!code-csharp[DLinqQueryConcepts#10](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryConcepts/cs/Program.cs#10)]
 [!code-vb[DLinqQueryConcepts#10](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryConcepts/vb/Module1.vb#10)]  
  
## <a name="see-also"></a>참고 항목  
 [쿼리 개념](../../../../../../docs/framework/data/adonet/sql/linq/query-concepts.md)
