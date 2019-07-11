---
title: IHostTaskManager::GetCurrentTask 메서드
ms.date: 03/30/2017
api_name:
- IHostTaskManager.GetCurrentTask
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostTaskManager::GetCurrentTask
helpviewer_keywords:
- GetCurrentTask method, IHostTaskManager interface [.NET Framework hosting]
- IHostTaskManager::GetCurrentTask method [.NET Framework hosting]
ms.assetid: f17bca49-90bd-4dee-a5e1-b9a57ea46f85
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: cb3044927e0d9975ed9347cd4f4896b3b75d3e29
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/10/2019
ms.locfileid: "67749627"
---
# <a name="ihosttaskmanagergetcurrenttask-method"></a><span data-ttu-id="7d968-102">IHostTaskManager::GetCurrentTask 메서드</span><span class="sxs-lookup"><span data-stu-id="7d968-102">IHostTaskManager::GetCurrentTask Method</span></span>
<span data-ttu-id="7d968-103">이 호출이 수행 된 운영 체제 스레드에서 현재 실행 중인 작업에 대 한 인터페이스 포인터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="7d968-103">Gets an interface pointer to the task that is currently executing on the operating system thread from which this call is made.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7d968-104">구문</span><span class="sxs-lookup"><span data-stu-id="7d968-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCurrentTask (  
    [out] IHostTask **pTask  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7d968-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="7d968-105">Parameters</span></span>  
 `pTask`  
 <span data-ttu-id="7d968-106">[out] 주소에 대 한 포인터를 [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md) 작업이 현재 실행 중인 경우 현재 실행 중인 작업 또는 null을 나타내는 인스턴스.</span><span class="sxs-lookup"><span data-stu-id="7d968-106">[out] A pointer to the address of an [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md) instance that represents the currently executing task, or null, if no task is currently executing.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="7d968-107">반환 값</span><span class="sxs-lookup"><span data-stu-id="7d968-107">Return Value</span></span>  
  
|<span data-ttu-id="7d968-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="7d968-108">HRESULT</span></span>|<span data-ttu-id="7d968-109">설명</span><span class="sxs-lookup"><span data-stu-id="7d968-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="7d968-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="7d968-110">S_OK</span></span>|<span data-ttu-id="7d968-111">`GetCurrentTask` 성공적으로 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="7d968-111">`GetCurrentTask` returned successfully.</span></span>|  
|<span data-ttu-id="7d968-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="7d968-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="7d968-113">프로세스에는 CLR (공용 언어 런타임)에 로드 되지 또는 CLR 상태인는 관리 코드를 실행 하거나 호출을 처리할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="7d968-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="7d968-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="7d968-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="7d968-115">호출 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="7d968-115">The call timed out.</span></span>|  
|<span data-ttu-id="7d968-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="7d968-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="7d968-117">호출자가 잠금을 소유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7d968-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="7d968-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="7d968-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="7d968-119">이벤트가 차단 된 스레드가 취소 된 또는 파이버를 대기 하 고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7d968-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="7d968-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="7d968-120">E_FAIL</span></span>|<span data-ttu-id="7d968-121">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="7d968-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="7d968-122">메서드 E_FAIL을 반환 하는 경우 CLR은 프로세스 내에서 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="7d968-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="7d968-123">메서드를 호스트 하는 데 대 한 후속 호출 HOST_E_CLRNOTAVAILABLE를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="7d968-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="7d968-124">HOST_E_INVALIDOPERATION</span><span class="sxs-lookup"><span data-stu-id="7d968-124">HOST_E_INVALIDOPERATION</span></span>|<span data-ttu-id="7d968-125">`GetCurrentTask` 컨트롤 외부에 호스트의 운영 체제 스레드에서 호출 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="7d968-125">`GetCurrentTask` was called on an operating system thread outside the control of the host.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7d968-126">설명</span><span class="sxs-lookup"><span data-stu-id="7d968-126">Remarks</span></span>  
 <span data-ttu-id="7d968-127">호스트를 설정할 수도 있습니다는 `pTask` 매개 변수를 null 작업을 시작 하지 않은 CLR을 실행 하지 못하도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="7d968-127">The host can also set the `pTask` parameter to null to prevent a task that it did not initiate from entering the CLR.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7d968-128">요구 사항</span><span class="sxs-lookup"><span data-stu-id="7d968-128">Requirements</span></span>  
 <span data-ttu-id="7d968-129">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="7d968-129">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7d968-130">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="7d968-130">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="7d968-131">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="7d968-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="7d968-132">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7d968-132">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7d968-133">참고자료</span><span class="sxs-lookup"><span data-stu-id="7d968-133">See also</span></span>

- [<span data-ttu-id="7d968-134">ICLRTask 인터페이스</span><span class="sxs-lookup"><span data-stu-id="7d968-134">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="7d968-135">ICLRTaskManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="7d968-135">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="7d968-136">IHostTask 인터페이스</span><span class="sxs-lookup"><span data-stu-id="7d968-136">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="7d968-137">IHostTaskManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="7d968-137">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
