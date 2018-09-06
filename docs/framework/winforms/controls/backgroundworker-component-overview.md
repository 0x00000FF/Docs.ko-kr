---
title: BackgroundWorker 구성 요소 개요
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
f1_keywords:
- BackgroundWorker
helpviewer_keywords:
- BackgroundWorker component
- background tasks
- Asynchronous Pattern
- forms [Windows Forms], multithreading
- components [Windows Forms], asynchronous
- forms [Windows Forms], background operations
- threading [Windows Forms], background operations
- background operations
ms.assetid: 64e9b3ab-7443-4a77-ab17-b8b8c0cb3f62
ms.openlocfilehash: 1f7da963db34434ee2631e9e2c0367abbd628656
ms.sourcegitcommit: 3c1c3ba79895335ff3737934e39372555ca7d6d0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/05/2018
ms.locfileid: "43749170"
---
# <a name="backgroundworker-component-overview"></a><span data-ttu-id="f4693-102">BackgroundWorker 구성 요소 개요</span><span class="sxs-lookup"><span data-stu-id="f4693-102">BackgroundWorker Component Overview</span></span>
<span data-ttu-id="f4693-103">일반적으로 수행하는 작업 중에는 실행 시간이 오래 걸릴 수 있는 것들이 많습니다.</span><span class="sxs-lookup"><span data-stu-id="f4693-103">There are many commonly performed operations that can take a long time to execute.</span></span> <span data-ttu-id="f4693-104">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="f4693-104">For example:</span></span>  
  
-   <span data-ttu-id="f4693-105">이미지 다운로드</span><span class="sxs-lookup"><span data-stu-id="f4693-105">Image downloads</span></span>  
  
-   <span data-ttu-id="f4693-106">웹 서비스 호출</span><span class="sxs-lookup"><span data-stu-id="f4693-106">Web service invocations</span></span>  
  
-   <span data-ttu-id="f4693-107">파일 다운로드 및 업로드(피어 투 피어 응용 프로그램용 파일 포함)</span><span class="sxs-lookup"><span data-stu-id="f4693-107">File downloads and uploads (including for peer-to-peer applications)</span></span>  
  
-   <span data-ttu-id="f4693-108">복잡한 로컬 계산</span><span class="sxs-lookup"><span data-stu-id="f4693-108">Complex local computations</span></span>  
  
-   <span data-ttu-id="f4693-109">데이터베이스 트랜잭션</span><span class="sxs-lookup"><span data-stu-id="f4693-109">Database transactions</span></span>  
  
-   <span data-ttu-id="f4693-110">로컬 디스크 액세스(메모리 액세스에 비해 속도가 느림)</span><span class="sxs-lookup"><span data-stu-id="f4693-110">Local disk access, given its slow speed relative to memory access</span></span>  
  
 <span data-ttu-id="f4693-111">이러한 작업을 수행하는 동안에는 사용자 인터페이스가 응답하지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f4693-111">Operations like these can cause your user interface to hang while they are running.</span></span> <span data-ttu-id="f4693-112">응답성이 뛰어난 UI가 필요한데 이러한 작업과 관련하여 지연이 길어지는 경우 <xref:System.ComponentModel.BackgroundWorker> 구성 요소를 사용하면 문제를 편리하게 해결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f4693-112">When you want a responsive UI and you are faced with long delays associated with such operations, the <xref:System.ComponentModel.BackgroundWorker> component provides a convenient solution.</span></span>  
  
 <span data-ttu-id="f4693-113"><xref:System.ComponentModel.BackgroundWorker> 구성 요소는 응용 프로그램의 주 UI 스레드와는 다른 스레드에서 시간이 많이 걸리는 작업을 "백그라운드"에서 비동기식으로 실행하는 기능을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="f4693-113">The <xref:System.ComponentModel.BackgroundWorker> component gives you the ability to execute time-consuming operations asynchronously ("in the background"), on a thread different from your application's main UI thread.</span></span> <span data-ttu-id="f4693-114"><xref:System.ComponentModel.BackgroundWorker>를 사용하려는 경우 백그라운드에서 실행하려는 시간이 많이 걸리는 작업자 프로세스를 지정한 다음 <xref:System.ComponentModel.BackgroundWorker.RunWorkerAsync%2A> 메서드만 호출하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f4693-114">To use a <xref:System.ComponentModel.BackgroundWorker>, you simply tell it what time-consuming worker method to execute in the background, and then you call the <xref:System.ComponentModel.BackgroundWorker.RunWorkerAsync%2A> method.</span></span> <span data-ttu-id="f4693-115">호출 스레드는 계속 정상적으로 실행되며 작업자 메서드는 비동기식으로 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="f4693-115">Your calling thread continues to run normally while the worker method runs asynchronously.</span></span> <span data-ttu-id="f4693-116">메서드가 완료되면 <xref:System.ComponentModel.BackgroundWorker>는 <xref:System.ComponentModel.BackgroundWorker.RunWorkerCompleted> 이벤트를 발생시켜 호출 스레드에 경고를 표시합니다. 이 이벤트는 필요에 따라 작업 결과를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="f4693-116">When the method is finished, the <xref:System.ComponentModel.BackgroundWorker> alerts the calling thread by firing the <xref:System.ComponentModel.BackgroundWorker.RunWorkerCompleted> event, which optionally contains the results of the operation.</span></span>  
  
 <span data-ttu-id="f4693-117">합니다 <xref:System.ComponentModel.BackgroundWorker> 구성 요소에서 사용할 수는 **도구 상자**는 **구성 요소** 탭 합니다. 폼에 <xref:System.ComponentModel.BackgroundWorker>를 추가하려면 <xref:System.ComponentModel.BackgroundWorker> 구성 요소를 폼으로 끌어 옵니다.</span><span class="sxs-lookup"><span data-stu-id="f4693-117">The <xref:System.ComponentModel.BackgroundWorker> component is available from the **Toolbox**, in the **Components** tab. To add a <xref:System.ComponentModel.BackgroundWorker> to your form, drag the <xref:System.ComponentModel.BackgroundWorker> component onto your form.</span></span> <span data-ttu-id="f4693-118">구성 요소 트레이에 표시 및 해당 속성에 표시 된 **속성** 창입니다.</span><span class="sxs-lookup"><span data-stu-id="f4693-118">It appears in the component tray, and its properties appear in the **Properties** window.</span></span>  
  
 <span data-ttu-id="f4693-119">비동기 작업을 시작하려면 <xref:System.ComponentModel.BackgroundWorker.RunWorkerAsync%2A> 메서드를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="f4693-119">To start your asynchronous operation, use the <xref:System.ComponentModel.BackgroundWorker.RunWorkerAsync%2A> method.</span></span> <span data-ttu-id="f4693-120"><xref:System.ComponentModel.BackgroundWorker.RunWorkerAsync%2A>는 작업자 메서드로 인수를 전달하는 데 사용할 수 있는 선택적 `object` 매개 변수를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="f4693-120"><xref:System.ComponentModel.BackgroundWorker.RunWorkerAsync%2A> takes an optional `object` parameter, which can be used to pass arguments to your worker method.</span></span> <span data-ttu-id="f4693-121"><xref:System.ComponentModel.BackgroundWorker> 클래스는 <xref:System.ComponentModel.BackgroundWorker.DoWork> 이벤트를 표시하며, 작업자 스레드는 <xref:System.ComponentModel.BackgroundWorker.DoWork> 이벤트 처리기를 통해 이 이벤트에 연결됩니다.</span><span class="sxs-lookup"><span data-stu-id="f4693-121">The <xref:System.ComponentModel.BackgroundWorker> class exposes the <xref:System.ComponentModel.BackgroundWorker.DoWork> event, to which your worker thread is attached through a <xref:System.ComponentModel.BackgroundWorker.DoWork> event handler.</span></span>  
  
 <span data-ttu-id="f4693-122"><xref:System.ComponentModel.BackgroundWorker.DoWork> 이벤트 처리기는 <xref:System.ComponentModel.DoWorkEventArgs> 속성을 포함하는 <xref:System.ComponentModel.DoWorkEventArgs.Argument%2A> 매개 변수를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="f4693-122">The <xref:System.ComponentModel.BackgroundWorker.DoWork> event handler takes a <xref:System.ComponentModel.DoWorkEventArgs> parameter, which has an <xref:System.ComponentModel.DoWorkEventArgs.Argument%2A> property.</span></span> <span data-ttu-id="f4693-123">이 속성은 <xref:System.ComponentModel.BackgroundWorker.RunWorkerAsync%2A>에서 매개 변수를 받으며 작업자 메서드로 전달될 수 있습니다. 이 작업자 메서드는 <xref:System.ComponentModel.BackgroundWorker.DoWork> 이벤트 처리기에서 호출됩니다.</span><span class="sxs-lookup"><span data-stu-id="f4693-123">This property receives the parameter from <xref:System.ComponentModel.BackgroundWorker.RunWorkerAsync%2A> and can be passed to your worker method, which will be called in the <xref:System.ComponentModel.BackgroundWorker.DoWork> event handler.</span></span> <span data-ttu-id="f4693-124">다음 예에서는 `ComputeFibonacci`라는 작업자 메서드에서 결과를 할당하는 방법을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="f4693-124">The following example shows how to assign a result from a worker method called `ComputeFibonacci`.</span></span> <span data-ttu-id="f4693-125">찾을 수 있습니다 보다 큰 예제의 일부 이기 [방법: 백그라운드 작업을 사용 하는 폼 구현](../../../../docs/framework/winforms/controls/how-to-implement-a-form-that-uses-a-background-operation.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="f4693-125">It is part of a larger example, which you can find at [How to: Implement a Form That Uses a Background Operation](../../../../docs/framework/winforms/controls/how-to-implement-a-form-that-uses-a-background-operation.md).</span></span>  
  
 [!code-cpp[System.ComponentModel.BackgroundWorker#5](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/CPP/fibonacciform.cpp#5)]
 [!code-csharp[System.ComponentModel.BackgroundWorker#5](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/CS/fibonacciform.cs#5)]
 [!code-vb[System.ComponentModel.BackgroundWorker#5](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/VB/fibonacciform.vb#5)]  
  
 <span data-ttu-id="f4693-126">이벤트 처리기를 사용 하 여 자세한 내용은 [이벤트](../../../../docs/standard/events/index.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="f4693-126">For more information on using event handlers, see [Events](../../../../docs/standard/events/index.md).</span></span>  
  
> [!CAUTION]
>  <span data-ttu-id="f4693-127">모든 종류의 다중 스레딩을 사용할 때는 매우 심각하고 복잡한 버그에 잠재적으로 노출됩니다.</span><span class="sxs-lookup"><span data-stu-id="f4693-127">When using multithreading of any sort, you potentially expose yourself to very serious and complex bugs.</span></span> <span data-ttu-id="f4693-128">다중 스레딩을 사용하는 솔루션을 구현하기 전에 [관리되는 스레딩을 구현하는 최선의 방법](../../../../docs/standard/threading/managed-threading-best-practices.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f4693-128">Consult the [Managed Threading Best Practices](../../../../docs/standard/threading/managed-threading-best-practices.md) before implementing any solution that uses multithreading.</span></span>  
  
 <span data-ttu-id="f4693-129">사용 하 여 대 한 자세한 내용은 합니다 <xref:System.ComponentModel.BackgroundWorker> 클래스를 참조 하십시오 [방법: 백그라운드에서 작업 실행](../../../../docs/framework/winforms/controls/how-to-run-an-operation-in-the-background.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="f4693-129">For more information on using the <xref:System.ComponentModel.BackgroundWorker> class, see [How to: Run an Operation in the Background](../../../../docs/framework/winforms/controls/how-to-run-an-operation-in-the-background.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f4693-130">참고 항목</span><span class="sxs-lookup"><span data-stu-id="f4693-130">See Also</span></span>  
 [<span data-ttu-id="f4693-131">빌드에 없음: Visual Basic의 다중 스레딩</span><span class="sxs-lookup"><span data-stu-id="f4693-131">NOT IN BUILD: Multithreading in Visual Basic</span></span>](https://msdn.microsoft.com/library/c731a50c-09c1-4468-9646-54c86b75d269)  
 [<span data-ttu-id="f4693-132">방법: 배경 작업을 사용하는 양식 구현</span><span class="sxs-lookup"><span data-stu-id="f4693-132">How to: Implement a Form That Uses a Background Operation</span></span>](../../../../docs/framework/winforms/controls/how-to-implement-a-form-that-uses-a-background-operation.md)
