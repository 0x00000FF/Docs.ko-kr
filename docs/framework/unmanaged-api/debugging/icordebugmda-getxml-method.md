---
title: "ICorDebugMDA::GetXML 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugMDA.GetXML
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugMDA::GetXML
helpviewer_keywords:
- ICorDebugMDA::GetXML method [.NET Framework debugging]
- GetXML method [.NET Framework debugging]
ms.assetid: 29746b24-3766-4255-8813-0426c45e73e5
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: c9f1ad3ac70f001feebb0b28eec13cb45ca2c866
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugmdagetxml-method"></a>ICorDebugMDA::GetXML 메서드
연결 된 관리 디버깅 도우미 (MDA)으로 표시 된 전체 XML 스트림을 가져옵니다 [ICorDebugMDA](../../../../docs/framework/unmanaged-api/debugging/icordebugmda-interface.md)합니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT GetXML (  
    [in] ULONG32   cchName,  
    [out] ULONG32  *pcchName,  
    [out, size_is(cchName), length_is(*pcchName)]  
        WCHAR      szName[]  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `cchName`  
 [in] `szName` 배열의 크기입니다.  
  
 `pcchName`  
 [out] XML 스트림의 길이에 대 한 포인터입니다.  
  
 `szName`  
 [out] XML 스트림을 저장할 배열입니다. 배열이 비어 있을 수 있습니다.  
  
## <a name="remarks"></a>설명  
 `GetXML` 메서드는 연결 된 XML 스트림의 크기에 따라 성능에 영향을 줄 수 있습니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [ICorDebugMDA 인터페이스](../../../../docs/framework/unmanaged-api/debugging/icordebugmda-interface.md)  
 [관리 디버깅 도우미를 사용하여 오류 진단](../../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)
