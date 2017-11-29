---
title: "IHostCrst::Leave 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IHostCrst.Leave
api_location: mscoree.dll
api_type: COM
f1_keywords: IHostCrst::Leave
helpviewer_keywords:
- IHostCrst::Leave method [.NET Framework hosting]
- Leave method [.NET Framework hosting]
ms.assetid: dfc51d9e-b36d-4dba-9ea1-4f63fa0601ae
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 21e9a99e4fd22b2cc7d954d0f7316c45ffd7074c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="ihostcrstleave-method"></a><span data-ttu-id="198e2-102">IHostCrst::Leave 메서드</span><span class="sxs-lookup"><span data-stu-id="198e2-102">IHostCrst::Leave Method</span></span>
<span data-ttu-id="198e2-103">현재 인스턴스에서 나타내는 임계 영역을 벗어날 [IHostCrst](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-interface.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="198e2-103">Leaves the critical section that is represented by the current instance of [IHostCrst](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-interface.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="198e2-104">구문</span><span class="sxs-lookup"><span data-stu-id="198e2-104">Syntax</span></span>  
  
```  
HRESULT Leave ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="198e2-105">반환 값</span><span class="sxs-lookup"><span data-stu-id="198e2-105">Return Value</span></span>  
  
|<span data-ttu-id="198e2-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="198e2-106">HRESULT</span></span>|<span data-ttu-id="198e2-107">설명</span><span class="sxs-lookup"><span data-stu-id="198e2-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="198e2-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="198e2-108">S_OK</span></span>|<span data-ttu-id="198e2-109">`Leave`성공적으로 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="198e2-109">`Leave` returned successfully.</span></span>|  
|<span data-ttu-id="198e2-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="198e2-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="198e2-111">공용 언어 런타임 (CLR) 프로세스에 로드 되지 않았습니다 또는 CLR 중인 상태를 관리 코드를 실행 하거나 호출을 처리할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="198e2-111">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="198e2-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="198e2-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="198e2-113">호출 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="198e2-113">The call timed out.</span></span>|  
|<span data-ttu-id="198e2-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="198e2-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="198e2-115">호출자에 게 잠금을 소유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="198e2-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="198e2-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="198e2-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="198e2-117">차단 된 스레드 이벤트 취소 되었습니다 또는 파이버가 기다리던 합니다.</span><span class="sxs-lookup"><span data-stu-id="198e2-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="198e2-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="198e2-118">E_FAIL</span></span>|<span data-ttu-id="198e2-119">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="198e2-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="198e2-120">메서드가 E_FAIL을 반환 하는 경우 CLR을 하는 프로세스 내에서 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="198e2-120">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="198e2-121">호스팅 방법에 대 한 후속 호출 HOST_E_CLRNOTAVAILABLE를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="198e2-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="198e2-122">설명</span><span class="sxs-lookup"><span data-stu-id="198e2-122">Remarks</span></span>  
 <span data-ttu-id="198e2-123">`Leave`CLR 호스트의 스레딩 구현에서 사용 하는 대신 해당 Win32와 직접 통신을 허용 `LeaveCriticalSection` 함수입니다.</span><span class="sxs-lookup"><span data-stu-id="198e2-123">`Leave` allows the CLR to communicate directly with the host's threading implementation, rather than using the corresponding Win32 `LeaveCriticalSection` function.</span></span> <span data-ttu-id="198e2-124">현재 임계 영역에 대 한 소유권 하는 스레드는 `IHostCrst` 인스턴스를 호출 해야 `Leave` 면 각 시간에 대 한 임계 영역에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="198e2-124">A thread that takes ownership of the critical section represented by the current `IHostCrst` instance must call `Leave` once for each time it enters that critical section.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="198e2-125">요구 사항</span><span class="sxs-lookup"><span data-stu-id="198e2-125">Requirements</span></span>  
 <span data-ttu-id="198e2-126">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="198e2-126">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="198e2-127">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="198e2-127">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="198e2-128">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="198e2-128">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="198e2-129">**.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="198e2-129">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="198e2-130">참고 항목</span><span class="sxs-lookup"><span data-stu-id="198e2-130">See Also</span></span>  
 [<span data-ttu-id="198e2-131">ICLRSyncManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="198e2-131">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)  
 [<span data-ttu-id="198e2-132">IHostCrst 인터페이스</span><span class="sxs-lookup"><span data-stu-id="198e2-132">IHostCrst Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-interface.md)  
 [<span data-ttu-id="198e2-133">IHostSyncManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="198e2-133">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)
