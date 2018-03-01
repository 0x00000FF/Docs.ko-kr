---
title: "ICorDebugManagedCallback2::MDANotification 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- ICorDebugManagedCallback2.MDANotification
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback2::MDANotification
helpviewer_keywords:
- MDANotification method [.NET Framework debugging]
- ICorDebugManagedCallback2::MDANotification method [.NET Framework debugging]
ms.assetid: 93f79627-bd31-4f4f-b95d-46a032a52fe4
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 5a58e286feb3387557d0a37c463f2af67abf8cc5
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugmanagedcallback2mdanotification-method"></a><span data-ttu-id="fb0bd-102">ICorDebugManagedCallback2::MDANotification 메서드</span><span class="sxs-lookup"><span data-stu-id="fb0bd-102">ICorDebugManagedCallback2::MDANotification Method</span></span>
<span data-ttu-id="fb0bd-103">코드 실행에 디버깅 중인 응용 프로그램 관리 디버깅 도우미 (MDA)를 발생 하는 알림을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="fb0bd-103">Provides notification that code execution has encountered a managed debugging assistant (MDA) in the application that is being debugged.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fb0bd-104">구문</span><span class="sxs-lookup"><span data-stu-id="fb0bd-104">Syntax</span></span>  
  
```  
HRESULT MDANotification(  
    [in] ICorDebugController  *pController,  
    [in] ICorDebugThread      *pThread,  
    [in] ICorDebugMDA         *pMDA  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="fb0bd-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="fb0bd-105">Parameters</span></span>  
 `pController`  
 <span data-ttu-id="fb0bd-106">[in] ICorDebugController 인터페이스를 노출 하는 프로세스 또는 MDA 발생 한 응용 프로그램 도메인에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="fb0bd-106">[in] A pointer to an ICorDebugController interface that exposes the process or application domain in which the MDA occurred.</span></span>  
  
 <span data-ttu-id="fb0bd-107">디버거는 인터페이스는 부분은 항상 쿼리할 수 있지만 컨트롤러는 프로세스 또는 응용 프로그램 도메인 인지에 대 한 가정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fb0bd-107">A debugger should not make any assumptions about whether the controller is a process or an application domain, although it can always query the interface to make a determination.</span></span>  
  
 `pThread`  
 <span data-ttu-id="fb0bd-108">[in] 디버그 이벤트가 발생 한 관리 되는 스레드를 노출 하는 ICorDebugThread 인터페이스에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="fb0bd-108">[in] A pointer to an ICorDebugThread interface that exposes the managed thread on which the debug event occurred.</span></span>  
  
 <span data-ttu-id="fb0bd-109">MDA는 관리 되지 않는에서 발생 한 경우 스레드가, 값 `pThread` null이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fb0bd-109">If the MDA occurred on an unmanaged thread, the value of `pThread` will be null.</span></span>  
  
 <span data-ttu-id="fb0bd-110">MDA 개체 자체에서 운영 체제 (OS) 스레드 ID를 가져와야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fb0bd-110">You must get the operating system (OS) thread ID from the MDA object itself.</span></span>  
  
 `pMDA`  
 <span data-ttu-id="fb0bd-111">[in] 에 대 한 포인터는 [ICorDebugMDA](../../../../docs/framework/unmanaged-api/debugging/icordebugmda-interface.md) MDA 정보를 제공 하는 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="fb0bd-111">[in] A pointer to an [ICorDebugMDA](../../../../docs/framework/unmanaged-api/debugging/icordebugmda-interface.md) interface that exposes the MDA information.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="fb0bd-112">설명</span><span class="sxs-lookup"><span data-stu-id="fb0bd-112">Remarks</span></span>  
 <span data-ttu-id="fb0bd-113">MDA는 추론 경고 및 호출을 제외한 모든 명시적 디버거 작업이 필요 하지 않은 [icordebugcontroller:: Continue](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-continue-method.md) 디버깅 중인 응용 프로그램의 실행을 다시 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="fb0bd-113">An MDA is a heuristic warning and does not require any explicit debugger action except for calling [ICorDebugController::Continue](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-continue-method.md) to resume execution of the application that is being debugged.</span></span>  
  
 <span data-ttu-id="fb0bd-114">공용 언어 런타임 (CLR) 된 mda 및 데이터에 언제 든 지 특정된 MDA를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fb0bd-114">The common language runtime (CLR) can determine which MDAs are fired and which data is in any given MDA at any point.</span></span> <span data-ttu-id="fb0bd-115">따라서, 디버거 특정 MDA 패턴이 필요한 기능을 빌드하면 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fb0bd-115">Therefore, debuggers should not build any functionality requiring specific MDA patterns.</span></span>  
  
 <span data-ttu-id="fb0bd-116">Mda 큐에 대기 하 고 MDA 발생 직후 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fb0bd-116">MDAs may be queued and fired shortly after the MDA is encountered.</span></span> <span data-ttu-id="fb0bd-117">런타임은 MDA를 발견할 때 MDA를 실행 하는 대신 실행에 대 한 안전 지점에 도달할 때까지 대기 해야 하는 경우 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fb0bd-117">This could happen if the runtime needs to wait until it reaches a safe point for firing the MDA, instead of firing the MDA when it encounters it.</span></span> <span data-ttu-id="fb0bd-118">또한 런타임에서 단일 큐에 대기 중인된 콜백 ("연결" 이벤트 작업와 유사) 집합이 Mda의 숫자를 발생 시킬 수를 의미 합니다.</span><span class="sxs-lookup"><span data-stu-id="fb0bd-118">It also means that the runtime may fire a number of MDAs in a single set of queued callbacks (similar to an "attach" event operation).</span></span>  
  
 <span data-ttu-id="fb0bd-119">디버거는에 대 한 참조를 해제 해야는 `ICorDebugMDA` 에서 반환 된 후 즉시 인스턴스는 `MDANotification` 콜백 CLR MDA가 사용 된 메모리에 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="fb0bd-119">A debugger should release the reference to an `ICorDebugMDA` instance immediately after returning from the `MDANotification` callback, to allow the CLR to recycle the memory consumed by an MDA.</span></span> <span data-ttu-id="fb0bd-120">인스턴스를 해제 하면 여러 개의 Mda가 실행 하는 경우 성능이 향상 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fb0bd-120">Releasing the instance may improve performance if many MDAs are firing.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fb0bd-121">요구 사항</span><span class="sxs-lookup"><span data-stu-id="fb0bd-121">Requirements</span></span>  
 <span data-ttu-id="fb0bd-122">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="fb0bd-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fb0bd-123">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="fb0bd-123">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="fb0bd-124">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="fb0bd-124">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="fb0bd-125">**.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fb0bd-125">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fb0bd-126">참고 항목</span><span class="sxs-lookup"><span data-stu-id="fb0bd-126">See Also</span></span>  
 [<span data-ttu-id="fb0bd-127">관리 디버깅 도우미를 사용하여 오류 진단</span><span class="sxs-lookup"><span data-stu-id="fb0bd-127">Diagnosing Errors with Managed Debugging Assistants</span></span>](../../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)  
 [<span data-ttu-id="fb0bd-128">ICorDebugManagedCallback2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="fb0bd-128">ICorDebugManagedCallback2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-interface.md)  
 [<span data-ttu-id="fb0bd-129">ICorDebugManagedCallback 인터페이스</span><span class="sxs-lookup"><span data-stu-id="fb0bd-129">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
