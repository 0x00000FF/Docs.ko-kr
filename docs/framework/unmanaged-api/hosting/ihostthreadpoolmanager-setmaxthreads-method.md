---
title: IHostThreadPoolManager::SetMaxThreads 메서드
ms.date: 03/30/2017
api_name:
- IHostThreadPoolManager.SetMaxThreads
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostThreadPoolManager::SetMaxThreads
helpviewer_keywords:
- IHostThreadPoolManager::SetMaxThreads method [.NET Framework hosting]
- SetMaxThreads method, IHostThreadPoolManager interface [.NET Framework hosting]
ms.assetid: 77cfd347-95c2-4425-b807-4ecc2a8d4578
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 905ce9183d295568977eb7e216e5327d6b4ee8bb
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54636094"
---
# <a name="ihostthreadpoolmanagersetmaxthreads-method"></a><span data-ttu-id="08825-102">IHostThreadPoolManager::SetMaxThreads 메서드</span><span class="sxs-lookup"><span data-stu-id="08825-102">IHostThreadPoolManager::SetMaxThreads Method</span></span>
<span data-ttu-id="08825-103">스레드 풀에서 호스트를 유지할 수 있는 스레드의 최대 수를 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="08825-103">Sets the maximum number of threads that the host can maintain in the thread pool.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="08825-104">구문</span><span class="sxs-lookup"><span data-stu-id="08825-104">Syntax</span></span>  
  
```  
HRESULT SetMaxThreads (  
    [in] DWORD MaxThreads  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="08825-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="08825-105">Parameters</span></span>  
 `MaxThreads`  
 <span data-ttu-id="08825-106">스레드 풀에 있는 최대 작업자 스레드 수입니다.</span><span class="sxs-lookup"><span data-stu-id="08825-106">The maximum number of worker threads in the thread pool.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="08825-107">반환 값</span><span class="sxs-lookup"><span data-stu-id="08825-107">Return Value</span></span>  
  
|<span data-ttu-id="08825-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="08825-108">HRESULT</span></span>|<span data-ttu-id="08825-109">설명</span><span class="sxs-lookup"><span data-stu-id="08825-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="08825-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="08825-110">S_OK</span></span>|<span data-ttu-id="08825-111">`SetMaxThreads` 성공적으로 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="08825-111">`SetMaxThreads` returned successfully.</span></span>|  
|<span data-ttu-id="08825-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="08825-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="08825-113">프로세스에는 CLR (공용 언어 런타임)에 로드 되지 또는 CLR 상태인는 관리 코드를 실행 하거나 호출을 처리할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="08825-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="08825-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="08825-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="08825-115">호출 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="08825-115">The call timed out.</span></span>|  
|<span data-ttu-id="08825-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="08825-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="08825-117">호출자가 잠금을 소유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="08825-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="08825-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="08825-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="08825-119">이벤트가 차단 된 스레드가 취소 된 또는 파이버를 대기 하 고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="08825-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="08825-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="08825-120">E_FAIL</span></span>|<span data-ttu-id="08825-121">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="08825-121">An unknown, catastrophic failure occurred.</span></span> <span data-ttu-id="08825-122">메서드 E_FAIL을 반환 하는 경우 CLR은 프로세스 내에서 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="08825-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="08825-123">메서드를 호스트 하는 데 대 한 후속 호출 HOST_E_CLRNOTAVAILABLE를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="08825-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="08825-124">E_NOTIMPL</span><span class="sxs-lookup"><span data-stu-id="08825-124">E_NOTIMPL</span></span>|<span data-ttu-id="08825-125">호스트의 구현을 제공 하지 않습니다 `SetMaxThreads`합니다.</span><span class="sxs-lookup"><span data-stu-id="08825-125">The host does not provide an implementation of `SetMaxThreads`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="08825-126">설명</span><span class="sxs-lookup"><span data-stu-id="08825-126">Remarks</span></span>  
 <span data-ttu-id="08825-127">호스트는 CLR 스레드 풀의 크기를 구성할 수 있도록 필요 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="08825-127">A host is not required to allow the CLR to configure the size of the thread pool.</span></span> <span data-ttu-id="08825-128">일부 호스트 구현, 성능, 확장성 등의 이유로 대해 스레드 풀에 대 한 독점적인 제어권이 필요할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="08825-128">Some hosts might want exclusive control over the thread pool, for reasons such as implementation, performance, or scalability.</span></span> <span data-ttu-id="08825-129">이 경우 호스트 e_notimpl HRESULT 값을 반환 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="08825-129">In this case, a host should return an HRESULT value of E_NOTIMPL.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="08825-130">요구 사항</span><span class="sxs-lookup"><span data-stu-id="08825-130">Requirements</span></span>  
 <span data-ttu-id="08825-131">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="08825-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="08825-132">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="08825-132">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="08825-133">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="08825-133">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="08825-134">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="08825-134">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="08825-135">참고자료</span><span class="sxs-lookup"><span data-stu-id="08825-135">See also</span></span>
- <xref:System.Threading.ThreadPool.SetMaxThreads%2A>
- <xref:System.Threading.ThreadPool>
- [<span data-ttu-id="08825-136">GetMaxThreads 메서드</span><span class="sxs-lookup"><span data-stu-id="08825-136">GetMaxThreads Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-getmaxthreads-method.md)
- [<span data-ttu-id="08825-137">SetMinThreads 메서드</span><span class="sxs-lookup"><span data-stu-id="08825-137">SetMinThreads Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-setminthreads-method.md)
- [<span data-ttu-id="08825-138">IHostThreadPoolManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="08825-138">IHostThreadPoolManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-interface.md)
