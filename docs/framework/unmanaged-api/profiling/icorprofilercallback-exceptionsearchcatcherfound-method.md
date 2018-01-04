---
title: "ICorProfilerCallback::ExceptionSearchCatcherFound 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerCallback.ExceptionSearchCatcherFound
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerCallback::ExceptionSearchCatcherFound
helpviewer_keywords:
- ExceptionSearchCatcherFound method [.NET Framework profiling]
- ICorProfilerCallback::ExceptionSearchCatcherFound method [.NET Framework profiling]
ms.assetid: 190f424d-5e37-4163-a191-0895686e9476
topic_type: apiref
caps.latest.revision: "12"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: fc226b6102c50b118a4b13f9cd25700dd1ca7301
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="icorprofilercallbackexceptionsearchcatcherfound-method"></a><span data-ttu-id="ade4c-102">ICorProfilerCallback::ExceptionSearchCatcherFound 메서드</span><span class="sxs-lookup"><span data-stu-id="ade4c-102">ICorProfilerCallback::ExceptionSearchCatcherFound Method</span></span>
<span data-ttu-id="ade4c-103">예외 처리의 검색 단계에서 throw 된 예외에 대 한 처리기를 찾았으며 프로파일러에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="ade4c-103">Notifies the profiler that the search phase of exception handling has located a handler for the exception that was thrown.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ade4c-104">구문</span><span class="sxs-lookup"><span data-stu-id="ade4c-104">Syntax</span></span>  
  
```  
RESULT ExceptionSearchCatcherFound(  
    [in] FunctionID functionId);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="ade4c-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="ade4c-105">Parameters</span></span>  
 `functionId`  
 <span data-ttu-id="ade4c-106">[in] 예외 처리기가 포함 된 함수의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="ade4c-106">[in] The ID of the function that contains the exception handler.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ade4c-107">요구 사항</span><span class="sxs-lookup"><span data-stu-id="ade4c-107">Requirements</span></span>  
 <span data-ttu-id="ade4c-108">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="ade4c-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ade4c-109">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="ade4c-109">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="ade4c-110">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ade4c-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ade4c-111">**.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ade4c-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ade4c-112">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ade4c-112">See Also</span></span>  
 [<span data-ttu-id="ade4c-113">ICorProfilerCallback 인터페이스</span><span class="sxs-lookup"><span data-stu-id="ade4c-113">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
