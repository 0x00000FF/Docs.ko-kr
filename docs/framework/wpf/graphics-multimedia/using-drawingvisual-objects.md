---
title: DrawingVisual 개체 사용
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- visual layer [WPF], DrawingVisual objects
- DrawingVisual objects in visual layer [WPF]
ms.assetid: 0b4e711d-e640-40cb-81c3-8f5c59909b7d
ms.openlocfilehash: 01e10a4b0f0bf4959850caf3951ad4ea915edb4e
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59121721"
---
# <a name="using-drawingvisual-objects"></a><span data-ttu-id="fc8cb-102">DrawingVisual 개체 사용</span><span class="sxs-lookup"><span data-stu-id="fc8cb-102">Using DrawingVisual Objects</span></span>
<span data-ttu-id="fc8cb-103">이 항목에서는 사용 하는 방법의 개요를 제공 <xref:System.Windows.Media.DrawingVisual> 개체는 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 시각적 계층입니다.</span><span class="sxs-lookup"><span data-stu-id="fc8cb-103">This topic provides an overview of how to use <xref:System.Windows.Media.DrawingVisual> objects in the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] visual layer.</span></span>  
  
<a name="drawingvisual_object"></a>   
## <a name="drawingvisual-object"></a><span data-ttu-id="fc8cb-104">DrawingVisual 개체</span><span class="sxs-lookup"><span data-stu-id="fc8cb-104">DrawingVisual Object</span></span>  
 <span data-ttu-id="fc8cb-105"><xref:System.Windows.Media.DrawingVisual> 는 경량 그리기 클래스 도형, 이미지 또는 텍스트를 렌더링 하는 데 사용 되는 합니다.</span><span class="sxs-lookup"><span data-stu-id="fc8cb-105">The <xref:System.Windows.Media.DrawingVisual> is a lightweight drawing class that is used to render shapes, images, or text.</span></span> <span data-ttu-id="fc8cb-106">이 클래스는 성능을 향상시키는 레이아웃이나 이벤트 처리를 제공하지 않으므로 간단한 클래스로 간주됩니다.</span><span class="sxs-lookup"><span data-stu-id="fc8cb-106">This class is considered lightweight because it does not provide layout or event handling, which improves its performance.</span></span> <span data-ttu-id="fc8cb-107">이러한 이유 때문에 그리기는 배경 및 클립 아트에 적합합니다.</span><span class="sxs-lookup"><span data-stu-id="fc8cb-107">For this reason, drawings are ideal for backgrounds and clip art.</span></span>  
  
<a name="drawingvisual_host_container"></a>   
## <a name="drawingvisual-host-container"></a><span data-ttu-id="fc8cb-108">DrawingVisual 호스트 컨테이너</span><span class="sxs-lookup"><span data-stu-id="fc8cb-108">DrawingVisual Host Container</span></span>  
 <span data-ttu-id="fc8cb-109">사용 하기 위해 <xref:System.Windows.Media.DrawingVisual> 개체를 개체에 대 한 호스트 컨테이너를 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fc8cb-109">In order to use <xref:System.Windows.Media.DrawingVisual> objects, you need to create a host container for the objects.</span></span> <span data-ttu-id="fc8cb-110">호스트 컨테이너 개체에서 파생 되어야 합니다는 <xref:System.Windows.FrameworkElement> 레이아웃 및 이벤트 처리 지원 제공 하는 클래스는 <xref:System.Windows.Media.DrawingVisual> 없는 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="fc8cb-110">The host container object must derive from the <xref:System.Windows.FrameworkElement> class, which provides the layout and event handling support that the <xref:System.Windows.Media.DrawingVisual> class lacks.</span></span> <span data-ttu-id="fc8cb-111">호스트 컨테이너 개체는 주 목적이 자식 개체를 포함하는 것이므로 표시 가능한 속성을 표시하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="fc8cb-111">The host container object does not display any visible properties, since its main purpose is to contain child objects.</span></span> <span data-ttu-id="fc8cb-112">그러나 합니다 <xref:System.Windows.UIElement.Visibility%2A> 호스트 컨테이너의 속성 설정 해야 합니다 <xref:System.Windows.Visibility.Visible>고, 그렇지 않으면 해당 자식 요소의 표시 되지 것입니다.</span><span class="sxs-lookup"><span data-stu-id="fc8cb-112">However, the <xref:System.Windows.UIElement.Visibility%2A> property of the host container must be set to <xref:System.Windows.Visibility.Visible>; otherwise, none of its child elements will be visible.</span></span>  
  
 <span data-ttu-id="fc8cb-113">시각적 개체 참조를 저장 해야 하는 시각적 개체에 대 한 호스트 컨테이너 개체를 만들면 사용자는 <xref:System.Windows.Media.VisualCollection>합니다.</span><span class="sxs-lookup"><span data-stu-id="fc8cb-113">When you create a host container object for visual objects, you need to store the visual object references in a <xref:System.Windows.Media.VisualCollection>.</span></span> <span data-ttu-id="fc8cb-114">사용 된 <xref:System.Windows.Media.VisualCollection.Add%2A> 호스트 컨테이너에 시각적 개체를 추가 하는 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="fc8cb-114">Use the <xref:System.Windows.Media.VisualCollection.Add%2A> method to add a visual object to the host container.</span></span> <span data-ttu-id="fc8cb-115">다음 예에서 호스트 컨테이너 개체가 만들어지고 3 개의 시각적 개체에 추가 됩니다 해당 <xref:System.Windows.Media.VisualCollection>합니다.</span><span class="sxs-lookup"><span data-stu-id="fc8cb-115">In the following example, a host container object is created, and three visual objects are added to its <xref:System.Windows.Media.VisualCollection>.</span></span>  
  
 [!code-csharp[DrawingVisualSample#100](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingVisualSample/CSharp/Window1.xaml.cs#100)]
 [!code-vb[DrawingVisualSample#100](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DrawingVisualSample/visualbasic/window1.xaml.vb#100)]  
  
> [!NOTE]
>  <span data-ttu-id="fc8cb-116">위의 코드 예제가 발췌된 전체 코드 샘플을 보려면 [DrawingVisuals를 사용하여 적중 테스트 샘플](https://go.microsoft.com/fwlink/?LinkID=159994)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="fc8cb-116">For the complete code sample from which the preceding code example was extracted, see [Hit Test Using DrawingVisuals Sample](https://go.microsoft.com/fwlink/?LinkID=159994).</span></span>  
  
<a name="creating_drawingvisual_objects"></a>   
## <a name="creating-drawingvisual-objects"></a><span data-ttu-id="fc8cb-117">DrawingVisual 개체 만들기</span><span class="sxs-lookup"><span data-stu-id="fc8cb-117">Creating DrawingVisual Objects</span></span>  
 <span data-ttu-id="fc8cb-118">만들 때를 <xref:System.Windows.Media.DrawingVisual> 개체를 그리기 내용이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="fc8cb-118">When you create a <xref:System.Windows.Media.DrawingVisual> object, it has no drawing content.</span></span> <span data-ttu-id="fc8cb-119">개체를 검색 하 여 텍스트, 그래픽 또는 이미지 콘텐츠를 추가할 수 있습니다 <xref:System.Windows.Media.DrawingContext> 및 그리기 넣습니다.</span><span class="sxs-lookup"><span data-stu-id="fc8cb-119">You can add text, graphics, or image content by retrieving the object's <xref:System.Windows.Media.DrawingContext> and drawing into it.</span></span> <span data-ttu-id="fc8cb-120">A <xref:System.Windows.Media.DrawingContext> 호출에서 반환 되는 <xref:System.Windows.Media.DrawingVisual.RenderOpen%2A> 메서드를 <xref:System.Windows.Media.DrawingVisual> 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="fc8cb-120">A <xref:System.Windows.Media.DrawingContext> is returned by calling the <xref:System.Windows.Media.DrawingVisual.RenderOpen%2A> method of a <xref:System.Windows.Media.DrawingVisual> object.</span></span>  
  
 <span data-ttu-id="fc8cb-121">에 사각형을 그리려면를 <xref:System.Windows.Media.DrawingContext>를 사용 합니다 <xref:System.Windows.Media.DrawingContext.DrawRectangle%2A> 메서드의 <xref:System.Windows.Media.DrawingContext> 개체.</span><span class="sxs-lookup"><span data-stu-id="fc8cb-121">To draw a rectangle into the <xref:System.Windows.Media.DrawingContext>, use the <xref:System.Windows.Media.DrawingContext.DrawRectangle%2A> method of the <xref:System.Windows.Media.DrawingContext> object.</span></span> <span data-ttu-id="fc8cb-122">다른 형식의 콘텐츠를 그리기 위한 비슷한 메서드가 존재합니다.</span><span class="sxs-lookup"><span data-stu-id="fc8cb-122">Similar methods exist for drawing other types of content.</span></span> <span data-ttu-id="fc8cb-123">그리기 콘텐츠를 완료 하면를 <xref:System.Windows.Media.DrawingContext>, 호출 합니다 <xref:System.Windows.Media.DrawingContext.Close%2A> 닫는 메서드를는 <xref:System.Windows.Media.DrawingContext> 콘텐츠를 유지 합니다.</span><span class="sxs-lookup"><span data-stu-id="fc8cb-123">When you are finished drawing content into the <xref:System.Windows.Media.DrawingContext>, call the <xref:System.Windows.Media.DrawingContext.Close%2A> method to close the <xref:System.Windows.Media.DrawingContext> and persist the content.</span></span>  
  
 <span data-ttu-id="fc8cb-124">다음 예제에서는 <xref:System.Windows.Media.DrawingVisual> 개체가 만들어지고에 사각형이 그려집니다 해당 <xref:System.Windows.Media.DrawingContext>합니다.</span><span class="sxs-lookup"><span data-stu-id="fc8cb-124">In the following example, a <xref:System.Windows.Media.DrawingVisual> object is created, and a rectangle is drawn into its <xref:System.Windows.Media.DrawingContext>.</span></span>  
  
 [!code-csharp[DrawingVisualSample#101](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingVisualSample/CSharp/Window1.xaml.cs#101)]
 [!code-vb[DrawingVisualSample#101](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DrawingVisualSample/visualbasic/window1.xaml.vb#101)]  
  
<a name="creating_overrides"></a>   
## <a name="creating-overrides-for-frameworkelement-members"></a><span data-ttu-id="fc8cb-125">FrameworkElement 멤버에 대한 재정의 만들기</span><span class="sxs-lookup"><span data-stu-id="fc8cb-125">Creating Overrides for FrameworkElement Members</span></span>  
 <span data-ttu-id="fc8cb-126">호스트 컨테이너 개체는 시각적 개체의 컬렉션을 관리합니다.</span><span class="sxs-lookup"><span data-stu-id="fc8cb-126">The host container object is responsible for managing its collection of visual objects.</span></span> <span data-ttu-id="fc8cb-127">호스트 컨테이너는 파생에 대 한 멤버 재정의 구현 하는이 위해서는 <xref:System.Windows.FrameworkElement> 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="fc8cb-127">This requires that the host container implement member overrides for the derived <xref:System.Windows.FrameworkElement> class.</span></span>  
  
 <span data-ttu-id="fc8cb-128">다음 목록에서는 재정의해야 하는 두 멤버에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="fc8cb-128">The following list describes the two members you must override:</span></span>  
  
-   <xref:System.Windows.FrameworkElement.GetVisualChild%2A><span data-ttu-id="fc8cb-129">: 자식 요소 컬렉션에서 지정된 된 인덱스에 있는 자식을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="fc8cb-129">: Returns a child at the specified index from the collection of child elements.</span></span>  
  
-   <xref:System.Windows.FrameworkElement.VisualChildrenCount%2A><span data-ttu-id="fc8cb-130">: 이 요소 내 시각적 자식 요소의 수를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="fc8cb-130">: Gets the number of visual child elements within this element.</span></span>  
  
 <span data-ttu-id="fc8cb-131">다음 예제에서는 두 가지에 대 한 재정의가 <xref:System.Windows.FrameworkElement> 멤버 구현 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fc8cb-131">In the following example, overrides for the two <xref:System.Windows.FrameworkElement> members are implemented.</span></span>  
  
 [!code-csharp[DrawingVisualSample#102](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingVisualSample/CSharp/Window1.xaml.cs#102)]
 [!code-vb[DrawingVisualSample#102](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DrawingVisualSample/visualbasic/window1.xaml.vb#102)]  
  
<a name="providing_hit_testing_support"></a>   
## <a name="providing-hit-testing-support"></a><span data-ttu-id="fc8cb-132">적중 테스트 지원 제공</span><span class="sxs-lookup"><span data-stu-id="fc8cb-132">Providing Hit Testing Support</span></span>  
 <span data-ttu-id="fc8cb-133">호스트 컨테이너 개체에서 표시 가능한 속성을 표시 하지 않더라도 이벤트 처리를 제공할 수 있습니다-단, 해당 <xref:System.Windows.UIElement.Visibility%2A> 속성으로 설정 되어 있어야 <xref:System.Windows.Visibility.Visible>합니다.</span><span class="sxs-lookup"><span data-stu-id="fc8cb-133">The host container object can provide event handling even if it does not display any visible properties—however, its <xref:System.Windows.UIElement.Visibility%2A> property must be set to <xref:System.Windows.Visibility.Visible>.</span></span> <span data-ttu-id="fc8cb-134">이 경우 왼쪽 마우스 단추 놓기와 같은 마우스 이벤트를 트래핑할 수 있는 호스트 컨테이너에 대한 이벤트 처리 루틴을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fc8cb-134">This allows you to create an event handling routine for the host container that can trap mouse events, such as the release of the left mouse button.</span></span> <span data-ttu-id="fc8cb-135">이벤트 처리 루틴은 적중 테스트를 호출 하 여 구현할 수는 <xref:System.Windows.Media.VisualTreeHelper.HitTest%2A> 메서드.</span><span class="sxs-lookup"><span data-stu-id="fc8cb-135">The event handling routine can then implement hit testing by invoking the <xref:System.Windows.Media.VisualTreeHelper.HitTest%2A> method.</span></span> <span data-ttu-id="fc8cb-136">메서드의 <xref:System.Windows.Media.HitTestResultCallback> 매개 변수는 적중 횟수 테스트의 결과 동작을 결정 하는 데 사용할 수 있는 사용자 정의 프로시저를 참조 합니다.</span><span class="sxs-lookup"><span data-stu-id="fc8cb-136">The method's <xref:System.Windows.Media.HitTestResultCallback> parameter refers to a user-defined procedure that you can use to determine the resulting action of a hit test.</span></span>  
  
 <span data-ttu-id="fc8cb-137">다음 예제에서는 호스트 컨테이너 개체 및 해당 자식에 대해 적중 테스트 지원이 구현됩니다.</span><span class="sxs-lookup"><span data-stu-id="fc8cb-137">In the following example, hit testing support is implemented for the host container object and its children.</span></span>  
  
 [!code-csharp[DrawingVisualSample#103](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingVisualSample/CSharp/Window1.xaml.cs#103)]
 [!code-vb[DrawingVisualSample#103](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DrawingVisualSample/visualbasic/window1.xaml.vb#103)]  
  
## <a name="see-also"></a><span data-ttu-id="fc8cb-138">참고자료</span><span class="sxs-lookup"><span data-stu-id="fc8cb-138">See also</span></span>

- <xref:System.Windows.Media.DrawingVisual>
- <xref:System.Windows.Media.VisualTreeHelper.HitTest%2A>
- [<span data-ttu-id="fc8cb-139">WPF 그래픽 렌더링 개요</span><span class="sxs-lookup"><span data-stu-id="fc8cb-139">WPF Graphics Rendering Overview</span></span>](wpf-graphics-rendering-overview.md)
- [<span data-ttu-id="fc8cb-140">시각적 계층에서 적중 테스트</span><span class="sxs-lookup"><span data-stu-id="fc8cb-140">Hit Testing in the Visual Layer</span></span>](hit-testing-in-the-visual-layer.md)
