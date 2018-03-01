---
title: "ICorDebugGenericValue::SetValue 메서드"
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
- ICorDebugGenericValue.SetValue
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugGenericValue::SetValue
helpviewer_keywords:
- ICorDebugGenericValue::SetValue method [.NET Framework debugging]
- SetValue method, ICorDebugGenericValue interface [.NET Framework debugging]
ms.assetid: ed4c6458-0435-44fc-8e78-8ba00be362f2
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 11cb4ab6d32f3dbada25fe42f062fdc2c1fabd17
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="icordebuggenericvaluesetvalue-method"></a><span data-ttu-id="352bb-102">ICorDebugGenericValue::SetValue 메서드</span><span class="sxs-lookup"><span data-stu-id="352bb-102">ICorDebugGenericValue::SetValue Method</span></span>
<span data-ttu-id="352bb-103">지정된 된 버퍼에서 새 값을 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="352bb-103">Copies a new value from the specified buffer.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="352bb-104">구문</span><span class="sxs-lookup"><span data-stu-id="352bb-104">Syntax</span></span>  
  
```  
HRESULT SetValue (  
    [in] void      *pFrom  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="352bb-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="352bb-105">Parameters</span></span>  
 `pFrom`  
 <span data-ttu-id="352bb-106">[in] 값을 복사할 대상 버퍼에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="352bb-106">[in] A pointer to the buffer from which to copy the value.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="352bb-107">설명</span><span class="sxs-lookup"><span data-stu-id="352bb-107">Remarks</span></span>  
 <span data-ttu-id="352bb-108">참조 형식의 경우 값은 콘텐츠가 아니라 참조 합니다.</span><span class="sxs-lookup"><span data-stu-id="352bb-108">For reference types, the value is the reference, not the content.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="352bb-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="352bb-109">Requirements</span></span>  
 <span data-ttu-id="352bb-110">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="352bb-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="352bb-111">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="352bb-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="352bb-112">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="352bb-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="352bb-113">**.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="352bb-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
