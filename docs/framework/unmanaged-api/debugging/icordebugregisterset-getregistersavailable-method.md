---
title: "ICorDebugRegisterSet::GetRegistersAvailable 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugRegisterSet.GetRegistersAvailable
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugRegisterSet::GetRegistersAvailable
helpviewer_keywords:
- ICorDebugRegisterSet::GetRegistersAvailable method [.NET Framework debugging]
- GetRegistersAvailable method, ICorDebugRegisterSet interface [.NET Framework debugging]
ms.assetid: 4ba08ffa-55a2-4662-9d6d-4738f1db60c9
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: aa4dd904b07aa2c9157e61e6968e96ef797ad3f9
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugregistersetgetregistersavailable-method"></a>ICorDebugRegisterSet::GetRegistersAvailable 메서드
비트 마스크를 가져옵니다가 있는 레지스터를 나타내는 [ICorDebugRegisterSet](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-interface.md) 현재 사용할 수 있습니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT GetRegistersAvailable (  
    [out] ULONG64   *pAvailable  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `pAvailable`  
 [out] 현재 사용할 수 있는 레지스터를 나타내는 비트 마스크입니다.  
  
## <a name="remarks"></a>설명  
 레지스터 주어진된 상황에 대 한 해당 값을 확인할 수 없는 경우 사용할 수 있습니다.  
  
 반환 된 마스크에는 각 레지스터에 대해 하나의 비트가 포함 (1 << 레지스터 인덱스). 레지스터를 사용할 수 있는 경우 비트 값이 1 또는 사용할 수 없는 경우 0입니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [ICorDebugRegisterSet 인터페이스](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-interface.md)  
 [ICorDebugRegisterSet2 인터페이스](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset2-interface.md)
