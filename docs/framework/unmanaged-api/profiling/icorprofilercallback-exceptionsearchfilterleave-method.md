---
title: ICorProfilerCallback::ExceptionSearchFilterLeave 메서드
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.ExceptionSearchFilterLeave
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::ExceptionSearchFilterLeave
helpviewer_keywords:
- ICorProfilerCallback::ExceptionSearchFilterLeave method [.NET Framework profiling]
- ExceptionSearchFilterLeave method [.NET Framework profiling]
ms.assetid: c28a2a82-dd11-4385-843f-b509fb61753b
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 3fcbd225acd3f4f24311d08b04c971e2550b8ef5
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54533574"
---
# <a name="icorprofilercallbackexceptionsearchfilterleave-method"></a><span data-ttu-id="9a28b-102">ICorProfilerCallback::ExceptionSearchFilterLeave 메서드</span><span class="sxs-lookup"><span data-stu-id="9a28b-102">ICorProfilerCallback::ExceptionSearchFilterLeave Method</span></span>
<span data-ttu-id="9a28b-103">사용자 필터를 방금 실행을 마친 프로파일러에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="9a28b-103">Notifies the profiler that a user filter has just finished executing.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9a28b-104">구문</span><span class="sxs-lookup"><span data-stu-id="9a28b-104">Syntax</span></span>  
  
```  
HRESULT ExceptionSearchFilterLeave();  
```  
  
## <a name="requirements"></a><span data-ttu-id="9a28b-105">요구 사항</span><span class="sxs-lookup"><span data-stu-id="9a28b-105">Requirements</span></span>  
 <span data-ttu-id="9a28b-106">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="9a28b-106">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9a28b-107">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="9a28b-107">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="9a28b-108">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9a28b-108">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9a28b-109">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9a28b-109">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9a28b-110">참고자료</span><span class="sxs-lookup"><span data-stu-id="9a28b-110">See also</span></span>
- [<span data-ttu-id="9a28b-111">ICorProfilerCallback 인터페이스</span><span class="sxs-lookup"><span data-stu-id="9a28b-111">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [<span data-ttu-id="9a28b-112">ExceptionSearchFilterEnter 메서드</span><span class="sxs-lookup"><span data-stu-id="9a28b-112">ExceptionSearchFilterEnter Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionsearchfilterenter-method.md)
