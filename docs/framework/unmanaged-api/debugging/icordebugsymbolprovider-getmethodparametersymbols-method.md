---
title: "ICorDebugSymbolProvider::GetMethodParameterSymbols 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: 58b7c0b9-f6ad-4b49-b92d-0e421cfd0ec6
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: dd3fc08eec9066f54d90fbe4824ce3f1a1c901dc
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugsymbolprovidergetmethodparametersymbols-method"></a>ICorDebugSymbolProvider::GetMethodParameterSymbols 메서드
메서드의 RVA(상대 가상 주소)가 지정된 경우 해당 메서드의 매개 변수 기호를 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT GetMethodParameterSymbols(  
   [in] ULONG32 nativeRVA,  
   [in] ULONG32 cRequestedSymbols,  
   [out] ULONG32 *pcFetchedSymbols,  
   [out, size_is(cRequestedSymbols), length_is(*pcFetchedSymbols)] ICorDebugVariableSymbol *pSymbols[]  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `nativeRVA`  
 [in] 메서드의 기본 상대 가상 주소입니다.  
  
 `cRequestedSymbols`  
 [in] 요청되는 로컬 기호 수입니다.  
  
 `pcFetchedSymbols`  
 [out] 메서드에 의해 검색되는 기호 수에 대한 포인터입니다.  
  
 `pcFetchedSymbols`  
 [out] 에 대 한 포인터는 [ICorDebugVariableSymbol](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablesymbol-interface.md) 메서드의 로컬 기호 있는 배열입니다.  
  
## <a name="remarks"></a>설명  
  
> [!NOTE]
>  이 메서드는 .NET 네이티브에서만 사용할 수 있습니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET framework 버전:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [GetMethodLocalSymbols 메서드](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-getmethodlocalsymbols-method.md)  
 [ICorDebugSymbolProvider 인터페이스](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-interface.md)  
 [디버깅 인터페이스](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
