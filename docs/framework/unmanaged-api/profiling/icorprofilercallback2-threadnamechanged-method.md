---
title: ICorProfilerCallback2::ThreadNameChanged 메서드
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback2.ThreadNameChanged
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback2::ThreadNameChanged
helpviewer_keywords:
- ThreadNameChanged method [.NET Framework profiling]
- ICorProfilerCallback2::ThreadNameChanged method [.NET Framework profiling]
ms.assetid: c8bbd76d-a9ff-44f2-87a6-be052819da36
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: bd350c843c32102291de8327f5c37b27e287fd5c
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54706367"
---
# <a name="icorprofilercallback2threadnamechanged-method"></a><span data-ttu-id="fdc5c-102">ICorProfilerCallback2::ThreadNameChanged 메서드</span><span class="sxs-lookup"><span data-stu-id="fdc5c-102">ICorProfilerCallback2::ThreadNameChanged Method</span></span>
<span data-ttu-id="fdc5c-103">스레드의 이름 변경 된 코드 프로파일러에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="fdc5c-103">Notifies the code profiler that the name of a thread has changed.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fdc5c-104">구문</span><span class="sxs-lookup"><span data-stu-id="fdc5c-104">Syntax</span></span>  
  
```  
HRESULT ThreadNameChanged(  
    [in] ThreadID threadId,  
    [in] ULONG cchName,  
    [in] WCHAR name[]);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="fdc5c-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="fdc5c-105">Parameters</span></span>  
 `threadId`  
 <span data-ttu-id="fdc5c-106">[in] 스레드 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="fdc5c-106">[in] The ID of the thread.</span></span>  
  
 `cchName`  
 <span data-ttu-id="fdc5c-107">[in] 스레드의 새 이름의 길이입니다.</span><span class="sxs-lookup"><span data-stu-id="fdc5c-107">[in] The length of the new name of the thread.</span></span>  
  
 `name`  
 <span data-ttu-id="fdc5c-108">[in] 스레드의 새 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="fdc5c-108">[in] The new name of the thread.</span></span> <span data-ttu-id="fdc5c-109">이름은 null로 종결 되지 합니다.</span><span class="sxs-lookup"><span data-stu-id="fdc5c-109">The name is not null-terminated.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fdc5c-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="fdc5c-110">Requirements</span></span>  
 <span data-ttu-id="fdc5c-111">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="fdc5c-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fdc5c-112">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="fdc5c-112">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="fdc5c-113">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="fdc5c-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="fdc5c-114">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fdc5c-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fdc5c-115">참고자료</span><span class="sxs-lookup"><span data-stu-id="fdc5c-115">See also</span></span>
- [<span data-ttu-id="fdc5c-116">ICorProfilerCallback 인터페이스</span><span class="sxs-lookup"><span data-stu-id="fdc5c-116">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [<span data-ttu-id="fdc5c-117">ICorProfilerCallback2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="fdc5c-117">ICorProfilerCallback2 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-interface.md)
