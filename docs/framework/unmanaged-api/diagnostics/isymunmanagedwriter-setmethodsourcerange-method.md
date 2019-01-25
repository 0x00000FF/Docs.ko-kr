---
title: ISymUnmanagedWriter::SetMethodSourceRange 메서드
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter.SetMethodSourceRange
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter::SetMethodSourceRange
helpviewer_keywords:
- SetMethodSourceRange method [.NET Framework debugging]
- ISymUnmanagedWriter::SetMethodSourceRange method [.NET Framework debugging]
ms.assetid: c698b86e-ace7-4b21-9549-f52d6a034959
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 40d05ee60d0183337e67b1f36722dff29ae9beaf
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54663546"
---
# <a name="isymunmanagedwritersetmethodsourcerange-method"></a>ISymUnmanagedWriter::SetMethodSourceRange 메서드
소스 파일 내에서 메서드의 실제 시작과 끝을 지정합니다. 이 메서드를 사용 하 여 메서드 내에 있는 시퀀스 위치의 독립적으로 메서드의 범위를 지정 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT SetMethodSourceRange(  
    [in] ISymUnmanagedDocumentWriter  *startDoc,  
    [in] ULONG32                      startLine,  
    [in] ULONG32                      startColumn,  
    [in] ISymUnmanagedDocumentWriter  *endDoc,  
    [in] ULONG32                      endLine,  
    [in] ULONG32                      endColumn);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `startDoc`  
 [in] 시작 위치를 포함 하는 문서에 대 한 포인터입니다.  
  
 `startLine`  
 [in] 시작 줄 번호입니다.  
  
 `startColumn`  
 [in] 시작 열입니다.  
  
 `endDoc`  
 [in] 끝 위치를 포함 하는 문서에 대 한 포인터입니다.  
  
 `endLine`  
 [in] 끝 줄 번호입니다.  
  
 `endColumn`  
 [in] 끝 열 번호입니다.  
  
## <a name="return-value"></a>반환 값  
 메서드가 성공 하면 s_ok이 고 그렇지 않으면 E_FAIL 또는 일부 다른 오류 코드입니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** CorSym.idl, CorSym.h  
  
## <a name="see-also"></a>참고자료
- [ISymUnmanagedWriter 인터페이스](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)
