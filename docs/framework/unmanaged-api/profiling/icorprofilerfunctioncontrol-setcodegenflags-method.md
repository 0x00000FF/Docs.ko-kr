---
title: ICorProfilerFunctionControl::SetCodegenFlags 메서드
ms.date: 03/30/2017
api_name:
- ICorProfilerFunctionControl.SetCodegenFlags
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerFunctionControl::SetCodegenFlags
helpviewer_keywords:
- ICorProfilerFunctionControl::SetCodegenFlags method [.NET Framework profiling]
- SetCodegenFlags method, ICorProfilerFunctionControl interface [.NET Framework profiling]
ms.assetid: a2d5daa5-b990-4ae5-bf2a-c0862fe58bd7
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 12f91bdd264135eb0ff3a48e15611cf5a0e3c064
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59104444"
---
# <a name="icorprofilerfunctioncontrolsetcodegenflags-method"></a><span data-ttu-id="a5e47-102">ICorProfilerFunctionControl::SetCodegenFlags 메서드</span><span class="sxs-lookup"><span data-stu-id="a5e47-102">ICorProfilerFunctionControl::SetCodegenFlags Method</span></span>
<span data-ttu-id="a5e47-103">하나 이상의 플래그를 설정 합니다 [COR_PRF_CODEGEN_FLAGS](../../../../docs/framework/unmanaged-api/profiling/cor-prf-codegen-flags-enumeration.md) 다시 컴파일된 함수는-just-in-time (JIT)에 대 한 코드 생성을 제어 하는 열거형입니다.</span><span class="sxs-lookup"><span data-stu-id="a5e47-103">Sets one or more flags from the [COR_PRF_CODEGEN_FLAGS](../../../../docs/framework/unmanaged-api/profiling/cor-prf-codegen-flags-enumeration.md) enumeration to control code generation for a just-in-time (JIT) recompiled function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a5e47-104">구문</span><span class="sxs-lookup"><span data-stu-id="a5e47-104">Syntax</span></span>  
  
```  
HRESULT SetCodegenFlags(  
    [in] DWORD flags);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a5e47-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="a5e47-105">Parameters</span></span>  
 `flags`  
 <span data-ttu-id="a5e47-106">[in] 하나 이상의 플래그를 [COR_PRF_CODEGEN_FLAGS](../../../../docs/framework/unmanaged-api/profiling/cor-prf-codegen-flags-enumeration.md) 열거형입니다.</span><span class="sxs-lookup"><span data-stu-id="a5e47-106">[in] One or more flags from the [COR_PRF_CODEGEN_FLAGS](../../../../docs/framework/unmanaged-api/profiling/cor-prf-codegen-flags-enumeration.md) enumeration.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a5e47-107">설명</span><span class="sxs-lookup"><span data-stu-id="a5e47-107">Remarks</span></span>  
 <span data-ttu-id="a5e47-108">프로파일러를 통해이 인터페이스의 인스턴스를 가져오고 합니다 [ICorProfilerCallback4::GetReJITParameters](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-getrejitparameters-method.md) 콜백 합니다.</span><span class="sxs-lookup"><span data-stu-id="a5e47-108">The profiler obtains an instance of this interface through the [ICorProfilerCallback4::GetReJITParameters](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-getrejitparameters-method.md) callback.</span></span> <span data-ttu-id="a5e47-109">`SetCodegenFlags` 프로파일러가 다시 컴파일된 함수에 대 한 코드 생성을 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a5e47-109">`SetCodegenFlags` allows the profiler to control the code generation for the recompiled function.</span></span> <span data-ttu-id="a5e47-110">다른 모든 JIT 다시 컴파일 매개 변수에서와 마찬가지로 코드 생성 플래그를 함수의 모든 인스턴스에 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a5e47-110">As with all other JIT recompilation parameters, the code generation flags apply to all instances of the function.</span></span>  
  
 <span data-ttu-id="a5e47-111">JIT 컴파일러는 함수를 컴파일할 때 다른 원본에서 지정 된 다른 플래그와 함께 이러한 컴파일 플래그를 고려 합니다.</span><span class="sxs-lookup"><span data-stu-id="a5e47-111">The JIT compiler considers these compilation flags, along with other flags specified by other sources, when compiling a function.</span></span>  <span data-ttu-id="a5e47-112">다른 원본 디버거, 전역 플래그를 사용 하 여 시작 하 여 프로파일러에 의해 설정 된 [icorprofilerinfo:: Seteventmask](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-seteventmask-method.md) 메서드 (값을 사용 하 여 `COR_PRF_DISABLE_INLINING` 및 `COR_PRF_DISABLE_OPTIMIZATIONS`), 및 프로파일러 [ Icorprofilercallback:: Jitinlining](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitinlining-method.md) 콜백 합니다.</span><span class="sxs-lookup"><span data-stu-id="a5e47-112">The other sources include the debugger, global flags set by the profiler on startup by using the [ICorProfilerInfo::SetEventMask](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-seteventmask-method.md) method (with the values `COR_PRF_DISABLE_INLINING` and `COR_PRF_DISABLE_OPTIMIZATIONS`), and the profiler’s [ICorProfilerCallback::JITInlining](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitinlining-method.md) callback.</span></span>  <span data-ttu-id="a5e47-113">JIT 컴파일러 최적화의 최소 크기를 요청 하는 원본에 대 한 우선 순위를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="a5e47-113">The JIT compiler gives precedence to a source that requests the least amount of optimizing.</span></span>  <span data-ttu-id="a5e47-114">예를 들어, 프로파일러를 지정 하는 경우 `COR_PRF_DISABLE_INLINING` 시작 시 하지만 지정 하지 않습니다 `COR_PRF_CODEGEN_DISABLE_INLINING` 에 [icorprofilerfunctioncontrol:: Setcodegenflags](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctioncontrol-setcodegenflags-method.md) 콜백, 인라인 처리는 여전히 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a5e47-114">For example, if the profiler specifies `COR_PRF_DISABLE_INLINING` on startup, but does not specify `COR_PRF_CODEGEN_DISABLE_INLINING` in the [ICorProfilerFunctionControl::SetCodegenFlags](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctioncontrol-setcodegenflags-method.md) callback, inlining is still disabled.</span></span>  <span data-ttu-id="a5e47-115">마찬가지로, 프로파일러를 지정 하지 않는 경우 `COR_PRF_CODEGEN_DISABLE_INLINING` 에서 `SetCodegenFlags`, 하지만 다음 비활성화를 사용 하 여 인라인 합니다 [icorprofilercallback:: Jitinlining](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitinlining-method.md) 콜백, 인라인을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a5e47-115">Similarly, if the profiler does not specify `COR_PRF_CODEGEN_DISABLE_INLINING` in `SetCodegenFlags`, but then disables inlining by using the [ICorProfilerCallback::JITInlining](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitinlining-method.md) callback, inlining is disabled.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a5e47-116">요구 사항</span><span class="sxs-lookup"><span data-stu-id="a5e47-116">Requirements</span></span>  
 <span data-ttu-id="a5e47-117">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="a5e47-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a5e47-118">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="a5e47-118">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="a5e47-119">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a5e47-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a5e47-120">**.NET Framework 버전:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a5e47-120">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a5e47-121">참고자료</span><span class="sxs-lookup"><span data-stu-id="a5e47-121">See also</span></span>

- [<span data-ttu-id="a5e47-122">ICorProfilerFunctionControl 인터페이스</span><span class="sxs-lookup"><span data-stu-id="a5e47-122">ICorProfilerFunctionControl Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctioncontrol-interface.md)
