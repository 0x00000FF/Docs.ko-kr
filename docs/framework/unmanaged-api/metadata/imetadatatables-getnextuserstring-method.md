---
title: IMetaDataTables::GetNextUserString 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataTables.GetNextUserString
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataTables::GetNextUserString
helpviewer_keywords:
- GetNextUserString method [.NET Framework metadata]
- IMetaDataTables::GetNextUserString method [.NET Framework metadata]
ms.assetid: b7cb40ee-67b7-4f4e-8dcc-ee7ac8bc986b
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 01b326765e792bf97658d951a2d5590d22eff546
ms.sourcegitcommit: fb78d8abbdb87144a3872cf154930157090dd933
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/26/2018
ms.locfileid: "47192546"
---
# <a name="imetadatatablesgetnextuserstring-method"></a>IMetaDataTables::GetNextUserString 메서드
현재 테이블 열에 다음 하드 코드 된 문자열을 포함 하는 행의 인덱스를 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT GetNextUserString (  
    [in]  ULONG   ixUserString,  
    [out] ULONG   *pNext  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `ixUserString`  
 [in] 현재 문자열 열을 인덱스 값입니다.  
  
 `pNext`  
 [out] 열에 다음 문자열의 행 인덱스에 대 한 포인터입니다.  
  
## <a name="remarks"></a>설명  
 바람직하지 않습니다이 메서드를 사용 하 여 일관 된 결과 반환 하지 않습니다. GUID 테이블에 대 한 내용은 "II: 메타 데이터 정의 및 의미" 공용 언어 인프라 (CLI) 설명서를 참조 하세요. 이 설명서는 온라인으로 제공됩니다. MSDN의 [ECMA C# 및 공용 언어 인프라 표준](https://go.microsoft.com/fwlink/?LinkID=99212) 및 Ecma International 웹 사이트의 [표준 ECMA-335 - CLI(공용 언어 인프라)](https://go.microsoft.com/fwlink/?LinkID=65552)를 참조하세요.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** Cor.h  
  
 **라이브러리:** MsCorEE.dll에서 리소스로 사용  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [IMetaDataTables 인터페이스](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-interface.md)  
 [IMetaDataTables2 인터페이스](../../../../docs/framework/unmanaged-api/metadata/imetadatatables2-interface.md)
