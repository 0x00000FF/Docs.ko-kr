---
title: ICorDebugArrayValue::GetDimensions 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugArrayValue.GetDimensions
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugArrayValue::GetDimensions
helpviewer_keywords:
- ICorDebugArrayValue::GetDimensions method [.NET Framework debugging]
- GetDimensions method [.NET Framework debugging]
ms.assetid: 6c116592-134b-4ef2-a319-680e92d013aa
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e9c341ba3d0164e65cd752baa20f674fe3afc714
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="icordebugarrayvaluegetdimensions-method"></a>ICorDebugArrayValue::GetDimensions 메서드
이 배열의 각 차원에 있는 요소 수를 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT GetDimensions (  
    [in] ULONG32         cdim,  
    [out, size_is(cdim), length_is(cdim)]   
        ULONG32          dims[]  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `cdim`  
 [in] 차원이 ICorDebugArrayValue 개체의 수입니다.  
  
 또한이 값은의 크기는 `dims` 배열 크기의 차원 수와 같은지는 `ICorDebugArrayValue` 개체입니다.  
  
 `dims`  
 [out] 이 차원에 있는 요소 수를 지정는 각각 정수, 배열 `ICorDebugArrayValue` 개체입니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
