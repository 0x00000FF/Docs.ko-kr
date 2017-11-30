---
title: "방법: 작업 및 해당 자식 취소"
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
helpviewer_keywords: tasks, how to cancel
ms.assetid: 08574301-8331-4719-ad50-9cf7f6ff3048
caps.latest.revision: "16"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 374068694a3aa9724905964717dc5e77c09fc0ab
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-cancel-a-task-and-its-children"></a><span data-ttu-id="8ad76-102">방법: 작업 및 해당 자식 취소</span><span class="sxs-lookup"><span data-stu-id="8ad76-102">How to: Cancel a Task and Its Children</span></span>
<span data-ttu-id="8ad76-103">이러한 예제는 다음과 같은 작업을 수행 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="8ad76-103">These examples show how to perform the following tasks:</span></span>  
  
1.  <span data-ttu-id="8ad76-104">만들고 취소 가능한 작업을 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="8ad76-104">Create and start a cancelable task.</span></span>  
  
2.  <span data-ttu-id="8ad76-105">사용자 대리자와 필요에 따라 작업 인스턴스는 취소 토큰을 전달 합니다.</span><span class="sxs-lookup"><span data-stu-id="8ad76-105">Pass a cancellation token to your user delegate and optionally to the task instance.</span></span>  
  
3.  <span data-ttu-id="8ad76-106">확인 한 사용자 대리자에서 취소 요청에 응답 합니다.</span><span class="sxs-lookup"><span data-stu-id="8ad76-106">Notice and respond to the cancellation request in your user delegate.</span></span>  
  
4.  <span data-ttu-id="8ad76-107">필요에 따라 확인할 수는 호출 스레드에서 작업이 취소 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="8ad76-107">Optionally notice on the calling thread that the task was canceled.</span></span>  
  
 <span data-ttu-id="8ad76-108">호출 스레드가; 작업을 강제로 종료 하지 않습니다. 취소를 요청한만 신호를 합니다.</span><span class="sxs-lookup"><span data-stu-id="8ad76-108">The calling thread does not forcibly end the task; it only signals that cancellation is requested.</span></span> <span data-ttu-id="8ad76-109">작업이 이미 실행 중인 경우 해당 요청을 인식 하 고 적절 하 게 응답 하는 사용자 대리자에서입니다.</span><span class="sxs-lookup"><span data-stu-id="8ad76-109">If the task is already running, it is up to the user delegate to notice the request and respond appropriately.</span></span> <span data-ttu-id="8ad76-110">취소 작업이 실행 되기 전에 요청 된 경우 사용자 대리자가 실행 되지 않으며 작업 개체가 취소 됨 상태로 전환 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="8ad76-110">If cancellation is requested before the task runs, then the user delegate is never executed and the task object transitions into the Canceled state.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8ad76-111">예제</span><span class="sxs-lookup"><span data-stu-id="8ad76-111">Example</span></span>  
 <span data-ttu-id="8ad76-112">종료 하는 방법을 보여 주는이 예제는 <xref:System.Threading.Tasks.Task> 와 해당 자식 취소 요청에 응답 합니다.</span><span class="sxs-lookup"><span data-stu-id="8ad76-112">This example shows how to terminate a <xref:System.Threading.Tasks.Task> and its children in response to a cancellation request.</span></span> <span data-ttu-id="8ad76-113">또한 <xref:System.Threading.Tasks.TaskCanceledException>을 throw하여 사용자 대리자가 종료될 때 호출 스레드에서 필요에 따라 <xref:System.Threading.Tasks.Task.Wait%2A> 메서드나 <xref:System.Threading.Tasks.Task.WaitAll%2A> 메서드를 사용하여 작업이 종료될 때까지 대기할 수 있음을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="8ad76-113">It also shows that when a user delegate terminates by throwing a <xref:System.Threading.Tasks.TaskCanceledException>, the calling thread can optionally use the <xref:System.Threading.Tasks.Task.Wait%2A> method or <xref:System.Threading.Tasks.Task.WaitAll%2A> method to wait for the tasks to finish.</span></span> <span data-ttu-id="8ad76-114">이 경우 `try/catch` 블록을 사용하여 호출 스레드에서 예외를 처리해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8ad76-114">In this case, you must use a `try/catch` block to handle the exceptions on the calling thread.</span></span>  
  
 [!code-csharp[TPL_Cancellation#04](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_cancellation/cs/cancel1.cs#04)]
 [!code-vb[TPL_Cancellation#04](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_cancellation/vb/cancel1.vb#04)]  
  
 <span data-ttu-id="8ad76-115"><xref:System.Threading.Tasks.Task?displayProperty=nameWithType> 클래스는 기반으로 하는 취소 모델와 완전히 통합 된 <xref:System.Threading.CancellationTokenSource?displayProperty=nameWithType> 및 <xref:System.Threading.CancellationToken?displayProperty=nameWithType> 형식.</span><span class="sxs-lookup"><span data-stu-id="8ad76-115">The <xref:System.Threading.Tasks.Task?displayProperty=nameWithType> class is fully integrated with the cancellation model that is based on the <xref:System.Threading.CancellationTokenSource?displayProperty=nameWithType> and <xref:System.Threading.CancellationToken?displayProperty=nameWithType> types.</span></span> <span data-ttu-id="8ad76-116">자세한 내용은 참조 [관리 되는 스레드의 취소](../../../docs/standard/threading/cancellation-in-managed-threads.md) 및 [작업 취소](../../../docs/standard/parallel-programming/task-cancellation.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="8ad76-116">For more information, see [Cancellation in Managed Threads](../../../docs/standard/threading/cancellation-in-managed-threads.md) and [Task Cancellation](../../../docs/standard/parallel-programming/task-cancellation.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8ad76-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="8ad76-117">See Also</span></span>  
 <xref:System.Threading.CancellationTokenSource?displayProperty=nameWithType>  
 <xref:System.Threading.CancellationToken?displayProperty=nameWithType>  
 <xref:System.Threading.Tasks.Task?displayProperty=nameWithType>  
 <xref:System.Threading.Tasks.Task%601?displayProperty=nameWithType>  
 [<span data-ttu-id="8ad76-118">작업 기반 비동기 프로그래밍</span><span class="sxs-lookup"><span data-stu-id="8ad76-118">Task-based Asynchronous Programming</span></span>](../../../docs/standard/parallel-programming/task-based-asynchronous-programming.md)  
 [<span data-ttu-id="8ad76-119">연결된 자식 작업 및 분리된 자식 작업</span><span class="sxs-lookup"><span data-stu-id="8ad76-119">Attached and Detached Child Tasks</span></span>](../../../docs/standard/parallel-programming/attached-and-detached-child-tasks.md)  
 [<span data-ttu-id="8ad76-120">PLINQ 및 TPL의 람다 식</span><span class="sxs-lookup"><span data-stu-id="8ad76-120">Lambda Expressions in PLINQ and TPL</span></span>](../../../docs/standard/parallel-programming/lambda-expressions-in-plinq-and-tpl.md)
