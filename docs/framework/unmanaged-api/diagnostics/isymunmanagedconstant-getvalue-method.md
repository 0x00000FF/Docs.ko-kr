---
title: ISymUnmanagedConstant::GetValue 메서드
ms.date: 03/30/2017
api_name:
- ISymUnmanagedConstant.GetValue
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedConstant::GetValue
helpviewer_keywords:
- GetValue method, ISymUnmanagedConstant interface [.NET Framework debugging]
- ISymUnmanagedConstant::GetValue method [.NET Framework debugging]
ms.assetid: 0036fc10-e768-47a8-b9cf-bf47faf8d194
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 75cc16f44ddf29b161c758718b697cc2aaba8e08
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59204668"
---
# <a name="isymunmanagedconstantgetvalue-method"></a>ISymUnmanagedConstant::GetValue 메서드
상수 값을 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT GetValue(  
    [out]  VARIANT* pValue  
);  
```  
  
## <a name="parameters"></a>매개 변수  
 `pValue`  
 [out] 값을 수신 하는 변수에 대 한 포인터입니다.  
  
## <a name="return-value"></a>반환 값  
 메서드가 성공 하면 s_ok이 고 그렇지 않으면 E_FAIL 또는 일부 다른 오류 코드입니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** CorSym.idl, CorSym.h  
  
## <a name="see-also"></a>참고자료

- [ISymUnmanagedConstant 인터페이스](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedconstant-interface.md)
- [GetName 메서드](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedconstant-getname-method.md)
- [GetSignature 메서드](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedconstant-getsignature-method.md)
