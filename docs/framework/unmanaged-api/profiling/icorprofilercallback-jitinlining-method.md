---
title: ICorProfilerCallback::JITInlining 메서드
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.JITInlining
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::JITInlining
helpviewer_keywords:
- JITInlining method [.NET Framework profiling]
- ICorProfilerCallback::JITInlining method [.NET Framework profiling]
ms.assetid: c2f45801-dd38-4b78-b6b7-64397dc73f83
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 53a8f9aefa4460493113c035aa05e971b05d5167
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54500173"
---
# <a name="icorprofilercallbackjitinlining-method"></a><span data-ttu-id="8b2c1-102">ICorProfilerCallback::JITInlining 메서드</span><span class="sxs-lookup"><span data-stu-id="8b2c1-102">ICorProfilerCallback::JITInlining Method</span></span>
<span data-ttu-id="8b2c1-103">다른 함수에 따라 함수를 삽입할 시간 (JIT) 컴파일러는 프로파일러에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="8b2c1-103">Notifies the profiler that the just-in-time (JIT) compiler is about to insert a function in line with another function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8b2c1-104">구문</span><span class="sxs-lookup"><span data-stu-id="8b2c1-104">Syntax</span></span>  
  
```  
HRESULT JITInlining(  
    [in]  FunctionID callerId,  
    [in]  FunctionID calleeId,  
    [out] BOOL      *pfShouldInline);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="8b2c1-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="8b2c1-105">Parameters</span></span>  
 `callerId`  
 <span data-ttu-id="8b2c1-106">[in] 함수의 ID는 `calleeId` 함수 삽입 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8b2c1-106">[in] The ID of the function into which the `calleeId` function will be inserted.</span></span>  
  
 `calleeId`  
 <span data-ttu-id="8b2c1-107">[in] 삽입할 함수의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="8b2c1-107">[in] The ID of the function to be inserted.</span></span>  
  
 `pfShouldInline`  
 <span data-ttu-id="8b2c1-108">[out] `true` ; 발생을 삽입할 수 있도록이 고, 그렇지 `false`합니다.</span><span class="sxs-lookup"><span data-stu-id="8b2c1-108">[out] `true` to allow the insertion to occur; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8b2c1-109">설명</span><span class="sxs-lookup"><span data-stu-id="8b2c1-109">Remarks</span></span>  
 <span data-ttu-id="8b2c1-110">프로파일러 설정할 수 있습니다 `pfShouldInline` 를 `false` 방지 하기 위해 합니다 `calleeId` 함수를 삽입 하는 `callerId` 함수.</span><span class="sxs-lookup"><span data-stu-id="8b2c1-110">The profiler can set `pfShouldInline` to `false` to prevent the `calleeId` function from being inserted into the `callerId` function.</span></span> <span data-ttu-id="8b2c1-111">또한 프로파일러 전역적으로 해제할 수 인라인 삽입 COR_PRF_DISABLE_INLINING 값을 사용 하 여 합니다 [COR_PRF_MONITOR](../../../../docs/framework/unmanaged-api/profiling/cor-prf-monitor-enumeration.md) 열거형입니다.</span><span class="sxs-lookup"><span data-stu-id="8b2c1-111">Also, the profiler can globally disable inline insertion by using the COR_PRF_DISABLE_INLINING value of the [COR_PRF_MONITOR](../../../../docs/framework/unmanaged-api/profiling/cor-prf-monitor-enumeration.md) enumeration.</span></span>  
  
 <span data-ttu-id="8b2c1-112">삽입 함수를 인라인으로 출입에 대 한 이벤트를 발생 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8b2c1-112">Functions inserted inline do not raise events for entering or leaving.</span></span> <span data-ttu-id="8b2c1-113">따라서 프로파일러 설정 해야 합니다 `pfShouldInline` 에 `false` 정확한 호출 그래프를 생성 하기 위해.</span><span class="sxs-lookup"><span data-stu-id="8b2c1-113">Therefore, the profiler must set `pfShouldInline` to `false` in order to produce an accurate callgraph.</span></span> <span data-ttu-id="8b2c1-114">설정 `pfShouldInline` 에 `false` 인라인 삽입에서 일반적으로 속도 증가 하 고 삽입 된 메서드에 대 한 별도 JIT 컴파일 이벤트 수가 감소 하기 때문에 성능이 저하 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8b2c1-114">Setting `pfShouldInline` to `false` will affect performance, because inline insertion typically increases speed and reduces the number of separate JIT compilation events for the inserted method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8b2c1-115">요구 사항</span><span class="sxs-lookup"><span data-stu-id="8b2c1-115">Requirements</span></span>  
 <span data-ttu-id="8b2c1-116">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="8b2c1-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8b2c1-117">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="8b2c1-117">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="8b2c1-118">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8b2c1-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8b2c1-119">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8b2c1-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8b2c1-120">참고자료</span><span class="sxs-lookup"><span data-stu-id="8b2c1-120">See also</span></span>
- [<span data-ttu-id="8b2c1-121">ICorProfilerCallback 인터페이스</span><span class="sxs-lookup"><span data-stu-id="8b2c1-121">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
