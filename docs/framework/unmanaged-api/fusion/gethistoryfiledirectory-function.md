---
title: GetHistoryFileDirectory 함수
ms.date: 03/30/2017
api_name:
- GetHistoryFileDirectory
api_location:
- fusion.dll
api_type:
- DLLExport
f1_keywords:
- GetHistoryFileDirectory
helpviewer_keywords:
- GetHistoryFileDirectory function [.NET Framework fusion]
ms.assetid: 93232222-926e-42ac-b85d-8a6d33977672
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: defe69e8d205a0c66f806e4ffacb09d5a9f63309
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54552114"
---
# <a name="gethistoryfiledirectory-function"></a>GetHistoryFileDirectory 함수
응용 프로그램 기록 디렉터리의 경로 검색합니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT GetHistoryFileDirectory (  
    [in]      LPWSTR      wzDir,  
    [in,out]  LPCWSTR  *pdwsize,  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `wzDir`  
 [out] 응용 프로그램 기록 디렉터리 경로 저장할 버퍼입니다.  
  
 `pdwSize`  
 [out에서] 버퍼의 길이입니다.  
  
## <a name="return-value"></a>반환 값  
 이 메서드는 다음 값 외에도 WinError.h 파일에 정의 된 대로 표준 COM 오류 코드를 반환 합니다.  
  
|반환 코드|설명|  
|-----------------|-----------------|  
|S_OK|메서드가 완료되었습니다.|  
|E_INVALIDARG|`wzDir` 또는 `pdwSize` 는 null 또는 버전 문자열이 잘못 되었습니다.|  
  
## <a name="remarks"></a>설명  
 성공적으로 완료 되는 `pdwSize` 경로 문자열의 길이 인수를 설정 합니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.  
  
 **헤더:** Fusion.h  
  
 **라이브러리:** Fusion.dll 및 Mscorwks.dll 합니다. 올바른 버전의.NET Framework 대상 지정 하는 데 Mscorwks.dll 대신 Fusion.dll를 사용 합니다.  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]  
  
## <a name="see-also"></a>참고자료
- [CreateHistoryReader 함수](../../../../docs/framework/unmanaged-api/fusion/createhistoryreader-function.md)
- [NukeDownloadedCache 함수](../../../../docs/framework/unmanaged-api/fusion/nukedownloadedcache-function.md)
- [Fusion 전역 정적 함수](../../../../docs/framework/unmanaged-api/fusion/fusion-global-static-functions.md)
