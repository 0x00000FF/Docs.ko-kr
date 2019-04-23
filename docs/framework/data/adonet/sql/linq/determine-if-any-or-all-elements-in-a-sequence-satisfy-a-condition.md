---
title: 시퀀스에서 일부 또는 모든 요소가 조건을 만족하는지 확인
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 339ec145-826c-46d2-8cf2-3acd252cd072
ms.openlocfilehash: c1bc8e18f2e3b0c67b98713e67fc261649a6a0e2
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59128338"
---
# <a name="determine-if-any-or-all-elements-in-a-sequence-satisfy-a-condition"></a>시퀀스에서 일부 또는 모든 요소가 조건을 만족하는지 확인
시퀀스의 모든 요소가 조건을 만족하면 <xref:System.Linq.Enumerable.All%2A> 연산자에서는 `true`를 반환합니다.  
  
 시퀀스의 모든 요소가 조건을 만족하면 <xref:System.Linq.Queryable.Any%2A> 연산자에서는 `true`를 반환합니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 적어도 하나의 주문이 있는 고객의 시퀀스를 반환합니다. 합니다 `Where` / `where` 절 `true` 경우는 지정 된 `Customer` 있는지 `Order`합니다.  
  
 [!code-csharp[DLinqQueryExamples#37](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#37)]
 [!code-vb[DLinqQueryExamples#37](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#37)]  
  
## <a name="example"></a>예제  
 다음 Visual Basic 코드에서는 주문을 하지 않은 고객의 목록을 확인하고 해당 목록에 있는 모든 고객에 대한 연락처 이름을 제공합니다.  
  
 [!code-vb[DLinqQueryExamples#37v](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#37v)]  
  
## <a name="example"></a>예제  
 다음 C# 예제에서는 "C"로 시작하는 `ShipCity`가 있는 주문의 고객 시퀀스를 반환합니다. 또한 반환에는 주문이 없는 고객도 포함됩니다. 디자인에 따라 <xref:System.Linq.Queryable.All%2A> 연산자는 빈 시퀀스에 대해 `true`를 반환합니다. 주문이 없는 고객은 `Count` 연산자를 사용하여 콘솔 결과에서 제거됩니다.  
  
 [!code-csharp[DLinqQueryExamples#38](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#38)]  
  
## <a name="see-also"></a>참고자료

- [쿼리 예제](../../../../../../docs/framework/data/adonet/sql/linq/query-examples.md)
