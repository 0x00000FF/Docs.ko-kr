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
ms.openlocfilehash: d7aa2e0e9bd33dfcd68bd19b5084fa1666232a5c
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54530803"
---
# <a name="how-to-use-the-image-element"></a>방법: Image 요소 사용
사용 하 여 응용 프로그램에서 이미지를 포함 하는 방법을 보여 주는이 예제는 <xref:System.Windows.Controls.Image> 요소입니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 200픽셀 너비의 이미지를 렌더링하는 방법을 보여 줍니다. 이 [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] 예제에서는 특성 구문과 속성 태그 구문을 모두 사용하여 이미지를 정의합니다. 특성 구문 및 속성 구문에 대한 자세한 내용은 [종속성 속성 개요](../../../../docs/framework/wpf/advanced/dependency-properties-overview.md)를 참조하세요. <xref:System.Windows.Media.Imaging.BitmapImage> 이미지의 원본 데이터를 정의 하는 데 사용 되 고 속성 태그 구문 예제에 대 한 명시적으로 정의 됩니다. 또한 합니다 <xref:System.Windows.Media.Imaging.BitmapImage.DecodePixelWidth%2A> 의 <xref:System.Windows.Media.Imaging.BitmapImage> 동일한 너비로 설정 됩니다는 <xref:System.Windows.FrameworkElement.Width%2A> 의 <xref:System.Windows.Controls.Image>. 이렇게 하는 이유는 이미지 렌더링에 사용되는 메모리 양을 최소화하기 위해서입니다.  
  
> [!NOTE]
>  일반적으로 렌더링된 된 이미지의 크기를 지정 하려는 경우 지정 된 <xref:System.Windows.FrameworkElement.Width%2A> 또는 <xref:System.Windows.FrameworkElement.Height%2A> 하나만 있습니다. 둘 중 하나만 지정하면 이미지의 가로 세로 비율이 유지됩니다. 그렇지 않으면 이미지가 예기치 않게 늘어나거나 휘어질 수 있습니다. 이미지를 제어 하려면 늘어나는 동작을 사용 합니다 <xref:System.Windows.Controls.Image.Stretch%2A> 및 <xref:System.Windows.Controls.Image.StretchDirection%2A> 속성입니다.  
  
> [!NOTE]
>  사용 하 여 이미지의 크기를 지정 하면 <xref:System.Windows.FrameworkElement.Width%2A> 또는 <xref:System.Windows.FrameworkElement.Height%2A>, 하거나 설정 해야 <xref:System.Windows.Media.Imaging.BitmapImage.DecodePixelWidth%2A> 또는 <xref:System.Windows.Media.Imaging.BitmapImage.DecodePixelHeight%2A> 각각 같은 크기로를 합니다.  
  
 <xref:System.Windows.Controls.Image.Stretch%2A> 속성 이미지 원본은 image 요소를 채우도록 확장 하는 방법을 결정 합니다. 자세한 내용은 <xref:System.Windows.Media.Stretch> 열거형을 참조하세요.  
  
 [!code-xaml[ImageElementExample_snip#ImageSimpleExampleInlineMarkup](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ImageElementExample_snip/CSharp/ImageSimpleExample.xaml#imagesimpleexampleinlinemarkup)]  
  
## <a name="example"></a>예제  
 다음 예제에서는 코드를 사용하여 200픽셀 너비의 이미지를 렌더링하는 방법을 보여 줍니다.  
  
> [!NOTE]
>  설정 <xref:System.Windows.Media.Imaging.BitmapImage> 속성 내에서 수행 해야 합니다는 <xref:System.Windows.Media.Imaging.BitmapImage.BeginInit%2A> 고 <xref:System.Windows.Media.Imaging.BitmapImage.EndInit%2A> 블록입니다.  
  
 [!code-csharp[ImageElementExample_snip#ImageSimpleExampleInlineCode1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ImageElementExample_snip/CSharp/ImageSimpleExample.xaml.cs#imagesimpleexampleinlinecode1)]
 [!code-vb[ImageElementExample_snip#ImageSimpleExampleInlineCode1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ImageElementExample_snip/VB/ImageSimpleExample.xaml.vb#imagesimpleexampleinlinecode1)]  
  
## <a name="see-also"></a>참고자료
- [이미징 개요](../../../../docs/framework/wpf/graphics-multimedia/imaging-overview.md)
