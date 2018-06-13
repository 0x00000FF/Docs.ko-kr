---
title: '방법: 브라우저에서 호스팅되는 페이지 인지 확인'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- hosted pages in browser [WPF]
- pages [WPF], hosted in browser
ms.assetid: 737e0f26-8371-49b4-9579-70879e51e1aa
ms.openlocfilehash: 6eb83429cb4f9dac5f3561b41997d24bcaa2c62f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33545899"
---
# <a name="how-to-determine-if-a-page-is-browser-hosted"></a>방법: 브라우저에서 호스팅되는 페이지 인지 확인
확인 하는 방법을 보여 주는이 예제는 <xref:System.Windows.Controls.Page> 브라우저에서 호스트 됩니다.  
  
## <a name="example"></a>예제  
 A <xref:System.Windows.Controls.Page> 호스트를 알 수 없는 수 있으며이, 결과적으로, 여러 다른 유형의 비롯 한 호스트에 로드 될 수는 <xref:System.Windows.Controls.Frame>, 즉 <xref:System.Windows.Navigation.NavigationWindow>, 브라우저 등입니다. 이 라이브러리 어셈블리가 하나 이상의 페이지를 포함 하 고 있는 참조 되는 여러 독립 실행형으로 탐색할 수 있을 때 발생할 수 있습니다 ([!INCLUDE[TLA#tla_xbap](../../../../includes/tlasharptla-xbap-md.md)]) 응용 프로그램을 호스트 합니다.  
  
 다음 예제에서는 사용 하는 방법을 <xref:System.Windows.Interop.BrowserInteropHelper.IsBrowserHosted%2A?displayProperty=nameWithType> 여부를 확인 하는 <xref:System.Windows.Controls.Page> 브라우저에서 호스트 됩니다.  
  
 [!code-csharp[HOWTOBrowserInteropHelperSnippets#IsBrowserHostedCODE](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HOWTOBrowserInteropHelperSnippets/CSharp/Page1.xaml.cs#isbrowserhostedcode)]
 [!code-vb[HOWTOBrowserInteropHelperSnippets#IsBrowserHostedCODE](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HOWTOBrowserInteropHelperSnippets/visualbasic/page1.xaml.vb#isbrowserhostedcode)]  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Windows.Controls.Frame>  
 <xref:System.Windows.Controls.Page>
