---
title: "ICLRGCManager::Collect 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRGCManager.Collect
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRGCManager::Collect
helpviewer_keywords:
- ICLRGCManager::Collect method [.NET Framework hosting]
- Collect method, ICLRGCManager interface [.NET Framework hosting]
ms.assetid: 0c6cbbea-c27c-4695-bda3-17c1910d8ddb
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: e2fdb66008a6bbe315f39a0d3fae293219d6b6c2
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="iclrgcmanagercollect-method"></a><span data-ttu-id="c5f56-102">ICLRGCManager::Collect 메서드</span><span class="sxs-lookup"><span data-stu-id="c5f56-102">ICLRGCManager::Collect Method</span></span>
<span data-ttu-id="c5f56-103">지정된 된 세대에 대 한 가비지 수집을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="c5f56-103">Forces a garbage collection for the specified generation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c5f56-104">구문</span><span class="sxs-lookup"><span data-stu-id="c5f56-104">Syntax</span></span>  
  
```  
HRESULT Collect (  
    [in] LONG Generation  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="c5f56-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="c5f56-105">Parameters</span></span>  
 `Generation`  
 <span data-ttu-id="c5f56-106">[in] 수집을 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="c5f56-106">[in] The generation to collect.</span></span> <span data-ttu-id="c5f56-107">모든 세대의 컬렉션을 수행 하는 값이-1입니다.</span><span class="sxs-lookup"><span data-stu-id="c5f56-107">A value of -1 forces a collection of all generations.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c5f56-108">반환 값</span><span class="sxs-lookup"><span data-stu-id="c5f56-108">Return Value</span></span>  
  
|<span data-ttu-id="c5f56-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="c5f56-109">HRESULT</span></span>|<span data-ttu-id="c5f56-110">설명</span><span class="sxs-lookup"><span data-stu-id="c5f56-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="c5f56-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="c5f56-111">S_OK</span></span>|<span data-ttu-id="c5f56-112">`Collect`성공적으로 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="c5f56-112">`Collect` returned successfully.</span></span>|  
|<span data-ttu-id="c5f56-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="c5f56-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="c5f56-114">공용 언어 런타임 (CLR) 프로세스에 로드 되지 않았습니다 또는 CLR 중인 상태를 관리 코드를 실행 하거나 호출을 처리할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c5f56-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="c5f56-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="c5f56-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="c5f56-116">호출 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="c5f56-116">The call timed out.</span></span>|  
|<span data-ttu-id="c5f56-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="c5f56-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="c5f56-118">호출자에 게 잠금을 소유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c5f56-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="c5f56-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="c5f56-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="c5f56-120">차단 된 스레드 이벤트 취소 되었습니다 또는 파이버가 기다리던 합니다.</span><span class="sxs-lookup"><span data-stu-id="c5f56-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="c5f56-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="c5f56-121">E_FAIL</span></span>|<span data-ttu-id="c5f56-122">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="c5f56-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="c5f56-123">E_FAIL을 반환 하는 메서드 후 CLR을 프로세스 내에서 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c5f56-123">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="c5f56-124">호스팅 방법에 대 한 후속 호출 HOST_E_CLRNOTAVAILABLE를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="c5f56-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c5f56-125">설명</span><span class="sxs-lookup"><span data-stu-id="c5f56-125">Remarks</span></span>  
 <span data-ttu-id="c5f56-126">`Collect` 메서드를 사용 하면 CLR의 가비지 수집기의 현재 상태에 관계 없이 수집을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="c5f56-126">The `Collect` method forces the CLR's garbage collector to perform a collection regardless of its current state.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c5f56-127">요구 사항</span><span class="sxs-lookup"><span data-stu-id="c5f56-127">Requirements</span></span>  
 <span data-ttu-id="c5f56-128">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="c5f56-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c5f56-129">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="c5f56-129">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="c5f56-130">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="c5f56-130">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="c5f56-131">**.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c5f56-131">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c5f56-132">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c5f56-132">See Also</span></span>  
 [<span data-ttu-id="c5f56-133">자동 메모리 관리</span><span class="sxs-lookup"><span data-stu-id="c5f56-133">Automatic Memory Management</span></span>](../../../../docs/standard/automatic-memory-management.md)  
 [<span data-ttu-id="c5f56-134">가비지 수집</span><span class="sxs-lookup"><span data-stu-id="c5f56-134">Garbage Collection</span></span>](../../../../docs/standard/garbage-collection/index.md)  
 [<span data-ttu-id="c5f56-135">ICLRControl 인터페이스</span><span class="sxs-lookup"><span data-stu-id="c5f56-135">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)  
 [<span data-ttu-id="c5f56-136">ICLRGCManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="c5f56-136">ICLRGCManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager-interface.md)  
 [<span data-ttu-id="c5f56-137">CLR 호스팅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="c5f56-137">CLR Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/clr-hosting-interfaces.md)  
 [<span data-ttu-id="c5f56-138">호스팅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="c5f56-138">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)  
 [<span data-ttu-id="c5f56-139">호스팅</span><span class="sxs-lookup"><span data-stu-id="c5f56-139">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
