---
title: "스레딩(Visual Basic)"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
ms.assetid: 704bb04b-ff23-471d-ab12-3cec1c2bca59
caps.latest.revision: 4
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 840cc7df20250acb67bd09a8d39b353c772e82da
ms.contentlocale: ko-kr
ms.lasthandoff: 07/28/2017

---
# <a name="threading-visual-basic"></a><span data-ttu-id="4e048-102">스레딩(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="4e048-102">Threading (Visual Basic)</span></span>
<span data-ttu-id="4e048-103">스레딩을 사용하면 Visual Basic 프로그램에서 동시 처리를 수행할 수 있으므로 한 번에 여러 작업을 진행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4e048-103">Threading enables your Visual Basic program to perform concurrent processing so that you can do more than one operation at a time.</span></span> <span data-ttu-id="4e048-104">예를 들어 스레딩을 사용하여 사용자의 입력을 모니터링하고, 백그라운드 작업을 수행하고, 동시 입력 스트림을 처리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4e048-104">For example, you can use threading to monitor input from the user, perform background tasks, and handle simultaneous streams of input.</span></span>  
  
 <span data-ttu-id="4e048-105">스레드에는 다음과 같은 속성이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4e048-105">Threads have the following properties:</span></span>  
  
-   <span data-ttu-id="4e048-106">스레드를 사용하면 프로그램에서 동시 처리를 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4e048-106">Threads enable your program to perform concurrent processing.</span></span>  
  
-   <span data-ttu-id="4e048-107">.NET Framework <xref:System.Threading> 네임스페이스를 통해 스레드를 쉽게 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4e048-107">The .NET Framework <xref:System.Threading> namespace makes using threads easier.</span></span>  
  
-   <span data-ttu-id="4e048-108">스레드는 응용 프로그램의 리소스를 공유합니다.</span><span class="sxs-lookup"><span data-stu-id="4e048-108">Threads share the application's resources.</span></span> <span data-ttu-id="4e048-109">자세한 내용은 [스레드 및 스레딩 사용](https://msdn.microsoft.com/library/e1dx6b2h)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="4e048-109">For more information, see [Using Threads and Threading](https://msdn.microsoft.com/library/e1dx6b2h).</span></span>  
  
 <span data-ttu-id="4e048-110">기본적으로 Visual Basic 프로그램에는 스레드가 하나 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4e048-110">By default, a Visual Basic program has one thread.</span></span> <span data-ttu-id="4e048-111">그러나 보조 스레드를 만들어 기본 스레드와 함께 코드를 실행하는 데 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4e048-111">However, auxiliary threads can be created and used to execute code in parallel with the primary thread.</span></span> <span data-ttu-id="4e048-112">이러한 스레드를 일반적으로 *작업자 스레드*라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e048-112">These threads are often called *worker threads*.</span></span>  
  
 <span data-ttu-id="4e048-113">작업자 스레드는 기본 스레드를 묶어두지 않고서도 시간이 오래 걸리거나 시간이 중요한 작업을 수행하는 데 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4e048-113">Worker threads can be used to perform time-consuming or time-critical tasks without tying up the primary thread.</span></span> <span data-ttu-id="4e048-114">예를 들어 작업자 스레드는 이전 요청이 완료될 때까지 기다리지 않고서도 서버 응용 프로그램에서 들어오는 요청을 이행하는 데 종종 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="4e048-114">For example, worker threads are often used in server applications to fulfill incoming requests without waiting for the previous request to be completed.</span></span> <span data-ttu-id="4e048-115">또한 작업자 스레드는 사용자 인터페이스 요소를 구동하는 주 스레드가 사용자 작업에 계속 응답하도록 데스크톱 응용 프로그램에서 "백그라운드" 작업을 수행하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="4e048-115">Worker threads are also used to perform "background" tasks in desktop applications so that the main thread--which drives user interface elements--remains responsive to user actions.</span></span>  
  
 <span data-ttu-id="4e048-116">스레딩은 처리량 및 응답성 관련 문제를 해결하지만, 교착 상태 및 경합 상태 같은 리소스 공유 문제를 유발할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4e048-116">Threading solves problems with throughput and responsiveness, but it can also introduce resource-sharing issues such as deadlocks and race conditions.</span></span> <span data-ttu-id="4e048-117">여러 스레드는 파일 핸들 및 네트워크 연결 같은 다양한 리소스를 필요로 하는 작업에 적합합니다.</span><span class="sxs-lookup"><span data-stu-id="4e048-117">Multiple threads are best for tasks that require different resources such as file handles and network connections.</span></span> <span data-ttu-id="4e048-118">단일 리소스에 여러 스레드를 할당하면 동기화 문제가 발생할 수 있으며, 다른 스레드를 기다릴 때 스레드를 자주 차단하면 여러 스레드를 사용하는 목적에 어긋납니다.</span><span class="sxs-lookup"><span data-stu-id="4e048-118">Assigning multiple threads to a single resource is likely to cause synchronization issues, and having threads frequently blocked when waiting for other threads defeats the purpose of using multiple threads.</span></span>  
  
 <span data-ttu-id="4e048-119">일반적인 전략은 작업자 스레드를 사용하여, 다른 스레드에서 사용하는 많은 리소스를 필요로 하지 않는 시간이 오래 걸리는 작업이나 시간이 중요한 작업을 수행하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="4e048-119">A common strategy is to use worker threads to perform time-consuming or time-critical tasks that do not require many of the resources used by other threads.</span></span> <span data-ttu-id="4e048-120">당연히 여러 스레드에서 프로그램의 일부 리소스에 액세스해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e048-120">Naturally, some resources in your program must be accessed by multiple threads.</span></span> <span data-ttu-id="4e048-121">이러한 경우에는 <xref:System.Threading> 네임스페이스에서 스레드 동기화에 대한 클래스를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="4e048-121">For these cases, the <xref:System.Threading> namespace provides classes for synchronizing threads.</span></span> <span data-ttu-id="4e048-122">이러한 클래스에는 <xref:System.Threading.Mutex>, <xref:System.Threading.Monitor>, <xref:System.Threading.Interlocked>, <xref:System.Threading.AutoResetEvent> 및 <xref:System.Threading.ManualResetEvent>가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4e048-122">These classes include <xref:System.Threading.Mutex>, <xref:System.Threading.Monitor>, <xref:System.Threading.Interlocked>, <xref:System.Threading.AutoResetEvent>, and <xref:System.Threading.ManualResetEvent>.</span></span>  
  
 <span data-ttu-id="4e048-123">이러한 클래스의 일부 또는 모두를 사용하여 여러 스레드 작업을 동기화할 수 있지만, 스레딩에 대한 일부 지원이 Visual Basic 언어에서 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="4e048-123">You can use some or all these classes to synchronize the activities of multiple threads, but some support for threading is supported by the Visual Basic language.</span></span> <span data-ttu-id="4e048-124">예를 들어 [SyncLock 문](../../../../visual-basic/language-reference/statements/synclock-statement.md)은 <xref:System.Threading.Monitor>를 암시적으로 사용하여 동기화 기능을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="4e048-124">For example, the [SyncLock Statement](../../../../visual-basic/language-reference/statements/synclock-statement.md) provides synchronization features through implicit use of <xref:System.Threading.Monitor>.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="4e048-125">[!INCLUDE[net_v40_long](~/includes/net-v40-long-md.md)]부터는 <xref:System.Threading.Tasks.Parallel?displayProperty=fullName> 및 <xref:System.Threading.Tasks.Task?displayProperty=fullName> 클래스, [PLINQ(병렬 LINQ)](https://msdn.microsoft.com/library/dd460688), <xref:System.Collections.Concurrent?displayProperty=fullName> 네임스페이스의 새로운 동시 컬렉션 클래스, 그리고 스레드가 아닌 작업 개념을 기반으로 하는 새로운 프로그래밍 모델로 인해 다중 스레드 프로그래밍이 매우 간소화되었습니다.</span><span class="sxs-lookup"><span data-stu-id="4e048-125">Beginning with the [!INCLUDE[net_v40_long](~/includes/net-v40-long-md.md)], multithreaded programming is greatly simplified with the <xref:System.Threading.Tasks.Parallel?displayProperty=fullName> and <xref:System.Threading.Tasks.Task?displayProperty=fullName> classes, [Parallel LINQ (PLINQ)](https://msdn.microsoft.com/library/dd460688), new concurrent collection classes in the <xref:System.Collections.Concurrent?displayProperty=fullName> namespace, and a new programming model that is based on the concept of tasks rather than threads.</span></span> <span data-ttu-id="4e048-126">자세한 내용은 [병렬 프로그래밍](https://msdn.microsoft.com/library/dd460693)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="4e048-126">For more information, see [Parallel Programming](https://msdn.microsoft.com/library/dd460693).</span></span>  
  
## <a name="related-topics"></a><span data-ttu-id="4e048-127">관련 항목</span><span class="sxs-lookup"><span data-stu-id="4e048-127">Related Topics</span></span>  
  
|<span data-ttu-id="4e048-128">제목</span><span class="sxs-lookup"><span data-stu-id="4e048-128">Title</span></span>|<span data-ttu-id="4e048-129">설명</span><span class="sxs-lookup"><span data-stu-id="4e048-129">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="4e048-130">다중 스레드 응용 프로그램(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="4e048-130">Multithreaded Applications (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/threading/multithreaded-applications.md)|<span data-ttu-id="4e048-131">스레드를 만들고 사용하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="4e048-131">Describes how to create and use threads.</span></span>|  
|[<span data-ttu-id="4e048-132">다중 스레드 프로시저의 매개 변수 및 반환 값(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="4e048-132">Parameters and Return Values for Multithreaded Procedures (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/threading/parameters-and-return-values-for-multithreaded-procedures.md)|<span data-ttu-id="4e048-133">다중 스레드 응용 프로그램을 사용하여 매개 변수를 전달하고 반환하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="4e048-133">Describes how to pass and return parameters with multithreaded applications.</span></span>|  
|[<span data-ttu-id="4e048-134">연습: BackgroundWorker 구성 요소를 사용한 다중 스레딩(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="4e048-134">Walkthrough: Multithreading with the BackgroundWorker Component (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/threading/walkthrough-multithreading-with-the-backgroundworker-component.md)|<span data-ttu-id="4e048-135">간단한 다중 스레드 응용 프로그램을 만드는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="4e048-135">Shows how to create a simple multithreaded application.</span></span>|  
|[<span data-ttu-id="4e048-136">스레드 동기화(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="4e048-136">Thread Synchronization (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/threading/thread-synchronization.md)|<span data-ttu-id="4e048-137">스레드 조작을 제어하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="4e048-137">Describes how to control the interactions of threads.</span></span>|  
|[<span data-ttu-id="4e048-138">스레드 타이머(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="4e048-138">Thread Timers (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/threading/thread-timers.md)|<span data-ttu-id="4e048-139">일정한 간격으로 별도의 스레드에서 프로시저를 실행하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="4e048-139">Describes how to run procedures on separate threads at fixed intervals.</span></span>|  
|[<span data-ttu-id="4e048-140">스레드 풀링(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="4e048-140">Thread Pooling (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/threading/thread-pooling.md)|<span data-ttu-id="4e048-141">시스템에서 관리하는 작업자 스레드 풀을 사용하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="4e048-141">Describes how to use a pool of worker threads that are managed by the system.</span></span>|  
|[<span data-ttu-id="4e048-142">방법: 스레드 풀 사용(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="4e048-142">How to: Use a Thread Pool (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/threading/how-to-use-a-thread-pool.md)|<span data-ttu-id="4e048-143">스레드 풀에서 여러 스레드의 동기화된 사용을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="4e048-143">Demonstrates synchronized use of multiple threads in the thread pool.</span></span>|  
|[<span data-ttu-id="4e048-144">스레딩</span><span class="sxs-lookup"><span data-stu-id="4e048-144">Threading</span></span>](https://msdn.microsoft.com/library/3e8s7xdd)|<span data-ttu-id="4e048-145">.NET Framework에서 스레딩을 구현하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="4e048-145">Describes how to implement threading in the .NET Framework.</span></span>|

