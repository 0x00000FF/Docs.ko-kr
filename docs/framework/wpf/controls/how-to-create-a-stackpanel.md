---
title: "방법: StackPanel 만들기"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: StackPanel control [WPF], creating
ms.assetid: e7ce65cb-720a-4bb6-95b6-286b74488a58
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 9226ac10e4f221cc381b7c59179b2667e20aa757
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-create-a-stackpanel"></a><span data-ttu-id="3841b-102">방법: StackPanel 만들기</span><span class="sxs-lookup"><span data-stu-id="3841b-102">How to: Create a StackPanel</span></span>
<span data-ttu-id="3841b-103">만드는 방법을 보여 주는이 예제는 <xref:System.Windows.Controls.StackPanel>합니다.</span><span class="sxs-lookup"><span data-stu-id="3841b-103">This example shows how to create a <xref:System.Windows.Controls.StackPanel>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3841b-104">예</span><span class="sxs-lookup"><span data-stu-id="3841b-104">Example</span></span>  
 <span data-ttu-id="3841b-105">A <xref:System.Windows.Controls.StackPanel> 를 지정 된 방향에서 요소 쌓을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3841b-105">A <xref:System.Windows.Controls.StackPanel> allows you to stack elements in a specified direction.</span></span> <span data-ttu-id="3841b-106">에 정의 된 속성을 사용 하 여 <xref:System.Windows.Controls.StackPanel>, 콘텐츠 이동 둘 다 수직으로 기본 설정인 또는 가로로 합니다.</span><span class="sxs-lookup"><span data-stu-id="3841b-106">By using properties that are defined on <xref:System.Windows.Controls.StackPanel>, content can flow both vertically, which is the default setting, or horizontally.</span></span>  
  
 <span data-ttu-id="3841b-107">5 개는 다음 예제에서는 세로로 쌓는 <xref:System.Windows.Controls.TextBlock> 가 서로 제어 <xref:System.Windows.Controls.Border> 및 <xref:System.Windows.Controls.Border.Background%2A>를 사용 하 여 <xref:System.Windows.Controls.StackPanel>합니다.</span><span class="sxs-lookup"><span data-stu-id="3841b-107">The following example vertically stacks five <xref:System.Windows.Controls.TextBlock> controls, each with a different <xref:System.Windows.Controls.Border> and <xref:System.Windows.Controls.Border.Background%2A>, by using <xref:System.Windows.Controls.StackPanel>.</span></span> <span data-ttu-id="3841b-108">하지만 지정 되지 않은 자식 요소 <xref:System.Windows.FrameworkElement.Width%2A> 부모 창에 맞게 늘이기 있으며 자식 요소는 지정 된 <xref:System.Windows.FrameworkElement.Width%2A>, 창 내에서 가운데 맞춤 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3841b-108">The child elements that have no specified <xref:System.Windows.FrameworkElement.Width%2A> stretch to fill the parent window; however, the child elements that have a specified <xref:System.Windows.FrameworkElement.Width%2A>, are centered within the window.</span></span>  
  
 <span data-ttu-id="3841b-109">기본 스택 방향을 <xref:System.Windows.Controls.StackPanel> 는 세로입니다.</span><span class="sxs-lookup"><span data-stu-id="3841b-109">The default stack direction in a <xref:System.Windows.Controls.StackPanel> is vertical.</span></span> <span data-ttu-id="3841b-110">콘텐츠 흐름을 제어 하는 <xref:System.Windows.Controls.StackPanel>를 사용 하 여는 <xref:System.Windows.Controls.StackPanel.Orientation%2A> 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="3841b-110">To control content flow in a <xref:System.Windows.Controls.StackPanel>, use the <xref:System.Windows.Controls.StackPanel.Orientation%2A> property.</span></span> <span data-ttu-id="3841b-111">사용 하 여 가로 맞춤을 제어할 수 있습니다는 <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="3841b-111">You can control horizontal alignment by using the <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> property.</span></span>  
  
```xaml  
<Page xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation" WindowTitle="StackPanel Sample">  
  <StackPanel>  
    <Border Background="SkyBlue" BorderBrush="Black" BorderThickness="1">  
      <TextBlock Foreground="Black" FontSize="12">Stacked Item #1</TextBlock>  
    </Border>  
    <Border Width="400" Background="CadetBlue" BorderBrush="Black" BorderThickness="1">  
      <TextBlock Foreground="Black" FontSize="14">Stacked Item #2</TextBlock>  
    </Border>  
    <Border Background="LightGoldenRodYellow" BorderBrush="Black" BorderThickness="1">  
      <TextBlock Foreground="Black" FontSize="16">Stacked Item #3</TextBlock>  
    </Border>  
    <Border Width="200" Background="PaleGreen" BorderBrush="Black" BorderThickness="1">  
      <TextBlock Foreground="Black" FontSize="18">Stacked Item #4</TextBlock>  
    </Border>  
    <Border Background="White" BorderBrush="Black" BorderThickness="1">  
      <TextBlock Foreground="Black" FontSize="20">Stacked Item #5</TextBlock>  
    </Border>  
  </StackPanel>  
</Page>  
```  
  
## <a name="see-also"></a><span data-ttu-id="3841b-112">참고 항목</span><span class="sxs-lookup"><span data-stu-id="3841b-112">See Also</span></span>  
 <xref:System.Windows.Controls.StackPanel>  
 [<span data-ttu-id="3841b-113">패널 개요</span><span class="sxs-lookup"><span data-stu-id="3841b-113">Panels Overview</span></span>](../../../../docs/framework/wpf/controls/panels-overview.md)  
 [<span data-ttu-id="3841b-114">방법 항목</span><span class="sxs-lookup"><span data-stu-id="3841b-114">How-to Topics</span></span>](../../../../docs/framework/wpf/controls/stackpanel-how-to-topics.md)
