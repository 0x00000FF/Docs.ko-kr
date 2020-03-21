---
title: UI 자동화 Value 컨트롤 패턴 구현
ms.date: 03/30/2017
helpviewer_keywords:
- control patterns, Value
- UI Automation, Value control pattern
- Value control pattern
ms.assetid: b0fcdd87-3add-4345-bca9-e891205e02ba
ms.openlocfilehash: eb77f26bbe3546a3f90804c3648f8547fb6abad0
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79180084"
---
# <a name="implementing-the-ui-automation-value-control-pattern"></a><span data-ttu-id="d2657-102">UI 자동화 Value 컨트롤 패턴 구현</span><span class="sxs-lookup"><span data-stu-id="d2657-102">Implementing the UI Automation Value Control Pattern</span></span>
> [!NOTE]
> <span data-ttu-id="d2657-103">이 설명서는 <xref:System.Windows.Automation> 네임스페이스에 정의된 관리되는 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] 클래스를 사용하려는 .NET Framework 개발자를 위한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="d2657-103">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="d2657-104">[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]에 대한 최신 정보는 [Windows 자동화 API: UI 자동화](/windows/win32/winauto/entry-uiauto-win32)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d2657-104">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](/windows/win32/winauto/entry-uiauto-win32).</span></span>  
  
 <span data-ttu-id="d2657-105">이 항목에서는 이벤트 및 속성에 대한 정보를 포함하여 <xref:System.Windows.Automation.Provider.IValueProvider>를 구현하기 위한 지침 및 규칙을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="d2657-105">This topic introduces guidelines and conventions for implementing <xref:System.Windows.Automation.Provider.IValueProvider>, including information on events and properties.</span></span> <span data-ttu-id="d2657-106">추가 참조에 대한 링크는 항목 끝에 나열되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d2657-106">Links to additional references are listed at the end of the topic.</span></span>  
  
 <span data-ttu-id="d2657-107"><xref:System.Windows.Automation.ValuePattern> 컨트롤 패턴는 범위에 걸쳐 있지 않은 내장 값이 있고 문자열로 나타낼 수 있는 컨트롤을 지원하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="d2657-107">The <xref:System.Windows.Automation.ValuePattern> control pattern is used to support controls that have an intrinsic value not spanning a range and that can be represented as a string.</span></span> <span data-ttu-id="d2657-108">이 문자열은 컨트롤 및 해당 설정에 따라 편집할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d2657-108">This string can be editable, depending on the control and its settings.</span></span> <span data-ttu-id="d2657-109">이 패턴을 구현하는 컨트롤의 예제를 보려면 [Control Pattern Mapping for UI Automation Clients](control-pattern-mapping-for-ui-automation-clients.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d2657-109">For examples of controls that implement this pattern, see [Control Pattern Mapping for UI Automation Clients](control-pattern-mapping-for-ui-automation-clients.md).</span></span>  
  
<a name="Implementation_Guidelines_and_Conventions"></a>
## <a name="implementation-guidelines-and-conventions"></a><span data-ttu-id="d2657-110">구현 지침 및 규칙</span><span class="sxs-lookup"><span data-stu-id="d2657-110">Implementation Guidelines and Conventions</span></span>  
 <span data-ttu-id="d2657-111">Value 컨트롤 패턴을 구현할 때는 다음 지침 및 규칙에 유의하세요.</span><span class="sxs-lookup"><span data-stu-id="d2657-111">When implementing the Value control pattern, note the following guidelines and conventions:</span></span>  
  
- <span data-ttu-id="d2657-112"><xref:System.Windows.Automation.ControlType.ListItem> 및 <xref:System.Windows.Automation.ControlType.TreeItem> 과 같은 컨트롤은 항목이 편집 가능한 경우 컨트롤의 현재 편집 모드와 관계 없이 <xref:System.Windows.Automation.ValuePattern> 을 지원해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2657-112">Controls such as <xref:System.Windows.Automation.ControlType.ListItem> and <xref:System.Windows.Automation.ControlType.TreeItem> must support <xref:System.Windows.Automation.ValuePattern> if the value of any of the items is editable, regardless of the current edit mode of the control.</span></span> <span data-ttu-id="d2657-113">자식 항목이 편집 가능한 경우 부모 컨트롤이 <xref:System.Windows.Automation.ValuePattern> 도 지원해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2657-113">The parent control must also support <xref:System.Windows.Automation.ValuePattern> if the child items are editable.</span></span>  
  
 <span data-ttu-id="d2657-114">![편집할 수 있는 목록 항목](./media/uia-valuepattern-editable-listitem.PNG "UIA_ValuePattern_Editable_ListItem")</span><span class="sxs-lookup"><span data-stu-id="d2657-114">![Editable list item.](./media/uia-valuepattern-editable-listitem.PNG "UIA_ValuePattern_Editable_ListItem")</span></span>  
<span data-ttu-id="d2657-115">편집 가능한 목록 항목의 예</span><span class="sxs-lookup"><span data-stu-id="d2657-115">Example of an Editable List Item</span></span>  
  
- <span data-ttu-id="d2657-116">단일 줄 편집 컨트롤은 <xref:System.Windows.Automation.Provider.IValueProvider>를 구현하여 해당 내용에 대한 프로그래밍 방식 액세스를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="d2657-116">Single-line edit controls support programmatic access to their contents by implementing <xref:System.Windows.Automation.Provider.IValueProvider>.</span></span> <span data-ttu-id="d2657-117">하지만 여러 줄 편집 컨트롤은 <xref:System.Windows.Automation.Provider.IValueProvider>를 구현하지 않습니다. 대신, <xref:System.Windows.Automation.Provider.ITextProvider>를 구현하여 내용에 대한 액세스를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="d2657-117">However, multi-line edit controls do not implement <xref:System.Windows.Automation.Provider.IValueProvider>; instead they provide access to their content by implementing <xref:System.Windows.Automation.Provider.ITextProvider>.</span></span>  
  
- <span data-ttu-id="d2657-118">여러 줄 편집 컨트롤의 텍스트 내용을 검색하려면 컨트롤이 <xref:System.Windows.Automation.Provider.ITextProvider>를 구현해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2657-118">To retrieve the textual contents of a multi-line edit control, the control must implement <xref:System.Windows.Automation.Provider.ITextProvider>.</span></span> <span data-ttu-id="d2657-119">하지만 <xref:System.Windows.Automation.Provider.ITextProvider> 는 컨트롤의 값 설정을 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d2657-119">However, <xref:System.Windows.Automation.Provider.ITextProvider> does not support setting the value of a control.</span></span>  
  
- <span data-ttu-id="d2657-120"><xref:System.Windows.Automation.Provider.IValueProvider> 는 서식 정보 및 하위 문자열 값 검색을 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d2657-120"><xref:System.Windows.Automation.Provider.IValueProvider> does not support the retrieval of formatting information or substring values.</span></span> <span data-ttu-id="d2657-121">이러한 시나리오에서는 <xref:System.Windows.Automation.Provider.ITextProvider> 를 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="d2657-121">Implement <xref:System.Windows.Automation.Provider.ITextProvider> in these scenarios.</span></span>  
  
- <span data-ttu-id="d2657-122"><xref:System.Windows.Automation.Provider.IValueProvider>색상 값(예: "노란색")과 이에 상응하는 내부 RGB 구조 간의 문자열 매핑을 지원하는 Microsoft Word의 **색상 선택** 선택 컨트롤(아래 그림)과 같은 컨트롤에 의해 구현되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2657-122"><xref:System.Windows.Automation.Provider.IValueProvider> must be implemented by controls such as the **Color Picker** selection control from Microsoft Word (illustrated below), which supports string mapping between a color value (for example, "yellow") and an equivalent internal RGB structure.</span></span>  
  
 <span data-ttu-id="d2657-123">![노란색이 강조 표시된 색 선택](./media/uia-valuepattern-colorpicker.png "UIA_ValuePattern_ColorPicker")</span><span class="sxs-lookup"><span data-stu-id="d2657-123">![Color picker with yellow highlighted.](./media/uia-valuepattern-colorpicker.png "UIA_ValuePattern_ColorPicker")</span></span>  
<span data-ttu-id="d2657-124">색 견본 문자열 매핑의 예</span><span class="sxs-lookup"><span data-stu-id="d2657-124">Example of Color Swatch String Mapping</span></span>  
  
- <span data-ttu-id="d2657-125">컨트롤에서 <xref:System.Windows.Automation.AutomationElement.IsEnabledProperty> 가 `true` 로 설정되고 <xref:System.Windows.Automation.ValuePattern.IsReadOnlyProperty> 가 `false` 로 설정되어야 <xref:System.Windows.Automation.Provider.IValueProvider.SetValue%2A>를 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d2657-125">A control should have its <xref:System.Windows.Automation.AutomationElement.IsEnabledProperty> set to `true` and its <xref:System.Windows.Automation.ValuePattern.IsReadOnlyProperty> set to `false` before allowing a call to <xref:System.Windows.Automation.Provider.IValueProvider.SetValue%2A>.</span></span>  
  
<a name="Required_Members_for_the_IValueProvider_Interface"></a>
## <a name="required-members-for-ivalueprovider"></a><span data-ttu-id="d2657-126">IValueProvider에 필요한 멤버</span><span class="sxs-lookup"><span data-stu-id="d2657-126">Required Members for IValueProvider</span></span>  
 <span data-ttu-id="d2657-127"><xref:System.Windows.Automation.Provider.IValueProvider>를 구현하려면 다음과 같은 속성 및 메서드가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="d2657-127">The following properties and methods are required for implementing <xref:System.Windows.Automation.Provider.IValueProvider>.</span></span>  
  
|<span data-ttu-id="d2657-128">필요한 멤버</span><span class="sxs-lookup"><span data-stu-id="d2657-128">Required members</span></span>|<span data-ttu-id="d2657-129">멤버 형식</span><span class="sxs-lookup"><span data-stu-id="d2657-129">Member type</span></span>|<span data-ttu-id="d2657-130">메모</span><span class="sxs-lookup"><span data-stu-id="d2657-130">Notes</span></span>|  
|----------------------|-----------------|-----------|  
|<xref:System.Windows.Automation.ValuePattern.IsReadOnlyProperty>|<span data-ttu-id="d2657-131">속성</span><span class="sxs-lookup"><span data-stu-id="d2657-131">Property</span></span>|<span data-ttu-id="d2657-132">None</span><span class="sxs-lookup"><span data-stu-id="d2657-132">None</span></span>|  
|<xref:System.Windows.Automation.ValuePattern.ValueProperty>|<span data-ttu-id="d2657-133">속성</span><span class="sxs-lookup"><span data-stu-id="d2657-133">Property</span></span>|<span data-ttu-id="d2657-134">None</span><span class="sxs-lookup"><span data-stu-id="d2657-134">None</span></span>|  
|<xref:System.Windows.Automation.ValuePattern.SetValue%2A>|<span data-ttu-id="d2657-135">방법</span><span class="sxs-lookup"><span data-stu-id="d2657-135">Method</span></span>|<span data-ttu-id="d2657-136">None</span><span class="sxs-lookup"><span data-stu-id="d2657-136">None</span></span>|  
  
<a name="Exceptions"></a>
## <a name="exceptions"></a><span data-ttu-id="d2657-137">예외</span><span class="sxs-lookup"><span data-stu-id="d2657-137">Exceptions</span></span>  
 <span data-ttu-id="d2657-138">공급자는 다음과 같은 예외를 throw해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2657-138">Providers must throw the following exceptions.</span></span>  
  
|<span data-ttu-id="d2657-139">예외 형식</span><span class="sxs-lookup"><span data-stu-id="d2657-139">Exception type</span></span>|<span data-ttu-id="d2657-140">조건</span><span class="sxs-lookup"><span data-stu-id="d2657-140">Condition</span></span>|  
|--------------------|---------------|  
|<xref:System.InvalidOperationException>|<xref:System.Windows.Automation.ValuePattern.SetValue%2A><br /><br /> <span data-ttu-id="d2657-141">- 로캘 관련 정보가 잘못된 형식의 날짜와 같은 잘못된 형식으로 컨트롤에 전달되는 경우.</span><span class="sxs-lookup"><span data-stu-id="d2657-141">-   If locale-specific information is passed to a control in an incorrect format such as an incorrectly formatted date.</span></span>|  
|<xref:System.ArgumentException>|<xref:System.Windows.Automation.ValuePattern.SetValue%2A><br /><br /> <span data-ttu-id="d2657-142">- 새 값을 문자열에서 컨트롤이 인식하는 형식으로 변환할 수 없는 경우.</span><span class="sxs-lookup"><span data-stu-id="d2657-142">-   If a new value cannot be converted from a string to a format the control recognizes.</span></span>|  
|<xref:System.Windows.Automation.ElementNotEnabledException>|<xref:System.Windows.Automation.ValuePattern.SetValue%2A><br /><br /> <span data-ttu-id="d2657-143">- 활성화되지 않은 컨트롤을 조작하려고 시도하는 경우</span><span class="sxs-lookup"><span data-stu-id="d2657-143">-   When an attempt is made to manipulate a control that is not enabled.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="d2657-144">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d2657-144">See also</span></span>

- [<span data-ttu-id="d2657-145">UI 자동화 컨트롤 패턴 개요</span><span class="sxs-lookup"><span data-stu-id="d2657-145">UI Automation Control Patterns Overview</span></span>](ui-automation-control-patterns-overview.md)
- [<span data-ttu-id="d2657-146">UI 자동화 공급자의 컨트롤 패턴 지원</span><span class="sxs-lookup"><span data-stu-id="d2657-146">Support Control Patterns in a UI Automation Provider</span></span>](support-control-patterns-in-a-ui-automation-provider.md)
- [<span data-ttu-id="d2657-147">클라이언트용 UI 자동화 컨트롤 패턴</span><span class="sxs-lookup"><span data-stu-id="d2657-147">UI Automation Control Patterns for Clients</span></span>](ui-automation-control-patterns-for-clients.md)
- [<span data-ttu-id="d2657-148">값 패턴 삽입 텍스트 샘플</span><span class="sxs-lookup"><span data-stu-id="d2657-148">ValuePattern Insert Text Sample</span></span>](https://github.com/Microsoft/WPF-Samples/tree/master/Accessibility/InsertText)
- [<span data-ttu-id="d2657-149">UI Automation Tree Overview</span><span class="sxs-lookup"><span data-stu-id="d2657-149">UI Automation Tree Overview</span></span>](ui-automation-tree-overview.md)
- [<span data-ttu-id="d2657-150">UI 자동화의 캐싱 사용</span><span class="sxs-lookup"><span data-stu-id="d2657-150">Use Caching in UI Automation</span></span>](use-caching-in-ui-automation.md)
