---
title: ICLRPolicyManager::SetTimeout 메서드
ms.date: 03/30/2017
api_name:
- ICLRPolicyManager.SetTimeout
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRPolicyManager::SetTimeout
helpviewer_keywords:
- SetTimeout method [.NET Framework hosting]
- ICLRPolicyManager::SetTimeout method [.NET Framework hosting]
ms.assetid: 954404fd-d52d-4e68-b582-8692f3a5f608
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 5b5a389af718322d1e0fffebae046bf28731877b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33435779"
---
# <a name="iclrpolicymanagersettimeout-method"></a><span data-ttu-id="83c8a-102">ICLRPolicyManager::SetTimeout 메서드</span><span class="sxs-lookup"><span data-stu-id="83c8a-102">ICLRPolicyManager::SetTimeout Method</span></span>
<span data-ttu-id="83c8a-103">지정된 된 작업에 대 한 제한 시간 값을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="83c8a-103">Sets a timeout value for the specified operation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="83c8a-104">구문</span><span class="sxs-lookup"><span data-stu-id="83c8a-104">Syntax</span></span>  
  
```  
HRESULT SetTimeout (  
    [in] EClrOperation operation,  
    [in] DWORD dsMilliseconds  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="83c8a-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="83c8a-105">Parameters</span></span>  
 `operation`  
 <span data-ttu-id="83c8a-106">[in] 중 하나는 [EClrOperation](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md) 제한 시간을 설정 하는 작업에 대 한 공용 언어 런타임 (CLR) 작업을 나타내는 값입니다.</span><span class="sxs-lookup"><span data-stu-id="83c8a-106">[in] One of the [EClrOperation](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md) values, indicating the common language runtime (CLR) operation for which to set a timeout.</span></span> <span data-ttu-id="83c8a-107">다음 값이 지원 됩니다.</span><span class="sxs-lookup"><span data-stu-id="83c8a-107">The following values are supported:</span></span>  
  
-   <span data-ttu-id="83c8a-108">OPR_AppDomainUnload</span><span class="sxs-lookup"><span data-stu-id="83c8a-108">OPR_AppDomainUnload</span></span>  
  
-   <span data-ttu-id="83c8a-109">OPR_ProcessExit</span><span class="sxs-lookup"><span data-stu-id="83c8a-109">OPR_ProcessExit</span></span>  
  
-   <span data-ttu-id="83c8a-110">OPR_ThreadRudeAbortInCriticalRegion</span><span class="sxs-lookup"><span data-stu-id="83c8a-110">OPR_ThreadRudeAbortInCriticalRegion</span></span>  
  
-   <span data-ttu-id="83c8a-111">OPR_ThreadRudeAbortInNonCriticalRegion</span><span class="sxs-lookup"><span data-stu-id="83c8a-111">OPR_ThreadRudeAbortInNonCriticalRegion</span></span>  
  
 `dwMilliseconds`  
 <span data-ttu-id="83c8a-112">[in] 새 시간 제한 값, 시간 (밀리초)입니다.</span><span class="sxs-lookup"><span data-stu-id="83c8a-112">[in] The new timeout value, in milliseconds.</span></span> <span data-ttu-id="83c8a-113">값이 INFINITE 하면 시간 초과 되지로 작업 합니다.</span><span class="sxs-lookup"><span data-stu-id="83c8a-113">A value of INFINITE causes the operation never to time out.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="83c8a-114">반환 값</span><span class="sxs-lookup"><span data-stu-id="83c8a-114">Return Value</span></span>  
  
|<span data-ttu-id="83c8a-115">HRESULT</span><span class="sxs-lookup"><span data-stu-id="83c8a-115">HRESULT</span></span>|<span data-ttu-id="83c8a-116">설명</span><span class="sxs-lookup"><span data-stu-id="83c8a-116">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="83c8a-117">S_OK</span><span class="sxs-lookup"><span data-stu-id="83c8a-117">S_OK</span></span>|<span data-ttu-id="83c8a-118">`SetTimeout` 성공적으로 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="83c8a-118">`SetTimeout` returned successfully.</span></span>|  
|<span data-ttu-id="83c8a-119">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="83c8a-119">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="83c8a-120">CLR은 프로세스에 로드 되지 않았습니다 또는 CLR 중인 상태를 관리 코드를 실행 하거나 호출을 처리할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="83c8a-120">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="83c8a-121">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="83c8a-121">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="83c8a-122">호출 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="83c8a-122">The call timed out.</span></span>|  
|<span data-ttu-id="83c8a-123">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="83c8a-123">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="83c8a-124">호출자에 게 잠금을 소유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="83c8a-124">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="83c8a-125">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="83c8a-125">HOST_E_ABANDONED</span></span>|<span data-ttu-id="83c8a-126">차단 된 스레드 이벤트 취소 되었습니다 또는 파이버가 기다리던 합니다.</span><span class="sxs-lookup"><span data-stu-id="83c8a-126">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="83c8a-127">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="83c8a-127">E_FAIL</span></span>|<span data-ttu-id="83c8a-128">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="83c8a-128">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="83c8a-129">E_FAIL을 반환 하는 메서드 후 CLR을 프로세스 내에서 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="83c8a-129">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="83c8a-130">호스팅 방법에 대 한 후속 호출 HOST_E_CLRNOTAVAILABLE를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="83c8a-130">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="83c8a-131">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="83c8a-131">E_INVALIDARG</span></span>|<span data-ttu-id="83c8a-132">시간 초과 설정할 수 없습니다 지정 된 `operation`, 또는 잘못 된 값에 대 한 제공 된 `operation`합니다.</span><span class="sxs-lookup"><span data-stu-id="83c8a-132">A timeout cannot be set for the specified `operation`, or an invalid value was supplied for `operation`.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="83c8a-133">요구 사항</span><span class="sxs-lookup"><span data-stu-id="83c8a-133">Requirements</span></span>  
 <span data-ttu-id="83c8a-134">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="83c8a-134">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="83c8a-135">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="83c8a-135">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="83c8a-136">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="83c8a-136">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="83c8a-137">**.NET framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="83c8a-137">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="83c8a-138">참고 항목</span><span class="sxs-lookup"><span data-stu-id="83c8a-138">See Also</span></span>  
 [<span data-ttu-id="83c8a-139">EClrOperation 열거형</span><span class="sxs-lookup"><span data-stu-id="83c8a-139">EClrOperation Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md)  
 [<span data-ttu-id="83c8a-140">ICLRControl 인터페이스</span><span class="sxs-lookup"><span data-stu-id="83c8a-140">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)  
 [<span data-ttu-id="83c8a-141">ICLRPolicyManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="83c8a-141">ICLRPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-interface.md)
