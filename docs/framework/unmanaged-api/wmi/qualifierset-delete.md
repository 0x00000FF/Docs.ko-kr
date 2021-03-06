---
title: QualifierSet_Delete 기능(관리되지 않는 API 참조)
description: QualifierSet_Delete 함수는 한정자를 이름으로 삭제합니다.
ms.date: 11/06/2017
api_name:
- QualifierSet_Delete
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- QualifierSet_Delete
helpviewer_keywords:
- QualifierSet_Delete function [.NET WMI and performance counters]
topic_type:
- Reference
ms.openlocfilehash: 0d2a02ba9d89ba16e776bb73563eaebf8a92f1fd
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79174903"
---
# <a name="qualifierset_delete-function"></a>QualifierSet_Delete 함수
지정된 한정자를 이름으로 삭제합니다.  

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT QualifierSet_Delete (
   [in] int                  vFunc,
   [in] IWbemQualifierSet*   ptr,
   [in] LPCWSTR              wszName
);
```  

## <a name="parameters"></a>매개 변수

`vFunc`  
【인】 이 매개 변수는 사용되지 않습니다.

`ptr`【인】 [IWbemQualifierSet](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset) 인스턴스에 대한 포인터입니다.

`wszName`【인】 삭제할 한정자의 이름입니다.

## <a name="return-value"></a>반환 값

이 함수에서 반환되는 다음 값은 *WbemCli.h* 헤더 파일에 정의되거나 코드에서 상수로 정의할 수 있습니다.

|지속적임  |값  |Description  |
|---------|---------|---------|
|`WBEM_E_INVALID_PARAMETER` | 0x80041008 | `wszName` 매개 변수가 잘못된 경우 |
|`WBEM_E_INVALID_OPERATION` | 0x80041016 | 이 한정자를 삭제하는 것은 불법입니다. |
|`WBEM_E_NOT_FOUND` | 0x80041002 | 지정된 한정자를 찾을 수 없습니다. |
|`WBEM_S_NO_ERROR` | 0 | 함수 호출이 성공했습니다.  |
| `WBEM_S_RESET_TO_DEFAULT` | 0x40002 | 로컬 재정의가 삭제되고 상위 개체의 원래 한정자가 범위를 다시 시작했습니다. |

## <a name="remarks"></a>설명

이 함수는 [IWbemQualifierSet::Delete](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemqualifierset-delete) 메서드에 대한 호출을 래핑합니다.

한정자 전파 규칙으로 인해 특정 한정자가 다른 개체에서 상속되고 현재 클래스 또는 인스턴스에서 재정의되었을 수 있습니다. 이 경우 메서드는 `QualifierSet_Delete` 한정자를 원래 상속된 값으로 재설정합니다. 이 경우 함수는 상태 `WBEM_S_RESET_TO_DEFAULT`코드를 반환합니다.

## <a name="requirements"></a>요구 사항  
 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** WMINet_Utils.idl  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>참고 항목

- [WMI 및 성능 카운터(관리되지 않는 API 참조)](index.md)
