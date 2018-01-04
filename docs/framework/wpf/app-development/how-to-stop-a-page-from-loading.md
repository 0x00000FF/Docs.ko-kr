---
title: "방법: 페이지 로드를 중지 합니다."
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
- pages [WPF], stopping from loading
- methods [WPF], Stoploading
- events [WPF], NavigationStopped
- NavigationStopped properties [WPF]
- stopping pages from loading [WPF]
- loading [WPF], stopping
ms.assetid: e2b695b0-517e-462c-8ccf-90cc8d6ba864
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 6109a45f885a6a94a5785329d10bce52a0090802
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-stop-a-page-from-loading"></a>방법: 페이지 로드를 중지 합니다.
호출 하는 방법을 보여 주는이 예제는 <xref:System.Windows.Navigation.NavigationWindow.StopLoading%2A> 메서드 다운로드를 마치기 전에 콘텐츠를 탐색을 중지할 수 있습니다.  
  
## <a name="example"></a>예  
 <xref:System.Windows.Navigation.NavigationWindow.StopLoading%2A>요청 된 콘텐츠의 다운로드를 중지 하 고 발생 된 <xref:System.Windows.Navigation.NavigationWindow.NavigationStopped> 이벤트를 발생 합니다.  
  
 [!code-csharp[HOWTONavigationSnippets#NavigateStopLoadingCODE](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HOWTONavigationSnippets/CSharp/MainWindow.xaml.cs#navigatestoploadingcode)]
 [!code-vb[HOWTONavigationSnippets#NavigateStopLoadingCODE](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HOWTONavigationSnippets/visualbasic/mainwindow.xaml.vb#navigatestoploadingcode)]
