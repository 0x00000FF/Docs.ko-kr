---
title: ICorDebugThread2 인터페이스
ms.date: 03/30/2017
api_name:
- ICorDebugThread2
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread2
helpviewer_keywords:
- ICorDebugThread2 interface [.NET Framework debugging]
ms.assetid: 678f89f9-cce7-46d1-af87-5e989abaa93c
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 82648714c375998e9daa1bb59cd9ebd9802b5794
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59153935"
---
# <a name="icordebugthread2-interface"></a>ICorDebugThread2 인터페이스
ICorDebugThread 인터페이스를 논리적으로 확장으로 사용 됩니다.  
  
## <a name="methods"></a>메서드  
  
|메서드|설명|  
|------------|-----------------|  
|[GetActiveFunctions 메서드](../../../../docs/framework/unmanaged-api/debugging/icordebugthread2-getactivefunctions-method.md)|COR_ACTIVE_FUNCTION 인스턴스 스레드 프레임의 현재 함수에 대 한 데이터를 포함 하는 배열을 가져옵니다.|  
|[GetConnectionID 메서드](../../../../docs/framework/unmanaged-api/debugging/icordebugthread2-getconnectionid-method.md)|이 대 한 연결 식별자를 가져옵니다 `ICorDebugThread2`합니다.|  
|[GetTaskID 메서드](../../../../docs/framework/unmanaged-api/debugging/icordebugthread2-gettaskid-method.md)|이 대 한 작업 식별자를 가져옵니다 `ICorDebugThread2`합니다.|  
|[GetVolatileOSThreadID 메서드](../../../../docs/framework/unmanaged-api/debugging/icordebugthread2-getvolatileosthreadid-method.md)|이 대 한 운영 체제 스레드 식별자를 가져옵니다 `ICorDebugThread2`합니다.|  
|[InterceptCurrentException 메서드](../../../../docs/framework/unmanaged-api/debugging/icordebugthread2-interceptcurrentexception-method.md)|디버거에서를 스레드에서 현재 예외를 가로챌 수 있습니다.|  
  
## <a name="remarks"></a>설명  
  
> [!NOTE]
>  이 인터페이스는 크로스 시스템 또는 크로스 프로세스 원격 호출을 지원하지 않습니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참고자료

- [디버깅 인터페이스](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
