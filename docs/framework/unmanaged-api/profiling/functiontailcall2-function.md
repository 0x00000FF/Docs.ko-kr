---
title: FunctionTailcall2 함수
ms.date: 03/30/2017
api_name:
- FunctionTailcall2
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- FunctionTailcall2
helpviewer_keywords:
- FunctionTailcall2 function [.NET Framework profiling]
ms.assetid: 249f9892-b5a9-41e1-b329-28a925904df6
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 8491f80c1b4340756c00b5540520bd76f0f583a0
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/06/2019
ms.locfileid: "57486999"
---
# <a name="functiontailcall2-function"></a>FunctionTailcall2 함수
현재 실행 중인 함수를 다른 함수에 대 한 마무리 호출이 수행 하려고 하는 스택 프레임에 대 한 정보를 제공 프로파일러에 알립니다.  
  
## <a name="syntax"></a>구문  
  
```  
void __stdcall FunctionTailcall2 (  
    [in] FunctionID         funcId,   
    [in] UINT_PTR           clientData,   
    [in] COR_PRF_FRAME_INFO func  
);  
```  
  
## <a name="parameters"></a>매개 변수  
 `funcId`  
 [in] 마무리 호출을 수행 하려고 하는 현재 실행 중인 함수의 식별자입니다.  
  
 `clientData`  
 [in] 프로파일러를 통해 이전에 지정 하는 매핑된 함수 식별자 [FunctionIDMapper](../../../../docs/framework/unmanaged-api/profiling/functionidmapper-function.md)를 마무리 호출을 수행 하려고 하는 현재 실행 중인 함수입니다.  
  
 `func`  
 [in] `COR_PRF_FRAME_INFO` 스택 프레임에 대 한 정보를 가리키는 값입니다.  
  
 프로파일러에 실행 엔진으로 다시 전달할 수 있는 불투명 핸들로이 처리 해야 합니다 [ICorProfilerInfo2::GetFunctionInfo2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getfunctioninfo2-method.md) 메서드.  
  
## <a name="remarks"></a>설명  
 마무리 호출의 대상 함수는 현재 스택 프레임을 사용 하 고 마무리 호출을 수행한 함수 호출자에 게 직접 반환 됩니다. 즉, 한 [FunctionLeave2](../../../../docs/framework/unmanaged-api/profiling/functionleave2-function.md) 마무리 호출의 대상이 되는 함수에 대 한 콜백 발행 되지 것입니다.  
  
 값을 `func` 후 매개 변수가 올바르지 않습니다는 `FunctionTailcall2` 함수 반환 값이 변경 될 수 있습니다 되거나 제거 되어 합니다.  
  
 `FunctionTailcall2` 함수 콜백을 구현 해야 합니다. 구현을 사용 해야 합니다 `__declspec`(`naked`) 저장소 클래스 특성입니다.  
  
 실행 엔진은이 함수를 호출 하기 전에 모든 레지스터를 저장 하지 않습니다.  
  
-   항목에는 부동 소수점 FPU (단위)에 포함 하 여 사용 하는 모든 레지스터를 저장 해야 합니다.  
  
-   종료 시 스택의 호출자에 의해 푸시된 모든 매개 변수에 팝 하 여 복원 해야 합니다.  
  
 구현의 `FunctionTailcall2` 가비지 수집 지연 될 수 있으므로 차단 하지 않아야 합니다. 구현 해야 스택의 가비지 컬렉션에 게 친숙 한 상태의 수 없을 수도 가비지 수집을 시도 하지 않습니다. 런타임이 될 때까지 차단 됩니다 가비지 수집을 시도 하는 경우 `FunctionTailcall2` 반환 합니다.  
  
 또한는 `FunctionTailcall2` 함수를 호출 해서는 안 관리 코드로 또는는 관리 되는 메모리를 할당 합니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.  
  
 **헤더:** CorProf.idl  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참고자료
- [FunctionEnter2 함수](../../../../docs/framework/unmanaged-api/profiling/functionenter2-function.md)
- [FunctionLeave2 함수](../../../../docs/framework/unmanaged-api/profiling/functionleave2-function.md)
- [SetEnterLeaveFunctionHooks2 메서드](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-setenterleavefunctionhooks2-method.md)
- [프로파일링 전역 정적 함수](../../../../docs/framework/unmanaged-api/profiling/profiling-global-static-functions.md)
