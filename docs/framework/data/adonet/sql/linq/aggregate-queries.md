---
title: 집계 쿼리
ms.date: 03/30/2017
ms.assetid: 13ec5580-05ce-4a1f-9d3d-8660be7891a2
ms.openlocfilehash: 8a3dd4b80ee8bb09dc0b5a06b6fa603f4b74fdf8
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/28/2019
ms.locfileid: "64610153"
---
# <a name="aggregate-queries"></a><span data-ttu-id="10d77-102">집계 쿼리</span><span class="sxs-lookup"><span data-stu-id="10d77-102">Aggregate Queries</span></span>
[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]<span data-ttu-id="10d77-103">에서는 `Average`, `Count`, `Max`, `Min` 및 `Sum` 집계 연산자가 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="10d77-103">supports the `Average`, `Count`, `Max`, `Min`, and `Sum` aggregate operators.</span></span> <span data-ttu-id="10d77-104">[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]에서 집계 연산자의 다음과 같은 특징에 유의하세요.</span><span class="sxs-lookup"><span data-stu-id="10d77-104">Note the following characteristics of aggregate operators in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]:</span></span>  
  
- <span data-ttu-id="10d77-105">집계 쿼리는 즉시 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="10d77-105">Aggregate queries are executed immediately.</span></span>  
  
     <span data-ttu-id="10d77-106">자세한 내용은 [LINQ 쿼리 소개(C#)](~/docs/csharp/programming-guide/concepts/linq/introduction-to-linq-queries.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="10d77-106">For more information, see [Introduction to LINQ Queries (C#)](~/docs/csharp/programming-guide/concepts/linq/introduction-to-linq-queries.md).</span></span>  
  
- <span data-ttu-id="10d77-107">집계 쿼리는 일반적으로 컬렉션 대신 숫자를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="10d77-107">Aggregate queries typically return a number instead of a collection.</span></span>  
  
     <span data-ttu-id="10d77-108">자세한 내용은 [집계 작업](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/bb546138(v=vs.120))합니다.</span><span class="sxs-lookup"><span data-stu-id="10d77-108">For more information, see [Aggregation Operations](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/bb546138(v=vs.120)).</span></span>  
  
- <span data-ttu-id="10d77-109">익명 형식에 대해서 집계를 호출할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="10d77-109">You cannot call aggregates against anonymous types.</span></span>  
  
 <span data-ttu-id="10d77-110">다음 항목의 예제에서는 Northwind 샘플 데이터베이스를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="10d77-110">The examples in the following topics derive from the Northwind sample database.</span></span> <span data-ttu-id="10d77-111">자세한 내용은 [샘플 데이터베이스 다운로드](../../../../../../docs/framework/data/adonet/sql/linq/downloading-sample-databases.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="10d77-111">For more information, see [Downloading Sample Databases](../../../../../../docs/framework/data/adonet/sql/linq/downloading-sample-databases.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="10d77-112">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="10d77-112">In This Section</span></span>  
 [<span data-ttu-id="10d77-113">숫자 시퀀스에서 평균 값 반환</span><span class="sxs-lookup"><span data-stu-id="10d77-113">Return the Average Value From a Numeric Sequence</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/return-the-average-value-from-a-numeric-sequence.md)  
 <span data-ttu-id="10d77-114"><xref:System.Linq.Enumerable.Average%2A> 연산자를 사용하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="10d77-114">Demonstrates how to use the <xref:System.Linq.Enumerable.Average%2A> operator.</span></span>  
  
 [<span data-ttu-id="10d77-115">시퀀스의 요소 수 계산</span><span class="sxs-lookup"><span data-stu-id="10d77-115">Count the Number of Elements in a Sequence</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/count-the-number-of-elements-in-a-sequence.md)  
 <span data-ttu-id="10d77-116"><xref:System.Linq.Enumerable.Count%2A> 연산자를 사용하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="10d77-116">Demonstrates how to use the <xref:System.Linq.Enumerable.Count%2A> operator.</span></span>  
  
 [<span data-ttu-id="10d77-117">숫자 시퀀스에서 최대값 찾기</span><span class="sxs-lookup"><span data-stu-id="10d77-117">Find the Maximum Value in a Numeric Sequence</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/find-the-maximum-value-in-a-numeric-sequence.md)  
 <span data-ttu-id="10d77-118"><xref:System.Linq.Enumerable.Max%2A> 연산자를 사용하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="10d77-118">Demonstrates how to use the <xref:System.Linq.Enumerable.Max%2A> operator.</span></span>  
  
 [<span data-ttu-id="10d77-119">숫자 시퀀스에서 최소값 찾기</span><span class="sxs-lookup"><span data-stu-id="10d77-119">Find the Minimum Value in a Numeric Sequence</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/find-the-minimum-value-in-a-numeric-sequence.md)  
 <span data-ttu-id="10d77-120"><xref:System.Linq.Enumerable.Min%2A> 연산자를 사용하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="10d77-120">Demonstrates how to use the <xref:System.Linq.Enumerable.Min%2A> operator.</span></span>  
  
 [<span data-ttu-id="10d77-121">숫자 시퀀스에서 값의 합계 계산</span><span class="sxs-lookup"><span data-stu-id="10d77-121">Compute the Sum of Values in a Numeric Sequence</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/compute-the-sum-of-values-in-a-numeric-sequence.md)  
 <span data-ttu-id="10d77-122"><xref:System.Linq.Enumerable.Sum%2A> 연산자를 사용하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="10d77-122">Demonstrates how to use the <xref:System.Linq.Enumerable.Sum%2A> operator.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="10d77-123">관련 단원</span><span class="sxs-lookup"><span data-stu-id="10d77-123">Related Sections</span></span>  
 [<span data-ttu-id="10d77-124">쿼리 예제</span><span class="sxs-lookup"><span data-stu-id="10d77-124">Query Examples</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/query-examples.md)  
 <span data-ttu-id="10d77-125">Visual Basic 및 C#의 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] 쿼리에 대한 링크를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="10d77-125">Provides links to [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] queries in Visual Basic and C#.</span></span>  
  
 [<span data-ttu-id="10d77-126">쿼리 개념</span><span class="sxs-lookup"><span data-stu-id="10d77-126">Query Concepts</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/query-concepts.md)  
 <span data-ttu-id="10d77-127">[!INCLUDE[vbteclinq](../../../../../../includes/vbteclinq-md.md)]의 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] 쿼리 설계 개념을 설명하는 항목에 대한 링크를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="10d77-127">Provides links to topics that explain concepts for designing [!INCLUDE[vbteclinq](../../../../../../includes/vbteclinq-md.md)] queries in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span></span>  
  
 [<span data-ttu-id="10d77-128">LINQ 쿼리 소개(C#)</span><span class="sxs-lookup"><span data-stu-id="10d77-128">Introduction to LINQ Queries (C#)</span></span>](~/docs/csharp/programming-guide/concepts/linq/introduction-to-linq-queries.md)  
 <span data-ttu-id="10d77-129">[!INCLUDE[vbteclinq](../../../../../../includes/vbteclinq-md.md)]의 쿼리 작동 방식을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="10d77-129">Explains how queries work in [!INCLUDE[vbteclinq](../../../../../../includes/vbteclinq-md.md)].</span></span>
