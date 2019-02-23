---
title: '방법: GruopBox 템플릿 정의'
ms.date: 03/30/2017
helpviewer_keywords:
- controls [WPF], GroupBox
- GroupBox control [WPF], creating templates
ms.assetid: 85a4d1a7-4753-4f4a-b26d-14fa10c1ddb5
ms.openlocfilehash: 6294a52d5914b52d191b564330f904e6a865c283
ms.sourcegitcommit: 8f95d3a37e591963ebbb9af6e90686fd5f3b8707
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/23/2019
ms.locfileid: "56745200"
---
# <a name="how-to-define-a-groupbox-template"></a><span data-ttu-id="3a05c-102">방법: GruopBox 템플릿 정의</span><span class="sxs-lookup"><span data-stu-id="3a05c-102">How to: Define a GroupBox Template</span></span>
<span data-ttu-id="3a05c-103">에 대 한 템플릿을 만드는 방법을 보여 주는이 예제는 <xref:System.Windows.Controls.GroupBox> 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="3a05c-103">This example shows how to create a template for a <xref:System.Windows.Controls.GroupBox> control.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3a05c-104">예제</span><span class="sxs-lookup"><span data-stu-id="3a05c-104">Example</span></span>  
 <span data-ttu-id="3a05c-105">다음 예제에서는 정의 <xref:System.Windows.Controls.GroupBox> 컨트롤 템플릿을 사용 하 여를 <xref:System.Windows.Controls.Grid> 레이아웃에 대 한 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="3a05c-105">The following example defines a <xref:System.Windows.Controls.GroupBox> control template by using a <xref:System.Windows.Controls.Grid> control for layout.</span></span> <span data-ttu-id="3a05c-106">템플릿을 사용 하는 <xref:System.Windows.Controls.BorderGapMaskConverter> 경계를 정의 하는 <xref:System.Windows.Controls.GroupBox> 테두리를 가리지 않습니다 있도록는 <xref:System.Windows.Controls.HeaderedContentControl.Header%2A> 콘텐츠.</span><span class="sxs-lookup"><span data-stu-id="3a05c-106">The template uses a <xref:System.Windows.Controls.BorderGapMaskConverter> to define the border of the <xref:System.Windows.Controls.GroupBox> so that the border does not obscure the <xref:System.Windows.Controls.HeaderedContentControl.Header%2A> content.</span></span>  
  
 [!code-xaml[GroupBoxSnippet#GroupBoxTemplate](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GroupBoxSnippet/CS/Window1.xaml#groupboxtemplate)]  
  
## <a name="see-also"></a><span data-ttu-id="3a05c-107">참고자료</span><span class="sxs-lookup"><span data-stu-id="3a05c-107">See also</span></span>
- <xref:System.Windows.Controls.GroupBox>
- <span data-ttu-id="3a05c-108">[방법: GroupBox 만들기](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms748321(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="3a05c-108">[How to: Create a GroupBox](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms748321(v=vs.90))</span></span>
