---
title: "GetVersionFromProcess 함수"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: GetVersionFromProcess
api_location:
- mscoree.dll
- mscoreei.dll
api_type: DLLExport
f1_keywords: GetVersionFromProcess
helpviewer_keywords: GetVersionFromProcess function [.NET Framework hosting]
ms.assetid: a9f7f824-64a1-408d-8607-91c7f19d21fe
topic_type: apiref
caps.latest.revision: "20"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 3c73d12731a5c72b8c0e724f74ee0aa9ebddeee9
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="getversionfromprocess-function"></a>GetVersionFromProcess 함수
지정 된 프로세스 핸들과 연결 된 공용 언어 런타임 (CLR)의 버전 번호를 가져옵니다.  
  
 이 함수에 더 이상 사용 되지는 [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)]합니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT GetVersionFromProcess (  
    [in]  HANDLE  hProcess,   
    [out] LPWSTR  pVersion,   
    [in]  DWORD   cchBuffer,   
    [out] DWORD  *dwLength  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `hProcess`  
 [in] 프로세스에 대 한 핸들입니다.  
  
 `pVersion`  
 [out] 메서드가 완료 되 면 버전 번호 문자열을 포함 하는 버퍼입니다.  
  
 `cchBuffer`  
 [in] 버전 버퍼의 길이입니다.  
  
 `pdwLength`  
 [out] 버전 번호 문자열의 길이에 대 한 포인터입니다.  
  
## <a name="return-value"></a>반환 값  
 이 메서드는 다음 값 외에도 WinError.h에 정의 된 대로 표준 구성 요소 개체 모델 (COM) 오류 코드를 반환 합니다.  
  
|반환 코드|설명|  
|-----------------|-----------------|  
|S_OK|메서드가 완료되었습니다.|  
|E_INVALIDARG|`pVersion`null 및 `cchBuffer` null이 아니면 또는 그 반대의 경우도 마찬가지입니다.<br /><br /> 또는<br /><br /> `hProcess`프로세스에 대 한 유효한 핸들이 않습니다.<br /><br /> 또는<br /><br /> CLR 로드 되지 않습니다.|  
|ERROR_INSUFFICIENT_BUFFER|`cchBuffer`가 null 이거나 버전 문자열의 길이 보다 작습니다.|  
|E_NOTIMPL|이 메서드는 Microsoft Windows 95, Microsoft Windows 98, 또는 Microsoft Windows Millennium Edition 운영 체제에서 사용할 수 없습니다.|  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** MSCorEE.h  
  
 **라이브러리:** MSCorEE.dll  
  
 **.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [GetRequestedRuntimeInfo 함수](../../../../docs/framework/unmanaged-api/hosting/getrequestedruntimeinfo-function.md)  
 [GetRequestedRuntimeVersion 함수](../../../../docs/framework/unmanaged-api/hosting/getrequestedruntimeversion-function.md)  
 [사용 되지 않는 CLR 호스팅 함수](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
