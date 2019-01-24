---
title: ICorProfilerCallback::RuntimeSuspendFinished 메서드
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.RuntimeSuspendFinished
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::RuntimeSuspendFinished
helpviewer_keywords:
- ICorProfilerCallback::RuntimeSuspendFinished method [.NET Framework profiling]
- RuntimeSuspendFinished method [.NET Framework profiling]
ms.assetid: b7723f58-c55c-4399-9972-1bbf3b866694
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 6f69c39938384c7feca28ae40aba3e80a0ba28ed
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54706656"
---
# <a name="icorprofilercallbackruntimesuspendfinished-method"></a><span data-ttu-id="dc3c0-102">ICorProfilerCallback::RuntimeSuspendFinished 메서드</span><span class="sxs-lookup"><span data-stu-id="dc3c0-102">ICorProfilerCallback::RuntimeSuspendFinished Method</span></span>
<span data-ttu-id="dc3c0-103">런타임에 모든 런타임 스레드 일시 중단 완료 되었음을 프로파일러에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="dc3c0-103">Notifies the profiler that the runtime has completed suspension of all runtime threads.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dc3c0-104">구문</span><span class="sxs-lookup"><span data-stu-id="dc3c0-104">Syntax</span></span>  
  
```  
HRESULT RuntimeSuspendFinished();  
```  
  
## <a name="remarks"></a><span data-ttu-id="dc3c0-105">설명</span><span class="sxs-lookup"><span data-stu-id="dc3c0-105">Remarks</span></span>  
 <span data-ttu-id="dc3c0-106">비관리 코드에 있는 모든 런타임 스레드 런타임을 다시 입력 하려고 할 때까지 계속 실행 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dc3c0-106">All runtime threads that are in unmanaged code are allowed to continue running until they try to re-enter the runtime.</span></span> <span data-ttu-id="dc3c0-107">이때 이러한도 일시 중단 됩니다 런타임을 다시 시작 될 때까지.</span><span class="sxs-lookup"><span data-stu-id="dc3c0-107">At that point they will also be suspended until the runtime resumes.</span></span> <span data-ttu-id="dc3c0-108">이 런타임에 입력 하는 새 스레드에도 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="dc3c0-108">This also applies to new threads that enter the runtime.</span></span> <span data-ttu-id="dc3c0-109">런타임의 모든 스레드는 즉시 일시 중단 되거나 인터럽트 가능한 코드에 포함 되어 있습니다 하거나 중단할 코드에 도달할 때 일시 중단 하 라는 메시지가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="dc3c0-109">All threads in the runtime are either suspended immediately if they are already in interruptible code, or they are asked to suspend when they reach interruptible code.</span></span>  
  
 <span data-ttu-id="dc3c0-110">합니다 `RuntimeSuspendFinished` callback은 동일한 스레드에서 발생 합니다 [icorprofilercallback:: Runtimesuspendstarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimesuspendstarted-method.md) 콜백 합니다.</span><span class="sxs-lookup"><span data-stu-id="dc3c0-110">The `RuntimeSuspendFinished` callback is guaranteed to occur on the same thread as the [ICorProfilerCallback::RuntimeSuspendStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimesuspendstarted-method.md) callback.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="dc3c0-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="dc3c0-111">Requirements</span></span>  
 <span data-ttu-id="dc3c0-112">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="dc3c0-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="dc3c0-113">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="dc3c0-113">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="dc3c0-114">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="dc3c0-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="dc3c0-115">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="dc3c0-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dc3c0-116">참고자료</span><span class="sxs-lookup"><span data-stu-id="dc3c0-116">See also</span></span>
- [<span data-ttu-id="dc3c0-117">ICorProfilerCallback 인터페이스</span><span class="sxs-lookup"><span data-stu-id="dc3c0-117">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [<span data-ttu-id="dc3c0-118">RuntimeSuspendAborted 메서드</span><span class="sxs-lookup"><span data-stu-id="dc3c0-118">RuntimeSuspendAborted Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimesuspendaborted-method.md)
