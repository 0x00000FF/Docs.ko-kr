---
title: ICorProfilerCallback3::InitializeForAttach 메서드
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback3.InitializeForAttach Method
api_location:
- Mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback3::InitializeForAttach
helpviewer_keywords:
- InitializeForAttach method [.NET Framework profiling]
- ICorProfilerCallback3::InitializeForAttach method [.NET Framework profiling]
ms.assetid: bed097b3-6d52-46c9-bee7-ac7910b6fc3f
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 84d07fe975bab1b0af81299893b52142630b5bb9
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61992240"
---
# <a name="icorprofilercallback3initializeforattach-method"></a><span data-ttu-id="5888a-102">ICorProfilerCallback3::InitializeForAttach 메서드</span><span class="sxs-lookup"><span data-stu-id="5888a-102">ICorProfilerCallback3::InitializeForAttach Method</span></span>
<span data-ttu-id="5888a-103">프로파일러가 연결 작업 후 상태를 초기화할 수 있도록 CLR(공용 언어 런타임)에 의해 호출됩니다.</span><span class="sxs-lookup"><span data-stu-id="5888a-103">Called by the common language runtime (CLR) to give the profiler an opportunity to initialize its state after an attach operation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5888a-104">구문</span><span class="sxs-lookup"><span data-stu-id="5888a-104">Syntax</span></span>  
  
```  
HRESULT InitializeForAttach(  
            [in] IUnknown * pCorProfilerInfoUnk,  
            [in] void * pvClientData,  
            [in] UINT cbClientData);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5888a-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="5888a-105">Parameters</span></span>  
 `pCorProfilerInfoUnk`  
 <span data-ttu-id="5888a-106">[in] `ICorProfilerInfo*` 인터페이스에 대한 인터페이스 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="5888a-106">[in] An interface pointer for the `ICorProfilerInfo*` interface.</span></span>  
  
 `pvClientData`  
 <span data-ttu-id="5888a-107">[in] 에 전달 된 데이터에 대 한 포인터를 [iclrprofiling:: Attachprofiler](../../../../docs/framework/unmanaged-api/profiling/iclrprofiling-attachprofiler-method.md) 에서 메서드는 `pvClientData` 매개 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="5888a-107">[in] A pointer to the data passed to the [IClrProfiling::AttachProfiler](../../../../docs/framework/unmanaged-api/profiling/iclrprofiling-attachprofiler-method.md) method in its `pvClientData` parameter.</span></span> <span data-ttu-id="5888a-108">이 매개 변수가 null일 경우 `cbClientData`는 0이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5888a-108">If this parameter is null, `cbClientData` will be 0 (zero).</span></span> <span data-ttu-id="5888a-109">CLR은 `InitializeForAttach`에서 반환될 때 이 메모리를 해제합니다.</span><span class="sxs-lookup"><span data-stu-id="5888a-109">The CLR frees this memory when it returns from `InitializeForAttach`.</span></span>  
  
 `cbClientData`  
 <span data-ttu-id="5888a-110">[in] `pvClientData`가 가리키는 데이터의 크기(바이트)입니다.</span><span class="sxs-lookup"><span data-stu-id="5888a-110">[in] The size, in bytes, of the data that `pvClientData` points to.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5888a-111">설명</span><span class="sxs-lookup"><span data-stu-id="5888a-111">Remarks</span></span>  
 <span data-ttu-id="5888a-112">CLR은 프로파일러가 콜백을 요청할 수 있도록 `InitializeForAttach`를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="5888a-112">The CLR calls `InitializeForAttach` to give the profiler an opportunity to request callbacks.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5888a-113">요구 사항</span><span class="sxs-lookup"><span data-stu-id="5888a-113">Requirements</span></span>  
 <span data-ttu-id="5888a-114">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="5888a-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5888a-115">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="5888a-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="5888a-116">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5888a-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5888a-117">**.NET Framework 버전:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5888a-117">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5888a-118">참고자료</span><span class="sxs-lookup"><span data-stu-id="5888a-118">See also</span></span>

- [<span data-ttu-id="5888a-119">ICorProfilerCallback 인터페이스</span><span class="sxs-lookup"><span data-stu-id="5888a-119">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [<span data-ttu-id="5888a-120">ICorProfilerInfo3 인터페이스</span><span class="sxs-lookup"><span data-stu-id="5888a-120">ICorProfilerInfo3 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-interface.md)
- [<span data-ttu-id="5888a-121">프로파일링 인터페이스</span><span class="sxs-lookup"><span data-stu-id="5888a-121">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
- [<span data-ttu-id="5888a-122">프로파일링</span><span class="sxs-lookup"><span data-stu-id="5888a-122">Profiling</span></span>](../../../../docs/framework/unmanaged-api/profiling/index.md)
