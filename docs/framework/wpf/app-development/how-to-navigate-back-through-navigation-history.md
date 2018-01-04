---
title: "방법: 탐색 기록을 통해 뒤로 탐색"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- history [WPF], navigating back
- navigation [WPF], through navigation history (back)
ms.assetid: 9343234b-d864-441d-b8a7-d895cba80a87
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: e3bfc809dbe76c17859cb3fcd83f8a293a24b308
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-navigate-back-through-navigation-history"></a><span data-ttu-id="94ac5-102">방법: 탐색 기록을 통해 뒤로 탐색</span><span class="sxs-lookup"><span data-stu-id="94ac5-102">How to: Navigate Back Through Navigation History</span></span>
<span data-ttu-id="94ac5-103">이 예제에는 탐색 기록 뒤에 항목을 탐색 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="94ac5-103">This example illustrates how to navigate to entries in back navigation history.</span></span>  
  
## <a name="example"></a><span data-ttu-id="94ac5-104">예</span><span class="sxs-lookup"><span data-stu-id="94ac5-104">Example</span></span>  
 <span data-ttu-id="94ac5-105">에 호스트 된 콘텐츠에서 실행 되는 코드는 <xref:System.Windows.Navigation.NavigationWindow>, <xref:System.Windows.Controls.Frame> 사용 <xref:System.Windows.Navigation.NavigationService>, 또는 [!INCLUDE[TLA#tla_iegeneric](../../../../includes/tlasharptla-iegeneric-md.md)] 탐색 기록, 한 번에 하나의 항목을 통해 다시 이동할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="94ac5-105">Code that is running from content that is hosted in a <xref:System.Windows.Navigation.NavigationWindow>, <xref:System.Windows.Controls.Frame> use <xref:System.Windows.Navigation.NavigationService>, or [!INCLUDE[TLA#tla_iegeneric](../../../../includes/tlasharptla-iegeneric-md.md)] can navigate back through navigation history, one entry at a time.</span></span>  
  
 <span data-ttu-id="94ac5-106">탐색 다시 하나의 항목 필요를 검사 하 여 뒤로 탐색 기록의 항목이 있는지 검사는 **CanGoBack** 속성을 호출 하 여 하나의 항목을 뒤로 탐색 하기 전에 **GoBack** 메서드입니다.</span><span class="sxs-lookup"><span data-stu-id="94ac5-106">Navigating back one entry requires first checking that there are entries in back navigation history, by inspecting the **CanGoBack** property, before navigating back one entry, by calling the **GoBack** method.</span></span> <span data-ttu-id="94ac5-107">이 다음 예에서 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="94ac5-107">This is illustrated in the following example:</span></span>  
  
 [!code-csharp[HOWTONavigationSnippets#NavigateBackCODE](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HOWTONavigationSnippets/CSharp/HomePage.xaml.cs#navigatebackcode)]
 [!code-vb[HOWTONavigationSnippets#NavigateBackCODE](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HOWTONavigationSnippets/visualbasic/homepage.xaml.vb#navigatebackcode)]  
  
 <span data-ttu-id="94ac5-108">**CanGoBack** 및 **GoBack** 구현 <xref:System.Windows.Navigation.NavigationWindow>, <xref:System.Windows.Controls.Frame>, 및 <xref:System.Windows.Navigation.NavigationService>합니다.</span><span class="sxs-lookup"><span data-stu-id="94ac5-108">**CanGoBack** and **GoBack** are implemented by <xref:System.Windows.Navigation.NavigationWindow>, <xref:System.Windows.Controls.Frame>, and <xref:System.Windows.Navigation.NavigationService>.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="94ac5-109">호출 하는 경우 **GoBack**를 뒤로 탐색 기록의 항목이 고는 <xref:System.InvalidOperationException> 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="94ac5-109">If you call **GoBack**, and there are no entries in back navigation history, an <xref:System.InvalidOperationException> is raised.</span></span>
