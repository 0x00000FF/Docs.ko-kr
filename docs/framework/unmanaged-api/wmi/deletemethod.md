---
title: DeleteMethod 함수 (관리 되지 않는 API 참조)
description: DeleteMethod 함수 CIM 클래스 정의에서 지정된 된 메서드를 삭제합니다.
ms.date: 11/06/2017
api_name:
- DeleteMethod
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- DeleteMethod
helpviewer_keywords:
- DeleteMethod function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: fd862910d0c9bb0274158c2c516211cef598a553
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33457810"
---
# <a name="deletemethod-function"></a>DeleteMethod 함수
CIM 클래스 정의에서 지정된 된 메서드를 삭제합니다.

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
    
## <a name="syntax"></a>구문  
  
```  
HRESULT Delete (
   [in] int               vFunc, 
   [in] IWbemClassObject* ptr, 
   [in] LPCWSTR           wszName 
); 
```  

## <a name="parameters"></a>매개 변수

`vFunc`  
[in] 이 매개 변수를 사용 하지 않습니다.

`ptr`  
[in] 에 대 한 포인터는 [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) 인스턴스.

`wszName`  
[in] 클래스 테이블에서 제거 하는 메서드의 이름입니다. `wszName` 유효한 포인터 여야 합니다. `LPCWSTR`합니다.

## <a name="return-value"></a>반환 값

이 함수에서 반환 되는 다음 값에 정의 된는 *WbemCli.h* 헤더 파일 또는 있습니다를 정의할 수 상수로 코드:

|상수  |값  |설명  |
|---------|---------|---------|
| `WBEM_E_NOT_FOUND` | 0x80041002 | 지정된 된 메서드는 존재 하지 않습니다. |
| `WBEM_E_OUT_OF_MEMORY` | 0x80041006 | 메모리가 부족 하 여 작업을 완료할 수 없습니다. |
| `WBEM_S_NO_ERROR` | 0 | 함수 호출이 성공 했습니다.  |

## <a name="remarks"></a>설명

이 함수에 대 한 호출을 래핑하는 [IWbemClassObject::DeleteMethod](https://msdn.microsoft.com/library/aa391439(v=vs.85).aspx) 메서드.

삭제 방법에 대 한 지원 되지 않습니다 [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) CIM 인스턴스를 가리키는 포인터입니다.

## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** WMINet_Utils.idl  
  
 **.NET framework 버전:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>참고자료  
[WMI 및 성능 카운터 (관리 되지 않는 API 참조)](index.md)
