---
title: "IMetaDataAssemblyImport::GetExportedTypeProps 메서드"
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
- IMetaDataAssemblyImport.GetExportedTypeProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyImport::GetExportedTypeProps
helpviewer_keywords:
- GetExportedTypeProps method [.NET Framework metadata]
- IMetaDataAssemblyImport::GetExportedTypeProps method [.NET Framework metadata]
ms.assetid: 25ca7623-5a55-4f09-b44a-36b03d142278
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 7fc5bb8266814fc4f1333de78fce4b6af86893c5
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="imetadataassemblyimportgetexportedtypeprops-method"></a>IMetaDataAssemblyImport::GetExportedTypeProps 메서드
지정한 메타 데이터 서명 사용 하 여 내보낸 형식의 속성 집합을 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT GetExportedTypeProps (  
    [in]  mdExportedType    mdct,   
    [out] LPWSTR            szName,   
    [in]  ULONG             cchName,   
    [out] ULONG             *pchName,   
    [out] mdToken           *ptkImplementation,   
    [out] mdTypeDef         *ptkTypeDef,   
    [out] DWORD             *pdwExportedTypeFlags  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `mdct`  
 [in] `mdExportedType` 내보낸된 형식을 나타내는 메타 데이터 토큰입니다.  
  
 `szName`  
 [out] 내보낸 형식의 이름입니다.  
  
 `cchName`  
 [in] 와이드 문자에서 크기의 `szName`합니다.  
  
 `pchName`  
 [out] 에 실제로 반환 된 와이드 문자 수`szName`  
  
 `ptkImplementation`  
 [out] `mdFile`, `mdAssemblyRef`, 또는 `mdExportedType` 내보낸 형식의 속성에 대 한 액세스 허용 또는 포함 된 메타 데이터 토큰입니다.  
  
 `ptkTypeDef`  
 [out] 에 대 한 포인터는 `mdTypeDef` 파일의 유형을 나타내는 토큰입니다.  
  
 `pdwExportedTypeFlags`  
 [out] 내보낸된 형식에 적용 되는 메타 데이터를 설명 하는 플래그에 대 한 포인터입니다. 하나 이상의 플래그 값 수 [CorTypeAttr](../../../../docs/framework/unmanaged-api/metadata/cortypeattr-enumeration.md) 값입니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** Cor.h  
  
 **라이브러리:** MsCorEE.dll에서 리소스로 사용  
  
 **.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [IMetaDataAssemblyImport 인터페이스](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)
