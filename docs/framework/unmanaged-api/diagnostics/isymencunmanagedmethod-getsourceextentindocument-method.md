---
title: ISymENCUnmanagedMethod::GetSourceExtentInDocument 메서드
ms.date: 03/30/2017
api_name:
- ISymENCUnmanagedMethod.GetSourceExtentInDocument
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymENCUnmanagedMethod::GetSourceExtentInDocument
helpviewer_keywords:
- GetSourceExtentInDocument method [.NET Framework debugging]
- ISymENCUnmanagedMethod::GetSourceExtentInDocument method [.NET Framework debugging]
ms.assetid: 9c5566ab-4ec7-4b61-9753-839bb90ae78c
topic_type:
- apiref
ms.openlocfilehash: 3ac8bb3a20ce82b734a572832a9cbb75fa2568c4
ms.sourcegitcommit: 7b1497c1927cb449cefd313bc5126ae37df30746
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/16/2020
ms.locfileid: "83441905"
---
# <a name="isymencunmanagedmethodgetsourceextentindocument-method"></a>ISymENCUnmanagedMethod::GetSourceExtentInDocument 메서드
특정 문서에서 메서드의 가장 작은 시작 줄과 가장 큰 끝 줄을 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT GetSourceExtentInDocument(  
    [in]  ISymUnmanagedDocument *document,  
    [out] ULONG32* pstartLine,  
    [out] ULONG32* pendLine);  
```  
  
## <a name="parameters"></a>매개 변수  
 `document`  
 진행 문서에 대 한 포인터입니다.  
  
 `pstartLine`  
 제한이 시작 줄을 수신 하는에 대 한 포인터 `ULONG32` 입니다.  
  
 `pendLine`  
 제한이 `ULONG32`끝 줄을 수신 하는에 대 한 포인터입니다.  
  
## <a name="return-value"></a>Return Value  
 메서드가 성공 하면이 고, 그렇지 않으면 S_OK입니다. 그렇지 않으면 E_FAIL 또는 일부 다른 오류 코드입니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** CorSym, CorSym  
  
## <a name="see-also"></a>참고 항목

- [ISymENCUnmanagedMethod 인터페이스](isymencunmanagedmethod-interface.md)
