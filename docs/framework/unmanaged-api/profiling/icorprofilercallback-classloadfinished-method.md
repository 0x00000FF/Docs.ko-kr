---
title: ICorProfilerCallback::ClassLoadFinished 메서드
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.ClassLoadFinished
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::ClassLoadFinished
helpviewer_keywords:
- ClassLoadFinished method [.NET Framework profiling]
- ICorProfilerCallback::ClassLoadFinished method [.NET Framework profiling]
ms.assetid: 3dd80fbe-d62d-4d4d-acf8-5b7d0efe607e
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 6508c989b143780090d582fd4175fe20bedeb770
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/10/2019
ms.locfileid: "67745444"
---
# <a name="icorprofilercallbackclassloadfinished-method"></a><span data-ttu-id="fb187-102">ICorProfilerCallback::ClassLoadFinished 메서드</span><span class="sxs-lookup"><span data-stu-id="fb187-102">ICorProfilerCallback::ClassLoadFinished Method</span></span>
<span data-ttu-id="fb187-103">클래스 로드 되었음을 프로파일러에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="fb187-103">Notifies the profiler that a class has finished loading.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fb187-104">구문</span><span class="sxs-lookup"><span data-stu-id="fb187-104">Syntax</span></span>  
  
```cpp  
HRESULT ClassLoadFinished(  
    [in] ClassID classId,  
    [in] HRESULT hrStatus);  
```  
  
## <a name="parameters"></a><span data-ttu-id="fb187-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="fb187-105">Parameters</span></span>  
 `classId`  
 <span data-ttu-id="fb187-106">[in] 로드 된 클래스를 식별 합니다.</span><span class="sxs-lookup"><span data-stu-id="fb187-106">[in] Identifies the class that was loaded.</span></span>  
  
 `hrStatus`  
 <span data-ttu-id="fb187-107">[in] 클래스가 성공적으로 로드 하는지 여부를 나타내는 HRESULT입니다.</span><span class="sxs-lookup"><span data-stu-id="fb187-107">[in] An HRESULT that indicates whether the class loaded successfully.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="fb187-108">설명</span><span class="sxs-lookup"><span data-stu-id="fb187-108">Remarks</span></span>  
 <span data-ttu-id="fb187-109">값 `classId` 될 때까지 정보 요청에 적합 하지 않습니다는 `ClassLoadFinished` 메서드가 호출 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fb187-109">The value of `classId` is not valid for an information request until the `ClassLoadFinished` method is called.</span></span>  
  
 <span data-ttu-id="fb187-110">일부 클래스를 로드 한 후 계속 사용할 수는 `ClassLoadFinished` 콜백 합니다.</span><span class="sxs-lookup"><span data-stu-id="fb187-110">Some parts of loading the class might continue after the `ClassLoadFinished` callback.</span></span> <span data-ttu-id="fb187-111">오류 HRESULT에서 `hrStatus` 오류가 발생 했음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="fb187-111">A failure HRESULT in `hrStatus` indicates a failure.</span></span> <span data-ttu-id="fb187-112">그러나 성공 HRESULT에서 `hrStatus` 클래스를 로드 하는 첫 번째 부분 성공 했다는 것만 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="fb187-112">However, a success HRESULT in `hrStatus` indicates only that the first part of loading the class has succeeded.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fb187-113">요구 사항</span><span class="sxs-lookup"><span data-stu-id="fb187-113">Requirements</span></span>  
 <span data-ttu-id="fb187-114">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="fb187-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fb187-115">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="fb187-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="fb187-116">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="fb187-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="fb187-117">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fb187-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fb187-118">참고자료</span><span class="sxs-lookup"><span data-stu-id="fb187-118">See also</span></span>

- [<span data-ttu-id="fb187-119">ICorProfilerCallback 인터페이스</span><span class="sxs-lookup"><span data-stu-id="fb187-119">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [<span data-ttu-id="fb187-120">ClassLoadStarted 메서드</span><span class="sxs-lookup"><span data-stu-id="fb187-120">ClassLoadStarted Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-classloadstarted-method.md)
