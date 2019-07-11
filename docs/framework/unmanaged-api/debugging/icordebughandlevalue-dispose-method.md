---
title: ICorDebugHandleValue::Dispose 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugHandleValue.Dispose
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugHandleValue::Dispose
helpviewer_keywords:
- ICorDebugHandleValue::Dispose method [.NET Framework debugging]
- Dispose method [.NET Framework debugging]
ms.assetid: c1542811-0a7f-4235-bcfd-b24370d6f24b
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d21703aa911b5222fff71282e6da26aa5c0e2853
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/10/2019
ms.locfileid: "67756850"
---
# <a name="icordebughandlevaluedispose-method"></a><span data-ttu-id="7a9cb-102">ICorDebugHandleValue::Dispose 메서드</span><span class="sxs-lookup"><span data-stu-id="7a9cb-102">ICorDebugHandleValue::Dispose Method</span></span>
<span data-ttu-id="7a9cb-103">명시적으로 인터페이스 포인터를 해제 하지 않고이 ICorDebugHandleValue 개체에서 참조 하는 핸들을 해제 합니다.</span><span class="sxs-lookup"><span data-stu-id="7a9cb-103">Releases the handle referenced by this ICorDebugHandleValue object without explicitly releasing the interface pointer.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7a9cb-104">구문</span><span class="sxs-lookup"><span data-stu-id="7a9cb-104">Syntax</span></span>  
  
```cpp  
HRESULT Dispose ();  
```  
  
## <a name="requirements"></a><span data-ttu-id="7a9cb-105">요구 사항</span><span class="sxs-lookup"><span data-stu-id="7a9cb-105">Requirements</span></span>  
 <span data-ttu-id="7a9cb-106">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="7a9cb-106">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7a9cb-107">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="7a9cb-107">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="7a9cb-108">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7a9cb-108">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7a9cb-109">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7a9cb-109">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
