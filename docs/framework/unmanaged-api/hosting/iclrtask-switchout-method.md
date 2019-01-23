---
title: ICLRTask::SwitchOut 메서드
ms.date: 03/30/2017
api_name:
- ICLRTask.SwitchOut
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRTask::SwitchOut
helpviewer_keywords:
- ICLRTask::SwitchOut method [.NET Framework hosting]
- SwitchOut method [.NET Framework hosting]
ms.assetid: b6fb168c-b24b-4ecf-a390-2b5ba3317ae6
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 5b0a4450b6cfa98d0c939c148229d48d0b1d4c7c
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54556576"
---
# <a name="iclrtaskswitchout-method"></a><span data-ttu-id="8af4b-102">ICLRTask::SwitchOut 메서드</span><span class="sxs-lookup"><span data-stu-id="8af4b-102">ICLRTask::SwitchOut Method</span></span>
<span data-ttu-id="8af4b-103">CLR (공용 언어 런타임) 태스크를 나타내는 현재 알립니다 [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) 인스턴스가 더 이상 작동 가능한 상태가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8af4b-103">Notifies the common language runtime (CLR) that the task represented by the current [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) instance is no longer in an operable state.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8af4b-104">구문</span><span class="sxs-lookup"><span data-stu-id="8af4b-104">Syntax</span></span>  
  
```  
HRESULT SwitchOut ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="8af4b-105">반환 값</span><span class="sxs-lookup"><span data-stu-id="8af4b-105">Return Value</span></span>  
  
|<span data-ttu-id="8af4b-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="8af4b-106">HRESULT</span></span>|<span data-ttu-id="8af4b-107">설명</span><span class="sxs-lookup"><span data-stu-id="8af4b-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="8af4b-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="8af4b-108">S_OK</span></span>|<span data-ttu-id="8af4b-109">`SwitchOut` 성공적으로 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="8af4b-109">`SwitchOut` returned successfully.</span></span>|  
|<span data-ttu-id="8af4b-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="8af4b-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="8af4b-111">CLR이 로드 된 프로세스에 또는 CLR 상태인는 관리 코드를 실행 하거나 호출을 처리할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="8af4b-111">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="8af4b-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="8af4b-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="8af4b-113">호출 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="8af4b-113">The call timed out.</span></span>|  
|<span data-ttu-id="8af4b-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="8af4b-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="8af4b-115">호출자가 잠금을 소유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8af4b-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="8af4b-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="8af4b-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="8af4b-117">이벤트가 차단 된 스레드가 취소 된 또는 파이버를 대기 하 고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8af4b-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="8af4b-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="8af4b-118">E_FAIL</span></span>|<span data-ttu-id="8af4b-119">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="8af4b-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="8af4b-120">메서드 E_FAIL을 반환 하는 경우 CLR은 프로세스 내에서 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="8af4b-120">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="8af4b-121">메서드를 호스트 하는 데 대 한 후속 호출 HOST_E_CLRNOTAVAILABLE를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="8af4b-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8af4b-122">설명</span><span class="sxs-lookup"><span data-stu-id="8af4b-122">Remarks</span></span>  
 <span data-ttu-id="8af4b-123">호스트 `SwitchOut` 는 일시적으로 중지 된 태스크 실행을 CLR에 알릴 수 있는 현재 `ICLRTask` 나타내는 인스턴스 및 작업을 다시 예약 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8af4b-123">A host calls `SwitchOut` to inform the CLR that it has temporarily stopped executing the task that the current `ICLRTask` instance represents, and will reschedule the task.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8af4b-124">요구 사항</span><span class="sxs-lookup"><span data-stu-id="8af4b-124">Requirements</span></span>  
 <span data-ttu-id="8af4b-125">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="8af4b-125">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8af4b-126">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="8af4b-126">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="8af4b-127">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="8af4b-127">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="8af4b-128">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8af4b-128">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8af4b-129">참고자료</span><span class="sxs-lookup"><span data-stu-id="8af4b-129">See also</span></span>
- [<span data-ttu-id="8af4b-130">ICLRTask 인터페이스</span><span class="sxs-lookup"><span data-stu-id="8af4b-130">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="8af4b-131">ICLRTaskManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="8af4b-131">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="8af4b-132">IHostTask 인터페이스</span><span class="sxs-lookup"><span data-stu-id="8af4b-132">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="8af4b-133">IHostTaskManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="8af4b-133">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
