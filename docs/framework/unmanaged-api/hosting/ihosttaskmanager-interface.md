---
title: "IHostTaskManager 인터페이스"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IHostTaskManager
api_location: mscoree.dll
api_type: COM
f1_keywords: IHostTaskManager
helpviewer_keywords: IHostTaskManager interface [.NET Framework hosting]
ms.assetid: 4a0b05b9-3ef1-4607-b7c8-bd4dd43647a0
topic_type: apiref
caps.latest.revision: "18"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 7a5086f3349b3756e507855a87bd724d2618212f
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="ihosttaskmanager-interface"></a><span data-ttu-id="ca1c3-102">IHostTaskManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="ca1c3-102">IHostTaskManager Interface</span></span>
<span data-ttu-id="ca1c3-103">공용 언어 런타임 (CLR)에서 표준 운영 체제 스레드 또는 파이버 함수를 사용 하는 대신 호스트를 통해 작업을 사용할 수 있는 메서드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="ca1c3-103">Provides methods that allow the common language runtime (CLR) to work with tasks through the host instead of using the standard operating system threading or fiber functions.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="ca1c3-104">메서드</span><span class="sxs-lookup"><span data-stu-id="ca1c3-104">Methods</span></span>  
  
|<span data-ttu-id="ca1c3-105">메서드</span><span class="sxs-lookup"><span data-stu-id="ca1c3-105">Method</span></span>|<span data-ttu-id="ca1c3-106">설명</span><span class="sxs-lookup"><span data-stu-id="ca1c3-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="ca1c3-107">BeginDelayAbort 메서드</span><span class="sxs-lookup"><span data-stu-id="ca1c3-107">BeginDelayAbort Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-begindelayabort-method.md)|<span data-ttu-id="ca1c3-108">호스트 관리 코드에는 현재 작업 중단할 수 없는 기간이 시작 됨을 알립니다.</span><span class="sxs-lookup"><span data-stu-id="ca1c3-108">Notifies the host that managed code is entering a period in which the current task must not be aborted.</span></span>|  
|[<span data-ttu-id="ca1c3-109">BeginThreadAffinity 메서드</span><span class="sxs-lookup"><span data-stu-id="ca1c3-109">BeginThreadAffinity Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-beginthreadaffinity-method.md)|<span data-ttu-id="ca1c3-110">현재 작업 이동 하지 말아야 다른 운영 체제 스레드에 마침표를 시작 하는 코드를 관리 하는 호스트에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="ca1c3-110">Notifies the host that managed code is entering a period in which the current task must not be moved to another operating system thread.</span></span>|  
|[<span data-ttu-id="ca1c3-111">CallNeedsHostHook 메서드</span><span class="sxs-lookup"><span data-stu-id="ca1c3-111">CallNeedsHostHook Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-callneedshosthook-method.md)|<span data-ttu-id="ca1c3-112">호스트를에서 공용 언어 런타임에서 관리 되지 않는 함수에 지정된 된 호출을 인라인 할 수 있는지 여부를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ca1c3-112">Enables the host to specify whether the common language runtime can inline the specified call to an unmanaged function.</span></span>|  
|[<span data-ttu-id="ca1c3-113">CreateTask 메서드</span><span class="sxs-lookup"><span data-stu-id="ca1c3-113">CreateTask Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-createtask-method.md)|<span data-ttu-id="ca1c3-114">호스트에서 새 작업을 만들도록 요청 합니다.</span><span class="sxs-lookup"><span data-stu-id="ca1c3-114">Requests that the host create a new task.</span></span>|  
|[<span data-ttu-id="ca1c3-115">EndDelayAbort 메서드</span><span class="sxs-lookup"><span data-stu-id="ca1c3-115">EndDelayAbort Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-enddelayabort-method.md)|<span data-ttu-id="ca1c3-116">관리 코드는 호스트를 종료 하 고 없는 현재 작업을 중단 하지 말아야, 기간을 호출한 후에 알립니다. `BeginDelayAbort`합니다.</span><span class="sxs-lookup"><span data-stu-id="ca1c3-116">Notifies the host that managed code is exiting the period in which the current task must not be aborted, following an earlier call to `BeginDelayAbort`.</span></span>|  
|[<span data-ttu-id="ca1c3-117">EndThreadAffinity 메서드</span><span class="sxs-lookup"><span data-stu-id="ca1c3-117">EndThreadAffinity Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-endthreadaffinity-method.md)|<span data-ttu-id="ca1c3-118">관리 코드는 호스트를 종료 하 고 없는 현재 작업 이동 하지 말아야 다른 운영 체제 스레드에 기간을 호출한 후에 알립니다. `BeginThreadAffinity`합니다.</span><span class="sxs-lookup"><span data-stu-id="ca1c3-118">Notifies the host that managed code is exiting the period in which the current task must not be moved to another operating system thread, following an earlier call to `BeginThreadAffinity`.</span></span>|  
|[<span data-ttu-id="ca1c3-119">EnterRuntime 메서드</span><span class="sxs-lookup"><span data-stu-id="ca1c3-119">EnterRuntime Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-enterruntime-method.md)|<span data-ttu-id="ca1c3-120">관리 되지 않는 메서드를 호출 하는 플랫폼 호출 메서드를 같은 반환 되는지 실행 제어 CLR을 호스트에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="ca1c3-120">Notifies the host that a call to an unmanaged method, such as a platform invoke method, is returning execution control to the CLR.</span></span>|  
|[<span data-ttu-id="ca1c3-121">GetCurrentTask 메서드</span><span class="sxs-lookup"><span data-stu-id="ca1c3-121">GetCurrentTask Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-getcurrenttask-method.md)|<span data-ttu-id="ca1c3-122">이 호출이 수행 된 운영 체제 스레드에 대해 현재 실행 중인 작업에 대 한 인터페이스 포인터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="ca1c3-122">Gets an interface pointer to the task that is currently executing on the operating system thread from which this call is made.</span></span>|  
|[<span data-ttu-id="ca1c3-123">GetStackGuarantee 메서드</span><span class="sxs-lookup"><span data-stu-id="ca1c3-123">GetStackGuarantee Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-getstackguarantee-method.md)|<span data-ttu-id="ca1c3-124">스택 공간이 스택 작업이 완료 된 후 사용 가능 하도록 보장 하지만 프로세스의 닫기 전에 크기를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="ca1c3-124">Gets the amount of stack space that is guaranteed to be available after a stack operation completes, but before the closing of a process.</span></span>|  
|[<span data-ttu-id="ca1c3-125">LeaveRuntime 메서드</span><span class="sxs-lookup"><span data-stu-id="ca1c3-125">LeaveRuntime Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-leaveruntime-method.md)|<span data-ttu-id="ca1c3-126">관리 코드는 호스트를 관리 되지 않는 함수를 호출 하려고에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="ca1c3-126">Notifies the host that managed code is about to make a call to an unmanaged function.</span></span>|  
|[<span data-ttu-id="ca1c3-127">ReverseEnterRuntime 메서드</span><span class="sxs-lookup"><span data-stu-id="ca1c3-127">ReverseEnterRuntime Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-reverseenterruntime-method.md)|<span data-ttu-id="ca1c3-128">비관리 코드에서 공용 언어 런타임 (CLR)로 호출이 수행 되는 호스트에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="ca1c3-128">Notifies the host that a call is being made into the common language runtime (CLR) from unmanaged code.</span></span>|  
|[<span data-ttu-id="ca1c3-129">ReverseLeaveRuntime 메서드</span><span class="sxs-lookup"><span data-stu-id="ca1c3-129">ReverseLeaveRuntime Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-reverseleaveruntime-method.md)|<span data-ttu-id="ca1c3-130">제어를 차례로 호출 된 관리 코드에서 관리 되지 않는 함수는 clr에서 호스트에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="ca1c3-130">Notifies the host that control is leaving the CLR and entering an unmanaged function that was, in turn, called from managed code.</span></span>|  
|[<span data-ttu-id="ca1c3-131">SetCLRTaskManager 메서드</span><span class="sxs-lookup"><span data-stu-id="ca1c3-131">SetCLRTaskManager Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-setclrtaskmanager-method.md)|<span data-ttu-id="ca1c3-132">호스트에 대 한 인터페이스 포인터에 제공 된 [ICLRTaskManager](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md) 인스턴스는 CLR에서 구현 합니다.</span><span class="sxs-lookup"><span data-stu-id="ca1c3-132">Provides the host with an interface pointer to an [ICLRTaskManager](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md) instance implemented by the CLR.</span></span>|  
|[<span data-ttu-id="ca1c3-133">SetLocale 메서드</span><span class="sxs-lookup"><span data-stu-id="ca1c3-133">SetLocale Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-setlocale-method.md)|<span data-ttu-id="ca1c3-134">CLR이는 현재 작업에서 로캘을 변경 되었음을 호스트에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="ca1c3-134">Notifies the host that the CLR has changed the locale on the current task.</span></span>|  
|[<span data-ttu-id="ca1c3-135">SetStackGuarantee 메서드</span><span class="sxs-lookup"><span data-stu-id="ca1c3-135">SetStackGuarantee Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-setstackguarantee-method.md)|<span data-ttu-id="ca1c3-136">내부용으로 예약되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ca1c3-136">Reserved for internal use only.</span></span>|  
|[<span data-ttu-id="ca1c3-137">SetUILocale 메서드</span><span class="sxs-lookup"><span data-stu-id="ca1c3-137">SetUILocale Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-setuilocale-method.md)|<span data-ttu-id="ca1c3-138">현재 작업에서 사용자 인터페이스 로캘이 변경 되었음을 호스트에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="ca1c3-138">Notifies the host that the user interface locale has been changed on the current task.</span></span>|  
|[<span data-ttu-id="ca1c3-139">Sleep 메서드</span><span class="sxs-lookup"><span data-stu-id="ca1c3-139">Sleep Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-sleep-method.md)|<span data-ttu-id="ca1c3-140">현재 작업 절전 모드로 전환 됨 호스트에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="ca1c3-140">Notifies the host that the current task is going to sleep.</span></span>|  
|[<span data-ttu-id="ca1c3-141">SwitchToTask 메서드</span><span class="sxs-lookup"><span data-stu-id="ca1c3-141">SwitchToTask Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-switchtotask-method.md)|<span data-ttu-id="ca1c3-142">현재 작업에서 전환 해야 함을 호스트에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="ca1c3-142">Notifies the host that it should switch out the current task.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ca1c3-143">설명</span><span class="sxs-lookup"><span data-stu-id="ca1c3-143">Remarks</span></span>  
 <span data-ttu-id="ca1c3-144">`IHostTaskManager`CLR을 만들고 작업을 관리할 수 있습니다 후크 제어가에서 비관리 코드로 마샬링하거나 그 반대로 하는 경우 작업을 수행 하 고 특정 동작을 지정 하는 호스트를 제공 하는 호스트 수 및 코드 실행 하는 동안 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ca1c3-144">`IHostTaskManager` allows the CLR to create and manage tasks, to provide hooks for the host to take action when control transfers from managed to unmanaged code and vice versa, and to specify certain actions the host can and cannot take during code execution.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ca1c3-145">요구 사항</span><span class="sxs-lookup"><span data-stu-id="ca1c3-145">Requirements</span></span>  
 <span data-ttu-id="ca1c3-146">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="ca1c3-146">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ca1c3-147">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="ca1c3-147">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="ca1c3-148">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="ca1c3-148">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="ca1c3-149">**.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ca1c3-149">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ca1c3-150">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ca1c3-150">See Also</span></span>  
 [<span data-ttu-id="ca1c3-151">ICLRTask 인터페이스</span><span class="sxs-lookup"><span data-stu-id="ca1c3-151">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)  
 [<span data-ttu-id="ca1c3-152">ICLRTaskManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="ca1c3-152">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)  
 [<span data-ttu-id="ca1c3-153">IHostTask 인터페이스</span><span class="sxs-lookup"><span data-stu-id="ca1c3-153">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)  
 [<span data-ttu-id="ca1c3-154">호스팅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="ca1c3-154">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
