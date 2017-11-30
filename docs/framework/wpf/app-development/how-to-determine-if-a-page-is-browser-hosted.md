---
title: "방법: 브라우저에서 호스팅되는 페이지 인지 확인"
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
- hosted pages in browser [WPF]
- pages [WPF], hosted in browser
ms.assetid: 737e0f26-8371-49b4-9579-70879e51e1aa
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 1da46596bf48d9648830d20758647be753f128fc
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-determine-if-a-page-is-browser-hosted"></a><span data-ttu-id="07a65-102">방법: 브라우저에서 호스팅되는 페이지 인지 확인</span><span class="sxs-lookup"><span data-stu-id="07a65-102">How to: Determine If a Page is Browser Hosted</span></span>
<span data-ttu-id="07a65-103">확인 하는 방법을 보여 주는이 예제는 <xref:System.Windows.Controls.Page> 브라우저에서 호스트 됩니다.</span><span class="sxs-lookup"><span data-stu-id="07a65-103">This example demonstrates how to determine if a <xref:System.Windows.Controls.Page> is hosted in a browser.</span></span>  
  
## <a name="example"></a><span data-ttu-id="07a65-104">예제</span><span class="sxs-lookup"><span data-stu-id="07a65-104">Example</span></span>  
 <span data-ttu-id="07a65-105">A <xref:System.Windows.Controls.Page> 호스트를 알 수 없는 수 있으며이, 결과적으로, 여러 다른 유형의 비롯 한 호스트에 로드 될 수는 <xref:System.Windows.Controls.Frame>, 즉 <xref:System.Windows.Navigation.NavigationWindow>, 브라우저 등입니다.</span><span class="sxs-lookup"><span data-stu-id="07a65-105">A <xref:System.Windows.Controls.Page> can be host agnostic and, consequently, can be loaded into several different types of hosts, including a <xref:System.Windows.Controls.Frame>, a <xref:System.Windows.Navigation.NavigationWindow>, or a browser.</span></span> <span data-ttu-id="07a65-106">이 라이브러리 어셈블리가 하나 이상의 페이지를 포함 하 고 있는 참조 되는 여러 독립 실행형으로 탐색할 수 있을 때 발생할 수 있습니다 ([!INCLUDE[TLA#tla_xbap](../../../../includes/tlasharptla-xbap-md.md)]) 응용 프로그램을 호스트 합니다.</span><span class="sxs-lookup"><span data-stu-id="07a65-106">This can happen when you have a library assembly that contains one or more pages, and which is referenced by multiple standalone and browsable ([!INCLUDE[TLA#tla_xbap](../../../../includes/tlasharptla-xbap-md.md)]) host applications.</span></span>  
  
 <span data-ttu-id="07a65-107">다음 예제에서는 사용 하는 방법을 <xref:System.Windows.Interop.BrowserInteropHelper.IsBrowserHosted%2A?displayProperty=nameWithType> 여부를 확인 하는 <xref:System.Windows.Controls.Page> 브라우저에서 호스트 됩니다.</span><span class="sxs-lookup"><span data-stu-id="07a65-107">The following example demonstrates how to use <xref:System.Windows.Interop.BrowserInteropHelper.IsBrowserHosted%2A?displayProperty=nameWithType> to determine if a <xref:System.Windows.Controls.Page> is hosted in a browser.</span></span>  
  
 [!code-csharp[HOWTOBrowserInteropHelperSnippets#IsBrowserHostedCODE](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HOWTOBrowserInteropHelperSnippets/CSharp/Page1.xaml.cs#isbrowserhostedcode)]
 [!code-vb[HOWTOBrowserInteropHelperSnippets#IsBrowserHostedCODE](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HOWTOBrowserInteropHelperSnippets/visualbasic/page1.xaml.vb#isbrowserhostedcode)]  
  
## <a name="see-also"></a><span data-ttu-id="07a65-108">참고 항목</span><span class="sxs-lookup"><span data-stu-id="07a65-108">See Also</span></span>  
 <xref:System.Windows.Controls.Frame>  
 <xref:System.Windows.Controls.Page>
