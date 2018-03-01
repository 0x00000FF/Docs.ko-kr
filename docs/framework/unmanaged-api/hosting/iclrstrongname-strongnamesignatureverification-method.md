---
title: "ICLRStrongName::StrongNameSignatureVerification 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- ICLRStrongName.StrongNameSignatureVerification
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRStrongName::StrongNameSignatureVerification
helpviewer_keywords:
- ICLRStrongName::StrongNameSignatureVerification method [.NET Framework hosting]
- StrongNameSignatureVerification method, ICLRStrongName interface [.NET Framework hosting]
ms.assetid: 734dc4d1-0a76-4736-b5ac-cb4253b3dd49
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: b1d8cb0ac6c671dae6ca5985e4082e2d3e71d89e
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="iclrstrongnamestrongnamesignatureverification-method"></a>ICLRStrongName::StrongNameSignatureVerification 메서드
어셈블리 매니페스트에 제공 된 경로의 강한 이름 서명을 확인 하도록 지정된 된 플래그에 따라 포함 되는지 여부를 나타내는 값을 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT StrongNameSignatureVerification (  
    [in]  LPCWSTR   wszFilePath,  
    [in]  DWORD     dwInFlags,  
    [out] DWORD     *pdwOutFlags  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `wszFilePath`  
 [in] 이식 가능한 실행 (.dll 또는.exe) 파일에 어셈블리 확인에 대 한 경로입니다.  
  
 `dwInFlags`  
 [in] 확인 동작을 수정 하는 플래그입니다. 다음 값이 지원 됩니다.  
  
-   `SN_INFLAG_FORCE_VER`(0x00000001)-강제로 레지스트리 설정을 재정의 해야 하는 경우에 확인 합니다.  
  
-   `SN_INFLAG_INSTALL`(0x00000002)-매니페스트를 확인 하는 처음으로 임을 지정 합니다.  
  
-   `SN_INFLAG_ADMIN_ACCESS`(0x00000004)-캐시 관리 권한이 있는 사용자 에게만 액세스를 사용할 수 있음을 지정 합니다.  
  
-   `SN_INFLAG_USER_ACCESS`(0x00000008)-어셈블리 현재 사용자에만 액세스할 수 있는지를 지정 합니다.  
  
-   `SN_INFLAG_ALL_ACCESS`(0x00000010)-캐시의 액세스 제한이 않음을 지정 합니다.  
  
-   `SN_INFLAG_RUNTIME`(0x80000000)-내부 디버깅 하기 위해 예약 되어 있습니다.  
  
 `pdwOutFlags`  
 [out] 강력한 이름 서명을 확인 하는지 여부를 나타내는 플래그입니다. 다음 값이 지원 됩니다.  
  
-   `SN_OUTFLAG_WAS_VERIFIED`이 값은로 설정 (0x00000001)- `false` 확인 레지스트리 설정으로 인해 성공 했는지를 지정 하려면.  
  
## <a name="return-value"></a>반환 값  
 `S_OK`메서드가 성공적으로 완료 하는 경우 그렇지 않으면 실패를 나타내는 HRESULT 값 (참조 [일반적인 HRESULT 값](http://go.microsoft.com/fwlink/?LinkId=213878) 목록에 대 한).  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** MetaHost.h  
  
 **라이브러리:** MSCorEE.dll에 리소스로 포함  
  
 **.NET framework 버전:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [StrongNameSignatureVerificationEx 메서드](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignatureverificationex-method.md)  
 [ICLRStrongName 인터페이스](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
