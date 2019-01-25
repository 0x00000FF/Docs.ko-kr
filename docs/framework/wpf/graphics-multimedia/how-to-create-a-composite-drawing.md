---
title: '방법: 합성 그리기 만들기'
ms.date: 03/30/2017
helpviewer_keywords:
- drawings [WPF], composite
- composite drawings [WPF]
- graphics [WPF], composite drawings
ms.assetid: 066eb0ab-5f0e-439d-85c6-dca60af269fc
ms.openlocfilehash: 886956b03bd3e17360283cee1bc0e4db1d2a4731
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54491417"
---
# <a name="how-to-create-a-composite-drawing"></a><span data-ttu-id="d1ad1-102">방법: 합성 그리기 만들기</span><span class="sxs-lookup"><span data-stu-id="d1ad1-102">How to: Create a Composite Drawing</span></span>
<span data-ttu-id="d1ad1-103">사용 하는 방법을 보여 주는이 예제는 <xref:System.Windows.Media.DrawingGroup> 여러 결합 하 여 복잡 한 그리기를 만들려면 <xref:System.Windows.Media.Drawing> 를 단일 합성 그리기로 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="d1ad1-103">This example shows how to use a <xref:System.Windows.Media.DrawingGroup> to create complex drawings by combining multiple <xref:System.Windows.Media.Drawing> objects into a single composite drawing.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d1ad1-104">예제</span><span class="sxs-lookup"><span data-stu-id="d1ad1-104">Example</span></span>  
 <span data-ttu-id="d1ad1-105">다음 예제에서는 <xref:System.Windows.Media.DrawingGroup> 합성 그리기를 만들려고 합니다 <xref:System.Windows.Media.GeometryDrawing> 및 <xref:System.Windows.Media.ImageDrawing> 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="d1ad1-105">The following example uses a <xref:System.Windows.Media.DrawingGroup> to create a composite drawing from the <xref:System.Windows.Media.GeometryDrawing> and <xref:System.Windows.Media.ImageDrawing> objects.</span></span> <span data-ttu-id="d1ad1-106">다음 그림에서는 이 예제가 생성하는 출력을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="d1ad1-106">The following illustration shows the output that this example produces.</span></span>  
  
 <span data-ttu-id="d1ad1-107">![여러 있는 DrawingGroup](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-simple.jpg "graphicsmm_simple")</span><span class="sxs-lookup"><span data-stu-id="d1ad1-107">![A DrawingGroup with multiple drawings](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-simple.jpg "graphicsmm_simple")</span></span>  
<span data-ttu-id="d1ad1-108">DrawingGroup를 사용 하 여 만든 합성 그리기</span><span class="sxs-lookup"><span data-stu-id="d1ad1-108">A composite drawing that is created by using DrawingGroup</span></span>  
  
 <span data-ttu-id="d1ad1-109">그리기의 범위를 보여 주는 회색 테두리를 note 합니다.</span><span class="sxs-lookup"><span data-stu-id="d1ad1-109">Note the gray border, which shows the bounds of the drawing.</span></span>  
  
 [!code-csharp[DrawingMiscSnippets_snip#GraphicsMMSimpleDrawingGroupExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/DrawingGroupExample.cs#graphicsmmsimpledrawinggroupexample)]
 [!code-xaml[DrawingMiscSnippets_snip#GraphicsMMSimpleDrawingGroupExample](../../../../samples/snippets/xaml/VS_Snippets_Wpf/DrawingMiscSnippets_snip/XAML/DrawingGroupExample.xaml#graphicsmmsimpledrawinggroupexample)]  
  
 <span data-ttu-id="d1ad1-110">사용할 수는 <xref:System.Windows.Media.DrawingGroup> 적용할를 <xref:System.Windows.Media.DrawingGroup.Transform%2A>, <xref:System.Windows.Media.DrawingGroup.Opacity%2A> 설정을 <xref:System.Windows.Media.DrawingGroup.OpacityMask%2A>, <xref:System.Windows.Media.DrawingGroup.BitmapEffect%2A>를 <xref:System.Windows.Media.DrawingGroup.ClipGeometry%2A>, 또는 <xref:System.Windows.Media.DrawingGroup.GuidelineSet%2A> 포함 그리기에.</span><span class="sxs-lookup"><span data-stu-id="d1ad1-110">You can use a <xref:System.Windows.Media.DrawingGroup> to apply a <xref:System.Windows.Media.DrawingGroup.Transform%2A>, <xref:System.Windows.Media.DrawingGroup.Opacity%2A> setting, <xref:System.Windows.Media.DrawingGroup.OpacityMask%2A>, <xref:System.Windows.Media.DrawingGroup.BitmapEffect%2A>, <xref:System.Windows.Media.DrawingGroup.ClipGeometry%2A>, or <xref:System.Windows.Media.DrawingGroup.GuidelineSet%2A> to the drawings it contains.</span></span> <span data-ttu-id="d1ad1-111">때문에 <xref:System.Windows.Media.DrawingGroup> 이기도 <xref:System.Windows.Media.Drawing>, 기타를 포함할 수 있습니다 <xref:System.Windows.Media.DrawingGroup> 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="d1ad1-111">Because a <xref:System.Windows.Media.DrawingGroup> is also a <xref:System.Windows.Media.Drawing>, it can contain other <xref:System.Windows.Media.DrawingGroup> objects.</span></span>  
  
 <span data-ttu-id="d1ad1-112">다음 예제에서는 추가 사용 하 여에 앞의 예제에 비슷합니다. <xref:System.Windows.Media.DrawingGroup> 일부 그리기를 불투명 마스크 및 비트맵 효과 적용 하는 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="d1ad1-112">The following example is similar to the preceding example, except that it uses additional <xref:System.Windows.Media.DrawingGroup> objects to apply bitmap effects and an opacity mask to some of its drawings.</span></span> <span data-ttu-id="d1ad1-113">다음 그림에서는 이 예제가 생성하는 출력을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="d1ad1-113">The following illustration shows the output that this example produces.</span></span>  
  
 <span data-ttu-id="d1ad1-114">![여러 있는 DrawingGroup](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-multiple.jpg "graphicsmm_multiple")</span><span class="sxs-lookup"><span data-stu-id="d1ad1-114">![A DrawingGroup with multiple drawings](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-multiple.jpg "graphicsmm_multiple")</span></span>  
<span data-ttu-id="d1ad1-115">합성 그리기는 여러 DrawingGroup 개체는</span><span class="sxs-lookup"><span data-stu-id="d1ad1-115">Composite drawing that has multiple DrawingGroup objects</span></span>  
  
 <span data-ttu-id="d1ad1-116">그리기의 범위를 보여 주는 회색 테두리를 note 합니다.</span><span class="sxs-lookup"><span data-stu-id="d1ad1-116">Note the gray border, which shows the bounds of the drawing.</span></span>  
  
 [!code-csharp[DrawingMiscSnippets_snip#GraphicsMMMultipleDrawingGroupsExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/DrawingGroupExample.cs#graphicsmmmultipledrawinggroupsexample)]
 [!code-xaml[DrawingMiscSnippets_snip#GraphicsMMMultipleDrawingGroupsExample](../../../../samples/snippets/xaml/VS_Snippets_Wpf/DrawingMiscSnippets_snip/XAML/DrawingGroupExample.xaml#graphicsmmmultipledrawinggroupsexample)]  
  
 <span data-ttu-id="d1ad1-117">에 대 한 자세한 내용은 <xref:System.Windows.Media.Drawing> 개체를 참조 하세요 [Drawing 개체 개요](../../../../docs/framework/wpf/graphics-multimedia/drawing-objects-overview.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="d1ad1-117">For more information about <xref:System.Windows.Media.Drawing> objects, see [Drawing Objects Overview](../../../../docs/framework/wpf/graphics-multimedia/drawing-objects-overview.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d1ad1-118">참고자료</span><span class="sxs-lookup"><span data-stu-id="d1ad1-118">See also</span></span>
- <xref:System.Windows.Media.DrawingGroup.BitmapEffect%2A>
- <xref:System.Windows.Media.DrawingGroup.Transform%2A>
- <xref:System.Windows.Media.DrawingGroup.OpacityMask%2A>
- <xref:System.Windows.Media.DrawingGroup.Opacity%2A>
- <xref:System.Windows.Media.DrawingGroup.ClipGeometry%2A>
- <xref:System.Windows.Media.DrawingGroup.GuidelineSet%2A>
- [<span data-ttu-id="d1ad1-119">Drawing 개체 개요</span><span class="sxs-lookup"><span data-stu-id="d1ad1-119">Drawing Objects Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/drawing-objects-overview.md)
