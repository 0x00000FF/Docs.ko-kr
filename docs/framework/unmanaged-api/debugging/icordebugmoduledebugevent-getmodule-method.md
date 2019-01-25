---
title: ICorDebugModuleDebugEvent::GetModule Method
ms.date: 03/30/2017
ms.assetid: b1141c35-4253-4e34-b3e4-ed406a9dea4f
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 1ad20bdee5fee83b62d5da7f52c607835055616f
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54672333"
---
# <a name="icordebugmoduledebugeventgetmodule-method"></a>ICorDebugModuleDebugEvent::GetModule Method
방금 로드 또는 언로드된 병합된 모듈을 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT GetModule(  
   [out]ICorDebugModule **ppModule  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `ppModule`  
 [out] 방금 로드 또는 언로드된 병합 된 모듈을 나타내는 ICorDebugModule 개체의 주소에 대 한 포인터입니다.  
  
## <a name="remarks"></a>설명  
 호출할 수 있습니다 합니다 [GetEventKind](../../../../docs/framework/unmanaged-api/debugging/icordebugdebugevent-geteventkind-method.md) 모듈 로드 또는 언로드 되었는지 여부를 결정 하는 방법입니다.  
  
> [!NOTE]
>  이 메서드는 .NET 네이티브에서만 사용할 수 있습니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a>참고자료
- [ICorDebugModuleDebugEvent 인터페이스](../../../../docs/framework/unmanaged-api/debugging/icordebugmoduledebugevent-interface.md)
- [디버깅 인터페이스](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
