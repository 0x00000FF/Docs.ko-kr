---
title: "비트맵 효과 개요"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: bitmap effects [WPF]
ms.assetid: 23cb338e-4b59-4b52-b294-96431f9c9568
caps.latest.revision: "34"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 0f642c699a0ecf3e3cce328363f90110766002e0
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="bitmap-effects-overview"></a><span data-ttu-id="db526-102">비트맵 효과 개요</span><span class="sxs-lookup"><span data-stu-id="db526-102">Bitmap Effects Overview</span></span>
<span data-ttu-id="db526-103">비트맵 효과를 사용하여 디자이너와 개발자들은 렌더링된 [!INCLUDE[TLA#tla_wpf](../../../../includes/tlasharptla-wpf-md.md)] 콘텐츠에 시각 효과를 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="db526-103">Bitmap effects enable designers and developers to apply visual effects to rendered [!INCLUDE[TLA#tla_wpf](../../../../includes/tlasharptla-wpf-md.md)] content.</span></span> <span data-ttu-id="db526-104">예를 들어 비트맵 효과 사용 하면 쉽게 적용할 수는 <xref:System.Windows.Media.Effects.DropShadowBitmapEffect> 효과나 흐림 효과 이미지 또는 단추를 합니다.</span><span class="sxs-lookup"><span data-stu-id="db526-104">For example, bitmap effects allow you to easily apply a <xref:System.Windows.Media.Effects.DropShadowBitmapEffect> effect or a blur effect to an image or a button.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="db526-105">에 [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)] 이후 버전의 <xref:System.Windows.Media.Effects.BitmapEffect> 클래스는 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="db526-105">In the [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)] or later, the <xref:System.Windows.Media.Effects.BitmapEffect> class is obsolete.</span></span> <span data-ttu-id="db526-106">사용 하려는 경우는 <xref:System.Windows.Media.Effects.BitmapEffect> 클래스, 사용 되지 않음 예외가 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="db526-106">If you try to use the <xref:System.Windows.Media.Effects.BitmapEffect> class, you will get an obsolete exception.</span></span> <span data-ttu-id="db526-107">클래스 대신에는 <xref:System.Windows.Media.Effects.BitmapEffect> 클래스는는 <xref:System.Windows.Media.Effects.Effect> 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="db526-107">The non-obsolete alternative to the <xref:System.Windows.Media.Effects.BitmapEffect> class is the <xref:System.Windows.Media.Effects.Effect> class.</span></span> <span data-ttu-id="db526-108">대부분의 경우에는 <xref:System.Windows.Media.Effects.Effect> 클래스는 훨씬 더 빨라집니다.</span><span class="sxs-lookup"><span data-stu-id="db526-108">In most situations, the <xref:System.Windows.Media.Effects.Effect> class is significantly faster.</span></span>  
  
  
  
<a name="wpf_effects"></a>   
## <a name="wpf-bitmap-effects"></a><span data-ttu-id="db526-109">WPF 비트맵 효과</span><span class="sxs-lookup"><span data-stu-id="db526-109">WPF Bitmap Effects</span></span>  
 <span data-ttu-id="db526-110">비트맵 효과 (<xref:System.Windows.Media.Effects.BitmapEffect> 개체)는 처리 작업을 간단한 픽셀입니다.</span><span class="sxs-lookup"><span data-stu-id="db526-110">Bitmap effects (<xref:System.Windows.Media.Effects.BitmapEffect> object) are simple pixel processing operations.</span></span> <span data-ttu-id="db526-111">비트맵 효과 <xref:System.Windows.Media.Imaging.BitmapSource> 를 입력 및 생성 새 <xref:System.Windows.Media.Imaging.BitmapSource> 흐림 또는 그림자 같은 효과 적용 한 후 합니다.</span><span class="sxs-lookup"><span data-stu-id="db526-111">A bitmap effect takes a <xref:System.Windows.Media.Imaging.BitmapSource> as an input and produces a new <xref:System.Windows.Media.Imaging.BitmapSource> after applying the effect, such as a blur or drop shadow.</span></span> <span data-ttu-id="db526-112">각 비트맵 효과 같은 필터링 속성을 제어할 수 있는 속성을 공개 <xref:System.Windows.Media.Effects.BlurBitmapEffect.Radius%2A> 의 <xref:System.Windows.Media.Effects.BlurBitmapEffect>합니다.</span><span class="sxs-lookup"><span data-stu-id="db526-112">Each bitmap effect exposes properties that can control the filtering properties, such as <xref:System.Windows.Media.Effects.BlurBitmapEffect.Radius%2A> of <xref:System.Windows.Media.Effects.BlurBitmapEffect>.</span></span>  
  
 <span data-ttu-id="db526-113">특별 한 경우로에서 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], 효과에 설정 될 수 속성으로 라이브 <xref:System.Windows.Media.Visual> 와 같은 개체는 <xref:System.Windows.Controls.Button> 또는 <xref:System.Windows.Controls.TextBox>합니다.</span><span class="sxs-lookup"><span data-stu-id="db526-113">As a special case, in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], effects can be set as properties on live <xref:System.Windows.Media.Visual> objects, such as a <xref:System.Windows.Controls.Button> or <xref:System.Windows.Controls.TextBox>.</span></span> <span data-ttu-id="db526-114">런타임에 픽셀 처리가 적용되고 렌더링됩니다.</span><span class="sxs-lookup"><span data-stu-id="db526-114">The pixel processing is applied and rendered at run-time.</span></span> <span data-ttu-id="db526-115">렌더링 시이 경우에 <xref:System.Windows.Media.Visual> 자동으로 변환 되며 해당 <xref:System.Windows.Media.Imaging.BitmapSource> 해당 하는 및에 대 한 입력으로 제공 됩니다는 <xref:System.Windows.Media.Effects.BitmapEffect>합니다.</span><span class="sxs-lookup"><span data-stu-id="db526-115">In this case, at the time of rendering, a <xref:System.Windows.Media.Visual> is automatically converted to its <xref:System.Windows.Media.Imaging.BitmapSource> equivalent and is fed as input to the <xref:System.Windows.Media.Effects.BitmapEffect>.</span></span> <span data-ttu-id="db526-116">출력 대체는 <xref:System.Windows.Media.Visual> 개체의 기본 렌더링 동작 합니다.</span><span class="sxs-lookup"><span data-stu-id="db526-116">The output replaces the <xref:System.Windows.Media.Visual> object's default rendering behavior.</span></span> <span data-ttu-id="db526-117">이 인해 <xref:System.Windows.Media.Effects.BitmapEffect> 개체에에서 렌더링할 소프트웨어만 즉, 하드웨어 가속 없이 시각적 개체에 효과 적용할 경우 시각적 개체를 강제 합니다.</span><span class="sxs-lookup"><span data-stu-id="db526-117">This is why <xref:System.Windows.Media.Effects.BitmapEffect> objects force visuals to render in software only i.e. no hardware acceleration on visuals when effects are applied.</span></span>  
  
-   <span data-ttu-id="db526-118"><xref:System.Windows.Media.Effects.BlurBitmapEffect>포커스를 벗어난 표시 되는 개체를 시뮬레이션 합니다.</span><span class="sxs-lookup"><span data-stu-id="db526-118"><xref:System.Windows.Media.Effects.BlurBitmapEffect> simulates an object that appears out-of-focus.</span></span>  
  
-   <span data-ttu-id="db526-119"><xref:System.Windows.Media.Effects.OuterGlowBitmapEffect>개체의 경계 주위에 색상의 무리 짐을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="db526-119"><xref:System.Windows.Media.Effects.OuterGlowBitmapEffect> creates a halo of color around the perimeter of an object.</span></span>  
  
-   <span data-ttu-id="db526-120"><xref:System.Windows.Media.Effects.DropShadowBitmapEffect>개체 뒤에 그림자를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="db526-120"><xref:System.Windows.Media.Effects.DropShadowBitmapEffect> creates a shadow behind an object.</span></span>  
  
-   <span data-ttu-id="db526-121"><xref:System.Windows.Media.Effects.BevelBitmapEffect>지정된 된 곡선에 따라 이미지의 표면을 올리는 3d 가장자리를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="db526-121"><xref:System.Windows.Media.Effects.BevelBitmapEffect> creates a bevel which raises the surface of an image according to a specified curve.</span></span>  
  
-   <span data-ttu-id="db526-122"><xref:System.Windows.Media.Effects.EmbossBitmapEffect>범프 매핑을 만듭니다는 <xref:System.Windows.Media.Visual> 인공 광원에서 깊이 및 질감 효과 주기 위해 합니다.</span><span class="sxs-lookup"><span data-stu-id="db526-122"><xref:System.Windows.Media.Effects.EmbossBitmapEffect> creates a bump mapping of a <xref:System.Windows.Media.Visual> to give the impression of depth and texture from an artificial light source.</span></span>  
  
> [!NOTE]
>  [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]<span data-ttu-id="db526-123"> 비트맵 효과는 소프트웨어 모드에서 렌더링됩니다.</span><span class="sxs-lookup"><span data-stu-id="db526-123"> bitmap effects are rendered in software mode.</span></span> <span data-ttu-id="db526-124">효과를 적용하는 모든 개체도 소프트웨어에서 렌더링됩니다.</span><span class="sxs-lookup"><span data-stu-id="db526-124">Any object that applies an effect will also be rendered in software.</span></span> <span data-ttu-id="db526-125">큰 시각적 개체에 비트맵 효과를 사용하거나 비트맵 효과의 속성에 애니메이션 효과를 줄 때 성능이 가장 크게 저하됩니다.</span><span class="sxs-lookup"><span data-stu-id="db526-125">Performance is degraded the most when using Bitmap effects on large visuals or animating properties of a Bitmap effect.</span></span> <span data-ttu-id="db526-126">따라서 여러분도 이러한 방식으로 비트맵 효과를 사용하지 않아야 하는 것은 물론, 다른 사용자들도 바람직한 경험을 얻을 수 있도록 철저히 테스트하고 주의해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="db526-126">This is not to say that you should not use Bitmap effects in this way at all, but you should use caution and test thoroughly to ensure that your users are getting the experience you expect.</span></span>  
  
> [!NOTE]
>  [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]<span data-ttu-id="db526-127"> 비트맵 효과는 부분 신뢰 실행을 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="db526-127"> bitmap effects do not support partial trust execution.</span></span> <span data-ttu-id="db526-128">비트맵 효과를 사용하려면 응용 프로그램에 완전 신뢰 권한이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="db526-128">An application must have full trust permissions to use bitmap effects.</span></span>  
  
<a name="applyeffects"></a>   
## <a name="how-to-apply-an-effect"></a><span data-ttu-id="db526-129">효과를 적용하는 방법</span><span class="sxs-lookup"><span data-stu-id="db526-129">How to Apply an Effect</span></span>  
 <span data-ttu-id="db526-130"><xref:System.Windows.Media.Effects.BitmapEffect>에 속성 <xref:System.Windows.Media.Visual>합니다.</span><span class="sxs-lookup"><span data-stu-id="db526-130"><xref:System.Windows.Media.Effects.BitmapEffect> is a property on <xref:System.Windows.Media.Visual>.</span></span> <span data-ttu-id="db526-131">따라서 효과를 시각적 개체와 같은 적용 한 <xref:System.Windows.Controls.Button>, <xref:System.Windows.Controls.Image>, <xref:System.Windows.Media.DrawingVisual>, 또는 <xref:System.Windows.UIElement>, 속성을 설정 하기만 됩니다.</span><span class="sxs-lookup"><span data-stu-id="db526-131">Therefore applying effects to Visuals, such as a <xref:System.Windows.Controls.Button>, <xref:System.Windows.Controls.Image>, <xref:System.Windows.Media.DrawingVisual>, or <xref:System.Windows.UIElement>, is as easy as setting a property.</span></span> <span data-ttu-id="db526-132"><xref:System.Windows.UIElement.BitmapEffect%2A>단일으로 설정할 수 있습니다 <xref:System.Windows.Media.Effects.BitmapEffect> 개체 또는 여러 효과 사용 하 여 연결 될 수 있습니다는 <xref:System.Windows.Media.Effects.BitmapEffectGroup> 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="db526-132"><xref:System.Windows.UIElement.BitmapEffect%2A> can be set to a single <xref:System.Windows.Media.Effects.BitmapEffect> object or multiple effects can be chained by using the <xref:System.Windows.Media.Effects.BitmapEffectGroup> object.</span></span>  
  
 <span data-ttu-id="db526-133">다음 예제에서는 적용 하는 <xref:System.Windows.Media.Effects.BitmapEffect> 에서 [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]합니다.</span><span class="sxs-lookup"><span data-stu-id="db526-133">The following example demonstrates how to apply a <xref:System.Windows.Media.Effects.BitmapEffect> in [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)].</span></span>  
  
 [!code-xaml[EffectsGallery_snip#BlurSimpleExampleInline](../../../../samples/snippets/csharp/VS_Snippets_Wpf/EffectsGallery_snip/CSharp/blursimpleexample.xaml#blursimpleexampleinline)]  
  
 <span data-ttu-id="db526-134">다음 예제에서는 적용 하는 <xref:System.Windows.Media.Effects.BitmapEffect> 코드에서.</span><span class="sxs-lookup"><span data-stu-id="db526-134">The following example demonstrates how to apply a <xref:System.Windows.Media.Effects.BitmapEffect> in code.</span></span>  
  
 [!code-csharp[EffectsGallery_snip#CodeBehindBlurCodeBehindExampleInline](../../../../samples/snippets/csharp/VS_Snippets_Wpf/EffectsGallery_snip/CSharp/blurcodebehindexample.xaml.cs#codebehindblurcodebehindexampleinline)]  
  
> [!NOTE]
>  <span data-ttu-id="db526-135">경우는 <xref:System.Windows.Media.Effects.BitmapEffect> 같은 레이아웃 컨테이너에 적용할 <xref:System.Windows.Controls.DockPanel> 또는 <xref:System.Windows.Controls.Canvas>, 요소 또는 시각적 개체를 모든 자식 요소를 포함 하 여의 시각적 트리에 효과가 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="db526-135">When a <xref:System.Windows.Media.Effects.BitmapEffect> is applied to a layout container, such as <xref:System.Windows.Controls.DockPanel> or <xref:System.Windows.Controls.Canvas>, the effect is applied to the visual tree of the element or visual, including all of its child elements.</span></span>  
  
<a name="customeffects"></a>   
## <a name="creating-custom-effects"></a><span data-ttu-id="db526-136">사용자 지정 효과 만들기</span><span class="sxs-lookup"><span data-stu-id="db526-136">Creating Custom Effects</span></span>  
 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]<span data-ttu-id="db526-137">에서는 또한 관리되는 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] 응용 프로그램에서 사용할 수 있는 사용자 지정 효과를 만들기 위한 관리되지 않는 인터페이스를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="db526-137"> also provides unmanaged interfaces to create custom effects that can be used in managed [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] applications.</span></span> <span data-ttu-id="db526-138">사용자 지정 비트맵 효과를 만들기 위한 추가 참조 자료에 대해서는 [관리되지 않는 WPF 비트맵 효과](https://msdn.microsoft.com/library/ms735092.aspx) 설명서를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="db526-138">For additional reference material for creating custom bitmap effects, see the [Unmanaged WPF Bitmap Effect](https://msdn.microsoft.com/library/ms735092.aspx) documentation.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="db526-139">참고 항목</span><span class="sxs-lookup"><span data-stu-id="db526-139">See Also</span></span>  
 <xref:System.Windows.Media.Effects.BitmapEffectGroup>  
 <xref:System.Windows.Media.Effects.BitmapEffectInput>  
 <xref:System.Windows.Media.Effects.BitmapEffectCollection>  
 [<span data-ttu-id="db526-140">관리 되지 않는 WPF 비트맵 효과</span><span class="sxs-lookup"><span data-stu-id="db526-140">Unmanaged WPF Bitmap Effect</span></span>](https://msdn.microsoft.com/library/ms735092.aspx)  
 [<span data-ttu-id="db526-141">이미징 개요</span><span class="sxs-lookup"><span data-stu-id="db526-141">Imaging Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/imaging-overview.md)  
 [<span data-ttu-id="db526-142">보안</span><span class="sxs-lookup"><span data-stu-id="db526-142">Security</span></span>](../../../../docs/framework/wpf/security-wpf.md)  
 [<span data-ttu-id="db526-143">WPF 그래픽 렌더링 개요</span><span class="sxs-lookup"><span data-stu-id="db526-143">WPF Graphics Rendering Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/wpf-graphics-rendering-overview.md)  
 [<span data-ttu-id="db526-144">2차원 그래픽 및 이미징</span><span class="sxs-lookup"><span data-stu-id="db526-144">2D Graphics and Imaging</span></span>](../../../../docs/framework/wpf/advanced/optimizing-performance-2d-graphics-and-imaging.md)
