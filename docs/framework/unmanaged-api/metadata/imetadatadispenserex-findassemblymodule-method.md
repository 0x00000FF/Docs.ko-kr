---
title: "IMetaDataDispenserEx::FindAssemblyModule 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataDispenserEx.FindAssemblyModule
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataDispenserEx::FindAssemblyModule
helpviewer_keywords:
- FindAssemblyModule method [.NET Framework metadata]
- IMetaDataDispenserEx::FindAssemblyModule method [.NET Framework metadata]
ms.assetid: d1fb65e1-7e19-4513-85b1-44f87c294d3e
topic_type: apiref
caps.latest.revision: "11"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 482bc9b9a89d876e7ac09fcb4edcd190adc168f9
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="imetadatadispenserexfindassemblymodule-method"></a>IMetaDataDispenserEx::FindAssemblyModule 메서드
이 메서드가 구현되지 않았습니다. 를 호출 하는 경우 E_NOTIMPL을 반환 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT FindAssemblyModule(  
    [in]  LPCWSTR  szAppBase,  
    [in]  LPCWSTR  szPrivateBin,  
    [in]  LPCWSTR  szGlobalBin,  
    [in]  LPCWSTR  szAssemblyName,  
    [in]  LPCWSTR  szModuleName,  
    [out] LPCWSTR  szName,  
    [in]  ULONG    cchName,  
    [out] ULONG    *pcName  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `szAppBase`  
 [in] 사용 되지 않습니다.  
  
 `szPrivateBin`  
 [in] 사용 되지 않습니다.  
  
 `szGlobalBin`  
 [in] 사용 되지 않습니다.  
  
 `szAssemblyName`  
 [in] 모듈의 이름입니다.  
  
 `szModuleName`  
 [in] 어셈블리를 찾을 수입니다.  
  
 `szName`  
 [out] 어셈블리의 단순한 이름입니다.  
  
 `cchName`  
 [in] 를 바이트 단위로 크기의 `szName`합니다.  
  
 `pcName`  
 [out] 에 실제로 반환 된 문자 수가 `szName`합니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** Cor.h  
  
 **라이브러리:** MsCorEE.dll에서 리소스로 사용  
  
 **.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [IMetaDataDispenserEx 인터페이스](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenserex-interface.md)  
 [IMetaDataDispenser 인터페이스](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-interface.md)
