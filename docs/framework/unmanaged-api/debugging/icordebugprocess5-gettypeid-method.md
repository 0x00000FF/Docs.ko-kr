---
title: "ICorDebugProcess5::GetTypeID 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs: cpp
api_name: ICorDebugProcess5.GetTypeID
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugProcess5::GetTypeID
helpviewer_keywords:
- ICorDebugProcess5::GetTypeID method [.NET Framework debugging]
- GetTypeID method, ICorDebugProcess5 interface [.NET Framework debugging]
ms.assetid: 47dbaea4-8857-462e-93ba-fff880fc9e50
topic_type: apiref
caps.latest.revision: "5"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 0f76285fceaa32f7c8b62b5cdf2ae7b4e9ec00de
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugprocess5gettypeid-method"></a><span data-ttu-id="220de-102">ICorDebugProcess5::GetTypeID 메서드</span><span class="sxs-lookup"><span data-stu-id="220de-102">ICorDebugProcess5::GetTypeID Method</span></span>
<span data-ttu-id="220de-103">개체의 주소를 변환는 [COR_TYPEID](../../../../docs/framework/unmanaged-api/debugging/cor-typeid-structure.md) 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="220de-103">Converts an object address to a [COR_TYPEID](../../../../docs/framework/unmanaged-api/debugging/cor-typeid-structure.md) identifier.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="220de-104">구문</span><span class="sxs-lookup"><span data-stu-id="220de-104">Syntax</span></span>  
  
```cpp
HRESULT GetTypeID(  
    [in] CORDB_ADDRESS obj,  
    [out] COR_TYPEID *pId  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="220de-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="220de-105">Parameters</span></span>  
 `obj`  
 <span data-ttu-id="220de-106">[in] 개체의 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="220de-106">[in] The object address.</span></span>  
  
 `pId`  
 <span data-ttu-id="220de-107">에 대 한 포인터는 [COR_TYPEID](../../../../docs/framework/unmanaged-api/debugging/cor-typeid-structure.md) 개체를 식별 하는 값입니다.</span><span class="sxs-lookup"><span data-stu-id="220de-107">A pointer to the [COR_TYPEID](../../../../docs/framework/unmanaged-api/debugging/cor-typeid-structure.md) value that identifies the object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="220de-108">설명</span><span class="sxs-lookup"><span data-stu-id="220de-108">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="220de-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="220de-109">Requirements</span></span>  
 <span data-ttu-id="220de-110">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="220de-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="220de-111">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="220de-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="220de-112">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="220de-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="220de-113">**.NET framework 버전:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="220de-113">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="220de-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="220de-114">See Also</span></span>  
 [<span data-ttu-id="220de-115">ICorDebugProcess5 인터페이스</span><span class="sxs-lookup"><span data-stu-id="220de-115">ICorDebugProcess5 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-interface.md)  
 [<span data-ttu-id="220de-116">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="220de-116">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
