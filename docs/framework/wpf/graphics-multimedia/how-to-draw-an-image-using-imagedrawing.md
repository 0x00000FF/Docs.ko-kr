---
title: '방법: ImageDrawing을 사용하여 이미지 그리기'
ms.date: 03/30/2017
helpviewer_keywords:
- drawing [WPF], images
- graphics [WPF], drawing images
- images [WPF], drawing
ms.assetid: df28ab41-25fb-4ab3-b51d-7f695b24f55e
ms.openlocfilehash: 2c7771f841fb3b600d4790eb4d484b0a09c45dd5
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33559881"
---
# <a name="how-to-draw-an-image-using-imagedrawing"></a><span data-ttu-id="7293a-102">방법: ImageDrawing을 사용하여 이미지 그리기</span><span class="sxs-lookup"><span data-stu-id="7293a-102">How to: Draw an Image Using ImageDrawing</span></span>
<span data-ttu-id="7293a-103">사용 하는 방법을 보여 주는이 예제는 <xref:System.Windows.Media.ImageDrawing> 이미지를 그리기 위해 합니다.</span><span class="sxs-lookup"><span data-stu-id="7293a-103">This example shows how to use an <xref:System.Windows.Media.ImageDrawing> to draw an image.</span></span> <span data-ttu-id="7293a-104"><xref:System.Windows.Media.ImageDrawing> 표시할 수 있습니다는 <xref:System.Windows.Media.ImageSource> 와 <xref:System.Windows.Media.DrawingBrush>, <xref:System.Windows.Media.DrawingImage>, 또는 <xref:System.Windows.Media.Visual>합니다.</span><span class="sxs-lookup"><span data-stu-id="7293a-104">An <xref:System.Windows.Media.ImageDrawing> enables you display an <xref:System.Windows.Media.ImageSource> with a <xref:System.Windows.Media.DrawingBrush>, <xref:System.Windows.Media.DrawingImage>, or <xref:System.Windows.Media.Visual>.</span></span> <span data-ttu-id="7293a-105">이미지를 그리기 위해 만들는 <xref:System.Windows.Media.ImageDrawing> 설정 하 고 해당 <xref:System.Windows.Media.ImageDrawing.ImageSource%2A?displayProperty=nameWithType> 및 <xref:System.Windows.Media.ImageDrawing.Rect%2A?displayProperty=nameWithType> 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="7293a-105">To draw an image, you create an <xref:System.Windows.Media.ImageDrawing> and set its <xref:System.Windows.Media.ImageDrawing.ImageSource%2A?displayProperty=nameWithType> and <xref:System.Windows.Media.ImageDrawing.Rect%2A?displayProperty=nameWithType> properties.</span></span> <span data-ttu-id="7293a-106"><xref:System.Windows.Media.ImageDrawing.ImageSource%2A?displayProperty=nameWithType> 속성 지정 그릴, 이미지 및 <xref:System.Windows.Media.ImageDrawing.Rect%2A?displayProperty=nameWithType> 속성 각 이미지의 크기와 위치를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="7293a-106">The <xref:System.Windows.Media.ImageDrawing.ImageSource%2A?displayProperty=nameWithType> property specifies the image to draw, and the <xref:System.Windows.Media.ImageDrawing.Rect%2A?displayProperty=nameWithType> property specifies the position and size of each image.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7293a-107">예제</span><span class="sxs-lookup"><span data-stu-id="7293a-107">Example</span></span>  
 <span data-ttu-id="7293a-108">다음 예제에서는 4 개를 사용 하 여 복합 그리기 <xref:System.Windows.Media.ImageDrawing> 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="7293a-108">The following example creates a composite drawing using four <xref:System.Windows.Media.ImageDrawing> objects.</span></span> <span data-ttu-id="7293a-109">이 예제는 다음 이미지를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="7293a-109">This example produces the following image:</span></span>  
  
 <span data-ttu-id="7293a-110">![여러 가지 DrawingImage 개체](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-imagedrawingexample.jpg "graphicsmm_ImageDrawingExample")</span><span class="sxs-lookup"><span data-stu-id="7293a-110">![Several DrawingImage objects](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-imagedrawingexample.jpg "graphicsmm_ImageDrawingExample")</span></span>  
<span data-ttu-id="7293a-111">4 개의 ImageDrawing 개체</span><span class="sxs-lookup"><span data-stu-id="7293a-111">Four ImageDrawing objects</span></span>  
  
 [!code-csharp[DrawingMiscSnippets_snip#ImageDrawingExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/ImageDrawingExample.cs#imagedrawingexample)]
 [!code-xaml[DrawingMiscSnippets_snip#ImageDrawingExample](../../../../samples/snippets/xaml/VS_Snippets_Wpf/DrawingMiscSnippets_snip/XAML/ImageDrawingExample.xaml#imagedrawingexample)]  
  
 <span data-ttu-id="7293a-112">사용 하지 않고 이미지를 표시 하는 간단한 방법을 보여 주는 예제 <xref:System.Windows.Media.ImageDrawing>, 참조 [이미지 요소를 사용 하 여](../../../../docs/framework/wpf/controls/how-to-use-the-image-element.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="7293a-112">For an example showing a simple way to display an image without using <xref:System.Windows.Media.ImageDrawing>, see [Use the Image Element](../../../../docs/framework/wpf/controls/how-to-use-the-image-element.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7293a-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="7293a-113">See Also</span></span>  
 <xref:System.Windows.Freezable.Freeze%2A>  
 <xref:System.Windows.Controls.Image>  
 [<span data-ttu-id="7293a-114">Drawing 개체 개요</span><span class="sxs-lookup"><span data-stu-id="7293a-114">Drawing Objects Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/drawing-objects-overview.md)  
 [<span data-ttu-id="7293a-115">Freezable 개체 개요</span><span class="sxs-lookup"><span data-stu-id="7293a-115">Freezable Objects Overview</span></span>](../../../../docs/framework/wpf/advanced/freezable-objects-overview.md)  
 [<span data-ttu-id="7293a-116">PresentationOptions:Freeze 특성</span><span class="sxs-lookup"><span data-stu-id="7293a-116">PresentationOptions:Freeze Attribute</span></span>](../../../../docs/framework/wpf/advanced/presentationoptions-freeze-attribute.md)
