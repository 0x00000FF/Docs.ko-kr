---
title: "ICorProfilerInfo4::EnumJITedFunctions2 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerInfo4.EnumJITedFunctions2
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerInfo4::EnumJITedFunctions2
helpviewer_keywords:
- EnumJITedFunctions2 method, ICorProfilerInfo4 interface [.NET Framework profiling]
- ICorProfilerInfo4::EnumJITedFunctions2 method [.NET Framework profiling]
ms.assetid: 40e9a1be-9bd2-4fad-9921-34a84b61c1e3
topic_type: apiref
caps.latest.revision: "8"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 9b9c8739a8ab47b4e24dba1b15c228d2800290d2
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="icorprofilerinfo4enumjitedfunctions2-method"></a><span data-ttu-id="3ce86-102">ICorProfilerInfo4::EnumJITedFunctions2 메서드</span><span class="sxs-lookup"><span data-stu-id="3ce86-102">ICorProfilerInfo4::EnumJITedFunctions2 Method</span></span>
<span data-ttu-id="3ce86-103">JIT 컴파일 및 JIT 다시 컴파일된 이전에 있던 모든 함수에 대 한 열거자를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="3ce86-103">Returns an enumerator for all functions that were previously JIT-compiled and JIT-recompiled.</span></span> <span data-ttu-id="3ce86-104">이 메서드를 대체는 [icorprofilerinfo3:: Enumjitedfunctions](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-enumjitedfunctions-method.md) 메서드 JIT 다시 컴파일된 Id를 열거 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3ce86-104">This method replaces the [ICorProfilerInfo3::EnumJITedFunctions](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-enumjitedfunctions-method.md) method, which does not enumerate JIT-recompiled IDs.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3ce86-105">구문</span><span class="sxs-lookup"><span data-stu-id="3ce86-105">Syntax</span></span>  
  
```  
HRESULT EnumJITedFunctions([out] ICorProfilerFunctionEnum** ppEnum);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="3ce86-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="3ce86-106">Parameters</span></span>  
 `ppEnum`  
 <span data-ttu-id="3ce86-107">[out] 에 대 한 포인터는 [ICorProfilerFunctionEnum](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctionenum-interface.md) 열거자입니다.</span><span class="sxs-lookup"><span data-stu-id="3ce86-107">[out] A pointer to the [ICorProfilerFunctionEnum](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctionenum-interface.md) enumerator.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3ce86-108">설명</span><span class="sxs-lookup"><span data-stu-id="3ce86-108">Remarks</span></span>  
 <span data-ttu-id="3ce86-109">이 메서드는와 겹칠 수 있습니다 `JITCompilation` 와 같은 콜백을 [icorprofilercallback:: Jitcompilationstarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitcompilationstarted-method.md) 메서드.</span><span class="sxs-lookup"><span data-stu-id="3ce86-109">This method may overlap with `JITCompilation` callbacks such as the [ICorProfilerCallback::JITCompilationStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitcompilationstarted-method.md) method.</span></span> <span data-ttu-id="3ce86-110">에 대 한 값을 포함 하는 반환 되는 열거형은 `COR_PRF_FUNCTION::reJitId` 필드입니다.</span><span class="sxs-lookup"><span data-stu-id="3ce86-110">The returned enumeration includes values for the `COR_PRF_FUNCTION::reJitId` field.</span></span> <span data-ttu-id="3ce86-111">[icorprofilerinfo3:: Enumjitedfunctions](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-enumjitedfunctions-method.md) 때문에이 메서드를 대체 하는 메서드가 JIT 다시 컴파일된 Id를 열거 하지 않습니다는 `COR_PRF_FUNCTION::reJitId` 필드는 항상 0으로 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3ce86-111">The [ICorProfilerInfo3::EnumJITedFunctions](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-enumjitedfunctions-method.md) method, which this method replaces, does not enumerate JIT-recompiled IDs, because the `COR_PRF_FUNCTION::reJitId` field is always set to 0.</span></span> <span data-ttu-id="3ce86-112">`ICorProfilerInfo4::EnumJITedFunctions` 메서드 했기 때문에 JIT 다시 컴파일된 Id를 열거할지 않습니다는 `COR_PRF_FUNCTION::reJitId` 필드가 올바르게 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3ce86-112">The `ICorProfilerInfo4::EnumJITedFunctions` method does enumerate JIT-recompiled IDs, because the `COR_PRF_FUNCTION::reJitId` field is set properly.</span></span> <span data-ttu-id="3ce86-113">[icorprofilerinfo4:: Enumjitedfunctions2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-enumjitedfunctions2-method.md) 메서드 반면 가비지 수집을 트리거할 수 [icorprofilerinfo3:: Enumjitedfunctions 메서드](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-enumjitedfunctions-method.md) 되지 것입니다.</span><span class="sxs-lookup"><span data-stu-id="3ce86-113">Note that the [ICorProfilerInfo4::EnumJITedFunctions2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-enumjitedfunctions2-method.md) method can trigger a garbage collection, whereas [ICorProfilerInfo3::EnumJITedFunctions method](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-enumjitedfunctions-method.md) will not.</span></span>  <span data-ttu-id="3ce86-114">자세한 내용은 참조 [CORPROF_E_UNSUPPORTED_CALL_SEQUENCE HRESULT](../../../../docs/framework/unmanaged-api/profiling/corprof-e-unsupported-call-sequence-hresult.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="3ce86-114">For more information, see [CORPROF_E_UNSUPPORTED_CALL_SEQUENCE HRESULT](../../../../docs/framework/unmanaged-api/profiling/corprof-e-unsupported-call-sequence-hresult.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3ce86-115">요구 사항</span><span class="sxs-lookup"><span data-stu-id="3ce86-115">Requirements</span></span>  
 <span data-ttu-id="3ce86-116">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="3ce86-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3ce86-117">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="3ce86-117">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="3ce86-118">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3ce86-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3ce86-119">**.NET framework 버전:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3ce86-119">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3ce86-120">참고 항목</span><span class="sxs-lookup"><span data-stu-id="3ce86-120">See Also</span></span>  
 [<span data-ttu-id="3ce86-121">EnumJITedFunctions 메서드</span><span class="sxs-lookup"><span data-stu-id="3ce86-121">EnumJITedFunctions Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-enumjitedfunctions-method.md)  
 [<span data-ttu-id="3ce86-122">ICorProfilerInfo4 인터페이스</span><span class="sxs-lookup"><span data-stu-id="3ce86-122">ICorProfilerInfo4 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-interface.md)  
 [<span data-ttu-id="3ce86-123">프로 파일링 인터페이스</span><span class="sxs-lookup"><span data-stu-id="3ce86-123">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)  
 [<span data-ttu-id="3ce86-124">프로파일링</span><span class="sxs-lookup"><span data-stu-id="3ce86-124">Profiling</span></span>](../../../../docs/framework/unmanaged-api/profiling/index.md)
