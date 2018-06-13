---
title: ICLRSyncManager::GetRWLockOwnerNext 메서드
ms.date: 03/30/2017
api_name:
- ICLRSyncManager.GetRWLockOwnerNext
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRSyncManager::GetRWLockOwnerNext
helpviewer_keywords:
- ICLRSyncManager::GetRWLockOwnerNext method [.NET Framework hosting]
- GetRWLockOwnerNext method [.NET Framework hosting]
ms.assetid: 0e025b6a-280e-40a2-a2d0-b15f58777b81
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 4725feff4645ec207be6e6afc7d1e1d38eca36ec
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33435212"
---
# <a name="iclrsyncmanagergetrwlockownernext-method"></a><span data-ttu-id="3da30-102">ICLRSyncManager::GetRWLockOwnerNext 메서드</span><span class="sxs-lookup"><span data-stu-id="3da30-102">ICLRSyncManager::GetRWLockOwnerNext Method</span></span>
<span data-ttu-id="3da30-103">다음 가져옵니다 [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md) 현재 판독기 / 작성기 잠금을 차단 된 인스턴스.</span><span class="sxs-lookup"><span data-stu-id="3da30-103">Gets the next [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md) instance that is blocked on the current reader-writer lock.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3da30-104">구문</span><span class="sxs-lookup"><span data-stu-id="3da30-104">Syntax</span></span>  
  
```  
HRESULT GetRWLockOwnerNext (  
    [in] SIZE_T       Iterator,  
    [out] IHostTask  *ppOwnerHostTask  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="3da30-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="3da30-105">Parameters</span></span>  
 `Iterator`  
 <span data-ttu-id="3da30-106">[in] 반복기에 대 한 호출을 사용 하 여 만든 [CreateRWLockOwnerIterator](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-createrwlockowneriterator-method.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="3da30-106">[in] The iterator that was created by using a call to [CreateRWLockOwnerIterator](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-createrwlockowneriterator-method.md).</span></span>  
  
 `ppOwnerHostTask`  
 <span data-ttu-id="3da30-107">[out] 다음에 대 한 포인터 `IHostTask` 없는 태스크가 대기 하는 경우 잠금 또는 null을 대기 하는 합니다.</span><span class="sxs-lookup"><span data-stu-id="3da30-107">[out] A pointer to the next `IHostTask` that is waiting on the lock, or null if no task is waiting.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="3da30-108">반환 값</span><span class="sxs-lookup"><span data-stu-id="3da30-108">Return Value</span></span>  
  
|<span data-ttu-id="3da30-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="3da30-109">HRESULT</span></span>|<span data-ttu-id="3da30-110">설명</span><span class="sxs-lookup"><span data-stu-id="3da30-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="3da30-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="3da30-111">S_OK</span></span>|<span data-ttu-id="3da30-112">`GetRWLockOwnerNext` 성공적으로 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="3da30-112">`GetRWLockOwnerNext` returned successfully.</span></span>|  
|<span data-ttu-id="3da30-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="3da30-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="3da30-114">공용 언어 런타임 (CLR) 프로세스에 로드 되지 않았습니다 또는 CLR 중인 상태를 관리 코드를 실행 하거나 호출을 처리할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="3da30-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="3da30-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="3da30-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="3da30-116">호출 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="3da30-116">The call timed out.</span></span>|  
|<span data-ttu-id="3da30-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="3da30-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="3da30-118">호출자에 게 잠금을 소유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3da30-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="3da30-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="3da30-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="3da30-120">차단 된 스레드 이벤트 취소 되었습니다 또는 파이버가 기다리던 합니다.</span><span class="sxs-lookup"><span data-stu-id="3da30-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="3da30-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="3da30-121">E_FAIL</span></span>|<span data-ttu-id="3da30-122">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="3da30-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="3da30-123">메서드가 E_FAIL을 반환 하는 경우 CLR을 하는 프로세스 내에서 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="3da30-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="3da30-124">호스팅 방법에 대 한 후속 호출 HOST_E_CLRNOTAVAILABLE를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="3da30-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3da30-125">설명</span><span class="sxs-lookup"><span data-stu-id="3da30-125">Remarks</span></span>  
 <span data-ttu-id="3da30-126">경우 `ppOwnerHostTask` 로 설정 된 호스트를 호출 해야 하 고 null 이면 반복 작업이 종료 된는 [DeleteRWLockOwnerIterator](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-deleterwlockowneriterator-method.md) 메서드.</span><span class="sxs-lookup"><span data-stu-id="3da30-126">If `ppOwnerHostTask` is set to null, the iteration has terminated, and the host should call the [DeleteRWLockOwnerIterator](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-deleterwlockowneriterator-method.md) method.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="3da30-127">CLR에서는 `AddRef` 에 `IHostTask` 를 `ppOwnerHostTask` 포인터를 유지 하는 호스트에서이 작업을 방지 하기 위해 포인트입니다.</span><span class="sxs-lookup"><span data-stu-id="3da30-127">The CLR calls `AddRef` on the `IHostTask` to which `ppOwnerHostTask` points to prevent this task from exiting while the host holds the pointer.</span></span> <span data-ttu-id="3da30-128">호스트에서는 호출 `Release` 완료 되 면 참조 횟수를 감소 시키기 위해 합니다.</span><span class="sxs-lookup"><span data-stu-id="3da30-128">The host must call `Release` to decrement the reference count when it is finished.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3da30-129">요구 사항</span><span class="sxs-lookup"><span data-stu-id="3da30-129">Requirements</span></span>  
 <span data-ttu-id="3da30-130">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="3da30-130">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3da30-131">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="3da30-131">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="3da30-132">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="3da30-132">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="3da30-133">**.NET framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3da30-133">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3da30-134">참고 항목</span><span class="sxs-lookup"><span data-stu-id="3da30-134">See Also</span></span>  
 [<span data-ttu-id="3da30-135">ICLRSyncManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="3da30-135">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)  
 [<span data-ttu-id="3da30-136">IHostSyncManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="3da30-136">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)
