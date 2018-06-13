---
title: IHostIoCompletionManager::CreateIoCompletionPort 메서드
ms.date: 03/30/2017
api_name:
- IHostIoCompletionManager.CreateIoCompletionPort
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostIoCompletionManager::CreateIoCompletionPort
helpviewer_keywords:
- IHostIoCompletionManager::CreateIoCompletionPort method [.NET Framework hosting]
- CreateIoCompletionPort method [.NET Framework hosting]
ms.assetid: 907a2b43-68db-44a7-acac-89e792e7bb3c
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 52e1dd05a87eaf06b5352d7c8d63c402a65d95ab
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33439077"
---
# <a name="ihostiocompletionmanagercreateiocompletionport-method"></a><span data-ttu-id="6486c-102">IHostIoCompletionManager::CreateIoCompletionPort 메서드</span><span class="sxs-lookup"><span data-stu-id="6486c-102">IHostIoCompletionManager::CreateIoCompletionPort Method</span></span>
<span data-ttu-id="6486c-103">요청 호스트 새 I/O 완료 포트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="6486c-103">Requests that the host create a new I/O completion port.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6486c-104">구문</span><span class="sxs-lookup"><span data-stu-id="6486c-104">Syntax</span></span>  
  
```  
HRESULT CreateIoCompletionPort (  
    [out] HANDLE *phPort  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="6486c-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="6486c-105">Parameters</span></span>  
 `phPort`  
 <span data-ttu-id="6486c-106">[out] 새로 만든된 I/O 완료 포트 또는 0 (영), 포트를 만들 수 없는 경우에 대 한 핸들에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="6486c-106">[out] A pointer to a handle to the newly created I/O completion port, or 0 (zero), if the port could not be created.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="6486c-107">반환 값</span><span class="sxs-lookup"><span data-stu-id="6486c-107">Return Value</span></span>  
  
|<span data-ttu-id="6486c-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="6486c-108">HRESULT</span></span>|<span data-ttu-id="6486c-109">설명</span><span class="sxs-lookup"><span data-stu-id="6486c-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="6486c-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="6486c-110">S_OK</span></span>|<span data-ttu-id="6486c-111">`CreateIoCompletionPort` 성공적으로 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="6486c-111">`CreateIoCompletionPort` returned successfully.</span></span>|  
|<span data-ttu-id="6486c-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="6486c-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="6486c-113">공용 언어 런타임 (CLR) 프로세스에 로드 되지 않았습니다 또는 CLR 중인 상태를 관리 코드를 실행 하거나 호출을 처리할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="6486c-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="6486c-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="6486c-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="6486c-115">호출 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="6486c-115">The call timed out.</span></span>|  
|<span data-ttu-id="6486c-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="6486c-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="6486c-117">호출자에 게 잠금을 소유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6486c-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="6486c-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="6486c-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="6486c-119">차단 된 스레드 이벤트 취소 되었습니다 또는 파이버가 기다리던 합니다.</span><span class="sxs-lookup"><span data-stu-id="6486c-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="6486c-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="6486c-120">E_FAIL</span></span>|<span data-ttu-id="6486c-121">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="6486c-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="6486c-122">메서드가 E_FAIL을 반환 하는 경우 CLR을 하는 프로세스 내에서 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="6486c-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="6486c-123">호스팅 방법에 대 한 후속 호출 HOST_E_CLRNOTAVAILABLE를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="6486c-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="6486c-124">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="6486c-124">E_OUTOFMEMORY</span></span>|<span data-ttu-id="6486c-125">요청 된 리소스를 할당할 메모리가 충분 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6486c-125">Not enough memory was available to allocate the requested resource.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6486c-126">설명</span><span class="sxs-lookup"><span data-stu-id="6486c-126">Remarks</span></span>  
 <span data-ttu-id="6486c-127">CLR에서는 `CreateIoCompletionPort` 메서드를 만들도록 새 I/O 완료 포트를 호스트에 요청 합니다.</span><span class="sxs-lookup"><span data-stu-id="6486c-127">The CLR calls the `CreateIoCompletionPort` method to request that the host create a new I/O completion port.</span></span> <span data-ttu-id="6486c-128">I/O 작업에 대 한 호출을 통해이 포트에 바인딩되기는 [ihostiocompletionmanager:: Bind](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-bind-method.md) 메서드.</span><span class="sxs-lookup"><span data-stu-id="6486c-128">It binds I/O operations to this port through a call to the [IHostIoCompletionManager::Bind](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-bind-method.md) method.</span></span> <span data-ttu-id="6486c-129">호스트 상태를 보고를 CLR로 호출 하 여 [iclriocompletionmanager:: Oncomplete](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-oncomplete-method.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="6486c-129">The host reports status back to the CLR by calling [ICLRIoCompletionManager::OnComplete](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-oncomplete-method.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6486c-130">요구 사항</span><span class="sxs-lookup"><span data-stu-id="6486c-130">Requirements</span></span>  
 <span data-ttu-id="6486c-131">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="6486c-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6486c-132">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="6486c-132">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="6486c-133">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="6486c-133">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="6486c-134">**.NET framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6486c-134">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6486c-135">참고 항목</span><span class="sxs-lookup"><span data-stu-id="6486c-135">See Also</span></span>  
 [<span data-ttu-id="6486c-136">ICLRIoCompletionManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="6486c-136">ICLRIoCompletionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-interface.md)  
 [<span data-ttu-id="6486c-137">IHostIoCompletionManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="6486c-137">IHostIoCompletionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-interface.md)
