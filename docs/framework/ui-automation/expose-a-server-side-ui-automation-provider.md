---
title: 서버 쪽 UI 자동화 공급자 노출
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- expose a server-side UI Automation provider
- UI Automation, server-side provider, exposing
- server-side UI Automation provider, exposing
ms.assetid: 55d419c0-2201-4101-90c9-2888df4dbb47
author: Xansky
ms.author: mhopkins
ms.openlocfilehash: 247a353a3f68289a85e581fd9b9c308e442a9412
ms.sourcegitcommit: fb78d8abbdb87144a3872cf154930157090dd933
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/29/2018
ms.locfileid: "47455490"
---
# <a name="expose-a-server-side-ui-automation-provider"></a><span data-ttu-id="cd840-102">서버 쪽 UI 자동화 공급자 노출</span><span class="sxs-lookup"><span data-stu-id="cd840-102">Expose a Server-side UI Automation Provider</span></span>
> [!NOTE]
>  <span data-ttu-id="cd840-103">이 설명서는 <xref:System.Windows.Automation> 네임스페이스에 정의된 관리되는 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] 클래스를 사용하려는 .NET Framework 개발자를 위한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="cd840-103">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="cd840-104">에 대 한 최신 정보에 대 한 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]를 참조 하세요 [Windows Automation API: UI 자동화](https://go.microsoft.com/fwlink/?LinkID=156746)합니다.</span><span class="sxs-lookup"><span data-stu-id="cd840-104">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](https://go.microsoft.com/fwlink/?LinkID=156746).</span></span>  
  
 <span data-ttu-id="cd840-105">이 항목에는 <xref:System.Windows.Forms.Control?displayProperty=nameWithType> 창에 호스트되는 서버 쪽 UI 자동화 공급자를 노출하는 방법을 보여주는 예제 코드가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cd840-105">This topic contains example code that shows how to expose a server-side UI Automation provider that is hosted in a <xref:System.Windows.Forms.Control?displayProperty=nameWithType> window.</span></span>  
  
 <span data-ttu-id="cd840-106">이 예제에서는 클라이언트 응용 프로그램이 창에 대한 정보를 요청할 때 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] 핵심 서비스가 보내는 메시지인 WM_GETOBJECT를 트랩하기 위해 창 프로시저를 재정의합니다.</span><span class="sxs-lookup"><span data-stu-id="cd840-106">The example overrides the window procedure to trap WM_GETOBJECT, which is the message sent by the [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] core service when a client application requests information about the window.</span></span>  
  
## <a name="example"></a><span data-ttu-id="cd840-107">예제</span><span class="sxs-lookup"><span data-stu-id="cd840-107">Example</span></span>  
 [!code-csharp[UIAFragmentProvider_snip#116](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIAFragmentProvider_snip/CSharp/ListFragment.cs#116)]
 [!code-vb[UIAFragmentProvider_snip#116](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UIAFragmentProvider_snip/VisualBasic/ListFragment.vb#116)]  
  
## <a name="see-also"></a><span data-ttu-id="cd840-108">참고 항목</span><span class="sxs-lookup"><span data-stu-id="cd840-108">See Also</span></span>  
 [<span data-ttu-id="cd840-109">UI 자동화 공급자 개요</span><span class="sxs-lookup"><span data-stu-id="cd840-109">UI Automation Providers Overview</span></span>](../../../docs/framework/ui-automation/ui-automation-providers-overview.md)  
 [<span data-ttu-id="cd840-110">서버 쪽 UI 자동화 공급자 구현</span><span class="sxs-lookup"><span data-stu-id="cd840-110">Server-Side UI Automation Provider Implementation</span></span>](../../../docs/framework/ui-automation/server-side-ui-automation-provider-implementation.md)
