---
title: "ICorDebugArrayValue::GetBaseIndicies 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugArrayValue.GetBaseIndicies
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugArrayValue::GetBaseIndicies
helpviewer_keywords:
- ICorDebugArrayValue::GetBaseIndicies method [.NET Framework debugging]
- GetBaseIndicies method [.NET Framework debugging]
ms.assetid: 868b339b-acdb-4fe0-91c7-b85f4fba99eb
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 820d81b4538c3cf2bf6fa123df2012ea06e2d978
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugarrayvaluegetbaseindicies-method"></a><span data-ttu-id="6d16d-102">ICorDebugArrayValue::GetBaseIndicies 메서드</span><span class="sxs-lookup"><span data-stu-id="6d16d-102">ICorDebugArrayValue::GetBaseIndicies Method</span></span>
<span data-ttu-id="6d16d-103">배열의 각 차원에 대 한 기본 인덱스를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="6d16d-103">Gets the base index of each dimension in the array.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6d16d-104">구문</span><span class="sxs-lookup"><span data-stu-id="6d16d-104">Syntax</span></span>  
  
```  
HRESULT GetBaseIndicies (  
    [in] ULONG32          cdim,  
    [out, size_is(cdim), length_is(cdim)]   
        ULONG32           indicies[]  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="6d16d-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="6d16d-105">Parameters</span></span>  
 `cdim`  
 <span data-ttu-id="6d16d-106">[in] 이 차원 수가 `ICorDebugArrayValue` 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="6d16d-106">[in] The number of dimensions of this `ICorDebugArrayValue` object.</span></span> <span data-ttu-id="6d16d-107">또한이 값은의 크기는 `indicies` 배열 크기의 차원 수와 같은지는 `ICorDebugArrayValue` 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="6d16d-107">This value is also the size of the `indicies` array because its size is equal to the number of dimensions of the `ICorDebugArrayValue` object.</span></span>  
  
 `indicies`  
 <span data-ttu-id="6d16d-108">[out] 이 차원의 기본 인덱스 (즉, 시작 인덱스)은 각각 정수, 배열 `ICorDebugArrayValue` 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="6d16d-108">[out] An array of integers, each of which is the base index (that is, the starting index) of a dimension of this `ICorDebugArrayValue` object.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6d16d-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="6d16d-109">Requirements</span></span>  
 <span data-ttu-id="6d16d-110">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="6d16d-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6d16d-111">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="6d16d-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="6d16d-112">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6d16d-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6d16d-113">**.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6d16d-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
