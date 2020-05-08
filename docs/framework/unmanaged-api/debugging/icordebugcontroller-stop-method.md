---
title: ICorDebugController::Stop 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugController.Stop
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugController::Stop
helpviewer_keywords:
- Stop method, ICorDebugController interface [.NET Framework debugging]
- ICorDebugController::Stop method [.NET Framework debugging]
ms.assetid: c34e79be-a7fb-479e-8dec-d126a4c330e5
topic_type:
- apiref
ms.openlocfilehash: bb7eee0997a6c8671693accf2c95e6e06e0a4f2e
ms.sourcegitcommit: fff146ba3fd1762c8c432d95c8b877825ae536fc
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/08/2020
ms.locfileid: "82976579"
---
# <a name="icordebugcontrollerstop-method"></a><span data-ttu-id="f18b4-102">ICorDebugController::Stop 메서드</span><span class="sxs-lookup"><span data-stu-id="f18b4-102">ICorDebugController::Stop Method</span></span>
<span data-ttu-id="f18b4-103">프로세스에서 관리 코드를 실행 하는 모든 스레드에서 협조적 중지를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="f18b4-103">Performs a cooperative stop on all threads that are running managed code in the process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f18b4-104">구문</span><span class="sxs-lookup"><span data-stu-id="f18b4-104">Syntax</span></span>  
  
```cpp  
HRESULT Stop (  
    [in] DWORD dwTimeoutIgnored  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f18b4-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="f18b4-105">Parameters</span></span>  
 `dwTimeoutIgnored`  
 <span data-ttu-id="f18b4-106">사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f18b4-106">Not used.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f18b4-107">설명</span><span class="sxs-lookup"><span data-stu-id="f18b4-107">Remarks</span></span>  
 <span data-ttu-id="f18b4-108">`Stop`프로세스에서 관리 코드를 실행 하는 모든 스레드에서 협조적 중지를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="f18b4-108">`Stop` performs a cooperative stop on all threads running managed code in the process.</span></span> <span data-ttu-id="f18b4-109">관리 전용 디버깅 세션 중에는 관리 되지 않는 스레드가 계속 실행 될 수 있지만 관리 코드를 호출 하려고 하면 차단 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f18b4-109">During a managed-only debugging session, unmanaged threads may continue to run (but will be blocked when trying to call managed code).</span></span> <span data-ttu-id="f18b4-110">Interop 디버깅 세션 중에는 관리 되지 않는 스레드도 중지 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f18b4-110">During an interop debugging session, unmanaged threads will also be stopped.</span></span> <span data-ttu-id="f18b4-111">값 `dwTimeoutIgnored` 은 현재 무시 되 고 무한 (-1)으로 처리 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f18b4-111">The `dwTimeoutIgnored` value is currently ignored and treated as INFINITE (-1).</span></span> <span data-ttu-id="f18b4-112">교착 상태가 발생 하 여 협조적 중지가 실패 하면 모든 스레드가 일시 중단 되 고 E_TIMEOUT 반환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f18b4-112">If the cooperative stop fails due to a deadlock, all threads are suspended and E_TIMEOUT is returned.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="f18b4-113">`Stop`는 디버깅 API의 유일한 동기 메서드입니다.</span><span class="sxs-lookup"><span data-stu-id="f18b4-113">`Stop` is the only synchronous method in the debugging API.</span></span> <span data-ttu-id="f18b4-114">에서 `Stop` S_OK를 반환할 때 프로세스가 중지 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f18b4-114">When `Stop` returns S_OK, the process is stopped.</span></span> <span data-ttu-id="f18b4-115">수신기에 중지를 알리기 위한 콜백이 제공 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f18b4-115">No callback is given to notify listeners of the stop.</span></span> <span data-ttu-id="f18b4-116">디버거는 [ICorDebugController:: Continue](icordebugcontroller-continue-method.md) 를 호출 하 여 프로세스를 다시 시작할 수 있도록 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f18b4-116">The debugger must call [ICorDebugController::Continue](icordebugcontroller-continue-method.md) to allow the process to resume.</span></span>  
  
 <span data-ttu-id="f18b4-117">디버거는 중지 카운터를 유지 관리 합니다.</span><span class="sxs-lookup"><span data-stu-id="f18b4-117">The debugger maintains a stop counter.</span></span> <span data-ttu-id="f18b4-118">카운터가 0으로 이동 하면 컨트롤러가 다시 시작 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f18b4-118">When the counter goes to zero, the controller is resumed.</span></span> <span data-ttu-id="f18b4-119">또는 디스패치 된 `Stop` 각 콜백에 대 한 각 호출은 카운터를 증가 시킵니다.</span><span class="sxs-lookup"><span data-stu-id="f18b4-119">Each call to `Stop` or each dispatched callback increments the counter.</span></span> <span data-ttu-id="f18b4-120">를 `ICorDebugController::Continue` 호출할 때마다 카운터가 감소 합니다.</span><span class="sxs-lookup"><span data-stu-id="f18b4-120">Each call to `ICorDebugController::Continue` decrements the counter.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f18b4-121">요구 사항</span><span class="sxs-lookup"><span data-stu-id="f18b4-121">Requirements</span></span>  
 <span data-ttu-id="f18b4-122">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f18b4-122">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f18b4-123">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f18b4-123">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f18b4-124">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f18b4-124">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f18b4-125">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f18b4-125">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f18b4-126">참고 항목</span><span class="sxs-lookup"><span data-stu-id="f18b4-126">See also</span></span>
