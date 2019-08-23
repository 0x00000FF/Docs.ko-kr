---
title: disconnectedContext MDA
ms.date: 03/30/2017
helpviewer_keywords:
- DisconnectedContext MDA
- MDAs (managed debugging assistants), disconnected context
- dead context
- transitioning disconnected apartment or context
- context disconnections
- managed debugging assistants (MDAs), disconnected context
ms.assetid: 1887d31d-7006-4491-93b3-68fd5b05f71d
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 1819fffaf2eccb6a26578eaf993100b8eca7c76e
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2019
ms.locfileid: "69966428"
---
# <a name="disconnectedcontext-mda"></a><span data-ttu-id="419d5-102">disconnectedContext MDA</span><span class="sxs-lookup"><span data-stu-id="419d5-102">disconnectedContext MDA</span></span>
<span data-ttu-id="419d5-103">`disconnectedContext` MDA(관리 디버깅 도우미)는 CLR이 COM 개체 관련 요청을 서비스하는 동안 연결이 끊어진 아파트 또는 컨텍스트로 전환하려고 하면 활성화됩니다.</span><span class="sxs-lookup"><span data-stu-id="419d5-103">The `disconnectedContext` managed debugging assistant (MDA) is activated when the CLR attempts to transition into a disconnected apartment or context while servicing a request concerning a COM object.</span></span>  
  
## <a name="symptoms"></a><span data-ttu-id="419d5-104">증상</span><span class="sxs-lookup"><span data-stu-id="419d5-104">Symptoms</span></span>  
 <span data-ttu-id="419d5-105">RCW([런타임 호출 가능 래퍼](../../standard/native-interop/runtime-callable-wrapper.md))에 대한 호출이 해당 호출이 존재하는 아파트 또는 컨텍스트 대신 현재 아파트 또는 컨텍스트의 기본 COM 구성 요소에 전달됩니다.</span><span class="sxs-lookup"><span data-stu-id="419d5-105">Calls made on a [Runtime Callable Wrapper](../../standard/native-interop/runtime-callable-wrapper.md) (RCW) are delivered to the underlying COM component in the current apartment or context instead of the one in which they exist.</span></span> <span data-ttu-id="419d5-106">따라서 COM 구성 요소가 다중 스레드가 아닌 경우 STA(단일 스레드 아파트) 구성 요소의 경우처럼 손상 및/또는 데이터 손실이 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="419d5-106">This can cause corruption and or data loss if the COM component is not multithreaded, as in the case of single-threaded apartment (STA) components.</span></span> <span data-ttu-id="419d5-107">또는 RCW 자체가 프록시인 경우 호출로 인해 RPC_E_WRONG_THREAD의 HRESULT로 <xref:System.Runtime.InteropServices.COMException>이 throw될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="419d5-107">Alternatively, if the RCW is itself a proxy, the call might result in the throwing of a <xref:System.Runtime.InteropServices.COMException> with an HRESULT of RPC_E_WRONG_THREAD.</span></span>  
  
## <a name="cause"></a><span data-ttu-id="419d5-108">원인</span><span class="sxs-lookup"><span data-stu-id="419d5-108">Cause</span></span>  
 <span data-ttu-id="419d5-109">CLR이 OLE 아파트 또는 컨텍스트로 전환하려고 할 때 이러한 아파트 또는 컨텍스트가 종료되었습니다.</span><span class="sxs-lookup"><span data-stu-id="419d5-109">The OLE apartment or context has been shut down when the CLR attempts to transition into it.</span></span> <span data-ttu-id="419d5-110">이 문제는 대개 아파트가 소유한 모든 COM 구성 요소가 완전히 해제되기 전에 STA 아파트가 종료되기 때문에 발생합니다. 이는 사용자 코드의 RCW에 대한 명시적 호출의 결과로 발생하거나, CLR 자체가 COM 구성 요소를 조작(예: 연결된 RCW가 가비지 수집되었을 때 CLR이 COM 구성 요소를 해제하는 경우)하는 동안 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="419d5-110">This is most commonly caused by STA apartments being shut down before all the COM components owned by the apartment were completely released This can occur as a result of an explicit call from user code on an RCW or while the CLR itself is manipulating the COM component, for example when the CLR is releasing the COM component when the associated RCW has been garbage collected.</span></span>  
  
## <a name="resolution"></a><span data-ttu-id="419d5-111">해결 방법</span><span class="sxs-lookup"><span data-stu-id="419d5-111">Resolution</span></span>  
 <span data-ttu-id="419d5-112">이 문제를 방지하려면 STA를 소유한 스레드가 애플리케이션이 아파트에 존재하는 모든 개체에서 종료되기 전에 종료되지 않도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="419d5-112">To avoid this problem, ensure the thread that owns the STA does not terminate before the application has finished with all the objects that live in the apartment.</span></span> <span data-ttu-id="419d5-113">동일한 내용이 컨텍스트에도 적용됩니다. 컨텍스트가 애플리케이션이 컨텍스트 내에 존재하는 모든 COM 구성 요소에서 완전히 종료되기 전에 종료되지 않도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="419d5-113">The same applies to contexts; ensure contexts are not shut down before the application is completely finished with any COM components that live inside the context.</span></span>  
  
## <a name="effect-on-the-runtime"></a><span data-ttu-id="419d5-114">런타임에 대한 영향</span><span class="sxs-lookup"><span data-stu-id="419d5-114">Effect on the Runtime</span></span>  
 <span data-ttu-id="419d5-115">이 MDA는 CLR에 아무런 영향을 미치지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="419d5-115">This MDA has no effect on the CLR.</span></span> <span data-ttu-id="419d5-116">연결이 끊어진 컨텍스트에 대한 데이터를 보고할 뿐입니다.</span><span class="sxs-lookup"><span data-stu-id="419d5-116">It only reports data about the disconnected context.</span></span>  
  
## <a name="output"></a><span data-ttu-id="419d5-117">출력</span><span class="sxs-lookup"><span data-stu-id="419d5-117">Output</span></span>  
 <span data-ttu-id="419d5-118">연결이 끊어진 아파트 또는 컨텍스트의 컨텍스트 쿠키를 보고합니다.</span><span class="sxs-lookup"><span data-stu-id="419d5-118">Reports the context cookie of the disconnected apartment or context.</span></span>  
  
## <a name="configuration"></a><span data-ttu-id="419d5-119">Configuration</span><span class="sxs-lookup"><span data-stu-id="419d5-119">Configuration</span></span>  
  
```xml  
<mdaConfig>  
  <assistants>  
    <disconnectedContext />  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="see-also"></a><span data-ttu-id="419d5-120">참고자료</span><span class="sxs-lookup"><span data-stu-id="419d5-120">See also</span></span>

- <xref:System.Runtime.InteropServices.MarshalAsAttribute>
- [<span data-ttu-id="419d5-121">관리 디버깅 도우미를 사용하여 오류 진단</span><span class="sxs-lookup"><span data-stu-id="419d5-121">Diagnosing Errors with Managed Debugging Assistants</span></span>](../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)
- [<span data-ttu-id="419d5-122">interop 마샬링</span><span class="sxs-lookup"><span data-stu-id="419d5-122">Interop Marshaling</span></span>](../../../docs/framework/interop/interop-marshaling.md)
