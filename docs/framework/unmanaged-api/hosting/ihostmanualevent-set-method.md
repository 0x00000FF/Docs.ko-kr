---
title: IHostManualEvent::Set 메서드
ms.date: 03/30/2017
api_name:
- IHostManualEvent.Set
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostManualEvent::Set
helpviewer_keywords:
- Set method, IHostManualEvent interface [.NET Framework hosting]
- IHostManualEvent::Set method [.NET Framework hosting]
ms.assetid: e930c174-f71d-4faa-bb59-f0fb3df4d77b
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3a10d7d5069b8fe42144517a028ed9258b0633da
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33440605"
---
# <a name="ihostmanualeventset-method"></a><span data-ttu-id="7fc3b-102">IHostManualEvent::Set 메서드</span><span class="sxs-lookup"><span data-stu-id="7fc3b-102">IHostManualEvent::Set Method</span></span>
<span data-ttu-id="7fc3b-103">에서는 현재 [IHostManualEvent](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-interface.md) 인스턴스 신호를 받은 상태로 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7fc3b-103">Sets the current [IHostManualEvent](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-interface.md) instance to a signaled state.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7fc3b-104">구문</span><span class="sxs-lookup"><span data-stu-id="7fc3b-104">Syntax</span></span>  
  
```  
HRESULT Set ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="7fc3b-105">반환 값</span><span class="sxs-lookup"><span data-stu-id="7fc3b-105">Return Value</span></span>  
  
|<span data-ttu-id="7fc3b-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="7fc3b-106">HRESULT</span></span>|<span data-ttu-id="7fc3b-107">설명</span><span class="sxs-lookup"><span data-stu-id="7fc3b-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="7fc3b-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="7fc3b-108">S_OK</span></span>|<span data-ttu-id="7fc3b-109">`Set` 성공적으로 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="7fc3b-109">`Set` returned successfully.</span></span>|  
|<span data-ttu-id="7fc3b-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="7fc3b-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="7fc3b-111">공용 언어 런타임 (CLR) 프로세스에 로드 되지 않았습니다 또는 CLR 중인 상태를 관리 코드를 실행 하거나 호출을 처리할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="7fc3b-111">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="7fc3b-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="7fc3b-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="7fc3b-113">호출 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="7fc3b-113">The call timed out.</span></span>|  
|<span data-ttu-id="7fc3b-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="7fc3b-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="7fc3b-115">호출자에 게 잠금을 소유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7fc3b-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="7fc3b-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="7fc3b-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="7fc3b-117">차단 된 스레드 이벤트 취소 되었습니다 또는 파이버가 기다리던 합니다.</span><span class="sxs-lookup"><span data-stu-id="7fc3b-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="7fc3b-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="7fc3b-118">E_FAIL</span></span>|<span data-ttu-id="7fc3b-119">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="7fc3b-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="7fc3b-120">메서드가 E_FAIL을 반환 하는 경우 CLR을 하는 프로세스 내에서 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="7fc3b-120">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="7fc3b-121">호스팅 방법에 대 한 후속 호출 HOST_E_CLRNOTAVAILABLE를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="7fc3b-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="7fc3b-122">요구 사항</span><span class="sxs-lookup"><span data-stu-id="7fc3b-122">Requirements</span></span>  
 <span data-ttu-id="7fc3b-123">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="7fc3b-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7fc3b-124">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="7fc3b-124">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="7fc3b-125">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="7fc3b-125">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="7fc3b-126">**.NET framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7fc3b-126">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7fc3b-127">참고 항목</span><span class="sxs-lookup"><span data-stu-id="7fc3b-127">See Also</span></span>  
 [<span data-ttu-id="7fc3b-128">ICLRSyncManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="7fc3b-128">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)  
 [<span data-ttu-id="7fc3b-129">IHostAutoEvent 인터페이스</span><span class="sxs-lookup"><span data-stu-id="7fc3b-129">IHostAutoEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostautoevent-interface.md)  
 [<span data-ttu-id="7fc3b-130">IHostManualEvent 인터페이스</span><span class="sxs-lookup"><span data-stu-id="7fc3b-130">IHostManualEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-interface.md)  
 [<span data-ttu-id="7fc3b-131">IHostSemaphore 인터페이스</span><span class="sxs-lookup"><span data-stu-id="7fc3b-131">IHostSemaphore Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsemaphore-interface.md)  
 [<span data-ttu-id="7fc3b-132">IHostSyncManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="7fc3b-132">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)
