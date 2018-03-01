---
title: "IHostTaskManager::SwitchToTask 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- IHostTaskManager.SwitchToTask
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostTaskManager::SwitchToTask
helpviewer_keywords:
- IHostTaskManager::SwitchToTask method [.NET Framework hosting]
- SwitchToTask method [.NET Framework hosting]
ms.assetid: 35d0c27e-4b14-49ce-810d-7ab2120177e8
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 03578a6a9579a807323d54308347f16f24ae90dd
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="ihosttaskmanagerswitchtotask-method"></a><span data-ttu-id="91a8c-102">IHostTaskManager::SwitchToTask 메서드</span><span class="sxs-lookup"><span data-stu-id="91a8c-102">IHostTaskManager::SwitchToTask Method</span></span>
<span data-ttu-id="91a8c-103">현재 작업에서 전환 해야 함을 호스트에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="91a8c-103">Notifies the host that it should switch out the current task.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="91a8c-104">구문</span><span class="sxs-lookup"><span data-stu-id="91a8c-104">Syntax</span></span>  
  
```  
HRESULT SwitchToTask (  
    [in] DWORD option  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="91a8c-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="91a8c-105">Parameters</span></span>  
 `option`  
 <span data-ttu-id="91a8c-106">[in] 중 하나는 [WAIT_OPTION](../../../../docs/framework/unmanaged-api/hosting/wait-option-enumeration.md) 열거 값을 나타내는 호스트에서 수행할 작업을 하는 경우 요청 된 작업이 차단 합니다.</span><span class="sxs-lookup"><span data-stu-id="91a8c-106">[in] One of the [WAIT_OPTION](../../../../docs/framework/unmanaged-api/hosting/wait-option-enumeration.md) enumeration values, indicating the action the host should take if the requested operation blocks.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="91a8c-107">반환 값</span><span class="sxs-lookup"><span data-stu-id="91a8c-107">Return Value</span></span>  
  
|<span data-ttu-id="91a8c-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="91a8c-108">HRESULT</span></span>|<span data-ttu-id="91a8c-109">설명</span><span class="sxs-lookup"><span data-stu-id="91a8c-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="91a8c-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="91a8c-110">S_OK</span></span>|<span data-ttu-id="91a8c-111">`SwitchToTask`성공적으로 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="91a8c-111">`SwitchToTask` returned successfully.</span></span>|  
|<span data-ttu-id="91a8c-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="91a8c-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="91a8c-113">공용 언어 런타임 (CLR) 프로세스에 로드 되지 않았습니다 또는 CLR 중인 상태를 관리 코드를 실행 하거나 호출을 처리할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="91a8c-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="91a8c-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="91a8c-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="91a8c-115">호출 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="91a8c-115">The call timed out.</span></span>|  
|<span data-ttu-id="91a8c-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="91a8c-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="91a8c-117">호출자에 게 잠금을 소유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="91a8c-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="91a8c-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="91a8c-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="91a8c-119">차단 된 스레드 이벤트 취소 되었습니다 또는 파이버가 기다리던 합니다.</span><span class="sxs-lookup"><span data-stu-id="91a8c-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="91a8c-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="91a8c-120">E_FAIL</span></span>|<span data-ttu-id="91a8c-121">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="91a8c-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="91a8c-122">메서드가 E_FAIL을 반환 하는 경우 CLR을 하는 프로세스 내에서 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="91a8c-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="91a8c-123">호스팅 방법에 대 한 후속 호출 HOST_E_CLRNOTAVAILABLE를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="91a8c-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="91a8c-124">설명</span><span class="sxs-lookup"><span data-stu-id="91a8c-124">Remarks</span></span>  
 <span data-ttu-id="91a8c-125">호스트에서 다른 작업으로 필요한 전환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="91a8c-125">The host can switch in another task as desired or needed.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="91a8c-126">`SwitchToTask`호스트; 하도록 전환 해야 하는 작업을 지정 하지 않습니다. 전환 해야 하는 작업에만 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="91a8c-126">`SwitchToTask` does not specify which task the host should switch to; it specifies only the task that it should switch from.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="91a8c-127">요구 사항</span><span class="sxs-lookup"><span data-stu-id="91a8c-127">Requirements</span></span>  
 <span data-ttu-id="91a8c-128">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="91a8c-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="91a8c-129">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="91a8c-129">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="91a8c-130">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="91a8c-130">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="91a8c-131">**.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="91a8c-131">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="91a8c-132">참고 항목</span><span class="sxs-lookup"><span data-stu-id="91a8c-132">See Also</span></span>  
 [<span data-ttu-id="91a8c-133">ICLRTask 인터페이스</span><span class="sxs-lookup"><span data-stu-id="91a8c-133">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)  
 [<span data-ttu-id="91a8c-134">ICLRTaskManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="91a8c-134">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)  
 [<span data-ttu-id="91a8c-135">IHostTask 인터페이스</span><span class="sxs-lookup"><span data-stu-id="91a8c-135">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)  
 [<span data-ttu-id="91a8c-136">IHostTaskManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="91a8c-136">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
