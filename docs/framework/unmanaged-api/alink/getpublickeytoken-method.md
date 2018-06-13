---
title: GetPublicKeyToken 메서드
ms.date: 03/30/2017
api_name:
- IALink2.GetPublicKeyToken
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- GetPublicKeyToken
helpviewer_keywords:
- GetPublicKeyToken method
ms.assetid: 4a16374c-94b0-47b0-9fed-88c2b0cdccd4
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 94a473d00110c07615ccdfc98bb8944e40dc30e3
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33405475"
---
# <a name="getpublickeytoken-method"></a>GetPublicKeyToken 메서드
지정 된 키 파일 또는 키 컨테이너에 대 한 공개 키 토큰을 검색합니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT GetPublicKeyToken(  
    LPCWSTR pszKeyFile,  
    LPCWSTR pszKeyContainer,  
    void* pvPublicKeyToken,  
    DWORD* pcbPublicKeyToken  
) PURE;  
```  
  
#### <a name="parameters"></a>매개 변수  
 `pszKeyFile`  
 키의 파일 이름입니다.  
  
 `pszKeyContainer`  
 키 컨테이너의 이름입니다.  
  
 `pvPublicKeyToken`  
 키 토큰이 저장 됩니다. 여기서는 주소입니다.  
  
 `pcbPublicKeyToken`  
 으로 표시 되는 버퍼를 바이트 단위로 크기를 지정 `pvPublicKeyToken`합니다. 반환 되 면 실제 사용 되는 바이트 수를 포함 합니다.  
  
## <a name="return-value"></a>반환 값  
 메서드가 성공 하면 S_OK를 반환 합니다.  
  
## <a name="requirements"></a>요구 사항  
 Alink.h가 필요합니다.  
  
## <a name="see-also"></a>참고 항목  
 [IALink2 인터페이스](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)  
 [IALink 인터페이스](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)  
 [ALink API](../../../../docs/framework/unmanaged-api/alink/index.md)
