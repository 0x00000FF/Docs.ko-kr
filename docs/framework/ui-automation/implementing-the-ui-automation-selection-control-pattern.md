---
title: UI 자동화 Selection 컨트롤 패턴 구현
ms.date: 03/30/2017
helpviewer_keywords:
- Selection control pattern
- UI Automation, Selection control pattern
- control patterns, Selection
ms.assetid: 449c3068-a5d6-4f66-84c6-1bcc7dd4d209
ms.openlocfilehash: 39baadbad4bf5aff1cc2cd7877489f43581e0fa0
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/03/2019
ms.locfileid: "73458165"
---
# <a name="implementing-the-ui-automation-selection-control-pattern"></a>UI 자동화 Selection 컨트롤 패턴 구현
> [!NOTE]
> 이 설명서는 <xref:System.Windows.Automation> 네임스페이스에 정의된 관리되는 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] 클래스를 사용하려는 .NET Framework 개발자를 위한 것입니다. [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]에 대한 최신 정보는 [Windows 자동화 API: UI 자동화](https://go.microsoft.com/fwlink/?LinkID=156746)를 참조하세요.  
  
 이 항목에서는 이벤트 및 속성에 대한 정보를 포함하여 <xref:System.Windows.Automation.Provider.ISelectionProvider>를 구현하기 위한 지침 및 규칙을 제공합니다. 추가 참조에 대한 링크는 항목 끝에 나열되어 있습니다.  
  
 <xref:System.Windows.Automation.SelectionPattern> 컨트롤 패턴은 선택 가능한 자식 항목 컬렉션에 컨테이너 역할을 하는 컨트롤을 지원하는 데 사용됩니다. 이 요소의 자식 항목은 <xref:System.Windows.Automation.Provider.ISelectionItemProvider>를 구현해야 합니다. 이 컨트롤 패턴을 구현하는 컨트롤의 예제를 보려면 [Control Pattern Mapping for UI Automation Clients](control-pattern-mapping-for-ui-automation-clients.md)을 참조하세요.  
  
<a name="Implementation_Guidelines_and_Conventions"></a>   
## <a name="implementation-guidelines-and-conventions"></a>구현 지침 및 규칙  
 Selection 컨트롤 패턴을 구현할 때는 다음 지침 및 규칙에 유의하세요.  
  
- <xref:System.Windows.Automation.Provider.ISelectionProvider> 를 구현하는 컨트롤을 통해 자식 항목을 하나 또는 여러 개 선택할 수 있습니다. 예를 들어 목록 상자, 목록 뷰, 트리 뷰는 여러 개의 선택을 지원하는 반면 콤보 상자, 슬라이더, 라디오 단추 그룹은 단일 선택을 지원합니다.  
  
- **볼륨** 슬라이더 컨트롤과 같이 최소, 최대, 연속 범위를 가진 컨트롤은 <xref:System.Windows.Automation.Provider.IRangeValueProvider> 대신 <xref:System.Windows.Automation.Provider.ISelectionProvider>를 구현해야 합니다.  
  
- **표시 속성** 대화 상자의 **화면 해상도** 슬라이더 또는 Microsoft Word의 **색 선택** 선택 컨트롤 (아래 그림 참조)과 같은 <xref:System.Windows.Automation.Provider.IRawElementProviderFragmentRoot>를 구현 하는 자식 컨트롤을 관리 하는 단일 선택 컨트롤 (아래 그림 참조) )는 <xref:System.Windows.Automation.Provider.ISelectionProvider>를 구현 해야 합니다. 해당 자식은 <xref:System.Windows.Automation.Provider.IRawElementProviderFragment>와 <xref:System.Windows.Automation.Provider.ISelectionItemProvider>를 모두 구현 해야 합니다.  
  
 ![노란색 강조 표시 된 색 선택기입니다.](./media/uia-valuepattern-colorpicker.png "UIA_ValuePattern_ColorPicker")  
색 견본 문자열 매핑의 예  
  
- 메뉴는 <xref:System.Windows.Automation.SelectionPattern>을 지원하지 않습니다. Microsoft Outlook의 **보기** 메뉴에 있는 **미리 보기 창** 항목과 같이 그래픽과 텍스트가 모두 포함 된 메뉴 항목을 사용 하 여 작업 하는 경우 상태를 전달 해야 하는 경우 <xref:System.Windows.Automation.Provider.IToggleProvider>를 구현 해야 합니다.  
  
<a name="Required_Members_for_ISelectionProvider"></a>   
## <a name="required-members-for-iselectionprovider"></a>ISelectionProvider에 필요한 멤버  
 <xref:System.Windows.Automation.Provider.ISelectionProvider> 인터페이스에는 다음과 같은 속성, 메서드 및 이벤트가 필요합니다.  
  
|필요한 멤버|Type|노트|  
|----------------------|----------|-----------|  
|<xref:System.Windows.Automation.Provider.ISelectionProvider.CanSelectMultiple%2A>|속성|<xref:System.Windows.Automation.Automation.AddAutomationPropertyChangedEventHandler%2A> 및 <xref:System.Windows.Automation.Automation.RemoveAutomationPropertyChangedEventHandler%2A>를 사용하여 속성 변경 이벤트를 지원해야 합니다.|  
|<xref:System.Windows.Automation.Provider.ISelectionProvider.IsSelectionRequired%2A>|속성|<xref:System.Windows.Automation.Automation.AddAutomationPropertyChangedEventHandler%2A> 및 <xref:System.Windows.Automation.Automation.RemoveAutomationPropertyChangedEventHandler%2A>를 사용하여 속성 변경 이벤트를 지원해야 합니다.|  
|<xref:System.Windows.Automation.Provider.ISelectionProvider.GetSelection%2A>|메서드|없음|  
|<xref:System.Windows.Automation.SelectionPatternIdentifiers.InvalidatedEvent>|이벤트(event)|컨테이너의 선택 항목이 현저히 변경되어 <xref:System.Windows.Automation.Provider.AutomationInteropProvider.InvalidateLimit> 상수가 허용하는 것보다 더 많은 추가 및 제거 이벤트를 보내야 하는 경우에 발생합니다.|  
  
 <xref:System.Windows.Automation.Provider.ISelectionProvider.IsSelectionRequired%2A> 및 <xref:System.Windows.Automation.Provider.ISelectionProvider.CanSelectMultiple%2A> 은 동적 속성일 수 있습니다. 예를 들어, 컨트롤의 초기 상태에서 기본적으로 항목이 선택되지 않을 수 있으며 이는 <xref:System.Windows.Automation.Provider.ISelectionProvider.IsSelectionRequired%2A> 가 `false`임을 나타냅니다. 그러나 항목이 선택된 후에는 컨트롤에 하나 이상의 항목이 항상 선택되어 있어야 합니다. 마찬가지로, 드문 경우지만 초기화될 때 컨트롤에서 여러 항목이 선택될 수 있지만 이후에는 하나의 선택 항목만 허용됩니다.  
  
<a name="Exceptions"></a>   
## <a name="exceptions"></a>예외  
 공급자는 다음과 같은 예외를 throw해야 합니다.  
  
|예외 형식|조건|  
|--------------------|---------------|  
|<xref:System.Windows.Automation.ElementNotEnabledException>|컨트롤이 사용 설정되지 않은 경우.|  
|<xref:System.InvalidOperationException>|컨트롤이 숨겨진 경우.|  
  
## <a name="see-also"></a>참조

- [UI 자동화 컨트롤 패턴 개요](ui-automation-control-patterns-overview.md)
- [UI 자동화 공급자의 컨트롤 패턴 지원](support-control-patterns-in-a-ui-automation-provider.md)
- [클라이언트용 UI 자동화 컨트롤 패턴](ui-automation-control-patterns-for-clients.md)
- [UI 자동화 SelectionItem 컨트롤 패턴 구현](implementing-the-ui-automation-selectionitem-control-pattern.md)
- [UI 자동화 트리 개요](ui-automation-tree-overview.md)
- [UI 자동화의 캐싱 사용](use-caching-in-ui-automation.md)
