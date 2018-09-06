---
title: UI 자동화 이벤트 구독
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- UI Automation, subscribing to events
- subscribing to UI Automation events
- events, subscribing to
- listening for events
ms.assetid: b688effa-b3e8-4b05-944d-05ed89a245aa
author: Xansky
ms.author: mhopkins
manager: markl
ms.openlocfilehash: c6845a85f9d3e07a4ecc9aad1ec11df8cdbc1f7a
ms.sourcegitcommit: a885cc8c3e444ca6471348893d5373c6e9e49a47
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/06/2018
ms.locfileid: "43870278"
---
# <a name="subscribe-to-ui-automation-events"></a><span data-ttu-id="b5375-102">UI 자동화 이벤트 구독</span><span class="sxs-lookup"><span data-stu-id="b5375-102">Subscribe to UI Automation Events</span></span>
> [!NOTE]
>  <span data-ttu-id="b5375-103">이 설명서는 <xref:System.Windows.Automation> 네임스페이스에 정의된 관리되는 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] 클래스를 사용하려는 .NET Framework 개발자를 위한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="b5375-103">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="b5375-104">에 대 한 최신 정보에 대 한 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]를 참조 하세요 [Windows Automation API: UI 자동화](https://go.microsoft.com/fwlink/?LinkID=156746)합니다.</span><span class="sxs-lookup"><span data-stu-id="b5375-104">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](https://go.microsoft.com/fwlink/?LinkID=156746).</span></span>  
  
 <span data-ttu-id="b5375-105">이 항목에서는 UI 자동화 공급자가 발생시킨 이벤트를 구독하는 방법을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="b5375-105">This topic shows how to subscribe to events raised by UI Automation providers.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b5375-106">예제</span><span class="sxs-lookup"><span data-stu-id="b5375-106">Example</span></span>  
 <span data-ttu-id="b5375-107">다음 예제 코드는 단추와 같은 컨트롤을 호출할 때 발생하는 이벤트에 대한 이벤트 처리기를 등록하고, 응용 프로그램 폼이 닫힐 때 이벤트 처리기를 제거하는 방법을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="b5375-107">The following example code registers an event handler for the event that is raised when a control such as a button is invoked, and removes it when the application form closes.</span></span> <span data-ttu-id="b5375-108">이벤트로 식별 되는 <xref:System.Windows.Automation.AutomationEvent> 매개 변수로 전달 된 <xref:System.Windows.Automation.Automation.AddAutomationEventHandler%2A>합니다.</span><span class="sxs-lookup"><span data-stu-id="b5375-108">The event is identified by an <xref:System.Windows.Automation.AutomationEvent> passed as a parameter to <xref:System.Windows.Automation.Automation.AddAutomationEventHandler%2A>.</span></span>  
  
 [!code-csharp[UIAClient_snip#101](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIAClient_snip/CSharp/ClientForm.cs#101)]
 [!code-vb[UIAClient_snip#101](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UIAClient_snip/VisualBasic/ClientForm.vb#101)]  
  
## <a name="example"></a><span data-ttu-id="b5375-109">예제</span><span class="sxs-lookup"><span data-stu-id="b5375-109">Example</span></span>  
 <span data-ttu-id="b5375-110">다음 예제에서는 사용 하는 방법을 보여 줍니다 [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] 포커스가 변경 될 때 발생 하는 이벤트를 구독할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b5375-110">The following example shows how to use [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] to subscribe to an event that is raised when the focus changes.</span></span> <span data-ttu-id="b5375-111">이벤트 처리기는 응용 프로그램 종료 시 호출될 수 있는 메서드에서 등록 취소되거나, UI 이벤트 알림이 더 이상 필요하지 않은 경우에 등록 취소됩니다.</span><span class="sxs-lookup"><span data-stu-id="b5375-111">The event handler is unregistered in a method that could be called on application shutdown, or when notification of UI events is no longer required.</span></span>  
  
 [!code-csharp[UIAClient_snip#102](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIAClient_snip/CSharp/ClientForm.cs#102)]
 [!code-vb[UIAClient_snip#102](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UIAClient_snip/VisualBasic/ClientForm.vb#102)]  
  
## <a name="see-also"></a><span data-ttu-id="b5375-112">참고 항목</span><span class="sxs-lookup"><span data-stu-id="b5375-112">See Also</span></span>  
 <xref:System.Windows.Automation.Automation.AddAutomationEventHandler%2A>  
 <xref:System.Windows.Automation.Automation.RemoveAllEventHandlers%2A>  
 <xref:System.Windows.Automation.Automation.RemoveAutomationEventHandler%2A>  
 [<span data-ttu-id="b5375-113">UI 자동화 이벤트 개요</span><span class="sxs-lookup"><span data-stu-id="b5375-113">UI Automation Events Overview</span></span>](../../../docs/framework/ui-automation/ui-automation-events-overview.md)
