---
title: "ISymUnmanagedDocument 인터페이스"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ISymUnmanagedDocument
api_location: diasymreader.dll
api_type: COM
f1_keywords: ISymUnmanagedDocument
helpviewer_keywords: ISymUnmanagedDocument interface [.NET Framework debugging]
ms.assetid: 5c26b366-6e81-467c-9dd0-02dd26fee0a3
topic_type: apiref
caps.latest.revision: "6"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 8654f28cc4d82a5ed1419215807ec3360522fd55
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="isymunmanageddocument-interface"></a>ISymUnmanagedDocument 인터페이스
기호 저장소가 참조하는 문서를 나타냅니다. 문서 (URL)는 uniform resource locator와 문서 형식 GUID 정의 됩니다. URL을 사용 하 여 저장 하는 방법에 관계 없이 문서를 찾을 수 있으며 문서 유형 GUID 수 있습니다. 기호 저장소에 문서 소스를 저장 하 고이 인터페이스를 통해 검색할 수 있습니다.  
  
## <a name="methods"></a>메서드  
  
|메서드|설명|  
|------------|-----------------|  
|[FindClosestLine 메서드](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocument-findclosestline-method.md)|시퀀스 포인트가 아닐 수 있는이 문서의 줄이 제공 된 시퀀스 위치가 되는 가장 가까운 줄을 반환 합니다.|  
|[GetCheckSum 메서드](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocument-getchecksum-method.md)|체크섬을 가져옵니다.|  
|[GetCheckSumAlgorithmId 메서드](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocument-getchecksumalgorithmid-method.md)|체크섬이 없는 경우에 모두 0으로 GUID를 반환 하거나 체크섬 알고리즘 식별자를 가져옵니다.|  
|[GetDocumentType 메서드](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocument-getdocumenttype-method.md)|이 문서의 문서 유형을 가져옵니다.|  
|[GetLanguage 메서드](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocument-getlanguage-method.md)|이 문서의 언어 식별자를 가져옵니다.|  
|[GetLanguageVendor 메서드](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocument-getlanguagevendor-method.md)|이 문서의 언어 공급 업체를 가져옵니다.|  
|[GetSourceLength 메서드](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocument-getsourcelength-method.md)|포함 소스의 길이(바이트)를 가져옵니다.|  
|[GetSourceRange 메서드](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocument-getsourcerange-method.md)|지정 된 버퍼로 포함된 리소스의 지정된 된 범위를 반환합니다.|  
|[GetURL 메서드](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocument-geturl-method.md)|이 문서에 대 한 URL을 반환합니다.|  
|[HasEmbeddedSource 메서드](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocument-hasembeddedsource-method.md)|반환 `true` 문서 소스 디버깅 기호;에 대해 포함 된 경우는 그렇지 않으면 반환 `false`합니다.|  
  
## <a name="see-also"></a>참고 항목  
 [진단 기호 저장소 인터페이스](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)
