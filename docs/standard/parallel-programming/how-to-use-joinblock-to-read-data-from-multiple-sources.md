---
title: '방법: JoinBlock을 사용하여 여러 소스에서 데이터 읽기'
ms.date: 03/30/2017
ms.prod: .net
ms.technology: dotnet-standard
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Task Parallel Library, dataflows
- TPL dataflow library, joining blocks in
- dataflow blocks, joining in TPL
ms.assetid: e9c1ada4-ac57-4704-87cb-2f5117f8151d
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: ba353a34306b06e0f1df4696af5545799e7a5b37
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/26/2018
---
# <a name="how-to-use-joinblock-to-read-data-from-multiple-sources"></a><span data-ttu-id="2ad63-102">방법: JoinBlock을 사용하여 여러 소스에서 데이터 읽기</span><span class="sxs-lookup"><span data-stu-id="2ad63-102">How to: Use JoinBlock to Read Data From Multiple Sources</span></span>
<span data-ttu-id="2ad63-103">이 문서에서는 <xref:System.Threading.Tasks.Dataflow.JoinBlock%602> 클래스를 사용하여 여러 소스에서 데이터를 사용할 수 있는 경우 작업을 수행하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="2ad63-103">This document explains how to use the <xref:System.Threading.Tasks.Dataflow.JoinBlock%602> class to perform an operation when data is available from multiple sources.</span></span> <span data-ttu-id="2ad63-104">또한 non-greedy 모드를 사용하여 여러 조인 블록이 데이터 소스를 보다 효율적으로 공유할 수 있도록 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="2ad63-104">It also demonstrates how to use non-greedy mode to enable multiple join blocks to share a data source more efficiently.</span></span>

[!INCLUDE [tpl-install-instructions](../../../includes/tpl-install-instructions.md)]

## <a name="example"></a><span data-ttu-id="2ad63-105">예</span><span class="sxs-lookup"><span data-stu-id="2ad63-105">Example</span></span>  
 <span data-ttu-id="2ad63-106">다음 예제에서는 세 가지 리소스 형식인 `NetworkResource`, `FileResource` 및 `MemoryResource`를 정의하고 리소스를 사용할 수 있게 되면 작업을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="2ad63-106">The following example defines three resource types, `NetworkResource`, `FileResource`, and `MemoryResource`, and performs operations when resources become available.</span></span> <span data-ttu-id="2ad63-107">이 예제에서는 첫 번째 작업을 수행하기 위해 `NetworkResource` 및 `MemoryResource` 쌍이 필요하고, 두 번째 작업을 수행하기 위해 `FileResource` 및 `MemoryResource` 쌍이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="2ad63-107">This example requires a `NetworkResource` and `MemoryResource` pair in order to perform the first operation and a `FileResource` and `MemoryResource` pair in order to perform the second operation.</span></span> <span data-ttu-id="2ad63-108">필요한 리소스를 모두 사용할 수 있을 때 이러한 작업이 수행될 수 있도록 하기 위해 이 예제에서는 <xref:System.Threading.Tasks.Dataflow.JoinBlock%602> 클래스를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="2ad63-108">To enable these operations to occur when all required resources are available, this example uses the <xref:System.Threading.Tasks.Dataflow.JoinBlock%602> class.</span></span> <span data-ttu-id="2ad63-109"><xref:System.Threading.Tasks.Dataflow.JoinBlock%602> 개체는 모든 소스에서 데이터를 받으면 해당 데이터를 대상에 전파합니다. 이 예제에서 대상은 <xref:System.Threading.Tasks.Dataflow.ActionBlock%601> 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="2ad63-109">When a <xref:System.Threading.Tasks.Dataflow.JoinBlock%602> object receives data from all sources, it propagates that data to its target, which in this example is an <xref:System.Threading.Tasks.Dataflow.ActionBlock%601> object.</span></span> <span data-ttu-id="2ad63-110">두 <xref:System.Threading.Tasks.Dataflow.JoinBlock%602> 개체 모두 `MemoryResource` 개체의 공유 풀에서 읽습니다.</span><span class="sxs-lookup"><span data-stu-id="2ad63-110">Both <xref:System.Threading.Tasks.Dataflow.JoinBlock%602> objects read from a shared pool of `MemoryResource` objects.</span></span>  
  
 [!code-csharp[TPLDataflow_NonGreedyJoin#1](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_nongreedyjoin/cs/nongreedyjoin.cs#1)]
 [!code-vb[TPLDataflow_NonGreedyJoin#1](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_nongreedyjoin/vb/nongreedyjoin.vb#1)]  
  
 <span data-ttu-id="2ad63-111">`MemoryResource` 개체의 공유 풀을 효율적으로 사용할 수 있도록 하기 위해 이 예제에서는 <xref:System.Threading.Tasks.Dataflow.GroupingDataflowBlockOptions> 속성이 <xref:System.Threading.Tasks.Dataflow.GroupingDataflowBlockOptions.Greedy%2A>로 설정된 `False` 개체를 지정하여 non-greedy 모드에서 작동하는 <xref:System.Threading.Tasks.Dataflow.JoinBlock%602> 개체를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="2ad63-111">To enable efficient use of the shared pool of `MemoryResource` objects, this example specifies a <xref:System.Threading.Tasks.Dataflow.GroupingDataflowBlockOptions> object that has the <xref:System.Threading.Tasks.Dataflow.GroupingDataflowBlockOptions.Greedy%2A> property set to `False` to create <xref:System.Threading.Tasks.Dataflow.JoinBlock%602> objects that act in non-greedy mode.</span></span> <span data-ttu-id="2ad63-112">non-greedy 조인 블록은 각 소스에서 메시지를 사용할 수 있을 때까지 들어오는 메시지를 모두 연기합니다.</span><span class="sxs-lookup"><span data-stu-id="2ad63-112">A non-greedy join block postpones all incoming messages until one is available from each source.</span></span> <span data-ttu-id="2ad63-113">연기된 메시지 중 하나라도 다른 블록에서 수락된 경우 조인 블록은 프로세스를 다시 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="2ad63-113">If any of the postponed messages were accepted by another block, the join block restarts the process.</span></span> <span data-ttu-id="2ad63-114">non-greedy 모드에서 하나 이상의 소스 블록을 공유하는 조인 블록은 다른 블록이 데이터를 기다릴 때 작업을 진행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2ad63-114">Non-greedy mode enables join blocks that share one or more source blocks to make forward progress as the other blocks wait for data.</span></span> <span data-ttu-id="2ad63-115">이 예제에서 `MemoryResource` 개체가 `memoryResources` 풀에 추가되는 경우 두 번째 데이터 소스를 받을 첫 번째 조인 블록은 작업을 진행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2ad63-115">In this example, if a `MemoryResource` object is added to the `memoryResources` pool, the first join block to receive its second data source can make forward progress.</span></span> <span data-ttu-id="2ad63-116">이 예제에서 기본값인 greedy 모드를 사용한다면 한 조인 블록이 `MemoryResource` 개체를 사용하고 두 번째 리소스를 사용할 수 있을 때까지 기다릴 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2ad63-116">If this example were to use greedy mode, which is the default, one join block might take the `MemoryResource` object and wait for the second resource to become available.</span></span> <span data-ttu-id="2ad63-117">그러나 다른 조인 블록이 두 번째 데이터 소스를 사용할 수 있는 경우 `MemoryResource` 개체가 또 다른 조인 블록에서 사용되었기 때문에 작업을 진행할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="2ad63-117">However, if the other join block has its second data source available, it cannot make forward progress because the `MemoryResource` object has been taken by the other join block.</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="2ad63-118">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="2ad63-118">Compiling the Code</span></span>  
 <span data-ttu-id="2ad63-119">예제 코드를 복사하여 Visual Studio 프로젝트에 붙여넣거나, `DataflowNonGreedyJoin.cs`(Visual Basic의 경우 `DataflowNonGreedyJoin.vb`) 파일에 붙여넣은 후 Visual Studio 명령 프롬프트 창에서 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="2ad63-119">Copy the example code and paste it in a Visual Studio project, or paste it in a file that is named `DataflowNonGreedyJoin.cs` (`DataflowNonGreedyJoin.vb` for Visual Basic), and then run the following command in a Visual Studio Command Prompt window.</span></span>  
  
 <span data-ttu-id="2ad63-120">Visual C#</span><span class="sxs-lookup"><span data-stu-id="2ad63-120">Visual C#</span></span>  
  
 <span data-ttu-id="2ad63-121">**csc.exe /r:System.Threading.Tasks.Dataflow.dll DataflowNonGreedyJoin.cs**</span><span class="sxs-lookup"><span data-stu-id="2ad63-121">**csc.exe /r:System.Threading.Tasks.Dataflow.dll DataflowNonGreedyJoin.cs**</span></span>  
  
 <span data-ttu-id="2ad63-122">Visual Basic</span><span class="sxs-lookup"><span data-stu-id="2ad63-122">Visual Basic</span></span>  
  
 <span data-ttu-id="2ad63-123">**vbc.exe /r:System.Threading.Tasks.Dataflow.dll DataflowNonGreedyJoin.vb**</span><span class="sxs-lookup"><span data-stu-id="2ad63-123">**vbc.exe /r:System.Threading.Tasks.Dataflow.dll DataflowNonGreedyJoin.vb**</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="2ad63-124">강력한 프로그래밍</span><span class="sxs-lookup"><span data-stu-id="2ad63-124">Robust Programming</span></span>  
 <span data-ttu-id="2ad63-125">non-greedy 조인을 사용하면 응용 프로그램에서 교착 상태를 방지하는 데도 도움이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2ad63-125">The use of non-greedy joins can also help you prevent deadlock in your application.</span></span> <span data-ttu-id="2ad63-126">소프트웨어 응용 프로그램에서 *교착 상태*는 두 개 이상의 프로세스가 각각 리소스를 보유하고 함께 다른 프로세스가 다른 리소스를 해제할 때까지 대기하는 경우 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="2ad63-126">In a software application, *deadlock* occurs when two or more processes each hold a resource and mutually wait for another process to release some other resource.</span></span> <span data-ttu-id="2ad63-127">두 가지 <xref:System.Threading.Tasks.Dataflow.JoinBlock%602> 개체를 정의하는 응용 프로그램의 경우,</span><span class="sxs-lookup"><span data-stu-id="2ad63-127">Consider an application that defines two <xref:System.Threading.Tasks.Dataflow.JoinBlock%602> objects.</span></span> <span data-ttu-id="2ad63-128">두 개체는 각각 두 공유 소스 블록에서 데이터를 읽습니다.</span><span class="sxs-lookup"><span data-stu-id="2ad63-128">Both objects each read data from two shared source blocks.</span></span> <span data-ttu-id="2ad63-129">greedy 모드에서 한 조인 블록이 첫 번째 소스에서 읽고 두 번째 조인 블록이 두 번째 소스에서 읽는 경우 두 조인 블록은 상대방이 리소스를 해제하기를 서로 기다리기 때문에 응용 프로그램에서 교착 상태가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2ad63-129">In greedy mode, if one join block reads from the first source and the second join block reads from the second source, the application might deadlock because both join blocks mutually wait for the other to release its resource.</span></span> <span data-ttu-id="2ad63-130">non-greedy 모드에서는 각 조인 블록이 모든 데이터를 사용할 수 있는 경우에만 소스에서 읽으므로 교착 상태의 위험이 제거됩니다.</span><span class="sxs-lookup"><span data-stu-id="2ad63-130">In non-greedy mode, each join block reads from its sources only when all data is available, and therefore, the risk of deadlock is eliminated.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2ad63-131">참고 항목</span><span class="sxs-lookup"><span data-stu-id="2ad63-131">See Also</span></span>  
 [<span data-ttu-id="2ad63-132">데이터 흐름</span><span class="sxs-lookup"><span data-stu-id="2ad63-132">Dataflow</span></span>](../../../docs/standard/parallel-programming/dataflow-task-parallel-library.md)
