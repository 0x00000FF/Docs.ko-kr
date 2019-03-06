---
title: ICorDebugProcess5::GetTypeID 메서드
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- ICorDebugProcess5.GetTypeID
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess5::GetTypeID
helpviewer_keywords:
- ICorDebugProcess5::GetTypeID method [.NET Framework debugging]
- GetTypeID method, ICorDebugProcess5 interface [.NET Framework debugging]
ms.assetid: 47dbaea4-8857-462e-93ba-fff880fc9e50
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f58e4213959ca1cd6e65bc809a9ad964bebc31ae
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/06/2019
ms.locfileid: "57494794"
---
# <a name="icordebugprocess5gettypeid-method"></a><span data-ttu-id="970a5-102">ICorDebugProcess5::GetTypeID 메서드</span><span class="sxs-lookup"><span data-stu-id="970a5-102">ICorDebugProcess5::GetTypeID Method</span></span>
<span data-ttu-id="970a5-103">개체의 주소를 변환 된 [COR_TYPEID](../../../../docs/framework/unmanaged-api/debugging/cor-typeid-structure.md) 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="970a5-103">Converts an object address to a [COR_TYPEID](../../../../docs/framework/unmanaged-api/debugging/cor-typeid-structure.md) identifier.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="970a5-104">구문</span><span class="sxs-lookup"><span data-stu-id="970a5-104">Syntax</span></span>  
  
```cpp
HRESULT GetTypeID(  
    [in] CORDB_ADDRESS obj,  
    [out] COR_TYPEID *pId  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="970a5-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="970a5-105">Parameters</span></span>  
 `obj`  
 <span data-ttu-id="970a5-106">[in] 개체 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="970a5-106">[in] The object address.</span></span>  
  
 `pId`  
 <span data-ttu-id="970a5-107">에 대 한 포인터를 [COR_TYPEID](../../../../docs/framework/unmanaged-api/debugging/cor-typeid-structure.md) 개체를 식별 하는 값입니다.</span><span class="sxs-lookup"><span data-stu-id="970a5-107">A pointer to the [COR_TYPEID](../../../../docs/framework/unmanaged-api/debugging/cor-typeid-structure.md) value that identifies the object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="970a5-108">설명</span><span class="sxs-lookup"><span data-stu-id="970a5-108">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="970a5-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="970a5-109">Requirements</span></span>  
 <span data-ttu-id="970a5-110">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="970a5-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="970a5-111">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="970a5-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="970a5-112">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="970a5-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="970a5-113">**.NET Framework 버전:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="970a5-113">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="970a5-114">참고자료</span><span class="sxs-lookup"><span data-stu-id="970a5-114">See also</span></span>
- [<span data-ttu-id="970a5-115">ICorDebugProcess5 인터페이스</span><span class="sxs-lookup"><span data-stu-id="970a5-115">ICorDebugProcess5 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-interface.md)
- [<span data-ttu-id="970a5-116">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="970a5-116">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
