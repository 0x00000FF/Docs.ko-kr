---
title: "IHostThreadPoolManager::GetMaxThreads 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IHostThreadPoolManager.GetMaxThreads
api_location: mscoree.dll
api_type: COM
f1_keywords: IHostThreadPoolManager::GetMaxThreads
helpviewer_keywords:
- IHostThreadPoolManager::GetMaxThreads method [.NET Framework hosting]
- GetMaxThreads method, IHostThreadPoolManager interface [.NET Framework hosting]
ms.assetid: db268876-6178-4a81-aca3-318ee7f96001
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 84867f1b5dfdcfd7a50d01c9e51cb0c42da62f0e
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="ihostthreadpoolmanagergetmaxthreads-method"></a><span data-ttu-id="6e75a-102">IHostThreadPoolManager::GetMaxThreads 메서드</span><span class="sxs-lookup"><span data-stu-id="6e75a-102">IHostThreadPoolManager::GetMaxThreads Method</span></span>
<span data-ttu-id="6e75a-103">스레드 풀에 동시에 호스트를 유지 하는 스레드의 최대 수를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="6e75a-103">Gets the maximum number of threads that the host maintains concurrently in the thread pool.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6e75a-104">구문</span><span class="sxs-lookup"><span data-stu-id="6e75a-104">Syntax</span></span>  
  
```  
HRESULT GetMaxThreads (  
    [out] DWORD *pdwMaxWorkerThreads  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="6e75a-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="6e75a-105">Parameters</span></span>  
 `pdwMaxWorkerThreads`  
 <span data-ttu-id="6e75a-106">[out] 스레드 풀에서 호스트를 유지 하는 스레드의 최대 수에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="6e75a-106">[out] A pointer to the maximum number of threads that the host maintains in the thread pool.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="6e75a-107">반환 값</span><span class="sxs-lookup"><span data-stu-id="6e75a-107">Return Value</span></span>  
  
|<span data-ttu-id="6e75a-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="6e75a-108">HRESULT</span></span>|<span data-ttu-id="6e75a-109">설명</span><span class="sxs-lookup"><span data-stu-id="6e75a-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="6e75a-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="6e75a-110">S_OK</span></span>|<span data-ttu-id="6e75a-111">`GetMaxThreads`성공적으로 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="6e75a-111">`GetMaxThreads` returned successfully.</span></span>|  
|<span data-ttu-id="6e75a-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="6e75a-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="6e75a-113">공용 언어 런타임 (CLR (프로세스에 로드 되지 않은 않았거나 상태에는 자신이 없습니다 관리 되는 코드 또는 호출 프로세스가 성공적으로 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="6e75a-113">The common language runtime (CLR( has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="6e75a-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="6e75a-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="6e75a-115">호출 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="6e75a-115">The call timed out.</span></span>|  
|<span data-ttu-id="6e75a-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="6e75a-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="6e75a-117">호출자에 게 잠금을 소유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6e75a-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="6e75a-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="6e75a-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="6e75a-119">차단 된 스레드 이벤트 취소 되었습니다 또는 파이버가 기다리던 합니다.</span><span class="sxs-lookup"><span data-stu-id="6e75a-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="6e75a-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="6e75a-120">E_FAIL</span></span>|<span data-ttu-id="6e75a-121">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="6e75a-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="6e75a-122">메서드가 E_FAIL을 반환 하는 경우 CLR을 하는 프로세스 내에서 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="6e75a-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="6e75a-123">호스팅 방법에 대 한 후속 호출 HOST_E_CLRNOTAVAILABLE를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="6e75a-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="6e75a-124">E_NOTIMPL</span><span class="sxs-lookup"><span data-stu-id="6e75a-124">E_NOTIMPL</span></span>|<span data-ttu-id="6e75a-125">호스트의 구현을 제공 하지 않는 `GetMaxThreads`합니다.</span><span class="sxs-lookup"><span data-stu-id="6e75a-125">The host does not provide an implementation of `GetMaxThreads`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6e75a-126">설명</span><span class="sxs-lookup"><span data-stu-id="6e75a-126">Remarks</span></span>  
 <span data-ttu-id="6e75a-127">CLR에서는 `GetMaxThreads` 스레드 풀에 있는 스레드의 총 수를 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="6e75a-127">The CLR calls `GetMaxThreads` to determine the total number of threads in the thread pool.</span></span> <span data-ttu-id="6e75a-128">[GetAvailableThreads](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-getavailablethreads-method.md) 메서드는 작업 항목을 현재 처리 되지 않습니다. 스레드 수를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="6e75a-128">The [GetAvailableThreads](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-getavailablethreads-method.md) method gets the number of threads that are not currently processing work items.</span></span> <span data-ttu-id="6e75a-129">반환된 된 값의 모든 요청은 `pdwMaxWorkerThreads` 매개 변수 중인 스레드가 사용 가능 해질 때까지 대기 합니다.</span><span class="sxs-lookup"><span data-stu-id="6e75a-129">All requests above the returned value of the `pdwMaxWorkerThreads` parameter remain queued until threads become available.</span></span>  
  
 <span data-ttu-id="6e75a-130">호스트의 구현을 제공 하지 않는 경우 `GetMaxThreads`, E_NOTIMPL HRESULT 값을 반환 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6e75a-130">If the host does not provide an implementation of `GetMaxThreads`, it should return an HRESULT value of E_NOTIMPL.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6e75a-131">요구 사항</span><span class="sxs-lookup"><span data-stu-id="6e75a-131">Requirements</span></span>  
 <span data-ttu-id="6e75a-132">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="6e75a-132">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6e75a-133">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="6e75a-133">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="6e75a-134">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="6e75a-134">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="6e75a-135">**.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6e75a-135">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6e75a-136">참고 항목</span><span class="sxs-lookup"><span data-stu-id="6e75a-136">See Also</span></span>  
 <xref:System.Threading.ThreadPool.GetMaxThreads%2A>  
 <xref:System.Threading.ThreadPool>  
 [<span data-ttu-id="6e75a-137">GetMinThreads 메서드</span><span class="sxs-lookup"><span data-stu-id="6e75a-137">GetMinThreads Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-getminthreads-method.md)  
 [<span data-ttu-id="6e75a-138">SetMaxThreads 메서드</span><span class="sxs-lookup"><span data-stu-id="6e75a-138">SetMaxThreads Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-setmaxthreads-method.md)  
 [<span data-ttu-id="6e75a-139">IHostThreadPoolManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="6e75a-139">IHostThreadPoolManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-interface.md)
