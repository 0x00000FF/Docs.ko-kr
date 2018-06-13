---
title: IMetaDataEmit2::DefineMethodSpec 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataEmit2.DefineMethodSpec
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit2::DefineMethodSpec
helpviewer_keywords:
- DefineMethodSpec method [.NET Framework metadata]
- IMetaDataEmit2::DefineMethodSpec method [.NET Framework metadata]
ms.assetid: 3c24e552-fc69-4971-b65a-a3e4b5f7f1e8
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 85b17199ad40d8b3fbf4e1a0271828e5a5ac7991
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33445262"
---
# <a name="imetadataemit2definemethodspec-method"></a>IMetaDataEmit2::DefineMethodSpec 메서드
메서드의 제네릭 인스턴스를 만들고 정의에 토큰을 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT DefineMethodSpec (  
    [in]  mdToken           tkParent,   
    [in]  PCCOR_SIGNATURE   pvSigBlob,   
    [in]  ULONG             cbSigBlob,   
    [out] mdMethodSpec      *pmi  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `tkParent`  
 [in] 제네릭 인스턴스를 만들려고 하는 방법에는 토큰입니다. 토큰 형식 이어야 합니다 `mdMethodDef` 또는 `mdMemberRef`합니다.  
  
 `pvSigBlob`  
 [in] 이진 COM + 메서드의 서명에 대 한 포인터입니다.  
  
 `cbSibBlob`  
 [in] 를 바이트 단위로 크기의 `pvSigBlob`합니다.  
  
 `pmi`  
 [out] 메서드의 메타 데이터 서명 정의에 토큰입니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** Cor.h  
  
 **라이브러리:** MsCorEE.dll에서 리소스로 사용  
  
 **.NET framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [IMetaDataEmit2 인터페이스](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)  
 [IMetaDataEmit 인터페이스](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
