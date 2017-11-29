---
title: "ICorProfilerCallback::ExceptionUnwindFinallyEnter 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerCallback.ExceptionUnwindFinallyEnter
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerCallback::ExceptionUnwindFinallyEnter
helpviewer_keywords:
- ICorProfilerCallback::ExceptionUnwindFinallyEnter method [.NET Framework profiling]
- ExceptionUnwindFinallyEnter method [.NET Framework profiling]
ms.assetid: c7fab986-b69f-4ec8-b7b7-91dcfc239cd0
topic_type: apiref
caps.latest.revision: "13"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: ec1b05e67a10f5e7b22a950d1dec24528b5c4914
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="icorprofilercallbackexceptionunwindfinallyenter-method"></a><span data-ttu-id="8100f-102">ICorProfilerCallback::ExceptionUnwindFinallyEnter 메서드</span><span class="sxs-lookup"><span data-stu-id="8100f-102">ICorProfilerCallback::ExceptionUnwindFinallyEnter Method</span></span>
<span data-ttu-id="8100f-103">해제 단계 예외 처리를 시작 하는 프로파일러에 알립니다는 `finally` 지정된 된 함수에 포함 된 절.</span><span class="sxs-lookup"><span data-stu-id="8100f-103">Notifies the profiler that the unwind phase of exception handling is entering a `finally` clause contained in the specified function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8100f-104">구문</span><span class="sxs-lookup"><span data-stu-id="8100f-104">Syntax</span></span>  
  
```  
HRESULT ExceptionUnwindFinallyEnter(  
    [in] FunctionID functionId);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="8100f-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="8100f-105">Parameters</span></span>  
 `functionId`  
 <span data-ttu-id="8100f-106">[in] 포함 된 함수 ID는 `finally` 절.</span><span class="sxs-lookup"><span data-stu-id="8100f-106">[in] The ID of the function that contains the `finally` clause.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8100f-107">설명</span><span class="sxs-lookup"><span data-stu-id="8100f-107">Remarks</span></span>  
 <span data-ttu-id="8100f-108">스택 가비지 수집을 허용 하는 상태가 아닐 수 있습니다 때문에이 메서드의 구현에서 프로파일러 차단 하지 않아야 하 고 따라서 선점형 가비지 수집을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="8100f-108">The profiler should not block in its implementation of this method because the stack may not be in a state that allows garbage collection, and therefore preemptive garbage collection cannot be enabled.</span></span> <span data-ttu-id="8100f-109">이때 프로파일러가 차단 하는 경우 가비지 수집을 시도 하 고, 런타임이이 콜백이 반환 될 때까지 차단 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8100f-109">If the profiler blocks here and garbage collection is attempted, the runtime will block until this callback returns.</span></span>  
  
 <span data-ttu-id="8100f-110">이 메서드는 프로파일러 구현에는 관리 코드에 또는 관리 되는 메모리 할당에서 호출 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8100f-110">The profiler's implementation of this method should not call into managed code or in any way cause a managed-memory allocation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8100f-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="8100f-111">Requirements</span></span>  
 <span data-ttu-id="8100f-112">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="8100f-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8100f-113">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="8100f-113">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="8100f-114">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8100f-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8100f-115">**.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8100f-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8100f-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="8100f-116">See Also</span></span>  
 [<span data-ttu-id="8100f-117">ICorProfilerCallback 인터페이스</span><span class="sxs-lookup"><span data-stu-id="8100f-117">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)  
 [<span data-ttu-id="8100f-118">GetNotifiedExceptionClauseInfo 메서드</span><span class="sxs-lookup"><span data-stu-id="8100f-118">GetNotifiedExceptionClauseInfo Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getnotifiedexceptionclauseinfo-method.md)  
 [<span data-ttu-id="8100f-119">ExceptionUnwindFinallyLeave 메서드</span><span class="sxs-lookup"><span data-stu-id="8100f-119">ExceptionUnwindFinallyLeave Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionunwindfinallyleave-method.md)
