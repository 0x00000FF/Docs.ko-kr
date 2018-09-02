---
title: Skip While 절(Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.QuerySkipWhile
helpviewer_keywords:
- Skip While statement [Visual Basic]
- Skip While clause [Visual Basic]
- queries [Visual Basic], Skip While
ms.assetid: 5dee8350-7520-4f1a-b00d-590cacd572d6
ms.openlocfilehash: a3c0749560d8cea1e46d96298347ce54f0bf9185
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/01/2018
ms.locfileid: "43393732"
---
# <a name="skip-while-clause-visual-basic"></a><span data-ttu-id="6fa42-102">Skip While 절(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="6fa42-102">Skip While Clause (Visual Basic)</span></span>
<span data-ttu-id="6fa42-103">지정된 조건이 `true`이면 컬렉션에 있는 요소를 무시하고 나머지 요소를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="6fa42-103">Bypasses elements in a collection as long as a specified condition is `true` and then returns the remaining elements.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6fa42-104">구문</span><span class="sxs-lookup"><span data-stu-id="6fa42-104">Syntax</span></span>  
  
```  
Skip While expression  
```  
  
## <a name="parts"></a><span data-ttu-id="6fa42-105">요소</span><span class="sxs-lookup"><span data-stu-id="6fa42-105">Parts</span></span>  
  
|<span data-ttu-id="6fa42-106">용어</span><span class="sxs-lookup"><span data-stu-id="6fa42-106">Term</span></span>|<span data-ttu-id="6fa42-107">정의</span><span class="sxs-lookup"><span data-stu-id="6fa42-107">Definition</span></span>|  
|---|---|  
|`expression`|<span data-ttu-id="6fa42-108">필수.</span><span class="sxs-lookup"><span data-stu-id="6fa42-108">Required.</span></span> <span data-ttu-id="6fa42-109">에 대 한 요소를 테스트 하는 조건을 나타내는 식입니다.</span><span class="sxs-lookup"><span data-stu-id="6fa42-109">An expression that represents a condition to test elements for.</span></span> <span data-ttu-id="6fa42-110">식을 반환 해야 합니다는 `Boolean` 값 또는 이와 동일한 기능 같은 `Integer` 으로 계산 되는 `Boolean`합니다.</span><span class="sxs-lookup"><span data-stu-id="6fa42-110">The expression must return a `Boolean` value or a functional equivalent, such as an `Integer` to be evaluated as a `Boolean`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6fa42-111">설명</span><span class="sxs-lookup"><span data-stu-id="6fa42-111">Remarks</span></span>  
 <span data-ttu-id="6fa42-112">합니다 `Skip While` 일까 지 제공 된 쿼리 결과의 시작 부분에서 요소를 무시 하는 절 `expression` 반환 `false`합니다.</span><span class="sxs-lookup"><span data-stu-id="6fa42-112">The `Skip While` clause bypasses elements from the beginning of a query result until the supplied `expression` returns `false`.</span></span> <span data-ttu-id="6fa42-113">이후에 `expression` 반환 `false`, 나머지 모든 요소를 반환 하는 쿼리.</span><span class="sxs-lookup"><span data-stu-id="6fa42-113">After `expression` returns `false`, the query returns all the remaining elements.</span></span> <span data-ttu-id="6fa42-114">`expression` 나머지 결과 대해 무시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6fa42-114">The `expression` is ignored for the remaining results.</span></span>  
  
 <span data-ttu-id="6fa42-115">`Skip While` 절에서 다른 합니다 `Where` 절에는 `Where` 특정 조건을 충족 하지 않는 쿼리에서 모든 요소를 제외 하려면 절을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6fa42-115">The `Skip While` clause differs from the `Where` clause in that the `Where` clause can be used to exclude all elements from a query that do not meet a particular condition.</span></span> <span data-ttu-id="6fa42-116">`Skip While` 절 조건이 충족 되지 않은 첫 번째 시간 까지만 요소를 제외 합니다.</span><span class="sxs-lookup"><span data-stu-id="6fa42-116">The `Skip While` clause excludes elements only until the first time that the condition is not satisfied.</span></span> <span data-ttu-id="6fa42-117">`Skip While` 절은 순서가 지정 된 쿼리 결과 사용 하 여 작업할 때 가장 유용 합니다.</span><span class="sxs-lookup"><span data-stu-id="6fa42-117">The `Skip While` clause is most useful when you are working with an ordered query result.</span></span>  
  
 <span data-ttu-id="6fa42-118">특정 수의 쿼리 결과의 시작 부분에서 결과 사용 하 여 무시할 수 있습니다는 `Skip` 절.</span><span class="sxs-lookup"><span data-stu-id="6fa42-118">You can bypass a specific number of results from the beginning of a query result by using the `Skip` clause.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6fa42-119">예제</span><span class="sxs-lookup"><span data-stu-id="6fa42-119">Example</span></span>  
 <span data-ttu-id="6fa42-120">다음 코드 예제에서는 `Skip While` 절 미국에서 첫 번째 고객을 찾을 때까지 결과를 건너뜁니다.</span><span class="sxs-lookup"><span data-stu-id="6fa42-120">The following code example uses the `Skip While` clause to bypass results until the first customer from the United States is found.</span></span>  
  
 [!code-vb[VbSimpleQuerySamples#3](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/skip-while-clause_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="6fa42-121">참고 항목</span><span class="sxs-lookup"><span data-stu-id="6fa42-121">See Also</span></span>  
 [<span data-ttu-id="6fa42-122">Visual Basic의 LINQ 소개</span><span class="sxs-lookup"><span data-stu-id="6fa42-122">Introduction to LINQ in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)  
 [<span data-ttu-id="6fa42-123">쿼리</span><span class="sxs-lookup"><span data-stu-id="6fa42-123">Queries</span></span>](../../../visual-basic/language-reference/queries/index.md)  
 [<span data-ttu-id="6fa42-124">Select 절</span><span class="sxs-lookup"><span data-stu-id="6fa42-124">Select Clause</span></span>](../../../visual-basic/language-reference/queries/select-clause.md)  
 [<span data-ttu-id="6fa42-125">From 절</span><span class="sxs-lookup"><span data-stu-id="6fa42-125">From Clause</span></span>](../../../visual-basic/language-reference/queries/from-clause.md)  
 [<span data-ttu-id="6fa42-126">Skip 절</span><span class="sxs-lookup"><span data-stu-id="6fa42-126">Skip Clause</span></span>](../../../visual-basic/language-reference/queries/skip-clause.md)  
 [<span data-ttu-id="6fa42-127">Take While 절</span><span class="sxs-lookup"><span data-stu-id="6fa42-127">Take While Clause</span></span>](../../../visual-basic/language-reference/queries/take-while-clause.md)  
 [<span data-ttu-id="6fa42-128">Where 절</span><span class="sxs-lookup"><span data-stu-id="6fa42-128">Where Clause</span></span>](../../../visual-basic/language-reference/queries/where-clause.md)
