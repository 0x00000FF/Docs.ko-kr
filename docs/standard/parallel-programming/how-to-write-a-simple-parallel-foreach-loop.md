---
title: "방법: 간단한 Parallel.ForEach 루프 작성"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- foreach, parallel version
- parallel programming, foreach
ms.assetid: cb5fab92-1c19-499e-ae91-8b7525dd875f
caps.latest.revision: "19"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 16d8cd3c3c01c2f9d83786e78f0eb1c45a38a49b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-write-a-simple-parallelforeach-loop"></a><span data-ttu-id="10a26-102">방법: 간단한 Parallel.ForEach 루프 작성</span><span class="sxs-lookup"><span data-stu-id="10a26-102">How to: Write a Simple Parallel.ForEach Loop</span></span>
<span data-ttu-id="10a26-103">사용 하는 방법을 보여 주는이 예제는 <xref:System.Threading.Tasks.Parallel.ForEach%2A?displayProperty=nameWithType> 하나를 통해 데이터 병렬 처리를 사용 하려면 루프 <xref:System.Collections.IEnumerable?displayProperty=nameWithType> 또는 <xref:System.Collections.Generic.IEnumerable%601?displayProperty=nameWithType> 데이터 원본입니다.</span><span class="sxs-lookup"><span data-stu-id="10a26-103">This example shows how to use a <xref:System.Threading.Tasks.Parallel.ForEach%2A?displayProperty=nameWithType> loop to enable data parallelism over any <xref:System.Collections.IEnumerable?displayProperty=nameWithType> or <xref:System.Collections.Generic.IEnumerable%601?displayProperty=nameWithType> data source.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="10a26-104">이 문서에서는 람다 식을 사용하여 PLINQ에 대리자를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="10a26-104">This documentation uses lambda expressions to define delegates in PLINQ.</span></span> <span data-ttu-id="10a26-105">C# 또는 Visual Basic의 람다 식을 잘 모르는 경우 [PLINQ 및 TPL의 람다 식](../../../docs/standard/parallel-programming/lambda-expressions-in-plinq-and-tpl.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="10a26-105">If you are not familiar with lambda expressions in C# or Visual Basic, see [Lambda Expressions in PLINQ and TPL](../../../docs/standard/parallel-programming/lambda-expressions-in-plinq-and-tpl.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="10a26-106">예제</span><span class="sxs-lookup"><span data-stu-id="10a26-106">Example</span></span>  
 [!code-csharp[TPL_Parallel#03](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_parallel/cs/simpleforeach.cs#03)]
 [!code-vb[TPL_Parallel#03](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_parallel/vb/simpleforeach.vb#03)]  
  
 <span data-ttu-id="10a26-107">A <xref:System.Threading.Tasks.Parallel.ForEach%2A> 와 비슷하게 작동 한 <xref:System.Threading.Tasks.Parallel.For%2A> 루프입니다.</span><span class="sxs-lookup"><span data-stu-id="10a26-107">A <xref:System.Threading.Tasks.Parallel.ForEach%2A> loop works like a <xref:System.Threading.Tasks.Parallel.For%2A> loop.</span></span> <span data-ttu-id="10a26-108">소스 컬렉션은 분할 및 시스템 환경에 따라 여러 스레드에서 작업 예약 합니다.</span><span class="sxs-lookup"><span data-stu-id="10a26-108">The source collection is partitioned and the work is scheduled on multiple threads based on the system environment.</span></span> <span data-ttu-id="10a26-109">시스템에 더 많은 프로세서를 더 빠르게 병렬 메서드를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="10a26-109">The more processors on the system, the faster the parallel method runs.</span></span> <span data-ttu-id="10a26-110">일부 소스 컬렉션에 대 한 순차 루프는 크기는 원본 및 수행 중인 작업의 종류에 따라 빠를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="10a26-110">For some source collections, a sequential loop may be faster, depending on the size of the source, and the kind of work being performed.</span></span> <span data-ttu-id="10a26-111">성능에 대 한 자세한 내용은 참조 [데이터 및 작업 병렬 처리에서 발생할 수 있는 문제](../../../docs/standard/parallel-programming/potential-pitfalls-in-data-and-task-parallelism.md)</span><span class="sxs-lookup"><span data-stu-id="10a26-111">For more information about performance, see [Potential Pitfalls in Data and Task Parallelism](../../../docs/standard/parallel-programming/potential-pitfalls-in-data-and-task-parallelism.md)</span></span>  
  
 <span data-ttu-id="10a26-112">병렬 루프에 대 한 자세한 내용은 참조 [하는 방법: 간단한 Parallel.For 루프 작성](../../../docs/standard/parallel-programming/how-to-write-a-simple-parallel-for-loop.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="10a26-112">For more information about parallel loops, see [How to: Write a Simple Parallel.For Loop](../../../docs/standard/parallel-programming/how-to-write-a-simple-parallel-for-loop.md).</span></span>  
  
 <span data-ttu-id="10a26-113">사용 하도록 <xref:System.Threading.Tasks.Parallel.ForEach%2A> 를 제네릭이 아닌 컬렉션에 사용할 수 있습니다는 <xref:System.Linq.Enumerable.Cast%2A> 확장 메서드를 다음 예제와 같이 제네릭 컬렉션에 컬렉션으로 변환 합니다.</span><span class="sxs-lookup"><span data-stu-id="10a26-113">To use <xref:System.Threading.Tasks.Parallel.ForEach%2A> with a non-generic collection, you can use the <xref:System.Linq.Enumerable.Cast%2A> extension method to convert the collection to a generic collection, as shown in the following example:</span></span>  
  
 [!code-csharp[TPL_Parallel#07](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_parallel/cs/nongeneric.cs#07)]
 [!code-vb[TPL_Parallel#07](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_parallel/vb/nongeneric.vb#07)]  
  
 <span data-ttu-id="10a26-114">처리를 병렬화 하 PLINQ (병렬 LINQ)을 사용할 수도 있습니다 <xref:System.Collections.Generic.IEnumerable%601> 데이터 원본입니다.</span><span class="sxs-lookup"><span data-stu-id="10a26-114">You can also use Parallel LINQ (PLINQ) to parallelize processing of <xref:System.Collections.Generic.IEnumerable%601> data sources.</span></span> <span data-ttu-id="10a26-115">PLINQ를 사용 하면 선언적 쿼리 구문을 사용 하 여 루프 동작을 표현할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="10a26-115">PLINQ enables you to use declarative query syntax to express the loop behavior.</span></span> <span data-ttu-id="10a26-116">자세한 내용은 [PLINQ(병렬 LINQ)](../../../docs/standard/parallel-programming/parallel-linq-plinq.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="10a26-116">For more information, see [Parallel LINQ (PLINQ)](../../../docs/standard/parallel-programming/parallel-linq-plinq.md).</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="10a26-117">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="10a26-117">Compiling the Code</span></span>  
  
-   <span data-ttu-id="10a26-118">복사 및 붙여넣기에이 코드는 [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] 2010 콘솔 응용 프로그램 프로젝트입니다.</span><span class="sxs-lookup"><span data-stu-id="10a26-118">Copy and paste this code into a [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] 2010 Console Application project.</span></span>  
  
-   <span data-ttu-id="10a26-119">System.Drawing.dll에 대 한 참조를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="10a26-119">Add a reference to System.Drawing.dll</span></span>  
  
-   <span data-ttu-id="10a26-120">F5 키를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="10a26-120">Press F5</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="10a26-121">참고 항목</span><span class="sxs-lookup"><span data-stu-id="10a26-121">See Also</span></span>  
 [<span data-ttu-id="10a26-122">데이터 병렬 처리</span><span class="sxs-lookup"><span data-stu-id="10a26-122">Data Parallelism</span></span>](../../../docs/standard/parallel-programming/data-parallelism-task-parallel-library.md)  
 [<span data-ttu-id="10a26-123">병렬 프로그래밍</span><span class="sxs-lookup"><span data-stu-id="10a26-123">Parallel Programming</span></span>](../../../docs/standard/parallel-programming/index.md)  
 [<span data-ttu-id="10a26-124">PLINQ(병렬 LINQ)</span><span class="sxs-lookup"><span data-stu-id="10a26-124">Parallel LINQ (PLINQ)</span></span>](../../../docs/standard/parallel-programming/parallel-linq-plinq.md)
