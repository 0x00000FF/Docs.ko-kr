---
title: ICorDebugMDA::GetName 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugMDA.GetName
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugMDA::GetName
helpviewer_keywords:
- ICorDebugMDA::GetName method [.NET Framework debugging]
- GetName method, ICorDebugMDA interface [.NET Framework debugging]
ms.assetid: 885bf5e8-00b7-4cd7-9d8d-e720d47918c4
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 5f62fa23d30a93f863cb2be0fa060bd2eba8dca1
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59141738"
---
# <a name="icordebugmdagetname-method"></a>ICorDebugMDA::GetName 메서드
관리 디버깅 도우미 (MDA)의 이름을 나타내는 문자열을 가져옵니다 [ICorDebugMDA](../../../../docs/framework/unmanaged-api/debugging/icordebugmda-interface.md)합니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT GetName (  
    [in] ULONG32   cchName,  
    [out] ULONG32  *pcchName,  
    [out, size_is(cchName), length_is(*pcchName)]  
        WCHAR      szName[]  
);  
```  
  
## <a name="parameters"></a>매개 변수  
 `cchName`  
 [in] `szName` 배열의 크기입니다.  
  
 `pcchName`  
 [out] 이름의 길이에 대 한 포인터입니다.  
  
 `szName`  
 [out] 이름을 저장 하는 배열입니다.  
  
## <a name="remarks"></a>설명  
 MDA 이름은 고유 값입니다. `GetName` 메서드는 XML 스트림을 가져오는 스키마를 기반으로 하는 스트림의 이름을 추출 하는 편리한 성능 대체 합니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참고자료

- [ICorDebugMDA 인터페이스](../../../../docs/framework/unmanaged-api/debugging/icordebugmda-interface.md)
- [관리 디버깅 도우미를 사용하여 오류 진단](../../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)
