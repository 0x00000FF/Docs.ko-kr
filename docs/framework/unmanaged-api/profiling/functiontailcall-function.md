---
title: FunctionTailcall 함수
ms.date: 03/30/2017
api_name:
- FunctionTailcall
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- FunctionTailcall
helpviewer_keywords:
- FunctionTailcall function [.NET Framework profiling]
ms.assetid: 66347e03-9a97-41e8-8f9d-89b80803f7b5
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 656f2498c7dd9ba165ab6759d8ca3b26e0d7c93f
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59207047"
---
# <a name="functiontailcall-function"></a>FunctionTailcall 함수
현재 실행 중인 함수에 대 한 다른 함수에 대 한 마무리 호출이 수행 하는 프로파일러에 알립니다.  
  
> [!NOTE]
>  `FunctionTailcall` 함수는.NET Framework 버전 2.0에서에서 사용 되지 않습니다. 계속 작동 하지만 성능이 저하 됩니다. 사용 된 [FunctionTailcall2](../../../../docs/framework/unmanaged-api/profiling/functiontailcall2-function.md) 함수를 대신 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
void __stdcall FunctionTailcall (  
    [in] FunctionID funcID  
);  
```  
  
## <a name="parameters"></a>매개 변수  
 `funcID`  
 [in] 마무리 호출을 수행 하려고 하는 현재 실행 중인 함수의 식별자입니다.  
  
## <a name="remarks"></a>설명  
 마무리 호출의 대상 함수는 현재 스택 프레임을 사용 하 고 마무리 호출을 수행한 함수 호출자에 게 직접 반환 됩니다. 즉, 한 [FunctionLeave](../../../../docs/framework/unmanaged-api/profiling/functionleave-function.md) 마무리 호출의 대상이 되는 함수에 대 한 콜백 발행 되지 것입니다.  
  
 `FunctionTailcall` 함수 콜백을 구현 해야 합니다. 구현을 사용 해야 합니다 `__declspec`(`naked`) 저장소 클래스 특성입니다.  
  
 실행 엔진은이 함수를 호출 하기 전에 모든 레지스터를 저장 하지 않습니다.  
  
-   항목에는 부동 소수점 FPU (단위)에 포함 하 여 사용 하는 모든 레지스터를 저장 해야 합니다.  
  
-   종료 시 스택의 호출자에 의해 푸시된 모든 매개 변수에 팝 하 여 복원 해야 합니다.  
  
 구현의 `FunctionTailcall` 가비지 수집 지연 될 수 있으므로 차단 하지 않아야 합니다. 구현 해야 스택의 가비지 컬렉션에 게 친숙 한 상태의 수 없을 수도 가비지 수집을 시도 하지 않습니다. 런타임이 될 때까지 차단 됩니다 가비지 수집을 시도 하는 경우 `FunctionTailcall` 반환 합니다.  
  
 또한는 `FunctionTailcall` 함수를 호출 해서는 안 관리 코드로 또는는 관리 되는 메모리를 할당 합니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.  
  
 **헤더:** CorProf.idl  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET framework 버전:** 1.1, 1.0  
  
## <a name="see-also"></a>참고자료

- [FunctionEnter2 함수](../../../../docs/framework/unmanaged-api/profiling/functionenter2-function.md)
- [FunctionLeave2 함수](../../../../docs/framework/unmanaged-api/profiling/functionleave2-function.md)
- [SetEnterLeaveFunctionHooks2 메서드](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-setenterleavefunctionhooks2-method.md)
- [프로파일링 전역 정적 함수](../../../../docs/framework/unmanaged-api/profiling/profiling-global-static-functions.md)
