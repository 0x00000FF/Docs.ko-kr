---
title: '방법: 저장소 및 재사용 쿼리'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: a012bd79-1809-45e3-adea-0229532396cc
ms.openlocfilehash: a913839ab8e6048b18270061a75ca632e2797fb8
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54630773"
---
# <a name="how-to-store-and-reuse-queries"></a>방법: 저장소 및 재사용 쿼리
구조적으로 유사한 쿼리를 여러 번 실행하는 응용 프로그램이 있는 경우 일반적으로 쿼리를 한 번 컴파일하고 다른 매개 변수와 함께 여러 번 실행하여 성능을 향상시킬 수 있습니다. 예를 들어, 응용 프로그램에서 특정 도시의 모든 고객을 검색해야 하며 사용자가 런타임에 양식에서 도시를 지정하는 경우를 생각해 봅니다. [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] 사용을 지원 *컴파일된 쿼리* 이 목적입니다.  
  
> [!NOTE]
>  이 사용 패턴은 컴파일된 쿼리가 사용되는 가장 일반적인 방식입니다. 다른 방법도 가능합니다. 예를 들어, 디자이너에 의해 생성된 코드를 확장하는 partial 클래스에서 컴파일된 쿼리를 정적 멤버로 저장할 수 있습니다.  
  
## <a name="example"></a>예제  
 대부분의 시나리오에서는 스레드 경계를 넘어 쿼리를 다시 사용할 수 있습니다. 이러한 경우 컴파일된 쿼리를 정적 변수에 저장하는 것이 특히 효과적입니다. 다음 코드 예제에서는 컴파일된 쿼리를 저장하도록 디자인된 `Queries` 클래스를 가정하고 강력한 형식의 <xref:System.Data.Linq.DataContext>를 나타내는 Northwind 클래스를 가정합니다.  
  
 [!code-csharp[DLinqQuerying#6](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQuerying/cs/Program.cs#6)]
 [!code-vb[DLinqQuerying#6](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQuerying/vb/Module1.vb#6)]  
  
 [!code-csharp[DLinqQuerying#7](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQuerying/cs/Program.cs#7)]
 [!code-vb[DLinqQuerying#7](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQuerying/vb/Module1.vb#7)]  
  
## <a name="example"></a>예제  
 먼저 반환 하는 쿼리 저장소 (정적 변수)에 현재는 *무명 형식*이므로 형식에 제네릭 인수로 제공할 이름이 없습니다. 다음 예제에서는 결과를 나타낼 수 있는 형식을 만든 다음 이를 제네릭 인수로 사용하여 이 문제를 해결할 수 있는 방법을 보여 줍니다.  
  
 [!code-csharp[DLinqQuerying#8](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQuerying/cs/Program.cs#8)]
 [!code-vb[DLinqQuerying#8](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQuerying/vb/Module1.vb#8)]  
  
## <a name="see-also"></a>참고자료
- <xref:System.Data.Linq.CompiledQuery>
- [쿼리 개념](../../../../../../docs/framework/data/adonet/sql/linq/query-concepts.md)
- [데이터베이스 쿼리](../../../../../../docs/framework/data/adonet/sql/linq/querying-the-database.md)
