---
title: ICorDebugVariableSymbol::GetName 메서드
ms.date: 03/30/2017
ms.assetid: c922b7d4-44e5-45e4-aef3-cc9c35a0be80
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d01f8c3956298daee9f11c912406079d98964225
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/06/2019
ms.locfileid: "57465300"
---
# <a name="icordebugvariablesymbolgetname-method"></a>ICorDebugVariableSymbol::GetName 메서드
변수의 이름을 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT GetName(  
   [in] ULONG32 cchName,   
   [out] ULONG32 *pcchName,   
   [out, size_is(cchName), length_is(*pcchName)] WCHAR szName[]  
);  
```  
  
## <a name="parameters"></a>매개 변수  
 `cchName`  
 [in] `szName` 버퍼의 문자 수입니다.  
  
 `pcchName`  
 [out] `szName` 버퍼에 실제로 기록된 문자 수에 대한 포인터입니다.  
  
 `szName`  
 변수 이름이 포함된 문자 배열에 대한 포인터입니다.  
  
## <a name="remarks"></a>설명  
  
> [!NOTE]
>  이 메서드는 .NET 네이티브에서만 사용할 수 있습니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a>참고자료
- [ICorDebugVariableSymbol 인터페이스](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablesymbol-interface.md)
- [디버깅 인터페이스](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
