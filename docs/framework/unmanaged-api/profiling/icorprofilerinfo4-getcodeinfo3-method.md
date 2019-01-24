---
title: ICorProfilerInfo4::GetCodeInfo3 메서드
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo4.GetCodeInfo3
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo4::GetCodeInfo3
helpviewer_keywords:
- GetCodeInfo3 method, ICorProfilerInfo4 interface [.NET Framework profiling]
- ICorProfilerInfo4::GetCodeInfo3 method [.NET Framework profiling]
ms.assetid: bb8c105e-4d9a-4684-8c05-ed6909cc1b8c
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 64382f0d405e84b2be78aac982b085fec35cb37b
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54675101"
---
# <a name="icorprofilerinfo4getcodeinfo3-method"></a><span data-ttu-id="4cea4-102">ICorProfilerInfo4::GetCodeInfo3 메서드</span><span class="sxs-lookup"><span data-stu-id="4cea4-102">ICorProfilerInfo4::GetCodeInfo3 Method</span></span>
<span data-ttu-id="4cea4-103">지정된 함수의 JIT 다시 컴파일된 버전과 연결된 네이티브 코드의 범위를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="4cea4-103">Gets the extents of native code associated with the JIT-recompiled version of the specified function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4cea4-104">구문</span><span class="sxs-lookup"><span data-stu-id="4cea4-104">Syntax</span></span>  
  
```  
HRESULT GetCodeInfo3(  
    [in]  FunctionID functionID,  
    [in]  ReJITID reJitId,  
    [in]  ULONG32 cCodeInfos,  
    [out] ULONG32 *pcCodeInfos,  
    [out, size_is(cCodeInfos), length_is(*pcCodeInfos)]  
    COR_PRF_CODE_INFO codeInfos[]);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="4cea4-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="4cea4-105">Parameters</span></span>  
 `functionID`  
 <span data-ttu-id="4cea4-106">[in] 네이티브 코드가 연결된 함수의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="4cea4-106">[in] The ID of the function with which the native code is associated.</span></span>  
  
 `reJitId`  
 <span data-ttu-id="4cea4-107">[in] JIT 다시 컴파일된 함수의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="4cea4-107">[in] The identity of the JIT-recompiled function.</span></span>  
  
 `cCodeInfos`  
 <span data-ttu-id="4cea4-108">[in] `codeInfos` 배열의 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="4cea4-108">[in] The size of the `codeInfos` array.</span></span>  
  
 `pcCodeInfos`  
 <span data-ttu-id="4cea4-109">[out] 총 수에 대 한 포인터 [COR_PRF_CODE_INFO](../../../../docs/framework/unmanaged-api/profiling/cor-prf-code-info-structure.md) 구조를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4cea4-109">[out] A pointer to the total number of [COR_PRF_CODE_INFO](../../../../docs/framework/unmanaged-api/profiling/cor-prf-code-info-structure.md) structures available.</span></span>  
  
 `codeInfos`  
 <span data-ttu-id="4cea4-110">[out] 호출자가 제공한 버퍼입니다.</span><span class="sxs-lookup"><span data-stu-id="4cea4-110">[out] A caller-provided buffer.</span></span> <span data-ttu-id="4cea4-111">메서드가 반환된 후에는 각각 네이티브 코드 블록을 설명하는 `COR_PRF_CODE_INFO` 구조체의 배열을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="4cea4-111">After the method returns, it contains an array of `COR_PRF_CODE_INFO` structures, each of which describes a block of native code.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4cea4-112">설명</span><span class="sxs-lookup"><span data-stu-id="4cea4-112">Remarks</span></span>  
 <span data-ttu-id="4cea4-113">합니다 `GetCodeInfo3` 메서드는 비슷합니다 [GetCodeInfo2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getcodeinfo2-method.md)한다는 점을 제외 하는 지정 된 IP 주소가 포함 된 함수의 JIT 다시 컴파일된 ID를 찾으면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4cea4-113">The `GetCodeInfo3` method is similar to [GetCodeInfo2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getcodeinfo2-method.md), except that it will get the JIT-recompiled ID of the function that contains the specified IP address.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="4cea4-114">`GetCodeInfo3` 반면 가비지 수집을 트리거할 수 있습니다 [GetCodeInfo2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getcodeinfo2-method.md) 것입니다.</span><span class="sxs-lookup"><span data-stu-id="4cea4-114">`GetCodeInfo3` can trigger a garbage collection, whereas [GetCodeInfo2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getcodeinfo2-method.md) will not.</span></span> <span data-ttu-id="4cea4-115">자세한 내용은 참조는 [CORPROF_E_UNSUPPORTED_CALL_SEQUENCE](../../../../docs/framework/unmanaged-api/profiling/corprof-e-unsupported-call-sequence-hresult.md) HRESULT입니다.</span><span class="sxs-lookup"><span data-stu-id="4cea4-115">For more information, see the [CORPROF_E_UNSUPPORTED_CALL_SEQUENCE](../../../../docs/framework/unmanaged-api/profiling/corprof-e-unsupported-call-sequence-hresult.md) HRESULT.</span></span>  
  
 <span data-ttu-id="4cea4-116">범위는 CIL(Common Intermediate Language) 오프셋의 오름차순으로 정렬됩니다.</span><span class="sxs-lookup"><span data-stu-id="4cea4-116">The extents are sorted in order of increasing Common Intermediate Language (CIL) offset.</span></span>  
  
 <span data-ttu-id="4cea4-117">후 `GetCodeInfo3` 반환 되어 있는지 확인 해야 합니다는 `codeInfos` 버퍼가 모두 포함 하기에 충분 합니다 [COR_PRF_CODE_INFO](../../../../docs/framework/unmanaged-api/profiling/cor-prf-code-info-structure.md) 구조입니다.</span><span class="sxs-lookup"><span data-stu-id="4cea4-117">After `GetCodeInfo3` returns, you must verify that the `codeInfos` buffer was large enough to contain all the [COR_PRF_CODE_INFO](../../../../docs/framework/unmanaged-api/profiling/cor-prf-code-info-structure.md) structures.</span></span> <span data-ttu-id="4cea4-118">이렇게 하려면 `cCodeInfos` 값을 `cchName` 매개 변수의 값과 비교합니다.</span><span class="sxs-lookup"><span data-stu-id="4cea4-118">To do this, compare the value of `cCodeInfos` with the value of the `cchName` parameter.</span></span> <span data-ttu-id="4cea4-119">하는 경우 `cCodeInfos` 의 크기로 나눈를 [COR_PRF_CODE_INFO](../../../../docs/framework/unmanaged-api/profiling/cor-prf-code-info-structure.md) 구조 보다 작습니다 `pcCodeInfos`, 더 큰 할당 `codeInfos` 버퍼, 업데이트 `cCodeInfos` 호출이 고 큰 새 크기로 사용 하 여 `GetCodeInfo3` 다시 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="4cea4-119">If `cCodeInfos` divided by the size of a [COR_PRF_CODE_INFO](../../../../docs/framework/unmanaged-api/profiling/cor-prf-code-info-structure.md) structure is smaller than `pcCodeInfos`, allocate a larger `codeInfos` buffer, update `cCodeInfos` with the new, larger size, and call `GetCodeInfo3` again.</span></span>  
  
 <span data-ttu-id="4cea4-120">또는 길이가 0인 `codeInfos` 버퍼로 `GetCodeInfo3`을 먼저 호출하여 올바른 버퍼 크기를 구합니다.</span><span class="sxs-lookup"><span data-stu-id="4cea4-120">Alternatively, you can first call `GetCodeInfo3` with a zero-length `codeInfos` buffer to obtain the correct buffer size.</span></span> <span data-ttu-id="4cea4-121">설정할 수 있습니다 합니다 `codeInfos` 버퍼 크기에서 반환 된 값 `pcCodeInfos`의 크기를 곱한 값을 [COR_PRF_CODE_INFO](../../../../docs/framework/unmanaged-api/profiling/cor-prf-code-info-structure.md) 구조 및 호출 `GetCodeInfo3` 다시 합니다.</span><span class="sxs-lookup"><span data-stu-id="4cea4-121">You can then set the `codeInfos` buffer size to the value returned in `pcCodeInfos`, multiplied by the size of a [COR_PRF_CODE_INFO](../../../../docs/framework/unmanaged-api/profiling/cor-prf-code-info-structure.md) structure, and call `GetCodeInfo3` again.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4cea4-122">요구 사항</span><span class="sxs-lookup"><span data-stu-id="4cea4-122">Requirements</span></span>  
 <span data-ttu-id="4cea4-123">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="4cea4-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4cea4-124">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="4cea4-124">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="4cea4-125">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4cea4-125">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4cea4-126">**.NET Framework 버전:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4cea4-126">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4cea4-127">참고자료</span><span class="sxs-lookup"><span data-stu-id="4cea4-127">See also</span></span>
- [<span data-ttu-id="4cea4-128">GetCodeInfo2 메서드</span><span class="sxs-lookup"><span data-stu-id="4cea4-128">GetCodeInfo2 Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getcodeinfo2-method.md)
- [<span data-ttu-id="4cea4-129">ICorProfilerInfo4 인터페이스</span><span class="sxs-lookup"><span data-stu-id="4cea4-129">ICorProfilerInfo4 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-interface.md)
- [<span data-ttu-id="4cea4-130">프로파일링 인터페이스</span><span class="sxs-lookup"><span data-stu-id="4cea4-130">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
- [<span data-ttu-id="4cea4-131">프로파일링</span><span class="sxs-lookup"><span data-stu-id="4cea4-131">Profiling</span></span>](../../../../docs/framework/unmanaged-api/profiling/index.md)
