---
title: 연산자 우선 순위(Entity SQL)
ms.date: 03/30/2017
ms.assetid: e92e4ca5-2889-4266-9625-47f0eb01a948
ms.openlocfilehash: 722ebe5f0ec530f8c7f86e9f9901451b060903f0
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61760352"
---
# <a name="operator-precedence-entity-sql"></a><span data-ttu-id="b7f78-102">연산자 우선 순위(Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="b7f78-102">Operator Precedence (Entity SQL)</span></span>
<span data-ttu-id="b7f78-103">경우는 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] 쿼리 연산자가 여러 개 있는 수행 되는 작업 시퀀스를 결정 하는 연산자 우선 순위입니다.</span><span class="sxs-lookup"><span data-stu-id="b7f78-103">When an [!INCLUDE[esql](../../../../../../includes/esql-md.md)] query has multiple operators, operator precedence determines the sequence in which the operations are performed.</span></span> <span data-ttu-id="b7f78-104">실행 순서는 쿼리 결과에 상당한 영향을 미칠 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b7f78-104">The order of execution can significantly affect the query result.</span></span>  
  
 <span data-ttu-id="b7f78-105">다음 표에서는 연산자 우선 순위를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="b7f78-105">Operators have the precedence levels shown in the following table.</span></span> <span data-ttu-id="b7f78-106">높은 수준의 연산자는 낮은 수준의 연산자보다 먼저 계산됩니다.</span><span class="sxs-lookup"><span data-stu-id="b7f78-106">An operator with a higher level is evaluated before an operator with a lower level.</span></span>  
  
|<span data-ttu-id="b7f78-107">수준</span><span class="sxs-lookup"><span data-stu-id="b7f78-107">Level</span></span>|<span data-ttu-id="b7f78-108">연산 유형</span><span class="sxs-lookup"><span data-stu-id="b7f78-108">Operation type</span></span>|<span data-ttu-id="b7f78-109">연산자</span><span class="sxs-lookup"><span data-stu-id="b7f78-109">Operator</span></span>|  
|-----------|--------------------|--------------|  
|<span data-ttu-id="b7f78-110">1</span><span class="sxs-lookup"><span data-stu-id="b7f78-110">1</span></span>|<span data-ttu-id="b7f78-111">기본 연산자</span><span class="sxs-lookup"><span data-stu-id="b7f78-111">Primary</span></span>|`. , [] ()`|  
|<span data-ttu-id="b7f78-112">2</span><span class="sxs-lookup"><span data-stu-id="b7f78-112">2</span></span>|<span data-ttu-id="b7f78-113">단항</span><span class="sxs-lookup"><span data-stu-id="b7f78-113">Unary</span></span>|`! not`|  
|<span data-ttu-id="b7f78-114">3</span><span class="sxs-lookup"><span data-stu-id="b7f78-114">3</span></span>|<span data-ttu-id="b7f78-115">곱하기</span><span class="sxs-lookup"><span data-stu-id="b7f78-115">Multiplicative</span></span>|`* / %`|  
|<span data-ttu-id="b7f78-116">4</span><span class="sxs-lookup"><span data-stu-id="b7f78-116">4</span></span>|<span data-ttu-id="b7f78-117">더하기</span><span class="sxs-lookup"><span data-stu-id="b7f78-117">Additive</span></span>|`+ -`|  
|<span data-ttu-id="b7f78-118">5</span><span class="sxs-lookup"><span data-stu-id="b7f78-118">5</span></span>|<span data-ttu-id="b7f78-119">순서 지정</span><span class="sxs-lookup"><span data-stu-id="b7f78-119">Ordering</span></span>|`< > <= >=`|  
|<span data-ttu-id="b7f78-120">6</span><span class="sxs-lookup"><span data-stu-id="b7f78-120">6</span></span>|<span data-ttu-id="b7f78-121">같음</span><span class="sxs-lookup"><span data-stu-id="b7f78-121">Equality</span></span>|`= != <>`|  
|<span data-ttu-id="b7f78-122">7</span><span class="sxs-lookup"><span data-stu-id="b7f78-122">7</span></span>|<span data-ttu-id="b7f78-123">조건부 AND</span><span class="sxs-lookup"><span data-stu-id="b7f78-123">Conditional AND</span></span>|`and &&`|  
|<span data-ttu-id="b7f78-124">8</span><span class="sxs-lookup"><span data-stu-id="b7f78-124">8</span></span>|<span data-ttu-id="b7f78-125">조건부 OR</span><span class="sxs-lookup"><span data-stu-id="b7f78-125">Conditional OR</span></span>|`or &#124;&#124;`|  
  
 <span data-ttu-id="b7f78-126">식에 연산자 우선 순위 수준이 동일한 두 연산자가 있으면 쿼리 내의 위치를 기준으로 왼쪽에서 오른쪽으로 계산됩니다.</span><span class="sxs-lookup"><span data-stu-id="b7f78-126">When two operators in an expression have the same operator precedence level, they are evaluated left to right, based on their position in the query.</span></span> <span data-ttu-id="b7f78-127">예를 들어, `x+y-z`는 `(x+y)-z`로 계산됩니다.</span><span class="sxs-lookup"><span data-stu-id="b7f78-127">For example, `x+y-z` is evaluated as `(x+y)-z`.</span></span>  
  
 <span data-ttu-id="b7f78-128">괄호를 사용하여 쿼리에서 연산자에 정의된 우선 순위를 재정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b7f78-128">You can use parentheses to override the defined precedence of the operators in a query.</span></span> <span data-ttu-id="b7f78-129">괄호 안의 모든 연산자를 먼저 계산하여 단일 결과를 생성한 후, 이 결과를 괄호 밖의 연산자에 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b7f78-129">Everything within parentheses is evaluated first to yield a single result before that result can be used by any operator outside the parentheses.</span></span> <span data-ttu-id="b7f78-130">예를 들어 `x+y*z` 곱합니다 `y` 하 여 `z` 추가한 `x`, 하지만 `(x+y)*z` 추가 `x` 에 `y` 다음 결과 곱합니다 `z`합니다.</span><span class="sxs-lookup"><span data-stu-id="b7f78-130">For example, `x+y*z` multiplies `y` by `z` and then adds `x`, but `(x+y)*z` adds `x` to `y` and then multiplies the result by `z`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b7f78-131">참고자료</span><span class="sxs-lookup"><span data-stu-id="b7f78-131">See also</span></span>

- [<span data-ttu-id="b7f78-132">Entity SQL 개요</span><span class="sxs-lookup"><span data-stu-id="b7f78-132">Entity SQL Overview</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-overview.md)
