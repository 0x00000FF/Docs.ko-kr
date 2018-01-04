---
title: "FunctionEnter3 함수"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: FunctionEnter3
api_location: mscorwks.dll
api_type: COM
f1_keywords: FunctionEnter3
helpviewer_keywords: FunctionEnter3 function [.NET Framework profiling]
ms.assetid: ef782c53-dae7-4990-b4ad-fddb1e690d4e
topic_type: apiref
caps.latest.revision: "12"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 4bbdfa608f1ea60462dc432a7c2b98cafe66d7be
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="functionenter3-function"></a><span data-ttu-id="dafdf-102">FunctionEnter3 함수</span><span class="sxs-lookup"><span data-stu-id="dafdf-102">FunctionEnter3 Function</span></span>
<span data-ttu-id="dafdf-103">제어는 함수에 전달 되 고 있음을 프로파일러에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="dafdf-103">Notifies the profiler that control is being passed to a function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dafdf-104">구문</span><span class="sxs-lookup"><span data-stu-id="dafdf-104">Syntax</span></span>  
  
```  
void __stdcall FunctionEnter3(FunctionOrRemappedID functionOrRemappedID);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="dafdf-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="dafdf-105">Parameters</span></span>  
 `functionOrRemappedID`  
 <span data-ttu-id="dafdf-106">[in] 컨트롤이 전달 함수의 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="dafdf-106">[in] The identifier of the function to which control is passed.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="dafdf-107">설명</span><span class="sxs-lookup"><span data-stu-id="dafdf-107">Remarks</span></span>  
 <span data-ttu-id="dafdf-108">`FunctionEnter3` 콜백 함수에 호출 되는 인수 검사는 지원 되지 않는 프로파일러에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="dafdf-108">The `FunctionEnter3` callback function notifies the profiler as functions are being called, but does not support argument inspection.</span></span> <span data-ttu-id="dafdf-109">사용 하 여는 [icorprofilerinfo3:: Setenterleavefunctionhooks3 메서드](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-setenterleavefunctionhooks3-method.md) 이 함수를 구현 하 여 등록할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dafdf-109">Use the [ICorProfilerInfo3::SetEnterLeaveFunctionHooks3 method](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-setenterleavefunctionhooks3-method.md) to register your implementation of this function.</span></span>  
  
 <span data-ttu-id="dafdf-110">`FunctionEnter3` 는 콜백 함수입니다; 구현 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="dafdf-110">The `FunctionEnter3` function is a callback; you must implement it.</span></span> <span data-ttu-id="dafdf-111">구현을 사용 해야 합니다는 `__declspec(naked)` 저장소 클래스 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="dafdf-111">The implementation must use the `__declspec(naked)` storage-class attribute.</span></span>  
  
 <span data-ttu-id="dafdf-112">실행 엔진은이 함수를 호출 하기 전에 레지스터를 저장 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="dafdf-112">The execution engine does not save any registers before calling this function.</span></span>  
  
-   <span data-ttu-id="dafdf-113">항목에는 부동 소수점 FPU (단위) 포함 하 여 사용 하는 모든 레지스터를 저장 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="dafdf-113">On entry, you must save all registers that you use, including those in the floating-point unit (FPU).</span></span>  
  
-   <span data-ttu-id="dafdf-114">끝낼 때 호출자에 의해 밀어넣은 모든 매개 변수 팝 하 여 스택을 복원 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="dafdf-114">On exit, you must restore the stack by popping off all the parameters that were pushed by its caller.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="dafdf-115">요구 사항</span><span class="sxs-lookup"><span data-stu-id="dafdf-115">Requirements</span></span>  
 <span data-ttu-id="dafdf-116">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="dafdf-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="dafdf-117">**헤더:** CorProf.idl</span><span class="sxs-lookup"><span data-stu-id="dafdf-117">**Header:** CorProf.idl</span></span>  
  
 <span data-ttu-id="dafdf-118">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="dafdf-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="dafdf-119">**.NET framework 버전:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="dafdf-119">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dafdf-120">참고 항목</span><span class="sxs-lookup"><span data-stu-id="dafdf-120">See Also</span></span>  
 [<span data-ttu-id="dafdf-121">FunctionLeave3</span><span class="sxs-lookup"><span data-stu-id="dafdf-121">FunctionLeave3</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionleave3-function.md)  
 [<span data-ttu-id="dafdf-122">FunctionTailcall3</span><span class="sxs-lookup"><span data-stu-id="dafdf-122">FunctionTailcall3</span></span>](../../../../docs/framework/unmanaged-api/profiling/functiontailcall3-function.md)  
 [<span data-ttu-id="dafdf-123">FunctionEnter3WithInfo</span><span class="sxs-lookup"><span data-stu-id="dafdf-123">FunctionEnter3WithInfo</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionenter3withinfo-function.md)  
 [<span data-ttu-id="dafdf-124">FunctionLeave3WithInfo</span><span class="sxs-lookup"><span data-stu-id="dafdf-124">FunctionLeave3WithInfo</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionleave3withinfo-function.md)  
 [<span data-ttu-id="dafdf-125">FunctionTailcall3WithInfo</span><span class="sxs-lookup"><span data-stu-id="dafdf-125">FunctionTailcall3WithInfo</span></span>](../../../../docs/framework/unmanaged-api/profiling/functiontailcall3withinfo-function.md)  
 [<span data-ttu-id="dafdf-126">SetEnterLeaveFunctionHooks3</span><span class="sxs-lookup"><span data-stu-id="dafdf-126">SetEnterLeaveFunctionHooks3</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-setenterleavefunctionhooks3-method.md)  
 [<span data-ttu-id="dafdf-127">SetEnterLeaveFunctionHooks3WithInfo</span><span class="sxs-lookup"><span data-stu-id="dafdf-127">SetEnterLeaveFunctionHooks3WithInfo</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-setenterleavefunctionhooks3withinfo-method.md)  
 [<span data-ttu-id="dafdf-128">SetFunctionIDMapper</span><span class="sxs-lookup"><span data-stu-id="dafdf-128">SetFunctionIDMapper</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-setfunctionidmapper-method.md)  
 [<span data-ttu-id="dafdf-129">SetFunctionIDMapper2</span><span class="sxs-lookup"><span data-stu-id="dafdf-129">SetFunctionIDMapper2</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-setfunctionidmapper2-method.md)  
 [<span data-ttu-id="dafdf-130">프로파일링 전역 정적 함수</span><span class="sxs-lookup"><span data-stu-id="dafdf-130">Profiling Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-global-static-functions.md)
