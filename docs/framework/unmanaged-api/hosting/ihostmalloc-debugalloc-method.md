---
title: IHostMAlloc::DebugAlloc 메서드
ms.date: 03/30/2017
api_name:
- IHostMAlloc.DebugAlloc
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostMAlloc::DebugAlloc
helpviewer_keywords:
- DebugAlloc method [.NET Framework hosting]
- IHostMAlloc::DebugAlloc method [.NET Framework hosting]
ms.assetid: 0bfbc527-bea2-43ce-b041-69186f4440dd
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e3ce303e8bcf33d192dbc7e2447ea6737577dcc5
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54554879"
---
# <a name="ihostmallocdebugalloc-method"></a><span data-ttu-id="32bab-102">IHostMAlloc::DebugAlloc 메서드</span><span class="sxs-lookup"><span data-stu-id="32bab-102">IHostMAlloc::DebugAlloc Method</span></span>
<span data-ttu-id="32bab-103">호스트는 힙에서 지정된 된 양의 메모리를 할당 하 고 또한 메모리가 할당 된 위치를 추적을 요청 합니다.</span><span class="sxs-lookup"><span data-stu-id="32bab-103">Requests that the host allocate the specified amount of memory from the heap, and additionally track where the memory was allocated.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="32bab-104">구문</span><span class="sxs-lookup"><span data-stu-id="32bab-104">Syntax</span></span>  
  
```  
HRESULT DebugAlloc (  
    [in]  SIZE_T  cbSize,   
    [in]  EMemoryCriticalLevel dwCriticalLevel,   
    [in]  char*   pszFileName,   
    [in]  int     iLineNo,   
    [out] void**  ppMem  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="32bab-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="32bab-105">Parameters</span></span>  
 `cbSize`  
 <span data-ttu-id="32bab-106">[in] 현재 메모리 할당 요청 바이트 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="32bab-106">[in] The size, in bytes, of the current memory allocation request.</span></span>  
  
 `dwCriticalLevel`  
 <span data-ttu-id="32bab-107">[in] 중 하나는 [EMemoryCriticalLevel](../../../../docs/framework/unmanaged-api/hosting/ememorycriticallevel-enumeration.md) 할당 오류가의 영향을 나타내는 값입니다.</span><span class="sxs-lookup"><span data-stu-id="32bab-107">[in] One of the [EMemoryCriticalLevel](../../../../docs/framework/unmanaged-api/hosting/ememorycriticallevel-enumeration.md) values, indicating the impact of an allocation failure.</span></span>  
  
 `pszFileName`  
 <span data-ttu-id="32bab-108">[in] 디버깅 중인 실행 파일의 코드 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="32bab-108">[in] The code file of the executable being debugged.</span></span>  
  
 `iLineNo`  
 <span data-ttu-id="32bab-109">[in] 줄 번호 `pszFileName` 할당을 요청 합니다.</span><span class="sxs-lookup"><span data-stu-id="32bab-109">[in] The line number in `pszFileName` where the allocation was requested.</span></span>  
  
 `ppMem`  
 <span data-ttu-id="32bab-110">[out] 할당 된 메모리 또는 요청을 완료할 수 없습니다 경우에 null 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="32bab-110">[out] A pointer to the allocated memory, or null if the request could not be completed.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="32bab-111">반환 값</span><span class="sxs-lookup"><span data-stu-id="32bab-111">Return Value</span></span>  
  
|<span data-ttu-id="32bab-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="32bab-112">HRESULT</span></span>|<span data-ttu-id="32bab-113">설명</span><span class="sxs-lookup"><span data-stu-id="32bab-113">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="32bab-114">S_OK</span><span class="sxs-lookup"><span data-stu-id="32bab-114">S_OK</span></span>|<span data-ttu-id="32bab-115">`DebugAlloc` 성공적으로 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="32bab-115">`DebugAlloc` returned successfully.</span></span>|  
|<span data-ttu-id="32bab-116">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="32bab-116">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="32bab-117">CLR이 로드 된 프로세스에 또는 CLR 상태인는 관리 코드를 실행 하거나 호출을 처리할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="32bab-117">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="32bab-118">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="32bab-118">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="32bab-119">호출 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="32bab-119">The call timed out.</span></span>|  
|<span data-ttu-id="32bab-120">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="32bab-120">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="32bab-121">호출자가 잠금을 소유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="32bab-121">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="32bab-122">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="32bab-122">HOST_E_ABANDONED</span></span>|<span data-ttu-id="32bab-123">이벤트가 차단 된 스레드가 취소 된 또는 파이버를 대기 하 고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="32bab-123">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="32bab-124">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="32bab-124">E_FAIL</span></span>|<span data-ttu-id="32bab-125">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="32bab-125">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="32bab-126">메서드 E_FAIL을 반환 하는 경우 CLR은 프로세스 내에서 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="32bab-126">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="32bab-127">메서드를 호스트 하는 데 대 한 후속 호출 HOST_E_CLRNOTAVAILABLE를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="32bab-127">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="32bab-128">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="32bab-128">E_OUTOFMEMORY</span></span>|<span data-ttu-id="32bab-129">할당 요청을 완료 하려면 사용할 수 있는 메모리가 충분 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="32bab-129">Not enough memory was available to complete the allocation request.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="32bab-130">설명</span><span class="sxs-lookup"><span data-stu-id="32bab-130">Remarks</span></span>  
 <span data-ttu-id="32bab-131">CLR에 대 한 인터페이스 포인터를 가져옵니다는 [IHostMalloc](../../../../docs/framework/unmanaged-api/hosting/ihostmalloc-interface.md) 를 호출 하 여 인스턴스를 [ihostmemorymanager:: Createmalloc](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-createmalloc-method.md) 메서드.</span><span class="sxs-lookup"><span data-stu-id="32bab-131">The CLR gets an interface pointer to an [IHostMalloc](../../../../docs/framework/unmanaged-api/hosting/ihostmalloc-interface.md) instance by calling the [IHostMemoryManager::CreateMalloc](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-createmalloc-method.md) method.</span></span> <span data-ttu-id="32bab-132">`DebugAlloc` 런타임에서를 사용 하 여 디버깅 중에 대 한 코드 파일 정보를 얻을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="32bab-132">`DebugAlloc` allows the runtime to get code file information for use during debugging.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="32bab-133">요구 사항</span><span class="sxs-lookup"><span data-stu-id="32bab-133">Requirements</span></span>  
 <span data-ttu-id="32bab-134">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="32bab-134">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="32bab-135">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="32bab-135">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="32bab-136">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="32bab-136">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="32bab-137">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="32bab-137">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="32bab-138">참고자료</span><span class="sxs-lookup"><span data-stu-id="32bab-138">See also</span></span>
- [<span data-ttu-id="32bab-139">IHostMemoryManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="32bab-139">IHostMemoryManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-interface.md)
- [<span data-ttu-id="32bab-140">IHostMalloc 인터페이스</span><span class="sxs-lookup"><span data-stu-id="32bab-140">IHostMalloc Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmalloc-interface.md)
