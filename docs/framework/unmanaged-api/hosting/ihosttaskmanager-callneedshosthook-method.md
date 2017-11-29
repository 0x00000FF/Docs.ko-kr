---
title: "IHostTaskManager::CallNeedsHostHook 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IHostTaskManager.CallNeedsHostHook
api_location: mscoree.dll
api_type: COM
f1_keywords: IHostTaskManager::CallNeedsHostHook
helpviewer_keywords:
- CallNeedsHostHook method [.NET Framework hosting]
- IHostTaskManager::CallNeedsHostHook method [.NET Framework hosting]
ms.assetid: b60f1f59-9825-4b57-961f-d2979518e6a7
topic_type: apiref
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 0daa122b3576c1a6e6e192a4992549e704721bb4
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="ihosttaskmanagercallneedshosthook-method"></a><span data-ttu-id="2cf56-102">IHostTaskManager::CallNeedsHostHook 메서드</span><span class="sxs-lookup"><span data-stu-id="2cf56-102">IHostTaskManager::CallNeedsHostHook Method</span></span>
<span data-ttu-id="2cf56-103">호스트를에서 공용 언어 런타임 (CLR)는 관리 되지 않는 함수에 지정된 된 호출을 인라인 할 수 있는지 여부를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2cf56-103">Enables the host to specify whether the common language runtime (CLR) can inline the specified call to an unmanaged function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2cf56-104">구문</span><span class="sxs-lookup"><span data-stu-id="2cf56-104">Syntax</span></span>  
  
```  
HRESULT CallNeedsHostHook (  
    [in]  SIZE_T target,   
    [out] BOOL   *pbCallNeedsHostHook  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="2cf56-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="2cf56-105">Parameters</span></span>  
 `target`  
 <span data-ttu-id="2cf56-106">[in] 호출 하는 관리 되지 않는 함수의 매핑된 이식 가능한 실행 (PE) 파일 내 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="2cf56-106">[in] The address within the mapped portable executable (PE) file of the unmanaged function that is to be called.</span></span>  
  
 `pbCallNeedsHostHook`  
 <span data-ttu-id="2cf56-107">[out] 호스트 연결에 대 한 호출 하는지 여부를 나타내는 부울 값에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="2cf56-107">[out] A pointer to a Boolean value that indicates whether the host requires the call to be hooked.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="2cf56-108">반환 값</span><span class="sxs-lookup"><span data-stu-id="2cf56-108">Return Value</span></span>  
  
|<span data-ttu-id="2cf56-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="2cf56-109">HRESULT</span></span>|<span data-ttu-id="2cf56-110">설명</span><span class="sxs-lookup"><span data-stu-id="2cf56-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="2cf56-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="2cf56-111">S_OK</span></span>|<span data-ttu-id="2cf56-112">`CallNeedsHostHook`성공적으로 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="2cf56-112">`CallNeedsHostHook` returned successfully.</span></span>|  
|<span data-ttu-id="2cf56-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="2cf56-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="2cf56-114">CLR은 프로세스에 로드 되지 않았습니다 또는 CLR 중인 상태를 관리 코드를 실행 하거나 호출을 처리할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="2cf56-114">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="2cf56-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="2cf56-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="2cf56-116">호출 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="2cf56-116">The call timed out.</span></span>|  
|<span data-ttu-id="2cf56-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="2cf56-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="2cf56-118">호출자에 게 잠금을 소유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2cf56-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="2cf56-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="2cf56-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="2cf56-120">차단 된 스레드 이벤트 취소 되었습니다 또는 파이버가 기다리던 합니다.</span><span class="sxs-lookup"><span data-stu-id="2cf56-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="2cf56-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="2cf56-121">E_FAIL</span></span>|<span data-ttu-id="2cf56-122">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="2cf56-122">An unknown catastrophic failure has occurred.</span></span> <span data-ttu-id="2cf56-123">메서드가 E_FAIL을 반환 하는 경우 CLR을 하는 프로세스 내에서 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="2cf56-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="2cf56-124">호스팅 방법에 대 한 후속 호출 HOST_E_CLRNOTAVAILABLE를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="2cf56-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2cf56-125">설명</span><span class="sxs-lookup"><span data-stu-id="2cf56-125">Remarks</span></span>  
 <span data-ttu-id="2cf56-126">CLR 코드 실행을 최적화 하도록 각 플랫폼의 분석을 수행 호출을 인라인 처리할 수 있는지 여부를 확인 하려면 컴파일하는 동안 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="2cf56-126">To help optimize code execution, the CLR performs an analysis of each platform invoke call during compilation to determine whether the call can be inlined.</span></span> <span data-ttu-id="2cf56-127">`CallNeedsHostHook`호스트를를 관리 되지 않는 함수에 대 한 호출 후크 해야 하도록 요구 하 여 해당 결정을 재정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2cf56-127">`CallNeedsHostHook` enables the host to override that decision by requiring that a call to an unmanaged function be hooked.</span></span> <span data-ttu-id="2cf56-128">호스트는 후크를 필요한 런타임 호출 인라인 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2cf56-128">If the host requires a hook, the runtime does not inline the call.</span></span>  
  
 <span data-ttu-id="2cf56-129">호스트 일반적으로 필요 후크를 부동 소수점 상태를 조정 해야 하는 경우 한 호출의 호스트 메모리 또는 모든 잠금이 발생에 대 한 런타임 요청을 추적할 수 없는 상태로 시작 하는 알림을 수신 합니다.</span><span class="sxs-lookup"><span data-stu-id="2cf56-129">The host typically would require a hook where it must adjust a floating-point state, or upon receiving notification that a call is entering a state where the host cannot track the runtime's requests for memory or any locks taken.</span></span> <span data-ttu-id="2cf56-130">런타임에에 대 한 호출을 사용 하 여 관리 코드에서 전환의 호스트에 알립니다 호스트 호출 후크 해야 필요한 경우 [EnterRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-enterruntime-method.md), [LeaveRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-leaveruntime-method.md), [ ReverseEnterRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-reverseenterruntime-method.md), 및 [ReverseLeaveRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-reverseleaveruntime-method.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="2cf56-130">When the host requires that the call be hooked, the runtime notifies the host of transitions to and from managed code by using calls to [EnterRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-enterruntime-method.md), [LeaveRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-leaveruntime-method.md), [ReverseEnterRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-reverseenterruntime-method.md), and [ReverseLeaveRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-reverseleaveruntime-method.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2cf56-131">요구 사항</span><span class="sxs-lookup"><span data-stu-id="2cf56-131">Requirements</span></span>  
 <span data-ttu-id="2cf56-132">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="2cf56-132">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2cf56-133">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="2cf56-133">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="2cf56-134">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="2cf56-134">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="2cf56-135">**.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2cf56-135">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2cf56-136">참고 항목</span><span class="sxs-lookup"><span data-stu-id="2cf56-136">See Also</span></span>  
 [<span data-ttu-id="2cf56-137">ICLRTask 인터페이스</span><span class="sxs-lookup"><span data-stu-id="2cf56-137">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)  
 [<span data-ttu-id="2cf56-138">ICLRTaskManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="2cf56-138">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)  
 [<span data-ttu-id="2cf56-139">IHostTask 인터페이스</span><span class="sxs-lookup"><span data-stu-id="2cf56-139">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)  
 [<span data-ttu-id="2cf56-140">IHostTaskManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="2cf56-140">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
