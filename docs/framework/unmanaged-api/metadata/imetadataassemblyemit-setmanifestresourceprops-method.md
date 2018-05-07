---
title: IMetaDataAssemblyEmit::SetManifestResourceProps 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataAssemblyEmit.SetManifestResourceProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyEmit::SetManifestResourceProps
helpviewer_keywords:
- SetManifestResourceProps method [.NET Framework metadata]
- IMetaDataAssemblyEmit::SetManifestResourceProps method [.NET Framework metadata]
ms.assetid: ef77efd1-849c-4e51-ba92-7ee3d2bf0339
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 755c64aa00b82bf2d8213217787f4dc1916c0898
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="imetadataassemblyemitsetmanifestresourceprops-method"></a>IMetaDataAssemblyEmit::SetManifestResourceProps 메서드
지정된 `ManifestResource` 메타데이터 구조를 수정합니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT SetManifestResourceProps (  
    [in] mdManifestResource  mr,  
    [in] mdToken             tkImplementation,   
    [in] DWORD               dwOffset,  
    [in] DWORD               dwResourceFlags  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `mr`  
 [in] 토큰을 지정 하는 `ManifestResource` 메타 데이터 구조를 수정할 수 있습니다.  
  
 `tkImplementation`  
 [in] 형식의 토큰 `File` 또는 `AssemblyRef`, 리소스 공급자에 매핑되는 합니다.  
  
 `dwOffset`  
 [in] 파일 내에서 리소스의 시작 부분에 대 한 오프셋입니다.  
  
 `dwResourceFlags`  
 [in] 리소스의 특성을 지정 하는 플래그 값의 비트 조합입니다.  
  
## <a name="remarks"></a>설명  
 만들려는 `ManifestResource` 메타 데이터 구조를 사용 하 여는 [imetadataassemblyemit:: Definemanifestresource](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-definemanifestresource-method.md) 메서드.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** Cor.h  
  
 **라이브러리:** MsCorEE.dll에서 리소스로 사용  
  
 **.NET framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [IMetaDataAssemblyEmit 인터페이스](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
