---
title: '방법: 사용자 지정 컨트롤에서 잉크 선택'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- controls [WPF], ink selection
- ink [WPF], selecting from custom control
- custom controls [WPF], ink selection
ms.assetid: 5f3a45c6-6d40-4017-9b47-933f134ceba3
ms.openlocfilehash: 5c9b2f3d64e4cbb309772d6a1d9fa88f589df84c
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59173600"
---
# <a name="how-to-select-ink-from-a-custom-control"></a><span data-ttu-id="3956f-102">방법: 사용자 지정 컨트롤에서 잉크 선택</span><span class="sxs-lookup"><span data-stu-id="3956f-102">How to: Select Ink from a Custom Control</span></span>
<span data-ttu-id="3956f-103">추가 하 여는 <xref:System.Windows.Ink.IncrementalLassoHitTester> 사용자 지정 컨트롤에 설정할 수 있습니다. 사용자는 방식과 유사 하 게 올가미 도구를 사용 하 여 잉크를 선택할 수 있도록 컨트롤을 <xref:System.Windows.Controls.InkCanvas> 올가미를 사용 하 여 잉크를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="3956f-103">By adding an <xref:System.Windows.Ink.IncrementalLassoHitTester> to your custom control, you can enable your control so that a user can select ink with a lasso tool, similar to the way the <xref:System.Windows.Controls.InkCanvas> selects ink with a lasso.</span></span>  
  
 <span data-ttu-id="3956f-104">이 예제에서는 잉크 지원 사용자 지정 컨트롤을 만드는 익숙하다고 가정 합니다.</span><span class="sxs-lookup"><span data-stu-id="3956f-104">This example assumes you are familiar with creating an ink-enabled custom control.</span></span>  <span data-ttu-id="3956f-105">잉크 입력을 허용 하는 사용자 지정 컨트롤을 참조 하세요 [잉크 입력 컨트롤 만들기](creating-an-ink-input-control.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="3956f-105">To create a custom control that accepts ink input, see [Creating an Ink Input Control](creating-an-ink-input-control.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="3956f-106">예제</span><span class="sxs-lookup"><span data-stu-id="3956f-106">Example</span></span>  
 <span data-ttu-id="3956f-107">사용자가 올가미를 그릴 때는 <xref:System.Windows.Ink.IncrementalLassoHitTester> 예측는 스트로크는 올가미 경로 경계 내에서 사용자가 올가미를 완료 합니다.</span><span class="sxs-lookup"><span data-stu-id="3956f-107">When the user draws a lasso, the <xref:System.Windows.Ink.IncrementalLassoHitTester> predicts which strokes will be within the lasso path's boundaries after the user completes the lasso.</span></span>  <span data-ttu-id="3956f-108">선택 중인 올가미 경로 경계 내에 확인 된 스트로크를 생각할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3956f-108">Strokes that are determined to be within the lasso path's boundaries can be thought of as being selected.</span></span>  <span data-ttu-id="3956f-109">선택된 된 스트로크를 선택 하지 않은 될 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3956f-109">Selected strokes can also become unselected.</span></span>  <span data-ttu-id="3956f-110">예를 들어 사용자 올가미를 그리는 동안 방향을 반대로 <xref:System.Windows.Ink.IncrementalLassoHitTester> 일부 스트로크를 선택 취소 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3956f-110">For example, if the user reverses direction while drawing the lasso, the <xref:System.Windows.Ink.IncrementalLassoHitTester> may unselect some strokes.</span></span>  
  
 <span data-ttu-id="3956f-111"><xref:System.Windows.Ink.IncrementalLassoHitTester> 발생을 <xref:System.Windows.Ink.IncrementalLassoHitTester.SelectionChanged> 사용자 올가미를 그리는 동안 응답을 사용자 지정 컨트롤을 사용 하도록 설정 하는 이벤트입니다.</span><span class="sxs-lookup"><span data-stu-id="3956f-111">The <xref:System.Windows.Ink.IncrementalLassoHitTester> raises the <xref:System.Windows.Ink.IncrementalLassoHitTester.SelectionChanged> event, which enables your custom control to respond while the user is drawing the lasso.</span></span>  <span data-ttu-id="3956f-112">예를 들어, 사용자 선택 하 고 선택 취소 하는 대로 스트로크의 모양을 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3956f-112">For example, you can change the appearance of strokes as the user selects and unselects them.</span></span>  
  
## <a name="managing-the-ink-mode"></a><span data-ttu-id="3956f-113">잉크 모드 관리</span><span class="sxs-lookup"><span data-stu-id="3956f-113">Managing the Ink Mode</span></span>  
 <span data-ttu-id="3956f-114">올가미 컨트롤에서 잉크를 다르게 표시 되 면 사용자에 게 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3956f-114">It is helpful to the user if the lasso appears differently than the ink on your control.</span></span> <span data-ttu-id="3956f-115">이렇게 하려면 사용자 지정 컨트롤 해야 여부를 추적 사용자가 작성 하거나 잉크를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="3956f-115">To accomplish this, your custom control must keep track of whether the user is writing or selecting ink.</span></span> <span data-ttu-id="3956f-116">이 작업을 수행 하는 가장 쉬운 방법은 두 값을 사용 하 여 열거형을 선언 하는 것: 잉크 및 사용자 잉크 선택 하는 것을 나타내려면 1 사용자가 쓰기를 나타내는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="3956f-116">The easiest way to do this is to declare an enumeration with two values: one to indicate that the user is writing ink and one to indicate that the user is selecting ink.</span></span>  
  
 [!code-csharp[HowToSelectInk#2](~/samples/snippets/csharp/VS_Snippets_Wpf/HowToSelectInk/CSharp/InkSelector.cs#2)]
 [!code-vb[HowToSelectInk#2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HowToSelectInk/VisualBasic/InkSelector.vb#2)]  
  
 <span data-ttu-id="3956f-117">다음으로 두 개의 추가 <xref:System.Windows.Ink.DrawingAttributes> 클래스: 사용자가 잉크 사용자가 잉크를 선택 하는 경우 사용할 때 사용할 것입니다.</span><span class="sxs-lookup"><span data-stu-id="3956f-117">Next, add two <xref:System.Windows.Ink.DrawingAttributes> to the class: one to use when the user writes ink, one to use when the user selects ink.</span></span>  <span data-ttu-id="3956f-118">생성자에서 초기화를 <xref:System.Windows.Ink.DrawingAttributes> 둘 다 연결 <xref:System.Windows.Ink.DrawingAttributes.AttributeChanged> 동일한 이벤트 처리기에는 이벤트입니다.</span><span class="sxs-lookup"><span data-stu-id="3956f-118">In the constructor, initialize the <xref:System.Windows.Ink.DrawingAttributes> and attach both <xref:System.Windows.Ink.DrawingAttributes.AttributeChanged> events to the same event handler.</span></span> <span data-ttu-id="3956f-119">설정한 합니다 <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer.DrawingAttributes%2A> 의 속성을 <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> 잉크를 <xref:System.Windows.Ink.DrawingAttributes>입니다.</span><span class="sxs-lookup"><span data-stu-id="3956f-119">Then set the <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer.DrawingAttributes%2A> property of the <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> to the ink <xref:System.Windows.Ink.DrawingAttributes>.</span></span>  
  
 [!code-csharp[HowToSelectInk#3](~/samples/snippets/csharp/VS_Snippets_Wpf/HowToSelectInk/CSharp/InkSelector.cs#3)]
 [!code-vb[HowToSelectInk#3](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HowToSelectInk/VisualBasic/InkSelector.vb#3)]  
[!code-csharp[HowToSelectInk#4](~/samples/snippets/csharp/VS_Snippets_Wpf/HowToSelectInk/CSharp/InkSelector.cs#4)]
[!code-vb[HowToSelectInk#4](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HowToSelectInk/VisualBasic/InkSelector.vb#4)]  
  
 <span data-ttu-id="3956f-120">선택 모드를 노출 하는 속성을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="3956f-120">Add a property that exposes the selection mode.</span></span> <span data-ttu-id="3956f-121">사용자 선택 모드가 변경 되 면 설정를 <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer.DrawingAttributes%2A> 의 속성을 <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> 적절 한 <xref:System.Windows.Ink.DrawingAttributes> 개체 한 후 다시 연결를 <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer.RootVisual%2A> 속성을를 <xref:System.Windows.Controls.InkPresenter>합니다.</span><span class="sxs-lookup"><span data-stu-id="3956f-121">When the user changes the selection mode, set the <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer.DrawingAttributes%2A> property of the <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> to the appropriate <xref:System.Windows.Ink.DrawingAttributes> object and then reattach the <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer.RootVisual%2A> Property to the <xref:System.Windows.Controls.InkPresenter>.</span></span>  
  
 [!code-csharp[HowToSelectInk#5](~/samples/snippets/csharp/VS_Snippets_Wpf/HowToSelectInk/CSharp/InkSelector.cs#5)]
 [!code-vb[HowToSelectInk#5](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HowToSelectInk/VisualBasic/InkSelector.vb#5)]  
  
 <span data-ttu-id="3956f-122">노출 된 <xref:System.Windows.Ink.DrawingAttributes> 응용 프로그램에는 잉크 스트로크 및 스트로크 선택의 모양을 확인할 수 있도록 하는 속성으로.</span><span class="sxs-lookup"><span data-stu-id="3956f-122">Expose the <xref:System.Windows.Ink.DrawingAttributes> as properties so applications can determine the appearance of the ink strokes and selection strokes.</span></span>  
  
 [!code-csharp[HowToSelectInk#6](~/samples/snippets/csharp/VS_Snippets_Wpf/HowToSelectInk/CSharp/InkSelector.cs#6)]
 [!code-vb[HowToSelectInk#6](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HowToSelectInk/VisualBasic/InkSelector.vb#6)]  
  
 <span data-ttu-id="3956f-123">때의 속성을 <xref:System.Windows.Ink.DrawingAttributes> 변경 내용을 개체를 <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer.RootVisual%2A> 다시 연결 되어야 합니다는 <xref:System.Windows.Controls.InkPresenter>합니다.</span><span class="sxs-lookup"><span data-stu-id="3956f-123">When a property of a <xref:System.Windows.Ink.DrawingAttributes> object changes, the <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer.RootVisual%2A> must be reattached to the <xref:System.Windows.Controls.InkPresenter>.</span></span>  <span data-ttu-id="3956f-124">에 대 한 이벤트 처리기에서는 <xref:System.Windows.Ink.DrawingAttributes.AttributeChanged> 이벤트를 다시 연결 합니다 <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer.RootVisual%2A> 에 <xref:System.Windows.Controls.InkPresenter>.</span><span class="sxs-lookup"><span data-stu-id="3956f-124">In the event handler for the <xref:System.Windows.Ink.DrawingAttributes.AttributeChanged> event, reattach the <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer.RootVisual%2A> to the <xref:System.Windows.Controls.InkPresenter>.</span></span>  
  
 [!code-csharp[HowToSelectInk#7](~/samples/snippets/csharp/VS_Snippets_Wpf/HowToSelectInk/CSharp/InkSelector.cs#7)]
 [!code-vb[HowToSelectInk#7](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HowToSelectInk/VisualBasic/InkSelector.vb#7)]  
  
## <a name="using-the-incrementallassohittester"></a><span data-ttu-id="3956f-125">IncrementalLassoHitTester를 사용 하 여</span><span class="sxs-lookup"><span data-stu-id="3956f-125">Using the IncrementalLassoHitTester</span></span>  
 <span data-ttu-id="3956f-126">만들기 및 초기화를 <xref:System.Windows.Ink.StrokeCollection> 선택한 스트로크가 들어 있는입니다.</span><span class="sxs-lookup"><span data-stu-id="3956f-126">Create and initialize a <xref:System.Windows.Ink.StrokeCollection> that contains the selected strokes.</span></span>  
  
 [!code-csharp[HowToSelectInk#8](~/samples/snippets/csharp/VS_Snippets_Wpf/HowToSelectInk/CSharp/InkSelector.cs#8)]
 [!code-vb[HowToSelectInk#8](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HowToSelectInk/VisualBasic/InkSelector.vb#8)]  
  
 <span data-ttu-id="3956f-127">사용자가 스트로크를 그릴 시작 되 면 잉크 또는 올가미를 선택된 된 스트로크의 선택 취소 합니다.</span><span class="sxs-lookup"><span data-stu-id="3956f-127">When the user starts to draw a stroke, either ink or the lasso, unselect any selected strokes.</span></span> <span data-ttu-id="3956f-128">그런 다음 사용자는 올가미를 그리고, 만듭니다는 <xref:System.Windows.Ink.IncrementalLassoHitTester> 를 호출 하 여 <xref:System.Windows.Ink.StrokeCollection.GetIncrementalLassoHitTester%2A>, 구독할 합니다 <xref:System.Windows.Ink.IncrementalLassoHitTester.SelectionChanged> 이벤트 및 호출 <xref:System.Windows.Ink.IncrementalHitTester.AddPoints%2A>합니다.</span><span class="sxs-lookup"><span data-stu-id="3956f-128">Then, if the user is drawing a lasso, create an <xref:System.Windows.Ink.IncrementalLassoHitTester> by calling <xref:System.Windows.Ink.StrokeCollection.GetIncrementalLassoHitTester%2A>, subscribe to the <xref:System.Windows.Ink.IncrementalLassoHitTester.SelectionChanged> event, and call <xref:System.Windows.Ink.IncrementalHitTester.AddPoints%2A>.</span></span> <span data-ttu-id="3956f-129">이 코드는 별도 메서드 수 있으며에서 호출 된 <xref:System.Windows.UIElement.OnStylusDown%2A> 고 <xref:System.Windows.UIElement.OnMouseDown%2A> 메서드.</span><span class="sxs-lookup"><span data-stu-id="3956f-129">This code can be a separate method and called from the <xref:System.Windows.UIElement.OnStylusDown%2A> and <xref:System.Windows.UIElement.OnMouseDown%2A> methods.</span></span>  
  
 [!code-csharp[HowToSelectInk#9](~/samples/snippets/csharp/VS_Snippets_Wpf/HowToSelectInk/CSharp/InkSelector.cs#9)]
 [!code-vb[HowToSelectInk#9](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HowToSelectInk/VisualBasic/InkSelector.vb#9)]  
  
 <span data-ttu-id="3956f-130">스타일러스 포인트를 추가 합니다 <xref:System.Windows.Ink.IncrementalLassoHitTester> 사용자 올가미를 그리는 동안.</span><span class="sxs-lookup"><span data-stu-id="3956f-130">Add the stylus points to the <xref:System.Windows.Ink.IncrementalLassoHitTester> while the user draws the lasso.</span></span>  <span data-ttu-id="3956f-131">다음 메서드를 호출 합니다 <xref:System.Windows.UIElement.OnStylusMove%2A>, <xref:System.Windows.UIElement.OnStylusUp%2A>를 <xref:System.Windows.UIElement.OnMouseMove%2A>, 및 <xref:System.Windows.UIElement.OnMouseLeftButtonUp%2A> 메서드.</span><span class="sxs-lookup"><span data-stu-id="3956f-131">Call the following method from the <xref:System.Windows.UIElement.OnStylusMove%2A>, <xref:System.Windows.UIElement.OnStylusUp%2A>, <xref:System.Windows.UIElement.OnMouseMove%2A>, and <xref:System.Windows.UIElement.OnMouseLeftButtonUp%2A> methods.</span></span>  
  
 [!code-csharp[HowToSelectInk#10](~/samples/snippets/csharp/VS_Snippets_Wpf/HowToSelectInk/CSharp/InkSelector.cs#10)]
 [!code-vb[HowToSelectInk#10](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HowToSelectInk/VisualBasic/InkSelector.vb#10)]  
  
 <span data-ttu-id="3956f-132">처리는 <xref:System.Windows.Ink.IncrementalLassoHitTester.SelectionChanged?displayProperty=nameWithType> 사용자 선택 하 고 스트로크를 선택 취소 하는 경우 응답 하는 이벤트입니다.</span><span class="sxs-lookup"><span data-stu-id="3956f-132">Handle the <xref:System.Windows.Ink.IncrementalLassoHitTester.SelectionChanged?displayProperty=nameWithType> event to respond when the user selects and unselects strokes.</span></span>  <span data-ttu-id="3956f-133">합니다 <xref:System.Windows.Ink.LassoSelectionChangedEventArgs> 클래스에는 <xref:System.Windows.Ink.LassoSelectionChangedEventArgs.SelectedStrokes%2A> 및 <xref:System.Windows.Ink.LassoSelectionChangedEventArgs.DeselectedStrokes%2A> 스트로크를 가져오는 속성을 선택 했으며 각각 선택 취소 합니다.</span><span class="sxs-lookup"><span data-stu-id="3956f-133">The <xref:System.Windows.Ink.LassoSelectionChangedEventArgs> class has the <xref:System.Windows.Ink.LassoSelectionChangedEventArgs.SelectedStrokes%2A> and <xref:System.Windows.Ink.LassoSelectionChangedEventArgs.DeselectedStrokes%2A> properties that get the strokes that were selected and unselected, respectively.</span></span>  
  
 [!code-csharp[HowToSelectInk#11](~/samples/snippets/csharp/VS_Snippets_Wpf/HowToSelectInk/CSharp/InkSelector.cs#11)]
 [!code-vb[HowToSelectInk#11](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HowToSelectInk/VisualBasic/InkSelector.vb#11)]  
  
 <span data-ttu-id="3956f-134">사용자 그리기 올가미 완료 되 면에서 등록을 취소 합니다 <xref:System.Windows.Ink.IncrementalLassoHitTester.SelectionChanged> 이벤트 및 호출 <xref:System.Windows.Ink.IncrementalHitTester.EndHitTesting%2A>합니다.</span><span class="sxs-lookup"><span data-stu-id="3956f-134">When the user finishes drawing the lasso, unsubscribe from the <xref:System.Windows.Ink.IncrementalLassoHitTester.SelectionChanged> event and call <xref:System.Windows.Ink.IncrementalHitTester.EndHitTesting%2A>.</span></span>  
  
 [!code-csharp[HowToSelectInk#12](~/samples/snippets/csharp/VS_Snippets_Wpf/HowToSelectInk/CSharp/InkSelector.cs#12)]
 [!code-vb[HowToSelectInk#12](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HowToSelectInk/VisualBasic/InkSelector.vb#12)]  
  
## <a name="putting-it-all-together"></a><span data-ttu-id="3956f-135">모든 함께 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="3956f-135">Putting it All Together.</span></span>  
 <span data-ttu-id="3956f-136">다음 예제는 사용자는 올가미를 사용 하 여 잉크를 선택할 수 있도록 사용자 지정 컨트롤입니다.</span><span class="sxs-lookup"><span data-stu-id="3956f-136">The following example is a custom control that enables a user to select ink with a lasso.</span></span>  
  
 [!code-csharp[HowToSelectInk#1](~/samples/snippets/csharp/VS_Snippets_Wpf/HowToSelectInk/CSharp/InkSelector.cs#1)]
 [!code-vb[HowToSelectInk#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HowToSelectInk/VisualBasic/InkSelector.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="3956f-137">참고자료</span><span class="sxs-lookup"><span data-stu-id="3956f-137">See also</span></span>

- <xref:System.Windows.Ink.IncrementalLassoHitTester>
- <xref:System.Windows.Ink.StrokeCollection>
- <xref:System.Windows.Input.StylusPointCollection>
- [<span data-ttu-id="3956f-138">잉크 입력 컨트롤 만들기</span><span class="sxs-lookup"><span data-stu-id="3956f-138">Creating an Ink Input Control</span></span>](creating-an-ink-input-control.md)
