---
title: System.ServiceModel.ManualFlowThrottleLimitReached
ms.date: 03/30/2017
ms.assetid: 9aba851f-1830-493b-8e3e-60f454eb923e
ms.openlocfilehash: a6b4e369d2d22d2441b3896321b7c152e21d967b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33483333"
---
# <a name="systemservicemodelmanualflowthrottlelimitreached"></a><span data-ttu-id="c6fbc-102">System.ServiceModel.ManualFlowThrottleLimitReached</span><span class="sxs-lookup"><span data-stu-id="c6fbc-102">System.ServiceModel.ManualFlowThrottleLimitReached</span></span>
<span data-ttu-id="c6fbc-103">System.ServiceModel.ManualFlowThrottleLimitReached</span><span class="sxs-lookup"><span data-stu-id="c6fbc-103">System.ServiceModel.ManualFlowThrottleLimitReached</span></span>  
  
## <a name="description"></a><span data-ttu-id="c6fbc-104">설명</span><span class="sxs-lookup"><span data-stu-id="c6fbc-104">Description</span></span>  
 <span data-ttu-id="c6fbc-105">시스템이 ManualFlowControlLimit 스로틀에 대해 설정된 제한에 도달했습니다.</span><span class="sxs-lookup"><span data-stu-id="c6fbc-105">The system reached the limit set for the ManualFlowControlLimit throttle.</span></span> <span data-ttu-id="c6fbc-106">스로틀 값은 ServiceHost 또는 InstanceContext에서 ManualFlowControlLimit 속성을 수정하여 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c6fbc-106">The throttle value can be changed by modifying the ManualFlowControlLimit property on either the ServiceHost or InstanceContext, as applicable.</span></span>  
  
 <span data-ttu-id="c6fbc-107">수동 흐름 제어 제한을 처음에 0으로 줄인 경우 이 추적을 내보냅니다.</span><span class="sxs-lookup"><span data-stu-id="c6fbc-107">This trace is emitted when the manual flow control limit is initially reduced to 0.</span></span> <span data-ttu-id="c6fbc-108">다음에 0으로 변경하면 추적되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c6fbc-108">Subsequent changes to 0 are not traced.</span></span> <span data-ttu-id="c6fbc-109">인스턴스 컨텍스트에 대한 흐름 제어 제한은 각 컨텍스트에 대해 한 번 추적됩니다.</span><span class="sxs-lookup"><span data-stu-id="c6fbc-109">Flow control limit on the instance context is traced once for each context.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c6fbc-110">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c6fbc-110">See Also</span></span>  
 [<span data-ttu-id="c6fbc-111">추적</span><span class="sxs-lookup"><span data-stu-id="c6fbc-111">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)  
 [<span data-ttu-id="c6fbc-112">추적을 사용하여 응용 프로그램 문제 해결</span><span class="sxs-lookup"><span data-stu-id="c6fbc-112">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)  
 [<span data-ttu-id="c6fbc-113">관리 및 진단</span><span class="sxs-lookup"><span data-stu-id="c6fbc-113">Administration and Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/index.md)
