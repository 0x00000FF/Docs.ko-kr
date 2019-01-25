---
title: ICLRTask::Abort 메서드
ms.date: 03/30/2017
api_name:
- ICLRTask.Abort
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRTask::Abort
helpviewer_keywords:
- ICLRTask::Abort method [.NET Framework hosting]
- Abort method, ICLRTask interface [.NET Framework hosting]
ms.assetid: b3594b5f-2e41-4e36-9096-3586276a138c
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9164e64c56a8a4ae908a3d06f878b399550703f9
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54715402"
---
# <a name="iclrtaskabort-method"></a><span data-ttu-id="3fc6b-102">ICLRTask::Abort 메서드</span><span class="sxs-lookup"><span data-stu-id="3fc6b-102">ICLRTask::Abort Method</span></span>
<span data-ttu-id="3fc6b-103">CLR (공용 언어 런타임) 작업을 중단 하도록 요청 하는 현재 [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) 인스턴스가 나타내는입니다.</span><span class="sxs-lookup"><span data-stu-id="3fc6b-103">Requests that the common language runtime (CLR) abort the task that the current [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) instance represents.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3fc6b-104">구문</span><span class="sxs-lookup"><span data-stu-id="3fc6b-104">Syntax</span></span>  
  
```  
HRESULT Abort ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="3fc6b-105">반환 값</span><span class="sxs-lookup"><span data-stu-id="3fc6b-105">Return Value</span></span>  
  
|<span data-ttu-id="3fc6b-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="3fc6b-106">HRESULT</span></span>|<span data-ttu-id="3fc6b-107">설명</span><span class="sxs-lookup"><span data-stu-id="3fc6b-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="3fc6b-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="3fc6b-108">S_OK</span></span>|<span data-ttu-id="3fc6b-109">`Abort` 성공적으로 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="3fc6b-109">`Abort` returned successfully.</span></span>|  
|<span data-ttu-id="3fc6b-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="3fc6b-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="3fc6b-111">CLR이 로드 된 프로세스에 또는 CLR 상태인는 관리 코드를 실행 하거나 호출을 처리할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="3fc6b-111">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="3fc6b-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="3fc6b-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="3fc6b-113">호출 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="3fc6b-113">The call timed out.</span></span>|  
|<span data-ttu-id="3fc6b-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="3fc6b-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="3fc6b-115">호출자가 잠금을 소유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3fc6b-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="3fc6b-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="3fc6b-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="3fc6b-117">이벤트가 차단 된 스레드가 취소 된 또는 파이버를 대기 하 고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3fc6b-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="3fc6b-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="3fc6b-118">E_FAIL</span></span>|<span data-ttu-id="3fc6b-119">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="3fc6b-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="3fc6b-120">메서드 E_FAIL을 반환 하는 경우 CLR은 프로세스 내에서 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="3fc6b-120">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="3fc6b-121">메서드를 호스트 하는 데 대 한 후속 호출 HOST_E_CLRNOTAVAILABLE를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="3fc6b-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3fc6b-122">설명</span><span class="sxs-lookup"><span data-stu-id="3fc6b-122">Remarks</span></span>  
 <span data-ttu-id="3fc6b-123">CLR에서 발생 한 <xref:System.Threading.ThreadAbortException> 호스트 호출 하는 경우 `Abort`합니다.</span><span class="sxs-lookup"><span data-stu-id="3fc6b-123">The CLR raises a <xref:System.Threading.ThreadAbortException> when the host calls `Abort`.</span></span> <span data-ttu-id="3fc6b-124">예: 종료자 또는 예외 처리 메커니즘을 실행 하려면 사용자 코드를 기다리지 않고 예외 정보를 초기화 한 후에 즉시 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="3fc6b-124">It returns immediately after the exception information is initialized, without waiting for user code, such as finalizers or exception handling mechanisms, to execute.</span></span> <span data-ttu-id="3fc6b-125">에 대 한 호출 `Abort` 신속 하 게 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="3fc6b-125">Calls to `Abort` thus return quickly.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3fc6b-126">요구 사항</span><span class="sxs-lookup"><span data-stu-id="3fc6b-126">Requirements</span></span>  
 <span data-ttu-id="3fc6b-127">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="3fc6b-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3fc6b-128">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="3fc6b-128">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="3fc6b-129">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="3fc6b-129">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="3fc6b-130">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3fc6b-130">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3fc6b-131">참고자료</span><span class="sxs-lookup"><span data-stu-id="3fc6b-131">See also</span></span>
- [<span data-ttu-id="3fc6b-132">ICLRTask 인터페이스</span><span class="sxs-lookup"><span data-stu-id="3fc6b-132">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="3fc6b-133">ICLRTaskManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="3fc6b-133">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="3fc6b-134">IHostTask 인터페이스</span><span class="sxs-lookup"><span data-stu-id="3fc6b-134">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="3fc6b-135">IHostTaskManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="3fc6b-135">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
