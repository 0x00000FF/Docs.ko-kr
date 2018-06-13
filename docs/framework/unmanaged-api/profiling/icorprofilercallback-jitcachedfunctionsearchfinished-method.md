---
title: ICorProfilerCallback::JITCachedFunctionSearchFinished 메서드
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.JITCachedFunctionSearchFinished
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::JITCachedFunctionSearchFinished
helpviewer_keywords:
- JITCachedFunctionSearchFinished method [.NET Framework profiling]
- ICorProfilerCallback::JITCachedFunctionSearchFinished method [.NET Framework profiling]
ms.assetid: 3c325c82-cddd-4b00-b3da-e450c36abf62
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 89c7b0fe0f3ade3f57aa50b100bc9b4ecc904a17
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33451999"
---
# <a name="icorprofilercallbackjitcachedfunctionsearchfinished-method"></a>ICorProfilerCallback::JITCachedFunctionSearchFinished 메서드
네이티브 이미지 생성기 (NGen.exe)를 사용 하 여 이전에 컴파일된 함수에 대 한 검색을 완료 되었음을 프로파일러에 알립니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT JITCachedFunctionSearchFinished(  
    [in] FunctionID        functionId,  
    [in] COR_PRF_JIT_CACHE result);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `functionId`  
 [in] 검색이 수행 되었을 함수의 ID입니다.  
  
 `result`  
 [in] 값은 [COR_PRF_JIT_CACHE](../../../../docs/framework/unmanaged-api/profiling/cor-prf-jit-cache-enumeration.md) 검색 결과 나타내는 열거형입니다.  
  
## <a name="remarks"></a>설명  
 .NET Framework 버전 2.0에에서는 [icorprofilercallback:: Jitcachedfunctionsearchstarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitcachedfunctionsearchstarted-method.md) 및 `JITCachedFunctionSearchFinished` 보통 NGen 이미지의 모든 함수에 대 한 콜백이 수행 될 되지 않습니다. 만 NGen 이미지의 프로파일러에 대 한 액세스에 최적화 된 이미지의 모든 기능에 대 한 콜백을 생성 됩니다. 그러나 추가 오버 헤드로 인해 프로파일러를 요청 해야 NGen 이미지 프로파일러 액세스에 최적화 된 이러한 콜백 함수를 컴파일된-just-in-time JIT ()를 사용 하려는 경우에 합니다. 그렇지 않으면 프로파일러 함수 정보를 수집 하기 위한 지연 전략을 사용 해야 합니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** CorProf.idl, CorProf.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [ICorProfilerCallback 인터페이스](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
