---
title: '방법: ImageDrawing을 사용하여 이미지 그리기'
ms.date: 03/30/2017
helpviewer_keywords:
- drawing [WPF], images
- graphics [WPF], drawing images
- images [WPF], drawing
ms.assetid: df28ab41-25fb-4ab3-b51d-7f695b24f55e
ms.openlocfilehash: 5c1617d1a60fde8e9f1c215a5b644f6fd330817a
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54629074"
---
# <a name="how-to-draw-an-image-using-imagedrawing"></a><span data-ttu-id="92004-102">방법: ImageDrawing을 사용하여 이미지 그리기</span><span class="sxs-lookup"><span data-stu-id="92004-102">How to: Draw an Image Using ImageDrawing</span></span>
<span data-ttu-id="92004-103">사용 하는 방법을 보여 주는이 예제는 <xref:System.Windows.Media.ImageDrawing> 이미지를 그리기 위해.</span><span class="sxs-lookup"><span data-stu-id="92004-103">This example shows how to use an <xref:System.Windows.Media.ImageDrawing> to draw an image.</span></span> <span data-ttu-id="92004-104"><xref:System.Windows.Media.ImageDrawing> 표시할 수 있도록을 <xref:System.Windows.Media.ImageSource> 사용 하 여를 <xref:System.Windows.Media.DrawingBrush>, <xref:System.Windows.Media.DrawingImage>, 또는 <xref:System.Windows.Media.Visual>합니다.</span><span class="sxs-lookup"><span data-stu-id="92004-104">An <xref:System.Windows.Media.ImageDrawing> enables you display an <xref:System.Windows.Media.ImageSource> with a <xref:System.Windows.Media.DrawingBrush>, <xref:System.Windows.Media.DrawingImage>, or <xref:System.Windows.Media.Visual>.</span></span> <span data-ttu-id="92004-105">만든 이미지를 그릴를 <xref:System.Windows.Media.ImageDrawing> 설정 및 해당 <xref:System.Windows.Media.ImageDrawing.ImageSource%2A?displayProperty=nameWithType> 고 <xref:System.Windows.Media.ImageDrawing.Rect%2A?displayProperty=nameWithType> 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="92004-105">To draw an image, you create an <xref:System.Windows.Media.ImageDrawing> and set its <xref:System.Windows.Media.ImageDrawing.ImageSource%2A?displayProperty=nameWithType> and <xref:System.Windows.Media.ImageDrawing.Rect%2A?displayProperty=nameWithType> properties.</span></span> <span data-ttu-id="92004-106">합니다 <xref:System.Windows.Media.ImageDrawing.ImageSource%2A?displayProperty=nameWithType> 그릴 이미지를 지정 하는 속성 및 <xref:System.Windows.Media.ImageDrawing.Rect%2A?displayProperty=nameWithType> 속성 각 이미지의 크기와 위치를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="92004-106">The <xref:System.Windows.Media.ImageDrawing.ImageSource%2A?displayProperty=nameWithType> property specifies the image to draw, and the <xref:System.Windows.Media.ImageDrawing.Rect%2A?displayProperty=nameWithType> property specifies the position and size of each image.</span></span>  
  
## <a name="example"></a><span data-ttu-id="92004-107">예제</span><span class="sxs-lookup"><span data-stu-id="92004-107">Example</span></span>  
 <span data-ttu-id="92004-108">다음 예에서는 4를 사용 하 여 합성 그리기 <xref:System.Windows.Media.ImageDrawing> 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="92004-108">The following example creates a composite drawing using four <xref:System.Windows.Media.ImageDrawing> objects.</span></span> <span data-ttu-id="92004-109">이 예제는 다음 이미지를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="92004-109">This example produces the following image:</span></span>  
  
 <span data-ttu-id="92004-110">![여러 가지 DrawingImage 개체](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-imagedrawingexample.jpg "graphicsmm_ImageDrawingExample")</span><span class="sxs-lookup"><span data-stu-id="92004-110">![Several DrawingImage objects](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-imagedrawingexample.jpg "graphicsmm_ImageDrawingExample")</span></span>  
<span data-ttu-id="92004-111">4 개의 ImageDrawing 개체</span><span class="sxs-lookup"><span data-stu-id="92004-111">Four ImageDrawing objects</span></span>  
  
 [!code-csharp[DrawingMiscSnippets_snip#ImageDrawingExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/ImageDrawingExample.cs#imagedrawingexample)]
 [!code-xaml[DrawingMiscSnippets_snip#ImageDrawingExample](../../../../samples/snippets/xaml/VS_Snippets_Wpf/DrawingMiscSnippets_snip/XAML/ImageDrawingExample.xaml#imagedrawingexample)]  
  
 <span data-ttu-id="92004-112">사용 하지 않고 이미지를 표시 하는 간단한 방법을 보여 주는 예제 <xref:System.Windows.Media.ImageDrawing>를 참조 하세요 [Image 요소 사용](../../../../docs/framework/wpf/controls/how-to-use-the-image-element.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="92004-112">For an example showing a simple way to display an image without using <xref:System.Windows.Media.ImageDrawing>, see [Use the Image Element](../../../../docs/framework/wpf/controls/how-to-use-the-image-element.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="92004-113">참고자료</span><span class="sxs-lookup"><span data-stu-id="92004-113">See also</span></span>
- <xref:System.Windows.Freezable.Freeze%2A>
- <xref:System.Windows.Controls.Image>
- [<span data-ttu-id="92004-114">Drawing 개체 개요</span><span class="sxs-lookup"><span data-stu-id="92004-114">Drawing Objects Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/drawing-objects-overview.md)
- [<span data-ttu-id="92004-115">Freezable 개체 개요</span><span class="sxs-lookup"><span data-stu-id="92004-115">Freezable Objects Overview</span></span>](../../../../docs/framework/wpf/advanced/freezable-objects-overview.md)
- [<span data-ttu-id="92004-116">PresentationOptions:Freeze 특성</span><span class="sxs-lookup"><span data-stu-id="92004-116">PresentationOptions:Freeze Attribute</span></span>](../../../../docs/framework/wpf/advanced/presentationoptions-freeze-attribute.md)
