---
title: 쿼리 결과를 메모리에 저장
description: 결과 저장 방법
ms.date: 11/30/2016
ms.assetid: 5b863961-1750-4cf9-9607-acea5054d15a
ms.openlocfilehash: 98a300b2c11eb037ed4ce34caea2673a4e0f8e6b
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/04/2018
ms.locfileid: "43525232"
---
# <a name="store-the-results-of-a-query-in-memory"></a><span data-ttu-id="f88f8-103">쿼리 결과를 메모리에 저장</span><span class="sxs-lookup"><span data-stu-id="f88f8-103">Store the results of a query in memory</span></span>

<span data-ttu-id="f88f8-104">쿼리는 기본적으로 데이터를 검색하고 구성하는 방법에 대한 명령 집합입니다.</span><span class="sxs-lookup"><span data-stu-id="f88f8-104">A query is basically a set of instructions for how to retrieve and organize data.</span></span> <span data-ttu-id="f88f8-105">쿼리는 결과의 각 후속 항목이 요청될 때 지연 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="f88f8-105">Queries are executed lazily, as each subsequent item in the result is requested.</span></span> <span data-ttu-id="f88f8-106">`foreach`를 사용하여 결과를 반복하는 경우 항목이 액세스될 때 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="f88f8-106">When you use `foreach` to iterate the results, items are returned as accessed.</span></span> <span data-ttu-id="f88f8-107">쿼리를 평가한 후 `foreach` 루프를 실행하지 않고 결과를 저장하려면 쿼리 변수에 대해 다음 메서드 중 하나를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="f88f8-107">To evaluate a query and store its results without executing a `foreach` loop, just call one of the following methods on the query variable:</span></span>

- <xref:System.Linq.Enumerable.ToList%2A>

- <xref:System.Linq.Enumerable.ToArray%2A>

- <xref:System.Linq.Enumerable.ToDictionary%2A>

- <xref:System.Linq.Enumerable.ToLookup%2A>

 <span data-ttu-id="f88f8-108">쿼리 결과를 저장하는 경우 다음 예제와 같이 반환된 컬렉션 개체를 새 변수에 할당하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="f88f8-108">We recommend that when you store the query results, you assign the returned collection object to a new variable as shown in the following example:</span></span>

## <a name="example"></a><span data-ttu-id="f88f8-109">예</span><span class="sxs-lookup"><span data-stu-id="f88f8-109">Example</span></span>

[!code-csharp[csProgGuideLINQ#25](~/samples/snippets/csharp/concepts/linq/how-to-store-the-results-of-a-query-in-memory_1.cs)]

## <a name="see-also"></a><span data-ttu-id="f88f8-110">참고 항목</span><span class="sxs-lookup"><span data-stu-id="f88f8-110">See also</span></span>

- [<span data-ttu-id="f88f8-111">LINQ(Language-Integrated Query)</span><span class="sxs-lookup"><span data-stu-id="f88f8-111">Language Integrated Query (LINQ)</span></span>](index.md)