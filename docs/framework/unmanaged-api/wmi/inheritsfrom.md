---
title: InheritsFrom 함수 (관리 되지 않는 API 참조)
description: InheritsFrom 함수 클래스 또는 인스턴스는 특정 부모 클래스 로부터 파생 있는지 여부를 결정 합니다.
ms.date: 11/06/2017
api_name:
- InheritsFrom
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- InheritsFrom
helpviewer_keywords:
- InheritsFrom function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 87a1c1ee44d3b192747bd785f538c0332300ff50
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33461417"
---
# <a name="inheritsfrom-function"></a>InheritsFrom 함수
현재 클래스 또는 인스턴스를 지정 된 부모 클래스에서 파생 있는지 여부를 결정 합니다.

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
    
## <a name="syntax"></a>구문  
  
```
HRESULT InheritsFrom (
   [in] int               vFunc, 
   [in] IWbemClassObject* ptr, 
   [in] LPCWSTR           wszAncestor 
); 
```  

## <a name="parameters"></a>매개 변수

`vFunc`  
[in] 이 매개 변수를 사용 하지 않습니다.

`ptr`  
[in] 에 대 한 포인터는 [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) 인스턴스.

`wszAncestor`  
[in] 클래스의 이름입니다. `wszAncestor` 유효한 가리켜야 `LPCWSTR`합니다.

## <a name="return-value"></a>반환 값

이 함수에서 반환 되는 다음 값에 정의 된는 *WbemCli.h* 헤더 파일 또는 있습니다를 정의할 수 상수로 코드:

|상수  |값  |설명  |
|---------|---------|---------|
| `WBEM_S_NO_ERROR` | 0 | 현재 개체에서 상속 `wszAncestor`합니다.  |
| `WBEM_S_FALSE` | 1 | 현재 개체에서 상속 되지 않는 `wszAncestor`합니다. |
|`WBEM_E_INVALID_PARAMETER` | 0x80041008 | `wszAncestor`가 `null`인 경우 |
  
## <a name="remarks"></a>설명

이 함수에 대 한 호출을 래핑하는 [IWbemClassObject::InheritsFrom](https://msdn.microsoft.com/library/aa391452(v=vs.85).aspx) 메서드.

## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** WMINet_Utils.idl  
  
 **.NET framework 버전:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>참고자료  
[WMI 및 성능 카운터 (관리 되지 않는 API 참조)](index.md)
