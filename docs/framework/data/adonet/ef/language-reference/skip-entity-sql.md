---
title: SKIP(Entity SQL)
ms.date: 03/30/2017
ms.assetid: e2139412-8ea4-451b-8f10-91af18dfa3ec
ms.openlocfilehash: 88d4c9c987f451e9a653d5b9c213e7158670ed4b
ms.sourcegitcommit: d6e27023aeaffc4b5a3cb4b88685018d6284ada4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/09/2019
ms.locfileid: "67662128"
---
# <a name="skip-entity-sql"></a><span data-ttu-id="7d91a-102">SKIP(Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="7d91a-102">SKIP (Entity SQL)</span></span>
<span data-ttu-id="7d91a-103">ORDER BY 절의 SKIP 하위 절을 사용하여 물리적 페이징을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7d91a-103">You can perform physical paging by using the SKIP sub-clause in the ORDER BY clause.</span></span> <span data-ttu-id="7d91a-104">SKIP 절은 ORDER BY 절과 별도로 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="7d91a-104">SKIP cannot be used separately from the ORDER BY clause.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7d91a-105">구문</span><span class="sxs-lookup"><span data-stu-id="7d91a-105">Syntax</span></span>  
  
```  
[ SKIP n ]  
```  
  
## <a name="arguments"></a><span data-ttu-id="7d91a-106">인수</span><span class="sxs-lookup"><span data-stu-id="7d91a-106">Arguments</span></span>  
 `n`  
 <span data-ttu-id="7d91a-107">건너뛸 항목의 개수입니다.</span><span class="sxs-lookup"><span data-stu-id="7d91a-107">The number of items to skip.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7d91a-108">설명</span><span class="sxs-lookup"><span data-stu-id="7d91a-108">Remarks</span></span>  
 <span data-ttu-id="7d91a-109">SKIP 식 하위 절이 ORDER BY 절에 있으면 결과는 정렬 지정에 따라 정렬되고 SKIP 식 바로 뒤에 있는 행에서 시작하는 행이 결과 집합에 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="7d91a-109">If a SKIP expression sub-clause is present in an ORDER BY clause, the results will be sorted according the sort specification and the result set will include rows starting from the next row immediately after the SKIP expression.</span></span> <span data-ttu-id="7d91a-110">예를 들어, SKIP 5를 사용하면 처음 다섯 개의 행을 건너뛰고 여섯 번째 행부터 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="7d91a-110">For example, SKIP 5 will skip the first five rows and return from the sixth row forward.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="7d91a-111">TOP 한정자와 SKIP 하위 절이 모두 같은 쿼리 식에 있는 경우 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] 쿼리는 유효하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7d91a-111">An [!INCLUDE[esql](../../../../../../includes/esql-md.md)] query is invalid if both the TOP modifier and the SKIP sub-clause are present in the same query expression.</span></span> <span data-ttu-id="7d91a-112">TOP 식을 변경하여 쿼리를 LIMIT 식에 다시 써야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7d91a-112">The query should be rewritten by changing the TOP expression to the LIMIT expression.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="7d91a-113">SQL Server 2000에서는 키가 아닌 열에 ORDER BY와 함께 SKIP을 사용 하면 잘못 된 결과가 반환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7d91a-113">In SQL Server 2000, using SKIP with ORDER BY on non-key columns might return incorrect results.</span></span> <span data-ttu-id="7d91a-114">키가 아닌 열에 중복 데이터가 있는 경우, 지정된 개수 이상의 행을 건너뛸 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7d91a-114">More than the specified number of rows might be skipped if the non-key column has duplicate data in it.</span></span> <span data-ttu-id="7d91a-115">SQL Server 2000의 SKIP은 변환 하는 방법을 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="7d91a-115">This is due to how SKIP is translated for SQL Server 2000.</span></span> <span data-ttu-id="7d91a-116">예를 들어 다음 코드에서는 `E.NonKeyColumn` 에 중복 값이 있으면 5개가 넘는 행을 건너뛸 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7d91a-116">For example, in the following code more than five rows might be skipped if `E.NonKeyColumn` has duplicate values:</span></span>  
>   
>  `SELECT [E] FROM Container.EntitySet AS [E] ORDER BY [E].[NonKeyColumn] DESC SKIP 5L`  
  
 <span data-ttu-id="7d91a-117">합니다 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] 쿼리 [방법: 쿼리 결과 통해 페이지](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738702(v=vs.100)) SKIP과 함께 ORDER BY 연산자를 사용 하 여 SELECT 문에서 반환 된 개체에서 사용 되는 정렬 순서를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="7d91a-117">The  [!INCLUDE[esql](../../../../../../includes/esql-md.md)] query in [How to: Page Through Query Results](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738702(v=vs.100)) uses the ORDER BY operator with SKIP to specify the sort order used on objects returned in a SELECT statement.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7d91a-118">참고자료</span><span class="sxs-lookup"><span data-stu-id="7d91a-118">See also</span></span>

- [<span data-ttu-id="7d91a-119">ORDER BY</span><span class="sxs-lookup"><span data-stu-id="7d91a-119">ORDER BY</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/order-by-entity-sql.md)
- <span data-ttu-id="7d91a-120">[방법: 쿼리 결과 페이징](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738702(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="7d91a-120">[How to: Page Through Query Results](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738702(v=vs.100))</span></span>
- [<span data-ttu-id="7d91a-121">페이징</span><span class="sxs-lookup"><span data-stu-id="7d91a-121">Paging</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/paging-entity-sql.md)
- [<span data-ttu-id="7d91a-122">TOP</span><span class="sxs-lookup"><span data-stu-id="7d91a-122">TOP</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/top-entity-sql.md)
