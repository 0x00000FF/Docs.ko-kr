---
title: "잉크 입력 컨트롤 만들기"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- ink strokes [WPF], managing
- managing ink strokes [WPF]
- ink input control [WPF]
- input from mouse [WPF], accepting
- mouse input [WPF], accepting
- ink [WPF], rendering
- ink strokes [WPF], collecting
- rendering ink [WPF]
- collecting ink strokes [WPF]
- DynamicRenderer objects [WPF]
- StylusPlugIn objects [WPF]
ms.assetid: c31f3a67-cb3f-4ded-af9e-ed21f6575b26
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 2cfc6553fe9dd176d2aa557df906141c13a5f425
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="creating-an-ink-input-control"></a><span data-ttu-id="ac54c-102">잉크 입력 컨트롤 만들기</span><span class="sxs-lookup"><span data-stu-id="ac54c-102">Creating an Ink Input Control</span></span>
<span data-ttu-id="ac54c-103">컨트롤을 만들 수는 사용자 지정 하는 동적 및 정적으로 잉크를 렌더링 합니다.</span><span class="sxs-lookup"><span data-stu-id="ac54c-103">You can create a custom control that dynamically and statically renders ink.</span></span> <span data-ttu-id="ac54c-104">즉, 사용자가 스트로크를 일으키는 잉크 "배치" 태블릿 펜 고 잉크 후 표시에 추가 된 컨트롤을 클립보드에서 붙여 넣은 태블릿 펜을 통해 또는 파일에서 로드 표시를 그릴 때 잉크를 렌더링 합니다.</span><span class="sxs-lookup"><span data-stu-id="ac54c-104">That is, render ink as a user draws a stroke, causing the ink to appear to "flow" from the tablet pen, and display ink after it is added to the control, either via the tablet pen, pasted from the Clipboard, or loaded from a file.</span></span> <span data-ttu-id="ac54c-105">잉크를 동적으로 렌더링 하려면 컨트롤을 사용 해야는 <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer>합니다.</span><span class="sxs-lookup"><span data-stu-id="ac54c-105">To dynamically render ink, your control must use a <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer>.</span></span> <span data-ttu-id="ac54c-106">잉크를 정적으로 렌더링 하려면 스타일러스 이벤트 메서드를 재정의 해야 (<xref:System.Windows.UIElement.OnStylusDown%2A>, <xref:System.Windows.UIElement.OnStylusMove%2A>, 및 <xref:System.Windows.UIElement.OnStylusUp%2A>)를 수집 하 <xref:System.Windows.Input.StylusPoint> 데이터를 스트로크를 만들고 추가 하는 프로그램 <xref:System.Windows.Controls.InkPresenter> (잉크를 렌더링 하는 컨트롤에).</span><span class="sxs-lookup"><span data-stu-id="ac54c-106">To statically render ink, you must override the stylus event methods (<xref:System.Windows.UIElement.OnStylusDown%2A>, <xref:System.Windows.UIElement.OnStylusMove%2A>, and <xref:System.Windows.UIElement.OnStylusUp%2A>) to collect <xref:System.Windows.Input.StylusPoint> data, create strokes, and add them to an <xref:System.Windows.Controls.InkPresenter> (which renders the ink on the control).</span></span>  
  
 <span data-ttu-id="ac54c-107">이 항목에는 다음과 같은 하위 단원이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ac54c-107">This topic contains the following subsections:</span></span>  
  
-   [<span data-ttu-id="ac54c-108">방법: 스타일러스 포인트 데이터 수집 및 잉크 스트로크 만들기</span><span class="sxs-lookup"><span data-stu-id="ac54c-108">How to: Collect Stylus Point Data and Create Ink Strokes</span></span>](#CollectingStylusPointDataAndCreatingInkStrokes)  
  
-   [<span data-ttu-id="ac54c-109">방법: 마우스 입력을 허용 하도록 컨트롤을 사용 하도록 설정</span><span class="sxs-lookup"><span data-stu-id="ac54c-109">How to: Enable Your Control to Accept Input from the Mouse</span></span>](#EnablingYourControlToAcceptInputTromTheMouse)  
  
-   [<span data-ttu-id="ac54c-110">정리 및</span><span class="sxs-lookup"><span data-stu-id="ac54c-110">Putting it together</span></span>](#PuttingItTogether)  
  
-   [<span data-ttu-id="ac54c-111">추가 플러그 인 및 DynamicRenderers를 사용 하 여</span><span class="sxs-lookup"><span data-stu-id="ac54c-111">Using Additional Plug-ins and DynamicRenderers</span></span>](#UsingAdditionalPluginsAndDynamicRenderers)  
  
-   [<span data-ttu-id="ac54c-112">결론</span><span class="sxs-lookup"><span data-stu-id="ac54c-112">Conclusion</span></span>](#AdvancedInkHandling_Conclusion)  
  
<a name="CollectingStylusPointDataAndCreatingInkStrokes"></a>   
## <a name="how-to-collect-stylus-point-data-and-create-ink-strokes"></a><span data-ttu-id="ac54c-113">방법: 스타일러스 포인트 데이터 수집 및 잉크 스트로크 만들기</span><span class="sxs-lookup"><span data-stu-id="ac54c-113">How to: Collect Stylus Point Data and Create Ink Strokes</span></span>  
 <span data-ttu-id="ac54c-114">스트로크를 수집 하 고 잉크를 관리 하는 컨트롤을 만들려면 다음을 수행.</span><span class="sxs-lookup"><span data-stu-id="ac54c-114">To create a control that collects and manages ink strokes do the following:</span></span>  
  
1.  <span data-ttu-id="ac54c-115">클래스를 파생 <xref:System.Windows.Controls.Control> 에서 파생 된 클래스 중 하나 또는 <xref:System.Windows.Controls.Control>와 같은 <xref:System.Windows.Controls.Label>합니다.</span><span class="sxs-lookup"><span data-stu-id="ac54c-115">Derive a class from <xref:System.Windows.Controls.Control> or one of the classes derived from <xref:System.Windows.Controls.Control>, such as <xref:System.Windows.Controls.Label>.</span></span>  
  
     [!code-csharp[AdvancedInkTopicsSamples#20](../../../../samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/StylusControl.cs#20)]  
    [!code-csharp[AdvancedInkTopicsSamples#14](../../../../samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/StylusControlSnippets.cs#14)]  
    [!code-csharp[AdvancedInkTopicsSamples#15](../../../../samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/StylusControlSnippets.cs#15)]  
  
2.  <span data-ttu-id="ac54c-116">추가 <xref:System.Windows.Controls.InkPresenter> 을 설정 하 고는 클래스는 <xref:System.Windows.Controls.ContentControl.Content%2A> 속성을 새 <xref:System.Windows.Controls.InkPresenter>합니다.</span><span class="sxs-lookup"><span data-stu-id="ac54c-116">Add an <xref:System.Windows.Controls.InkPresenter> to the class and set the <xref:System.Windows.Controls.ContentControl.Content%2A> property to the new <xref:System.Windows.Controls.InkPresenter>.</span></span>  
  
     [!code-csharp[AdvancedInkTopicsSamples#16](../../../../samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/StylusControlSnippets.cs#16)]  
  
3.  <span data-ttu-id="ac54c-117">연결는 <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer.RootVisual%2A> 의 <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> 에 <xref:System.Windows.Controls.InkPresenter> 호출 하 여는 <xref:System.Windows.Controls.InkPresenter.AttachVisuals%2A> 메서드를 추가 하 고는 <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> 에 <xref:System.Windows.UIElement.StylusPlugIns%2A> 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="ac54c-117">Attach the <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer.RootVisual%2A> of the <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> to the <xref:System.Windows.Controls.InkPresenter> by calling the <xref:System.Windows.Controls.InkPresenter.AttachVisuals%2A> method, and add the <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> to the <xref:System.Windows.UIElement.StylusPlugIns%2A> collection.</span></span> <span data-ttu-id="ac54c-118">이 통해는 <xref:System.Windows.Controls.InkPresenter> 을 잉크로 설정 하면 제어 스타일러스 지점 데이터를 수집 합니다.</span><span class="sxs-lookup"><span data-stu-id="ac54c-118">This allows the <xref:System.Windows.Controls.InkPresenter> to display the ink as the stylus point data is collected by your control.</span></span>  
  
     [!code-csharp[AdvancedInkTopicsSamples#17](../../../../samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/StylusControlSnippets.cs#17)]  
    [!code-csharp[AdvancedInkTopicsSamples#18](../../../../samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/StylusControlSnippets.cs#18)]  
  
4.  <span data-ttu-id="ac54c-119"><xref:System.Windows.UIElement.OnStylusDown%2A> 메서드를 재정의합니다.</span><span class="sxs-lookup"><span data-stu-id="ac54c-119">Override the <xref:System.Windows.UIElement.OnStylusDown%2A> method.</span></span>  <span data-ttu-id="ac54c-120">이 방법에 대 한 호출을 사용 하 여 스타일러스 캡처 <xref:System.Windows.Input.Stylus.Capture%2A>합니다.</span><span class="sxs-lookup"><span data-stu-id="ac54c-120">In this method, capture the stylus with a call to <xref:System.Windows.Input.Stylus.Capture%2A>.</span></span> <span data-ttu-id="ac54c-121">스타일러스를 캡처하여를 계속 받으려면 컨트롤은 <xref:System.Windows.UIElement.StylusMove> 및 <xref:System.Windows.UIElement.StylusUp> 위에 있는 컨트롤의 경계를 벗어나 하는 경우에 이벤트입니다.</span><span class="sxs-lookup"><span data-stu-id="ac54c-121">By capturing the stylus, your control will to continue to receive <xref:System.Windows.UIElement.StylusMove> and <xref:System.Windows.UIElement.StylusUp> events even if the stylus leaves the control's boundaries.</span></span> <span data-ttu-id="ac54c-122">필수 엄격 하 게 하지만 효율적인 사용자 환경을 가급적 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="ac54c-122">This is not strictly mandatory, but almost always desired for a good user experience.</span></span> <span data-ttu-id="ac54c-123">새 <xref:System.Windows.Input.StylusPointCollection> 수집 하기 위해 <xref:System.Windows.Input.StylusPoint> 데이터입니다.</span><span class="sxs-lookup"><span data-stu-id="ac54c-123">Create a new <xref:System.Windows.Input.StylusPointCollection> to gather <xref:System.Windows.Input.StylusPoint> data.</span></span> <span data-ttu-id="ac54c-124">초기 집합을 마지막으로 추가 <xref:System.Windows.Input.StylusPoint> 데이터를는 <xref:System.Windows.Input.StylusPointCollection>합니다.</span><span class="sxs-lookup"><span data-stu-id="ac54c-124">Finally, add the initial set of <xref:System.Windows.Input.StylusPoint> data to the <xref:System.Windows.Input.StylusPointCollection>.</span></span>  
  
     [!code-csharp[AdvancedInkTopicsSamples#7](../../../../samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/StylusControl.cs#7)]  
  
5.  <span data-ttu-id="ac54c-125">재정의 <xref:System.Windows.UIElement.OnStylusMove%2A> 메서드를 추가 하 고는 <xref:System.Windows.Input.StylusPoint> 데이터를는 <xref:System.Windows.Input.StylusPointCollection> 앞에서 만든 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="ac54c-125">Override the <xref:System.Windows.UIElement.OnStylusMove%2A> method and add the <xref:System.Windows.Input.StylusPoint> data to the <xref:System.Windows.Input.StylusPointCollection> object that you created earlier.</span></span>  
  
     [!code-csharp[AdvancedInkTopicsSamples#8](../../../../samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/StylusControl.cs#8)]  
  
6.  <span data-ttu-id="ac54c-126">재정의 <xref:System.Windows.UIElement.OnStylusUp%2A> 메서드는 새 <xref:System.Windows.Ink.Stroke> 와 <xref:System.Windows.Input.StylusPointCollection> 데이터입니다.</span><span class="sxs-lookup"><span data-stu-id="ac54c-126">Override the <xref:System.Windows.UIElement.OnStylusUp%2A> method and create a new <xref:System.Windows.Ink.Stroke> with the <xref:System.Windows.Input.StylusPointCollection> data.</span></span> <span data-ttu-id="ac54c-127">새 추가 <xref:System.Windows.Ink.Stroke> 하기 위해 생성는 <xref:System.Windows.Controls.InkPresenter.Strokes%2A> 의 컬렉션은 <xref:System.Windows.Controls.InkPresenter> 스타일러스 캡처를 해제 하 고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ac54c-127">Add the new <xref:System.Windows.Ink.Stroke> you created to the <xref:System.Windows.Controls.InkPresenter.Strokes%2A> collection of the <xref:System.Windows.Controls.InkPresenter> and release stylus capture.</span></span>  
  
     [!code-csharp[AdvancedInkTopicsSamples#10](../../../../samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/StylusControl.cs#10)]  
  
<a name="EnablingYourControlToAcceptInputTromTheMouse"></a>   
## <a name="how-to-enable-your-control-to-accept-input-from-the-mouse"></a><span data-ttu-id="ac54c-128">방법: 마우스 입력을 허용 하도록 컨트롤을 사용 하도록 설정</span><span class="sxs-lookup"><span data-stu-id="ac54c-128">How to: Enable Your Control to Accept Input from the Mouse</span></span>  
 <span data-ttu-id="ac54c-129">응용 프로그램에 위의 컨트롤을 추가 하 고 실행 한 마우스를 사용 하 여 입력 장치로 스트로크 유지 되지 않습니다을 알 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ac54c-129">If you add the preceding control to your application, run it, and use the mouse as an input device, you will notice that the strokes are not persisted.</span></span> <span data-ttu-id="ac54c-130">선을 마우스 입력된 장치로 사용 되는 유지 하려면 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="ac54c-130">To persist the strokes when the mouse is used as the input device do the following:</span></span>  
  
1.  <span data-ttu-id="ac54c-131">재정의 <xref:System.Windows.UIElement.OnMouseLeftButtonDown%2A> 을 새로 만듭니다 <xref:System.Windows.Input.StylusPointCollection> 이벤트가 발생할 때 마우스의 위치를 받고을 만들는 <xref:System.Windows.Input.StylusPoint> 지점 데이터를 사용 하 고 추가 <xref:System.Windows.Input.StylusPoint> 에 <xref:System.Windows.Input.StylusPointCollection>합니다.</span><span class="sxs-lookup"><span data-stu-id="ac54c-131">Override the <xref:System.Windows.UIElement.OnMouseLeftButtonDown%2A> and create a new <xref:System.Windows.Input.StylusPointCollection> Get the position of the mouse when the event occurred and create a <xref:System.Windows.Input.StylusPoint> using the point data and add the <xref:System.Windows.Input.StylusPoint> to the <xref:System.Windows.Input.StylusPointCollection>.</span></span>  
  
     [!code-csharp[AdvancedInkTopicsSamples#11](../../../../samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/StylusControl.cs#11)]  
  
2.  <span data-ttu-id="ac54c-132"><xref:System.Windows.UIElement.OnMouseMove%2A> 메서드를 재정의합니다.</span><span class="sxs-lookup"><span data-stu-id="ac54c-132">Override the <xref:System.Windows.UIElement.OnMouseMove%2A> method.</span></span> <span data-ttu-id="ac54c-133">이벤트가 발생 한 경우는 마우스의 상대 위치를 받고을 만들는 <xref:System.Windows.Input.StylusPoint> 지점 데이터를 사용 하 여 합니다.</span><span class="sxs-lookup"><span data-stu-id="ac54c-133">Get the position of the mouse when the event occurred and create a <xref:System.Windows.Input.StylusPoint> using the point data.</span></span>  <span data-ttu-id="ac54c-134">추가 <xref:System.Windows.Input.StylusPoint> 에 <xref:System.Windows.Input.StylusPointCollection> 앞에서 만든 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="ac54c-134">Add the <xref:System.Windows.Input.StylusPoint> to the <xref:System.Windows.Input.StylusPointCollection> object that you created earlier.</span></span>  
  
     [!code-csharp[AdvancedInkTopicsSamples#12](../../../../samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/StylusControl.cs#12)]  
  
3.  <span data-ttu-id="ac54c-135"><xref:System.Windows.UIElement.OnMouseLeftButtonUp%2A> 메서드를 재정의합니다.</span><span class="sxs-lookup"><span data-stu-id="ac54c-135">Override the <xref:System.Windows.UIElement.OnMouseLeftButtonUp%2A> method.</span></span>  <span data-ttu-id="ac54c-136">새 <xref:System.Windows.Ink.Stroke> 와 <xref:System.Windows.Input.StylusPointCollection> 데이터를 새 추가 <xref:System.Windows.Ink.Stroke> 하기 위해 생성는 <xref:System.Windows.Controls.InkPresenter.Strokes%2A> 의 컬렉션은 <xref:System.Windows.Controls.InkPresenter>합니다.</span><span class="sxs-lookup"><span data-stu-id="ac54c-136">Create a new <xref:System.Windows.Ink.Stroke> with the <xref:System.Windows.Input.StylusPointCollection> data, and add the new <xref:System.Windows.Ink.Stroke> you created to the <xref:System.Windows.Controls.InkPresenter.Strokes%2A> collection of the <xref:System.Windows.Controls.InkPresenter>.</span></span>  
  
     [!code-csharp[AdvancedInkTopicsSamples#13](../../../../samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/StylusControl.cs#13)]  
  
<a name="PuttingItTogether"></a>   
## <a name="putting-it-together"></a><span data-ttu-id="ac54c-137">정리 및</span><span class="sxs-lookup"><span data-stu-id="ac54c-137">Putting it together</span></span>  
 <span data-ttu-id="ac54c-138">다음 예제는 사용자가 마우스 또는 펜을 사용 하는 경우 잉크를 수집 하는 사용자 지정 컨트롤입니다.</span><span class="sxs-lookup"><span data-stu-id="ac54c-138">The following example is a custom control that collects ink when the user uses either the mouse or the pen.</span></span>  
  
 [!code-csharp[AdvancedInkTopicsSamples#20](../../../../samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/StylusControl.cs#20)]  
[!code-csharp[AdvancedInkTopicsSamples#6](../../../../samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/StylusControl.cs#6)]  
  
<a name="UsingAdditionalPluginsAndDynamicRenderers"></a>   
## <a name="using-additional-plug-ins-and-dynamicrenderers"></a><span data-ttu-id="ac54c-139">추가 플러그 인 및 DynamicRenderers를 사용 하 여</span><span class="sxs-lookup"><span data-stu-id="ac54c-139">Using Additional Plug-ins and DynamicRenderers</span></span>  
 <span data-ttu-id="ac54c-140">사용자 지정 컨트롤에는 InkCanvas 같이 사용자 지정을 가질 수 있습니다 <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> 및 추가 <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="ac54c-140">Like the InkCanvas, your custom control can have custom <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> and additional <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> objects.</span></span> <span data-ttu-id="ac54c-141">이를 추가 <xref:System.Windows.UIElement.StylusPlugIns%2A> 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="ac54c-141">Add these to the <xref:System.Windows.UIElement.StylusPlugIns%2A> collection.</span></span> <span data-ttu-id="ac54c-142">순서는 <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> 개체에 <xref:System.Windows.Input.StylusPlugIns.StylusPlugInCollection> 렌더링 될 때 잉크의 모양에 영향을 줍니다.</span><span class="sxs-lookup"><span data-stu-id="ac54c-142">The order of the <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> objects in the <xref:System.Windows.Input.StylusPlugIns.StylusPlugInCollection> affects the appearance of the ink when it is rendered.</span></span> <span data-ttu-id="ac54c-143">있다고 가정 하면는 <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> 호출 `dynamicRenderer` 및 사용자 지정 <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> 호출 `translatePlugin` 태블릿 펜에서 잉크를 오프셋입니다.</span><span class="sxs-lookup"><span data-stu-id="ac54c-143">Suppose you have a <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> called `dynamicRenderer` and a custom <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> called `translatePlugin` that offsets the ink from the tablet pen.</span></span> <span data-ttu-id="ac54c-144">경우 `translatePlugin` 은 첫 번째 <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> 에 <xref:System.Windows.Input.StylusPlugIns.StylusPlugInCollection>, 및 `dynamicRenderer` 는 두 번째 사용자가 펜 "이동" 하 잉크 오프셋 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ac54c-144">If `translatePlugin` is the first <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> in the <xref:System.Windows.Input.StylusPlugIns.StylusPlugInCollection>, and `dynamicRenderer` is the second, the ink that "flows" will be offset as the user moves the pen.</span></span> <span data-ttu-id="ac54c-145">경우 `dynamicRenderer` 처음, 및 `translatePlugin` 는 두 번째 사용자가 펜 뗄 때까지 잉크 오프셋 되지 것입니다.</span><span class="sxs-lookup"><span data-stu-id="ac54c-145">If `dynamicRenderer` is first, and `translatePlugin` is second, the ink will not be offset until the user lifts the pen.</span></span>  
  
<a name="AdvancedInkHandling_Conclusion"></a>   
## <a name="conclusion"></a><span data-ttu-id="ac54c-146">결론</span><span class="sxs-lookup"><span data-stu-id="ac54c-146">Conclusion</span></span>  
 <span data-ttu-id="ac54c-147">수집 하 여 스타일러스 이벤트 메서드를 재정의 하 여 잉크를 렌더링 하는 컨트롤을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ac54c-147">You can create a control that collects and renders ink by overriding the stylus event methods.</span></span> <span data-ttu-id="ac54c-148">컨트롤을 직접 만들어서 파생 <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> 클래스를 삽입 하는에 <xref:System.Windows.Input.StylusPlugIns.StylusPlugInCollection>, 디지털 잉크 상상할 수 있는 거의 모든 동작을 구현할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ac54c-148">By creating your own control, deriving your own <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> classes, and inserting them the into <xref:System.Windows.Input.StylusPlugIns.StylusPlugInCollection>, you can implement virtually any behavior imaginable with digital ink.</span></span> <span data-ttu-id="ac54c-149">에 액세스할 수 있는 <xref:System.Windows.Input.StylusPoint> 것으로 데이터는 생성으로 사용자 지정할 수 있도록 <xref:System.Windows.Input.Stylus> 입력 하 고 응용 프로그램에 따라 화면에 렌더링 합니다.</span><span class="sxs-lookup"><span data-stu-id="ac54c-149">You have access to the <xref:System.Windows.Input.StylusPoint> data as it is generated, giving you the opportunity to  customize <xref:System.Windows.Input.Stylus> input and render it on the screen as appropriate for your application.</span></span> <span data-ttu-id="ac54c-150">이러한 하위 수준 액세스를 갖고 있으므로 <xref:System.Windows.Input.StylusPoint> 데이터를 잉크 컬렉션을 구현 하 고 응용 프로그램에 대 한 최적의 성능으로 렌더링 합니다.</span><span class="sxs-lookup"><span data-stu-id="ac54c-150">Because you have such low-level access to the <xref:System.Windows.Input.StylusPoint> data, you can implement ink collection and render it with optimal performance for your application.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ac54c-151">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ac54c-151">See Also</span></span>  
 [<span data-ttu-id="ac54c-152">고급 잉크 처리</span><span class="sxs-lookup"><span data-stu-id="ac54c-152">Advanced Ink Handling</span></span>](../../../../docs/framework/wpf/advanced/advanced-ink-handling.md)  
 [<span data-ttu-id="ac54c-153">액세스 및 조작을 펜 입력</span><span class="sxs-lookup"><span data-stu-id="ac54c-153">Accessing and Manipulating Pen Input</span></span>](http://go.microsoft.com/fwlink/?LinkId=50752&clcid=0x409)
