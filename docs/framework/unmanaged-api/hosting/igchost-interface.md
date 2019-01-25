---
title: IGCHost 인터페이스
ms.date: 03/30/2017
api_name:
- IGCHost
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IGCHost
helpviewer_keywords:
- IGCHost interface [.NET Framework hosting]
ms.assetid: 9ad70ffd-6963-4ab2-8c84-3d86c3fb8deb
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 123eda65510263951895f9c7ac4c6b1781bbd5f6
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54736690"
---
# <a name="igchost-interface"></a><span data-ttu-id="19c74-102">IGCHost 인터페이스</span><span class="sxs-lookup"><span data-stu-id="19c74-102">IGCHost Interface</span></span>
<span data-ttu-id="19c74-103">가비지 컬렉션 시스템에 대 한 정보를 얻기 위한 고 가비지 컬렉션의 일부 측면을 제어 하기 위한 메서드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="19c74-103">Provides methods for obtaining information about the garbage collection system and for controlling some aspects of garbage collection.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="19c74-104">부터 [!INCLUDE[net_v45](../../../../includes/net-v45-md.md)]를 사용할 수는 [IGCHost2::SetGCStartupLimitsEx](../../../../docs/framework/unmanaged-api/hosting/igchost2-setgcstartuplimitsex-method.md) 가비지 수집 세그먼트의 크기 및 가비지 컬렉션 시스템의 0 세대의 최대 크기 값 보다 큰으로 설정 하는 방법의 `DWORD` 에 의해 적용 되는 제한 된 [SetGCStartupLimits](../../../../docs/framework/unmanaged-api/hosting/igchost-setgcstartuplimits-method.md) 메서드.</span><span class="sxs-lookup"><span data-stu-id="19c74-104">Starting with the [!INCLUDE[net_v45](../../../../includes/net-v45-md.md)], you can use the [IGCHost2::SetGCStartupLimitsEx](../../../../docs/framework/unmanaged-api/hosting/igchost2-setgcstartuplimitsex-method.md) method to set the size of a garbage collection segment and the maximum size of the garbage collection system's generation 0 to values greater than the `DWORD` limit that is imposed by the [SetGCStartupLimits](../../../../docs/framework/unmanaged-api/hosting/igchost-setgcstartuplimits-method.md) method.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="19c74-105">이 인터페이스는 전문가 전용입니다.</span><span class="sxs-lookup"><span data-stu-id="19c74-105">This interface is for expert usage only.</span></span> <span data-ttu-id="19c74-106">부적절 하 게 사용 하는 경우에 응용 프로그램의 성능 영향을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="19c74-106">It can affect the performance of an application if used improperly.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="19c74-107">메서드</span><span class="sxs-lookup"><span data-stu-id="19c74-107">Methods</span></span>  
  
|<span data-ttu-id="19c74-108">메서드</span><span class="sxs-lookup"><span data-stu-id="19c74-108">Method</span></span>|<span data-ttu-id="19c74-109">설명</span><span class="sxs-lookup"><span data-stu-id="19c74-109">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="19c74-110">Collect 메서드</span><span class="sxs-lookup"><span data-stu-id="19c74-110">Collect Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/igchost-collect-method.md)|<span data-ttu-id="19c74-111">현재 가비지 컬렉션의 상태에 관계 없이 지정된 된 세대에 발생 하는 수집을 강제로 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="19c74-111">Forces a collection to occur for the given generation, regardless of the state of the current garbage collection.</span></span>|  
|[<span data-ttu-id="19c74-112">GetStats 메서드</span><span class="sxs-lookup"><span data-stu-id="19c74-112">GetStats Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/igchost-getstats-method.md)|<span data-ttu-id="19c74-113">가비지 컬렉션 시스템의 현재 상태에 대 한 통계를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="19c74-113">Gets the statistics for the current state of the garbage collection system.</span></span>|  
|[<span data-ttu-id="19c74-114">GetThreadStats 메서드</span><span class="sxs-lookup"><span data-stu-id="19c74-114">GetThreadStats Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/igchost-getthreadstats-method.md)|<span data-ttu-id="19c74-115">가비지 컬렉션에 대 한 스레드당 통계를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="19c74-115">Gets the per-thread statistics for garbage collection.</span></span>|  
|[<span data-ttu-id="19c74-116">SetGCStartupLimits 메서드</span><span class="sxs-lookup"><span data-stu-id="19c74-116">SetGCStartupLimits Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/igchost-setgcstartuplimits-method.md)|<span data-ttu-id="19c74-117">0 세대에 대 한 세그먼트 크기 및 최대 크기를 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="19c74-117">Sets the segment size and the maximum size for generation 0.</span></span>|  
|[<span data-ttu-id="19c74-118">SetVirtualMemLimit 메서드</span><span class="sxs-lookup"><span data-stu-id="19c74-118">SetVirtualMemLimit Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/igchost-setvirtualmemlimit-method.md)|<span data-ttu-id="19c74-119">런타임의 가상 메모리의 최대 크기를 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="19c74-119">Sets the maximum size of the runtime's virtual memory.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="19c74-120">요구 사항</span><span class="sxs-lookup"><span data-stu-id="19c74-120">Requirements</span></span>  
 <span data-ttu-id="19c74-121">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="19c74-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="19c74-122">**헤더:** GCHost.idl, GCHost.h</span><span class="sxs-lookup"><span data-stu-id="19c74-122">**Header:** GCHost.idl, GCHost.h</span></span>  
  
 <span data-ttu-id="19c74-123">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="19c74-123">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="19c74-124">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="19c74-124">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="19c74-125">참고자료</span><span class="sxs-lookup"><span data-stu-id="19c74-125">See also</span></span>
- [<span data-ttu-id="19c74-126">호스팅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="19c74-126">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
- [<span data-ttu-id="19c74-127">CorRuntimeHost Coclass</span><span class="sxs-lookup"><span data-stu-id="19c74-127">CorRuntimeHost Coclass</span></span>](../../../../docs/framework/unmanaged-api/hosting/corruntimehost-coclass.md)
