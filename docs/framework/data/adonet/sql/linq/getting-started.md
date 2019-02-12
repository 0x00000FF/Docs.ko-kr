---
title: 시작
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: db8a557a-fef8-4f4f-bb91-8cff7250ee25
ms.openlocfilehash: 50b6d6992664f4b0a87984af8243b195fc479b8a
ms.sourcegitcommit: d2ccb199ae6bc5787b4762e9ea6d3f6fe88677af
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/12/2019
ms.locfileid: "56091580"
---
# <a name="getting-started"></a><span data-ttu-id="dde96-102">시작</span><span class="sxs-lookup"><span data-stu-id="dde96-102">Getting Started</span></span>
<span data-ttu-id="dde96-103">사용 하 여 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]를 사용할 수는 [!INCLUDE[vbteclinq](../../../../../../includes/vbteclinq-md.md)] 메모리 내 컬렉션을 액세스 하는 것 처럼 데이터베이스를 SQL에 액세스 하는 기술입니다.</span><span class="sxs-lookup"><span data-stu-id="dde96-103">By using [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], you can use the [!INCLUDE[vbteclinq](../../../../../../includes/vbteclinq-md.md)] technology to access SQL databases just as you would access an in-memory collection.</span></span>  
  
 <span data-ttu-id="dde96-104">예를 들어 다음 코드에서 `nw` 개체는 `Northwind` 데이터베이스를 나타내기 위해 만든 것으로 `Customers` 테이블을 대상으로 열은 `Customers`에서 `London`가 필터링되고 `CompanyName`에 대한 문자열은 검색용으로 선택됩니다.</span><span class="sxs-lookup"><span data-stu-id="dde96-104">For example, the `nw` object in the following code is created to represent the `Northwind` database, the `Customers` table is targeted, the rows are filtered for `Customers` from `London`, and a string for `CompanyName` is selected for retrieval.</span></span>  
  
 <span data-ttu-id="dde96-105">루프가 실행되면 `CompanyName` 값의 컬렉션이 검색됩니다.</span><span class="sxs-lookup"><span data-stu-id="dde96-105">When the loop is executed, the collection of `CompanyName` values is retrieved.</span></span>  
  
 [!code-csharp[DLinqGettingStarted#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqGettingStarted/cs/Program.cs#1)]
 [!code-vb[DLinqGettingStarted#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqGettingStarted/vb/Module1.vb#1)]  
  
## <a name="next-steps"></a><span data-ttu-id="dde96-106">다음 단계</span><span class="sxs-lookup"><span data-stu-id="dde96-106">Next Steps</span></span>  
 <span data-ttu-id="dde96-107">삽입 및 업데이트를 비롯 한 몇 가지 추가 예제를 참조 하세요 [어떤 있습니다 수 수행 된 LINQ to SQL](../../../../../../docs/framework/data/adonet/sql/linq/what-you-can-do-with-linq-to-sql.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="dde96-107">For some additional examples, including inserting and updating, see [What You Can Do With LINQ to SQL](../../../../../../docs/framework/data/adonet/sql/linq/what-you-can-do-with-linq-to-sql.md).</span></span>  
  
 <span data-ttu-id="dde96-108">그런 다음 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]을 사용하는 실제 경험을 가지는 연습과 자습서를 시도해 보세요.</span><span class="sxs-lookup"><span data-stu-id="dde96-108">Next, try some walkthroughs and tutorials to have a hands-on experience of using [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span></span> <span data-ttu-id="dde96-109">참조 [연습으로 학습](../../../../../../docs/framework/data/adonet/sql/linq/learning-by-walkthroughs.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="dde96-109">See [Learning by Walkthroughs](../../../../../../docs/framework/data/adonet/sql/linq/learning-by-walkthroughs.md).</span></span>  
  
 <span data-ttu-id="dde96-110">마지막으로 직접 시작 하는 방법에 알아봅니다 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] 프로젝트를 읽으면 [LINQ to SQL 사용을 위한 일반 단계](../../../../../../docs/framework/data/adonet/sql/linq/typical-steps-for-using-linq-to-sql.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="dde96-110">Finally, learn how to get started on your own [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] project by reading [Typical Steps for Using LINQ to SQL](../../../../../../docs/framework/data/adonet/sql/linq/typical-steps-for-using-linq-to-sql.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dde96-111">참고자료</span><span class="sxs-lookup"><span data-stu-id="dde96-111">See also</span></span>
- [<span data-ttu-id="dde96-112">LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="dde96-112">LINQ to SQL</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/index.md)
- [<span data-ttu-id="dde96-113">LINQ 소개 (C#)</span><span class="sxs-lookup"><span data-stu-id="dde96-113">Introduction to LINQ (C#)</span></span>](../../../../../csharp/programming-guide/concepts/linq/introduction-to-linq.md)
- [<span data-ttu-id="dde96-114">LINQ 소개(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="dde96-114">Introduction to LINQ (Visual Basic)</span></span>](../../../../../visual-basic/programming-guide/concepts/linq/introduction-to-linq.md)
- [<span data-ttu-id="dde96-115">LINQ to SQL 개체 모델</span><span class="sxs-lookup"><span data-stu-id="dde96-115">The LINQ to SQL Object Model</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/the-linq-to-sql-object-model.md)
