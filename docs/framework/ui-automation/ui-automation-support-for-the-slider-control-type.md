---
title: "UI Automation Support for the Slider Control Type | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-bcl"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "control types, Slider"
  - "UI Automation, Slider control type"
  - "Slider control type"
ms.assetid: 045ea62f-7b50-46cf-a5a9-8eb97704355f
caps.latest.revision: 18
author: "Xansky"
ms.author: "mhopkins"
manager: "markl"
caps.handback.revision: 18
---
# UI Automation Support for the Slider Control Type
> [!NOTE]
>  이 설명서는 <xref:System.Windows.Automation> 네임스페이스에 정의된 관리되는 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] 클래스를 사용하려는 .NET Framework 개발자를 위한 것입니다.[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]에 대한 최신 정보는 [Windows 자동화 API: UI 자동화](http://go.microsoft.com/fwlink/?LinkID=156746)를 참조하세요.  
  
 이 항목에서는 Slider 컨트롤 형식에 대한 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] 지원 정보를 제공합니다.[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]에서, 컨트롤 형식은 <xref:System.Windows.Automation.AutomationElement.ControlTypeProperty> 속성을 사용하기 위해 컨트롤이 충족해야 하는 조건 집합입니다. 이 조건에는 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] 트리 구조, [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] 속성 값, 컨트롤 형식에 대한 특정 지침이 포함됩니다.  
  
 슬라이더 컨트롤은 사용자가 마우스를 사용하여 숫자 범위를 설정하거나 항목 집합에서 선택할 수 있도록 하는 단추가 있는 복합 컨트롤입니다.  
  
 다음 섹션에서는 Slider 컨트롤 형식에 필요한 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] 트리 구조, 속성, 컨트롤 패턴, 이벤트를 정의합니다.[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] 요구 사항은 [!INCLUDE[TLA#tla_winclient](../../../includes/tlasharptla-winclient-md.md)], [!INCLUDE[TLA#tla_win32](../../../includes/tlasharptla-win32-md.md)] 또는 [!INCLUDE[TLA#tla_winforms](../../../includes/tlasharptla-winforms-md.md)]의 모든 슬라이더 컨트롤에 적용됩니다.  
  
<a name="Required_UI_Automation_Tree_Structure"></a>   
## 필요한 UI 자동화 트리 구조  
 다음 표는 슬라이더 컨트롤과 관련된 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] 트리의 컨트롤 뷰 및 콘텐츠 뷰를 보여주고 각 뷰에 포함될 수 있는 내용에 대해 설명합니다.[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] 트리에 대한 자세한 내용은 [UI Automation Tree Overview](../../../docs/framework/ui-automation/ui-automation-tree-overview.md)를 참조하세요.  
  
|컨트롤 뷰|콘텐츠 뷰|  
|-----------|-----------|  
|슬라이더<br /><br /> -   Button\(2 또는 4개\)<br />-   Thumb\(1개만\)<br />-   List Item\(0개 이상\)|슬라이더<br /><br /> -   List Item\(0개 이상\)|  
  
<a name="Required_UI_Automation_Properties"></a>   
## 필요한 UI 자동화 속성  
 다음 표에서는 값 또는 정의가 Slider 컨트롤 형식과 특별히 관련된 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] 속성을 나열하여 보여 줍니다.[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] 속성에 대한 자세한 내용은 [UI Automation Properties for Clients](../../../docs/framework/ui-automation/ui-automation-properties-for-clients.md)를 참조하세요.  
  
|[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] 속성|값|노트|  
|------------------------------------------------------------------------------|-------|--------|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.AutomationIdProperty>|메모를 참조하세요.|이 속성의 값은 응용 프로그램의 모든 컨트롤에서 고유해야 합니다.|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.BoundingRectangleProperty>|메모를 참조하세요.|전체 컨트롤이 포함된 가장 바깥쪽 사각형입니다.|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.ClickablePointProperty>|메모를 참조하세요.|슬라이더 컨트롤의 전체 경계 사각형은 자식 컨트롤이 차지하기 때문에 대부분의 슬라이더 컨트롤은 <xref:System.Windows.Automation.NoClickablePointException>을 발생시켜야 합니다.|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.IsKeyboardFocusableProperty>|메모를 참조하세요.|컨트롤이 키보드 포커스를 받을 수 있으면 해당 컨트롤은 이 속성을 지원해야 합니다.|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.NameProperty>|메모를 참조하세요.|편집 컨트롤의 이름은 일반적으로 정적 텍스트 레이블에서 생성됩니다. 정적 텍스트 레이블이 없는 경우 응용 프로그램 개발자가 `Name`의 속성 값을 할당해야 합니다.`Name` 속성에는 편집 컨트롤의 텍스트 내용이 포함되지 않아야 합니다.|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.LabeledByProperty>|메모를 참조하세요.|컨트롤과 연결된 정적 텍스트 레이블이 있는 경우, 이 속성은 해당 컨트롤에 대한 참조를 노출해야 합니다. 텍스트 컨트롤이 다른 컨트롤의 하위 구성 요소일 경우 이 컨트롤에 `LabeledBy` 속성 집합이 없습니다.|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.ControlTypeProperty>|슬라이더|이 값은 모든 [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] 프레임워크에 대해 동일합니다.|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.LocalizedControlTypeProperty>|"slider"|Edit 컨트롤 형식에 해당하는 지역화된 문자열입니다.|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.IsContentElementProperty>|True|편집 컨트롤이 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] 트리의 콘텐츠 뷰에 항상 포함됩니다.|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.IsControlElementProperty>|True|편집 컨트롤이 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] 트리의 컨트롤 뷰에 항상 포함됩니다.|  
  
<a name="Required_UI_Automation_Control_Patterns"></a>   
## 필요한 UI 자동화 컨트롤 패턴  
 다음 표에서는 모든 슬라이더 컨트롤에서 지원되는 데 필요한 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] 컨트롤 패턴을 나열하여 보여 줍니다. 컨트롤 패턴에 대한 자세한 내용은 [UI Automation Control Patterns Overview](../../../docs/framework/ui-automation/ui-automation-control-patterns-overview.md)를 참조하세요.  
  
|컨트롤 패턴|지원|노트|  
|------------|--------|--------|  
|<xref:System.Windows.Automation.Provider.ISelectionProvider>|종속|콘텐츠가 불연속 옵션 집합의 값 중 하나를 나타내는 경우 슬라이더는 Selection 컨트롤 패턴을 지원해야 합니다. Selection 컨트롤 패턴이 지원되면 해당 선택은 슬라이더의 자식 목록 항목 중 하나 이상으로 노출되어야 합니다.|  
|<xref:System.Windows.Automation.Provider.IRangeValueProvider>|종속|콘텐츠를 숫자 범위 내에 있는 값으로 설정할 수 있는 경우 슬라이더는 RangeValue 컨트롤 패턴을 지원해야 합니다.|  
|<xref:System.Windows.Automation.Provider.IValueProvider>|종속|콘텐츠가 불연속 옵션 집합의 값 중 하나를 나타내는 경우 슬라이더 Value 컨트롤 패턴을 지원 해야 합니다.|  
  
<a name="Required_UI_Automation_Events"></a>   
## 필요한 UI 자동화 이벤트  
 다음 표에서는 모든 슬라이더 컨트롤에서 지원되는 데 필요한 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] 이벤트를 나열하여 보여 줍니다.  
  
 이벤트에 대한 자세한 내용은 [UI Automation Events Overview](../../../docs/framework/ui-automation/ui-automation-events-overview.md)를 참조하세요.  
  
|[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] 이벤트|지원|노트|  
|-------------------------------------------------------------------------------|--------|--------|  
|<xref:System.Windows.Automation.SelectionPatternIdentifiers.InvalidatedEvent>|종속|없음|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.BoundingRectangleProperty> 속성 변경 이벤트|필수|없음|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.IsOffscreenProperty> 속성 변경 이벤트|필수|없음|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.IsEnabledProperty> 속성 변경 이벤트|필수|없음|  
|<xref:System.Windows.Automation.RangeValuePatternIdentifiers.ValueProperty> 속성 변경 이벤트|종속|없음|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.AutomationFocusChangedEvent>|필수|없음|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.StructureChangedEvent>|필수|없음|  
  
## 참고 항목  
 <xref:System.Windows.Automation.ControlType.Slider>   
 [UI Automation Control Types Overview](../../../docs/framework/ui-automation/ui-automation-control-types-overview.md)   
 [UI Automation Overview](../../../docs/framework/ui-automation/ui-automation-overview.md)