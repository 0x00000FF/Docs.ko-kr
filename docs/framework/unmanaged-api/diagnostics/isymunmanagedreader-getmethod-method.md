---
title: ISymUnmanagedReader::GetMethod 메서드
ms.date: 03/30/2017
api_name:
- ISymUnmanagedReader.GetMethod
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedReader::GetMethod
helpviewer_keywords:
- GetMethod method, ISymUnmanagedReader interface [.NET Framework debugging]
- ISymUnmanagedReader::GetMethod method [.NET Framework debugging]
ms.assetid: ae6cfb29-bc2c-4606-af86-1d32ebd31020
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: deb5d7aa24cf750a9584ef2aa32d10816ec12f57
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54614408"
---
# <a name="isymunmanagedreadergetmethod-method"></a>ISymUnmanagedReader::GetMethod 메서드
메서드 토큰을 지정 된 기호 판독기 메서드를 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT GetMethod (  
    [in]  mdMethodDef  token,  
    [out, retval] ISymUnmanagedMethod**  pRetVal);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `token`  
 [in] 메서드 토큰입니다.  
  
 `pRetVal`  
 [out] 반환 되는 인터페이스 포인터입니다.  
  
## <a name="return-value"></a>반환 값  
 메서드가 성공 하면 s_ok이 고 그렇지 않으면 E_FAIL 또는 일부 다른 오류 코드입니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** CorSym.idl, CorSym.h  
  
## <a name="see-also"></a>참고자료
- [ISymUnmanagedReader 인터페이스](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)
