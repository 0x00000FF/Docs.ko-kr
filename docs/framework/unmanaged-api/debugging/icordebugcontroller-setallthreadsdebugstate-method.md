---
title: ICorDebugController::SetAllThreadsDebugState 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugController.SetAllThreadsDebugState
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugController::SetAllThreadsDebugState
helpviewer_keywords:
- SetAllThreadsDebugState method [.NET Framework debugging]
- ICorDebugController::SetAllThreadsDebugState method [.NET Framework debugging]
ms.assetid: bdda4bd7-4743-4d58-a22b-8067e967db95
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a8d14deae1923e2904818fc01ffa3665fdf5ea6c
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54710575"
---
# <a name="icordebugcontrollersetallthreadsdebugstate-method"></a><span data-ttu-id="dfb81-102">ICorDebugController::SetAllThreadsDebugState 메서드</span><span class="sxs-lookup"><span data-stu-id="dfb81-102">ICorDebugController::SetAllThreadsDebugState Method</span></span>
<span data-ttu-id="dfb81-103">프로세스의 모든 관리 되는 스레드의 디버그 상태를 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="dfb81-103">Sets the debug state of all managed threads in the process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dfb81-104">구문</span><span class="sxs-lookup"><span data-stu-id="dfb81-104">Syntax</span></span>  
  
```  
HRESULT SetAllThreadsDebugState (  
    [in] CorDebugThreadState  state,  
    [in] ICorDebugThread      *pExceptThisThread  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="dfb81-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="dfb81-105">Parameters</span></span>  
 `state`  
 <span data-ttu-id="dfb81-106">[in] 디버깅을 위한 스레드 상태를 지정 하는 "CorDebugThreadState" 열거형의 값입니다.</span><span class="sxs-lookup"><span data-stu-id="dfb81-106">[in] A value of the "CorDebugThreadState" enumeration that specifies the state of the thread for debugging.</span></span>  
  
 `pExceptThisThread`  
 <span data-ttu-id="dfb81-107">[in] 디버그 상태 설정에서 제외 해야 하는 스레드를 나타내는 "ICorDebugThread" 개체에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="dfb81-107">[in] A pointer to an "ICorDebugThread" object that represents a thread to be exempted from the debug state setting.</span></span> <span data-ttu-id="dfb81-108">이 값이 null 인 경우에 스레드가 없습니다 제외 됩니다.</span><span class="sxs-lookup"><span data-stu-id="dfb81-108">If this value is null, no thread is exempted.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="dfb81-109">설명</span><span class="sxs-lookup"><span data-stu-id="dfb81-109">Remarks</span></span>  
 <span data-ttu-id="dfb81-110">`SetAllThreadsDebugState` 메서드를 통해 표시 되지 않는 스레드 영향을 줄 수 [EnumerateThreads 메서드](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-enumeratethreads-method.md)를 사용 하 여 일시 중단 된 하므로 스레드는 `SetAllThreadsDebugState` 메서드를 사용 하 여 다시 시작 해야 할를 `SetAllThreadsDebugState` 메서드.</span><span class="sxs-lookup"><span data-stu-id="dfb81-110">The `SetAllThreadsDebugState` method may affect threads that are not visible via [EnumerateThreads Method](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-enumeratethreads-method.md), so threads that were suspended with the `SetAllThreadsDebugState` method will need to be resumed with the `SetAllThreadsDebugState` method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="dfb81-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="dfb81-111">Requirements</span></span>  
 <span data-ttu-id="dfb81-112">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="dfb81-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="dfb81-113">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="dfb81-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="dfb81-114">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="dfb81-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="dfb81-115">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="dfb81-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dfb81-116">참고자료</span><span class="sxs-lookup"><span data-stu-id="dfb81-116">See also</span></span>

