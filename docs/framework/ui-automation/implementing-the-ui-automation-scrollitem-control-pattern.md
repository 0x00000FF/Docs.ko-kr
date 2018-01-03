---
title: "UI 자동화 ScrollItem 컨트롤 패턴 구현"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-bcl
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- control patterns, Scroll Item
- UI Automation, Scroll Item control pattern
- Scroll Item control pattern
ms.assetid: 903bab5c-80c1-44d7-bdc2-0a418893b987
caps.latest.revision: "16"
author: Xansky
ms.author: mhopkins
manager: markl
ms.workload: dotnet
ms.openlocfilehash: ef089e72c3b8dd089db5022ea1808cee98c27ecd
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="implementing-the-ui-automation-scrollitem-control-pattern"></a><span data-ttu-id="4ed94-102">UI 자동화 ScrollItem 컨트롤 패턴 구현</span><span class="sxs-lookup"><span data-stu-id="4ed94-102">Implementing the UI Automation ScrollItem Control Pattern</span></span>
> [!NOTE]
>  <span data-ttu-id="4ed94-103">이 설명서는 <xref:System.Windows.Automation> 네임스페이스에 정의된 관리되는 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] 클래스를 사용하려는 .NET Framework 개발자를 위한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="4ed94-103">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="4ed94-104">[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]에 대한 최신 정보는 [Windows 자동화 API: UI 자동화](http://go.microsoft.com/fwlink/?LinkID=156746)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="4ed94-104">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](http://go.microsoft.com/fwlink/?LinkID=156746).</span></span>  
  
 <span data-ttu-id="4ed94-105">지침 및 규칙을 구현 하기 위한이 항목에서는 소개는 <xref:System.Windows.Automation.Provider.IScrollItemProvider>, 속성, 메서드 및 이벤트에 대 한 정보를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="4ed94-105">This topic introduces guidelines and conventions for implementing the <xref:System.Windows.Automation.Provider.IScrollItemProvider>, including information about properties, methods, and events.</span></span> <span data-ttu-id="4ed94-106">추가 참조에 대한 링크는 항목 끝에 나열되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4ed94-106">Links to additional references are listed at the end of the topic.</span></span>  
  
 <span data-ttu-id="4ed94-107"><xref:System.Windows.Automation.ScrollItemPattern> 구현 하는 컨테이너의 개별 자식 컨트롤을 지 원하는 컨트롤 패턴은 사용 <xref:System.Windows.Automation.Provider.IScrollProvider>합니다.</span><span class="sxs-lookup"><span data-stu-id="4ed94-107">The <xref:System.Windows.Automation.ScrollItemPattern> control pattern is used to support individual child controls of containers that implement <xref:System.Windows.Automation.Provider.IScrollProvider>.</span></span> <span data-ttu-id="4ed94-108">이 컨트롤 패턴은 자식 컨트롤과 해당 컨테이너 간에 통신 채널 역할을 하여 컨테이너가 자식 컨트롤이 표시되도록 뷰포트 내에 현재 표시된 콘텐츠(또는 영역)를 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4ed94-108">This control pattern acts as a communication channel between a child control and its container to ensure that the container can change the currently visible content (or region) within its viewport to display the child control.</span></span> <span data-ttu-id="4ed94-109">이 컨트롤 패턴을 구현하는 컨트롤의 예제를 보려면 [Control Pattern Mapping for UI Automation Clients](../../../docs/framework/ui-automation/control-pattern-mapping-for-ui-automation-clients.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="4ed94-109">For examples of controls that implement this control pattern, see [Control Pattern Mapping for UI Automation Clients](../../../docs/framework/ui-automation/control-pattern-mapping-for-ui-automation-clients.md).</span></span>  
  
<a name="Implementation_Guidelines_and_Conventions"></a>   
## <a name="implementation-guidelines-and-conventions"></a><span data-ttu-id="4ed94-110">구현 지침 및 규칙</span><span class="sxs-lookup"><span data-stu-id="4ed94-110">Implementation Guidelines and Conventions</span></span>  
 <span data-ttu-id="4ed94-111">Scroll Item 컨트롤 패턴을 구현할 때는 다음 지침 및 규칙에 유의하세요.</span><span class="sxs-lookup"><span data-stu-id="4ed94-111">When implementing the Scroll Item control pattern, note the following guidelines and conventions:</span></span>  
  
-   <span data-ttu-id="4ed94-112">창 또는 캔버스 컨트롤 내에 포함된 항목은 IScrollItemProvider 인터페이스를 구현하는 데 필요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4ed94-112">Items contained within a Window or Canvas control are not required to implement the IScrollItemProvider interface.</span></span> <span data-ttu-id="4ed94-113">그러나 대신,를 노출 해야 올바른 위치를는 <xref:System.Windows.Automation.AutomationElementIdentifiers.BoundingRectangleProperty>합니다.</span><span class="sxs-lookup"><span data-stu-id="4ed94-113">As an alternative, however, they must expose a valid location for the <xref:System.Windows.Automation.AutomationElementIdentifiers.BoundingRectangleProperty>.</span></span> <span data-ttu-id="4ed94-114">이렇게 하면 UI 자동화 클라이언트 응용 프로그램이 컨테이너의 <xref:System.Windows.Automation.ScrollPattern> 컨트롤 패턴 메서드를 사용하여 자식 항목을 표시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4ed94-114">This will allow a UI Automation client application to use the <xref:System.Windows.Automation.ScrollPattern> control pattern methods on the container to display the child item.</span></span>  
  
<a name="Required_Members_for_IScrollItemProvider"></a>   
## <a name="required-members-for-iscrollitemprovider"></a><span data-ttu-id="4ed94-115">IScrollItemProvider에 필요한 멤버</span><span class="sxs-lookup"><span data-stu-id="4ed94-115">Required Members for IScrollItemProvider</span></span>  
 <span data-ttu-id="4ed94-116">다음 메서드는 IScrollProvider 인터페이스를 구현하는 데 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="4ed94-116">The following method is required for implementing the IScrollProvider interface.</span></span>  
  
|<span data-ttu-id="4ed94-117">필요한 멤버</span><span class="sxs-lookup"><span data-stu-id="4ed94-117">Required members</span></span>|<span data-ttu-id="4ed94-118">멤버 형식</span><span class="sxs-lookup"><span data-stu-id="4ed94-118">Member type</span></span>|<span data-ttu-id="4ed94-119">노트</span><span class="sxs-lookup"><span data-stu-id="4ed94-119">Notes</span></span>|  
|----------------------|-----------------|-----------|  
|<xref:System.Windows.Automation.Provider.IScrollItemProvider.ScrollIntoView%2A>|<span data-ttu-id="4ed94-120">메서드</span><span class="sxs-lookup"><span data-stu-id="4ed94-120">-   Method</span></span>|<span data-ttu-id="4ed94-121">없음</span><span class="sxs-lookup"><span data-stu-id="4ed94-121">None</span></span>|  
  
 <span data-ttu-id="4ed94-122">이 컨트롤 패턴에는 연결된 속성 또는 이벤트가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="4ed94-122">This control pattern has no associated properties or events.</span></span>  
  
<a name="Exceptions"></a>   
## <a name="exceptions"></a><span data-ttu-id="4ed94-123">예외</span><span class="sxs-lookup"><span data-stu-id="4ed94-123">Exceptions</span></span>  
 <span data-ttu-id="4ed94-124">공급자는 다음과 같은 예외를 throw해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4ed94-124">Providers must throw the following exceptions.</span></span>  
  
|<span data-ttu-id="4ed94-125">예외 형식</span><span class="sxs-lookup"><span data-stu-id="4ed94-125">Exception Type</span></span>|<span data-ttu-id="4ed94-126">조건</span><span class="sxs-lookup"><span data-stu-id="4ed94-126">Condition</span></span>|  
|--------------------|---------------|  
|<xref:System.InvalidOperationException>|<span data-ttu-id="4ed94-127">항목을 스크롤하여 볼 수 없는 경우:</span><span class="sxs-lookup"><span data-stu-id="4ed94-127">If an item cannot be scrolled into view:</span></span><br /><br /> -   <xref:System.Windows.Automation.ScrollItemPattern.ScrollIntoView%2A>|  
  
## <a name="see-also"></a><span data-ttu-id="4ed94-128">참고 항목</span><span class="sxs-lookup"><span data-stu-id="4ed94-128">See Also</span></span>  
 [<span data-ttu-id="4ed94-129">UI 자동화 컨트롤 패턴 개요</span><span class="sxs-lookup"><span data-stu-id="4ed94-129">UI Automation Control Patterns Overview</span></span>](../../../docs/framework/ui-automation/ui-automation-control-patterns-overview.md)  
 [<span data-ttu-id="4ed94-130">UI 자동화 공급자의 컨트롤 패턴 지원</span><span class="sxs-lookup"><span data-stu-id="4ed94-130">Support Control Patterns in a UI Automation Provider</span></span>](../../../docs/framework/ui-automation/support-control-patterns-in-a-ui-automation-provider.md)  
 [<span data-ttu-id="4ed94-131">클라이언트용 UI 자동화 컨트롤 패턴</span><span class="sxs-lookup"><span data-stu-id="4ed94-131">UI Automation Control Patterns for Clients</span></span>](../../../docs/framework/ui-automation/ui-automation-control-patterns-for-clients.md)  
 [<span data-ttu-id="4ed94-132">UI 자동화 트리 개요</span><span class="sxs-lookup"><span data-stu-id="4ed94-132">UI Automation Tree Overview</span></span>](../../../docs/framework/ui-automation/ui-automation-tree-overview.md)  
 [<span data-ttu-id="4ed94-133">UI 자동화의 캐싱 사용</span><span class="sxs-lookup"><span data-stu-id="4ed94-133">Use Caching in UI Automation</span></span>](../../../docs/framework/ui-automation/use-caching-in-ui-automation.md)
