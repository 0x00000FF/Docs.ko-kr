---
title: ICorDebugArrayValue::GetCount 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugArrayValue.GetCount
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugArrayValue::GetCount
helpviewer_keywords:
- ICorDebugArrayValue::GetCount method [.NET Framework debugging]
- GetCount method, ICorDebugArrayValue interface [.NET Framework debugging]
ms.assetid: 44cd98cf-2127-4d46-8c6a-da4e857bb6b0
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e45f49d17a5b71abfb58ff8c0126abad49322c5b
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/10/2019
ms.locfileid: "67737589"
---
# <a name="icordebugarrayvaluegetcount-method"></a><span data-ttu-id="7b5f6-102">ICorDebugArrayValue::GetCount 메서드</span><span class="sxs-lookup"><span data-stu-id="7b5f6-102">ICorDebugArrayValue::GetCount Method</span></span>
<span data-ttu-id="7b5f6-103">배열에 있는 요소의 총 수를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="7b5f6-103">Gets the total number of elements in the array.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7b5f6-104">구문</span><span class="sxs-lookup"><span data-stu-id="7b5f6-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCount (  
    [out] ULONG32 *pnCount  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7b5f6-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="7b5f6-105">Parameters</span></span>  
 `pnCount`  
 <span data-ttu-id="7b5f6-106">[out] 배열에 있는 요소의 총 수에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="7b5f6-106">[out] A pointer to the total number of elements in the array.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7b5f6-107">요구 사항</span><span class="sxs-lookup"><span data-stu-id="7b5f6-107">Requirements</span></span>  
 <span data-ttu-id="7b5f6-108">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="7b5f6-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7b5f6-109">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="7b5f6-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="7b5f6-110">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7b5f6-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7b5f6-111">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7b5f6-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
