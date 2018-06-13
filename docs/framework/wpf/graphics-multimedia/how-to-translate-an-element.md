---
title: '방법: 요소 변환'
ms.date: 03/30/2017
helpviewer_keywords:
- graphics [WPF], translations
ms.assetid: 461c8273-15df-42f6-8672-89ba22887cc0
ms.openlocfilehash: 0089f294c54662d1ea4929ec25c08464072cbdde
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33561945"
---
# <a name="how-to-translate-an-element"></a><span data-ttu-id="1bb75-102">방법: 요소 변환</span><span class="sxs-lookup"><span data-stu-id="1bb75-102">How to: Translate an Element</span></span>
<span data-ttu-id="1bb75-103">이 예제에서는 변환 (이동) 하는 요소를 사용 하 여는 <xref:System.Windows.Media.TranslateTransform>합니다.</span><span class="sxs-lookup"><span data-stu-id="1bb75-103">This example shows how to translate (move) an element by using a <xref:System.Windows.Media.TranslateTransform>.</span></span>  
  
 <span data-ttu-id="1bb75-104"><xref:System.Windows.Media.TranslateTransform> 클래스 절대 위치 지정을 지원 하지 않는 패널 내에서 요소를 이동 하는 데 특히 유용 합니다.</span><span class="sxs-lookup"><span data-stu-id="1bb75-104">The <xref:System.Windows.Media.TranslateTransform> class is especially useful for moving elements inside panels that do not support absolute positioning.</span></span> <span data-ttu-id="1bb75-105">예를 들어 적용 하 여는 <xref:System.Windows.Media.TranslateTransform> 에 <xref:System.Windows.UIElement.RenderTransform%2A> 요소의 속성 내에서 요소를 이동할 수 있습니다는 <xref:System.Windows.Controls.StackPanel> 또는 <xref:System.Windows.Controls.DockPanel>합니다.</span><span class="sxs-lookup"><span data-stu-id="1bb75-105">For example, by applying a <xref:System.Windows.Media.TranslateTransform> to the <xref:System.Windows.UIElement.RenderTransform%2A> property of an element, you can move an element within a <xref:System.Windows.Controls.StackPanel> or <xref:System.Windows.Controls.DockPanel>.</span></span>  
  
 <span data-ttu-id="1bb75-106">사용 하 여는 <xref:System.Windows.Media.TranslateTransform.X%2A> 의 속성은 <xref:System.Windows.Media.TranslateTransform> 픽셀 x 축 따라 요소를 이동 하려면 시간을 지정 하려면.</span><span class="sxs-lookup"><span data-stu-id="1bb75-106">Use the <xref:System.Windows.Media.TranslateTransform.X%2A> property of the <xref:System.Windows.Media.TranslateTransform> to specify the amount, in pixels, to move the element along the x-axis.</span></span> <span data-ttu-id="1bb75-107">사용 하 여는 <xref:System.Windows.Media.TranslateTransform.Y%2A> 속성을 시도 하는 양 y 축 따라 요소를 이동 하려면를 픽셀 단위로 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="1bb75-107">Use the <xref:System.Windows.Media.TranslateTransform.Y%2A> property to specify the amount, in pixels, to move the element along the y-axis.</span></span> <span data-ttu-id="1bb75-108">마지막으로 적용 된 <xref:System.Windows.Media.TranslateTransform> 에 <xref:System.Windows.UIElement.RenderTransform%2A> 요소의 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="1bb75-108">Finally, apply the <xref:System.Windows.Media.TranslateTransform> to the <xref:System.Windows.UIElement.RenderTransform%2A> property of the element.</span></span>  
  
 <span data-ttu-id="1bb75-109">다음 예제에서는 한 <xref:System.Windows.Media.TranslateTransform> 요소 50 픽셀을 오른쪽 테이블과 50 픽셀 아래로 이동 하려면.</span><span class="sxs-lookup"><span data-stu-id="1bb75-109">The following example uses a <xref:System.Windows.Media.TranslateTransform> to move an element 50 pixels to the right and 50 pixels down.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1bb75-110">예제</span><span class="sxs-lookup"><span data-stu-id="1bb75-110">Example</span></span>  
 [!code-xaml[transformsSample#53](../../../../samples/snippets/csharp/VS_Snippets_Wpf/transformsSample/CS/TranslateTransformExample.xaml#53)]  
  
 <span data-ttu-id="1bb75-111">전체 샘플을 보려면 [2차원 변환 샘플](http://go.microsoft.com/fwlink/?LinkID=158252)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="1bb75-111">For the complete sample, see [2-D Transforms Sample](http://go.microsoft.com/fwlink/?LinkID=158252).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1bb75-112">참고 항목</span><span class="sxs-lookup"><span data-stu-id="1bb75-112">See Also</span></span>  
 [<span data-ttu-id="1bb75-113">Transform 개요</span><span class="sxs-lookup"><span data-stu-id="1bb75-113">Transforms Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/transforms-overview.md)
