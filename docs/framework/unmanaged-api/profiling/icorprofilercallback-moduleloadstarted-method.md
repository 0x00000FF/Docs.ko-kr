---
title: "ICorProfilerCallback::ModuleLoadStarted 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- ICorProfilerCallback.ModuleLoadStarted
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::ModuleLoadStarted
helpviewer_keywords:
- ModuleLoadStarted method [.NET Framework profiling]
- ICorProfilerCallback::ModuleLoadStarted method [.NET Framework profiling]
ms.assetid: 9cd2fe75-408a-400f-a6b1-9979624a2fe2
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 09f88b2a287eef0bf3fe8edeba4b76a3b3a1ce4a
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="icorprofilercallbackmoduleloadstarted-method"></a><span data-ttu-id="e774e-102">ICorProfilerCallback::ModuleLoadStarted 메서드</span><span class="sxs-lookup"><span data-stu-id="e774e-102">ICorProfilerCallback::ModuleLoadStarted Method</span></span>
<span data-ttu-id="e774e-103">모듈 로드 되 고 있음을 프로파일러에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="e774e-103">Notifies the profiler that a module is being loaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e774e-104">구문</span><span class="sxs-lookup"><span data-stu-id="e774e-104">Syntax</span></span>  
  
```  
HRESULT ModuleLoadStarted(  
    [in] ModuleID moduleId);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="e774e-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="e774e-105">Parameters</span></span>  
 `moduleId`  
 <span data-ttu-id="e774e-106">[in] 로드 되는 모듈의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="e774e-106">[in] The ID of the module that is being loaded.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e774e-107">설명</span><span class="sxs-lookup"><span data-stu-id="e774e-107">Remarks</span></span>  
 <span data-ttu-id="e774e-108">값 `moduleId` 될 때까지 정보 요청에 유효 하지는 [icorprofilercallback:: Moduleloadfinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadfinished-method.md) 메서드를 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="e774e-108">The value of `moduleId` is not valid for an information request until the [ICorProfilerCallback::ModuleLoadFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadfinished-method.md) method is called.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e774e-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="e774e-109">Requirements</span></span>  
 <span data-ttu-id="e774e-110">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="e774e-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e774e-111">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="e774e-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="e774e-112">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e774e-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e774e-113">**.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e774e-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e774e-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="e774e-114">See Also</span></span>  
 [<span data-ttu-id="e774e-115">ICorProfilerCallback 인터페이스</span><span class="sxs-lookup"><span data-stu-id="e774e-115">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
