---
title: ISymUnmanagedENCUpdate::GetLocalVariables 메서드
ms.date: 03/30/2017
api_name:
- ISymUnmanagedENCUpdate.GetLocalVariables
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedENCUpdate::GetLocalVariables
helpviewer_keywords:
- ISymUnmanagedENCUpdate::GetLocalVariables method [.NET Framework debugging]
- GetLocalVariables method [.NET Framework debugging]
ms.assetid: 5c8840be-ffea-447f-9c8d-178f1eaf8d06
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: a53493d666cb16fcc9b407ca3a46072afa306b97
ms.sourcegitcommit: 35316b768394e56087483cde93f854ba607b63bc
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/26/2018
ms.locfileid: "52297558"
---
# <a name="isymunmanagedencupdategetlocalvariables-method"></a>ISymUnmanagedENCUpdate::GetLocalVariables 메서드
지역 변수를 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT GetLocalVariables(  
    [in]  mdMethodDef  mdMethodToken,  
    [in]  ULONG        cLocals,  
    [out, size_is(cLocals), length_is(*pceltFetched)]  
        ISymUnmanagedVariable *rgLocals[],  
    [out] ULONG        *pceltFetched);  
```  
  
## <a name="parameters"></a>매개 변수  
 `mdMethodToken`  
 [in] 메서드의 메타 데이터 토큰입니다.  
  
 `cLocals`  
 [in] A `ULONG` 의 크기를 나타내는 `rgLocals` 매개 변수입니다.  
  
 `rgLocals`  
 [out] 반환된 된 배열 [ISymUnmanagedVariable](isymunmanagedvariable-interface.md) 인스턴스.  
  
 `pceltFetched`  
 [out] 에 대 한 포인터를 `ULONG` 의 크기를 받는 `rgLocals` 지역 변수를 포함 하는 데 필요한 버퍼입니다.  
  
## <a name="return-value"></a>반환 값  
 메서드가 성공 하면 s_ok이 고 그렇지 않으면 E_FAIL 또는 일부 다른 오류 코드입니다.  
  
## <a name="requirements"></a>요구 사항  
 **Header:** CorSym.idl, CorSym.h  
  
## <a name="see-also"></a>참고 항목  
 [ISymUnmanagedENCUpdate 인터페이스](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedencupdate-interface.md)
