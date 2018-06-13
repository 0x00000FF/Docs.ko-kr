---
title: ICLRDataTarget::Request 메서드
ms.date: 03/30/2017
api_name:
- ICLRDataTarget.Request
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICLRDataTarget::Request
helpviewer_keywords:
- ICLRDataTarget::Request method [.NET Framework debugging]
- Request method [.NET Framework debugging]
ms.assetid: 4723bd1c-eddb-4ed2-897a-010024a47e01
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: dc79277c75118b11766e66137284bd5655eed091
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33405374"
---
# <a name="iclrdatatargetrequest-method"></a>ICLRDataTarget::Request 메서드
구현에 의해 정의 된 대로 작업을 요청 하는 공용 언어 런타임 (CLR) 데이터 액세스 서비스에서 호출 됩니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT Request (  
    [in] ULONG32            reqCode,  
    [in] ULONG32            inBufferSize,  
    [in, size_is(inBufferSize)]   
        BYTE                *inBuffer,  
    [in] ULONG32            outBufferSize,  
    [out, size_is(outBufferSize)]   
        BYTE                *outBuffer  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `reqCode`  
 [in] 사용자 정의입니다.  
  
 `inBufferSize`  
 [in] 들어오는 요청에 사용 되는 입력된 버퍼의 크기입니다.  
  
 `inBuffer`  
 [in] 요청을 포함 하는 버퍼입니다.  
  
 `outBufferSize`  
 [in] 응답에 사용 되는 출력 버퍼의 크기입니다.  
  
 `outBuffer`  
 [out] 응답을 포함 하는 버퍼입니다.  
  
## <a name="remarks"></a>설명  
 `Request` 메서드 지정 되지 않은 사용자 지정 작업 추가 용이 하 게 합니다. 즉,이 메서드는 인터페이스 정의 수정할 필요 없이 확장성을 제공 합니다.  
  
 이 메서드는 디버깅 응용 프로그램의 작성자가 구현합니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** ClrData.idl, ClrData.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [ICLRDataTarget 인터페이스](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-interface.md)
