---
title: Freezable 개체 개요
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Freezable objects [WPF], description
- unfreezing Freezable objects [WPF]
- classes [WPF], Freezable
ms.assetid: 89c71692-4f43-4057-b611-67c6a8a863a2
ms.openlocfilehash: b2ef3c3dbbfbcef08f58c47948f76cb2c238b48a
ms.sourcegitcommit: 4d8efe00f2e5ab42e598aff298d13b8c052d9593
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/16/2019
ms.locfileid: "68238522"
---
# <a name="freezable-objects-overview"></a><span data-ttu-id="d70ab-102">Freezable 개체 개요</span><span class="sxs-lookup"><span data-stu-id="d70ab-102">Freezable Objects Overview</span></span>
<span data-ttu-id="d70ab-103">이 항목에서는 효과적으로 사용 하 고 만드는 방법을 설명 <xref:System.Windows.Freezable> 응용 프로그램 성능을 개선 하는 데 도움이 되는 특별 한 기능을 제공 하는 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="d70ab-103">This topic describes how to effectively use and create <xref:System.Windows.Freezable> objects, which provide special features that can help improve application performance.</span></span> <span data-ttu-id="d70ab-104">Freezable 개체의 예로 브러시, 펜, 변환, 기 하 도형 및 애니메이션을 들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d70ab-104">Examples of freezable objects include brushes, pens, transformations, geometries, and animations.</span></span>  
  
<a name="whatisafreezable"></a>   
## <a name="what-is-a-freezable"></a><span data-ttu-id="d70ab-105">Freezable 란?</span><span class="sxs-lookup"><span data-stu-id="d70ab-105">What Is a Freezable?</span></span>  
 <span data-ttu-id="d70ab-106"><xref:System.Windows.Freezable> 는 특별 한 유형의 두 가지 상태에 있는 개체: 않음과 고정 합니다.</span><span class="sxs-lookup"><span data-stu-id="d70ab-106">A <xref:System.Windows.Freezable> is a special type of object that has two states: unfrozen and frozen.</span></span> <span data-ttu-id="d70ab-107">고정 되지 않은 한 <xref:System.Windows.Freezable> 다른 모든 개체 처럼 동작 하 게 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d70ab-107">When unfrozen, a <xref:System.Windows.Freezable> appears to behave like any other object.</span></span> <span data-ttu-id="d70ab-108">고정 하는 경우는 <xref:System.Windows.Freezable> 더 이상 수정할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d70ab-108">When frozen, a <xref:System.Windows.Freezable> can no longer be modified.</span></span>  
  
 <span data-ttu-id="d70ab-109">A <xref:System.Windows.Freezable> 제공을 <xref:System.Windows.Freezable.Changed> 이벤트 개체에 대 한 수정은의 관찰자에 게 알립니다.</span><span class="sxs-lookup"><span data-stu-id="d70ab-109">A <xref:System.Windows.Freezable> provides a <xref:System.Windows.Freezable.Changed> event to notify observers of any modifications to the object.</span></span> <span data-ttu-id="d70ab-110">고정 된 <xref:System.Windows.Freezable> 더 이상 변경 알림을에 리소스를 소비 해야 하므로 성능을 향상 시킬 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d70ab-110">Freezing a <xref:System.Windows.Freezable> can improve its performance, because it no longer needs to spend resources on change notifications.</span></span> <span data-ttu-id="d70ab-111">고정 된 <xref:System.Windows.Freezable> 스레드를 고정 하는 동안 전체에서 공유할 수도 <xref:System.Windows.Freezable> 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d70ab-111">A frozen <xref:System.Windows.Freezable> can also be shared across threads, while an unfrozen <xref:System.Windows.Freezable> cannot.</span></span>  
  
 <span data-ttu-id="d70ab-112">하지만 합니다 <xref:System.Windows.Freezable> 클래스는 가장 다양 한 용도로 <xref:System.Windows.Freezable> 개체 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] 그래픽 하위 시스템에 관련 된 합니다.</span><span class="sxs-lookup"><span data-stu-id="d70ab-112">Although the <xref:System.Windows.Freezable> class has many applications, most <xref:System.Windows.Freezable> objects in [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] are related to the graphics sub-system.</span></span>  
  
 <span data-ttu-id="d70ab-113"><xref:System.Windows.Freezable> 클래스 쉽게 특정 그래픽 시스템 개체를 사용 하 고 응용 프로그램의 성능을 향상 시킬 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d70ab-113">The <xref:System.Windows.Freezable> class makes it easier to use certain graphics system objects and can help improve application performance.</span></span> <span data-ttu-id="d70ab-114">상속 되는 형식의 예입니다 <xref:System.Windows.Freezable> 포함 된 <xref:System.Windows.Media.Brush>, <xref:System.Windows.Media.Transform>, 및 <xref:System.Windows.Media.Geometry> 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="d70ab-114">Examples of types that inherit from <xref:System.Windows.Freezable> include the <xref:System.Windows.Media.Brush>, <xref:System.Windows.Media.Transform>, and <xref:System.Windows.Media.Geometry> classes.</span></span> <span data-ttu-id="d70ab-115">관리 되지 않는 리소스를 포함 하기 때문에 시스템 수정에 대 한 이러한 개체를 모니터링 하 고 원래 개체에 변경 되 면 해당 관리 되지 않는 리소스를 업데이트 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d70ab-115">Because they contain unmanaged resources, the system must monitor these objects for modifications, and then update their corresponding unmanaged resources when there is a change to the original object.</span></span> <span data-ttu-id="d70ab-116">그래픽 시스템 개체를 실제로 수정 하지 않습니다, 경우에 시스템을 계속 사용 해야 개체를 모니터링 하는 리소스의 일부 변경 하는 경우.</span><span class="sxs-lookup"><span data-stu-id="d70ab-116">Even if you don't actually modify a graphics system object, the system must still spend some of its resources monitoring the object, in case you do change it.</span></span>  
  
 <span data-ttu-id="d70ab-117">예를 들어 만든를 <xref:System.Windows.Media.SolidColorBrush> 브러시를 단추의 배경을 그리는 데 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="d70ab-117">For example, suppose you create a <xref:System.Windows.Media.SolidColorBrush> brush and use it to paint the background of a button.</span></span>  
  
 [!code-csharp[freezablesample_procedural#FrozenExamplePart1](~/samples/snippets/csharp/VS_Snippets_Wpf/freezablesample_procedural/CSharp/freezablesample.cs#frozenexamplepart1)]
 [!code-vb[freezablesample_procedural#FrozenExamplePart1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/freezablesample_procedural/visualbasic/freezablesample.vb#frozenexamplepart1)]  
  
 <span data-ttu-id="d70ab-118">단추를 렌더링할 때는 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 그래픽 하위 시스템 그룹 단추의 모양을 형성 하는 픽셀을 그릴 제공한 정보를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="d70ab-118">When the button is rendered, the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] graphics sub-system uses the information you provided to paint a group of pixels to create the appearance of a button.</span></span> <span data-ttu-id="d70ab-119">단색 브러시를 사용 하는 단추를 그려야 하는 방법을 설명 하기 위해 있지만 단색 브러시 그리기를 실제로 수행 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d70ab-119">Although you used a solid color brush to describe how the button should be painted, your solid color brush doesn't actually do the painting.</span></span> <span data-ttu-id="d70ab-120">단추와 브러시를 신속 하 고 하위 수준 개체를 생성 하는 그래픽 시스템 이며 실제로 화면에 표시 하는 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="d70ab-120">The graphics system generates fast, low-level objects for the button and the brush, and it is those objects that actually appear on the screen.</span></span>  
  
 <span data-ttu-id="d70ab-121">브러시를 수정 하는 경우 이러한 하위 수준 개체 다시 생성 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d70ab-121">If you were to modify the brush, those low-level objects would have to be regenerated.</span></span> <span data-ttu-id="d70ab-122">Freezable 클래스는 해당 해당 생성 된 하위 수준 개체를 찾으려고 하 고 변경 되 면 업데이트 브러시를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="d70ab-122">The freezable class is what gives a brush the ability to find its corresponding generated, low-level objects and to update them when it changes.</span></span> <span data-ttu-id="d70ab-123">이 기능을 사용 하면 브러시 라고 하지 "고정" 합니다.</span><span class="sxs-lookup"><span data-stu-id="d70ab-123">When this ability is enabled, the brush is said to be "unfrozen."</span></span>  
  
 <span data-ttu-id="d70ab-124">Freezable의 <xref:System.Windows.Freezable.Freeze%2A> 메서드를 사용 하면 이러한 자동 업데이트 기능을 사용 하지 않도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="d70ab-124">A freezable's <xref:System.Windows.Freezable.Freeze%2A> method enables you to disable this self-updating ability.</span></span> <span data-ttu-id="d70ab-125">"고정" 또는 수정할 수 없게 되는 브러시를 만들려면이 메서드를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d70ab-125">You can use this method to make the brush become "frozen," or unmodifiable.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d70ab-126">일부 Freezable 개체를 고정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d70ab-126">Not every Freezable object can be frozen.</span></span> <span data-ttu-id="d70ab-127">Throw 되지 않도록 하는 <xref:System.InvalidOperationException>, Freezable 개체의 값을 확인 <xref:System.Windows.Freezable.CanFreeze%2A> 고정 하기 전에 고정 가능 여부를 결정 하는 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="d70ab-127">To avoid throwing an <xref:System.InvalidOperationException>, check the value of the Freezable object's <xref:System.Windows.Freezable.CanFreeze%2A> property to determine whether it can be frozen before attempting to freeze it.</span></span>  
  
 [!code-csharp[freezablesample_procedural#FrozenExamplePart2](~/samples/snippets/csharp/VS_Snippets_Wpf/freezablesample_procedural/CSharp/freezablesample.cs#frozenexamplepart2)]
 [!code-vb[freezablesample_procedural#FrozenExamplePart2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/freezablesample_procedural/visualbasic/freezablesample.vb#frozenexamplepart2)]  
  
 <span data-ttu-id="d70ab-128">Freezable을 수정 해야 하는 더 이상, 고정 성능상의 이점을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="d70ab-128">When you no longer need to modify a freezable, freezing it provides performance benefits.</span></span> <span data-ttu-id="d70ab-129">이 예제에서 브러시를 고정 하는 경우 그래픽 시스템 더 이상 변경 내용을 모니터링 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d70ab-129">If you were to freeze the brush in this example, the graphics system would no longer need to monitor it for changes.</span></span> <span data-ttu-id="d70ab-130">그래픽 시스템 브러시를 변경 하지 않습니다 인식 하기 때문에 다른 최적화를 만들 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d70ab-130">The graphics system can also make other optimizations, because it knows the brush won't change.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d70ab-131">편의 위해 명시적으로 고정 되지 않는 한 freezable 개체 고정 되지 않은 유지 합니다.</span><span class="sxs-lookup"><span data-stu-id="d70ab-131">For convenience, freezable objects remain unfrozen unless you explicitly freeze them.</span></span>  
  
<a name="frozenfreezables"></a>   
## <a name="using-freezables"></a><span data-ttu-id="d70ab-132">Freezable을 사용 하 여</span><span class="sxs-lookup"><span data-stu-id="d70ab-132">Using Freezables</span></span>  
 <span data-ttu-id="d70ab-133">고정 되지 않은 freezable 사용할 다른 형식의 개체를 사용 하 여 같은 합니다.</span><span class="sxs-lookup"><span data-stu-id="d70ab-133">Using an unfrozen freezable is like using any other type of object.</span></span> <span data-ttu-id="d70ab-134">다음 예에서 색을 <xref:System.Windows.Media.SolidColorBrush> 단추의 배경을 칠하는 데 사용 된 후 빨간색으로 노란색에서 변경 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d70ab-134">In the following example, the color of a <xref:System.Windows.Media.SolidColorBrush> is changed from yellow to red after it's used to paint the background of a button.</span></span> <span data-ttu-id="d70ab-135">그래픽 시스템은 자동으로 변경 하려면 단추 노랑에서 빨강으로 다음에 화면 새로 고칠 때 백그라운드에서 작동 합니다.</span><span class="sxs-lookup"><span data-stu-id="d70ab-135">The graphics system works behind the scenes to automatically change the button from yellow to red the next time the screen is refreshed.</span></span>  
  
 [!code-csharp[freezablesample_procedural#UnFrozenExampleShort](~/samples/snippets/csharp/VS_Snippets_Wpf/freezablesample_procedural/CSharp/freezablesample.cs#unfrozenexampleshort)]
 [!code-vb[freezablesample_procedural#UnFrozenExampleShort](~/samples/snippets/visualbasic/VS_Snippets_Wpf/freezablesample_procedural/visualbasic/freezablesample.vb#unfrozenexampleshort)]  
  
### <a name="freezing-a-freezable"></a><span data-ttu-id="d70ab-136">Freezable 고정</span><span class="sxs-lookup"><span data-stu-id="d70ab-136">Freezing a Freezable</span></span>  
 <span data-ttu-id="d70ab-137">확인 하는 <xref:System.Windows.Freezable> 호출, 해당 <xref:System.Windows.Freezable.Freeze%2A> 메서드.</span><span class="sxs-lookup"><span data-stu-id="d70ab-137">To make a <xref:System.Windows.Freezable> unmodifiable, you call its <xref:System.Windows.Freezable.Freeze%2A> method.</span></span> <span data-ttu-id="d70ab-138">Freezable 개체를 포함 하는 개체를 중지 하면 해당 개체도 고정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d70ab-138">When you freeze an object that contains freezable objects, those objects are frozen as well.</span></span> <span data-ttu-id="d70ab-139">예를 들어, 고정 하면를 <xref:System.Windows.Media.PathGeometry>, 그림 및 포함 된 세그먼트에 고정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d70ab-139">For example, if you freeze a <xref:System.Windows.Media.PathGeometry>, the figures and segments it contains would be frozen too.</span></span>  
  
 <span data-ttu-id="d70ab-140">Freezable **없습니다** 다음 중 하나라도 해당 하는 경우 고정 될:</span><span class="sxs-lookup"><span data-stu-id="d70ab-140">A Freezable **can't** be frozen if any of the following are true:</span></span>  
  
- <span data-ttu-id="d70ab-141">애니메이션 효과가 적용 또는 데이터 바인딩된 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="d70ab-141">It has animated or data bound properties.</span></span>  
  
- <span data-ttu-id="d70ab-142">동적 리소스에서 설정 하는 속성이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d70ab-142">It has properties set by a dynamic resource.</span></span> <span data-ttu-id="d70ab-143">(참조를 [XAML 리소스](xaml-resources.md) 동적 리소스에 대 한 자세한 내용은 합니다.)</span><span class="sxs-lookup"><span data-stu-id="d70ab-143">(See the [XAML Resources](xaml-resources.md) for more information about dynamic resources.)</span></span>  
  
- <span data-ttu-id="d70ab-144">포함 된 <xref:System.Windows.Freezable> 고정할 수 없는 하위 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="d70ab-144">It contains <xref:System.Windows.Freezable> sub-objects that can't be frozen.</span></span>  
  
 <span data-ttu-id="d70ab-145">이러한 조건이 false 이면 및 수정 하지 않으려는 경우는 <xref:System.Windows.Freezable>, 앞에서 설명한 성능 이점을 얻을 수 고를 고정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d70ab-145">If these conditions are false, and you don't intend to modify the <xref:System.Windows.Freezable>, then you should freeze it to gain the performance benefits described earlier.</span></span>  
  
 <span data-ttu-id="d70ab-146">Freezable의 호출 되 면 <xref:System.Windows.Freezable.Freeze%2A> 메서드를 더 이상 수정할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d70ab-146">Once you call a freezable's <xref:System.Windows.Freezable.Freeze%2A> method, it can no longer be modified.</span></span> <span data-ttu-id="d70ab-147">고정 된 수정 하려고 하면 개체는 <xref:System.InvalidOperationException> throw 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d70ab-147">Attempting to modify a frozen object causes an <xref:System.InvalidOperationException> to be thrown.</span></span> <span data-ttu-id="d70ab-148">다음 코드를 고정 한 후 브러시를 수정 하려고 하기 때문에 예외를 throw 합니다.</span><span class="sxs-lookup"><span data-stu-id="d70ab-148">The following code throws an exception, because we attempt to modify the brush after it's been frozen.</span></span>  
  
 [!code-csharp[freezablesample_procedural#ExceptionExample](~/samples/snippets/csharp/VS_Snippets_Wpf/freezablesample_procedural/CSharp/freezablesample.cs#exceptionexample)]
 [!code-vb[freezablesample_procedural#ExceptionExample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/freezablesample_procedural/visualbasic/freezablesample.vb#exceptionexample)]  
  
 <span data-ttu-id="d70ab-149">이 예외를 방지 하려면 사용할 수 있습니다는 <xref:System.Windows.Freezable.IsFrozen%2A> 결정 하는 방법 여부를 <xref:System.Windows.Freezable> 고정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d70ab-149">To avoid throwing this exception, you can use the <xref:System.Windows.Freezable.IsFrozen%2A> method to determine whether a <xref:System.Windows.Freezable> is frozen.</span></span>  
  
 [!code-csharp[freezablesample_procedural#CheckIsFrozenExample](~/samples/snippets/csharp/VS_Snippets_Wpf/freezablesample_procedural/CSharp/freezablesample.cs#checkisfrozenexample)]
 [!code-vb[freezablesample_procedural#CheckIsFrozenExample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/freezablesample_procedural/visualbasic/freezablesample.vb#checkisfrozenexample)]  
  
 <span data-ttu-id="d70ab-150">앞의 코드 예제에서 사용 하 여 고정 된 개체의 수정 가능한 복사본 했습니다는 <xref:System.Windows.Freezable.Clone%2A> 메서드.</span><span class="sxs-lookup"><span data-stu-id="d70ab-150">In the preceding code example, a modifiable copy was made of a frozen object using the <xref:System.Windows.Freezable.Clone%2A> method.</span></span> <span data-ttu-id="d70ab-151">다음 섹션에서는 복제를 자세히 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="d70ab-151">The next section discusses cloning in more detail.</span></span>  
  
 <span data-ttu-id="d70ab-152">**참고** 때문에 고정 된 freezable 애니메이션을 적용할 수, 애니메이션 시스템에서의 수정 가능한 복제본을 자동으로 만듭니다 고정 <xref:System.Windows.Freezable> 를 사용 하 여 애니메이션을 적용 하려고 할 때 개체는 <xref:System.Windows.Media.Animation.Storyboard>합니다.</span><span class="sxs-lookup"><span data-stu-id="d70ab-152">**Note** Because a frozen freezable cannot be animated, the animation system will automatically create modifiable clones of frozen <xref:System.Windows.Freezable> objects when you try to animate them with a <xref:System.Windows.Media.Animation.Storyboard>.</span></span> <span data-ttu-id="d70ab-153">성능 복제로 인 한 오버 헤드를 제거 하려면 애니메이션을 적용 하려는 경우 고정 되지 않은 개체를 그대로 둡니다.</span><span class="sxs-lookup"><span data-stu-id="d70ab-153">To eliminate the performance overhead caused by cloning, leave an object unfrozen if you intend to animate it.</span></span> <span data-ttu-id="d70ab-154">Storyboard로 애니메이션 효과 적용 하는 방법에 대 한 자세한 내용은 참조는 [스토리 보드 개요](../graphics-multimedia/storyboards-overview.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="d70ab-154">For more information about animating with storyboards, see the [Storyboards Overview](../graphics-multimedia/storyboards-overview.md).</span></span>  
  
### <a name="freezing-from-markup"></a><span data-ttu-id="d70ab-155">태그에서 고정</span><span class="sxs-lookup"><span data-stu-id="d70ab-155">Freezing from Markup</span></span>  
 <span data-ttu-id="d70ab-156">고정 하는 <xref:System.Windows.Freezable> 사용할 태그에 선언 된 개체는 `PresentationOptions:Freeze` 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="d70ab-156">To freeze a <xref:System.Windows.Freezable> object declared in markup, you use the `PresentationOptions:Freeze` attribute.</span></span> <span data-ttu-id="d70ab-157">다음 예제에서는 <xref:System.Windows.Media.SolidColorBrush> 페이지 리소스로 선언 되 고 고정 합니다.</span><span class="sxs-lookup"><span data-stu-id="d70ab-157">In the following example, a <xref:System.Windows.Media.SolidColorBrush> is declared as a page resource and frozen.</span></span> <span data-ttu-id="d70ab-158">그런 다음 단추의 배경색을 설정 하는 것이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d70ab-158">It is then used to set the background of a button.</span></span>  
  
 [!code-xaml[FreezableSample#FreezeFromMarkupWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/FreezableSample/CS/FreezeFromMarkupExample.xaml#freezefrommarkupwholepage)]  
  
 <span data-ttu-id="d70ab-159">사용 하는 `Freeze` 프레젠테이션 옵션 네임 스페이스에 매핑해야 특성: `http://schemas.microsoft.com/winfx/2006/xaml/presentation/options`합니다.</span><span class="sxs-lookup"><span data-stu-id="d70ab-159">To use the `Freeze` attribute, you must map to the presentation options namespace: `http://schemas.microsoft.com/winfx/2006/xaml/presentation/options`.</span></span> <span data-ttu-id="d70ab-160">`PresentationOptions` 이 네임 스페이스를 매핑하기 위한 권장 되는 접두사가 같습니다.</span><span class="sxs-lookup"><span data-stu-id="d70ab-160">`PresentationOptions` is the recommended prefix for mapping this namespace:</span></span>  
  
```  
xmlns:PresentationOptions="http://schemas.microsoft.com/winfx/2006/xaml/presentation/options"   
```  
  
 <span data-ttu-id="d70ab-161">일부 XAML 판독기에서이 특성을 인식 하므로 것을 사용 하는 합니다 [mc: Ignorable 특성](mc-ignorable-attribute.md) 표시는 `Presentation:Freeze` 특성을 무시할 수:</span><span class="sxs-lookup"><span data-stu-id="d70ab-161">Because not all XAML readers recognize this attribute, it's recommended that you use the [mc:Ignorable Attribute](mc-ignorable-attribute.md) to mark the `Presentation:Freeze` attribute as ignorable:</span></span>  
  
```  
xmlns:mc="http://schemas.openxmlformats.org/markup-compatibility/2006"  
mc:Ignorable="PresentationOptions"  
```  
  
 <span data-ttu-id="d70ab-162">자세한 내용은 참조는 [mc: Ignorable 특성](mc-ignorable-attribute.md) 페이지입니다.</span><span class="sxs-lookup"><span data-stu-id="d70ab-162">For more information, see the [mc:Ignorable Attribute](mc-ignorable-attribute.md) page.</span></span>  
  
### <a name="unfreezing-a-freezable"></a><span data-ttu-id="d70ab-163">"고정 해제"를 Freezable</span><span class="sxs-lookup"><span data-stu-id="d70ab-163">"Unfreezing" a Freezable</span></span>  
 <span data-ttu-id="d70ab-164">하지만 고정 하면를 <xref:System.Windows.Freezable> 되지 수정 또는 고정; 가능 사용 하 여 고정된 클론을 만들 수 있습니다 합니다 <xref:System.Windows.Freezable.Clone%2A> 또는 <xref:System.Windows.Freezable.CloneCurrentValue%2A> 메서드.</span><span class="sxs-lookup"><span data-stu-id="d70ab-164">Once frozen, a <xref:System.Windows.Freezable> can never be modified or unfrozen; however, you can create an unfrozen clone using the <xref:System.Windows.Freezable.Clone%2A> or <xref:System.Windows.Freezable.CloneCurrentValue%2A> method.</span></span>  
  
 <span data-ttu-id="d70ab-165">다음 예제에서는 단추의 배경 브러시를 사용 하 여 설정 되 고 고정 되는 브러시입니다.</span><span class="sxs-lookup"><span data-stu-id="d70ab-165">In the following example, the button's background is set with a brush and that brush is then frozen.</span></span> <span data-ttu-id="d70ab-166">고정 되지 않은 복사본을 사용 하 여 브러시 만들어집니다는 <xref:System.Windows.Freezable.Clone%2A> 메서드.</span><span class="sxs-lookup"><span data-stu-id="d70ab-166">An unfrozen copy is made of the brush using the <xref:System.Windows.Freezable.Clone%2A> method.</span></span> <span data-ttu-id="d70ab-167">복제를 수정 하 고 빨간색에서 노란색 단추의 배경을 변경 하는 데 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="d70ab-167">The clone is modified and used to change the button's background from yellow to red.</span></span>  
  
 [!code-csharp[freezablesample_procedural#CloneExample](~/samples/snippets/csharp/VS_Snippets_Wpf/freezablesample_procedural/CSharp/freezablesample.cs#cloneexample)]
 [!code-vb[freezablesample_procedural#CloneExample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/freezablesample_procedural/visualbasic/freezablesample.vb#cloneexample)]  
  
> [!NOTE]
>  <span data-ttu-id="d70ab-168">복제 방법을 사용 하 여 애니메이션 새 복사 되지 않습니다 <xref:System.Windows.Freezable>합니다.</span><span class="sxs-lookup"><span data-stu-id="d70ab-168">Regardless of which clone method you use, animations are never copied to the new <xref:System.Windows.Freezable>.</span></span>  
  
 <span data-ttu-id="d70ab-169">합니다 <xref:System.Windows.Freezable.Clone%2A> 고 <xref:System.Windows.Freezable.CloneCurrentValue%2A> 메서드는 freezable의 전체 복사본을 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="d70ab-169">The <xref:System.Windows.Freezable.Clone%2A> and <xref:System.Windows.Freezable.CloneCurrentValue%2A> methods produce deep copies of the freezable.</span></span> <span data-ttu-id="d70ab-170">Freezable은 freezable 개체 고정 다른에 있으면 또한 복제 되며 수정할 수 있게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d70ab-170">If the freezable contains other frozen freezable objects, they are also cloned and made modifiable.</span></span> <span data-ttu-id="d70ab-171">예를 들어, 고정 된 복제 <xref:System.Windows.Media.PathGeometry> 수정할 수 있도록, 하려면 그림 및 포함 된 세그먼트에도 복사 되어 수정할 수 있게 합니다.</span><span class="sxs-lookup"><span data-stu-id="d70ab-171">For example, if you clone a frozen <xref:System.Windows.Media.PathGeometry> to make it modifiable, the figures and segments it contains are also copied and made modifiable.</span></span>  
  
<a name="createyourownfreezableclass"></a>   
## <a name="creating-your-own-freezable-class"></a><span data-ttu-id="d70ab-172">사용자 고유의 Freezable 클래스 만들기</span><span class="sxs-lookup"><span data-stu-id="d70ab-172">Creating Your Own Freezable Class</span></span>  
 <span data-ttu-id="d70ab-173">파생 된 클래스 <xref:System.Windows.Freezable> 다음과 같은 기능이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d70ab-173">A class that derives from <xref:System.Windows.Freezable> gains the following features.</span></span>  
  
- <span data-ttu-id="d70ab-174">특수 상태: 읽기 전용 (고정) 및 쓰기 가능 상태입니다.</span><span class="sxs-lookup"><span data-stu-id="d70ab-174">Special states: a read-only (frozen) and a writable state.</span></span>  
  
- <span data-ttu-id="d70ab-175">스레드 보안: 고정 된 <xref:System.Windows.Freezable> 스레드 간에 공유할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d70ab-175">Thread safety: a frozen <xref:System.Windows.Freezable> can be shared across threads.</span></span>  
  
- <span data-ttu-id="d70ab-176">자세한 변경 알림: 달리 <xref:System.Windows.DependencyObject>s, Freezable 개체 변경 알림을 제공할 하위 속성 값을 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="d70ab-176">Detailed change notification: Unlike other <xref:System.Windows.DependencyObject>s, Freezable objects provide change notifications when sub-property values change.</span></span>  
  
- <span data-ttu-id="d70ab-177">쉬운 복제: Freezable 클래스가 이미 전체 복제를 만드는 여러 메서드를 구현 합니다.</span><span class="sxs-lookup"><span data-stu-id="d70ab-177">Easy cloning: the Freezable class has already implemented several methods that produce deep clones.</span></span>  
  
 <span data-ttu-id="d70ab-178">A <xref:System.Windows.Freezable> 유형의 <xref:System.Windows.DependencyObject>, 따라서 종속성 속성 시스템을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="d70ab-178">A <xref:System.Windows.Freezable> is a type of <xref:System.Windows.DependencyObject>, and therefore uses the dependency property system.</span></span> <span data-ttu-id="d70ab-179">클래스 속성을 종속성 속성 일 필요가 없지만 있으므로 작성 하는 코드의 양이 감소 하므로 종속성 속성을 사용 하는 <xref:System.Windows.Freezable> 클래스는 종속성 속성을 염두에서에 두고 설계 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="d70ab-179">Your class properties don't have to be dependency properties, but using dependency properties will reduce the amount of code you have to write, because the <xref:System.Windows.Freezable> class was designed with dependency properties in mind.</span></span> <span data-ttu-id="d70ab-180">종속성 속성 시스템에 대 한 자세한 내용은 참조는 [종속성 속성 개요](dependency-properties-overview.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="d70ab-180">For more information about the dependency property system, see the [Dependency Properties Overview](dependency-properties-overview.md).</span></span>  
  
 <span data-ttu-id="d70ab-181">모든 <xref:System.Windows.Freezable> 서브 클래스를 재정의 해야 합니다는 <xref:System.Windows.Freezable.CreateInstanceCore%2A> 메서드.</span><span class="sxs-lookup"><span data-stu-id="d70ab-181">Every <xref:System.Windows.Freezable> subclass must override the <xref:System.Windows.Freezable.CreateInstanceCore%2A> method.</span></span> <span data-ttu-id="d70ab-182">클래스에서는 종속성 속성의 모든 데이터에 대 한 경우 완료 합니다.</span><span class="sxs-lookup"><span data-stu-id="d70ab-182">If your class uses dependency properties for all its data, you're finished.</span></span>  
  
 <span data-ttu-id="d70ab-183">비 종속성 속성 데이터 멤버를 포함 하는 클래스, 경우 다음 방법 재정의 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d70ab-183">If your class contains non-dependency property data members, you must also override the following methods:</span></span>  
  
- <xref:System.Windows.Freezable.CloneCore%2A>  
  
- <xref:System.Windows.Freezable.CloneCurrentValueCore%2A>  
  
- <xref:System.Windows.Freezable.GetAsFrozenCore%2A>  
  
- <xref:System.Windows.Freezable.GetCurrentValueAsFrozenCore%2A>  
  
- <xref:System.Windows.Freezable.FreezeCore%2A>  
  
 <span data-ttu-id="d70ab-184">또한 다음 규칙에 액세스 하 고는 종속성 속성이 아닌 데이터 멤버에 쓰기를 준수 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d70ab-184">You must also observe the following rules for accessing and writing to data members that are not dependency properties:</span></span>  
  
- <span data-ttu-id="d70ab-185">비 종속성 속성 데이터 멤버를 읽는 모든 API의 시작 부분에서 호출 된 <xref:System.Windows.Freezable.ReadPreamble%2A> 메서드.</span><span class="sxs-lookup"><span data-stu-id="d70ab-185">At the beginning of any API that reads non-dependency property data members, call the <xref:System.Windows.Freezable.ReadPreamble%2A> method.</span></span>  
  
- <span data-ttu-id="d70ab-186">비 종속성 속성 데이터 멤버를 기록 하는 모든 API의 시작 부분에서 호출 된 <xref:System.Windows.Freezable.WritePreamble%2A> 메서드.</span><span class="sxs-lookup"><span data-stu-id="d70ab-186">At the beginning of any API that writes non-dependency property data members, call the <xref:System.Windows.Freezable.WritePreamble%2A> method.</span></span> <span data-ttu-id="d70ab-187">(호출한 후 <xref:System.Windows.Freezable.WritePreamble%2A> 에서 API를 추가로 호출할 필요가 <xref:System.Windows.Freezable.ReadPreamble%2A> 비 종속성 속성 데이터 멤버를 읽은 경우.)</span><span class="sxs-lookup"><span data-stu-id="d70ab-187">(Once you've called <xref:System.Windows.Freezable.WritePreamble%2A> in an API, you don't need to make an additional call to <xref:System.Windows.Freezable.ReadPreamble%2A> if you also read non-dependency property data members.)</span></span>  
  
- <span data-ttu-id="d70ab-188">호출 된 <xref:System.Windows.Freezable.WritePostscript%2A> 비 종속성 속성 데이터 멤버에 쓰는 메서드를 종료 하기 전에 메서드.</span><span class="sxs-lookup"><span data-stu-id="d70ab-188">Call the <xref:System.Windows.Freezable.WritePostscript%2A> method before exiting methods that write to non-dependency property data members.</span></span>  
  
 <span data-ttu-id="d70ab-189">클래스는 종속성 속성이 아닌 데이터 멤버를 포함 하는 경우 <xref:System.Windows.DependencyObject> 개체를 호출 해야 합니다 <xref:System.Windows.Freezable.OnFreezablePropertyChanged%2A> 을 변경할 때마다 해당 값 중 하나 멤버를 설정 하는 경우에 메서드 `null`합니다.</span><span class="sxs-lookup"><span data-stu-id="d70ab-189">If your class contains non-dependency-property data members that are <xref:System.Windows.DependencyObject> objects, you must also call the <xref:System.Windows.Freezable.OnFreezablePropertyChanged%2A> method each time you change one of their values, even if you're setting the member to `null`.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d70ab-190">각각 시작 하는 것이 중요 <xref:System.Windows.Freezable> 메서드가 기본 구현에 대 한 호출을 사용 하 여 재정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="d70ab-190">It's very important that you begin each <xref:System.Windows.Freezable> method you override with a call to the base implementation.</span></span>  
  
 <span data-ttu-id="d70ab-191">사용자 지정의 예 <xref:System.Windows.Freezable> 클래스를 참조 합니다 [사용자 지정 애니메이션 샘플](https://go.microsoft.com/fwlink/?LinkID=159981)합니다.</span><span class="sxs-lookup"><span data-stu-id="d70ab-191">For an example of a custom <xref:System.Windows.Freezable> class, see the [Custom Animation Sample](https://go.microsoft.com/fwlink/?LinkID=159981).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d70ab-192">참고자료</span><span class="sxs-lookup"><span data-stu-id="d70ab-192">See also</span></span>

- <xref:System.Windows.Freezable>
- [<span data-ttu-id="d70ab-193">사용자 지정 애니메이션 샘플</span><span class="sxs-lookup"><span data-stu-id="d70ab-193">Custom Animation Sample</span></span>](https://go.microsoft.com/fwlink/?LinkID=159981)
- [<span data-ttu-id="d70ab-194">종속성 속성 개요</span><span class="sxs-lookup"><span data-stu-id="d70ab-194">Dependency Properties Overview</span></span>](dependency-properties-overview.md)
- [<span data-ttu-id="d70ab-195">사용자 지정 종속성 속성</span><span class="sxs-lookup"><span data-stu-id="d70ab-195">Custom Dependency Properties</span></span>](custom-dependency-properties.md)
