---
title: ImportFileEx2 메서드
ms.date: 03/30/2017
api_name:
- IALink2.ImportFileEx2
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- ImportFileEx2
helpviewer_keywords:
- ImportFileEx2 method
ms.assetid: 02c789fd-16fc-48c6-9619-56e87e2a37ca
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 784e58e0c5c2329705671580d53763f2ac30f0b2
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59201353"
---
# <a name="importfileex2-method"></a>ImportFileEx2 메서드
어셈블리 및 바인딩되지 않은 모듈을 가져옵니다. 이 메서드는 [ImportFile 메서드](../../../../docs/framework/unmanaged-api/alink/importfile-method.md), 되지만 가져올 파일 디스크에 없는 경우 경우에 작동 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT ImportFileEx2(  
    LPCWSTR pszFilename,  
    LPCWSTR pszTargetName,  
    IMetaDataAssemblyImport* pAssemblyScopeIn,  
    BOOL fSmartImport,  
    DWORD dwOpenFlags,  
    mdToken* pImportToken,  
    IMetaDataAssemblyImport** ppAssemblyScope,  
    DWORD* pdwCountOfScopes  
) PURE;  
```  
  
## <a name="parameters"></a>매개 변수  
 `pszFilename`  
 가져올 파일의 이름입니다.  
  
 `pszTargetName`  
 대상 파일의 선택적 이름입니다.  
  
 `pAssemblyScopeIn`  
 선택적 가져오기 범위 [IMetaDataAssemblyImport 인터페이스](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md) 인터페이스입니다.  
  
 `fSmartImport`  
 TRUE 이면 ImportTypes 되, 그렇지 않으면 가져오기는 수동으로 수행 해야 합니다.  
  
 `dwOpenFlags`  
 에 전달 하는 플래그 [OpenScope 메서드](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-openscope-method.md)합니다.  
  
 `pImportToken`  
 어셈블리 또는 파일에 대 한 고유 ID를 받습니다.  
  
 `ppAssemblyScope`  
 어셈블리 가져오기 범위를 받는 [IMetaDataAssemblyImport 인터페이스](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md) 인터페이스입니다. 파일 어셈블리가 아닌 경우 NULL 일 수 있습니다.  
  
 `pdwCountOfScopes`  
 파일 및/또는 가져온 범위 수를 받습니다.  
  
## <a name="return-value"></a>반환 값  
 메서드가 성공 하면 S_OK를 반환 합니다.  
  
## <a name="requirements"></a>요구 사항  
 Alink.h가 필요합니다.  
  
## <a name="see-also"></a>참고자료

- [IALink2 인터페이스](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)
- [IALink 인터페이스](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)
- [ALink API](../../../../docs/framework/unmanaged-api/alink/index.md)
