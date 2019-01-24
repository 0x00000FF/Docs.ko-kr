---
title: IMetaDataEmit::DefineField 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.DefineField
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::DefineField
helpviewer_keywords:
- IMetaDataEmit::DefineField method [.NET Framework metadata]
- DefineField method, IMetaDataEmit interface [.NET Framework metadata
ms.assetid: 6b5be4fc-2e86-499c-8b09-833160bca767
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: dfe888f74face85179306c982f7b5a888752987e
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54742801"
---
# <a name="imetadataemitdefinefield-method"></a>IMetaDataEmit::DefineField 메서드
지정 된 메타 데이터 서명을 사용 하 여 필드에 대 한 정의 만들고 해당 필드 정의 하는 토큰을 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT DefineField (   
    [in]  mdTypeDef   td,   
    [in]  LPCWSTR     szName,   
    [in]  DWORD       dwFieldFlags,   
    [in]  PCCOR_SIGNATURE pvSigBlob,   
    [in]  ULONG       cbSigBlob,   
    [in]  DWORD       dwCPlusTypeFlag,   
    [in]  void const  *pValue,   
    [in]  ULONG       cchValue,   
    [out] mdFieldDef  *pmd   
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `td`  
 [in] `mdTypeDef` 바깥쪽 클래스 또는 인터페이스에 대 한 토큰입니다.  
  
 `szName`  
 [in] 유니코드에 대 한 필드 이름입니다.  
  
 `dwFieldFlags`  
 [in] 필드 특성입니다. 이 비트 마스크의 `CorFieldAttr` 값입니다.  
  
 `pvSigBlob`  
 [in] BLOB으로 필드 시그니처입니다.  
  
 `cbSigBlob`  
 [in] 바이트 수가 `pvSigBlob`합니다.  
  
 `dwCPlusTypeFlag`  
 [in] 합니다 `ELEMENT_TYPE_` *\** 상수 값에 대 한 합니다. 이 `CorElementType` 값입니다. 필드에 대 한 상수 값을 정의 하지 않는, 사용 하 여 `ELEMENT_TYPE_END`입니다.  
  
 `pValue`  
 [in] 필드의 상수 값입니다.  
  
 `cchValue`  
 [in] \(유니코드) 문자의 크기 `pValue`합니다.  
  
 `pmd`  
 [out] `mdFieldDef` 할당 된 토큰입니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.  
  
 **헤더:** Cor.h  
  
 **라이브러리:** MSCorEE.dll에서 리소스로 사용  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참고자료
- [IMetaDataEmit 인터페이스](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [IMetaDataEmit2 인터페이스](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
