---
title: UI 자동화 Dock 컨트롤 패턴 구현
ms.date: 03/30/2017
helpviewer_keywords:
- control patterns, dock
- dock control pattern
- UI Automation, dock control pattern
ms.assetid: ea3d2212-7c8e-4dd7-bf08-73141ca2d4fb
ms.openlocfilehash: 1e2084483a34709392b9d3ceab02472c36944132
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/23/2019
ms.locfileid: "74435442"
---
# <a name="implementing-the-ui-automation-dock-control-pattern"></a><span data-ttu-id="ec156-102">UI 자동화 Dock 컨트롤 패턴 구현</span><span class="sxs-lookup"><span data-stu-id="ec156-102">Implementing the UI Automation Dock Control Pattern</span></span>
> [!NOTE]
> <span data-ttu-id="ec156-103">이 설명서는 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] 네임스페이스에 정의된 관리되는 <xref:System.Windows.Automation> 클래스를 사용하려는 .NET Framework 개발자를 위한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="ec156-103">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="ec156-104">[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]에 대한 최신 정보는 [Windows 자동화 API: UI 자동화](/windows/win32/winauto/entry-uiauto-win32)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ec156-104">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](/windows/win32/winauto/entry-uiauto-win32).</span></span>  
  
 <span data-ttu-id="ec156-105">이 항목에서는 속성에 대한 정보를 포함하여 <xref:System.Windows.Automation.Provider.IDockProvider>를 구현하기 위한 지침 및 규칙을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="ec156-105">This topic introduces guidelines and conventions for implementing <xref:System.Windows.Automation.Provider.IDockProvider>, including information about properties.</span></span> <span data-ttu-id="ec156-106">추가 참조에 대한 링크는 항목 끝에 나열되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ec156-106">Links to additional references are listed at the end of the topic.</span></span>  
  
 <span data-ttu-id="ec156-107"><xref:System.Windows.Automation.DockPattern> 컨트롤 패턴은 도킹 컨테이너 내에서 컨트롤의 도킹 속성을 노출하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ec156-107">The <xref:System.Windows.Automation.DockPattern> control pattern is used to expose the dock properties of a control within a docking container.</span></span> <span data-ttu-id="ec156-108">도킹 컨테이너는 자식 요소를 서로 맞춰 가로 또는 세로로 정렬할 수 있는 컨트롤입니다.</span><span class="sxs-lookup"><span data-stu-id="ec156-108">A docking container is a control that allows you to arrange child elements horizontally and vertically, relative to each other.</span></span> <span data-ttu-id="ec156-109">이 컨트롤 패턴을 구현하는 컨트롤의 예제를 보려면 [Control Pattern Mapping for UI Automation Clients](control-pattern-mapping-for-ui-automation-clients.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ec156-109">For examples of controls that implement this control pattern, see [Control Pattern Mapping for UI Automation Clients](control-pattern-mapping-for-ui-automation-clients.md).</span></span>  
  
 <span data-ttu-id="ec156-110">![두 개의 도킹 된 자식을 포함 하는 도킹 컨테이너](./media/uia-dockpattern-dockingexample.PNG "UIA_DockPattern_DockingExample")</span><span class="sxs-lookup"><span data-stu-id="ec156-110">![Docking container with two docked children.](./media/uia-dockpattern-dockingexample.PNG "UIA_DockPattern_DockingExample")</span></span>  
<span data-ttu-id="ec156-111">Visual Studio에서 "클래스 뷰" 창이 DockPosition.Right이고 "오류 목록" 창이 DockPosition.Bottom인 도킹의 예</span><span class="sxs-lookup"><span data-stu-id="ec156-111">Docking Example from Visual Studio Where "Class View" Window Is DockPosition.Right and "Error List" Window Is DockPosition.Bottom</span></span>  
  
<a name="Implementation_Guidelines_and_Conventions"></a>   
## <a name="implementation-guidelines-and-conventions"></a><span data-ttu-id="ec156-112">구현 지침 및 규칙</span><span class="sxs-lookup"><span data-stu-id="ec156-112">Implementation Guidelines and Conventions</span></span>  
 <span data-ttu-id="ec156-113">Dock 컨트롤 패턴을 구현할 때는 다음 지침 및 규칙에 유의하세요.</span><span class="sxs-lookup"><span data-stu-id="ec156-113">When implementing the Dock control pattern, note the following guidelines and conventions:</span></span>  
  
- <span data-ttu-id="ec156-114"><xref:System.Windows.Automation.Provider.IDockProvider> 는 도킹 컨테이너의 속성 또는 도킹 컨테이너 내에 있는 현재 컨트롤에 인접하여 도킹된 컨트롤의 속성을 노출하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ec156-114"><xref:System.Windows.Automation.Provider.IDockProvider> does not expose any properties of the docking container or any properties of controls that are docked adjacent to the current control within the docking container.</span></span>  
  
- <span data-ttu-id="ec156-115">컨트롤은 현재 z-순서에 따라 서로 맞춰가며 도킹됩니다. z-순서 배치가 높을수록 도킹 컨테이너의 지정된 가장자리에서 멀리 배치됩니다.</span><span class="sxs-lookup"><span data-stu-id="ec156-115">Controls are docked relative to each other based on their current z-order; the higher their z-order placement, the farther they are placed from the specified edge of the docking container.</span></span>  
  
- <span data-ttu-id="ec156-116">도킹 컨테이너의 크기가 조정되는 경우, 컨테이너 내의 모든 도킹된 컨트롤은 원래 도킹되었던 가장자리와 같은 수준의 위치로 재조정됩니다.</span><span class="sxs-lookup"><span data-stu-id="ec156-116">If the docking container is resized, any docked controls within the container will be repositioned flush to the same edge to which they were originally docked.</span></span> <span data-ttu-id="ec156-117">또한 도킹된 컨트롤의 크기가 조정되어 <xref:System.Windows.Automation.DockPosition>의 도킹 동작에 따라 컨테이너 내의 모든 공간을 채웁니다.</span><span class="sxs-lookup"><span data-stu-id="ec156-117">The docked controls will also resize to fill any space within the container according to the docking behavior of their <xref:System.Windows.Automation.DockPosition>.</span></span> <span data-ttu-id="ec156-118">예를 들어, <xref:System.Windows.Automation.DockPosition.Top> 이 지정된 경우 컨트롤의 왼쪽과 오른쪽이 확장되어 사용 가능한 모든 공간을 채웁니다.</span><span class="sxs-lookup"><span data-stu-id="ec156-118">For example, if <xref:System.Windows.Automation.DockPosition.Top> is specified, the left and right sides of the control will expand to fill any available space.</span></span> <span data-ttu-id="ec156-119"><xref:System.Windows.Automation.DockPosition.Fill> 이 지정된 경우 컨트롤의 상/하/좌/우 모두 확장되어 사용 가능한 모든 공간을 채웁니다.</span><span class="sxs-lookup"><span data-stu-id="ec156-119">If <xref:System.Windows.Automation.DockPosition.Fill> is specified, all four sides of the control will expand to fill any available space.</span></span>  
  
- <span data-ttu-id="ec156-120">다중 모니터 시스템에서, 컨트롤은 현재 모니터의 왼쪽 또는 오른쪽에 도킹해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ec156-120">On a multi-monitor system, controls should dock to the left or right side of the current monitor.</span></span> <span data-ttu-id="ec156-121">그렇지 않을 경우, 가장 왼쪽에 있는 모니터의 왼쪽이나 가장 오른쪽에 있는 모니터의 오른쪽에 도킹해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ec156-121">If that is not possible, they should dock to the left side of the leftmost monitor or the right side of the rightmost monitor.</span></span>  
  
<a name="Required_Members_for_IDockProvider"></a>   
## <a name="required-members-for-idockprovider"></a><span data-ttu-id="ec156-122">IDockProvider에 필요한 멤버</span><span class="sxs-lookup"><span data-stu-id="ec156-122">Required Members for IDockProvider</span></span>  
 <span data-ttu-id="ec156-123">IDockProvider 인터페이스를 구현하려면 다음과 같은 속성 및 메서드가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="ec156-123">The following properties and methods are required for implementing the IDockProvider interface.</span></span>  
  
|<span data-ttu-id="ec156-124">필요한 멤버</span><span class="sxs-lookup"><span data-stu-id="ec156-124">Required members</span></span>|<span data-ttu-id="ec156-125">멤버 유형</span><span class="sxs-lookup"><span data-stu-id="ec156-125">Member type</span></span>|<span data-ttu-id="ec156-126">참고</span><span class="sxs-lookup"><span data-stu-id="ec156-126">Notes</span></span>|  
|----------------------|-----------------|-----------|  
|<xref:System.Windows.Automation.Provider.IDockProvider.DockPosition%2A>|<span data-ttu-id="ec156-127">속성</span><span class="sxs-lookup"><span data-stu-id="ec156-127">Property</span></span>|<span data-ttu-id="ec156-128">없음</span><span class="sxs-lookup"><span data-stu-id="ec156-128">None</span></span>|  
|<xref:System.Windows.Automation.Provider.IDockProvider.SetDockPosition%2A>|<span data-ttu-id="ec156-129">메서드</span><span class="sxs-lookup"><span data-stu-id="ec156-129">Method</span></span>|<span data-ttu-id="ec156-130">없음</span><span class="sxs-lookup"><span data-stu-id="ec156-130">None</span></span>|  
  
 <span data-ttu-id="ec156-131">이 컨트롤 패턴에 연결된 이벤트가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ec156-131">This control pattern has no associated events.</span></span>  
  
<a name="Exceptions"></a>   
## <a name="exceptions"></a><span data-ttu-id="ec156-132">예외</span><span class="sxs-lookup"><span data-stu-id="ec156-132">Exceptions</span></span>  
 <span data-ttu-id="ec156-133">공급자는 다음과 같은 예외를 throw해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ec156-133">Providers must throw the following exceptions.</span></span>  
  
|<span data-ttu-id="ec156-134">예외 형식</span><span class="sxs-lookup"><span data-stu-id="ec156-134">Exception type</span></span>|<span data-ttu-id="ec156-135">조건</span><span class="sxs-lookup"><span data-stu-id="ec156-135">Condition</span></span>|  
|--------------------|---------------|  
|<xref:System.InvalidOperationException>|<xref:System.Windows.Automation.Provider.IDockProvider.SetDockPosition%2A><br /><br /> <span data-ttu-id="ec156-136">-컨트롤이 요청 된 도킹 스타일을 실행할 수 없는 경우</span><span class="sxs-lookup"><span data-stu-id="ec156-136">-   When a control is not able to execute the requested dock style.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="ec156-137">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ec156-137">See also</span></span>

- [<span data-ttu-id="ec156-138">UI 자동화 컨트롤 패턴 개요</span><span class="sxs-lookup"><span data-stu-id="ec156-138">UI Automation Control Patterns Overview</span></span>](ui-automation-control-patterns-overview.md)
- [<span data-ttu-id="ec156-139">UI 자동화 공급자의 컨트롤 패턴 지원</span><span class="sxs-lookup"><span data-stu-id="ec156-139">Support Control Patterns in a UI Automation Provider</span></span>](support-control-patterns-in-a-ui-automation-provider.md)
- [<span data-ttu-id="ec156-140">클라이언트용 UI 자동화 컨트롤 패턴</span><span class="sxs-lookup"><span data-stu-id="ec156-140">UI Automation Control Patterns for Clients</span></span>](ui-automation-control-patterns-for-clients.md)
- [<span data-ttu-id="ec156-141">UI 자동화 트리 개요</span><span class="sxs-lookup"><span data-stu-id="ec156-141">UI Automation Tree Overview</span></span>](ui-automation-tree-overview.md)
- [<span data-ttu-id="ec156-142">UI 자동화의 캐싱 사용</span><span class="sxs-lookup"><span data-stu-id="ec156-142">Use Caching in UI Automation</span></span>](use-caching-in-ui-automation.md)
