---
title: ISymUnmanagedReader2::GetMethodByVersionPreRemap 메서드
ms.date: 03/30/2017
api_name:
- ISymUnmanagedReader2.GetMethodByVersionPreRemap
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedReader2::GetMethodByVersionPreRemap
helpviewer_keywords:
- GetMethodByVersionPreRemap method [.NET Framework debugging]
- ISymUnmanagedReader2::GetMethodByVersionPreRemap method [.NET Framework debugging]
ms.assetid: 0d144ed4-bdb0-4cac-960c-cb90f4dca173
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: efa34d262157faed2e05cd6e7517c259cd279146
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33428578"
---
# <a name="isymunmanagedreader2getmethodbyversionpreremap-method"></a>ISymUnmanagedReader2::GetMethodByVersionPreRemap 메서드
메서드 토큰이 편집 하며 계속 하기 버전 번호를 지정 된 기호 판독기 메서드를 가져옵니다. 버전 번호는 1부터 시작 하 고 메서드가 편집 하며 계속 하기 작업의 결과로 변경 될 때마다 증가 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT GetMethodByVersionPreRemap(  
    [in]  mdMethodDef token,  
    [in]  int version,  
    [out, retval] ISymUnmanagedMethod** pRetVal);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `token`  
 [in] 메서드 메타 데이터 토큰입니다.  
  
 `version`  
 [in] 메서드 버전입니다.  
  
 `pRetVal`  
 [out] 반환 된에 대 한 포인터 [ISymUnmanagedMethod](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-interface.md) 인터페이스입니다.  
  
## <a name="return-value"></a>반환 값  
 메서드가 성공 하면 s_ok이 고 그렇지 않으면 E_FAIL 또는 일부 기타 오류 코드입니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** CorSym.idl 합니다. CorSym.h  
  
## <a name="see-also"></a>참고 항목  
 [ISymUnmanagedReader2 인터페이스](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader2-interface.md)
