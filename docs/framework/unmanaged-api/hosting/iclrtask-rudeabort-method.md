---
title: ICLRTask::RudeAbort 메서드
ms.date: 03/30/2017
api_name:
- ICLRTask.RudeAbort
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRTask::RudeAbort
helpviewer_keywords:
- RudeAbort method, ICLRTask interface [.NET Framework hosting]
- ICLRTask::RudeAbort method [.NET Framework hosting]
ms.assetid: b5785468-fcd7-4cc3-8a5d-8796337b53fc
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3e2145f321d2850468eaa73cc35a9dbd19af0480
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54649480"
---
# <a name="iclrtaskrudeabort-method"></a><span data-ttu-id="543a8-102">ICLRTask::RudeAbort 메서드</span><span class="sxs-lookup"><span data-stu-id="543a8-102">ICLRTask::RudeAbort Method</span></span>
<span data-ttu-id="543a8-103">CLR (공용 언어 런타임)를 나타내는 현재 작업을 중단 하도록 지시 [ICLRTask 인터페이스](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) 즉시 및 무조건 인스턴스.</span><span class="sxs-lookup"><span data-stu-id="543a8-103">Instructs the common language runtime (CLR) to abort the task represented by the current [ICLRTask Interface](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) instance immediately and unconditionally.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="543a8-104">구문</span><span class="sxs-lookup"><span data-stu-id="543a8-104">Syntax</span></span>  
  
```  
HRESULT RudeAbort ();   
```  
  
## <a name="return-value"></a><span data-ttu-id="543a8-105">반환 값</span><span class="sxs-lookup"><span data-stu-id="543a8-105">Return Value</span></span>  
  
|<span data-ttu-id="543a8-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="543a8-106">HRESULT</span></span>|<span data-ttu-id="543a8-107">설명</span><span class="sxs-lookup"><span data-stu-id="543a8-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="543a8-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="543a8-108">S_OK</span></span>|<span data-ttu-id="543a8-109">`RudeAbort` 성공적으로 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="543a8-109">`RudeAbort` returned successfully.</span></span>|  
|<span data-ttu-id="543a8-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="543a8-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="543a8-111">CLR이 로드 된 프로세스에 또는 CLR 상태인는 관리 코드를 실행 하거나 호출을 처리할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="543a8-111">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="543a8-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="543a8-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="543a8-113">호출 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="543a8-113">The call timed out.</span></span>|  
|<span data-ttu-id="543a8-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="543a8-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="543a8-115">호출자가 잠금을 소유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="543a8-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="543a8-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="543a8-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="543a8-117">이벤트가 차단 된 스레드가 취소 된 또는 파이버를 대기 하 고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="543a8-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="543a8-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="543a8-118">E_FAIL</span></span>|<span data-ttu-id="543a8-119">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="543a8-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="543a8-120">메서드 E_FAIL을 반환 하는 경우 CLR은 프로세스 내에서 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="543a8-120">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="543a8-121">메서드를 호스트 하는 데 대 한 후속 호출 HOST_E_CLRNOTAVAILABLE를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="543a8-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="543a8-122">설명</span><span class="sxs-lookup"><span data-stu-id="543a8-122">Remarks</span></span>  
 <span data-ttu-id="543a8-123">호스트 `RudeAbort` 즉시 작업을 중단 합니다.</span><span class="sxs-lookup"><span data-stu-id="543a8-123">A host calls `RudeAbort` to abort a task immediately.</span></span> <span data-ttu-id="543a8-124">종료자 및 예외 처리 루틴 실행을 보장 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="543a8-124">Finalizers and exception handling routines are not guaranteed to be executed.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="543a8-125">요구 사항</span><span class="sxs-lookup"><span data-stu-id="543a8-125">Requirements</span></span>  
 <span data-ttu-id="543a8-126">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="543a8-126">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="543a8-127">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="543a8-127">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="543a8-128">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="543a8-128">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="543a8-129">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="543a8-129">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="543a8-130">참고자료</span><span class="sxs-lookup"><span data-stu-id="543a8-130">See also</span></span>
- [<span data-ttu-id="543a8-131">ICLRTask 인터페이스</span><span class="sxs-lookup"><span data-stu-id="543a8-131">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="543a8-132">ICLRTaskManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="543a8-132">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="543a8-133">IHostTask 인터페이스</span><span class="sxs-lookup"><span data-stu-id="543a8-133">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="543a8-134">IHostTaskManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="543a8-134">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
