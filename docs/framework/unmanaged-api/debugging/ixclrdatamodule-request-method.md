---
title: IXCLRDataModule::Request 메서드
ms.date: 01/16/2019
api.name:
- IXCLRDataModule::Request Method
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- IXCLRDataModule::Request Method
helpviewer.keywords:
- IXCLRDataModule::Request Method [.NET Framework debugging]
topic_type:
- apiref
author: cshung
ms.author: andrewau
ms.openlocfilehash: 0226a11b142515296d976e3d645cb2475d634420
ms.sourcegitcommit: b56d59ad42140d277f2acbd003b74d655fdbc9f1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/19/2019
ms.locfileid: "54416588"
---
# <a name="ixclrdatamodulerequest-method"></a>IXCLRDataModule::Request 메서드

모듈의 데이터를 사용 하 여 지정 된 버퍼를 채우는 데 요청 합니다.

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a>구문
```
HRESULT Request([in] ULONG32 reqCode,
    [in] ULONG32 inBufferSize,
    [in, size_is(inBufferSize)] BYTE* inBuffer,
    [in] ULONG32 outBufferSize,
    [out, size_is(outBufferSize)] BYTE* outBuffer);
```

### <a name="parameters"></a>매개 변수

`reqCode` [in] 요청 전송 하는 유형입니다.

`inBufferSize` [in]에 전달 되어야 하는 입력된 버퍼의 크기입니다.

`inBuffer` [in, size_is(inBufferSize)] 요청에서 보낼 원시 데이터에 대 한 버퍼 포인터입니다.

`outBufferSize` [in] 출력 버퍼의 크기입니다.

`outBuffer` [out, size_is(outBufferSize)] 요청 응답을 저장 하는 데 버퍼 포인터입니다.

## <a name="remarks"></a>설명

제공 된 메서드는의 일부는 `IXCLRDataModule` 인터페이스 및 가상 메서드 테이블의 36th 슬롯에 해당 합니다.

## <a name="requirements"></a>요구 사항

**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.  
**헤더:** 없음   
**라이브러리:** 없음  
**.NET Framework 버전:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]  

## <a name="see-also"></a>참고 항목
- [디버깅](../../../../docs/framework/unmanaged-api/debugging/index.md)
- [IXCLRDataModule 인터페이스](../../../../docs/framework/unmanaged-api/debugging/ixclrdatamodule-interface.md)
