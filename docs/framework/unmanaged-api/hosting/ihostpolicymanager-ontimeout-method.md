---
title: IHostPolicyManager::OnTimeout 메서드
ms.date: 03/30/2017
api_name:
- IHostPolicyManager.OnTimeout
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostPolicyManager::OnTimeout
helpviewer_keywords:
- IHostPolicyManager::OnTimeout method [.NET Framework hosting]
- OnTimeout method [.NET Framework hosting]
ms.assetid: 0a313b51-5e4d-4714-a86b-af75cf3902e6
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7f6257cdf966850a17d5cf58ef1ac2e6ab7103b0
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33439376"
---
# <a name="ihostpolicymanagerontimeout-method"></a><span data-ttu-id="507f3-102">IHostPolicyManager::OnTimeout 메서드</span><span class="sxs-lookup"><span data-stu-id="507f3-102">IHostPolicyManager::OnTimeout Method</span></span>
<span data-ttu-id="507f3-103">공용 언어 런타임 (CLR)를 호출 하 여 지정 된 작업을 수행 하려고 하는 호스트에 알립니다는 [iclrpolicymanager:: Setactionontimeout](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setactionontimeout-method.md) 메서드가 시간 제한에 대 한 응답에서입니다.</span><span class="sxs-lookup"><span data-stu-id="507f3-103">Notifies the host that the common language runtime (CLR) is about to take the action specified by a call to the [ICLRPolicyManager::SetActionOnTimeout](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setactionontimeout-method.md) method in response to a timeout.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="507f3-104">구문</span><span class="sxs-lookup"><span data-stu-id="507f3-104">Syntax</span></span>  
  
```  
HRESULT OnTimeout (  
    [in] EClrOperation  operation,   
    [in] EPolicyAction  action  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="507f3-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="507f3-105">Parameters</span></span>  
 `operation`  
 <span data-ttu-id="507f3-106">[in] 중 하나는 [EClrOperation](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md) 시간이 초과 되었습니다 작업의 종류를 나타내는 값입니다.</span><span class="sxs-lookup"><span data-stu-id="507f3-106">[in] One of the [EClrOperation](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md) values, indicating the kind of operation that timed out.</span></span>  
  
 `action`  
 <span data-ttu-id="507f3-107">[in] 중 하나는 [EPolicyAction](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md) 에 대 한 응답 시간 제한 값을 CLR 작업을 나타내는 걸립니다.</span><span class="sxs-lookup"><span data-stu-id="507f3-107">[in] One of the [EPolicyAction](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md) values, indicating the action the CLR is taking in response to the timeout.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="507f3-108">반환 값</span><span class="sxs-lookup"><span data-stu-id="507f3-108">Return Value</span></span>  
  
|<span data-ttu-id="507f3-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="507f3-109">HRESULT</span></span>|<span data-ttu-id="507f3-110">설명</span><span class="sxs-lookup"><span data-stu-id="507f3-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="507f3-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="507f3-111">S_OK</span></span>|<span data-ttu-id="507f3-112">`OnTimeout` 성공적으로 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="507f3-112">`OnTimeout` returned successfully.</span></span>|  
|<span data-ttu-id="507f3-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="507f3-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="507f3-114">CLR은 프로세스에 로드 되지 않았습니다 또는 CLR 중인 상태를 관리 코드를 실행 하거나 호출을 처리할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="507f3-114">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="507f3-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="507f3-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="507f3-116">호출 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="507f3-116">The call timed out.</span></span>|  
|<span data-ttu-id="507f3-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="507f3-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="507f3-118">호출자에 게 잠금을 소유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="507f3-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="507f3-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="507f3-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="507f3-120">차단 된 스레드 이벤트 취소 되었습니다 또는 파이버가 기다리던 합니다.</span><span class="sxs-lookup"><span data-stu-id="507f3-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="507f3-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="507f3-121">E_FAIL</span></span>|<span data-ttu-id="507f3-122">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="507f3-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="507f3-123">메서드가 E_FAIL을 반환 하는 경우 CLR을 하는 프로세스 내에서 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="507f3-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="507f3-124">호스팅 방법에 대 한 후속 호출 HOST_E_CLRNOTAVAILABLE를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="507f3-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="507f3-125">요구 사항</span><span class="sxs-lookup"><span data-stu-id="507f3-125">Requirements</span></span>  
 <span data-ttu-id="507f3-126">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="507f3-126">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="507f3-127">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="507f3-127">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="507f3-128">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="507f3-128">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="507f3-129">**.NET framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="507f3-129">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="507f3-130">참고 항목</span><span class="sxs-lookup"><span data-stu-id="507f3-130">See Also</span></span>  
 [<span data-ttu-id="507f3-131">EClrOperation 열거형</span><span class="sxs-lookup"><span data-stu-id="507f3-131">EClrOperation Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md)  
 [<span data-ttu-id="507f3-132">EPolicyAction 열거형</span><span class="sxs-lookup"><span data-stu-id="507f3-132">EPolicyAction Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md)  
 [<span data-ttu-id="507f3-133">ICLRPolicyManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="507f3-133">ICLRPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-interface.md)  
 [<span data-ttu-id="507f3-134">IHostPolicyManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="507f3-134">IHostPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostpolicymanager-interface.md)
