---
title: '방법: UI를 반환하는 추가 기능 만들기'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- creating an add-in that returns a UI [WPF]
- implementing add-in pipeline segments [WPF]
- add-in [WPF], returns a UI
ms.assetid: 57f274b7-4c66-4b72-92eb-81939a393776
ms.openlocfilehash: 1886703e089ed538f68a7221906d815a8ae72076
ms.sourcegitcommit: 55f438d4d00a34b9aca9eedaac3f85590bb11565
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/23/2019
ms.locfileid: "71182662"
---
# <a name="how-to-create-an-add-in-that-returns-a-ui"></a><span data-ttu-id="1f09c-102">방법: UI를 반환하는 추가 기능 만들기</span><span class="sxs-lookup"><span data-stu-id="1f09c-102">How to: Create an Add-In That Returns a UI</span></span>
<span data-ttu-id="1f09c-103">이 예제에서는 Windows Presentation Foundation (WPF)를 호스트 WPF 독립 실행형 응용 프로그램에 반환 하는 추가 기능을 만드는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="1f09c-103">This example shows how to create an add-in that returns a Windows Presentation Foundation (WPF) to a host WPF standalone application.</span></span>  
  
 <span data-ttu-id="1f09c-104">추가 기능은 WPF 사용자 정의 컨트롤인 UI를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="1f09c-104">The add-in returns a UI that is a WPF user control.</span></span> <span data-ttu-id="1f09c-105">이 사용자 정의 컨트롤의 콘텐츠는 클릭했을 때 메시지 상자를 표시하는 하나의 단추입니다.</span><span class="sxs-lookup"><span data-stu-id="1f09c-105">The content of the user control is a single button that, when clicked, displays a message box.</span></span> <span data-ttu-id="1f09c-106">WPF 독립 실행형 응용 프로그램은 추가 기능을 호스팅하고 추가 기능에서 반환 하는 사용자 정의 컨트롤을 주 응용 프로그램 창의 콘텐츠로 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="1f09c-106">The WPF standalone application hosts the add-in and displays the user control (returned by the add-in) as the content of the main application window.</span></span>  
  
 <span data-ttu-id="1f09c-107">**필수 구성 요소**</span><span class="sxs-lookup"><span data-stu-id="1f09c-107">**Prerequisites**</span></span>  
  
 <span data-ttu-id="1f09c-108">이 예제에서는이 시나리오를 사용 하도록 설정 하는 .NET Framework 추가 기능 모델에 대 한 WPF 확장을 강조 표시 하 고 다음을 가정 합니다.</span><span class="sxs-lookup"><span data-stu-id="1f09c-108">This example highlights the WPF extensions to the .NET Framework add-in model that enable this scenario, and assumes the following:</span></span>  
  
- <span data-ttu-id="1f09c-109">파이프라인, 추가 기능 및 호스트 개발을 포함 하 여 .NET Framework 추가 기능 모델에 대 한 지식.</span><span class="sxs-lookup"><span data-stu-id="1f09c-109">Knowledge of the .NET Framework add-in model, including pipeline, add-in, and host development.</span></span> <span data-ttu-id="1f09c-110">이러한 개념을 잘 모르는 경우 [추가 기능 및 확장성](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb384200(v%3dvs.100))을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="1f09c-110">If you are unfamiliar with these concepts, see [Add-ins and Extensibility](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb384200(v%3dvs.100)).</span></span> <span data-ttu-id="1f09c-111">파이프라인, 추가 기능 및 호스트 응용 프로그램을 구현 하는 방법을 보여 주는 자습서를 보려면 [연습: 확장 가능한 응용 프로그램](../../add-ins/walkthrough-create-extensible-app.md)만들기</span><span class="sxs-lookup"><span data-stu-id="1f09c-111">For a tutorial that demonstrates the implementation of a pipeline, an add-in, and a host application, see [Walkthrough: Creating an Extensible Application](../../add-ins/walkthrough-create-extensible-app.md).</span></span>  
  
- <span data-ttu-id="1f09c-112">다음 위치에서 찾을 수 있는 .NET Framework 추가 기능 모델에 대 한 WPF 확장 정보 [WPF 추가 기능 개요](wpf-add-ins-overview.md).</span><span class="sxs-lookup"><span data-stu-id="1f09c-112">Knowledge of the WPF extensions to the .NET Framework add-in model, which can be found here: [WPF Add-Ins Overview](wpf-add-ins-overview.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="1f09c-113">예제</span><span class="sxs-lookup"><span data-stu-id="1f09c-113">Example</span></span>  
 <span data-ttu-id="1f09c-114">WPF UI를 반환 하는 추가 기능을 만들려면 각 파이프라인 세그먼트, 추가 기능 및 호스트 응용 프로그램에 대 한 특정 코드가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="1f09c-114">To create an add-in that returns a WPF UI requires specific code for each pipeline segment, the add-in, and the host application.</span></span>  

<a name="Contract"></a>   
## <a name="implementing-the-contract-pipeline-segment"></a><span data-ttu-id="1f09c-115">계약 파이프라인 세그먼트 구현</span><span class="sxs-lookup"><span data-stu-id="1f09c-115">Implementing the Contract Pipeline Segment</span></span>  
 <span data-ttu-id="1f09c-116">계약에서 UI를 반환 하기 위해 메서드를 정의 해야 하며, 반환 값은 형식 <xref:System.AddIn.Contract.INativeHandleContract>이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1f09c-116">A method must be defined by the contract for returning a UI, and its return value must be of type <xref:System.AddIn.Contract.INativeHandleContract>.</span></span> <span data-ttu-id="1f09c-117">이는 다음 코드의 `GetAddInUI` `IWPFAddInContract` 계약 메서드에서 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="1f09c-117">This is demonstrated by the `GetAddInUI` method of the `IWPFAddInContract` contract in the following code.</span></span>  
  
 [!code-csharp[SimpleAddInReturnsAUISample#ContractCode](~/samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/CSharp/Contracts/IWPFAddInContract.cs#contractcode)]
 [!code-vb[SimpleAddInReturnsAUISample#ContractCode](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/VisualBasic/Contracts/IWPFAddInContract.vb#contractcode)]  
  
<a name="AddInView"></a>   
## <a name="implementing-the-add-in-view-pipeline-segment"></a><span data-ttu-id="1f09c-118">추가 기능 뷰 파이프라인 세그먼트 구현</span><span class="sxs-lookup"><span data-stu-id="1f09c-118">Implementing the Add-In View Pipeline Segment</span></span>  
 <span data-ttu-id="1f09c-119">추가 기능은에서 [!INCLUDE[TLA2#tla_ui#plural](../../../../includes/tla2sharptla-uisharpplural-md.md)] 제공 하는를의 <xref:System.Windows.FrameworkElement>서브 클래스로 구현 하기 때문에와 상관 관계가 `IWPFAddInView.GetAddInUI` 있는 추가 기능 뷰의 메서드는 형식의 <xref:System.Windows.FrameworkElement>값을 반환 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1f09c-119">Because the add-in implements the [!INCLUDE[TLA2#tla_ui#plural](../../../../includes/tla2sharptla-uisharpplural-md.md)] it provides as subclasses of <xref:System.Windows.FrameworkElement>, the method on the add-in view that correlates to `IWPFAddInView.GetAddInUI` must return a value of type <xref:System.Windows.FrameworkElement>.</span></span> <span data-ttu-id="1f09c-120">다음 코드에서는 인터페이스로 구현된 계약의 추가 기능 뷰를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="1f09c-120">The following code shows the add-in view of the contract, implemented as an interface.</span></span>  
  
 [!code-csharp[SimpleAddInReturnsAUISample#AddInViewCode](~/samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/CSharp/AddInViews/IWPFAddInView.cs#addinviewcode)]
 [!code-vb[SimpleAddInReturnsAUISample#AddInViewCode](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/VisualBasic/AddInViews/IWPFAddInView.vb#addinviewcode)]  
  
<a name="AddInSideAdapter"></a>   
## <a name="implementing-the-add-in-side-adapter-pipeline-segment"></a><span data-ttu-id="1f09c-121">추가 기능 쪽 어댑터 파이프라인 세그먼트 구현</span><span class="sxs-lookup"><span data-stu-id="1f09c-121">Implementing the Add-In-Side Adapter Pipeline Segment</span></span>  
 <span data-ttu-id="1f09c-122">계약 메서드는를 반환 <xref:System.AddIn.Contract.INativeHandleContract>하지만 추가 기능에서을 <xref:System.Windows.FrameworkElement> 반환 합니다 (추가 기능 뷰에서 지정한 대로).</span><span class="sxs-lookup"><span data-stu-id="1f09c-122">The contract method returns an <xref:System.AddIn.Contract.INativeHandleContract>, but the add-in returns a <xref:System.Windows.FrameworkElement> (as specified by the add-in view).</span></span> <span data-ttu-id="1f09c-123">따라서 격리 경계를 통과 <xref:System.AddIn.Contract.INativeHandleContract> 하기 전에를으로 변환 해야합니다.<xref:System.Windows.FrameworkElement></span><span class="sxs-lookup"><span data-stu-id="1f09c-123">Consequently, the <xref:System.Windows.FrameworkElement> must be converted to an <xref:System.AddIn.Contract.INativeHandleContract> before crossing the isolation boundary.</span></span> <span data-ttu-id="1f09c-124">이 작업은 다음 코드와 같이를 호출 <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ViewToContractAdapter%2A>하 여 추가 기능 측 어댑터에 의해 수행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1f09c-124">This work is performed by the add-in-side adapter by calling <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ViewToContractAdapter%2A>, as shown in the following code.</span></span>  
  
 [!code-csharp[SimpleAddInReturnsAUISample#AddInSideAdapterCode](~/samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/CSharp/AddInSideAdapters/WPFAddIn_ViewToContractAddInSideAdapter.cs#addinsideadaptercode)]
 [!code-vb[SimpleAddInReturnsAUISample#AddInSideAdapterCode](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/VisualBasic/AddInSideAdapters/WPFAddIn_ViewToContractAddInSideAdapter.vb#addinsideadaptercode)]  
  
<a name="HostView"></a>   
## <a name="implementing-the-host-view-pipeline-segment"></a><span data-ttu-id="1f09c-125">호스트 뷰 파이프라인 세그먼트 구현</span><span class="sxs-lookup"><span data-stu-id="1f09c-125">Implementing the Host View Pipeline Segment</span></span>  
 <span data-ttu-id="1f09c-126">호스트 응용 프로그램은를 표시 <xref:System.Windows.FrameworkElement>하므로에 `IWPFAddInHostView.GetAddInUI` 상관 관계를 설정 하는 호스트 뷰의 메서드는 형식의 <xref:System.Windows.FrameworkElement>값을 반환 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1f09c-126">Because the host application will display a <xref:System.Windows.FrameworkElement>, the method on the host view that correlates to `IWPFAddInHostView.GetAddInUI` must return a value of type <xref:System.Windows.FrameworkElement>.</span></span> <span data-ttu-id="1f09c-127">다음 코드에서는 인터페이스로 구현된 계약의 호스트 뷰를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="1f09c-127">The following code shows the host view of the contract, implemented as an interface.</span></span>  
  
 [!code-csharp[SimpleAddInReturnsAUISample#HostViewCode](~/samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/CSharp/HostViews/IWPFAddInHostView.cs#hostviewcode)]
 [!code-vb[SimpleAddInReturnsAUISample#HostViewCode](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/VisualBasic/HostViews/IWPFAddInHostView.vb#hostviewcode)]  
  
<a name="HostSideAdapter"></a>   
## <a name="implementing-the-host-side-adapter-pipeline-segment"></a><span data-ttu-id="1f09c-128">호스트 측 어댑터 파이프라인 세그먼트 구현</span><span class="sxs-lookup"><span data-stu-id="1f09c-128">Implementing the Host-Side Adapter Pipeline Segment</span></span>  
 <span data-ttu-id="1f09c-129">계약 메서드는를 반환 <xref:System.AddIn.Contract.INativeHandleContract>하지만 호스트 응용 프로그램에는 호스트 <xref:System.Windows.FrameworkElement> 보기에 지정 된 대로가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="1f09c-129">The contract method returns an <xref:System.AddIn.Contract.INativeHandleContract>, but the host application expects a <xref:System.Windows.FrameworkElement> (as specified by the host view).</span></span> <span data-ttu-id="1f09c-130">따라서 격리 경계를 넘는 <xref:System.Windows.FrameworkElement> 후를로 변환 해야합니다.<xref:System.AddIn.Contract.INativeHandleContract></span><span class="sxs-lookup"><span data-stu-id="1f09c-130">Consequently, the <xref:System.AddIn.Contract.INativeHandleContract> must be converted to a <xref:System.Windows.FrameworkElement> after crossing the isolation boundary.</span></span> <span data-ttu-id="1f09c-131">이 작업은 다음 코드와 같이를 호출 <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ContractToViewAdapter%2A>하 여 호스트 측 어댑터에서 수행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1f09c-131">This work is performed by the host-side adapter by calling <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ContractToViewAdapter%2A>, as shown in the following code.</span></span>  
  
 [!code-csharp[SimpleAddInReturnsAUISample#HostSideAdapterCode](~/samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/CSharp/HostSideAdapters/WPFAddIn_ContractToViewHostSideAdapter.cs#hostsideadaptercode)]
 [!code-vb[SimpleAddInReturnsAUISample#HostSideAdapterCode](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/VisualBasic/HostSideAdapters/WPFAddIn_ContractToViewHostSideAdapter.vb#hostsideadaptercode)]  
  
<a name="AddIn"></a>   
## <a name="implementing-the-add-in"></a><span data-ttu-id="1f09c-132">추가 기능 구현</span><span class="sxs-lookup"><span data-stu-id="1f09c-132">Implementing the Add-In</span></span>  
 <span data-ttu-id="1f09c-133">추가 기능 측 어댑터와 추가 기능 뷰를 만든 후에는 추가`WPFAddIn1.AddIn`기능 ()에서 <xref:System.Windows.FrameworkElement> 개체를 <xref:System.Windows.Controls.UserControl> 반환 하는 `IWPFAddInView.GetAddInUI` 메서드를 구현 해야 합니다 (이 예제에서는).</span><span class="sxs-lookup"><span data-stu-id="1f09c-133">With the add-in-side adapter and add-in view created, the add-in (`WPFAddIn1.AddIn`) must implement the `IWPFAddInView.GetAddInUI` method to return a <xref:System.Windows.FrameworkElement> object (a <xref:System.Windows.Controls.UserControl> in this example).</span></span> <span data-ttu-id="1f09c-134">다음 코드는 <xref:System.Windows.Controls.UserControl>, `AddInUI`의 구현을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="1f09c-134">The implementation of the <xref:System.Windows.Controls.UserControl>, `AddInUI`, is shown by the following code.</span></span>  
  
 [!code-xaml[SimpleAddInReturnsAUISample#AddInUIMarkup](~/samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/CSharp/WPFAddIn1/AddInUI.xaml#addinuimarkup)]  
  
 [!code-csharp[SimpleAddInReturnsAUISample#AddInUICodeBehind](~/samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/CSharp/WPFAddIn1/AddInUI.xaml.cs#addinuicodebehind)]
 [!code-vb[SimpleAddInReturnsAUISample#AddInUICodeBehind](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/VisualBasic/WPFAddIn1/AddInUI.xaml.vb#addinuicodebehind)]  
  
 <span data-ttu-id="1f09c-135">다음 코드에 표시 `IWPFAddInView.GetAddInUI` 된 것 처럼 추가 기능에서를 구현 하면의 `AddInUI`새 인스턴스만 반환 하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1f09c-135">The implementation of the `IWPFAddInView.GetAddInUI` by the add-in simply needs to return a new instance of `AddInUI`, as shown by the following code.</span></span>  
  
 [!code-csharp[SimpleAddInReturnsAUISample#AddInCode](~/samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/CSharp/WPFAddIn1/AddIn.cs#addincode)]
 [!code-vb[SimpleAddInReturnsAUISample#AddInCode](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/VisualBasic/WPFAddIn1/AddIn.vb#addincode)]  
  
<a name="App"></a>   
## <a name="implementing-the-host-application"></a><span data-ttu-id="1f09c-136">호스트 애플리케이션 구현</span><span class="sxs-lookup"><span data-stu-id="1f09c-136">Implementing the Host Application</span></span>  
 <span data-ttu-id="1f09c-137">호스트 쪽 어댑터와 호스트 뷰를 만든 상태에서 호스트 응용 프로그램은 .NET Framework 추가 기능 모델을 사용 하 여 파이프라인을 열고, 추가 기능에 대 한 호스트 뷰를 가져오고, 메서드를 `IWPFAddInHostView.GetAddInUI` 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1f09c-137">With the host-side adapter and host view created, the host application can use the .NET Framework add-in model to open the pipeline, acquire a host view of the add-in, and call the `IWPFAddInHostView.GetAddInUI` method.</span></span> <span data-ttu-id="1f09c-138">이러한 단계는 다음 코드에 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1f09c-138">These steps are shown in the following code.</span></span>  
  
 [!code-csharp[SimpleAddInReturnsAUISample#GetUICode](~/samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/CSharp/Host/MainWindow.xaml.cs#getuicode)]
 [!code-vb[SimpleAddInReturnsAUISample#GetUICode](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/VisualBasic/Host/MainWindow.xaml.vb#getuicode)]  
  
## <a name="see-also"></a><span data-ttu-id="1f09c-139">참고 항목</span><span class="sxs-lookup"><span data-stu-id="1f09c-139">See also</span></span>

- <span data-ttu-id="1f09c-140">[추가 기능 및 확장성](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb384200(v%3dvs.100))</span><span class="sxs-lookup"><span data-stu-id="1f09c-140">[Add-ins and Extensibility](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb384200(v%3dvs.100))</span></span>
- [<span data-ttu-id="1f09c-141">WPF 추가 기능 개요</span><span class="sxs-lookup"><span data-stu-id="1f09c-141">WPF Add-Ins Overview</span></span>](wpf-add-ins-overview.md)
