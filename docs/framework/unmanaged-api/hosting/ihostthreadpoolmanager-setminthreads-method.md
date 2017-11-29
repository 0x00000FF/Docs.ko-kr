---
title: "IHostThreadPoolManager::SetMinThreads 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IHostThreadPoolManager.SetMinThreads
api_location: mscoree.dll
api_type: COM
f1_keywords: IHostThreadPoolManager::SetMinThreads
helpviewer_keywords:
- SetMinThreads method, IHostThreadPoolManager interface [.NET Framework hosting]
- IHostThreadPoolManager::SetMinThreads method [.NET Framework hosting]
ms.assetid: 10409db9-9fd2-4e4d-b8cd-cf6fec0afaa2
topic_type: apiref
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: ab0b107c050b1c4b686f761ede75ea2349825270
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="ihostthreadpoolmanagersetminthreads-method"></a><span data-ttu-id="614d4-102">IHostThreadPoolManager::SetMinThreads 메서드</span><span class="sxs-lookup"><span data-stu-id="614d4-102">IHostThreadPoolManager::SetMinThreads Method</span></span>
<span data-ttu-id="614d4-103">요청에 대비 하 여에서 호스트를 유지 해야 하는 유휴 상태 스레드의 최소 개수를 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="614d4-103">Sets the minimum number of idle threads that the host must maintain in anticipation of requests.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="614d4-104">구문</span><span class="sxs-lookup"><span data-stu-id="614d4-104">Syntax</span></span>  
  
```  
HRESULT SetMinThreads (  
    [in] DWORD MinThreads  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="614d4-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="614d4-105">Parameters</span></span>  
 `MinThreads`  
 <span data-ttu-id="614d4-106">[in] 호스트를 유지 해야 하는 스레드의 새 최소 수입니다.</span><span class="sxs-lookup"><span data-stu-id="614d4-106">[in] The new minimum number of threads that the host must maintain.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="614d4-107">반환 값</span><span class="sxs-lookup"><span data-stu-id="614d4-107">Return Value</span></span>  
  
|<span data-ttu-id="614d4-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="614d4-108">HRESULT</span></span>|<span data-ttu-id="614d4-109">설명</span><span class="sxs-lookup"><span data-stu-id="614d4-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="614d4-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="614d4-110">S_OK</span></span>|<span data-ttu-id="614d4-111">`SetMinThreads`성공적으로 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="614d4-111">`SetMinThreads` returned successfully.</span></span>|  
|<span data-ttu-id="614d4-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="614d4-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="614d4-113">공용 언어 런타임 (CLR) 프로세스에 로드 되지 않았습니다 또는 CLR 중인 상태를 관리 코드를 실행 하거나 호출을 처리할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="614d4-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="614d4-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="614d4-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="614d4-115">호출 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="614d4-115">The call timed out.</span></span>|  
|<span data-ttu-id="614d4-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="614d4-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="614d4-117">호출자에 게 잠금을 소유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="614d4-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="614d4-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="614d4-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="614d4-119">차단 된 스레드 이벤트 취소 되었습니다 또는 파이버가 기다리던 합니다.</span><span class="sxs-lookup"><span data-stu-id="614d4-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="614d4-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="614d4-120">E_FAIL</span></span>|<span data-ttu-id="614d4-121">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="614d4-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="614d4-122">메서드가 E_FAIL을 반환 하는 경우 CLR을 하는 프로세스 내에서 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="614d4-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="614d4-123">호스팅 방법에 대 한 후속 호출 HOST_E_CLRNOTAVAILABLE를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="614d4-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="614d4-124">E_NOTIMPL</span><span class="sxs-lookup"><span data-stu-id="614d4-124">E_NOTIMPL</span></span>|<span data-ttu-id="614d4-125">호스트의 구현을 제공 하지 않는 `SetMinThreads`합니다.</span><span class="sxs-lookup"><span data-stu-id="614d4-125">The host does not provide an implementation of `SetMinThreads`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="614d4-126">설명</span><span class="sxs-lookup"><span data-stu-id="614d4-126">Remarks</span></span>  
 <span data-ttu-id="614d4-127">호스트의 구현을 제공 하지 않아도 됩니다 `SetMinThreads`합니다.</span><span class="sxs-lookup"><span data-stu-id="614d4-127">A host is not required to provide an implementation of `SetMinThreads`.</span></span> <span data-ttu-id="614d4-128">이 경우 E_NOTIMPL HRESULT 값을 반환 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="614d4-128">In this case, it should return an HRESULT value of E_NOTIMPL.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="614d4-129">요구 사항</span><span class="sxs-lookup"><span data-stu-id="614d4-129">Requirements</span></span>  
 <span data-ttu-id="614d4-130">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="614d4-130">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="614d4-131">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="614d4-131">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="614d4-132">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="614d4-132">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="614d4-133">**.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="614d4-133">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="614d4-134">참고 항목</span><span class="sxs-lookup"><span data-stu-id="614d4-134">See Also</span></span>  
 <xref:System.Threading.ThreadPool.SetMinThreads%2A>  
 <xref:System.Threading.ThreadPool>  
 [<span data-ttu-id="614d4-135">GetMinThreads 메서드</span><span class="sxs-lookup"><span data-stu-id="614d4-135">GetMinThreads Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-getminthreads-method.md)  
 [<span data-ttu-id="614d4-136">SetMaxThreads 메서드</span><span class="sxs-lookup"><span data-stu-id="614d4-136">SetMaxThreads Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-setmaxthreads-method.md)  
 [<span data-ttu-id="614d4-137">IHostThreadPoolManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="614d4-137">IHostThreadPoolManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-interface.md)
