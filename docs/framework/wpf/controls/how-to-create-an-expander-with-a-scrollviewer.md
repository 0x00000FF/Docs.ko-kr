---
title: '방법: ScrollViewer가 있는 Expander 만들기'
ms.date: 03/30/2017
helpviewer_keywords:
- controls [WPF], Expander
- ScrollViewer control [WPF], with Expander control
- Expander control [WPF], creating
- controls [WPF], ScrollViewer
ms.assetid: 2ad124d2-2406-4157-aaf2-64e067298f01
ms.openlocfilehash: 8d21c7ec0172dca23f218a0d710c3976872f162c
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54681965"
---
# <a name="how-to-create-an-expander-with-a-scrollviewer"></a><span data-ttu-id="0369a-102">방법: ScrollViewer가 있는 Expander 만들기</span><span class="sxs-lookup"><span data-stu-id="0369a-102">How to: Create an Expander with a ScrollViewer</span></span>
<span data-ttu-id="0369a-103">만드는 방법을 보여 주는이 예제는 <xref:System.Windows.Controls.Expander> 이미지 및 텍스트와 같은 복잡 한 콘텐츠를 포함 하는 컨트롤입니다.</span><span class="sxs-lookup"><span data-stu-id="0369a-103">This example shows how to create an <xref:System.Windows.Controls.Expander> control that contains complex content, such as an image and text.</span></span> <span data-ttu-id="0369a-104">예제의 콘텐츠도 포함 합니다 <xref:System.Windows.Controls.Expander> 에 <xref:System.Windows.Controls.ScrollViewer> 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="0369a-104">The example also encloses the content of the <xref:System.Windows.Controls.Expander> in a <xref:System.Windows.Controls.ScrollViewer> control.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0369a-105">예제</span><span class="sxs-lookup"><span data-stu-id="0369a-105">Example</span></span>  
 <span data-ttu-id="0369a-106">다음 예제에서는 만드는 방법을 보여 줍니다는 <xref:System.Windows.Controls.Expander>합니다.</span><span class="sxs-lookup"><span data-stu-id="0369a-106">The following example shows how to create an <xref:System.Windows.Controls.Expander>.</span></span> <span data-ttu-id="0369a-107">이 예제에서는 사용을 <xref:System.Windows.Controls.Primitives.BulletDecorator> 정의 하기 위해 이미지 및 텍스트를 포함 하는 컨트롤은 <xref:System.Windows.Controls.HeaderedContentControl.Header%2A>합니다.</span><span class="sxs-lookup"><span data-stu-id="0369a-107">The example uses a <xref:System.Windows.Controls.Primitives.BulletDecorator> control, which contains an image and text, in order to define the <xref:System.Windows.Controls.HeaderedContentControl.Header%2A>.</span></span> <span data-ttu-id="0369a-108"><xref:System.Windows.Controls.ScrollViewer> 컨트롤은 확장 된 콘텐츠를 스크롤 하는 방법을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="0369a-108">A <xref:System.Windows.Controls.ScrollViewer> control provides a method for scrolling the expanded content.</span></span>  
  
 <span data-ttu-id="0369a-109">설정 하는 예제는 합니다 <xref:System.Windows.FrameworkElement.Height%2A> 속성에는 <xref:System.Windows.Controls.ScrollViewer> 대신 콘텐츠.</span><span class="sxs-lookup"><span data-stu-id="0369a-109">Note that the example sets the <xref:System.Windows.FrameworkElement.Height%2A> property on the <xref:System.Windows.Controls.ScrollViewer> instead of on the content.</span></span> <span data-ttu-id="0369a-110">경우는 <xref:System.Windows.FrameworkElement.Height%2A> 콘텐츠를 설정 합니다 <xref:System.Windows.Controls.ScrollViewer> 내용을 스크롤 하는 사용자를 허용 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0369a-110">If the <xref:System.Windows.FrameworkElement.Height%2A> is set on the content, the <xref:System.Windows.Controls.ScrollViewer> does not allow the user to scroll the content.</span></span> <span data-ttu-id="0369a-111"><xref:System.Windows.FrameworkElement.Width%2A> 속성이 설정 되어 합니다 <xref:System.Windows.Controls.Expander> 컨트롤과이 설정을 적용할를 <xref:System.Windows.Controls.HeaderedContentControl.Header%2A> 및 확장 된 콘텐츠입니다.</span><span class="sxs-lookup"><span data-stu-id="0369a-111">The <xref:System.Windows.FrameworkElement.Width%2A> property is set on the <xref:System.Windows.Controls.Expander> control and this setting applies to the <xref:System.Windows.Controls.HeaderedContentControl.Header%2A> and the expanded content.</span></span>  
  
 [!code-xaml[ExpanderRichContent#CreateExpander](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpanderRichContent/CSharp/Window1.xaml#createexpander)]  
  
 [!code-csharp[ExpanderRichContent#CreateExpanderCode](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpanderRichContent/CSharp/Window1.xaml.cs#createexpandercode)]  
  
## <a name="see-also"></a><span data-ttu-id="0369a-112">참고자료</span><span class="sxs-lookup"><span data-stu-id="0369a-112">See also</span></span>
- <xref:System.Windows.Controls.Expander>
- [<span data-ttu-id="0369a-113">Expander 개요</span><span class="sxs-lookup"><span data-stu-id="0369a-113">Expander Overview</span></span>](../../../../docs/framework/wpf/controls/expander-overview.md)
- [<span data-ttu-id="0369a-114">방법 항목</span><span class="sxs-lookup"><span data-stu-id="0369a-114">How-to Topics</span></span>](../../../../docs/framework/wpf/controls/expander-how-to-topics.md)
