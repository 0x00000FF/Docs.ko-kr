---
title: IMetaDataImport::FindTypeDefByName 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataImport.FindTypeDefByName
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::FindTypeDefByName
helpviewer_keywords:
- FindTypeDefByName method [.NET Framework metadata]
- IMetaDataImport::FindTypeDefByName method [.NET Framework metadata]
ms.assetid: f4c2cd88-ac28-4bad-9ab1-2cf9d2de41e6
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 3b6040f21bb530ce775fc79e33b97eb14870c04f
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54578821"
---
# <a name="imetadataimportfindtypedefbyname-method"></a>IMetaDataImport::FindTypeDefByName 메서드
토큰에 대 한 TypeDef 메타 데이터에 대 한 포인터를 가져옵니다는 <xref:System.Type> 지정한 이름을 가진 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT FindTypeDefByName  
   [in]  LPCWSTR       szTypeDef,  
   [in]  mdToken       tkEnclosingClass,  
   [out] mdTypeDef     *ptd  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `szTypeDef`  
 [in] TypeDef 토큰을 가져올 형식의 이름입니다.  
  
 `tkEnclosingClass`  
 [in] 바깥쪽 클래스를 나타내는 형식 정의 또는 TypeRef 토큰입니다. 찾을 형식의 중첩된 된 클래스를 없는 경우이 값을 NULL로 설정 합니다.  
  
 `ptd`  
 [out] 일치 하는 TypeDef 토큰에 대 한 포인터입니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.  
  
 **헤더:** Cor.h  
  
 **라이브러리:** MsCorEE.dll에 리소스로 포함  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참고자료
- [IMetaDataImport 인터페이스](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [IMetaDataImport2 인터페이스](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
