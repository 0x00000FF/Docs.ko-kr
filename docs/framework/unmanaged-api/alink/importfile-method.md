---
title: ImportFile 메서드
ms.date: 03/30/2017
api_name:
- IALink.ImportFile
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- ImportFile
helpviewer_keywords:
- ImportFile method
ms.assetid: bcbe321f-b83a-4e9a-9f10-8d913e244dc9
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 16793cfd93ce296ba0e2bc70c59c22d598aacacd
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/06/2019
ms.locfileid: "57500670"
---
# <a name="importfile-method"></a>ImportFile 메서드
어셈블리 및 바인딩되지 않은 모듈을 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT ImportFile(  
    LPCWSTR pszFilename,  
    LPCWSTR pszTargetName,  
    BOOL fSmartImport,  
    mdToken* pImportToken,  
    IMetaDataAssemblyImport** ppAssemblyScope,  
    DWORD* pdwCountOfScopes  
) PURE;  
```  
  
## <a name="parameters"></a>매개 변수  
 `pszFilename`  
 가져올 파일의 정규화 된 이름입니다.  
  
 `pszTargetName`  
 어셈블리에 링크 되어 파일의 이름을 사용할 수 있는 선택적 출력 파일 이름입니다.  
  
 `fSmartImport`  
 TRUE 이면 ImportTypes 되, 그렇지 않으면 가져오기는 수동으로 수행 해야 합니다.  
  
 `pImportToken`  
 고유한 파일 ID를 저장할 토큰에 대 한 포인터입니다. 어셈블리 또는 파일의 파일 수 있습니다.  
  
 `ppAssemblyScope`  
 에 대 한 포인터를 받는 [IMetaDataAssemblyImport 인터페이스](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)합니다. 파일 어셈블리가 아닌 경우 NULL 일 수 있습니다.  
  
 `pdwCountOfScopes`  
 파일 및/또는 가져온 범위 수에 대 한 포인터입니다.  
  
## <a name="return-value"></a>반환 값  
 메서드가 성공 하면 S_OK를 반환 합니다.  
  
## <a name="requirements"></a>요구 사항  
 Alink.h 필요  
  
## <a name="see-also"></a>참고자료
- [IALink 인터페이스](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)
- [IALink2 인터페이스](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)
- [ALink API](../../../../docs/framework/unmanaged-api/alink/index.md)
