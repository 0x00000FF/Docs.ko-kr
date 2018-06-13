---
title: ICLRPolicyManager::SetDefaultAction 메서드
ms.date: 03/30/2017
api_name:
- ICLRPolicyManager.SetDefaultAction
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRPolicyManager::SetDefaultAction
helpviewer_keywords:
- SetDefaultAction method [.NET Framework hosting]
- ICLRPolicyManager::SetDefaultAction method [.NET Framework hosting]
ms.assetid: f9411e7a-27df-451f-9f6c-d643d6a7a7ce
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9a183c7491ad5d67bc2c68edba3ef2d54839da12
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33435452"
---
# <a name="iclrpolicymanagersetdefaultaction-method"></a><span data-ttu-id="55a2d-102">ICLRPolicyManager::SetDefaultAction 메서드</span><span class="sxs-lookup"><span data-stu-id="55a2d-102">ICLRPolicyManager::SetDefaultAction Method</span></span>
<span data-ttu-id="55a2d-103">지정 된 작업이 수행 될 때 공용 언어 런타임 (CLR) 수행할 정책 동작을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="55a2d-103">Specifies the policy action the common language runtime (CLR) should take when the specified operation occurs.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="55a2d-104">구문</span><span class="sxs-lookup"><span data-stu-id="55a2d-104">Syntax</span></span>  
  
```  
HRESULT SetDefaultAction (  
    [in] EClrOperation operation,  
    [in] EPolicyAction action  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="55a2d-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="55a2d-105">Parameters</span></span>  
 `operation`  
 <span data-ttu-id="55a2d-106">[in] 중 하나는 [EClrOperation](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md) 는 CLR에 대 한 동작을 사용자 지정할 수는 작업을 나타내는 값입니다.</span><span class="sxs-lookup"><span data-stu-id="55a2d-106">[in] One of the [EClrOperation](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md) values, indicating the action for which CLR behavior should be customized.</span></span>  
  
 `action`  
 <span data-ttu-id="55a2d-107">[in] 중 하나는 [EPolicyAction](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md) 때 수행할 CLR 정책 동작을 나타내는 값을 `operation` 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="55a2d-107">[in] One of the [EPolicyAction](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md) values, indicating the policy action the CLR should take when `operation` occurs.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="55a2d-108">반환 값</span><span class="sxs-lookup"><span data-stu-id="55a2d-108">Return Value</span></span>  
  
|<span data-ttu-id="55a2d-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="55a2d-109">HRESULT</span></span>|<span data-ttu-id="55a2d-110">설명</span><span class="sxs-lookup"><span data-stu-id="55a2d-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="55a2d-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="55a2d-111">S_OK</span></span>|<span data-ttu-id="55a2d-112">`SetDefaultAction` 성공적으로 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="55a2d-112">`SetDefaultAction` returned successfully.</span></span>|  
|<span data-ttu-id="55a2d-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="55a2d-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="55a2d-114">CLR은 프로세스에 로드 되지 않았습니다 또는 CLR 중인 상태를 관리 코드를 실행 하거나 호출을 처리할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="55a2d-114">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="55a2d-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="55a2d-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="55a2d-116">호출 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="55a2d-116">The call timed out.</span></span>|  
|<span data-ttu-id="55a2d-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="55a2d-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="55a2d-118">호출자에 게 잠금을 소유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="55a2d-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="55a2d-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="55a2d-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="55a2d-120">차단 된 스레드 이벤트 취소 되었습니다 또는 파이버가 기다리던 합니다.</span><span class="sxs-lookup"><span data-stu-id="55a2d-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="55a2d-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="55a2d-121">E_FAIL</span></span>|<span data-ttu-id="55a2d-122">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="55a2d-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="55a2d-123">E_FAIL을 반환 하는 메서드 후 CLR을 프로세스 내에서 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="55a2d-123">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="55a2d-124">호스팅 방법에 대 한 후속 호출 HOST_E_CLRNOTAVAILABLE를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="55a2d-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="55a2d-125">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="55a2d-125">E_INVALIDARG</span></span>|<span data-ttu-id="55a2d-126">잘못 된 `action` 에 대해 지정 된 된 `operation`, 또는 잘못 된 값에 대 한 제공 된 `operation`합니다.</span><span class="sxs-lookup"><span data-stu-id="55a2d-126">An invalid `action` was specified for the `operation`, or an invalid value was supplied for `operation`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="55a2d-127">설명</span><span class="sxs-lookup"><span data-stu-id="55a2d-127">Remarks</span></span>  
 <span data-ttu-id="55a2d-128">CLR 작업에 대 한 기본 동작으로 정책 작업 값 중 일부를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="55a2d-128">Not all policy action values can be specified as the default behavior for CLR operations.</span></span> <span data-ttu-id="55a2d-129">`SetDefaultAction` 에스컬레이션 동작에만 일반적으로 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="55a2d-129">`SetDefaultAction` can typically be used only to escalate behavior.</span></span> <span data-ttu-id="55a2d-130">예를 들어 호스트 스레드 중단으로 강제 변환할 수 있는지 지정할 수 스레드 중단 있지만 반대 작업을 지정할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="55a2d-130">For example, a host can specify that thread aborts be turned into rude thread aborts, but cannot specify the opposite.</span></span> <span data-ttu-id="55a2d-131">아래 표에서 설명 하는 유효한 `action` 각각의 가능한 값 `operation` 값입니다.</span><span class="sxs-lookup"><span data-stu-id="55a2d-131">The table below describes the valid `action` values for each possible `operation` value.</span></span>  
  
|<span data-ttu-id="55a2d-132">에 대 한 값 `operation`</span><span class="sxs-lookup"><span data-stu-id="55a2d-132">Value for `operation`</span></span>|<span data-ttu-id="55a2d-133">에 대 한 유효한 값 `action`</span><span class="sxs-lookup"><span data-stu-id="55a2d-133">Valid values for `action`</span></span>|  
|---------------------------|-------------------------------|  
|<span data-ttu-id="55a2d-134">OPR_ThreadAbort</span><span class="sxs-lookup"><span data-stu-id="55a2d-134">OPR_ThreadAbort</span></span>|<span data-ttu-id="55a2d-135">-eAbortThread</span><span class="sxs-lookup"><span data-stu-id="55a2d-135">-   eAbortThread</span></span><br /><span data-ttu-id="55a2d-136">-eRudeAbortThread</span><span class="sxs-lookup"><span data-stu-id="55a2d-136">-   eRudeAbortThread</span></span><br /><span data-ttu-id="55a2d-137">-eUnloadAppDomain</span><span class="sxs-lookup"><span data-stu-id="55a2d-137">-   eUnloadAppDomain</span></span><br /><span data-ttu-id="55a2d-138">-eRudeUnloadAppDomain</span><span class="sxs-lookup"><span data-stu-id="55a2d-138">-   eRudeUnloadAppDomain</span></span><br /><span data-ttu-id="55a2d-139">-eExitProcess</span><span class="sxs-lookup"><span data-stu-id="55a2d-139">-   eExitProcess</span></span><br /><span data-ttu-id="55a2d-140">-eFastExitProcess</span><span class="sxs-lookup"><span data-stu-id="55a2d-140">-   eFastExitProcess</span></span><br /><span data-ttu-id="55a2d-141">-eRudeExitProcess</span><span class="sxs-lookup"><span data-stu-id="55a2d-141">-   eRudeExitProcess</span></span><br /><span data-ttu-id="55a2d-142">-eDisableRuntime</span><span class="sxs-lookup"><span data-stu-id="55a2d-142">-   eDisableRuntime</span></span>|  
|<span data-ttu-id="55a2d-143">OPR_ThreadRudeAbortInNonCriticalRegion</span><span class="sxs-lookup"><span data-stu-id="55a2d-143">OPR_ThreadRudeAbortInNonCriticalRegion</span></span><br /><br /> <span data-ttu-id="55a2d-144">OPR_ThreadRudeAbortInCriticalRegion</span><span class="sxs-lookup"><span data-stu-id="55a2d-144">OPR_ThreadRudeAbortInCriticalRegion</span></span>|<span data-ttu-id="55a2d-145">-eRudeAbortThread</span><span class="sxs-lookup"><span data-stu-id="55a2d-145">-   eRudeAbortThread</span></span><br /><span data-ttu-id="55a2d-146">-eUnloadAppDomain</span><span class="sxs-lookup"><span data-stu-id="55a2d-146">-   eUnloadAppDomain</span></span><br /><span data-ttu-id="55a2d-147">-eRudeUnloadAppDomain</span><span class="sxs-lookup"><span data-stu-id="55a2d-147">-   eRudeUnloadAppDomain</span></span><br /><span data-ttu-id="55a2d-148">-eExitProcess</span><span class="sxs-lookup"><span data-stu-id="55a2d-148">-   eExitProcess</span></span><br /><span data-ttu-id="55a2d-149">-eFastExitProcess</span><span class="sxs-lookup"><span data-stu-id="55a2d-149">-   eFastExitProcess</span></span><br /><span data-ttu-id="55a2d-150">-eRudeExitProcess</span><span class="sxs-lookup"><span data-stu-id="55a2d-150">-   eRudeExitProcess</span></span><br /><span data-ttu-id="55a2d-151">-eDisableRuntime</span><span class="sxs-lookup"><span data-stu-id="55a2d-151">-   eDisableRuntime</span></span>|  
|<span data-ttu-id="55a2d-152">OPR_AppDomainUnload</span><span class="sxs-lookup"><span data-stu-id="55a2d-152">OPR_AppDomainUnload</span></span>|<span data-ttu-id="55a2d-153">-eUnloadAppDomain</span><span class="sxs-lookup"><span data-stu-id="55a2d-153">-   eUnloadAppDomain</span></span><br /><span data-ttu-id="55a2d-154">-eRudeUnloadAppDomain</span><span class="sxs-lookup"><span data-stu-id="55a2d-154">-   eRudeUnloadAppDomain</span></span><br /><span data-ttu-id="55a2d-155">-eExitProcess</span><span class="sxs-lookup"><span data-stu-id="55a2d-155">-   eExitProcess</span></span><br /><span data-ttu-id="55a2d-156">-eFastExitProcess</span><span class="sxs-lookup"><span data-stu-id="55a2d-156">-   eFastExitProcess</span></span><br /><span data-ttu-id="55a2d-157">-eRudeExitProcess</span><span class="sxs-lookup"><span data-stu-id="55a2d-157">-   eRudeExitProcess</span></span><br /><span data-ttu-id="55a2d-158">-eDisableRuntime</span><span class="sxs-lookup"><span data-stu-id="55a2d-158">-   eDisableRuntime</span></span>|  
|<span data-ttu-id="55a2d-159">OPR_AppDomainRudeUnload</span><span class="sxs-lookup"><span data-stu-id="55a2d-159">OPR_AppDomainRudeUnload</span></span>|<span data-ttu-id="55a2d-160">-eRudeUnloadAppDomain</span><span class="sxs-lookup"><span data-stu-id="55a2d-160">-   eRudeUnloadAppDomain</span></span><br /><span data-ttu-id="55a2d-161">-eExitProcess</span><span class="sxs-lookup"><span data-stu-id="55a2d-161">-   eExitProcess</span></span><br /><span data-ttu-id="55a2d-162">-eFastExitProcess</span><span class="sxs-lookup"><span data-stu-id="55a2d-162">-   eFastExitProcess</span></span><br /><span data-ttu-id="55a2d-163">-eRudeExitProcess</span><span class="sxs-lookup"><span data-stu-id="55a2d-163">-   eRudeExitProcess</span></span><br /><span data-ttu-id="55a2d-164">-eDisableRuntime</span><span class="sxs-lookup"><span data-stu-id="55a2d-164">-   eDisableRuntime</span></span>|  
|<span data-ttu-id="55a2d-165">OPR_ProcessExit</span><span class="sxs-lookup"><span data-stu-id="55a2d-165">OPR_ProcessExit</span></span>|<span data-ttu-id="55a2d-166">-eExitProcess</span><span class="sxs-lookup"><span data-stu-id="55a2d-166">-   eExitProcess</span></span><br /><span data-ttu-id="55a2d-167">-eFastExitProcess</span><span class="sxs-lookup"><span data-stu-id="55a2d-167">-   eFastExitProcess</span></span><br /><span data-ttu-id="55a2d-168">-eRudeExitProcess</span><span class="sxs-lookup"><span data-stu-id="55a2d-168">-   eRudeExitProcess</span></span><br /><span data-ttu-id="55a2d-169">-eDisableRuntime</span><span class="sxs-lookup"><span data-stu-id="55a2d-169">-   eDisableRuntime</span></span>|  
|<span data-ttu-id="55a2d-170">OPR_FinalizerRun</span><span class="sxs-lookup"><span data-stu-id="55a2d-170">OPR_FinalizerRun</span></span>|<span data-ttu-id="55a2d-171">-eNoAction</span><span class="sxs-lookup"><span data-stu-id="55a2d-171">-   eNoAction</span></span><br /><span data-ttu-id="55a2d-172">-eAbortThread</span><span class="sxs-lookup"><span data-stu-id="55a2d-172">-   eAbortThread</span></span><br /><span data-ttu-id="55a2d-173">-eRudeAbortThread</span><span class="sxs-lookup"><span data-stu-id="55a2d-173">-   eRudeAbortThread</span></span><br /><span data-ttu-id="55a2d-174">-eUnloadAppDomain</span><span class="sxs-lookup"><span data-stu-id="55a2d-174">-   eUnloadAppDomain</span></span><br /><span data-ttu-id="55a2d-175">-eRudeUnloadAppDomain</span><span class="sxs-lookup"><span data-stu-id="55a2d-175">-   eRudeUnloadAppDomain</span></span><br /><span data-ttu-id="55a2d-176">-eExitProcess</span><span class="sxs-lookup"><span data-stu-id="55a2d-176">-   eExitProcess</span></span><br /><span data-ttu-id="55a2d-177">-eFastExitProcess</span><span class="sxs-lookup"><span data-stu-id="55a2d-177">-   eFastExitProcess</span></span><br /><span data-ttu-id="55a2d-178">-eRudeExitProcess</span><span class="sxs-lookup"><span data-stu-id="55a2d-178">-   eRudeExitProcess</span></span><br /><span data-ttu-id="55a2d-179">-eDisableRuntime</span><span class="sxs-lookup"><span data-stu-id="55a2d-179">-   eDisableRuntime</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="55a2d-180">요구 사항</span><span class="sxs-lookup"><span data-stu-id="55a2d-180">Requirements</span></span>  
 <span data-ttu-id="55a2d-181">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="55a2d-181">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="55a2d-182">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="55a2d-182">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="55a2d-183">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="55a2d-183">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="55a2d-184">**.NET framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="55a2d-184">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="55a2d-185">참고 항목</span><span class="sxs-lookup"><span data-stu-id="55a2d-185">See Also</span></span>  
 [<span data-ttu-id="55a2d-186">EClrOperation 열거형</span><span class="sxs-lookup"><span data-stu-id="55a2d-186">EClrOperation Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md)  
 [<span data-ttu-id="55a2d-187">EPolicyAction 열거형</span><span class="sxs-lookup"><span data-stu-id="55a2d-187">EPolicyAction Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md)  
 [<span data-ttu-id="55a2d-188">ICLRPolicyManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="55a2d-188">ICLRPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-interface.md)
