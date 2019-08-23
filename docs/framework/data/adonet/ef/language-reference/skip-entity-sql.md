---
title: SKIP(Entity SQL)
ms.date: 03/30/2017
ms.assetid: e2139412-8ea4-451b-8f10-91af18dfa3ec
ms.openlocfilehash: 6ddbdd41a00b3934649b24ca96a5a07e5cbf0d34
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2019
ms.locfileid: "69911141"
---
# <a name="skip-entity-sql"></a><span data-ttu-id="f0c47-102">SKIP(Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="f0c47-102">SKIP (Entity SQL)</span></span>
<span data-ttu-id="f0c47-103">ORDER BY 절의 SKIP 하위 절을 사용하여 물리적 페이징을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f0c47-103">You can perform physical paging by using the SKIP sub-clause in the ORDER BY clause.</span></span> <span data-ttu-id="f0c47-104">SKIP 절은 ORDER BY 절과 별도로 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f0c47-104">SKIP cannot be used separately from the ORDER BY clause.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f0c47-105">구문</span><span class="sxs-lookup"><span data-stu-id="f0c47-105">Syntax</span></span>  
  
```  
[ SKIP n ]  
```  
  
## <a name="arguments"></a><span data-ttu-id="f0c47-106">인수</span><span class="sxs-lookup"><span data-stu-id="f0c47-106">Arguments</span></span>  
 `n`  
 <span data-ttu-id="f0c47-107">건너뛸 항목의 개수입니다.</span><span class="sxs-lookup"><span data-stu-id="f0c47-107">The number of items to skip.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f0c47-108">설명</span><span class="sxs-lookup"><span data-stu-id="f0c47-108">Remarks</span></span>  
 <span data-ttu-id="f0c47-109">SKIP 식 하위 절이 ORDER BY 절에 있으면 결과는 정렬 지정에 따라 정렬되고 SKIP 식 바로 뒤에 있는 행에서 시작하는 행이 결과 집합에 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="f0c47-109">If a SKIP expression sub-clause is present in an ORDER BY clause, the results will be sorted according the sort specification and the result set will include rows starting from the next row immediately after the SKIP expression.</span></span> <span data-ttu-id="f0c47-110">예를 들어, SKIP 5를 사용하면 처음 다섯 개의 행을 건너뛰고 여섯 번째 행부터 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="f0c47-110">For example, SKIP 5 will skip the first five rows and return from the sixth row forward.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="f0c47-111">TOP 한정자와 SKIP 하위 절이 모두 같은 쿼리 식에 있는 경우 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] 쿼리는 유효하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f0c47-111">An [!INCLUDE[esql](../../../../../../includes/esql-md.md)] query is invalid if both the TOP modifier and the SKIP sub-clause are present in the same query expression.</span></span> <span data-ttu-id="f0c47-112">TOP 식을 변경하여 쿼리를 LIMIT 식에 다시 써야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f0c47-112">The query should be rewritten by changing the TOP expression to the LIMIT expression.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="f0c47-113">SQL Server 2000에서 키가 아닌 열에 ORDER BY와 함께 SKIP을 사용 하면 잘못 된 결과가 반환 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f0c47-113">In SQL Server 2000, using SKIP with ORDER BY on non-key columns might return incorrect results.</span></span> <span data-ttu-id="f0c47-114">키가 아닌 열에 중복 데이터가 있는 경우, 지정된 개수 이상의 행을 건너뛸 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f0c47-114">More than the specified number of rows might be skipped if the non-key column has duplicate data in it.</span></span> <span data-ttu-id="f0c47-115">이는 SQL Server 2000에 대해 SKIP이 변환 되기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="f0c47-115">This is due to how SKIP is translated for SQL Server 2000.</span></span> <span data-ttu-id="f0c47-116">예를 들어 다음 코드에서는 `E.NonKeyColumn` 에 중복 값이 있으면 5개가 넘는 행을 건너뛸 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f0c47-116">For example, in the following code more than five rows might be skipped if `E.NonKeyColumn` has duplicate values:</span></span>  
>   
>  `SELECT [E] FROM Container.EntitySet AS [E] ORDER BY [E].[NonKeyColumn] DESC SKIP 5L`  
  
 <span data-ttu-id="f0c47-117">[!INCLUDE[esql](../../../../../../includes/esql-md.md)] 방법 :[ 쿼리 결과](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738702(v=vs.100)) 를 통한 페이지에서는 SKIP과 함께 ORDER by 연산자를 사용 하 여 SELECT 문에서 반환 되는 개체에 사용 되는 정렬 순서를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="f0c47-117">The  [!INCLUDE[esql](../../../../../../includes/esql-md.md)] query in [How to: Page Through Query Results](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738702(v=vs.100)) uses the ORDER BY operator with SKIP to specify the sort order used on objects returned in a SELECT statement.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f0c47-118">참고자료</span><span class="sxs-lookup"><span data-stu-id="f0c47-118">See also</span></span>

- [<span data-ttu-id="f0c47-119">ORDER BY</span><span class="sxs-lookup"><span data-stu-id="f0c47-119">ORDER BY</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/order-by-entity-sql.md)
- <span data-ttu-id="f0c47-120">[방법: 쿼리 결과를 통한 페이지](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738702(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="f0c47-120">[How to: Page Through Query Results](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738702(v=vs.100))</span></span>
- [<span data-ttu-id="f0c47-121">페이징</span><span class="sxs-lookup"><span data-stu-id="f0c47-121">Paging</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/paging-entity-sql.md)
- [<span data-ttu-id="f0c47-122">TOP</span><span class="sxs-lookup"><span data-stu-id="f0c47-122">TOP</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/top-entity-sql.md)
