---
title: IHostManualEvent::Wait 메서드
ms.date: 03/30/2017
api_name:
- IHostManualEvent.Wait
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostManualEvent::Wait
helpviewer_keywords:
- IHostManualEvent::Wait method [.NET Framework hosting]
- Wait method, IHostManualEvent interface [.NET Framework hosting]
ms.assetid: 1fbb7d8b-8a23-4c2b-8376-1a70cd2d6030
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2242395a02254268c9492e534309c690a343ffbe
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/10/2019
ms.locfileid: "67767270"
---
# <a name="ihostmanualeventwait-method"></a><span data-ttu-id="388a9-102">IHostManualEvent::Wait 메서드</span><span class="sxs-lookup"><span data-stu-id="388a9-102">IHostManualEvent::Wait Method</span></span>
<span data-ttu-id="388a9-103">현재 [IHostManualEvent](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-interface.md) 을 소유 하는 때까지 대기 하는 인스턴스 또는 지정된 된 시간 간격이 경과 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="388a9-103">Causes the current [IHostManualEvent](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-interface.md) instance to wait until it is owned, or a specified amount of time elapses.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="388a9-104">구문</span><span class="sxs-lookup"><span data-stu-id="388a9-104">Syntax</span></span>  
  
```cpp  
HRESULT Wait (  
    [in] DWORD dwMilliseconds,  
    [in] DWORD option  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="388a9-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="388a9-105">Parameters</span></span>  
 `dwMilliseconds`  
 <span data-ttu-id="388a9-106">[in] 하는 경우 반환 되기 전에 대기할 시간을 밀리초 단위로 현재 `IHostManualEvent` 인스턴스를 소유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="388a9-106">[in] The number of milliseconds to wait before returning, if the current `IHostManualEvent` instance is not owned.</span></span>  
  
 `option`  
 <span data-ttu-id="388a9-107">[in] 중 하나는 [WAIT_OPTION](../../../../docs/framework/unmanaged-api/hosting/wait-option-enumeration.md) 값을 호스트 하는 경우이 수행 해야 하는 작업을 나타내는 작업이 차단 됩니다.</span><span class="sxs-lookup"><span data-stu-id="388a9-107">[in] One of the [WAIT_OPTION](../../../../docs/framework/unmanaged-api/hosting/wait-option-enumeration.md) values, indicating the action the host should take if this operation blocks.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="388a9-108">반환 값</span><span class="sxs-lookup"><span data-stu-id="388a9-108">Return Value</span></span>  
  
|<span data-ttu-id="388a9-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="388a9-109">HRESULT</span></span>|<span data-ttu-id="388a9-110">Description</span><span class="sxs-lookup"><span data-stu-id="388a9-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="388a9-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="388a9-111">S_OK</span></span>|<span data-ttu-id="388a9-112">`Wait` 성공적으로 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="388a9-112">`Wait` returned successfully.</span></span>|  
|<span data-ttu-id="388a9-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="388a9-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="388a9-114">프로세스에는 CLR (공용 언어 런타임)에 로드 되지 또는 CLR 상태인는 관리 코드를 실행 하거나 호출을 처리할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="388a9-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="388a9-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="388a9-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="388a9-116">호출 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="388a9-116">The call timed out.</span></span>|  
|<span data-ttu-id="388a9-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="388a9-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="388a9-118">호출자가 잠금을 소유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="388a9-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="388a9-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="388a9-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="388a9-120">이벤트가 차단 된 스레드가 취소 된 또는 파이버를 대기 하 고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="388a9-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="388a9-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="388a9-121">E_FAIL</span></span>|<span data-ttu-id="388a9-122">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="388a9-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="388a9-123">메서드 E_FAIL을 반환 하는 경우 CLR은 프로세스 내에서 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="388a9-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="388a9-124">메서드를 호스트 하는 데 대 한 후속 호출 HOST_E_CLRNOTAVAILABLE를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="388a9-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="388a9-125">HOST_E_DEADLOCK</span><span class="sxs-lookup"><span data-stu-id="388a9-125">HOST_E_DEADLOCK</span></span>|<span data-ttu-id="388a9-126">호스트 대기 간격 동안 교착 상태를 감지 하 여 현재 `IHostManualEvent` 인스턴스 교착 상태가 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="388a9-126">The host detected a deadlock during the wait interval, and chose the current `IHostManualEvent` instance as the deadlock victim.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="388a9-127">요구 사항</span><span class="sxs-lookup"><span data-stu-id="388a9-127">Requirements</span></span>  
 <span data-ttu-id="388a9-128">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="388a9-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="388a9-129">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="388a9-129">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="388a9-130">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="388a9-130">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="388a9-131">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="388a9-131">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="388a9-132">참고자료</span><span class="sxs-lookup"><span data-stu-id="388a9-132">See also</span></span>

- [<span data-ttu-id="388a9-133">ICLRSyncManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="388a9-133">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)
- [<span data-ttu-id="388a9-134">IHostAutoEvent 인터페이스</span><span class="sxs-lookup"><span data-stu-id="388a9-134">IHostAutoEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostautoevent-interface.md)
- [<span data-ttu-id="388a9-135">IHostManualEvent 인터페이스</span><span class="sxs-lookup"><span data-stu-id="388a9-135">IHostManualEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-interface.md)
- [<span data-ttu-id="388a9-136">IHostSemaphore 인터페이스</span><span class="sxs-lookup"><span data-stu-id="388a9-136">IHostSemaphore Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsemaphore-interface.md)
- [<span data-ttu-id="388a9-137">IHostSyncManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="388a9-137">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)
