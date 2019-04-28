---
title: ICorDebugManagedCallback3 인터페이스
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback3
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback3
helpviewer_keywords:
- ICorDebugManagedCallback3 interface [.NET Framework debugging]
ms.assetid: a95389d3-cf2e-47a4-9805-61426acc6b65
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: acab49097059081540ec364d7f134d31432988a3
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61723266"
---
# <a name="icordebugmanagedcallback3-interface"></a>ICorDebugManagedCallback3 인터페이스
활성화된 사용자 지정 디버거 알림이 발생했음을 나타내는 콜백 메서드를 제공합니다.  
  
## <a name="methods"></a>메서드  
  
|메서드|설명|  
|------------|-----------------|  
|[CustomNotification 메서드](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback3-customnotification-method.md)|설정 된 사용자 지정 디버거 알림이 발생을 나타냅니다.|  
  
## <a name="remarks"></a>설명  
 이 인터페이스는 논리적으로 확장 합니다 [ICorDebugManagedCallback](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md) 하 고 [ICorDebugManagedCallback2](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-interface.md) 인터페이스입니다.  
  
> [!NOTE]
>  이 인터페이스는 크로스 시스템 또는 크로스 프로세스 원격 호출을 지원하지 않습니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>참고자료

- [ICorDebugManagedCallback 인터페이스](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
- [ICorDebugManagedCallback2 인터페이스](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-interface.md)
- [디버깅 인터페이스](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [디버깅](../../../../docs/framework/unmanaged-api/debugging/index.md)
