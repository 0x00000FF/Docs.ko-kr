---
title: ICorDebugAssembly Interface1
ms.date: 03/30/2017
api_name:
- ICorDebugAssembly
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugAssembly
helpviewer_keywords:
- ICorDebugAssembly interface [.NET Framework debugging]
ms.assetid: 9d657a28-6984-4c5e-8a54-89d20080baff
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 88134fb7854091bb60e8084a6d776bdec922c7e1
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="icordebugassembly-interface1"></a>ICorDebugAssembly Interface1
어셈블리를 나타냅니다.  
  
## <a name="methods"></a>메서드  
  
|메서드|설명|  
|------------|-----------------|  
|[EnumerateModules 메서드](../../../../docs/framework/unmanaged-api/debugging/icordebugassembly-enumeratemodules-method.md)|어셈블리에 포함 된 모듈에 대 한 열거자를 가져옵니다.|  
|[GetAppDomain 메서드](../../../../docs/framework/unmanaged-api/debugging/icordebugassembly-getappdomain-method.md)|이 포함 하는 응용 프로그램 도메인에 대 한 인터페이스 포인터를 가져옵니다 `ICorDebugAssembly` 인스턴스.|  
|[GetCodeBase 메서드](../../../../docs/framework/unmanaged-api/debugging/icordebugassembly-getcodebase-method.md)|현재 버전의.NET Framework에서 구현 되지 않습니다.|  
|[GetName 메서드](../../../../docs/framework/unmanaged-api/debugging/icordebugassembly-getname-method.md)|어셈블리의 이름을 가져옵니다.|  
|[GetProcess 메서드](../../../../docs/framework/unmanaged-api/debugging/icordebugassembly-getprocess-method.md)|어셈블리 실행 되 고 있는 ICorDebugProcess 인스턴스를 가져옵니다.|  
  
## <a name="remarks"></a>설명  
  
> [!NOTE]
>  이 인터페이스는 크로스 시스템 또는 크로스 프로세스 원격 호출을 지원하지 않습니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [디버깅 인터페이스](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
