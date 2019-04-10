---
title: ICLRAppDomainResourceMonitor 인터페이스
ms.date: 03/30/2017
api_name:
- ICLRAppDomainResourceMonitor
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRAppDomainResourceMonitor
helpviewer_keywords:
- ICLRAppDomainResourceMonitor interface [.NET Framework hosting]
ms.assetid: 72fa83a1-8997-41d7-b355-ab177a24a303
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 15bdbc001838e3d13a9789c8f54daa80f3b6ef9a
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59219826"
---
# <a name="iclrappdomainresourcemonitor-interface"></a><span data-ttu-id="2edfa-102">ICLRAppDomainResourceMonitor 인터페이스</span><span class="sxs-lookup"><span data-stu-id="2edfa-102">ICLRAppDomainResourceMonitor Interface</span></span>
<span data-ttu-id="2edfa-103">응용 프로그램 도메인의 메모리 및 CPU 사용량을 검사 하는 방법을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="2edfa-103">Provides methods that inspect an application domain's memory and CPU usage.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="2edfa-104">메서드</span><span class="sxs-lookup"><span data-stu-id="2edfa-104">Methods</span></span>  
  
|<span data-ttu-id="2edfa-105">메서드</span><span class="sxs-lookup"><span data-stu-id="2edfa-105">Method</span></span>|<span data-ttu-id="2edfa-106">설명</span><span class="sxs-lookup"><span data-stu-id="2edfa-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="2edfa-107">GetCurrentAllocated 메서드</span><span class="sxs-lookup"><span data-stu-id="2edfa-107">GetCurrentAllocated Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrappdomainresourcemonitor-getcurrentallocated-method.md)|<span data-ttu-id="2edfa-108">응용 프로그램 도메인이 만들어진 후에 가비지 수집 된 메모리 없이 적용 된 모든 메모리 할당의 바이트의 총 크기를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="2edfa-108">Gets the total size, in bytes, of all memory allocations that have been made by the application domain since it was created, without subtracting memory that has been garbage-collected.</span></span>|  
|[<span data-ttu-id="2edfa-109">GetCurrentSurvived 메서드</span><span class="sxs-lookup"><span data-stu-id="2edfa-109">GetCurrentSurvived Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrappdomainresourcemonitor-getcurrentsurvived-method.md)|<span data-ttu-id="2edfa-110">마지막 전체 차단 가비지 수집에도 유지 되 고 현재 응용 프로그램 도메인에서 참조 되는 바이트 수를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="2edfa-110">Gets the number of bytes that survived the last full, blocking garbage collection and that are referenced by the current application domain.</span></span>|  
|[<span data-ttu-id="2edfa-111">GetCurrentCpuTime 메서드</span><span class="sxs-lookup"><span data-stu-id="2edfa-111">GetCurrentCpuTime Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrappdomainresourcemonitor-getcurrentcputime-method.md)|<span data-ttu-id="2edfa-112">응용 프로그램 도메인이 만들어진 후 현재 응용 프로그램 도메인에서 실행 하는 동안 모든 스레드에서 사용 된 총 프로세서 시간을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="2edfa-112">Gets the total processor time that has been used by all threads while executing in the current application domain, since the application domain was created.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2edfa-113">설명</span><span class="sxs-lookup"><span data-stu-id="2edfa-113">Remarks</span></span>  
 <span data-ttu-id="2edfa-114">`ICLRAppDomainResourceMonitor` 인터페이스는 다음 관리 되는 속성에 유사한 기능을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="2edfa-114">The `ICLRAppDomainResourceMonitor` interface provides functionality that is similar to the following managed properties:</span></span>  
  
-   <xref:System.AppDomain.MonitoringIsEnabled%2A?displayProperty=nameWithType>  
  
-   <xref:System.AppDomain.MonitoringTotalProcessorTime%2A?displayProperty=nameWithType>  
  
-   <xref:System.AppDomain.MonitoringTotalAllocatedMemorySize%2A?displayProperty=nameWithType>  
  
-   <xref:System.AppDomain.MonitoringSurvivedProcessMemorySize%2A?displayProperty=nameWithType>  
  
-   <xref:System.AppDomain.MonitoringSurvivedMemorySize%2A?displayProperty=nameWithType>  
  
## <a name="requirements"></a><span data-ttu-id="2edfa-115">요구 사항</span><span class="sxs-lookup"><span data-stu-id="2edfa-115">Requirements</span></span>  
 <span data-ttu-id="2edfa-116">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="2edfa-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2edfa-117">**헤더:** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="2edfa-117">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="2edfa-118">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="2edfa-118">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="2edfa-119">.NET Framework 버전:</span><span class="sxs-lookup"><span data-stu-id="2edfa-119">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="2edfa-120">참고자료</span><span class="sxs-lookup"><span data-stu-id="2edfa-120">See also</span></span>

- [<span data-ttu-id="2edfa-121">\<appDomainResourceMonitoring > 요소</span><span class="sxs-lookup"><span data-stu-id="2edfa-121">\<appDomainResourceMonitoring> Element</span></span>](../../../../docs/framework/configure-apps/file-schema/runtime/appdomainresourcemonitoring-element.md)
- [<span data-ttu-id="2edfa-122">응용 프로그램 도메인 리소스 모니터링</span><span class="sxs-lookup"><span data-stu-id="2edfa-122">Application Domain Resource Monitoring</span></span>](../../../../docs/standard/garbage-collection/app-domain-resource-monitoring.md)
- [<span data-ttu-id="2edfa-123">호스팅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="2edfa-123">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
- [<span data-ttu-id="2edfa-124">호스팅</span><span class="sxs-lookup"><span data-stu-id="2edfa-124">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
