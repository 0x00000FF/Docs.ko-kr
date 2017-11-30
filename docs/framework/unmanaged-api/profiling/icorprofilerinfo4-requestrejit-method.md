---
title: "ICorProfilerInfo4::RequestReJIT 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerInfo4.RequestReJIT
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerInfo4::RequestReJIT
helpviewer_keywords:
- RequestReJIT method, ICorProfilerInfo4 interface [.NET Framework profiling]
- ICorProfilerInfo4::RequestReJIT method [.NET Framework profiling]
ms.assetid: 781ed736-f30c-4816-920e-3552e36542c6
topic_type: apiref
caps.latest.revision: "10"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: d62dbb2829480e8972d1d4966673ba8eb58f1831
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="icorprofilerinfo4requestrejit-method"></a>ICorProfilerInfo4::RequestReJIT 메서드
지정된 함수의 모든 인스턴스에 대한 JIT 다시 컴파일을 요청합니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT RequestReJIT (  
   [in] ULONG    cFunctions,  
   [in, size_is(cFunctions)]  ModuleID    moduleIds[],  
   [in, size_is(cFunctions)]  mdMethodDef methodIds[]);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `cFunctions`  
 [in] 다시 컴파일할 함수 개수입니다.  
  
 `moduleIds`  
 [in] 다시 컴파일할 함수를 식별하는 (`module`, `methodDef`) 쌍의 `moduleId` 부분을 지정합니다.  
  
 `methodIds`  
 [in] 다시 컴파일할 함수를 식별하는 (`module`, `methodDef`) 쌍의 `methodId` 부분을 지정합니다.  
  
## <a name="return-value"></a>반환 값  
 이 메서드는 다음과 같은 특정 HRESULT뿐만 아니라 메서드 오류를 나타내는 HRESULT 오류도 반환합니다.  
  
|HRESULT|설명|  
|-------------|-----------------|  
|S_OK|JIT 다시 컴파일을 위해 모든 메서드에 표시하려고 했습니다. 프로파일러를 구현 해야 합니다는 [icorprofilercallback4:: Rejiterror](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-rejiterror-method.md) 메서드를 결정 하는 메서드와 JIT 다시 컴파일을 위해 성공적으로 표시 합니다.|  
|CORPROF_E_CALLBACK4_REQUIRED|프로파일러를 구현 해야 합니다는 [ICorProfilerCallback4](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-interface.md) 지원 되는 데이 호출에 대 한 인터페이스입니다.|  
|CORPROF_E_REJIT_NOT_ENABLED|JIT 다시 컴파일이 사용하도록 설정되지 않았습니다. 사용 하 여 초기화 하는 동안 JIT 다시 컴파일을 사용 하도록 설정 해야 하면는 [icorprofilerinfo:: Seteventmask](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-seteventmask-method.md) 설정 하는 메서드는 `COR_PRF_ENABLE_REJIT` 플래그입니다.|  
|E_INVALIDARG|`cFunctions`가 0이거나 `moduleIds` 또는 `methodIds`가 `NULL`입니다.|  
|||  
|E_OUTOFMEMORY|메모리 부족 때문에 CLR에서 요청을 완료하지 못했습니다.|  
  
## <a name="remarks"></a>설명  
 `RequestReJIT`를 호출하여 런타임에서 지정된 함수 집합을 다시 컴파일하도록 합니다. 코드 프로파일러에서 사용할 수는 [ICorProfilerFunctionControl](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctioncontrol-interface.md) 는 함수가 다시 컴파일될 때 생성 되는 코드를 조정 하는 인터페이스입니다. 이 기능은 현재 실행 중인 함수에는 영향을 주지 않고 이후 함수 호출에만 영향을 줍니다. 지정된 함수가 이전에 JIT 다시 컴파일된 경우 다시 컴파일 요청은 함수를 되돌리고 다시 컴파일하는 것과 같습니다. 되돌리는 기능을 유지하기 위해 JIT 컴파일러는 함수의 원래 버전은 컴파일할 때 인라인 처리 결정을 위해 호출 수신자의 원래 버전만 고려합니다. JIT 컴파일러는 함수를 다시 컴파일할 때 인라인 처리를 위해 호출 수신자의 현재 버전(다시 컴파일된 버전 또는 원래 버전)을 고려합니다.  
  
 프로파일러는 일반적으로 프로파일러가 하나 이상의 메서드를 계측하도록 요청하는 사용자 입력에 대한 응답으로 `RequestReJIT`를 호출합니다. `RequestReJIT`는 일반적으로 해당 작업의 일부를 수행하기 위해 런타임을 일시 중단하며, 가비지 수집을 트리거할 수 있습니다. 따라서 프로파일러는 현재 프로파일러 콜백을 실행 중인 CLR에서 만든 스레드가 아니라 이전에 만든 스레드에서 `RequestReJIT`를 호출해야 합니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** CorProf.idl, CorProf.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET framework 버전:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [ICorProfilerInfo4 인터페이스](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-interface.md)  
 [프로 파일링 인터페이스](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)  
 [프로파일링](../../../../docs/framework/unmanaged-api/profiling/index.md)
