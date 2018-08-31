---
title: '연습: 백그라운드에서 작업 실행'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- background tasks
- forms [Windows Forms], multithreading
- forms [Windows Forms], background operations
- background threads
- BackgroundWorker class [Windows Forms], examples
- threading [Windows Forms], background operations
- background operations
ms.assetid: 1b9a4e0a-f134-48ff-a1be-c461446a31ba
ms.openlocfilehash: 09019f24248985c0a1057873f0226ee69a30ca9d
ms.sourcegitcommit: fe02afbc39e78afd78cc6050e4a9c12a75f579f8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/30/2018
ms.locfileid: "43254756"
---
# <a name="walkthrough-running-an-operation-in-the-background"></a><span data-ttu-id="fa5e4-102">연습: 백그라운드에서 작업 실행</span><span class="sxs-lookup"><span data-stu-id="fa5e4-102">Walkthrough: Running an Operation in the Background</span></span>
<span data-ttu-id="fa5e4-103">완료하는 데 오랜 시간이 걸리는 작업이 있으며 사용자 인터페이스에서 지연이 발생되지 않게 하려는 경우 <xref:System.ComponentModel.BackgroundWorker> 클래스를 사용하여 다른 스레드에서 작업을 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fa5e4-103">If you have an operation that will take a long time to complete, and you do not want to cause delays in your user interface, you can use the <xref:System.ComponentModel.BackgroundWorker> class to run the operation on another thread.</span></span>  
  
 <span data-ttu-id="fa5e4-104">이 예제에서 사용 되는 코드의 전체 목록은 참조 하세요 [방법: 백그라운드에서 작업 실행](../../../../docs/framework/winforms/controls/how-to-run-an-operation-in-the-background.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="fa5e4-104">For a complete listing of the code used in this example, see [How to: Run an Operation in the Background](../../../../docs/framework/winforms/controls/how-to-run-an-operation-in-the-background.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="fa5e4-105">표시되는 대화 상자와 메뉴 명령은 활성 설정이나 버전에 따라 도움말에서 설명하는 것과 다를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fa5e4-105">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="fa5e4-106">설정을 변경하려면 **도구** 메뉴에서 **설정 가져오기 및 내보내기** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="fa5e4-106">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="fa5e4-107">자세한 내용은 [Visual Studio IDE 개인 설정](/visualstudio/ide/personalizing-the-visual-studio-ide)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="fa5e4-107">For more information, see [Personalize the Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).</span></span>  
  
### <a name="to-run-an-operation-in-the-background"></a><span data-ttu-id="fa5e4-108">백그라운드에서 작업을 실행 하려면</span><span class="sxs-lookup"><span data-stu-id="fa5e4-108">To run an operation in the background</span></span>  
  
1.  <span data-ttu-id="fa5e4-109">Windows Forms 디자이너에서 활성 폼을 사용 하 여 두를 끌어 <xref:System.Windows.Forms.Button> 에서 제어를 **도구 상자** 폼을 설정 합니다 `Name` 및 <xref:System.Windows.Forms.Control.Text%2A> 다음 표에 따라 단추의 속성을 합니다.</span><span class="sxs-lookup"><span data-stu-id="fa5e4-109">With your form active in the Windows Forms Designer, drag two <xref:System.Windows.Forms.Button> controls from the **Toolbox** to the form, and then set the `Name` and <xref:System.Windows.Forms.Control.Text%2A> properties of the buttons according to the following table.</span></span>  
  
    |<span data-ttu-id="fa5e4-110">단추</span><span class="sxs-lookup"><span data-stu-id="fa5e4-110">Button</span></span>|<span data-ttu-id="fa5e4-111">이름</span><span class="sxs-lookup"><span data-stu-id="fa5e4-111">Name</span></span>|<span data-ttu-id="fa5e4-112">텍스트</span><span class="sxs-lookup"><span data-stu-id="fa5e4-112">Text</span></span>|  
    |------------|----------|----------|  
    |`button1`|`startBtn`|<span data-ttu-id="fa5e4-113">**Start**</span><span class="sxs-lookup"><span data-stu-id="fa5e4-113">**Start**</span></span>|  
    |`button2`|`cancelBtn`|<span data-ttu-id="fa5e4-114">**취소**</span><span class="sxs-lookup"><span data-stu-id="fa5e4-114">**Cancel**</span></span>|  
  
2.  <span data-ttu-id="fa5e4-115">열기를 **도구 상자**를 클릭 합니다 **구성 요소** 탭 한 다음 끌어는 <xref:System.ComponentModel.BackgroundWorker> 구성 요소를 폼.</span><span class="sxs-lookup"><span data-stu-id="fa5e4-115">Open the **Toolbox**, click the **Components** tab, and then drag the <xref:System.ComponentModel.BackgroundWorker> component onto your form.</span></span>  
  
     <span data-ttu-id="fa5e4-116">합니다 `backgroundWorker1` 구성 요소에 표시 되는 **구성 요소 트레이에**합니다.</span><span class="sxs-lookup"><span data-stu-id="fa5e4-116">The `backgroundWorker1` component appears in the **Component Tray**.</span></span>  
  
3.  <span data-ttu-id="fa5e4-117">에 **속성** 창에서 설정 합니다 <xref:System.ComponentModel.BackgroundWorker.WorkerSupportsCancellation%2A> 속성을 `true`합니다.</span><span class="sxs-lookup"><span data-stu-id="fa5e4-117">In the **Properties** window, set the <xref:System.ComponentModel.BackgroundWorker.WorkerSupportsCancellation%2A> property to `true`.</span></span>  
  
4.  <span data-ttu-id="fa5e4-118">에 **속성** 창을 **이벤트** 단추를 두 번 클릭 하는 <xref:System.ComponentModel.BackgroundWorker.DoWork> 및 <xref:System.ComponentModel.BackgroundWorker.RunWorkerCompleted> 이벤트 처리기를 만들려면 이벤트.</span><span class="sxs-lookup"><span data-stu-id="fa5e4-118">In the **Properties** window, click on the **Events** button, and then double-click the <xref:System.ComponentModel.BackgroundWorker.DoWork> and <xref:System.ComponentModel.BackgroundWorker.RunWorkerCompleted> events to create event handlers.</span></span>  
  
5.  <span data-ttu-id="fa5e4-119">에 시간이 많이 걸리는 코드를 삽입 합니다 <xref:System.ComponentModel.BackgroundWorker.DoWork> 이벤트 처리기입니다.</span><span class="sxs-lookup"><span data-stu-id="fa5e4-119">Insert your time-consuming code into the <xref:System.ComponentModel.BackgroundWorker.DoWork> event handler.</span></span>  
  
6.  <span data-ttu-id="fa5e4-120">작업에 필요한 모든 매개 변수를 추출 합니다 <xref:System.ComponentModel.DoWorkEventArgs.Argument%2A> 의 속성을 <xref:System.ComponentModel.DoWorkEventArgs> 매개 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="fa5e4-120">Extract any parameters required by the operation from the <xref:System.ComponentModel.DoWorkEventArgs.Argument%2A> property of the <xref:System.ComponentModel.DoWorkEventArgs> parameter.</span></span>  
  
7.  <span data-ttu-id="fa5e4-121">에 계산의 결과 할당 합니다 <xref:System.ComponentModel.DoWorkEventArgs.Result%2A> 의 속성을 <xref:System.ComponentModel.DoWorkEventArgs>.</span><span class="sxs-lookup"><span data-stu-id="fa5e4-121">Assign the result of the computation to the <xref:System.ComponentModel.DoWorkEventArgs.Result%2A> property of the <xref:System.ComponentModel.DoWorkEventArgs>.</span></span>  
  
     <span data-ttu-id="fa5e4-122">이 수는 <xref:System.ComponentModel.BackgroundWorker.RunWorkerCompleted> 이벤트 처리기입니다.</span><span class="sxs-lookup"><span data-stu-id="fa5e4-122">This is will be available to the <xref:System.ComponentModel.BackgroundWorker.RunWorkerCompleted> event handler.</span></span>  
  
     [!code-csharp[System.ComponentModel.BackgroundWorker.Example#2](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker.Example/CS/Form1.cs#2)]
     [!code-vb[System.ComponentModel.BackgroundWorker.Example#2](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker.Example/VB/Form1.vb#2)]  
  
8.  <span data-ttu-id="fa5e4-123">작업의 결과 검색 하는 코드를 삽입 합니다 <xref:System.ComponentModel.BackgroundWorker.RunWorkerCompleted> 이벤트 처리기입니다.</span><span class="sxs-lookup"><span data-stu-id="fa5e4-123">Insert code for retrieving the result of your operation in the <xref:System.ComponentModel.BackgroundWorker.RunWorkerCompleted> event handler.</span></span>  
  
     [!code-csharp[System.ComponentModel.BackgroundWorker.Example#3](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker.Example/CS/Form1.cs#3)]
     [!code-vb[System.ComponentModel.BackgroundWorker.Example#3](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker.Example/VB/Form1.vb#3)]  
  
9. <span data-ttu-id="fa5e4-124">`TimeConsumingOperation` 메서드를 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="fa5e4-124">Implement the `TimeConsumingOperation` method.</span></span>  
  
     [!code-csharp[System.ComponentModel.BackgroundWorker.Example#4](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker.Example/CS/Form1.cs#4)]
     [!code-vb[System.ComponentModel.BackgroundWorker.Example#4](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker.Example/VB/Form1.vb#4)]  
  
10. <span data-ttu-id="fa5e4-125">Windows Forms 디자이너에서 두 번 클릭 `startButton` 만들려면는 <xref:System.Windows.Forms.Control.Click> 이벤트 처리기입니다.</span><span class="sxs-lookup"><span data-stu-id="fa5e4-125">In the Windows Forms Designer, double-click `startButton` to create the <xref:System.Windows.Forms.Control.Click> event handler.</span></span>  
  
11. <span data-ttu-id="fa5e4-126">호출 된 <xref:System.ComponentModel.BackgroundWorker.RunWorkerAsync%2A> 에서 메서드를 <xref:System.Windows.Forms.Control.Click> 에 대 한 이벤트 처리기 `startButton`합니다.</span><span class="sxs-lookup"><span data-stu-id="fa5e4-126">Call the <xref:System.ComponentModel.BackgroundWorker.RunWorkerAsync%2A> method in the <xref:System.Windows.Forms.Control.Click> event handler for `startButton`.</span></span>  
  
     [!code-csharp[System.ComponentModel.BackgroundWorker.Example#5](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker.Example/CS/Form1.cs#5)]
     [!code-vb[System.ComponentModel.BackgroundWorker.Example#5](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker.Example/VB/Form1.vb#5)]  
  
12. <span data-ttu-id="fa5e4-127">Windows Forms 디자이너에서 두 번 클릭 `cancelButton` 만들려면는 <xref:System.Windows.Forms.Control.Click> 이벤트 처리기입니다.</span><span class="sxs-lookup"><span data-stu-id="fa5e4-127">In the Windows Forms Designer, double-click `cancelButton` to create the <xref:System.Windows.Forms.Control.Click> event handler.</span></span>  
  
13. <span data-ttu-id="fa5e4-128">호출 된 <xref:System.ComponentModel.BackgroundWorker.CancelAsync%2A> 에서 메서드를 <xref:System.Windows.Forms.Control.Click> 에 대 한 이벤트 처리기 `cancelButton`합니다.</span><span class="sxs-lookup"><span data-stu-id="fa5e4-128">Call the <xref:System.ComponentModel.BackgroundWorker.CancelAsync%2A> method in the <xref:System.Windows.Forms.Control.Click> event handler for `cancelButton`.</span></span>  
  
     [!code-csharp[System.ComponentModel.BackgroundWorker.Example#6](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker.Example/CS/Form1.cs#6)]
     [!code-vb[System.ComponentModel.BackgroundWorker.Example#6](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker.Example/VB/Form1.vb#6)]  
  
14. <span data-ttu-id="fa5e4-129">파일의 맨 위에 있는 System.ComponentModel 및 System.Threading 네임 스페이스를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="fa5e4-129">At the top of the file, import the System.ComponentModel and System.Threading namespaces.</span></span>  
  
     [!code-csharp[System.ComponentModel.BackgroundWorker.Example#7](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker.Example/CS/Form1.cs#7)]
     [!code-vb[System.ComponentModel.BackgroundWorker.Example#7](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker.Example/VB/Form1.vb#7)]  
  
15. <span data-ttu-id="fa5e4-130">솔루션을 빌드하려면 f6 키를 디버거 외부에서 응용 프로그램을 실행 하려면 ctrl+f5를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="fa5e4-130">Press F6 to build the solution, and then press CTRL-F5 to run the application outside the debugger.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="fa5e4-131">F5 키를 눌러 디버거에서 응용 프로그램을 실행 하는 예외에서 발생 된 `TimeConsumingOperation` 메서드를 포착 하 디버거에 의해 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="fa5e4-131">If you press F5 to run the application under the debugger, the exception raised in the `TimeConsumingOperation` method is caught and displayed by the debugger.</span></span> <span data-ttu-id="fa5e4-132">디버거, 외부 응용 프로그램을 실행 하는 경우는 <xref:System.ComponentModel.BackgroundWorker> 예외를 처리 하 고 캐시에 <xref:System.ComponentModel.AsyncCompletedEventArgs.Error%2A> 의 속성은 <xref:System.ComponentModel.RunWorkerCompletedEventArgs>합니다.</span><span class="sxs-lookup"><span data-stu-id="fa5e4-132">When you run the application outside the debugger, the <xref:System.ComponentModel.BackgroundWorker> handles the exception and caches it in the <xref:System.ComponentModel.AsyncCompletedEventArgs.Error%2A> property of the <xref:System.ComponentModel.RunWorkerCompletedEventArgs>.</span></span>  
  
1.  <span data-ttu-id="fa5e4-133">클릭 합니다 **시작** 비동기 작업을 실행 하려면 단추를 클릭 합니다 **취소** 비동기 작업 실행을 중지 하려면 단추.</span><span class="sxs-lookup"><span data-stu-id="fa5e4-133">Click the **Start** button to run an asynchronous operation, and then click the **Cancel** button to stop a running asynchronous operation.</span></span>  
  
     <span data-ttu-id="fa5e4-134">각 작업의 결과가 <xref:System.Windows.Forms.MessageBox>에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="fa5e4-134">The outcome of each operation is displayed in a <xref:System.Windows.Forms.MessageBox>.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="fa5e4-135">다음 단계</span><span class="sxs-lookup"><span data-stu-id="fa5e4-135">Next Steps</span></span>  
  
-   <span data-ttu-id="fa5e4-136">비동기 작업이 진행 됨에 따라 진행률을 보고 하는 폼을 구현 합니다.</span><span class="sxs-lookup"><span data-stu-id="fa5e4-136">Implement a form that reports progress as an asynchronous operation proceeds.</span></span> <span data-ttu-id="fa5e4-137">자세한 내용은 [방법: 백그라운드 작업을 사용 하는 폼 구현](../../../../docs/framework/winforms/controls/how-to-implement-a-form-that-uses-a-background-operation.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="fa5e4-137">For more information, see [How to: Implement a Form That Uses a Background Operation](../../../../docs/framework/winforms/controls/how-to-implement-a-form-that-uses-a-background-operation.md).</span></span>  
  
-   <span data-ttu-id="fa5e4-138">구성 요소에 대 한 비동기 패턴을 지 원하는 클래스를 구현 합니다.</span><span class="sxs-lookup"><span data-stu-id="fa5e4-138">Implement a class that supports the Asynchronous Pattern for Components.</span></span> <span data-ttu-id="fa5e4-139">자세한 내용은 [이벤트 기반 비동기 패턴 구현](../../../../docs/standard/asynchronous-programming-patterns/implementing-the-event-based-asynchronous-pattern.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="fa5e4-139">For more information, see [Implementing the Event-based Asynchronous Pattern](../../../../docs/standard/asynchronous-programming-patterns/implementing-the-event-based-asynchronous-pattern.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fa5e4-140">참고 항목</span><span class="sxs-lookup"><span data-stu-id="fa5e4-140">See Also</span></span>  
 <xref:System.ComponentModel.BackgroundWorker>  
 <xref:System.ComponentModel.DoWorkEventArgs>  
 [<span data-ttu-id="fa5e4-141">방법: 배경 작업을 사용하는 양식 구현</span><span class="sxs-lookup"><span data-stu-id="fa5e4-141">How to: Implement a Form That Uses a Background Operation</span></span>](../../../../docs/framework/winforms/controls/how-to-implement-a-form-that-uses-a-background-operation.md)  
 [<span data-ttu-id="fa5e4-142">방법: 백그라운드에서 작업 실행</span><span class="sxs-lookup"><span data-stu-id="fa5e4-142">How to: Run an Operation in the Background</span></span>](../../../../docs/framework/winforms/controls/how-to-run-an-operation-in-the-background.md)  
 [<span data-ttu-id="fa5e4-143">BackgroundWorker 구성 요소</span><span class="sxs-lookup"><span data-stu-id="fa5e4-143">BackgroundWorker Component</span></span>](../../../../docs/framework/winforms/controls/backgroundworker-component.md)
