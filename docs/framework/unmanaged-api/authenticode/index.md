---
title: Authenticode(관리되지 않는 API 참조)
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: ''
ms.topic: reference
ms.assetid: 7e8cc303-6e77-4116-aa8b-7ea297a3a467
caps.latest.revision: 4
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 0b790064ef64ab44f3798a62d5dbf004f0f0bba6
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="authenticode-unmanaged-api-reference"></a>Authenticode(관리되지 않는 API 참조)
Authenticode XrML 라이센스 만들기 및 확인 모듈을 지원합니다.  
  
## <a name="in-this-section"></a>섹션 내용  
 [_AxlGetIssuerPublicKeyHash 함수](../../../../docs/framework/unmanaged-api/authenticode/axlgetissuerpublickeyhash-function.md)  
 지정한 인증서에 서명하는 데 사용되는 개인 키에 연결된 공개 키의 SHA-1 해시를 검색합니다.  
  
 [_AxlPublicKeyBlobToPublicKeyToken 함수](../../../../docs/framework/unmanaged-api/authenticode/axlpublickeyblobtopublickeytoken-function.md)  
 CSP PUBLICKEYBLOB 형식에서 강력한 이름 공개 키 토큰을 계산합니다.  
  
 [_AxlRSAKeyValueToPublicKeyToken 함수](../../../../docs/framework/unmanaged-api/authenticode/axlrsakeyvaluetopublickeytoken-function.md)  
 모듈러스 및 지수를 강력한 이름 공개 키 토큰으로 변환합니다.  
  
 [CertFreeAuthenticodeSignerInfo 함수](../../../../docs/framework/unmanaged-api/authenticode/certfreeauthenticodesignerinfo-function.md)  
 AXL_AUTHENTICODE_SIGNER_INFO 구조체에 할당된 리소스를 해제합니다.  
  
 [CertFreeAuthenticodeTimestamperInfo 함수](../../../../docs/framework/unmanaged-api/authenticode/certfreeauthenticodetimestamperinfo-function.md)  
 AXL_AUTHENTICODE_TIMESTAMPER_INFO 구조체에 할당된 리소스를 해제합니다.  
  
 [CertTimestampAuthenticodeLicense 함수](../../../../docs/framework/unmanaged-api/authenticode/certtimestampauthenticodelicense-function.md)  
 CertCreateAuthenticodeLicense에 의해 작성된 Authenticode XrML 라이선스에 타임스탬프를 적용합니다.  
  
 [CertVerifyAuthenticodeLicense 함수](../../../../docs/framework/unmanaged-api/authenticode/certverifyauthenticodelicense-function.md)  
 Authenticode XrML 라이선스의 유효성을 확인합니다.  
  
 [AXL_AUTHENTICODE_SIGNER_INFO 구조체](../../../../docs/framework/unmanaged-api/authenticode/axl-authenticode-signer-info-structure.md)  
 Authenticode 서명자 정보를 정의합니다.  
  
 [AXL_AUTHENTICODE_TIMESTAMPER_INFO 구조체](../../../../docs/framework/unmanaged-api/authenticode/axl-authenticode-timestamper-info-structure.md)  
 Authenticode 타임스탬퍼 정보를 정의합니다.  
  
## <a name="see-also"></a>참고 항목  
 [관리되지 않는 API 참조](../../../../docs/framework/unmanaged-api/index.md)
