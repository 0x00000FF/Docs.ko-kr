---
title: ICorProfilerInfo::SetEnterLeaveFunctionHooks 메서드
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo.SetEnterLeaveFunctionHooks
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo::SetEnterLeaveFunctionHooks
helpviewer_keywords:
- SetEnterLeaveFunctionHooks method [.NET Framework profiling]
- ICorProfilerInfo::SetEnterLeaveFunctionHooks method [.NET Framework profiling]
ms.assetid: 72399636-c219-4ffd-8ac8-39432c9d4641
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 58e7b3e76d90e9e43f3f5259c52b52cd9f8e1f6e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33455077"
---
# <a name="icorprofilerinfosetenterleavefunctionhooks-method"></a><span data-ttu-id="42927-102">ICorProfilerInfo::SetEnterLeaveFunctionHooks 메서드</span><span class="sxs-lookup"><span data-stu-id="42927-102">ICorProfilerInfo::SetEnterLeaveFunctionHooks Method</span></span>
<span data-ttu-id="42927-103">"입력", "둡니다" 및 "tailcall" 관리 되는 함수의 후크에서 호출 되는 프로파일러 구현 함수를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="42927-103">Specifies profiler-implemented functions to be called on "enter", "leave", and "tailcall" hooks of managed functions.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="42927-104">구문</span><span class="sxs-lookup"><span data-stu-id="42927-104">Syntax</span></span>  
  
```  
HRESULT SetEnterLeaveFunctionHooks(  
    [in] FunctionEnter    *pFuncEnter,  
    [in] FunctionLeave    *pFuncLeave,  
    [in] FunctionTailcall *pFuncTailcall);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="42927-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="42927-105">Parameters</span></span>  
 `pFuncEnter`  
 <span data-ttu-id="42927-106">[in] 로 사용 하는 구현에 대 한 포인터는 [FunctionEnter](../../../../docs/framework/unmanaged-api/profiling/functionenter-function.md) 콜백 합니다.</span><span class="sxs-lookup"><span data-stu-id="42927-106">[in] A pointer to the implementation to be used as the [FunctionEnter](../../../../docs/framework/unmanaged-api/profiling/functionenter-function.md) callback.</span></span>  
  
 `pFuncLeave`  
 <span data-ttu-id="42927-107">[in] 로 사용 하는 구현에 대 한 포인터는 [FunctionLeave](../../../../docs/framework/unmanaged-api/profiling/functionleave-function.md) 콜백 합니다.</span><span class="sxs-lookup"><span data-stu-id="42927-107">[in] A pointer to the implementation to be used as the [FunctionLeave](../../../../docs/framework/unmanaged-api/profiling/functionleave-function.md) callback.</span></span>  
  
 `pFuncTailcall`  
 <span data-ttu-id="42927-108">[in] 로 사용 하는 구현에 대 한 포인터는 [FunctionTailcall](../../../../docs/framework/unmanaged-api/profiling/functiontailcall-function.md) 콜백 합니다.</span><span class="sxs-lookup"><span data-stu-id="42927-108">[in] A pointer to the implementation to be used as the [FunctionTailcall](../../../../docs/framework/unmanaged-api/profiling/functiontailcall-function.md) callback.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="42927-109">설명</span><span class="sxs-lookup"><span data-stu-id="42927-109">Remarks</span></span>  
 <span data-ttu-id="42927-110">.NET Framework 버전 1.0에서는 각 함수 포인터 해당 해당 콜백 사용 하지 않으려면 null 일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="42927-110">In the .NET Framework version 1.0, each function pointer can be null to disable that corresponding callback.</span></span>  
  
 <span data-ttu-id="42927-111">한 번에 하나의 집합만 콜백 활성화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="42927-111">Only one set of callbacks can be active at a time.</span></span> <span data-ttu-id="42927-112">따라서 프로파일러 둘 다를 호출 하는 경우 `SetEnterLeaveFunctionHooks` 및 [icorprofilerinfo2:: Setenterleavefunctionhooks2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-setenterleavefunctionhooks2-method.md), 다음 `SetEnterLeaveFunctionHooks2` 우선적으로 적용 합니다.</span><span class="sxs-lookup"><span data-stu-id="42927-112">Thus, if a profiler calls both `SetEnterLeaveFunctionHooks` and [ICorProfilerInfo2::SetEnterLeaveFunctionHooks2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-setenterleavefunctionhooks2-method.md), then `SetEnterLeaveFunctionHooks2` takes precedence.</span></span>  
  
 <span data-ttu-id="42927-113">`SetEnterLeaveFunctionHooks` 프로파일러의 에서만 메서드를 호출할 수 있습니다 [icorprofilercallback:: Initialize](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-initialize-method.md) 콜백 합니다.</span><span class="sxs-lookup"><span data-stu-id="42927-113">The `SetEnterLeaveFunctionHooks` method can be called only from the profiler's [ICorProfilerCallback::Initialize](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-initialize-method.md) callback.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="42927-114">요구 사항</span><span class="sxs-lookup"><span data-stu-id="42927-114">Requirements</span></span>  
 <span data-ttu-id="42927-115">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="42927-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="42927-116">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="42927-116">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="42927-117">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="42927-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="42927-118">**.NET framework 버전:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="42927-118">**.NET Framework Versions:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="42927-119">참고 항목</span><span class="sxs-lookup"><span data-stu-id="42927-119">See Also</span></span>  
 [<span data-ttu-id="42927-120">ICorProfilerInfo 인터페이스</span><span class="sxs-lookup"><span data-stu-id="42927-120">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
