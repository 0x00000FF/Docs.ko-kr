---
title: "데이터 분할(C#)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-csharp
ms.topic: article
ms.assetid: 2a5c507b-fe22-443c-a768-dec7f9ec568d
caps.latest.revision: "3"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 32b95887e05767513dd818743dd1726149503b0f
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="partitioning-data-c"></a><span data-ttu-id="9fcd4-102">데이터 분할(C#)</span><span class="sxs-lookup"><span data-stu-id="9fcd4-102">Partitioning Data (C#)</span></span>
<span data-ttu-id="9fcd4-103">LINQ의 분할은 요소를 다시 정렬한 후 섹션 중 하나를 반환하지 않고 입력 시퀀스를 두 개의 섹션으로 나누는 작업을 가리킵니다.</span><span class="sxs-lookup"><span data-stu-id="9fcd4-103">Partitioning in LINQ refers to the operation of dividing an input sequence into two sections, without rearranging the elements, and then returning one of the sections.</span></span>  
  
 <span data-ttu-id="9fcd4-104">다음 그림은 문자 시퀀스에 대한 세 가지 분할 작업의 결과를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="9fcd4-104">The following illustration shows the results of three different partitioning operations on a sequence of characters.</span></span> <span data-ttu-id="9fcd4-105">첫 번째 작업은 시퀀스에서 처음 세 개의 요소를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="9fcd4-105">The first operation returns the first three elements in the sequence.</span></span> <span data-ttu-id="9fcd4-106">두 번째 작업은 처음 세 개의 요소를 건너뛰고 나머지 요소를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="9fcd4-106">The second operation skips the first three elements and returns the remaining elements.</span></span> <span data-ttu-id="9fcd4-107">세 번째 작업은 시퀀스에서 처음 두 개의 요소를 건너뛰고 다음 세 개의 요소를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="9fcd4-107">The third operation skips the first two elements in the sequence and returns the next three elements.</span></span>  
  
 <span data-ttu-id="9fcd4-108">![LINQ 분할 작업](../../../../csharp/programming-guide/concepts/linq/media/linq_partition.png "LINQ_Partition")</span><span class="sxs-lookup"><span data-stu-id="9fcd4-108">![LINQ Partitioning Operations](../../../../csharp/programming-guide/concepts/linq/media/linq_partition.png "LINQ_Partition")</span></span>  
  
 <span data-ttu-id="9fcd4-109">시퀀스를 분할하는 표준 쿼리 연산자 메서드가 다음 섹션에 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9fcd4-109">The standard query operator methods that partition sequences are listed in the following section.</span></span>  
  
## <a name="operators"></a><span data-ttu-id="9fcd4-110">연산자</span><span class="sxs-lookup"><span data-stu-id="9fcd4-110">Operators</span></span>  
  
|<span data-ttu-id="9fcd4-111">연산자 이름</span><span class="sxs-lookup"><span data-stu-id="9fcd4-111">Operator Name</span></span>|<span data-ttu-id="9fcd4-112">설명</span><span class="sxs-lookup"><span data-stu-id="9fcd4-112">Description</span></span>|<span data-ttu-id="9fcd4-113">C# 쿼리 식 구문</span><span class="sxs-lookup"><span data-stu-id="9fcd4-113">C# Query Expression Syntax</span></span>|<span data-ttu-id="9fcd4-114">추가 정보</span><span class="sxs-lookup"><span data-stu-id="9fcd4-114">More Information</span></span>|  
|-------------------|-----------------|---------------------------------|----------------------|  
|<span data-ttu-id="9fcd4-115">Skip</span><span class="sxs-lookup"><span data-stu-id="9fcd4-115">Skip</span></span>|<span data-ttu-id="9fcd4-116">시퀀스에서 지정한 위치까지 요소를 건너뜁니다.</span><span class="sxs-lookup"><span data-stu-id="9fcd4-116">Skips elements up to a specified position in a sequence.</span></span>|<span data-ttu-id="9fcd4-117">해당 사항 없음.</span><span class="sxs-lookup"><span data-stu-id="9fcd4-117">Not applicable.</span></span>|<xref:System.Linq.Enumerable.Skip%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Skip%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="9fcd4-118">SkipWhile</span><span class="sxs-lookup"><span data-stu-id="9fcd4-118">SkipWhile</span></span>|<span data-ttu-id="9fcd4-119">요소가 조건을 충족하지 않을 때까지 조건자 함수를 기반으로 하여 요소를 건너뜁니다.</span><span class="sxs-lookup"><span data-stu-id="9fcd4-119">Skips elements based on a predicate function until an element does not satisfy the condition.</span></span>|<span data-ttu-id="9fcd4-120">해당 사항 없음.</span><span class="sxs-lookup"><span data-stu-id="9fcd4-120">Not applicable.</span></span>|<xref:System.Linq.Enumerable.SkipWhile%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.SkipWhile%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="9fcd4-121">Take</span><span class="sxs-lookup"><span data-stu-id="9fcd4-121">Take</span></span>|<span data-ttu-id="9fcd4-122">시퀀스에서 지정된 위치까지 요소를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="9fcd4-122">Takes elements up to a specified position in a sequence.</span></span>|<span data-ttu-id="9fcd4-123">해당 사항 없음.</span><span class="sxs-lookup"><span data-stu-id="9fcd4-123">Not applicable.</span></span>|<xref:System.Linq.Enumerable.Take%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Take%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="9fcd4-124">TakeWhile</span><span class="sxs-lookup"><span data-stu-id="9fcd4-124">TakeWhile</span></span>|<span data-ttu-id="9fcd4-125">요소가 조건을 충족하지 않을 때까지 조건자 함수를 기반으로 하여 요소를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="9fcd4-125">Takes elements based on a predicate function until an element does not satisfy the condition.</span></span>|<span data-ttu-id="9fcd4-126">해당 사항 없음.</span><span class="sxs-lookup"><span data-stu-id="9fcd4-126">Not applicable.</span></span>|<xref:System.Linq.Enumerable.TakeWhile%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.TakeWhile%2A?displayProperty=nameWithType>|  
  
## <a name="see-also"></a><span data-ttu-id="9fcd4-127">참고 항목</span><span class="sxs-lookup"><span data-stu-id="9fcd4-127">See Also</span></span>  
 <xref:System.Linq>  
 [<span data-ttu-id="9fcd4-128">표준 쿼리 연산자 개요(C#)</span><span class="sxs-lookup"><span data-stu-id="9fcd4-128">Standard Query Operators Overview (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/standard-query-operators-overview.md)
