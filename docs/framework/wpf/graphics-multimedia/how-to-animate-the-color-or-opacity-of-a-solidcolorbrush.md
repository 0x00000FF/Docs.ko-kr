---
title: '방법: SolidColorBrush의 색 또는 불투명도에 애니메이션 효과 주기'
ms.date: 03/30/2017
helpviewer_keywords:
- SolidColorBrush [WPF], animating color of
- colors [WPF], animating
- opacity [WPF], animating
- animation [WPF], color of SolidColorBrush
- animation [WPF], opacity of SolidColorBrush
- SolidColorBrush [WPF], animating opacity of
ms.assetid: d9154354-843f-4713-bad1-35bb0ba6eaeb
ms.openlocfilehash: e440cf49b8b16051361650f9659dc6006c2e7b56
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61789248"
---
# <a name="how-to-animate-the-color-or-opacity-of-a-solidcolorbrush"></a><span data-ttu-id="66d7f-102">방법: SolidColorBrush의 색 또는 불투명도에 애니메이션 효과 주기</span><span class="sxs-lookup"><span data-stu-id="66d7f-102">How to: Animate the Color or Opacity of a SolidColorBrush</span></span>
<span data-ttu-id="66d7f-103">애니메이션을 적용 하는 방법을 보여 주는이 예제는 <xref:System.Windows.Media.SolidColorBrush.Color%2A> 하 고 <xref:System.Windows.Media.Brush.Opacity%2A> 의 <xref:System.Windows.Media.SolidColorBrush>합니다.</span><span class="sxs-lookup"><span data-stu-id="66d7f-103">This example shows how to animate the <xref:System.Windows.Media.SolidColorBrush.Color%2A> and <xref:System.Windows.Media.Brush.Opacity%2A> of a <xref:System.Windows.Media.SolidColorBrush>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="66d7f-104">예제</span><span class="sxs-lookup"><span data-stu-id="66d7f-104">Example</span></span>  
 <span data-ttu-id="66d7f-105">다음 예제에서는 3 개의 애니메이션을 사용 하 여 애니메이션 효과를 주는 합니다 <xref:System.Windows.Media.SolidColorBrush.Color%2A> 하 고 <xref:System.Windows.Media.Brush.Opacity%2A> 의 <xref:System.Windows.Media.SolidColorBrush>.</span><span class="sxs-lookup"><span data-stu-id="66d7f-105">The following example uses three animations to animate the <xref:System.Windows.Media.SolidColorBrush.Color%2A> and <xref:System.Windows.Media.Brush.Opacity%2A> of a <xref:System.Windows.Media.SolidColorBrush>.</span></span>  
  
- <span data-ttu-id="66d7f-106">첫 번째 애니메이션을 <xref:System.Windows.Media.Animation.ColorAnimation>, 브러시의 색을 변경 <xref:System.Windows.Media.Colors.Gray%2A> 마우스 사각형 안으로 이동할 때.</span><span class="sxs-lookup"><span data-stu-id="66d7f-106">The first animation, a <xref:System.Windows.Media.Animation.ColorAnimation>, changes the brush's color to <xref:System.Windows.Media.Colors.Gray%2A> when the mouse enters the rectangle.</span></span>  
  
- <span data-ttu-id="66d7f-107">다음 애니메이션 다른 <xref:System.Windows.Media.Animation.ColorAnimation>, 브러시의 색을 변경 <xref:System.Windows.Media.Colors.Orange%2A> 마우스가 사각형을 벗어날 때입니다.</span><span class="sxs-lookup"><span data-stu-id="66d7f-107">The next animation, another <xref:System.Windows.Media.Animation.ColorAnimation>, changes the brush's color to <xref:System.Windows.Media.Colors.Orange%2A> when the mouse leaves the rectangle.</span></span>  
  
- <span data-ttu-id="66d7f-108">마지막 애니메이션을 <xref:System.Windows.Media.Animation.DoubleAnimation>, 마우스 왼쪽된 단추를 누를 때 브러시의 불투명도 0.0으로 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="66d7f-108">The final animation, a <xref:System.Windows.Media.Animation.DoubleAnimation>, changes the brush's opacity to 0.0 when the left mouse button is pressed.</span></span>  
  
 [!code-csharp[brushanimations_snip#SolidColorBrushAnimationExample](~/samples/snippets/csharp/VS_Snippets_Wpf/brushanimations_snip/CSharp/SolidColorBrushExample.cs#solidcolorbrushanimationexample)]  
  
 <span data-ttu-id="66d7f-109">다양 한 유형의 브러시에 애니메이션을 적용 하는 방법을 보여주는 전체 샘플을 보려면 합니다 [브러시 샘플](https://go.microsoft.com/fwlink/?LinkID=159973)합니다.</span><span class="sxs-lookup"><span data-stu-id="66d7f-109">For a more complete sample, which shows how to animate different types of brushes, see the [Brushes Sample](https://go.microsoft.com/fwlink/?LinkID=159973).</span></span> <span data-ttu-id="66d7f-110">애니메이션에 대 한 자세한 내용은 참조는 [애니메이션 개요](animation-overview.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="66d7f-110">For more information about animation, see the [Animation Overview](animation-overview.md).</span></span>  
  
 <span data-ttu-id="66d7f-111">다른 애니메이션 예제를 사용 하 여 일관성을 위해이 예제의 코드 버전 사용을 <xref:System.Windows.Media.Animation.Storyboard> 애니메이션을 적용 하는 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="66d7f-111">For consistency with other animation examples, the code versions of this example use a <xref:System.Windows.Media.Animation.Storyboard> object to apply their animations.</span></span> <span data-ttu-id="66d7f-112">그러나 코드에서 단일 애니메이션을 적용할 때 간단 하 게 사용 합니다 <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A> 사용 하는 대신 메서드를 <xref:System.Windows.Media.Animation.Storyboard>입니다.</span><span class="sxs-lookup"><span data-stu-id="66d7f-112">However, when applying a single animation in code, it's simpler to use the <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A> method instead of using a <xref:System.Windows.Media.Animation.Storyboard>.</span></span> <span data-ttu-id="66d7f-113">예제를 보려면 [Storyboard를 사용하지 않고 속성에 애니메이션 효과 주기](how-to-animate-a-property-without-using-a-storyboard.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="66d7f-113">For an example, see [Animate a Property Without Using a Storyboard](how-to-animate-a-property-without-using-a-storyboard.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="66d7f-114">참고자료</span><span class="sxs-lookup"><span data-stu-id="66d7f-114">See also</span></span>

- [<span data-ttu-id="66d7f-115">애니메이션 개요</span><span class="sxs-lookup"><span data-stu-id="66d7f-115">Animation Overview</span></span>](animation-overview.md)
- [<span data-ttu-id="66d7f-116">Storyboard 개요</span><span class="sxs-lookup"><span data-stu-id="66d7f-116">Storyboards Overview</span></span>](storyboards-overview.md)
- [<span data-ttu-id="66d7f-117">브러시 샘플</span><span class="sxs-lookup"><span data-stu-id="66d7f-117">Brushes Sample</span></span>](https://go.microsoft.com/fwlink/?LinkID=159973)
