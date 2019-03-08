---
title: Async (Visual Basic) 응용 프로그램 미세 조정
ms.date: 07/20/2015
ms.assetid: 4c3e7997-a95f-4fbe-a6ac-60ba042d30b9
ms.openlocfilehash: bd03e0874cedd360f5b31984b4b49b3d5b647c7f
ms.sourcegitcommit: 58fc0e6564a37fa1b9b1b140a637e864c4cf696e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/08/2019
ms.locfileid: "57677047"
---
# <a name="fine-tuning-your-async-application-visual-basic"></a><span data-ttu-id="b7205-102">Async (Visual Basic) 응용 프로그램 미세 조정</span><span class="sxs-lookup"><span data-stu-id="b7205-102">Fine-Tuning Your Async Application (Visual Basic)</span></span>
<span data-ttu-id="b7205-103"><xref:System.Threading.Tasks.Task> 형식이 제공하는 메서드 및 속성을 사용하여 async 애플리케이션에 정확성 및 유연성을 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b7205-103">You can add precision and flexibility to your async applications by using the methods and properties that the <xref:System.Threading.Tasks.Task> type makes available.</span></span> <span data-ttu-id="b7205-104">이 섹션의 항목에서는 <xref:System.Threading.CancellationToken>을 사용하는 예제와 <xref:System.Threading.Tasks.Task.WhenAll%2A?displayProperty=nameWithType> 및 <xref:System.Threading.Tasks.Task.WhenAny%2A?displayProperty=nameWithType>과 같은 중요한 `Task` 메서드를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="b7205-104">The topics in this section show examples that use <xref:System.Threading.CancellationToken> and important `Task` methods such as <xref:System.Threading.Tasks.Task.WhenAll%2A?displayProperty=nameWithType> and <xref:System.Threading.Tasks.Task.WhenAny%2A?displayProperty=nameWithType>.</span></span>  
  
 <span data-ttu-id="b7205-105">`WhenAny` 및 `WhenAll`를 사용하면 더 쉽게 여러 작업을 시작하고 단일 작업을 모니터링하여 완료할 때까지 기다릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b7205-105">By using `WhenAny` and `WhenAll`, you can more easily start multiple tasks and await their completion by monitoring a single task.</span></span>  
  
-   <span data-ttu-id="b7205-106">`WhenAny`는 컬렉션의 임의 작업이 완료되면 완료되는 작업을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="b7205-106">`WhenAny` returns a task that completes when any task in a collection is complete.</span></span>  
  
     <span data-ttu-id="b7205-107">사용 하는 예제에 대 한 `WhenAny`를 참조 하세요 [취소 작업 남은 비동기 작업 하나가 완료 되 면 (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/cancel-remaining-async-tasks-after-one-is-complete.md)하 고 [여러 비동기 작업을 시작 하 고 프로세스에 완료 될 때마다 (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/start-multiple-async-tasks-and-process-them-as-they-complete.md).</span><span class="sxs-lookup"><span data-stu-id="b7205-107">For examples that use `WhenAny`, see  [Cancel Remaining Async Tasks after One Is Complete (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/cancel-remaining-async-tasks-after-one-is-complete.md)and [Start Multiple Async Tasks and Process Them As They Complete (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/start-multiple-async-tasks-and-process-them-as-they-complete.md).</span></span>  
  
-   <span data-ttu-id="b7205-108">`WhenAll`은 컬렉션의 모든 작업이 완료되면 완료되는 작업을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="b7205-108">`WhenAll` returns a task that completes when all tasks in a collection are complete.</span></span>  
  
     <span data-ttu-id="b7205-109">자세한 내용과 `WhenAll`을 사용하는 예제는 [방법: Task.WhenAll (Visual Basic)을 사용 하 여 비동기 연습 확장](../../../../visual-basic/programming-guide/concepts/async/how-to-extend-the-async-walkthrough-by-using-task-whenall.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="b7205-109">For more information and an example that uses `WhenAll`, see [How to: Extend the Async Walkthrough by Using Task.WhenAll (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/how-to-extend-the-async-walkthrough-by-using-task-whenall.md).</span></span>  
  
 <span data-ttu-id="b7205-110">이 섹션에 포함된 예제는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="b7205-110">This section includes the following examples.</span></span>  
  
-   <span data-ttu-id="b7205-111">[비동기 작업 또는 작업 (Visual Basic)의 목록을 취소](../../../../visual-basic/programming-guide/concepts/async/cancel-an-async-task-or-a-list-of-tasks.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="b7205-111">[Cancel an Async Task or a List of Tasks (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/cancel-an-async-task-or-a-list-of-tasks.md).</span></span>  
  
-   [<span data-ttu-id="b7205-112">(Visual Basic) 시간의 기간 이후 비동기 작업 취소</span><span class="sxs-lookup"><span data-stu-id="b7205-112">Cancel Async Tasks after a Period of Time (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/async/cancel-async-tasks-after-a-period-of-time.md)  
  
-   [<span data-ttu-id="b7205-113">하나가 (Visual Basic) 완료 되 면 남은 비동기 작업 취소</span><span class="sxs-lookup"><span data-stu-id="b7205-113">Cancel Remaining Async Tasks after One Is Complete (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/async/cancel-remaining-async-tasks-after-one-is-complete.md)  
  
-   [<span data-ttu-id="b7205-114">여러 비동기 작업을 시작 하 고 (Visual Basic)를 완료 될 때마다 처리</span><span class="sxs-lookup"><span data-stu-id="b7205-114">Start Multiple Async Tasks and Process Them As They Complete (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/async/start-multiple-async-tasks-and-process-them-as-they-complete.md)  
  
> [!NOTE]
>  <span data-ttu-id="b7205-115">예제를 실행하려면 Visual Studio 2012 이상 및 .NET Framework 4.5 이상이 컴퓨터에 설치되어 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b7205-115">To run the examples, you must have Visual Studio 2012 or newer and the .NET Framework 4.5 or newer installed on your computer.</span></span>  
  
 <span data-ttu-id="b7205-116">다음 그림과 같이 프로젝트는 프로세스를 시작하는 단추와 프로세스를 취소하는 단추가 포함된 UI를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="b7205-116">The projects create a UI that contains a button that starts the process and a button that cancels it, as the following image shows.</span></span> <span data-ttu-id="b7205-117">단추 이름은 `startButton` 및 `cancelButton`입니다.</span><span class="sxs-lookup"><span data-stu-id="b7205-117">The buttons are named `startButton` and `cancelButton`.</span></span>  
  
 <span data-ttu-id="b7205-118">![취소 단추가 있는 WPF 창](./media/fine-tuning-your-async-application/cancellation-and-start-button.png "시작 및 중지 단추를 사용 하 여 대화 상자")</span><span class="sxs-lookup"><span data-stu-id="b7205-118">![WPF window with Cancel button](./media/fine-tuning-your-async-application/cancellation-and-start-button.png "Dialog box with a Start and Stop button")</span></span>  
  
 <span data-ttu-id="b7205-119">[Async 샘플: 애플리케이션 미세 조정](https://code.msdn.microsoft.com/Async-Fine-Tuning-Your-a676abea)에서 전체 WPF(Windows Presentation Foundation) 프로젝트를 다운로드하여 완료할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b7205-119">You can download the complete Windows Presentation Foundation (WPF) projects from [Async Sample: Fine Tuning Your Application](https://code.msdn.microsoft.com/Async-Fine-Tuning-Your-a676abea).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b7205-120">참고자료</span><span class="sxs-lookup"><span data-stu-id="b7205-120">See also</span></span>
- [<span data-ttu-id="b7205-121">Async 및 Await를 사용한 비동기 프로그래밍(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b7205-121">Asynchronous Programming with Async and Await (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/async/index.md)
