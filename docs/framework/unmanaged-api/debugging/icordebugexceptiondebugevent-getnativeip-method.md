---
title: ICorDebugExceptionDebugEvent::GetNativeIP 메서드
ms.date: 03/30/2017
ms.assetid: 12e6a262-d9ac-49b8-9b80-1e653a2a3819
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3a3fa4ad73847d172ee8e1c7d239bfc00fe11638
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/10/2019
ms.locfileid: "67754339"
---
# <a name="icordebugexceptiondebugeventgetnativeip-method"></a>ICorDebugExceptionDebugEvent::GetNativeIP 메서드
이 예외 디버그 이벤트에 대한 네이티브 명령 포인터를 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT GetNativeIP(  
   [out]CORDB_ADDRESS *pIP  
);  
```  
  
## <a name="parameters"></a>매개 변수  
 `pIP`  
 [out] 이 예외 디버그 이벤트의 명령 포인터에 대한 포인터입니다. 자세한 내용은 설명 부분을 참조하세요.  
  
## <a name="remarks"></a>설명  
 이 명령 포인터의 의미는 다음 표와 같이 이벤트 유형에 따라 달라집니다.  
  
|이벤트 유형|`pStackPointer` 값의 의미|  
|----------------|--------------------------------------|  
|[MANAGED_EXCEPTION_FIRST_CHANCE](../../../../docs/framework/unmanaged-api/debugging/cordebugrecordformat-enumeration.md)|오류가 발생한 명령의 주소입니다.|  
|[MANAGED_EXCEPTION_USER_FIRST_CHANCE](../../../../docs/framework/unmanaged-api/debugging/cordebugrecordformat-enumeration.md)|프레임의 코드 주소에 나타난 합니다 [GetStackPointer](../../../../docs/framework/unmanaged-api/debugging/icordebugexceptiondebugevent-getstackpointer-method.md) 메서드는 실행이 다시 시작 하는 경우 예외가 발생 합니다. 예외로 인해 `try/catch/finally` 절의 catch 블록과 같은 다른 코드가 이 프레임에서 실행되거나 실행되지 않을 수 있습니다.|  
|[MANAGED_EXCEPTION_CATCH_HANDLER_FOUND](../../../../docs/framework/unmanaged-api/debugging/cordebugrecordformat-enumeration.md)|되는 코드 주소 `catch` 처리기 실행이 표시 된 프레임에서 시작 합니다 [GetStackPointer](../../../../docs/framework/unmanaged-api/debugging/icordebugexceptiondebugevent-getstackpointer-method.md) 메서드.|  
|[MANAGED_EXCEPTION_UNHANDLED](../../../../docs/framework/unmanaged-api/debugging/cordebugrecordformat-enumeration.md)|`pIP`가 0입니다.|  
  
 이벤트 유형은에서 사용할 수는 [icordebugdebugevent:: Geteventkind](../../../../docs/framework/unmanaged-api/debugging/icordebugdebugevent-geteventkind-method.md) 메서드.  
  
> [!NOTE]
>  이 메서드는 .NET 네이티브에서만 사용할 수 있습니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a>참고자료

- [ICorDebugExceptionDebugEvent 인터페이스](../../../../docs/framework/unmanaged-api/debugging/icordebugexceptiondebugevent-interface.md)
- [디버깅 인터페이스](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
