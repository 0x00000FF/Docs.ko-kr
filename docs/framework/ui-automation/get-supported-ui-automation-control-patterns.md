---
title: 지원되는 UI 자동화 컨트롤 패턴 가져오기
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- control patterns, getting
- UI Automation, getting control patterns
- getting, control patterns
ms.assetid: 006c54c9-50bf-48d9-a855-9d62eb95603a
ms.openlocfilehash: 64c5bae738cee5249e6c2406a2f94667ecb2931f
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59337021"
---
# <a name="get-supported-ui-automation-control-patterns"></a><span data-ttu-id="19313-102">지원되는 UI 자동화 컨트롤 패턴 가져오기</span><span class="sxs-lookup"><span data-stu-id="19313-102">Get Supported UI Automation Control Patterns</span></span>
> [!NOTE]
>  <span data-ttu-id="19313-103">이 설명서는 <xref:System.Windows.Automation> 네임스페이스에 정의된 관리되는 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] 클래스를 사용하려는 .NET Framework 개발자를 위한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="19313-103">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="19313-104">에 대 한 최신 정보에 대 한 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]를 참조 하세요 [Windows Automation API: UI 자동화](https://go.microsoft.com/fwlink/?LinkID=156746)합니다.</span><span class="sxs-lookup"><span data-stu-id="19313-104">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](https://go.microsoft.com/fwlink/?LinkID=156746).</span></span>  
  
 <span data-ttu-id="19313-105">이 항목에서는 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]  요소에서 컨트롤 패턴을 검색하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="19313-105">This topic shows how to retrieve control pattern objects from [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] elements.</span></span>  
  
### <a name="obtain-all-control-patterns"></a><span data-ttu-id="19313-106">모든 컨트롤 패턴 가져오기</span><span class="sxs-lookup"><span data-stu-id="19313-106">Obtain All Control Patterns</span></span>  
  
1. <span data-ttu-id="19313-107">사용할 컨트롤 패턴이 있는 <xref:System.Windows.Automation.AutomationElement>를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="19313-107">Get the <xref:System.Windows.Automation.AutomationElement> whose control patterns you are interested in.</span></span>  
  
2. <span data-ttu-id="19313-108">요소에서 모든 컨트롤 패턴을 가져오려면 <xref:System.Windows.Automation.AutomationElement.GetSupportedPatterns%2A>를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="19313-108">Call <xref:System.Windows.Automation.AutomationElement.GetSupportedPatterns%2A> to get all control patterns from the element.</span></span>  
  
> [!CAUTION]
>  <span data-ttu-id="19313-109">클라이언트가 <xref:System.Windows.Automation.AutomationElement.GetSupportedPatterns%2A>를 사용하지 않는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="19313-109">It is strongly recommended that a client not use <xref:System.Windows.Automation.AutomationElement.GetSupportedPatterns%2A>.</span></span> <span data-ttu-id="19313-110">이 메서드는 기존의 각 컨트롤 패턴에 대해 내부적으로 <xref:System.Windows.Automation.AutomationElement.GetCurrentPattern%2A>을 호출하기 때문에 성능에 심각한 영향을 줄 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="19313-110">Performance can be severely affected as this method calls <xref:System.Windows.Automation.AutomationElement.GetCurrentPattern%2A> internally for each existing control pattern.</span></span> <span data-ttu-id="19313-111">가능하면 클라이언트는 사용할 키 패턴에 대해 <xref:System.Windows.Automation.AutomationElement.GetCurrentPattern%2A>을 호출해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="19313-111">If possible, a client should call <xref:System.Windows.Automation.AutomationElement.GetCurrentPattern%2A> for the key patterns of interest.</span></span>  
  
### <a name="obtain-a-specific-control-pattern"></a><span data-ttu-id="19313-112">특정 컨트롤 패턴 가져오기</span><span class="sxs-lookup"><span data-stu-id="19313-112">Obtain a Specific Control Pattern</span></span>  
  
1. <span data-ttu-id="19313-113">사용할 컨트롤 패턴이 있는 <xref:System.Windows.Automation.AutomationElement>를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="19313-113">Get the <xref:System.Windows.Automation.AutomationElement> whose control patterns you are interested in.</span></span>  
  
2. <span data-ttu-id="19313-114">특정 패턴을 쿼리하려면 <xref:System.Windows.Automation.AutomationElement.GetCurrentPattern%2A> 또는 <xref:System.Windows.Automation.AutomationElement.TryGetCurrentPattern%2A>를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="19313-114">Call <xref:System.Windows.Automation.AutomationElement.GetCurrentPattern%2A> or <xref:System.Windows.Automation.AutomationElement.TryGetCurrentPattern%2A> to query for a specific pattern.</span></span> <span data-ttu-id="19313-115">이러한 메서드는 비슷하지만, 해당 패턴을 찾을 수 없는 경우 <xref:System.Windows.Automation.AutomationElement.GetCurrentPattern%2A>에서 예외가 발생하고 <xref:System.Windows.Automation.AutomationElement.TryGetCurrentPattern%2A>가 `false`를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="19313-115">These methods are similar, but if the pattern is not found, <xref:System.Windows.Automation.AutomationElement.GetCurrentPattern%2A> raises an exception, and <xref:System.Windows.Automation.AutomationElement.TryGetCurrentPattern%2A> returns `false`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="19313-116">예제</span><span class="sxs-lookup"><span data-stu-id="19313-116">Example</span></span>  
 <span data-ttu-id="19313-117">다음 예제에서는 목록 항목에 대해 <xref:System.Windows.Automation.AutomationElement>를 검색하고 해당 요소에서 <xref:System.Windows.Automation.SelectionItemPattern>을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="19313-117">The following example retrieves an <xref:System.Windows.Automation.AutomationElement> for a list item and obtains a <xref:System.Windows.Automation.SelectionItemPattern> from that element.</span></span>  
  
 [!code-csharp[UIAClient_snip#103](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIAClient_snip/CSharp/ClientForm.cs#103)]
 [!code-vb[UIAClient_snip#103](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UIAClient_snip/VisualBasic/ClientForm.vb#103)]  
  
## <a name="see-also"></a><span data-ttu-id="19313-118">참고자료</span><span class="sxs-lookup"><span data-stu-id="19313-118">See also</span></span>

- [<span data-ttu-id="19313-119">클라이언트용 UI 자동화 컨트롤 패턴</span><span class="sxs-lookup"><span data-stu-id="19313-119">UI Automation Control Patterns for Clients</span></span>](../../../docs/framework/ui-automation/ui-automation-control-patterns-for-clients.md)
