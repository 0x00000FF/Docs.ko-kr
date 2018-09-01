---
title: _AxlRSAKeyValueToPublicKeyToken 함수
ms.date: 03/30/2017
api_name:
- _AxlRSAKeyValueToPublicKeyToken
api_location:
- clr.dll
api_type:
- DLLExport
ms.assetid: d60f19fe-7bec-47ba-b60e-ba9ce66abf8c
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e09391af9b5d71cfa423b3bf1a2b307117d0dee1
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/01/2018
ms.locfileid: "43385889"
---
# <a name="axlrsakeyvaluetopublickeytoken-function"></a>\_AxlRSAKeyValueToPublicKeyToken 함수

모듈러스 및 지수를 강력한 이름 공개 키 토큰으로 변환합니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT _AxlRSAKeyValueToPublicKeyToken (  
    [in]  PCRYPT_DATA_BLOB pModulusBlob,  
    [in]  PCRYPT_DATA_BLOB pExponentBlob,  
    [out] LPWSTR           *ppwszPublicKeyToken  
);  
```  
  
### <a name="parameters"></a>매개 변수  
 `pModulusBlob`  
 [in] Base64로 인코딩된 모듈러스 blob (에서 \<모듈러스 > 요소).  참조 된 [CRYPTOAPI_BLOB](/windows/desktop/api/dpapi/ns-dpapi-_cryptoapi_blob) 구조입니다.  
  
 `pExponentBlob`  
 [in] Base64로 인코딩된 지 수 blob (에서 \<지 수 > 요소). 참조 된 [CRYPTOAPI_BLOB](/windows/desktop/api/dpapi/ns-dpapi-_cryptoapi_blob) 구조입니다.  
  
 `ppwszPublicKeyToken`  
 [out] 16진수로 인코딩된 공개 키 토큰을 받는 WCHAR *에 대한 포인터입니다.  
  
## <a name="return-value"></a>반환 값  
 함수가 정상적으로 실행되는 경우 `S_OK`입니다. 그러지 않으면 오류 코드가 반환됩니다.  
  
## <a name="see-also"></a>참고 항목  
 [Authenticode](../../../../docs/framework/unmanaged-api/authenticode/index.md)
