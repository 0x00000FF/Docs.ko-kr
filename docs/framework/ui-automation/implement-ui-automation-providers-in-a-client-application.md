---
title: 클라이언트 응용 프로그램에서 UI 자동화 공급자 구현
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- client-side UI Automation provider, implementation within applications
- UI Automation, implementing client-side provider within application
ms.assetid: f325f0d8-1715-41ea-85ca-45b82ffea8bc
author: Xansky
ms.author: mhopkins
ms.openlocfilehash: becd247e07a2ece2865251e7a8bbd10f0750ddb3
ms.sourcegitcommit: fb78d8abbdb87144a3872cf154930157090dd933
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/26/2018
ms.locfileid: "47195812"
---
# <a name="implement-ui-automation-providers-in-a-client-application"></a>클라이언트 응용 프로그램에서 UI 자동화 공급자 구현
> [!NOTE]
>  이 설명서는 <xref:System.Windows.Automation> 네임스페이스에 정의된 관리되는 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] 클래스를 사용하려는 .NET Framework 개발자를 위한 것입니다. 에 대 한 최신 정보에 대 한 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]를 참조 하세요 [Windows Automation API: UI 자동화](https://go.microsoft.com/fwlink/?LinkID=156746)합니다.  
  
 이 항목에는 응용 프로그램 내에서 클라이언트 쪽 UI 자동화 공급자를 구현하는 방법을 보여 주는 예제 코드가 있습니다.  
  
 이 방법은 일반적인 시나리오는 아닙니다. 대부분의 경우, UI 자동화 클라이언트 응용 프로그램은 서버 쪽 공급자 또는 DLL에 상주하는 클라이언트 쪽 공급자를 사용합니다.  
  
## <a name="example"></a>예제  
 다음 코드 예제에서는 콘솔 창에 대한 간단한 공급자를 구현합니다. 이 코드에는 유용한 기능이 없지만, 클라이언트 코드 내에서 공급자를 설정하고 <xref:System.Windows.Automation.ClientSettings.RegisterClientSideProviders%2A>을 사용하여 공급자를 등록하는 기본적인 단계를 확인할 수 있습니다.  
  
 [!code-csharp[UIAClientSideProvider_snip#201](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIAClientSideProvider_snip/CSharp/ClientImplementationProgram.cs#201)]
 [!code-vb[UIAClientSideProvider_snip#201](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UIAClientSideProvider_snip/visualbasic/clientimplementationprogram.vb#201)]  
  
## <a name="see-also"></a>참고 항목  
 [UI 자동화 공급자 개요](../../../docs/framework/ui-automation/ui-automation-providers-overview.md)  
 [클라이언트 쪽 공급자 어셈블리 등록](../../../docs/framework/ui-automation/register-a-client-side-provider-assembly.md)  
 [클라이언트 쪽 UI 자동화 공급자 만들기](../../../docs/framework/ui-automation/create-a-client-side-ui-automation-provider.md)  
 [클라이언트 쪽 UI 자동화 공급자 구현](../../../docs/framework/ui-automation/client-side-ui-automation-provider-implementation.md)
