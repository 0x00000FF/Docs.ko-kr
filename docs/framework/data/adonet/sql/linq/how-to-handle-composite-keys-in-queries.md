---
title: '방법: 쿼리에서 복합 키 처리'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: ce2f14fd-1038-458a-91e3-a078c61f0d10
ms.openlocfilehash: 2621ab4db207d1b868fbe3778c30c744201b0506
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59135254"
---
# <a name="how-to-handle-composite-keys-in-queries"></a>방법: 쿼리에서 복합 키 처리
일부 연산자는 인수를 하나만 받아들일 수 있습니다. 인수가 데이터베이스에서 둘 이상의 열을 포함하는 경우 조합을 나타내는 익명 형식을 만들어야 합니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 `GroupBy` 인수를 하나만 사용하는 `key` 연산자를 호출하는 쿼리를 보여 줍니다.  
  
 [!code-csharp[DLinqCompositeKeys#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqCompositeKeys/cs/Program.cs#1)]
 [!code-vb[DLinqCompositeKeys#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqCompositeKeys/vb/Module1.vb#1)]  
  
## <a name="example"></a>예제  
 다음 예제와 같이 동일한 경우 조인과 관련이 있습니다.  
  
 [!code-csharp[DLinqCompositeKeys#2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqCompositeKeys/cs/Program.cs#2)]
 [!code-vb[DLinqCompositeKeys#2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqCompositeKeys/vb/Module1.vb#2)]  
  
## <a name="see-also"></a>참고자료

- [쿼리 개념](../../../../../../docs/framework/data/adonet/sql/linq/query-concepts.md)
