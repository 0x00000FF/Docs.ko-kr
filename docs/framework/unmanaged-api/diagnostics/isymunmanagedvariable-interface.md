---
title: "ISymUnmanagedVariable 인터페이스"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- ISymUnmanagedVariable
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedVariable
helpviewer_keywords:
- ISymUnmanagedVariable interface [.NET Framework debugging]
ms.assetid: 704c69ba-77bc-40d7-8c0c-400061686321
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: e5ae8d1d05274363dc523c1a2cebf4ed09c1f461
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="isymunmanagedvariable-interface"></a>ISymUnmanagedVariable 인터페이스
매개 변수, 지역 변수 또는 필드와 같은 변수를 나타냅니다.  
  
## <a name="methods"></a>메서드  
  
|메서드|설명|  
|------------|-----------------|  
|[GetAddressField1 메서드](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-getaddressfield1-method.md)|이 변수에 대 한 첫 번째 주소 필드를 가져옵니다. 해당 의미 주소의 종류에 따라 달라 집니다.|  
|[GetAddressField2 메서드](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-getaddressfield2-method.md)|이 변수에 대 한 두 번째 주소 필드를 가져옵니다. 해당 의미 주소의 종류에 따라 달라 집니다.|  
|[GetAddressField3 메서드](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-getaddressfield3-method.md)|이 변수에 대 한 세 번째 주소 필드를 가져옵니다. 해당 의미 주소의 종류에 따라 달라 집니다.|  
|[GetAddressKind 메서드](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-getaddresskind-method.md)|이 변수의 주소가의 종류를 가져옵니다.|  
|[GetAttributes 메서드](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-getattributes-method.md)|이 변수에 대 한 특성 플래그를 가져옵니다.|  
|[GetEndOffset 메서드](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-getendoffset-method.md)|해당 부모 노드에이 변수의 끝 오프셋을 가져옵니다.|  
|[GetName 메서드](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-getname-method.md)|이 변수의 이름을 가져옵니다.|  
|[GetSignature 메서드](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-getsignature-method.md)|이 변수 시그니처를 가져옵니다.|  
|[GetStartOffset 메서드](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-getstartoffset-method.md)|해당 부모 노드에이 변수의 시작 오프셋을 가져옵니다.|  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** CorSym.idl, CorSym.h  
  
## <a name="see-also"></a>참고 항목  
 [진단 기호 저장소 인터페이스](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)
