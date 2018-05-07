---
title: SetAssemblyProps 메서드
ms.date: 03/30/2017
api_name:
- IALink.SetAssemblyProps
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- SetAssemblyProps
helpviewer_keywords:
- SetAssemblyProps method
ms.assetid: a3d7cf29-1414-49e6-8aae-9b3283c4f5f0
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: aed553a3a8d54b5229a122e76b61e3e58d4af3c1
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="setassemblyprops-method"></a>SetAssemblyProps 메서드
어셈블리 수준 속성을 할당합니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT SetAssemblyProps(  
    mdAssembly      AssemblyID,  
    mdToken         FileToken,  
    AssemblyOptions Option,  
    VARIANT         Value  
) PURE;  
```  
  
#### <a name="parameters"></a>매개 변수  
 `AssemblyID`  
 어셈블리의 ID입니다.  
  
 `FileToken`  
 속성을 정의 하는 파일입니다. 경우 NULL이 될 수 `AssemblyID` 바인딩되지 않은 어셈블리를 나타내지 않습니다.  
  
 `Option`  
 수정할 수 있는 옵션을 나타냅니다.  
  
 `Value`  
 옵션의 새 값입니다.  
  
## <a name="return-value"></a>반환 값  
 메서드가 성공 하면 S_OK를 반환 합니다.  
  
## <a name="requirements"></a>요구 사항  
 Alink.h가 필요합니다.  
  
## <a name="see-also"></a>참고 항목  
 [IALink 인터페이스](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)  
 [IALink2 인터페이스](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)  
 [ALink API](../../../../docs/framework/unmanaged-api/alink/index.md)
