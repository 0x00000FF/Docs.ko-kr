---
title: "IAssemblyName::GetProperty 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IAssemblyName.GetProperty
api_location: fusion.dll
api_type: COM
f1_keywords: IAssemblyName::GetProperty
helpviewer_keywords:
- IAssemblyName::GetProperty method [.NET Framework fusion]
- GetProperty method [.NET Framework fusion]
ms.assetid: e59fda62-77d5-4e37-89cb-ce7ae4627975
topic_type: apiref
caps.latest.revision: "7"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 6eae7cf2d6dabe9bad4912d6a97249f52464fe65
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="iassemblynamegetproperty-method"></a>IAssemblyName::GetProperty 메서드
지정 된 속성 식별자가 참조 하는 속성에 대 한 포인터를 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT GetProperty (  
    [in]      DWORD    PropertyId,  
    [out]     LPVOID   pvProperty,  
    [in, out] LPDWORD  pcbProperty  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `PropertyId`  
 [in] 요청된 된 속성에 대 한 고유 식별자입니다.  
  
 `pvProperty`  
 [out] 반환 된 속성 데이터입니다.  
  
 `pcbProperty`  
 [out에서] 를 바이트 단위로 크기의 `pvProperty`합니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** Fusion.h  
  
 **.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [IAssemblyName 인터페이스](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md)
