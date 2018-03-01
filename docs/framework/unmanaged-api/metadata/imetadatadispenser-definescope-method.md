---
title: "IMetaDataDispenser::DefineScope 메서드"
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
- IMetaDataDispenser.DefineScope
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataDispenser::DefineScope
helpviewer_keywords:
- DefineScope method [.NET Framework metadata]
- IMetaDataDispenser::DefineScope method [.NET Framework metadata]
ms.assetid: af28db02-29af-45ac-aec6-8d6c6123c2ff
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: df7a700a5747f88f14cbfa4d10f1f4d0c2a14ab7
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="imetadatadispenserdefinescope-method"></a>IMetaDataDispenser::DefineScope 메서드
새 메타 데이터를 만들 수 있는 메모리에 새 영역을 만듭니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT DefineScope (  
    [in]  REFCLSID    rclsid,  
    [in]  DWORD       dwCreateFlags,  
    [in]  REFIID      riid,   
    [out] IUnknown    **ppIUnk  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `rclsid`  
 [in] 만들 메타 데이터 구조 버전의 CLSID입니다. 이 값은.NET Framework 버전 2.0에 대 한 CLSID_CorMetaDataRuntime 이어야 합니다.  
  
 `dwCreateFlags`  
 [in] 옵션을 지정 하는 플래그입니다. 이 값에는.NET Framework 2.0에 대 한 0 이어야 합니다.  
  
 `riid`  
 [in] 반환할; 원하는 메타 데이터 인터페이스의 IID 호출자에 게 새 메타 데이터를 만들려면 인터페이스를 사용 합니다.  
  
 값 `riid` "내보내기" 인터페이스 중 하나를 지정 해야 합니다. 유효한 값은 IID_IMetaDataEmit, IID_IMetaDataAssemblyEmit, 또는 IID_IMetaDataEmit2입니다.  
  
 `ppIUnk`  
 [out] 반환 되는 인터페이스 포인터입니다.  
  
## <a name="remarks"></a>설명  
 `DefineScope`메모리 내 메타 데이터 테이블의 집합을 만듭니다, 그리고 메타 데이터에 대 한 고유 GUID (모듈 버전 식별자 또는 MVID) 생성 및 내보낼 컴파일 단위에 대 한 모듈 테이블에 항목을 만듭니다.  
  
 사용 하 여 전체 특성 메타 데이터 범위에 연결할 수는 [imetadataemit:: Setmoduleprops](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-setmoduleprops-method.md) 또는 [imetadataemit:: Definecustomattribute](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definecustomattribute-method.md) 메서드를 적절 하 게 합니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** Cor.h  
  
 **라이브러리:** MsCorEE.dll에서 리소스로 사용  
  
 **.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [IMetaDataDispenser 인터페이스](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-interface.md)  
 [IMetaDataDispenserEx 인터페이스](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenserex-interface.md)  
 [IMetaDataAssemblyEmit 인터페이스](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)  
 [IMetaDataEmit 인터페이스](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)  
 [IMetaDataEmit2 인터페이스](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
