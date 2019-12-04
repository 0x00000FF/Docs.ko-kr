---
title: UI 자동화에서 캐싱 사용
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- caching, UI Automation
- UI Automation, caching
ms.assetid: ec722dff-6009-4279-b86a-e18d3fa94ebf
ms.openlocfilehash: 679192b611a423e095ee9acc956d247364940edf
ms.sourcegitcommit: 32a575bf4adccc901f00e264f92b759ced633379
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/04/2019
ms.locfileid: "74800801"
---
# <a name="use-caching-in-ui-automation"></a><span data-ttu-id="d595d-102">UI 자동화에서 캐싱 사용</span><span class="sxs-lookup"><span data-stu-id="d595d-102">Use Caching in UI Automation</span></span>
> [!NOTE]
> <span data-ttu-id="d595d-103">이 설명서는 <xref:System.Windows.Automation> 네임스페이스에 정의된 관리되는 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] 클래스를 사용하려는 .NET Framework 개발자를 위한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="d595d-103">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="d595d-104">[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]에 대한 최신 정보는 [Windows 자동화 API: UI 자동화](/windows/win32/winauto/entry-uiauto-win32)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d595d-104">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](/windows/win32/winauto/entry-uiauto-win32).</span></span>  
  
 <span data-ttu-id="d595d-105">이 섹션에서는 <xref:System.Windows.Automation.AutomationElement> 속성 및 컨트롤 패턴의 캐싱을 구현하는 방법을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="d595d-105">This section shows how to implement caching of <xref:System.Windows.Automation.AutomationElement> properties and control patterns.</span></span>  
  
### <a name="activate-a-cache-request"></a><span data-ttu-id="d595d-106">캐시 요청 활성화</span><span class="sxs-lookup"><span data-stu-id="d595d-106">Activate a Cache Request</span></span>  
  
1. <span data-ttu-id="d595d-107"><xref:System.Windows.Automation.CacheRequest>를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="d595d-107">Create a <xref:System.Windows.Automation.CacheRequest>.</span></span>  
  
2. <span data-ttu-id="d595d-108"><xref:System.Windows.Automation.CacheRequest.Add%2A>를 사용하여 속성 및 패턴을 캐시에 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="d595d-108">Specify properties and patterns to cache by using <xref:System.Windows.Automation.CacheRequest.Add%2A>.</span></span>  
  
3. <span data-ttu-id="d595d-109"><xref:System.Windows.Automation.CacheRequest.TreeScope%2A> 속성을 설정하여 캐시 범위를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="d595d-109">Specify the scope of caching by setting the <xref:System.Windows.Automation.CacheRequest.TreeScope%2A> property.</span></span>  
  
4. <span data-ttu-id="d595d-110"><xref:System.Windows.Automation.CacheRequest.TreeFilter%2A> 속성을 설정하여 하위 트리의 뷰를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="d595d-110">Specify the view of the subtree by setting the <xref:System.Windows.Automation.CacheRequest.TreeFilter%2A> property.</span></span>  
  
5. <span data-ttu-id="d595d-111">개체에 대한 전체 참조를 검색하지 않음으로써 효율성을 높이려는 경우 <xref:System.Windows.Automation.CacheRequest.AutomationElementMode%2A> 속성을 <xref:System.Windows.Automation.AutomationElementMode.None> 으로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="d595d-111">Set the <xref:System.Windows.Automation.CacheRequest.AutomationElementMode%2A> property to <xref:System.Windows.Automation.AutomationElementMode.None> if you wish to increase efficiency by not retrieving a full reference to objects.</span></span> <span data-ttu-id="d595d-112">(이렇게 하면 해당 개체에서 현재 값을 검색할 수 없습니다.)</span><span class="sxs-lookup"><span data-stu-id="d595d-112">(This will make it impossible to retrieve current values from those objects.)</span></span>  
  
6. <span data-ttu-id="d595d-113">`using` 블록 (Microsoft Visual Basic .NET의`Using`) 내에서 <xref:System.Windows.Automation.CacheRequest.Activate%2A>를 사용 하 여 요청을 활성화 합니다.</span><span class="sxs-lookup"><span data-stu-id="d595d-113">Activate the request by using <xref:System.Windows.Automation.CacheRequest.Activate%2A> within a `using` block (`Using` in Microsoft Visual Basic .NET).</span></span>  
  
 <span data-ttu-id="d595d-114"><xref:System.Windows.Automation.AutomationElement> 개체를 가져오거나 이벤트를 구독한 후, <xref:System.Windows.Automation.CacheRequest.Pop%2A> ( <xref:System.Windows.Automation.CacheRequest.Push%2A> 가 사용된 경우)를 사용하거나 <xref:System.Windows.Automation.CacheRequest.Activate%2A>에서 생성된 개체를 삭제하여 요청을 비활성화합니다.</span><span class="sxs-lookup"><span data-stu-id="d595d-114">After obtaining <xref:System.Windows.Automation.AutomationElement> objects or subscribing to events, deactivate the request by using <xref:System.Windows.Automation.CacheRequest.Pop%2A> (if <xref:System.Windows.Automation.CacheRequest.Push%2A> was used) or by disposing the object created by <xref:System.Windows.Automation.CacheRequest.Activate%2A>.</span></span> <span data-ttu-id="d595d-115">`using` 블록 (Microsoft Visual Basic .NET의`Using`)에서 <xref:System.Windows.Automation.CacheRequest.Activate%2A>를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="d595d-115">(Use <xref:System.Windows.Automation.CacheRequest.Activate%2A> in a `using` block (`Using` in Microsoft Visual Basic .NET).</span></span>  
  
### <a name="cache-automationelement-properties"></a><span data-ttu-id="d595d-116">AutomationElement 속성 캐시</span><span class="sxs-lookup"><span data-stu-id="d595d-116">Cache AutomationElement Properties</span></span>  
  
1. <span data-ttu-id="d595d-117"><xref:System.Windows.Automation.CacheRequest> 가 활성 상태인 동안 <xref:System.Windows.Automation.AutomationElement> 또는 <xref:System.Windows.Automation.AutomationElement.FindFirst%2A> 을 사용하여 <xref:System.Windows.Automation.AutomationElement.FindAll%2A>개체를 가져옵니다. 또는 <xref:System.Windows.Automation.AutomationElement> 가 활성 상태였을 때 등록한 이벤트의 소스로 <xref:System.Windows.Automation.CacheRequest> 를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="d595d-117">While a <xref:System.Windows.Automation.CacheRequest> is active, obtain <xref:System.Windows.Automation.AutomationElement> objects by using <xref:System.Windows.Automation.AutomationElement.FindFirst%2A> or <xref:System.Windows.Automation.AutomationElement.FindAll%2A>; or obtain an <xref:System.Windows.Automation.AutomationElement> as the source of an event that you registered for when the <xref:System.Windows.Automation.CacheRequest> was active.</span></span> <span data-ttu-id="d595d-118">( <xref:System.Windows.Automation.CacheRequest> 를 GetUpdatedCache 또는 <xref:System.Windows.Automation.TreeWalker> 메서드 중 하나에 전달하여 캐시를 만들 수도 있습니다.)</span><span class="sxs-lookup"><span data-stu-id="d595d-118">(You can also create a cache by passing a <xref:System.Windows.Automation.CacheRequest> to GetUpdatedCache or one of the <xref:System.Windows.Automation.TreeWalker> methods.)</span></span>  
  
2. <span data-ttu-id="d595d-119"><xref:System.Windows.Automation.AutomationElement.GetCachedPropertyValue%2A> 를 사용하거나 <xref:System.Windows.Automation.AutomationElement.Cached%2A> 의 <xref:System.Windows.Automation.AutomationElement>속성에서 속성을 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="d595d-119">Use <xref:System.Windows.Automation.AutomationElement.GetCachedPropertyValue%2A> or retrieve a property from the <xref:System.Windows.Automation.AutomationElement.Cached%2A> property of the <xref:System.Windows.Automation.AutomationElement>.</span></span>  
  
### <a name="obtain-cached-patterns-and-their-properties"></a><span data-ttu-id="d595d-120">캐시된 패턴 및 해당 속성 가져오기</span><span class="sxs-lookup"><span data-stu-id="d595d-120">Obtain Cached Patterns and Their Properties</span></span>  
  
1. <span data-ttu-id="d595d-121"><xref:System.Windows.Automation.CacheRequest> 가 활성 상태인 동안 <xref:System.Windows.Automation.AutomationElement> 또는 <xref:System.Windows.Automation.AutomationElement.FindFirst%2A> 을 사용하여 <xref:System.Windows.Automation.AutomationElement.FindAll%2A>개체를 가져옵니다. 또는 <xref:System.Windows.Automation.AutomationElement> 가 활성 상태였을 때 등록한 이벤트의 소스로 <xref:System.Windows.Automation.CacheRequest> 를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="d595d-121">While a <xref:System.Windows.Automation.CacheRequest> is active, obtain <xref:System.Windows.Automation.AutomationElement> objects by using <xref:System.Windows.Automation.AutomationElement.FindFirst%2A> or <xref:System.Windows.Automation.AutomationElement.FindAll%2A>; or obtain an <xref:System.Windows.Automation.AutomationElement> as the source of an event that you registered for when the <xref:System.Windows.Automation.CacheRequest> was active.</span></span> <span data-ttu-id="d595d-122">( <xref:System.Windows.Automation.CacheRequest> 를 GetUpdatedCache 또는 <xref:System.Windows.Automation.TreeWalker> 메서드 중 하나에 전달하여 캐시를 만들 수도 있습니다.)</span><span class="sxs-lookup"><span data-stu-id="d595d-122">(You can also create a cache by passing a <xref:System.Windows.Automation.CacheRequest> to GetUpdatedCache or one of the <xref:System.Windows.Automation.TreeWalker> methods.)</span></span>  
  
2. <span data-ttu-id="d595d-123"><xref:System.Windows.Automation.AutomationElement.GetCachedPattern%2A> 또는 <xref:System.Windows.Automation.AutomationElement.TryGetCachedPattern%2A> 을 사용하여 캐시된 패턴을 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="d595d-123">Use <xref:System.Windows.Automation.AutomationElement.GetCachedPattern%2A> or <xref:System.Windows.Automation.AutomationElement.TryGetCachedPattern%2A> to retrieve a cached pattern.</span></span>  
  
3. <span data-ttu-id="d595d-124">컨트롤 패턴의 `Cached` 속성에서 속성 값을 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="d595d-124">Retrieve property values from the `Cached` property of the control pattern.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d595d-125">예제</span><span class="sxs-lookup"><span data-stu-id="d595d-125">Example</span></span>  
 <span data-ttu-id="d595d-126">다음 코드 예제는 <xref:System.Windows.Automation.CacheRequest.Activate%2A> 를 사용하여 <xref:System.Windows.Automation.CacheRequest>를 활성화하는 캐싱의 다양한 측면을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="d595d-126">The following code example shows various aspects of caching, using <xref:System.Windows.Automation.CacheRequest.Activate%2A> to activate the <xref:System.Windows.Automation.CacheRequest>.</span></span>  
  
 [!code-csharp[UIAClient_snip#107](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIAClient_snip/CSharp/ClientForm.cs#107)]
 [!code-vb[UIAClient_snip#107](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UIAClient_snip/VisualBasic/ClientForm.vb#107)]  
  
## <a name="example"></a><span data-ttu-id="d595d-127">예제</span><span class="sxs-lookup"><span data-stu-id="d595d-127">Example</span></span>  
 <span data-ttu-id="d595d-128">다음 코드 예제는 <xref:System.Windows.Automation.CacheRequest.Push%2A> 를 사용하여 <xref:System.Windows.Automation.CacheRequest>를 활성화하는 캐싱의 다양한 측면을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="d595d-128">The following code example shows various aspects of caching, using <xref:System.Windows.Automation.CacheRequest.Push%2A> to activate the <xref:System.Windows.Automation.CacheRequest>.</span></span> <span data-ttu-id="d595d-129">캐시 요청을 중첩하려는 경우를 제외하고, <xref:System.Windows.Automation.CacheRequest.Activate%2A>를 사용하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="d595d-129">Except when you wish to nest cache requests, it is preferable to use <xref:System.Windows.Automation.CacheRequest.Activate%2A>.</span></span>  
  
 [!code-csharp[UIAClient_snip#108](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIAClient_snip/CSharp/ClientForm.cs#108)]
 [!code-vb[UIAClient_snip#108](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UIAClient_snip/VisualBasic/ClientForm.vb#108)]  
  
## <a name="see-also"></a><span data-ttu-id="d595d-130">참조</span><span class="sxs-lookup"><span data-stu-id="d595d-130">See also</span></span>

- [<span data-ttu-id="d595d-131">UI 자동화 클라이언트의 캐싱</span><span class="sxs-lookup"><span data-stu-id="d595d-131">Caching in UI Automation Clients</span></span>](caching-in-ui-automation-clients.md)
