---
title: '방법: ThicknessConverter 개체 사용'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- border thickness [WPF]
- ThicknessConverter objects [WPF]
ms.assetid: 52682194-d7fd-499c-8005-73fcc84e7b2c
ms.openlocfilehash: 653137c0707c2b7ee51f6bdac6bb2501f1845e1a
ms.sourcegitcommit: 8f95d3a37e591963ebbb9af6e90686fd5f3b8707
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/23/2019
ms.locfileid: "56747345"
---
# <a name="how-to-use-a-thicknessconverter-object"></a><span data-ttu-id="52e1a-102">방법: ThicknessConverter 개체 사용</span><span class="sxs-lookup"><span data-stu-id="52e1a-102">How to: Use a ThicknessConverter Object</span></span>
## <a name="example"></a><span data-ttu-id="52e1a-103">예제</span><span class="sxs-lookup"><span data-stu-id="52e1a-103">Example</span></span>  
 <span data-ttu-id="52e1a-104">인스턴스를 만드는 방법을 보여 주는이 예제 <xref:System.Windows.ThicknessConverter> 테두리의 두께 변경 하려면 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="52e1a-104">This example shows how to create an instance of <xref:System.Windows.ThicknessConverter> and use it to change the thickness of a border.</span></span>  
  
 <span data-ttu-id="52e1a-105">이 예제에서는 라는 사용자 지정 메서드를 정의 `changeThickness`;이 메서드는 먼저 내용의 변환를 <xref:System.Windows.Controls.ListBoxItem>별도의 정의 된 대로 [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] 인스턴스에 파일을 <xref:System.Windows.Thickness>, 나중에 콘텐츠를 변환 하 고는 <xref:System.String>합니다.</span><span class="sxs-lookup"><span data-stu-id="52e1a-105">The example defines a custom method called `changeThickness`; this method first converts the contents of a <xref:System.Windows.Controls.ListBoxItem>, as defined in a separate [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] file, to an instance of <xref:System.Windows.Thickness>, and later converts the content into a <xref:System.String>.</span></span> <span data-ttu-id="52e1a-106">이 메서드는 전달를 <xref:System.Windows.Controls.ListBoxItem> 에 <xref:System.Windows.ThicknessConverter> 변환 하는 개체를 <xref:System.Windows.Controls.ContentControl.Content%2A> 의 <xref:System.Windows.Controls.ListBoxItem> 인스턴스에 <xref:System.Windows.Thickness>합니다.</span><span class="sxs-lookup"><span data-stu-id="52e1a-106">This method passes the <xref:System.Windows.Controls.ListBoxItem> to a <xref:System.Windows.ThicknessConverter> object, which converts the <xref:System.Windows.Controls.ContentControl.Content%2A> of a <xref:System.Windows.Controls.ListBoxItem> to an instance of <xref:System.Windows.Thickness>.</span></span> <span data-ttu-id="52e1a-107">이 값은 다음 값으로 다시 전달 합니다 <xref:System.Windows.Controls.Border.BorderThickness%2A> 의 속성을 <xref:System.Windows.Controls.Border>.</span><span class="sxs-lookup"><span data-stu-id="52e1a-107">This value is then passed back as the value of the <xref:System.Windows.Controls.Border.BorderThickness%2A> property of the <xref:System.Windows.Controls.Border>.</span></span>  
  
 <span data-ttu-id="52e1a-108">이 예제에서는 실행되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="52e1a-108">This example does not run.</span></span>  
  
 [!code-csharp[ThicknessConverter#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ThicknessConverter/CSharp/Window1.xaml.cs#1)]
 [!code-vb[ThicknessConverter#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ThicknessConverter/VisualBasic/Window1.xaml.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="52e1a-109">참고자료</span><span class="sxs-lookup"><span data-stu-id="52e1a-109">See also</span></span>
- <xref:System.Windows.Thickness>
- <xref:System.Windows.ThicknessConverter>
- <xref:System.Windows.Controls.Border>
- <span data-ttu-id="52e1a-110">[방법: Margin 속성 변경](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms750561(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="52e1a-110">[How to: Change the Margin Property](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms750561(v=vs.90))</span></span>
- <span data-ttu-id="52e1a-111">[방법: ListBoxItem을 새 데이터 형식으로 변환](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms749147(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="52e1a-111">[How to: Convert a ListBoxItem to a new Data Type](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms749147(v=vs.90))</span></span>
- [<span data-ttu-id="52e1a-112">패널 개요</span><span class="sxs-lookup"><span data-stu-id="52e1a-112">Panels Overview</span></span>](../../../../docs/framework/wpf/controls/panels-overview.md)
