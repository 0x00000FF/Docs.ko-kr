---
title: '방법: Image 요소 사용'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- controls [WPF], Image
- Image control [WPF]
- rendering images [WPF]
ms.assetid: 5b92e74b-1b56-4756-ac64-d5e9e08d9854
ms.openlocfilehash: 967159894e25721bdf380f851712e91d76088f87
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59205305"
---
# <a name="how-to-use-the-image-element"></a><span data-ttu-id="4a144-102">방법: Image 요소 사용</span><span class="sxs-lookup"><span data-stu-id="4a144-102">How to: Use the Image Element</span></span>
<span data-ttu-id="4a144-103">사용 하 여 응용 프로그램에서 이미지를 포함 하는 방법을 보여 주는이 예제는 <xref:System.Windows.Controls.Image> 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="4a144-103">This example shows how to include images in an application by using the <xref:System.Windows.Controls.Image> element.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4a144-104">예제</span><span class="sxs-lookup"><span data-stu-id="4a144-104">Example</span></span>  
 <span data-ttu-id="4a144-105">다음 예제에서는 200픽셀 너비의 이미지를 렌더링하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="4a144-105">The following example shows how to render an image 200 pixels wide.</span></span> <span data-ttu-id="4a144-106">이 [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] 예제에서는 특성 구문과 속성 태그 구문을 모두 사용하여 이미지를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="4a144-106">In this [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] example, both attribute syntax and property tag syntax are used to define the image.</span></span> <span data-ttu-id="4a144-107">특성 구문 및 속성 구문에 대한 자세한 내용은 [종속성 속성 개요](../advanced/dependency-properties-overview.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="4a144-107">For more information on attribute syntax and property syntax, see [Dependency Properties Overview](../advanced/dependency-properties-overview.md).</span></span> <span data-ttu-id="4a144-108"><xref:System.Windows.Media.Imaging.BitmapImage> 이미지의 원본 데이터를 정의 하는 데 사용 되 고 속성 태그 구문 예제에 대 한 명시적으로 정의 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4a144-108">A <xref:System.Windows.Media.Imaging.BitmapImage> is used to define the image's source data and is explicitly defined for the property tag syntax example.</span></span> <span data-ttu-id="4a144-109">또한 합니다 <xref:System.Windows.Media.Imaging.BitmapImage.DecodePixelWidth%2A> 의 <xref:System.Windows.Media.Imaging.BitmapImage> 동일한 너비로 설정 됩니다는 <xref:System.Windows.FrameworkElement.Width%2A> 의 <xref:System.Windows.Controls.Image>.</span><span class="sxs-lookup"><span data-stu-id="4a144-109">In addition, the <xref:System.Windows.Media.Imaging.BitmapImage.DecodePixelWidth%2A> of the <xref:System.Windows.Media.Imaging.BitmapImage> is set to the same width as the <xref:System.Windows.FrameworkElement.Width%2A> of the <xref:System.Windows.Controls.Image>.</span></span> <span data-ttu-id="4a144-110">이렇게 하는 이유는 이미지 렌더링에 사용되는 메모리 양을 최소화하기 위해서입니다.</span><span class="sxs-lookup"><span data-stu-id="4a144-110">This is done to ensure that the minimum amount of memory is used rendering the image.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="4a144-111">일반적으로 렌더링된 된 이미지의 크기를 지정 하려는 경우 지정 된 <xref:System.Windows.FrameworkElement.Width%2A> 또는 <xref:System.Windows.FrameworkElement.Height%2A> 하나만 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4a144-111">In general, if you want to specify the size of a rendered image, specify only the <xref:System.Windows.FrameworkElement.Width%2A> or the <xref:System.Windows.FrameworkElement.Height%2A> but not both.</span></span> <span data-ttu-id="4a144-112">둘 중 하나만 지정하면 이미지의 가로 세로 비율이 유지됩니다.</span><span class="sxs-lookup"><span data-stu-id="4a144-112">If you only specify one, the image's aspect ratio is preserved.</span></span> <span data-ttu-id="4a144-113">그렇지 않으면 이미지가 예기치 않게 늘어나거나 휘어질 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4a144-113">Otherwise, the image may unexpectedly appear stretched or warped.</span></span> <span data-ttu-id="4a144-114">이미지를 제어 하려면 늘어나는 동작을 사용 합니다 <xref:System.Windows.Controls.Image.Stretch%2A> 및 <xref:System.Windows.Controls.Image.StretchDirection%2A> 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="4a144-114">To control the image's stretching behavior, use the <xref:System.Windows.Controls.Image.Stretch%2A> and <xref:System.Windows.Controls.Image.StretchDirection%2A> properties.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="4a144-115">사용 하 여 이미지의 크기를 지정 하면 <xref:System.Windows.FrameworkElement.Width%2A> 또는 <xref:System.Windows.FrameworkElement.Height%2A>, 하거나 설정 해야 <xref:System.Windows.Media.Imaging.BitmapImage.DecodePixelWidth%2A> 또는 <xref:System.Windows.Media.Imaging.BitmapImage.DecodePixelHeight%2A> 각각 같은 크기로를 합니다.</span><span class="sxs-lookup"><span data-stu-id="4a144-115">When you specify the size of an image with either <xref:System.Windows.FrameworkElement.Width%2A> or <xref:System.Windows.FrameworkElement.Height%2A>, you should also set either <xref:System.Windows.Media.Imaging.BitmapImage.DecodePixelWidth%2A> or <xref:System.Windows.Media.Imaging.BitmapImage.DecodePixelHeight%2A> to the same respective size.</span></span>  
  
 <span data-ttu-id="4a144-116"><xref:System.Windows.Controls.Image.Stretch%2A> 속성 이미지 원본은 image 요소를 채우도록 확장 하는 방법을 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="4a144-116">The <xref:System.Windows.Controls.Image.Stretch%2A> property determines how the image source is stretched to fill the image element.</span></span> <span data-ttu-id="4a144-117">자세한 내용은 <xref:System.Windows.Media.Stretch> 열거형을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="4a144-117">For more information, see the <xref:System.Windows.Media.Stretch> enumeration.</span></span>  
  
 [!code-xaml[ImageElementExample_snip#ImageSimpleExampleInlineMarkup](~/samples/snippets/csharp/VS_Snippets_Wpf/ImageElementExample_snip/CSharp/ImageSimpleExample.xaml#imagesimpleexampleinlinemarkup)]  
  
## <a name="example"></a><span data-ttu-id="4a144-118">예제</span><span class="sxs-lookup"><span data-stu-id="4a144-118">Example</span></span>  
 <span data-ttu-id="4a144-119">다음 예제에서는 코드를 사용하여 200픽셀 너비의 이미지를 렌더링하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="4a144-119">The following example shows how to render an image 200 pixels wide using code.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="4a144-120">설정 <xref:System.Windows.Media.Imaging.BitmapImage> 속성 내에서 수행 해야 합니다는 <xref:System.Windows.Media.Imaging.BitmapImage.BeginInit%2A> 고 <xref:System.Windows.Media.Imaging.BitmapImage.EndInit%2A> 블록입니다.</span><span class="sxs-lookup"><span data-stu-id="4a144-120">Setting <xref:System.Windows.Media.Imaging.BitmapImage> properties must be done within a <xref:System.Windows.Media.Imaging.BitmapImage.BeginInit%2A> and <xref:System.Windows.Media.Imaging.BitmapImage.EndInit%2A> block.</span></span>  
  
 [!code-csharp[ImageElementExample_snip#ImageSimpleExampleInlineCode1](~/samples/snippets/csharp/VS_Snippets_Wpf/ImageElementExample_snip/CSharp/ImageSimpleExample.xaml.cs#imagesimpleexampleinlinecode1)]
 [!code-vb[ImageElementExample_snip#ImageSimpleExampleInlineCode1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ImageElementExample_snip/VB/ImageSimpleExample.xaml.vb#imagesimpleexampleinlinecode1)]  
  
## <a name="see-also"></a><span data-ttu-id="4a144-121">참고자료</span><span class="sxs-lookup"><span data-stu-id="4a144-121">See also</span></span>

- [<span data-ttu-id="4a144-122">이미징 개요</span><span class="sxs-lookup"><span data-stu-id="4a144-122">Imaging Overview</span></span>](../graphics-multimedia/imaging-overview.md)
