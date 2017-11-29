---
title: "ICLRDataTarget3::GetExceptionThreadID 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs: cpp
api_name: ICLRDataTarget3.GetExceptionThreadID
api_location: mscordbi.dll
api_type: COM
ms.assetid: 307d6ac7-4a86-45f3-999d-6b47004a68f2
topic_type: apiref
caps.latest.revision: "3"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: f05d264d4bf55de930a07eda6bf369570c8b7fa8
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="iclrdatatarget3getexceptionthreadid-method"></a>ICLRDataTarget3::GetExceptionThreadID 메서드
CLR(공용 언어 런타임) 데이터 액세스 서비스에 의해 호출되어 예외를 throw한 스레드의 ID를 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT GetExceptionThreadID(  
    [out] ULONG32* threadID  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `threadID`  
 [out] 예외를 throw한 스레드의 ID입니다.  
  
## <a name="return-value"></a>반환 값  
 반환 값은 성공 시 `S_OK`이고 실패 시에는 오류 `HRESULT` 코드입니다. `HRESULT` 코드는 다음을 비롯한 여러 항목을 포함할 수 있습니다.  
  
|반환 코드|설명|  
|-----------------|-----------------|  
|`S_OK`|메서드가 정상적으로 실행되었습니다.|  
|`HRESULT_FROM_WIN32(ERROR_NOT_FOUND)`|예외의 유효한 스레드 ID를 찾을 수 없습니다.|  
  
## <a name="remarks"></a>설명  
 이 메서드는 디버깅 응용 프로그램의 작성자가 구현합니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** ClrData.idl, ClrData.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET framework 버전:**[!INCLUDE[v451_update](../../../../includes/v451-update-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [ICLRDataTarget3 인터페이스](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget3-interface.md)  
 [GetExceptionContextRecord 메서드](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget3-getexceptioncontextrecord-method.md)  
 [GetExceptionRecord 메서드](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget3-getexceptionrecord-method.md)
