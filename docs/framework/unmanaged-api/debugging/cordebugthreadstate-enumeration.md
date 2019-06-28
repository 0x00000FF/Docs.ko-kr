---
title: CorDebugThreadState 열거형
ms.date: 03/30/2017
api_name:
- CorDebugThreadState
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CorDebugThreadState
helpviewer_keywords:
- CorDebugThreadState enumeration [.NET Framework debugging]
ms.assetid: a3ccdf18-4ec6-494d-9024-48e5c8c724f5
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ba2ee070b7d03efc830058014aa445bb1a3d4329
ms.sourcegitcommit: 9b1ac36b6c80176fd4e20eb5bfcbd9d56c3264cf
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/28/2019
ms.locfileid: "67422257"
---
# <a name="cordebugthreadstate-enumeration"></a><span data-ttu-id="35e05-102">CorDebugThreadState 열거형</span><span class="sxs-lookup"><span data-stu-id="35e05-102">CorDebugThreadState Enumeration</span></span>
<span data-ttu-id="35e05-103">디버깅을 위한 스레드 상태를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="35e05-103">Specifies the state of a thread for debugging.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="35e05-104">구문</span><span class="sxs-lookup"><span data-stu-id="35e05-104">Syntax</span></span>  
  
```  
typedef enum CorDebugThreadState {  
    THREAD_RUN,  
    THREAD_SUSPEND  
} CorDebugThreadState;  
```  
  
## <a name="members"></a><span data-ttu-id="35e05-105">멤버</span><span class="sxs-lookup"><span data-stu-id="35e05-105">Members</span></span>  
  
|<span data-ttu-id="35e05-106">멤버</span><span class="sxs-lookup"><span data-stu-id="35e05-106">Member</span></span>|<span data-ttu-id="35e05-107">설명</span><span class="sxs-lookup"><span data-stu-id="35e05-107">Description</span></span>|  
|------------|-----------------|  
|`THREAD_RUN`|<span data-ttu-id="35e05-108">디버그 이벤트를 발생 하지 않는 한 스레드가 자유롭게를 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="35e05-108">The thread runs freely, unless a debug event occurs.</span></span>|  
|`THREAD_SUSPEND`|<span data-ttu-id="35e05-109">스레드를 실행할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="35e05-109">The thread cannot run.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="35e05-110">설명</span><span class="sxs-lookup"><span data-stu-id="35e05-110">Remarks</span></span>  
 <span data-ttu-id="35e05-111">디버거가 사용 하 여 `CorDebugThreadState` 스레드의 실행을 제어 하는 열거형입니다.</span><span class="sxs-lookup"><span data-stu-id="35e05-111">The debugger uses the `CorDebugThreadState` enumeration to control a thread's execution.</span></span> <span data-ttu-id="35e05-112">스레드의 상태를 사용 하 여 설정할 수는 [icordebugthread:: Setdebugstate](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-setdebugstate-method.md) 하거나 [icordebugcontroller:: Setallthreadsdebugstate](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-setallthreadsdebugstate-method.md) 메서드.</span><span class="sxs-lookup"><span data-stu-id="35e05-112">The state of a thread can be set by using the [ICorDebugThread::SetDebugState](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-setdebugstate-method.md) or [ICorDebugController::SetAllThreadsDebugState](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-setallthreadsdebugstate-method.md) method.</span></span>  
  
 <span data-ttu-id="35e05-113">에 제공 된 콜백을 합니다 [호스팅 API](../../../../docs/framework/unmanaged-api/hosting/index.md) 메시지 펌프를 수 있으므로 중단 된 상태가 필요 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="35e05-113">A callback provided to the [hosting API](../../../../docs/framework/unmanaged-api/hosting/index.md) enables message pumping, so an interrupted state is not needed.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="35e05-114">요구 사항</span><span class="sxs-lookup"><span data-stu-id="35e05-114">Requirements</span></span>  
 <span data-ttu-id="35e05-115">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="35e05-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="35e05-116">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="35e05-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="35e05-117">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="35e05-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="35e05-118">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="35e05-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="35e05-119">참고자료</span><span class="sxs-lookup"><span data-stu-id="35e05-119">See also</span></span>

- [<span data-ttu-id="35e05-120">디버깅 열거형</span><span class="sxs-lookup"><span data-stu-id="35e05-120">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
