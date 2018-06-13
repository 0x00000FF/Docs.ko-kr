---
title: IHostCrst::Enter 메서드
ms.date: 03/30/2017
api_name:
- IHostCrst.Enter
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostCrst::Enter
helpviewer_keywords:
- Enter method [.NET Framework hosting]
- IHostCrst::Enter method [.NET Framework hosting]
ms.assetid: 100dd7eb-7053-4295-9bb3-32ba47f6ec79
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a472b686799bfec4b53b8880a0c52c6f0846b03a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33442379"
---
# <a name="ihostcrstenter-method"></a><span data-ttu-id="e5f73-102">IHostCrst::Enter 메서드</span><span class="sxs-lookup"><span data-stu-id="e5f73-102">IHostCrst::Enter Method</span></span>
<span data-ttu-id="e5f73-103">현재 표시 되는 임계 영역 입력 [IHostCrst](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-interface.md) 인스턴스.</span><span class="sxs-lookup"><span data-stu-id="e5f73-103">Enters the critical section that is represented by the current [IHostCrst](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-interface.md) instance.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e5f73-104">구문</span><span class="sxs-lookup"><span data-stu-id="e5f73-104">Syntax</span></span>  
  
```  
HRESULT Enter (  
    [in] DWORD option  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="e5f73-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="e5f73-105">Parameters</span></span>  
 `option`  
 <span data-ttu-id="e5f73-106">[in] 중 하나는 [WAIT_OPTION](../../../../docs/framework/unmanaged-api/hosting/wait-option-enumeration.md) 값을 호스트 하는 경우 수행할 동작을 나타내는 작업을 차단 합니다.</span><span class="sxs-lookup"><span data-stu-id="e5f73-106">[in] One of the [WAIT_OPTION](../../../../docs/framework/unmanaged-api/hosting/wait-option-enumeration.md) values, indicating what action the host should take if the operation blocks.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e5f73-107">반환 값</span><span class="sxs-lookup"><span data-stu-id="e5f73-107">Return Value</span></span>  
  
|<span data-ttu-id="e5f73-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="e5f73-108">HRESULT</span></span>|<span data-ttu-id="e5f73-109">설명</span><span class="sxs-lookup"><span data-stu-id="e5f73-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="e5f73-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="e5f73-110">S_OK</span></span>|<span data-ttu-id="e5f73-111">`Enter` 성공적으로 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="e5f73-111">`Enter` returned successfully.</span></span>|  
|<span data-ttu-id="e5f73-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="e5f73-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="e5f73-113">공용 언어 런타임 (CLR) 프로세스에 로드 되지 않았습니다 또는 CLR 중인 상태를 관리 코드를 실행 하거나 호출을 처리할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e5f73-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="e5f73-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="e5f73-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="e5f73-115">호출 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="e5f73-115">The call timed out.</span></span>|  
|<span data-ttu-id="e5f73-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="e5f73-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="e5f73-117">호출자에 게 잠금을 소유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e5f73-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="e5f73-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="e5f73-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="e5f73-119">차단 된 스레드 이벤트 취소 되었습니다 또는 파이버가 기다리던 합니다.</span><span class="sxs-lookup"><span data-stu-id="e5f73-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="e5f73-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="e5f73-120">E_FAIL</span></span>|<span data-ttu-id="e5f73-121">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="e5f73-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="e5f73-122">메서드가 E_FAIL을 반환 하는 경우 CLR을 하는 프로세스 내에서 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e5f73-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="e5f73-123">호스팅 방법에 대 한 후속 호출 HOST_E_CLRNOTAVAILABLE를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="e5f73-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e5f73-124">설명</span><span class="sxs-lookup"><span data-stu-id="e5f73-124">Remarks</span></span>  
 <span data-ttu-id="e5f73-125">`Enter` Win32 미러링 `EnterCriticalSection` 함수입니다.</span><span class="sxs-lookup"><span data-stu-id="e5f73-125">`Enter` mirrors the Win32 `EnterCriticalSection` function.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e5f73-126">이 메서드는 임계 영역 입력 될 때까지 반환 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e5f73-126">This method does not return until the critical section is entered.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e5f73-127">요구 사항</span><span class="sxs-lookup"><span data-stu-id="e5f73-127">Requirements</span></span>  
 <span data-ttu-id="e5f73-128">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="e5f73-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e5f73-129">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="e5f73-129">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="e5f73-130">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="e5f73-130">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="e5f73-131">**.NET framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e5f73-131">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e5f73-132">참고 항목</span><span class="sxs-lookup"><span data-stu-id="e5f73-132">See Also</span></span>  
 [<span data-ttu-id="e5f73-133">ICLRSyncManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="e5f73-133">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)  
 [<span data-ttu-id="e5f73-134">IHostCrst 인터페이스</span><span class="sxs-lookup"><span data-stu-id="e5f73-134">IHostCrst Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-interface.md)  
 [<span data-ttu-id="e5f73-135">IHostSyncManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="e5f73-135">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)
