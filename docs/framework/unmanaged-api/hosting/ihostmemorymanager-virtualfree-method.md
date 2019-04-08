---
title: IHostMemoryManager::VirtualFree 메서드
ms.date: 03/30/2017
api_name:
- IHostMemoryManager.VirtualFree
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostMemoryManager::VirtualFree
helpviewer_keywords:
- IHostMemoryManager::VirtualFree method [.NET Framework hosting]
- VirtualFree method [.NET Framework hosting]
ms.assetid: 1a436e89-eb28-4d15-bcf1-a072f86dbd99
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 03cac2b8433d6491d1fa474a0d4064ef4e260d6e
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59099913"
---
# <a name="ihostmemorymanagervirtualfree-method"></a><span data-ttu-id="1ad1f-102">IHostMemoryManager::VirtualFree 메서드</span><span class="sxs-lookup"><span data-stu-id="1ad1f-102">IHostMemoryManager::VirtualFree Method</span></span>
<span data-ttu-id="1ad1f-103">역할을 해당 하는 Win32 함수에 대 한 논리적 래퍼입니다.</span><span class="sxs-lookup"><span data-stu-id="1ad1f-103">Serves as a logical wrapper for the corresponding Win32 function.</span></span> <span data-ttu-id="1ad1f-104">Win32 구현의 `VirtualFree` 해제, 커밋 또는 해제 하 고 호출 하는 프로세스의 가상 주소 공간 내의 페이지 영역을 커밋 해제 합니다.</span><span class="sxs-lookup"><span data-stu-id="1ad1f-104">The Win32 implementation of `VirtualFree` releases, decommits, or releases and decommits a region of pages within the virtual address space of the calling process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1ad1f-105">구문</span><span class="sxs-lookup"><span data-stu-id="1ad1f-105">Syntax</span></span>  
  
```  
HRESULT VirtualFree (  
    [in] LPVOID  lpAddress,  
    [in] SIZE_T  dwSize,  
    [in] DWORD   dwFreeType  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1ad1f-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="1ad1f-106">Parameters</span></span>  
 `lpAddress`  
 <span data-ttu-id="1ad1f-107">[in] 해제할 가상 메모리 페이지의 기본 주소에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="1ad1f-107">[in] A pointer to the base address of the virtual memory pages to be freed.</span></span>  
  
 `dwSize`  
 <span data-ttu-id="1ad1f-108">[in] 해제할 영역의 바이트 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="1ad1f-108">[in] The size, in bytes, of the region to be freed.</span></span>  
  
 `dwFreeType`  
 <span data-ttu-id="1ad1f-109">[in] 해제 작업의 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="1ad1f-109">[in] The type of freeing operation.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="1ad1f-110">반환 값</span><span class="sxs-lookup"><span data-stu-id="1ad1f-110">Return Value</span></span>  
  
|<span data-ttu-id="1ad1f-111">HRESULT</span><span class="sxs-lookup"><span data-stu-id="1ad1f-111">HRESULT</span></span>|<span data-ttu-id="1ad1f-112">설명</span><span class="sxs-lookup"><span data-stu-id="1ad1f-112">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="1ad1f-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="1ad1f-113">S_OK</span></span>|`VirtualFree` <span data-ttu-id="1ad1f-114">성공적으로 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="1ad1f-114">returned successfully.</span></span>|  
|<span data-ttu-id="1ad1f-115">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="1ad1f-115">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="1ad1f-116">프로세스에는 CLR (공용 언어 런타임)에 로드 되지 또는 CLR 상태인는 관리 코드를 실행 하거나 호출을 처리할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="1ad1f-116">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="1ad1f-117">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="1ad1f-117">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="1ad1f-118">호출 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="1ad1f-118">The call timed out.</span></span>|  
|<span data-ttu-id="1ad1f-119">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="1ad1f-119">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="1ad1f-120">호출자가 잠금을 소유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1ad1f-120">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="1ad1f-121">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="1ad1f-121">HOST_E_ABANDONED</span></span>|<span data-ttu-id="1ad1f-122">이벤트가 차단 된 스레드가 취소 된 또는 파이버를 대기 하 고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1ad1f-122">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="1ad1f-123">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="1ad1f-123">E_FAIL</span></span>|<span data-ttu-id="1ad1f-124">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="1ad1f-124">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="1ad1f-125">메서드 E_FAIL을 반환 하는 경우 CLR은 프로세스 내에서 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="1ad1f-125">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="1ad1f-126">메서드를 호스트 하는 데 대 한 후속 호출 HOST_E_CLRNOTAVAILABLE를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="1ad1f-126">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="1ad1f-127">HOST_E_INVALIDOPERATION</span><span class="sxs-lookup"><span data-stu-id="1ad1f-127">HOST_E_INVALIDOPERATION</span></span>|<span data-ttu-id="1ad1f-128">호스트를 통해 할당 되지 않은 메모리를 해제 하려고 했습니다.</span><span class="sxs-lookup"><span data-stu-id="1ad1f-128">An attempt was made to free memory that was not allocated through the host.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1ad1f-129">설명</span><span class="sxs-lookup"><span data-stu-id="1ad1f-129">Remarks</span></span>  
 `VirtualFree` <span data-ttu-id="1ad1f-130">연결 된 가상 메모리 페이지를 해제 합니다 `lpAddress` 대 한 이전 호출을 통해 매개 변수를 [ihostmemorymanager:: Virtualalloc](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-virtualalloc-method.md) 함수입니다.</span><span class="sxs-lookup"><span data-stu-id="1ad1f-130">frees virtual memory pages associated with the `lpAddress` parameter through an earlier call to the [IHostMemoryManager::VirtualAlloc](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-virtualalloc-method.md) function.</span></span> <span data-ttu-id="1ad1f-131">호스트를 통해 할당 되지 않은 메모리를 확보 하려고 HOST_E_INVALIDOPERATION 반환 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1ad1f-131">Attempts to free memory that was not allocated through the host should return HOST_E_INVALIDOPERATION.</span></span>  
  
 <span data-ttu-id="1ad1f-132">의미 체계는 동일 하 게 Win32 구현의 `VirtualFree`합니다.</span><span class="sxs-lookup"><span data-stu-id="1ad1f-132">The semantics are identical to those of the Win32 implementation of `VirtualFree`.</span></span> <span data-ttu-id="1ad1f-133">자세한 내용은 Windows 플랫폼 설명서를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="1ad1f-133">For more information, see the Windows Platform documentation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1ad1f-134">요구 사항</span><span class="sxs-lookup"><span data-stu-id="1ad1f-134">Requirements</span></span>  
 <span data-ttu-id="1ad1f-135">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="1ad1f-135">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1ad1f-136">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="1ad1f-136">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="1ad1f-137">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="1ad1f-137">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="1ad1f-138">.NET Framework 버전:</span><span class="sxs-lookup"><span data-stu-id="1ad1f-138">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="1ad1f-139">참고자료</span><span class="sxs-lookup"><span data-stu-id="1ad1f-139">See also</span></span>

- [<span data-ttu-id="1ad1f-140">IHostMemoryManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="1ad1f-140">IHostMemoryManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-interface.md)
- [<span data-ttu-id="1ad1f-141">IHostMalloc 인터페이스</span><span class="sxs-lookup"><span data-stu-id="1ad1f-141">IHostMalloc Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmalloc-interface.md)
