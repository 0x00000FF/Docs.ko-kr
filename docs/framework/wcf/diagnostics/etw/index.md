---
title: ETW를 사용한 분석 추적
ms.date: 03/30/2017
helpviewer_keywords:
- diagnostics [WCF], analytic tracing
- administration [WCF], analytic tracing
- analytic tracing [WCF]
ms.assetid: 1d518e47-a38d-41e8-93d7-8c3b361f6a56
ms.openlocfilehash: cff13439995d8a90da15b7afa15723f21574e35e
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61962047"
---
# <a name="analytic-tracing-with-etw"></a><span data-ttu-id="c96c8-102">ETW를 사용한 분석 추적</span><span class="sxs-lookup"><span data-stu-id="c96c8-102">Analytic Tracing with ETW</span></span>
<span data-ttu-id="c96c8-103">Windows Communication Foundation (WCF) 분석 추적에는 WCF 서비스를 실행 하는 동안 진단 정보를 캡처할 수가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c96c8-103">Windows Communication Foundation (WCF) analytic tracing offers a way to capture diagnostic information during the execution of a WCF service.</span></span> <span data-ttu-id="c96c8-104">프로덕션 환경에서 WCF 서비스의 문제를 해결할 수 WCF 스택의 주요 지점에서 WCF 분석 추적 이벤트를 내보냅니다.</span><span class="sxs-lookup"><span data-stu-id="c96c8-104">WCF analytic tracing events are emitted at key points in the WCF stack to allow troubleshooting of WCF services in a production environment.</span></span> <span data-ttu-id="c96c8-105">WCF 서비스에 대 한 분석 추적에 미치는 영향을 최소화 프로덕션 서버의 성능에 호스팅하는 [!INCLUDE[netfx_current_long](../../../../../includes/netfx-current-long-md.md)] WCF 서비스 처럼 이러한 이벤트에 대 한 Windows ETW (이벤트 추적) 세션에 매우 효율적으로 내보내집니다.</span><span class="sxs-lookup"><span data-stu-id="c96c8-105">Analytic tracing for WCF services has minimal impact on the performance of a product server that hosts [!INCLUDE[netfx_current_long](../../../../../includes/netfx-current-long-md.md)] WCF services as these events are very efficiently emitted to an Event Tracing for Windows (ETW) session.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="c96c8-106">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="c96c8-106">In This Section</span></span>  
 [<span data-ttu-id="c96c8-107">분석 추적 개요</span><span class="sxs-lookup"><span data-stu-id="c96c8-107">Analytic Tracing Overview</span></span>](../../../../../docs/framework/wcf/diagnostics/etw/analytic-tracing-overview.md)  
 <span data-ttu-id="c96c8-108">WCF 분석 추적에서 작동 하는 방법에 대해 설명 [!INCLUDE[netfx_current_long](../../../../../includes/netfx-current-long-md.md)]합니다.</span><span class="sxs-lookup"><span data-stu-id="c96c8-108">Discusses how WCF analytic tracing works in [!INCLUDE[netfx_current_long](../../../../../includes/netfx-current-long-md.md)].</span></span>  
  
 [<span data-ttu-id="c96c8-109">동적으로 분석 추적을 사용하도록 설정</span><span class="sxs-lookup"><span data-stu-id="c96c8-109">Dynamically Enabling Analytic Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/etw/dynamically-enabling-analytic-tracing.md)  
 <span data-ttu-id="c96c8-110">ETW를 사용하여 추적을 동적으로 사용하거나 사용하지 않도록 설정하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="c96c8-110">Discusses how to enable or disable tracing dynamically using ETW.</span></span>  
  
 [<span data-ttu-id="c96c8-111">메시지 흐름 추적 구성</span><span class="sxs-lookup"><span data-stu-id="c96c8-111">Configuring Message Flow Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/etw/configuring-message-flow-tracing.md)  
 <span data-ttu-id="c96c8-112">메시지 흐름 추적을 구성하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="c96c8-112">Describes how to configure message flow tracing.</span></span>  
  
 [<span data-ttu-id="c96c8-113">분석 추적 이벤트 참조</span><span class="sxs-lookup"><span data-stu-id="c96c8-113">Analytic Trace Event Reference</span></span>](../../../../../docs/framework/wcf/diagnostics/etw/analytic-trace-event-reference.md)  
 <span data-ttu-id="c96c8-114">이벤트 ID와 함께 해당 이벤트 수준, 이벤트 메시지 및 키워드가 포함된 표를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="c96c8-114">Shows a table of event IDs with their event levels, event messages and keywords.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c96c8-115">참고자료</span><span class="sxs-lookup"><span data-stu-id="c96c8-115">See also</span></span>

- [<span data-ttu-id="c96c8-116">WCF 서비스 및 Windows용 이벤트 추적</span><span class="sxs-lookup"><span data-stu-id="c96c8-116">WCF Services and Event Tracing for Windows</span></span>](../../../../../docs/framework/wcf/samples/wcf-services-and-event-tracing-for-windows.md)
- [<span data-ttu-id="c96c8-117">Windows에서 이벤트 추적으로 이벤트 추적</span><span class="sxs-lookup"><span data-stu-id="c96c8-117">Tracking Events into Event Tracing in Windows</span></span>](../../../../../docs/framework/windows-workflow-foundation/samples/tracking-events-into-event-tracing-in-windows.md)
