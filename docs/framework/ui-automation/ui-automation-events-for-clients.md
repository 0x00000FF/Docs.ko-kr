---
title: 클라이언트용 UI 자동화 이벤트
ms.date: 03/30/2017
helpviewer_keywords:
- UI Automation, events for clients
- events, UI Automation clients
ms.assetid: b909e388-3f24-4997-b6d4-bd9c35c2dc27
author: Xansky
ms.author: mhopkins
ms.openlocfilehash: fdd192f7ba6273cb4f7927ccb6b34963b3aaea7d
ms.sourcegitcommit: 213292dfbb0c37d83f62709959ff55c50af5560d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/25/2018
ms.locfileid: "47070560"
---
# <a name="ui-automation-events-for-clients"></a>클라이언트용 UI 자동화 이벤트
> [!NOTE]
>  이 설명서는 <xref:System.Windows.Automation> 네임스페이스에 정의된 관리되는 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] 클래스를 사용하려는 .NET Framework 개발자를 위한 것입니다. 에 대 한 최신 정보에 대 한 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]를 참조 하세요 [Windows Automation API: UI 자동화](https://go.microsoft.com/fwlink/?LinkID=156746)합니다.  
  
 이 항목에서는 [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] 이벤트가 UI 자동화 클라이언트에서 사용되는 방법을 설명합니다.  
  
 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] 클라이언트가 원하는 이벤트를 구독할 수 있습니다. 이 기능은 지속적으로 모든를 폴링할 필요가 없으므로 성능이 향상 됩니다.는 [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] 시스템 정보, 구조 또는 상태가 변경 되었는지 여부에 대 한 요소입니다.  
  
 정의된 기능 내에서만 이벤트를 수신 대기하는 기능을 통해 효율성도 향상되었습니다. 예를 들어 클라이언트가 수신 대기할 수 포커스 변경 이벤트를 모든 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] 요소 트리에서 특정 요소와 해당 하위 항목입니다.  
  
> [!NOTE]
>  가능한 모든 이벤트가 올라오는 가정 하지 마십시오는 [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] 공급자입니다. 모든 속성 변경에 대 한 표준 프록시 공급자에 의해 발생 하는 이벤트를 발생 하는 예를 들어 [!INCLUDE[TLA#tla_winforms](../../../includes/tlasharptla-winforms-md.md)] 고 [!INCLUDE[TLA2#tla_win32](../../../includes/tla2sharptla-win32-md.md)] 컨트롤입니다.  
  
 넓은 관점 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] 이벤트를 참조 하세요 [UI Automation Events Overview](../../../docs/framework/ui-automation/ui-automation-events-overview.md)합니다.  
  
<a name="Subscribing_to_Events"></a>   
## <a name="subscribing-to-events"></a>이벤트 구독  
 클라이언트 응용 프로그램은 다음 방법 중 하나로 이벤트 처리기를 등록하여 특정 종류의 이벤트를 구독합니다.  
  
|메서드|이벤트 형식|이벤트 인수 형식|대리자 형식|  
|------------|----------------|--------------------------|-------------------|  
|<xref:System.Windows.Automation.Automation.AddAutomationFocusChangedEventHandler%2A>|포커스 변경|<xref:System.Windows.Automation.AutomationFocusChangedEventArgs>|<xref:System.Windows.Automation.AutomationFocusChangedEventHandler>|  
|<xref:System.Windows.Automation.Automation.AddAutomationPropertyChangedEventHandler%2A>|속성 변경|<xref:System.Windows.Automation.AutomationPropertyChangedEventArgs>|<xref:System.Windows.Automation.AutomationPropertyChangedEventHandler>|  
|<xref:System.Windows.Automation.Automation.AddStructureChangedEventHandler%2A>|구조 변경|<xref:System.Windows.Automation.StructureChangedEventArgs>|<xref:System.Windows.Automation.StructureChangedEventHandler>|  
|<xref:System.Windows.Automation.Automation.AddAutomationEventHandler%2A>|다른 모든 이벤트로 식별 되는 <xref:System.Windows.Automation.AutomationEvent>|<xref:System.Windows.Automation.AutomationEventArgs> 또는 <xref:System.Windows.Automation.WindowClosedEventArgs>|<xref:System.Windows.Automation.AutomationEventHandler>|  
  
 메서드를 호출하기 전에, 이벤트를 처리하는 대리자 메서드를 만들어야 합니다. 원하는 경우, 단일 메서드에서 여러 종류의 이벤트를 처리하고 이 메서드를 여러 번 호출하여 테이블에 있는 메서드 중 하나에 전달할 수 있습니다. 예를 들어, 단일 <xref:System.Windows.Automation.AutomationEventHandler> 에 따라 서로 다른 다양 한 이벤트를 처리 하도록 설정할 수 있습니다는 <xref:System.Windows.Automation.AutomationEventArgs.EventId%2A>합니다.  
  
> [!NOTE]
>  창이 닫힌 이벤트를 처리 하려면 같이 이벤트 처리기에 전달 되는 인수 형식을 캐스팅 <xref:System.Windows.Automation.WindowClosedEventArgs>합니다. 때문에 [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] 요소는 창에 대 한 더 이상 유효, 사용할 수 없습니다는 `sender` 매개 변수 정보를 검색할 사용 <xref:System.Windows.Automation.WindowClosedEventArgs.GetRuntimeId%2A> 대신 합니다.  
  
> [!CAUTION]
>  응용 프로그램 자체에서 이벤트를 받을 수 있으면 [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)], 응용 프로그램을 사용 하지 마십시오 [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] 스레드 이벤트를 구독 하거나 구독을 취소 합니다. 이렇게 하면 예기치 않은 동작이 발생할 수 있습니다. 자세한 내용은 [UI Automation Threading Issues](../../../docs/framework/ui-automation/ui-automation-threading-issues.md)을 참조하세요.  
  
 종료되거나 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] 이벤트가 더 이상 응용 프로그램에 필요하지 않는 경우에는 UI 자동화 클라이언트가 다음 메서드 중 하나를 호출해야 합니다.  
  
|메서드|설명|  
|------------|-----------------|  
|<xref:System.Windows.Automation.Automation.RemoveAutomationEventHandler%2A>|사용 하 여 등록 된 이벤트 처리기를 등록 취소 <xref:System.Windows.Automation.Automation.AddAutomationEventHandler%2A>합니다.|  
|<xref:System.Windows.Automation.Automation.RemoveAutomationFocusChangedEventHandler%2A>|사용 하 여 등록 된 이벤트 처리기를 등록 취소 <xref:System.Windows.Automation.Automation.AddAutomationFocusChangedEventHandler%2A>합니다.|  
|<xref:System.Windows.Automation.Automation.RemoveAutomationPropertyChangedEventHandler%2A>|사용 하 여 등록 된 이벤트 처리기를 등록 취소 <xref:System.Windows.Automation.Automation.AddAutomationPropertyChangedEventHandler%2A>합니다.|  
|<xref:System.Windows.Automation.Automation.RemoveAllEventHandlers%2A>|등록된 모든 이벤트 처리기를 등록 취소합니다.|  
  
 예제 코드를 참조 하세요 [UI Automation 이벤트를 구독할](../../../docs/framework/ui-automation/subscribe-to-ui-automation-events.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [UI 자동화 이벤트 구독](../../../docs/framework/ui-automation/subscribe-to-ui-automation-events.md)  
 [UI 자동화 이벤트 개요](../../../docs/framework/ui-automation/ui-automation-events-overview.md)  
 [UI 자동화 속성 개요](../../../docs/framework/ui-automation/ui-automation-properties-overview.md)  
 [TrackFocus 샘플](https://msdn.microsoft.com/library/4a91c0af-6bb5-4d38-a743-cf136f268fc9)
