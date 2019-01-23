---
title: IHostTaskManager::EndThreadAffinity 메서드
ms.date: 03/30/2017
api_name:
- IHostTaskManager.EndThreadAffinity
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostTaskManager::EndThreadAffinity
helpviewer_keywords:
- EndThreadAffinity method [.NET Framework hosting]
- IHostTaskManager::EndThreadAffinity method [.NET Framework hosting]
ms.assetid: 7738a904-0cd7-4fde-a3eb-2323a5533157
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 8de8816f08fa98055bb397d77d060721a0fb30d0
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54557918"
---
# <a name="ihosttaskmanagerendthreadaffinity-method"></a><span data-ttu-id="87f7c-102">IHostTaskManager::EndThreadAffinity 메서드</span><span class="sxs-lookup"><span data-stu-id="87f7c-102">IHostTaskManager::EndThreadAffinity Method</span></span>
<span data-ttu-id="87f7c-103">관리 코드는 호스트는 기간이 종료 됨는 현재 작업 이동 하지 말아야 다른 운영 체제 스레드에 대 한 이전 호출 다음에 게 알립니다 [ihosttaskmanager:: Beginthreadaffinity](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-beginthreadaffinity-method.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="87f7c-103">Notifies the host that managed code is exiting the period in which the current task must not be moved to another operating system thread, following an earlier call to [IHostTaskManager::BeginThreadAffinity](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-beginthreadaffinity-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="87f7c-104">구문</span><span class="sxs-lookup"><span data-stu-id="87f7c-104">Syntax</span></span>  
  
```  
HRESULT EndThreadAffinity ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="87f7c-105">반환 값</span><span class="sxs-lookup"><span data-stu-id="87f7c-105">Return Value</span></span>  
  
|<span data-ttu-id="87f7c-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="87f7c-106">HRESULT</span></span>|<span data-ttu-id="87f7c-107">설명</span><span class="sxs-lookup"><span data-stu-id="87f7c-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="87f7c-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="87f7c-108">S_OK</span></span>|<span data-ttu-id="87f7c-109">`EndThreadAffinity` 성공적으로 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="87f7c-109">`EndThreadAffinity` returned successfully.</span></span>|  
|<span data-ttu-id="87f7c-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="87f7c-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="87f7c-111">프로세스에는 CLR (공용 언어 런타임)에 로드 되지 또는 CLR 상태인는 관리 코드를 실행 하거나 호출을 처리할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="87f7c-111">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="87f7c-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="87f7c-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="87f7c-113">호출 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="87f7c-113">The call timed out.</span></span>|  
|<span data-ttu-id="87f7c-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="87f7c-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="87f7c-115">호출자가 잠금을 소유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="87f7c-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="87f7c-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="87f7c-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="87f7c-117">이벤트가 차단 된 스레드가 취소 된 또는 파이버를 대기 하 고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="87f7c-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="87f7c-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="87f7c-118">E_FAIL</span></span>|<span data-ttu-id="87f7c-119">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="87f7c-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="87f7c-120">메서드 E_FAIL을 반환 하는 경우 CLR은 프로세스 내에서 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="87f7c-120">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="87f7c-121">메서드를 호스트 하는 데 대 한 후속 호출 HOST_E_CLRNOTAVAILABLE를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="87f7c-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="87f7c-122">E_UNEXPECTED</span><span class="sxs-lookup"><span data-stu-id="87f7c-122">E_UNEXPECTED</span></span>|<span data-ttu-id="87f7c-123">`EndThreadAffinity` 에 대 한 이전 해당 호출 없이 호출한 `BeginThreadAffinity`합니다.</span><span class="sxs-lookup"><span data-stu-id="87f7c-123">`EndThreadAffinity` was called without an earlier corresponding call to `BeginThreadAffinity`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="87f7c-124">설명</span><span class="sxs-lookup"><span data-stu-id="87f7c-124">Remarks</span></span>  
 <span data-ttu-id="87f7c-125">CLR에서는 해당 호출 `BeginThreadAffinity` 호출 하기 전에 현재 작업에서 `EndThreadAffinity`합니다.</span><span class="sxs-lookup"><span data-stu-id="87f7c-125">The CLR makes a corresponding call to `BeginThreadAffinity` on the current task before calling `EndThreadAffinity`.</span></span> <span data-ttu-id="87f7c-126">이러한 해당 호출에 없는 경우 호스트의 구현을 [IHostTaskManager](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md) E_UNEXPECTED를 반환 하 고 아무 작업도 수행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="87f7c-126">In the absence of such a corresponding call, the host's implementation of [IHostTaskManager](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md) should return E_UNEXPECTED, and take no action.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="87f7c-127">요구 사항</span><span class="sxs-lookup"><span data-stu-id="87f7c-127">Requirements</span></span>  
 <span data-ttu-id="87f7c-128">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="87f7c-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="87f7c-129">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="87f7c-129">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="87f7c-130">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="87f7c-130">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="87f7c-131">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="87f7c-131">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="87f7c-132">참고자료</span><span class="sxs-lookup"><span data-stu-id="87f7c-132">See also</span></span>
- <xref:System.Threading>
- [<span data-ttu-id="87f7c-133">ICLRTask 인터페이스</span><span class="sxs-lookup"><span data-stu-id="87f7c-133">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="87f7c-134">ICLRTaskManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="87f7c-134">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="87f7c-135">IHostTask 인터페이스</span><span class="sxs-lookup"><span data-stu-id="87f7c-135">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="87f7c-136">IHostTaskManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="87f7c-136">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
