---
title: "방법: UI를 반환하는 추가 기능 만들기"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- creating an add-in that returns a UI [WPF]
- implementing add-in pipeline segments [WPF]
- add-in [WPF], returns a UI
ms.assetid: 57f274b7-4c66-4b72-92eb-81939a393776
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 361983c4e2b392cdf8410fdb1193a56f6d26d067
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-create-an-add-in-that-returns-a-ui"></a><span data-ttu-id="ffb1d-102">방법: UI를 반환하는 추가 기능 만들기</span><span class="sxs-lookup"><span data-stu-id="ffb1d-102">How to: Create an Add-In That Returns a UI</span></span>
<span data-ttu-id="ffb1d-103">반환 하는 추가 기능을 만드는 방법을 보여 주는이 예제는 [!INCLUDE[TLA#tla_wpf](../../../../includes/tlasharptla-wpf-md.md)] [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] 호스트에 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] 독립 실행형 응용 프로그램입니다.</span><span class="sxs-lookup"><span data-stu-id="ffb1d-103">This example shows how to create an add-in that returns a [!INCLUDE[TLA#tla_wpf](../../../../includes/tlasharptla-wpf-md.md)][!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] to a host [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] standalone application.</span></span>  
  
 <span data-ttu-id="ffb1d-104">추가 기능은 반환는 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] 즉는 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] 사용자 정의 컨트롤입니다.</span><span class="sxs-lookup"><span data-stu-id="ffb1d-104">The add-in returns a [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] that is a [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] user control.</span></span> <span data-ttu-id="ffb1d-105">이 사용자 정의 컨트롤의 콘텐츠는 클릭했을 때 메시지 상자를 표시하는 하나의 단추입니다.</span><span class="sxs-lookup"><span data-stu-id="ffb1d-105">The content of the user control is a single button that, when clicked, displays a message box.</span></span> <span data-ttu-id="ffb1d-106">[!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] 독립 실행형 응용 프로그램 추가 기능을 호스트 하 고 (추가 기능에서 반환 됨) 사용자 정의 컨트롤의 기본 응용 프로그램 창 내용으로 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ffb1d-106">The [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] standalone application hosts the add-in and displays the user control (returned by the add-in) as the content of the main application window.</span></span>  
  
 <span data-ttu-id="ffb1d-107">**필수 구성 요소**</span><span class="sxs-lookup"><span data-stu-id="ffb1d-107">**Prerequisites**</span></span>  
  
 <span data-ttu-id="ffb1d-108">이 예제에서는 강조 표시는 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] 에 대 한 확장 된 [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] 이 시나리오를 사용 하 고 다음을 가정 하는 추가 기능 모델:</span><span class="sxs-lookup"><span data-stu-id="ffb1d-108">This example highlights the [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] extensions to the [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] add-in model that enable this scenario, and assumes the following:</span></span>  
  
-   <span data-ttu-id="ffb1d-109">기술 자료는 [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] 추가 기능 모델, 파이프라인, 추가 기능 및 개발 호스트를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="ffb1d-109">Knowledge of the [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] add-in model, including pipeline, add-in, and host development.</span></span> <span data-ttu-id="ffb1d-110">이러한 개념을 잘 모르는 경우 참조 [추가 기능 및 확장성](../../../../docs/framework/add-ins/index.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="ffb1d-110">If you are unfamiliar with these concepts, see [Add-ins and Extensibility](../../../../docs/framework/add-ins/index.md).</span></span> <span data-ttu-id="ffb1d-111">파이프라인, 추가 기능 및 호스트 응용 프로그램의 구현을 설명 하는 자습서를 참조 하십시오. [연습: 확장 가능한 응용 프로그램 만들기](../../../../docs/framework/add-ins/walkthrough-create-extensible-app.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="ffb1d-111">For a tutorial that demonstrates the implementation of a pipeline, an add-in, and a host application, see [Walkthrough: Creating an Extensible Application](../../../../docs/framework/add-ins/walkthrough-create-extensible-app.md).</span></span>  
  
-   <span data-ttu-id="ffb1d-112">기술 자료는 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] 에 대 한 확장은 [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] 추가 기능에서 모델을 찾아볼 수 있습니다: [WPF 추가 기능 개요](../../../../docs/framework/wpf/app-development/wpf-add-ins-overview.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="ffb1d-112">Knowledge of the [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] extensions to the [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] add-in model, which can be found here: [WPF Add-Ins Overview](../../../../docs/framework/wpf/app-development/wpf-add-ins-overview.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="ffb1d-113">예</span><span class="sxs-lookup"><span data-stu-id="ffb1d-113">Example</span></span>  
 <span data-ttu-id="ffb1d-114">반환 하는 추가 기능을 만드는 한 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] 각 파이프라인 세그먼트에서 추가 기능을 하 고 호스트 응용 프로그램에 대 한 특정 코드가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="ffb1d-114">To create an add-in that returns a [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)][!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] requires specific code for each pipeline segment, the add-in, and the host application.</span></span>  
    
  
<a name="Contract"></a>   
## <a name="implementing-the-contract-pipeline-segment"></a><span data-ttu-id="ffb1d-115">계약 파이프라인 세그먼트 구현</span><span class="sxs-lookup"><span data-stu-id="ffb1d-115">Implementing the Contract Pipeline Segment</span></span>  
 <span data-ttu-id="ffb1d-116">반환 하기 위한 계약을 통해 메서드를 정의 해야 합니다는 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)], 반환 값 형식 이어야 하 고 <xref:System.AddIn.Contract.INativeHandleContract>합니다.</span><span class="sxs-lookup"><span data-stu-id="ffb1d-116">A method must be defined by the contract for returning a [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)], and its return value must be of type <xref:System.AddIn.Contract.INativeHandleContract>.</span></span> <span data-ttu-id="ffb1d-117">이 확인할는 `GetAddInUI` 의 메서드는 `IWPFAddInContract` 다음 코드에서 계약입니다.</span><span class="sxs-lookup"><span data-stu-id="ffb1d-117">This is demonstrated by the `GetAddInUI` method of the `IWPFAddInContract` contract in the following code.</span></span>  
  
 [!code-csharp[SimpleAddInReturnsAUISample#ContractCode](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/CSharp/Contracts/IWPFAddInContract.cs#contractcode)]
 [!code-vb[SimpleAddInReturnsAUISample#ContractCode](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/VisualBasic/Contracts/IWPFAddInContract.vb#contractcode)]  
  
<a name="AddInView"></a>   
## <a name="implementing-the-add-in-view-pipeline-segment"></a><span data-ttu-id="ffb1d-118">추가 기능 뷰 파이프라인 세그먼트 구현</span><span class="sxs-lookup"><span data-stu-id="ffb1d-118">Implementing the Add-In View Pipeline Segment</span></span>  
 <span data-ttu-id="ffb1d-119">추가 기능을 구현 하기 때문에 [!INCLUDE[TLA2#tla_ui#plural](../../../../includes/tla2sharptla-uisharpplural-md.md)] 의 서브 클래스로 제공 <xref:System.Windows.FrameworkElement>, 상관 관계에 있는 추가 기능을 보기에 대 한 메서드가 `IWPFAddInView.GetAddInUI` 형식의 값을 반환 해야 <xref:System.Windows.FrameworkElement>합니다.</span><span class="sxs-lookup"><span data-stu-id="ffb1d-119">Because the add-in implements the [!INCLUDE[TLA2#tla_ui#plural](../../../../includes/tla2sharptla-uisharpplural-md.md)] it provides as subclasses of <xref:System.Windows.FrameworkElement>, the method on the add-in view that correlates to `IWPFAddInView.GetAddInUI` must return a value of type <xref:System.Windows.FrameworkElement>.</span></span> <span data-ttu-id="ffb1d-120">다음 코드에서는 인터페이스로 구현된 계약의 추가 기능 뷰를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="ffb1d-120">The following code shows the add-in view of the contract, implemented as an interface.</span></span>  
  
 [!code-csharp[SimpleAddInReturnsAUISample#AddInViewCode](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/CSharp/AddInViews/IWPFAddInView.cs#addinviewcode)]
 [!code-vb[SimpleAddInReturnsAUISample#AddInViewCode](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/VisualBasic/AddInViews/IWPFAddInView.vb#addinviewcode)]  
  
<a name="AddInSideAdapter"></a>   
## <a name="implementing-the-add-in-side-adapter-pipeline-segment"></a><span data-ttu-id="ffb1d-121">추가 기능 쪽 어댑터 파이프라인 세그먼트 구현</span><span class="sxs-lookup"><span data-stu-id="ffb1d-121">Implementing the Add-In-Side Adapter Pipeline Segment</span></span>  
 <span data-ttu-id="ffb1d-122">계약 메서드의 반환는 <xref:System.AddIn.Contract.INativeHandleContract>, 추가 기능을 반환 하지만 <xref:System.Windows.FrameworkElement> (추가 기능을 보기에 지정 된 대로).</span><span class="sxs-lookup"><span data-stu-id="ffb1d-122">The contract method returns an <xref:System.AddIn.Contract.INativeHandleContract>, but the add-in returns a <xref:System.Windows.FrameworkElement> (as specified by the add-in view).</span></span> <span data-ttu-id="ffb1d-123">따라서는 <xref:System.Windows.FrameworkElement> 으로 변환 해야는 <xref:System.AddIn.Contract.INativeHandleContract> 격리 경계를 통과 하기 전에.</span><span class="sxs-lookup"><span data-stu-id="ffb1d-123">Consequently, the <xref:System.Windows.FrameworkElement> must be converted to an <xref:System.AddIn.Contract.INativeHandleContract> before crossing the isolation boundary.</span></span> <span data-ttu-id="ffb1d-124">이 작업은 호출 하 여 추가 기능 측 어댑터에 의해 수행 <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ViewToContractAdapter%2A>다음 코드에 나온 것 처럼 합니다.</span><span class="sxs-lookup"><span data-stu-id="ffb1d-124">This work is performed by the add-in-side adapter by calling <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ViewToContractAdapter%2A>, as shown in the following code.</span></span>  
  
 [!code-csharp[SimpleAddInReturnsAUISample#AddInSideAdapterCode](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/CSharp/AddInSideAdapters/WPFAddIn_ViewToContractAddInSideAdapter.cs#addinsideadaptercode)]
 [!code-vb[SimpleAddInReturnsAUISample#AddInSideAdapterCode](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/VisualBasic/AddInSideAdapters/WPFAddIn_ViewToContractAddInSideAdapter.vb#addinsideadaptercode)]  
  
<a name="HostView"></a>   
## <a name="implementing-the-host-view-pipeline-segment"></a><span data-ttu-id="ffb1d-125">호스트 뷰 파이프라인 세그먼트 구현</span><span class="sxs-lookup"><span data-stu-id="ffb1d-125">Implementing the Host View Pipeline Segment</span></span>  
 <span data-ttu-id="ffb1d-126">호스트 응용 프로그램이 표시 됩니다는 <xref:System.Windows.FrameworkElement>, 상관 관계에 있는 [호스트] 보기에 대 한 메서드가 `IWPFAddInHostView.GetAddInUI` 형식의 값을 반환 해야 <xref:System.Windows.FrameworkElement>합니다.</span><span class="sxs-lookup"><span data-stu-id="ffb1d-126">Because the host application will display a <xref:System.Windows.FrameworkElement>, the method on the host view that correlates to `IWPFAddInHostView.GetAddInUI` must return a value of type <xref:System.Windows.FrameworkElement>.</span></span> <span data-ttu-id="ffb1d-127">다음 코드에서는 인터페이스로 구현된 계약의 호스트 뷰를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="ffb1d-127">The following code shows the host view of the contract, implemented as an interface.</span></span>  
  
 [!code-csharp[SimpleAddInReturnsAUISample#HostViewCode](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/CSharp/HostViews/IWPFAddInHostView.cs#hostviewcode)]
 [!code-vb[SimpleAddInReturnsAUISample#HostViewCode](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/VisualBasic/HostViews/IWPFAddInHostView.vb#hostviewcode)]  
  
<a name="HostSideAdapter"></a>   
## <a name="implementing-the-host-side-adapter-pipeline-segment"></a><span data-ttu-id="ffb1d-128">호스트 측 어댑터 파이프라인 세그먼트 구현</span><span class="sxs-lookup"><span data-stu-id="ffb1d-128">Implementing the Host-Side Adapter Pipeline Segment</span></span>  
 <span data-ttu-id="ffb1d-129">계약 메서드의 반환는 <xref:System.AddIn.Contract.INativeHandleContract>, 호스트 응용 프로그램에는 있지만 <xref:System.Windows.FrameworkElement> ([호스트] 보기에서 지정 된 대로).</span><span class="sxs-lookup"><span data-stu-id="ffb1d-129">The contract method returns an <xref:System.AddIn.Contract.INativeHandleContract>, but the host application expects a <xref:System.Windows.FrameworkElement> (as specified by the host view).</span></span> <span data-ttu-id="ffb1d-130">따라서는 <xref:System.AddIn.Contract.INativeHandleContract> 으로 변환 해야는 <xref:System.Windows.FrameworkElement> 격리 경계를 통과 한 후 합니다.</span><span class="sxs-lookup"><span data-stu-id="ffb1d-130">Consequently, the <xref:System.AddIn.Contract.INativeHandleContract> must be converted to a <xref:System.Windows.FrameworkElement> after crossing the isolation boundary.</span></span> <span data-ttu-id="ffb1d-131">이 작업은 호출 하 여 호스트 측 어댑터에 의해 수행 <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ContractToViewAdapter%2A>다음 코드에 나온 것 처럼 합니다.</span><span class="sxs-lookup"><span data-stu-id="ffb1d-131">This work is performed by the host-side adapter by calling <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ContractToViewAdapter%2A>, as shown in the following code.</span></span>  
  
 [!code-csharp[SimpleAddInReturnsAUISample#HostSideAdapterCode](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/CSharp/HostSideAdapters/WPFAddIn_ContractToViewHostSideAdapter.cs#hostsideadaptercode)]
 [!code-vb[SimpleAddInReturnsAUISample#HostSideAdapterCode](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/VisualBasic/HostSideAdapters/WPFAddIn_ContractToViewHostSideAdapter.vb#hostsideadaptercode)]  
  
<a name="AddIn"></a>   
## <a name="implementing-the-add-in"></a><span data-ttu-id="ffb1d-132">추가 기능 구현</span><span class="sxs-lookup"><span data-stu-id="ffb1d-132">Implementing the Add-In</span></span>  
 <span data-ttu-id="ffb1d-133">추가 기능 측 어댑터 및 추가 기능에서 보기를 만든 추가 기능을 사용 하 여 (`WPFAddIn1.AddIn`)를 구현 해야 합니다는 `IWPFAddInView.GetAddInUI` 반환 하는 메서드는 <xref:System.Windows.FrameworkElement> 개체 (한 <xref:System.Windows.Controls.UserControl> 이 예에서).</span><span class="sxs-lookup"><span data-stu-id="ffb1d-133">With the add-in-side adapter and add-in view created, the add-in (`WPFAddIn1.AddIn`) must implement the `IWPFAddInView.GetAddInUI` method to return a <xref:System.Windows.FrameworkElement> object (a <xref:System.Windows.Controls.UserControl> in this example).</span></span> <span data-ttu-id="ffb1d-134">구현에서 <xref:System.Windows.Controls.UserControl>, `AddInUI`, 다음 코드에 의해 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ffb1d-134">The implementation of the <xref:System.Windows.Controls.UserControl>, `AddInUI`, is shown by the following code.</span></span>  
  
 [!code-xaml[SimpleAddInReturnsAUISample#AddInUIMarkup](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/CSharp/WPFAddIn1/AddInUI.xaml#addinuimarkup)]  
  
 [!code-csharp[SimpleAddInReturnsAUISample#AddInUICodeBehind](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/CSharp/WPFAddIn1/AddInUI.xaml.cs#addinuicodebehind)]
 [!code-vb[SimpleAddInReturnsAUISample#AddInUICodeBehind](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/VisualBasic/WPFAddIn1/AddInUI.xaml.vb#addinuicodebehind)]  
  
 <span data-ttu-id="ffb1d-135">구현에서 `IWPFAddInView.GetAddInUI` 추가 기능에서 단순히를 새 인스턴스를 반환 해야 `AddInUI`다음 코드에 의해 표시 된 것 처럼 합니다.</span><span class="sxs-lookup"><span data-stu-id="ffb1d-135">The implementation of the `IWPFAddInView.GetAddInUI` by the add-in simply needs to return a new instance of `AddInUI`, as shown by the following code.</span></span>  
  
 [!code-csharp[SimpleAddInReturnsAUISample#AddInCode](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/CSharp/WPFAddIn1/AddIn.cs#addincode)]
 [!code-vb[SimpleAddInReturnsAUISample#AddInCode](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/VisualBasic/WPFAddIn1/AddIn.vb#addincode)]  
  
<a name="App"></a>   
## <a name="implementing-the-host-application"></a><span data-ttu-id="ffb1d-136">호스트 응용 프로그램 구현</span><span class="sxs-lookup"><span data-stu-id="ffb1d-136">Implementing the Host Application</span></span>  
 <span data-ttu-id="ffb1d-137">호스트 응용 프로그램 호스트 측 어댑터와 생성 [호스트] 보기 צ ְ ײ는 [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] 을 열어이 파이프라인에서 추가 기능을 및 호출 기능의 호스트 뷰를 가져올 추가 기능 모델은 `IWPFAddInHostView.GetAddInUI` 메서드.</span><span class="sxs-lookup"><span data-stu-id="ffb1d-137">With the host-side adapter and host view created, the host application can use the [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] add-in model to open the pipeline, acquire a host view of the add-in, and call the `IWPFAddInHostView.GetAddInUI` method.</span></span> <span data-ttu-id="ffb1d-138">이러한 단계는 다음 코드에 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ffb1d-138">These steps are shown in the following code.</span></span>  
  
 [!code-csharp[SimpleAddInReturnsAUISample#GetUICode](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/CSharp/Host/MainWindow.xaml.cs#getuicode)]
 [!code-vb[SimpleAddInReturnsAUISample#GetUICode](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/VisualBasic/Host/MainWindow.xaml.vb#getuicode)]  
  
## <a name="see-also"></a><span data-ttu-id="ffb1d-139">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ffb1d-139">See Also</span></span>  
 [<span data-ttu-id="ffb1d-140">추가 기능 및 확장성</span><span class="sxs-lookup"><span data-stu-id="ffb1d-140">Add-ins and Extensibility</span></span>](../../../../docs/framework/add-ins/index.md)  
 [<span data-ttu-id="ffb1d-141">WPF 추가 기능 개요</span><span class="sxs-lookup"><span data-stu-id="ffb1d-141">WPF Add-Ins Overview</span></span>](../../../../docs/framework/wpf/app-development/wpf-add-ins-overview.md)
