---
title: ICorDebugModule2::ResolveAssembly 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugModule2.ResolveAssembly
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugModule2::ResolveAssembly
helpviewer_keywords:
- ICorDebugModule2::ResolveAssembly method [.NET Framework debugging]
- ResolveAssembly method [.NET Framework debugging]
ms.assetid: ddf9085c-7161-44bd-9609-cd2732b9009f
topic_type:
- apiref
ms.openlocfilehash: e64e39d10d20f63430ffe9d2c4df8643e286a677
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/12/2020
ms.locfileid: "83210038"
---
# <a name="icordebugmodule2resolveassembly-method"></a>ICorDebugModule2::ResolveAssembly 메서드

지정 된 메타 데이터 토큰에서 참조 하는 어셈블리를 확인 합니다.

## <a name="syntax"></a>구문

```cpp
HRESULT ResolveAssembly (
    [in]  mdToken             tkAssemblyRef,
    [out] ICorDebugAssembly   **ppAssembly
);
```

## <a name="parameters"></a>매개 변수

`tkAssemblyRef`\
진행 `mdToken`어셈블리를 참조 하는 값입니다.

`ppAssembly`\
제한이 어셈블리를 나타내는 ICorDebugAssembly 개체의 주소에 대 한 포인터입니다.

## <a name="remarks"></a>설명

가 호출 될 때 어셈블리가 아직 로드 되지 않은 경우에는 `ResolveAssembly` HRESULT 값이 CORDBG_E_CANNOT_RESOLVE_ASSEMBLY 반환 됩니다.

## <a name="requirements"></a>요구 사항

**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.

**헤더:** CorDebug.idl, CorDebug.h

**라이브러리:** CorGuids.lib

**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
