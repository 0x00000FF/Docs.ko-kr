---
title: IMetaDataAssemblyImport::EnumAssemblyRefs 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataAssemblyImport.EnumAssemblyRefs
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyImport::EnumAssemblyRefs
helpviewer_keywords:
- IMetaDataAssemblyImport::EnumAssemblyRefs method [.NET Framework metadata]
- EnumAssemblyRefs method [.NET Framework metadata]
ms.assetid: 8844d0dd-730e-4592-8a7b-c1462d312c70
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 7d10fb391953e924feb553ae4516fb7674345ed3
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54592016"
---
# <a name="imetadataassemblyimportenumassemblyrefs-method"></a>IMetaDataAssemblyImport::EnumAssemblyRefs 메서드
열거는 `mdAssemblyRef` 어셈블리 매니페스트에 정의 된 인스턴스.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT EnumAssemblyRefs (  
    [in, out] HCORENUM        *phEnum,   
    [out]     mdAssemblyRef   rAssemblyRefs[],   
    [in]      ULONG           cMax,   
    [out]     ULONG           *pcTokens  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `phEnum`  
 [out에서] 열거자에 대 한 포인터입니다. Null 이어야 합니다 경우이 값은 `EnumAssemblyRefs` 처음으로 호출 됩니다.  
  
 `rAssemblyRefs`  
 [out] 열거형 `mdAssemblyRef` 메타 데이터 토큰입니다.  
  
 `cMax`  
 [in] 에 배치할 수 있는 토큰의 최대 수는 `rAssemblyRefs` 배열입니다.  
  
 `pcTokens`  
 [out] 토큰의 수에 실제로 배치 `rAssemblyRefs`합니다.  
  
## <a name="return-value"></a>반환 값  
  
|HRESULT|설명|  
|-------------|-----------------|  
|`S_OK`|`EnumAssemblyRefs` 성공적으로 반환 합니다.|  
|`S_FALSE`|열거할 토큰이 있습니다. 이 경우 `pcTokens` 0으로 설정 됩니다.|  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.  
  
 **헤더:** Cor.h  
  
 **라이브러리:** MsCorEE.dll에서 리소스로 사용  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참고자료
- [IMetaDataAssemblyImport 인터페이스](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)
