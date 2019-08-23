---
title: '방법: UI인 추가 기능 만들기'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- creating an add-in that is a UI [WPF]
- add-ins [WPF], UI
- creating UI add-ins [WPF]
- UI add-ins [WPF], creating
- implementing UI add-ins [WPF]
- pipeline segments [WPF], creating add-ins
ms.assetid: 86375525-282b-4039-8352-8680051a10ea
ms.openlocfilehash: fa30b7860bd8afdb68b0b54cd8d40f3e1ec86077
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2019
ms.locfileid: "69949125"
---
# <a name="how-to-create-an-add-in-that-is-a-ui"></a><span data-ttu-id="f30ab-102">방법: UI인 추가 기능 만들기</span><span class="sxs-lookup"><span data-stu-id="f30ab-102">How to: Create an Add-In That Is a UI</span></span>
<span data-ttu-id="f30ab-103">이 예제에서는 WPF 독립 실행형 응용 프로그램에서 호스팅하는 Windows Presentation Foundation (WPF) 인 추가 기능을 만드는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="f30ab-103">This example shows how to create an add-in that is a Windows Presentation Foundation (WPF) which is hosted by a WPF standalone application.</span></span>  
  
 <span data-ttu-id="f30ab-104">추가 기능은 WPF 사용자 정의 컨트롤인 UI입니다.</span><span class="sxs-lookup"><span data-stu-id="f30ab-104">The add-in is a UI that is a WPF user control.</span></span> <span data-ttu-id="f30ab-105">이 사용자 정의 컨트롤의 콘텐츠는 클릭했을 때 메시지 상자를 표시하는 하나의 단추입니다.</span><span class="sxs-lookup"><span data-stu-id="f30ab-105">The content of the user control is a single button that, when clicked, displays a message box.</span></span> <span data-ttu-id="f30ab-106">WPF 독립 실행형 응용 프로그램은 주 응용 프로그램 창의 콘텐츠로 추가 기능 UI를 호스팅합니다.</span><span class="sxs-lookup"><span data-stu-id="f30ab-106">The WPF standalone application hosts the add-in UI as the content of the main application window.</span></span>  
  
 <span data-ttu-id="f30ab-107">**필수 조건**</span><span class="sxs-lookup"><span data-stu-id="f30ab-107">**Prerequisites**</span></span>  
  
 <span data-ttu-id="f30ab-108">이 예제에서는이 시나리오를 사용 하도록 설정 하는 .NET Framework 추가 기능 모델에 대 한 WPF 확장을 강조 표시 하 고 다음을 가정 합니다.</span><span class="sxs-lookup"><span data-stu-id="f30ab-108">This example highlights the WPF extensions to the .NET Framework add-in model that enable this scenario, and assumes the following:</span></span>  
  
- <span data-ttu-id="f30ab-109">파이프라인, 추가 기능 및 호스트 개발을 포함 하 여 .NET Framework 추가 기능 모델에 대 한 지식.</span><span class="sxs-lookup"><span data-stu-id="f30ab-109">Knowledge of the .NET Framework add-in model, including pipeline, add-in, and host development.</span></span> <span data-ttu-id="f30ab-110">이러한 개념을 잘 모르는 경우 [추가 기능 및 확장성](/previous-versions/dotnet/netframework-4.0/bb384200(v%3dvs.100))을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="f30ab-110">If you are unfamiliar with these concepts, see [Add-ins and Extensibility](/previous-versions/dotnet/netframework-4.0/bb384200(v%3dvs.100)).</span></span> <span data-ttu-id="f30ab-111">파이프라인, 추가 기능 및 호스트 응용 프로그램을 구현 하는 방법을 보여 주는 자습서를 보려면 [연습: 확장 가능한 응용 프로그램](/previous-versions/dotnet/netframework-4.0/bb788290(v%3dvs.100))만들기</span><span class="sxs-lookup"><span data-stu-id="f30ab-111">For a tutorial that demonstrates the implementation of a pipeline, an add-in, and a host application, see [Walkthrough: Creating an Extensible Application](/previous-versions/dotnet/netframework-4.0/bb788290(v%3dvs.100)).</span></span>  
  
- <span data-ttu-id="f30ab-112">.NET Framework 추가 기능 모델에 대 한 WPF 확장 정보</span><span class="sxs-lookup"><span data-stu-id="f30ab-112">Knowledge of the WPF extensions to the .NET Framework add-in model.</span></span> <span data-ttu-id="f30ab-113">[WPF 추가 기능 개요](wpf-add-ins-overview.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="f30ab-113">See [WPF Add-Ins Overview](wpf-add-ins-overview.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="f30ab-114">예제</span><span class="sxs-lookup"><span data-stu-id="f30ab-114">Example</span></span>  
 <span data-ttu-id="f30ab-115">WPF UI 인 추가 기능을 만들려면 각 파이프라인 세그먼트, 추가 기능 및 호스트 응용 프로그램에 대 한 특정 코드가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="f30ab-115">To create an add-in that is a WPF UI requires specific code for each pipeline segment, the add-in, and the host application.</span></span>  

<a name="Contract"></a>   
## <a name="implementing-the-contract-pipeline-segment"></a><span data-ttu-id="f30ab-116">계약 파이프라인 세그먼트 구현</span><span class="sxs-lookup"><span data-stu-id="f30ab-116">Implementing the Contract Pipeline Segment</span></span>

<span data-ttu-id="f30ab-117">추가 기능이 UI 인 경우 추가 기능에 대 한 계약은를 구현 <xref:System.AddIn.Contract.INativeHandleContract>해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f30ab-117">When an add-in is a UI, the contract for the add-in must implement <xref:System.AddIn.Contract.INativeHandleContract>.</span></span> <span data-ttu-id="f30ab-118">예제 `IWPFAddInContract` 에서는 다음 코드 <xref:System.AddIn.Contract.INativeHandleContract>와 같이을 구현 합니다.</span><span class="sxs-lookup"><span data-stu-id="f30ab-118">In the example, `IWPFAddInContract` implements <xref:System.AddIn.Contract.INativeHandleContract>, as shown in the following code.</span></span>  
  
[!code-csharp[SimpleAddInIsAUISample#ContractCode](~/samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInIsAUISample/CSharp/Contracts/IWPFAddInContract.cs#contractcode)]
[!code-vb[SimpleAddInIsAUISample#ContractCode](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleAddInIsAUISample/VisualBasic/Contracts/IWPFAddInContract.vb#contractcode)]

<a name="AddInViewPipeline"></a>   
## <a name="implementing-the-add-in-view-pipeline-segment"></a><span data-ttu-id="f30ab-119">추가 기능 뷰 파이프라인 세그먼트 구현</span><span class="sxs-lookup"><span data-stu-id="f30ab-119">Implementing the Add-In View Pipeline Segment</span></span>

<span data-ttu-id="f30ab-120">추가 기능이 <xref:System.Windows.FrameworkElement> 형식의 하위 클래스로 구현 되기 때문에 추가 기능 뷰도 하위 클래스 <xref:System.Windows.FrameworkElement>여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f30ab-120">Because the add-in is implemented as a subclass of the <xref:System.Windows.FrameworkElement> type, the add-in view must also subclass <xref:System.Windows.FrameworkElement>.</span></span> <span data-ttu-id="f30ab-121">다음 코드에서는 `WPFAddInView` 클래스로 구현 된 계약의 추가 기능 뷰를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="f30ab-121">The following code shows the add-in view of the contract, implemented as the `WPFAddInView` class.</span></span>  
  
[!code-csharp[SimpleAddInIsAUISample#AddInViewCode](~/samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInIsAUISample/CSharp/AddInViews/WPFAddInView.cs#addinviewcode)]  
[!code-vb[SimpleAddInIsAUISample#AddInViewCode](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleAddInIsAUISample/VisualBasic/AddInViews/WPFAddInView.vb#AddInViewCode)]  
  
<span data-ttu-id="f30ab-122">여기서는 추가 기능 뷰가에서 <xref:System.Windows.Controls.UserControl>파생 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f30ab-122">Here, the add-in view is derived from <xref:System.Windows.Controls.UserControl>.</span></span> <span data-ttu-id="f30ab-123">따라서 추가 기능 UI는 에서도 파생 <xref:System.Windows.Controls.UserControl>되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f30ab-123">Consequently, the add-in UI should also derive from <xref:System.Windows.Controls.UserControl>.</span></span>  
  
<a name="AddInSideAdapter"></a>
## <a name="implementing-the-add-in-side-adapter-pipeline-segment"></a><span data-ttu-id="f30ab-124">추가 기능 쪽 어댑터 파이프라인 세그먼트 구현</span><span class="sxs-lookup"><span data-stu-id="f30ab-124">Implementing the Add-In-Side Adapter Pipeline Segment</span></span>

<span data-ttu-id="f30ab-125">계약은 <xref:System.AddIn.Contract.INativeHandleContract>인 반면 추가 기능은 추가 기능 뷰 파이프라인 세그먼트로 지정 <xref:System.Windows.FrameworkElement> 되는입니다.</span><span class="sxs-lookup"><span data-stu-id="f30ab-125">While the contract is an <xref:System.AddIn.Contract.INativeHandleContract>, the add-in is a <xref:System.Windows.FrameworkElement> (as specified by the add-in view pipeline segment).</span></span> <span data-ttu-id="f30ab-126">따라서 격리 경계를 통과 <xref:System.AddIn.Contract.INativeHandleContract> 하기 전에를으로 변환 해야합니다.<xref:System.Windows.FrameworkElement></span><span class="sxs-lookup"><span data-stu-id="f30ab-126">Therefore, the <xref:System.Windows.FrameworkElement> must be converted to an <xref:System.AddIn.Contract.INativeHandleContract> before crossing the isolation boundary.</span></span> <span data-ttu-id="f30ab-127">이 작업은 다음 코드와 같이를 호출 <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ViewToContractAdapter%2A>하 여 추가 기능 측 어댑터에 의해 수행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f30ab-127">This work is performed by the add-in-side adapter by calling <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ViewToContractAdapter%2A>, as shown in the following code.</span></span>  
  
[!code-csharp[SimpleAddInIsAUISample#AddInSideAdapterCode](~/samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInIsAUISample/CSharp/AddInSideAdapters/WPFAddIn_ViewToContractAddInSideAdapter.cs#addinsideadaptercode)]  
[!code-vb[SimpleAddInIsAUISample#AddInSideAdapterCode](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleAddInIsAUISample/VisualBasic/AddInSideAdapters/WPFAddIn_ViewToContractAddInSideAdapter.vb#addinsideadaptercode)]

<span data-ttu-id="f30ab-128">추가 기능이 ui를 반환 하는 추가 기능 모델에서 ( [ui를 반환 하는 추가 기능 만들기](how-to-create-an-add-in-that-returns-a-ui.md)참조) 추가 기능 어댑터는를 호출 <xref:System.Windows.FrameworkElement> <xref:System.AddIn.Contract.INativeHandleContract> <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ViewToContractAdapter%2A>하 여를로 변환 합니다.</span><span class="sxs-lookup"><span data-stu-id="f30ab-128">In the add-in model where an add-in returns a UI (see [Create an Add-In That Returns a UI](how-to-create-an-add-in-that-returns-a-ui.md)), the add-in adapter converted the <xref:System.Windows.FrameworkElement> to an <xref:System.AddIn.Contract.INativeHandleContract> by calling <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ViewToContractAdapter%2A>.</span></span> <span data-ttu-id="f30ab-129"><xref:System.AddIn.Pipeline.FrameworkElementAdapters.ViewToContractAdapter%2A>를 호출 하는 코드를 작성 하는 데 사용할 메서드를 구현 해야 하지만이 모델 에서도를 호출 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f30ab-129"><xref:System.AddIn.Pipeline.FrameworkElementAdapters.ViewToContractAdapter%2A> must also be called in this model, although you need to implement a method from which to write the code to call it.</span></span> <span data-ttu-id="f30ab-130"><xref:System.AddIn.Pipeline.ContractBase.QueryContract%2A> <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ViewToContractAdapter%2A> 호출 하는코드에가필요한경우를호출하는코드를재정의하고구현하여이작업을수행합니다.<xref:System.AddIn.Pipeline.ContractBase.QueryContract%2A> <xref:System.AddIn.Contract.INativeHandleContract></span><span class="sxs-lookup"><span data-stu-id="f30ab-130">You do this by overriding <xref:System.AddIn.Pipeline.ContractBase.QueryContract%2A> and implementing the code that calls <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ViewToContractAdapter%2A> if the code that is calling <xref:System.AddIn.Pipeline.ContractBase.QueryContract%2A> is expecting an <xref:System.AddIn.Contract.INativeHandleContract>.</span></span> <span data-ttu-id="f30ab-131">이 경우 호출자가 호스트 쪽 어댑터가 됩니다. 이에 대해서는 이후의 하위 단원에서 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="f30ab-131">In this case, the caller will be the host-side adapter, which is covered in a subsequent subsection.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="f30ab-132">또한 호스트 응용 프로그램 ui <xref:System.AddIn.Pipeline.ContractBase.QueryContract%2A> 와 추가 기능 ui 사이에서 탭 이동을 사용 하려면이 모델에서를 재정의 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f30ab-132">You also need to override <xref:System.AddIn.Pipeline.ContractBase.QueryContract%2A> in this model to enable tabbing between host application UI and add-in UI.</span></span> <span data-ttu-id="f30ab-133">자세한 내용은 [Wpf 추가 기능 개요](wpf-add-ins-overview.md)의 "wpf 추가 기능 제한 사항"을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="f30ab-133">For more information, see "WPF Add-In Limitations" in [WPF Add-Ins Overview](wpf-add-ins-overview.md).</span></span>  
  
<span data-ttu-id="f30ab-134">추가 기능 측 어댑터는에서 <xref:System.AddIn.Contract.INativeHandleContract>파생 되는 인터페이스를 구현 하므로를 재정의 <xref:System.AddIn.Pipeline.ContractBase.QueryContract%2A> 하더라도를 구현 <xref:System.AddIn.Contract.INativeHandleContract.GetHandle%2A>해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f30ab-134">Because the add-in-side adapter implements an interface that derives from <xref:System.AddIn.Contract.INativeHandleContract>, you also need to implement <xref:System.AddIn.Contract.INativeHandleContract.GetHandle%2A>, although this is ignored when <xref:System.AddIn.Pipeline.ContractBase.QueryContract%2A> is overridden.</span></span>  
  
<a name="HostViewPipeline"></a>   
## <a name="implementing-the-host-view-pipeline-segment"></a><span data-ttu-id="f30ab-135">호스트 뷰 파이프라인 세그먼트 구현</span><span class="sxs-lookup"><span data-stu-id="f30ab-135">Implementing the Host View Pipeline Segment</span></span>

<span data-ttu-id="f30ab-136">이 모델에서 호스트 응용 프로그램은 일반적으로 호스트 뷰가 <xref:System.Windows.FrameworkElement> 하위 클래스가 될 것으로 예상 합니다.</span><span class="sxs-lookup"><span data-stu-id="f30ab-136">In this model, the host application typically expects the host view to be a <xref:System.Windows.FrameworkElement> subclass.</span></span> <span data-ttu-id="f30ab-137">호스트 측 어댑터는가 격리 경계를 <xref:System.AddIn.Contract.INativeHandleContract> <xref:System.AddIn.Contract.INativeHandleContract> 교차할 때 <xref:System.Windows.FrameworkElement> 를로 변환 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f30ab-137">The host-side adapter must convert the <xref:System.AddIn.Contract.INativeHandleContract> to a <xref:System.Windows.FrameworkElement> after the <xref:System.AddIn.Contract.INativeHandleContract> crosses the isolation boundary.</span></span> <span data-ttu-id="f30ab-138">호스트 응용 프로그램에서 메서드를 호출 하 여를 가져오기 <xref:System.Windows.FrameworkElement>때문에 호스트 뷰는를 포함 하 여를 <xref:System.Windows.FrameworkElement> "반환" 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f30ab-138">Because a method isn't being called by the host application to get the <xref:System.Windows.FrameworkElement>, the host view must "return" the <xref:System.Windows.FrameworkElement> by containing it.</span></span> <span data-ttu-id="f30ab-139">따라서 호스트 뷰는와 <xref:System.Windows.FrameworkElement> <xref:System.Windows.Controls.UserControl>같은 다른 ui를 포함할 수 있는의 서브 클래스에서 파생 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f30ab-139">Consequently, the host view must derive from a subclass of <xref:System.Windows.FrameworkElement> that can contain other UIs, such as <xref:System.Windows.Controls.UserControl>.</span></span> <span data-ttu-id="f30ab-140">다음 코드에서는 `WPFAddInHostView` 클래스로 구현 된 계약의 호스트 뷰를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="f30ab-140">The following code shows the host view of the contract, implemented as the `WPFAddInHostView` class.</span></span>  

[!code-csharp[WPFAddInHostView class](~/samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInIsAUISample/CSharp/HostViews/WPFAddInHostView.cs#HostViewCode)]
[!code-vb[WPFAddInHostView class](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleAddInIsAUISample/VisualBasic/HostViews/WPFAddInHostView.vb#HostViewCode)]

<a name="HostSideAdapter"></a>   
## <a name="implementing-the-host-side-adapter-pipeline-segment"></a><span data-ttu-id="f30ab-141">호스트 측 어댑터 파이프라인 세그먼트 구현</span><span class="sxs-lookup"><span data-stu-id="f30ab-141">Implementing the Host-Side Adapter Pipeline Segment</span></span>

<span data-ttu-id="f30ab-142">계약은 <xref:System.AddIn.Contract.INativeHandleContract>이지만 호스트 응용 프로그램에는 호스트 보기에 지정 <xref:System.Windows.Controls.UserControl> 된 대로가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="f30ab-142">While the contract is an <xref:System.AddIn.Contract.INativeHandleContract>, the host application expects a <xref:System.Windows.Controls.UserControl> (as specified by the host view).</span></span> <span data-ttu-id="f30ab-143">따라서가 <xref:System.Windows.FrameworkElement> 에서 <xref:System.AddIn.Contract.INativeHandleContract> 파생되는호스트뷰의콘텐츠로설정되기전에격리경계를통과한후를로<xref:System.Windows.Controls.UserControl>변환 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f30ab-143">Consequently, the <xref:System.AddIn.Contract.INativeHandleContract> must be converted to a <xref:System.Windows.FrameworkElement> after crossing the isolation boundary, before being set as content of the host view (which derives from <xref:System.Windows.Controls.UserControl>).</span></span>  
  
<span data-ttu-id="f30ab-144">다음 코드와 같이 이 작업은 호스트 쪽 어댑터로 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="f30ab-144">This work is performed by the host-side adapter, as shown in the following code.</span></span>  

[!code-csharp[Host-side adapter](~/samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInIsAUISample/CSharp/HostSideAdapters/WPFAddIn_ContractToViewHostSideAdapter.cs#HostSideAdapterCode)]
[!code-vb[Host-side adapter](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleAddInIsAUISample/VisualBasic/HostSideAdapters/WPFAddIn_ContractToViewHostSideAdapter.vb#HostSideAdapterCode)]

<span data-ttu-id="f30ab-145">여기에서 볼 수 있듯이 호스트 측 어댑터는 추가 기능 측 <xref:System.AddIn.Contract.INativeHandleContract> 어댑터의 <xref:System.AddIn.Pipeline.ContractBase.QueryContract%2A> 메서드를 호출 하 여를 가져옵니다 ( <xref:System.AddIn.Contract.INativeHandleContract> 가 격리 경계를 교차 하는 지점).</span><span class="sxs-lookup"><span data-stu-id="f30ab-145">As you can see, the host-side adapter acquires the <xref:System.AddIn.Contract.INativeHandleContract> by calling the add-in-side adapter's <xref:System.AddIn.Pipeline.ContractBase.QueryContract%2A> method (this is the point where the <xref:System.AddIn.Contract.INativeHandleContract> crosses the isolation boundary).</span></span>  
  
<span data-ttu-id="f30ab-146">그런 다음 호스트 측 어댑터는를 호출 <xref:System.AddIn.Contract.INativeHandleContract> <xref:System.Windows.FrameworkElement> <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ContractToViewAdapter%2A>하 여를로 변환 합니다.</span><span class="sxs-lookup"><span data-stu-id="f30ab-146">The host-side adapter then converts the <xref:System.AddIn.Contract.INativeHandleContract> to a <xref:System.Windows.FrameworkElement> by calling <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ContractToViewAdapter%2A>.</span></span> <span data-ttu-id="f30ab-147">마지막으로는 <xref:System.Windows.FrameworkElement> 호스트 뷰의 콘텐츠로 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f30ab-147">Finally, the <xref:System.Windows.FrameworkElement> is set as the content of the host view.</span></span>  
  
<a name="AddIn"></a>   
## <a name="implementing-the-add-in"></a><span data-ttu-id="f30ab-148">추가 기능 구현</span><span class="sxs-lookup"><span data-stu-id="f30ab-148">Implementing the Add-In</span></span>

<span data-ttu-id="f30ab-149">추가 기능 쪽 어댑터와 추가 기능 뷰를 배치했으면 다음 코드와 같이 추가 기능 뷰에서 파생시켜 추가 기능을 구현할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f30ab-149">With the add-in-side adapter and add-in view in place, the add-in can be implemented by deriving from the add-in view, as shown in the following code.</span></span>  

[!code-csharp[Add-in implementation](~/samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInIsAUISample/CSharp/WPFAddIn1/AddInUI.xaml.cs#AddInCodeBehind)]
[!code-vb[Add-in implementation](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleAddInIsAUISample/VisualBasic/WPFAddIn1/AddInUI.xaml.vb#AddInCodeBehind)]

<span data-ttu-id="f30ab-150">이 예제에서이 모델의 흥미로운 장점 하나를 확인할 수 있습니다. 추가 기능 개발자가 추가 기능 클래스와 추가 기능 UI가 아니라 UI 뿐 이므로 추가 기능을 구현 하기만 하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f30ab-150">From this example, you can see one interesting benefit of this model: add-in developers only need to implement the add-in (since it is the UI as well), rather than both an add-in class and an add-in UI.</span></span>  
  
<a name="HostApp"></a>
## <a name="implementing-the-host-application"></a><span data-ttu-id="f30ab-151">호스트 애플리케이션 구현</span><span class="sxs-lookup"><span data-stu-id="f30ab-151">Implementing the Host Application</span></span>

<span data-ttu-id="f30ab-152">호스트 쪽 어댑터와 호스트 뷰를 만든 경우 호스트 응용 프로그램은 .NET Framework 추가 기능 모델을 사용 하 여 파이프라인을 열고 추가 기능에 대 한 호스트 뷰를 가져올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f30ab-152">With the host-side adapter and host view created, the host application can use the .NET Framework add-in model to open the pipeline and acquire a host view of the add-in.</span></span> <span data-ttu-id="f30ab-153">이러한 단계는 다음 코드에 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f30ab-153">These steps are shown in the following code.</span></span>  

[!code-csharp[Acquiring a host view of the add-in](~/samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInIsAUISample/CSharp/Host/MainWindow.xaml.cs#GetUICode)]
[!code-vb[Acquiring a host view of the add-in](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleAddInIsAUISample/VisualBasic/Host/MainWindow.xaml.vb#GetUICode)]

<span data-ttu-id="f30ab-154">호스트 응용 프로그램은 일반적인 .NET Framework 추가 기능 모델 코드를 사용 하 여 추가 기능을 활성화 합니다 .이 경우 호스트 응용 프로그램에 호스트 뷰가 암시적으로 반환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f30ab-154">The host application uses typical .NET Framework add-in model code to activate the add-in, which implicitly returns the host view to the host application.</span></span> <span data-ttu-id="f30ab-155">그런 다음 호스트 응용 프로그램은 <xref:System.Windows.Controls.UserControl> <xref:System.Windows.Controls.Grid>에서 호스트 뷰 ()를 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="f30ab-155">The host application subsequently displays the host view (which is a <xref:System.Windows.Controls.UserControl>) from a <xref:System.Windows.Controls.Grid>.</span></span>  
  
 <span data-ttu-id="f30ab-156">추가 기능 UI와의 상호 작용을 처리 하는 코드는 추가 기능의 응용 프로그램 도메인에서 실행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f30ab-156">The code for processing interactions with the add-in UI runs in the add-in's application domain.</span></span> <span data-ttu-id="f30ab-157">이러한 상호 작용에는 다음이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="f30ab-157">These interactions include the following:</span></span>  
  
- <span data-ttu-id="f30ab-158"><xref:System.Windows.Controls.Button> 이벤트<xref:System.Windows.Controls.Primitives.ButtonBase.Click> 처리</span><span class="sxs-lookup"><span data-stu-id="f30ab-158">Handling the <xref:System.Windows.Controls.Button><xref:System.Windows.Controls.Primitives.ButtonBase.Click> event.</span></span>  
  
- <span data-ttu-id="f30ab-159">를 <xref:System.Windows.MessageBox>표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="f30ab-159">Showing the <xref:System.Windows.MessageBox>.</span></span>  
  
 <span data-ttu-id="f30ab-160">이 작업은 호스트 애플리케이션에서 완전히 격리됩니다.</span><span class="sxs-lookup"><span data-stu-id="f30ab-160">This activity is completely isolated from the host application.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f30ab-161">참고자료</span><span class="sxs-lookup"><span data-stu-id="f30ab-161">See also</span></span>

- <span data-ttu-id="f30ab-162">[추가 기능 및 확장성](/previous-versions/dotnet/netframework-4.0/bb384200(v%3dvs.100))</span><span class="sxs-lookup"><span data-stu-id="f30ab-162">[Add-ins and Extensibility](/previous-versions/dotnet/netframework-4.0/bb384200(v%3dvs.100))</span></span>
- [<span data-ttu-id="f30ab-163">WPF 추가 기능 개요</span><span class="sxs-lookup"><span data-stu-id="f30ab-163">WPF Add-Ins Overview</span></span>](wpf-add-ins-overview.md)
