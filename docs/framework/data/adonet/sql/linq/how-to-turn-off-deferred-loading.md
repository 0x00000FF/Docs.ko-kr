---
title: '방법: 지연 콘텐츠 해제'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 1b84b852-3cad-41a7-8077-149a70d50c8b
ms.openlocfilehash: f82e347ecdb3c69cee3749855d1e4cb457a460f6
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62033620"
---
# <a name="how-to-turn-off-deferred-loading"></a><span data-ttu-id="850f0-102">방법: 지연 콘텐츠 해제</span><span class="sxs-lookup"><span data-stu-id="850f0-102">How to: Turn Off Deferred Loading</span></span>
<span data-ttu-id="850f0-103"><xref:System.Data.Linq.DataContext.DeferredLoadingEnabled%2A>를 `false`로 설정하여 지연된 로드를 해제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="850f0-103">You can turn off deferred loading by setting <xref:System.Data.Linq.DataContext.DeferredLoadingEnabled%2A> to `false`.</span></span> <span data-ttu-id="850f0-104">자세한 내용은 [즉시 로드 비교 지연](../../../../../../docs/framework/data/adonet/sql/linq/deferred-versus-immediate-loading.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="850f0-104">For more information, see [Deferred versus Immediate Loading](../../../../../../docs/framework/data/adonet/sql/linq/deferred-versus-immediate-loading.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="850f0-105">개체 추적이 해제되면 지연된 로드는 암시적으로 해제된 것입니다.</span><span class="sxs-lookup"><span data-stu-id="850f0-105">Deferred loading is turned off by implication when object tracking is turned off.</span></span> <span data-ttu-id="850f0-106">자세한 내용은 [방법: 읽기 전용으로 정보를 검색할](../../../../../../docs/framework/data/adonet/sql/linq/how-to-retrieve-information-as-read-only.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="850f0-106">For more information, see [How to: Retrieve Information As Read-Only](../../../../../../docs/framework/data/adonet/sql/linq/how-to-retrieve-information-as-read-only.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="850f0-107">예제</span><span class="sxs-lookup"><span data-stu-id="850f0-107">Example</span></span>  
 <span data-ttu-id="850f0-108">다음 예제에서는 <xref:System.Data.Linq.DataContext.DeferredLoadingEnabled%2A>를 `false`로 설정하여 지연된 로드를 해제하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="850f0-108">The following example shows how to turn off deferred loading by setting <xref:System.Data.Linq.DataContext.DeferredLoadingEnabled%2A> to `false`.</span></span>  
  
 [!code-csharp[DLinqQuerying#3](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQuerying/cs/Program.cs#3)]
 [!code-vb[DLinqQuerying#3](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQuerying/vb/Module1.vb#3)]  
  
## <a name="see-also"></a><span data-ttu-id="850f0-109">참고자료</span><span class="sxs-lookup"><span data-stu-id="850f0-109">See also</span></span>

- [<span data-ttu-id="850f0-110">쿼리 개념</span><span class="sxs-lookup"><span data-stu-id="850f0-110">Query Concepts</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/query-concepts.md)
- [<span data-ttu-id="850f0-111">데이터베이스 쿼리</span><span class="sxs-lookup"><span data-stu-id="850f0-111">Querying the Database</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/querying-the-database.md)
