---
title: UI 자동화 Value 컨트롤 패턴 구현
ms.date: 03/30/2017
helpviewer_keywords:
- control patterns, Value
- UI Automation, Value control pattern
- Value control pattern
ms.assetid: b0fcdd87-3add-4345-bca9-e891205e02ba
author: Xansky
ms.author: mhopkins
manager: markl
ms.openlocfilehash: 300d9df608553f9f8ae999287b3214c8a9eaea21
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/02/2018
ms.locfileid: "43468125"
---
# <a name="implementing-the-ui-automation-value-control-pattern"></a><span data-ttu-id="d2b67-102">UI 자동화 Value 컨트롤 패턴 구현</span><span class="sxs-lookup"><span data-stu-id="d2b67-102">Implementing the UI Automation Value Control Pattern</span></span>
> [!NOTE]
>  <span data-ttu-id="d2b67-103">이 설명서는 <xref:System.Windows.Automation> 네임스페이스에 정의된 관리되는 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] 클래스를 사용하려는 .NET Framework 개발자를 위한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="d2b67-103">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="d2b67-104">에 대 한 최신 정보에 대 한 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]를 참조 하세요 [Windows Automation API: UI 자동화](https://go.microsoft.com/fwlink/?LinkID=156746)합니다.</span><span class="sxs-lookup"><span data-stu-id="d2b67-104">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](https://go.microsoft.com/fwlink/?LinkID=156746).</span></span>  
  
 <span data-ttu-id="d2b67-105">이 항목에서는 이벤트 및 속성에 대한 정보를 포함하여 <xref:System.Windows.Automation.Provider.IValueProvider>를 구현하기 위한 지침 및 규칙을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="d2b67-105">This topic introduces guidelines and conventions for implementing <xref:System.Windows.Automation.Provider.IValueProvider>, including information on events and properties.</span></span> <span data-ttu-id="d2b67-106">추가 참조에 대한 링크는 항목 끝에 나열되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d2b67-106">Links to additional references are listed at the end of the topic.</span></span>  
  
 <span data-ttu-id="d2b67-107"><xref:System.Windows.Automation.ValuePattern> 컨트롤 패턴는 범위에 걸쳐 있지 않은 내장 값이 있고 문자열로 나타낼 수 있는 컨트롤을 지원하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="d2b67-107">The <xref:System.Windows.Automation.ValuePattern> control pattern is used to support controls that have an intrinsic value not spanning a range and that can be represented as a string.</span></span> <span data-ttu-id="d2b67-108">이 문자열은 컨트롤 및 해당 설정에 따라 편집할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d2b67-108">This string can be editable, depending on the control and its settings.</span></span> <span data-ttu-id="d2b67-109">이 패턴을 구현하는 컨트롤의 예제를 보려면 [Control Pattern Mapping for UI Automation Clients](../../../docs/framework/ui-automation/control-pattern-mapping-for-ui-automation-clients.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d2b67-109">For examples of controls that implement this pattern, see [Control Pattern Mapping for UI Automation Clients](../../../docs/framework/ui-automation/control-pattern-mapping-for-ui-automation-clients.md).</span></span>  
  
<a name="Implementation_Guidelines_and_Conventions"></a>   
## <a name="implementation-guidelines-and-conventions"></a><span data-ttu-id="d2b67-110">구현 지침 및 규칙</span><span class="sxs-lookup"><span data-stu-id="d2b67-110">Implementation Guidelines and Conventions</span></span>  
 <span data-ttu-id="d2b67-111">Value 컨트롤 패턴을 구현할 때는 다음 지침 및 규칙에 유의하세요.</span><span class="sxs-lookup"><span data-stu-id="d2b67-111">When implementing the Value control pattern, note the following guidelines and conventions:</span></span>  
  
-   <span data-ttu-id="d2b67-112"><xref:System.Windows.Automation.ControlType.ListItem> 및 <xref:System.Windows.Automation.ControlType.TreeItem> 과 같은 컨트롤은 항목이 편집 가능한 경우 컨트롤의 현재 편집 모드와 관계 없이 <xref:System.Windows.Automation.ValuePattern> 을 지원해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2b67-112">Controls such as <xref:System.Windows.Automation.ControlType.ListItem> and <xref:System.Windows.Automation.ControlType.TreeItem> must support <xref:System.Windows.Automation.ValuePattern> if the value of any of the items is editable, regardless of the current edit mode of the control.</span></span> <span data-ttu-id="d2b67-113">자식 항목이 편집 가능한 경우 부모 컨트롤이 <xref:System.Windows.Automation.ValuePattern> 도 지원해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2b67-113">The parent control must also support <xref:System.Windows.Automation.ValuePattern> if the child items are editable.</span></span>  
  
 <span data-ttu-id="d2b67-114">![편집할 수 있는 목록 항목입니다. ](../../../docs/framework/ui-automation/media/uia-valuepattern-editable-listitem.PNG "UIA_ValuePattern_Editable_ListItem")</span><span class="sxs-lookup"><span data-stu-id="d2b67-114">![Editable list item.](../../../docs/framework/ui-automation/media/uia-valuepattern-editable-listitem.PNG "UIA_ValuePattern_Editable_ListItem")</span></span>  
<span data-ttu-id="d2b67-115">편집 가능한 목록 항목의 예</span><span class="sxs-lookup"><span data-stu-id="d2b67-115">Example of an Editable List Item</span></span>  
  
-   <span data-ttu-id="d2b67-116">단일 줄 편집 컨트롤은 <xref:System.Windows.Automation.Provider.IValueProvider>를 구현하여 해당 내용에 대한 프로그래밍 방식 액세스를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="d2b67-116">Single-line edit controls support programmatic access to their contents by implementing <xref:System.Windows.Automation.Provider.IValueProvider>.</span></span> <span data-ttu-id="d2b67-117">하지만 여러 줄 편집 컨트롤은 <xref:System.Windows.Automation.Provider.IValueProvider>를 구현하지 않습니다. 대신, <xref:System.Windows.Automation.Provider.ITextProvider>를 구현하여 내용에 대한 액세스를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="d2b67-117">However, multi-line edit controls do not implement <xref:System.Windows.Automation.Provider.IValueProvider>; instead they provide access to their content by implementing <xref:System.Windows.Automation.Provider.ITextProvider>.</span></span>  
  
-   <span data-ttu-id="d2b67-118">여러 줄 편집 컨트롤의 텍스트 내용을 검색하려면 컨트롤이 <xref:System.Windows.Automation.Provider.ITextProvider>를 구현해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2b67-118">To retrieve the textual contents of a multi-line edit control, the control must implement <xref:System.Windows.Automation.Provider.ITextProvider>.</span></span> <span data-ttu-id="d2b67-119">하지만 <xref:System.Windows.Automation.Provider.ITextProvider> 는 컨트롤의 값 설정을 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d2b67-119">However, <xref:System.Windows.Automation.Provider.ITextProvider> does not support setting the value of a control.</span></span>  
  
-   <span data-ttu-id="d2b67-120"><xref:System.Windows.Automation.Provider.IValueProvider> 는 서식 정보 및 하위 문자열 값 검색을 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d2b67-120"><xref:System.Windows.Automation.Provider.IValueProvider> does not support the retrieval of formatting information or substring values.</span></span> <span data-ttu-id="d2b67-121">이러한 시나리오에서는 <xref:System.Windows.Automation.Provider.ITextProvider> 를 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="d2b67-121">Implement <xref:System.Windows.Automation.Provider.ITextProvider> in these scenarios.</span></span>  
  
-   <span data-ttu-id="d2b67-122"><xref:System.Windows.Automation.Provider.IValueProvider> 는 색 값(예: "노란색") 및 해당되는 내부 **구조 간의 문자열 매핑을 지원하는** 의 [!INCLUDE[TLA#tla_word](../../../includes/tlasharptla-word-md.md)] 색 선택 [!INCLUDE[TLA#tla_rgb](../../../includes/tlasharptla-rgb-md.md)] 선택 항목 컨트롤과 같은(아래 그림 참조) 컨트롤이 구현해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2b67-122"><xref:System.Windows.Automation.Provider.IValueProvider> must be implemented by controls such as the **Color Picker** selection control from [!INCLUDE[TLA#tla_word](../../../includes/tlasharptla-word-md.md)] (illustrated below), which supports string mapping between a color value (for example, "yellow") and an equivalent internal [!INCLUDE[TLA#tla_rgb](../../../includes/tlasharptla-rgb-md.md)] structure.</span></span>  
  
 <span data-ttu-id="d2b67-123">![노란색이 강조 표시 된 색 선택 합니다. ](../../../docs/framework/ui-automation/media/uia-valuepattern-colorpicker.png "UIA_ValuePattern_ColorPicker")</span><span class="sxs-lookup"><span data-stu-id="d2b67-123">![Color picker with yellow highlighted.](../../../docs/framework/ui-automation/media/uia-valuepattern-colorpicker.png "UIA_ValuePattern_ColorPicker")</span></span>  
<span data-ttu-id="d2b67-124">색 견본 문자열 매핑의 예</span><span class="sxs-lookup"><span data-stu-id="d2b67-124">Example of Color Swatch String Mapping</span></span>  
  
-   <span data-ttu-id="d2b67-125">컨트롤에서 <xref:System.Windows.Automation.AutomationElement.IsEnabledProperty> 가 `true` 로 설정되고 <xref:System.Windows.Automation.ValuePattern.IsReadOnlyProperty> 가 `false` 로 설정되어야 <xref:System.Windows.Automation.Provider.IValueProvider.SetValue%2A>를 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d2b67-125">A control should have its <xref:System.Windows.Automation.AutomationElement.IsEnabledProperty> set to `true` and its <xref:System.Windows.Automation.ValuePattern.IsReadOnlyProperty> set to `false` before allowing a call to <xref:System.Windows.Automation.Provider.IValueProvider.SetValue%2A>.</span></span>  
  
<a name="Required_Members_for_the_IValueProvider_Interface"></a>   
## <a name="required-members-for-ivalueprovider"></a><span data-ttu-id="d2b67-126">IValueProvider에 필요한 멤버</span><span class="sxs-lookup"><span data-stu-id="d2b67-126">Required Members for IValueProvider</span></span>  
 <span data-ttu-id="d2b67-127"><xref:System.Windows.Automation.Provider.IValueProvider>를 구현하려면 다음과 같은 속성 및 메서드가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="d2b67-127">The following properties and methods are required for implementing <xref:System.Windows.Automation.Provider.IValueProvider>.</span></span>  
  
|<span data-ttu-id="d2b67-128">필요한 멤버</span><span class="sxs-lookup"><span data-stu-id="d2b67-128">Required members</span></span>|<span data-ttu-id="d2b67-129">멤버 형식</span><span class="sxs-lookup"><span data-stu-id="d2b67-129">Member type</span></span>|<span data-ttu-id="d2b67-130">노트</span><span class="sxs-lookup"><span data-stu-id="d2b67-130">Notes</span></span>|  
|----------------------|-----------------|-----------|  
|<xref:System.Windows.Automation.ValuePattern.IsReadOnlyProperty>|<span data-ttu-id="d2b67-131">속성</span><span class="sxs-lookup"><span data-stu-id="d2b67-131">Property</span></span>|<span data-ttu-id="d2b67-132">없음</span><span class="sxs-lookup"><span data-stu-id="d2b67-132">None</span></span>|  
|<xref:System.Windows.Automation.ValuePattern.ValueProperty>|<span data-ttu-id="d2b67-133">속성</span><span class="sxs-lookup"><span data-stu-id="d2b67-133">Property</span></span>|<span data-ttu-id="d2b67-134">없음</span><span class="sxs-lookup"><span data-stu-id="d2b67-134">None</span></span>|  
|<xref:System.Windows.Automation.ValuePattern.SetValue%2A>|<span data-ttu-id="d2b67-135">메서드</span><span class="sxs-lookup"><span data-stu-id="d2b67-135">Method</span></span>|<span data-ttu-id="d2b67-136">없음</span><span class="sxs-lookup"><span data-stu-id="d2b67-136">None</span></span>|  
  
<a name="Exceptions"></a>   
## <a name="exceptions"></a><span data-ttu-id="d2b67-137">예외</span><span class="sxs-lookup"><span data-stu-id="d2b67-137">Exceptions</span></span>  
 <span data-ttu-id="d2b67-138">공급자는 다음과 같은 예외를 throw해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2b67-138">Providers must throw the following exceptions.</span></span>  
  
|<span data-ttu-id="d2b67-139">예외 형식</span><span class="sxs-lookup"><span data-stu-id="d2b67-139">Exception type</span></span>|<span data-ttu-id="d2b67-140">조건</span><span class="sxs-lookup"><span data-stu-id="d2b67-140">Condition</span></span>|  
|--------------------|---------------|  
|<xref:System.InvalidOperationException>|<xref:System.Windows.Automation.ValuePattern.SetValue%2A><br /><br /> <span data-ttu-id="d2b67-141">-경우 로캘별 정보 형식이 잘못 된 날짜와 같은 잘못 된 형식으로 컨트롤에 전달 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d2b67-141">-   If locale-specific information is passed to a control in an incorrect format such as an incorrectly formatted date.</span></span>|  
|<xref:System.ArgumentException>|<xref:System.Windows.Automation.ValuePattern.SetValue%2A><br /><br /> <span data-ttu-id="d2b67-142">-새 값을 형식으로 문자열에서 변환할 수 없는 하는 경우 컨트롤이 인식 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2b67-142">-   If a new value cannot be converted from a string to a format the control recognizes.</span></span>|  
|<xref:System.Windows.Automation.ElementNotEnabledException>|<xref:System.Windows.Automation.ValuePattern.SetValue%2A><br /><br /> <span data-ttu-id="d2b67-143">-시도가 설정 되지 않은 컨트롤을 조작 하려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2b67-143">-   When an attempt is made to manipulate a control that is not enabled.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="d2b67-144">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d2b67-144">See Also</span></span>  
 [<span data-ttu-id="d2b67-145">UI 자동화 컨트롤 패턴 개요</span><span class="sxs-lookup"><span data-stu-id="d2b67-145">UI Automation Control Patterns Overview</span></span>](../../../docs/framework/ui-automation/ui-automation-control-patterns-overview.md)  
 [<span data-ttu-id="d2b67-146">UI 자동화 공급자의 컨트롤 패턴 지원</span><span class="sxs-lookup"><span data-stu-id="d2b67-146">Support Control Patterns in a UI Automation Provider</span></span>](../../../docs/framework/ui-automation/support-control-patterns-in-a-ui-automation-provider.md)  
 [<span data-ttu-id="d2b67-147">클라이언트용 UI 자동화 컨트롤 패턴</span><span class="sxs-lookup"><span data-stu-id="d2b67-147">UI Automation Control Patterns for Clients</span></span>](../../../docs/framework/ui-automation/ui-automation-control-patterns-for-clients.md)  
 [<span data-ttu-id="d2b67-148">TextPattern Insert 텍스트 샘플</span><span class="sxs-lookup"><span data-stu-id="d2b67-148">TextPattern Insert Text Sample</span></span>](https://msdn.microsoft.com/library/67353f93-7ee2-42f2-ab76-5c078cf6ca16)  
 [<span data-ttu-id="d2b67-149">UI 자동화 트리 개요</span><span class="sxs-lookup"><span data-stu-id="d2b67-149">UI Automation Tree Overview</span></span>](../../../docs/framework/ui-automation/ui-automation-tree-overview.md)  
 [<span data-ttu-id="d2b67-150">UI 자동화의 캐싱 사용</span><span class="sxs-lookup"><span data-stu-id="d2b67-150">Use Caching in UI Automation</span></span>](../../../docs/framework/ui-automation/use-caching-in-ui-automation.md)
