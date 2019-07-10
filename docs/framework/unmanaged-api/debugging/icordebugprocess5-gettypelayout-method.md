---
title: ICorDebugProcess5::GetTypeLayout 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugProcess5.GetTypeLayout
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess5::GetTypeLayout
helpviewer_keywords:
- ICorDebugProcess5::GetTypeLayout method [.NET Framework debugging]
- GetTypeLayout method, ICorDebugProcess5 interface [.NET Framework debugging]
ms.assetid: bd62f5d1-e874-41f1-81e5-a29a7572c15d
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ee556f559a7dc4c271f110f7bba4c86b675c3511
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/10/2019
ms.locfileid: "67736499"
---
# <a name="icordebugprocess5gettypelayout-method"></a><span data-ttu-id="51e38-102">ICorDebugProcess5::GetTypeLayout 메서드</span><span class="sxs-lookup"><span data-stu-id="51e38-102">ICorDebugProcess5::GetTypeLayout Method</span></span>
<span data-ttu-id="51e38-103">해당 형식 식별자를 기반으로 하는 메모리에서 개체의 레이아웃에 대 한 정보를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="51e38-103">Gets information about the layout of an object in memory based on its type identifier.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="51e38-104">구문</span><span class="sxs-lookup"><span data-stu-id="51e38-104">Syntax</span></span>  
  
```cpp  
HRESULT GetTypeLayout(    [in] COR_TYPEID id,     [out] COR_TYPE_LAYOUT *pLayout);  
```  
  
## <a name="parameters"></a><span data-ttu-id="51e38-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="51e38-105">Parameters</span></span>  
 `id`  
 <span data-ttu-id="51e38-106">[in] A [COR_TYPEID](../../../../docs/framework/unmanaged-api/debugging/cor-typeid-structure.md) 해당 레이아웃이 필요한 형식을 지정 하는 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="51e38-106">[in] A [COR_TYPEID](../../../../docs/framework/unmanaged-api/debugging/cor-typeid-structure.md) token that specifies the type whose layout is desired.</span></span>  
  
 `pLayout`  
 <span data-ttu-id="51e38-107">[out] 에 대 한 포인터를 [COR_TYPE_LAYOUT](../../../../docs/framework/unmanaged-api/debugging/cor-type-layout-structure.md) 메모리에서 개체의 레이아웃에 대 한 정보를 포함 하는 구조입니다.</span><span class="sxs-lookup"><span data-stu-id="51e38-107">[out] A pointer to a [COR_TYPE_LAYOUT](../../../../docs/framework/unmanaged-api/debugging/cor-type-layout-structure.md) structure that contains information about the layout of the object in memory.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="51e38-108">설명</span><span class="sxs-lookup"><span data-stu-id="51e38-108">Remarks</span></span>  
 <span data-ttu-id="51e38-109">합니다 `ICorDebugProcess5::GetTypeLayout` 메서드를 기반으로 개체에 대 한 정보를 제공 합니다. 해당 [COR_TYPEID](../../../../docs/framework/unmanaged-api/debugging/cor-typeid-structure.md)를 다른 숫자로 반환 되는 [ICorDebugProcess5](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-interface.md) 메서드.</span><span class="sxs-lookup"><span data-stu-id="51e38-109">The `ICorDebugProcess5::GetTypeLayout` method provides information about an object based on its [COR_TYPEID](../../../../docs/framework/unmanaged-api/debugging/cor-typeid-structure.md), which is returned by a number of other [ICorDebugProcess5](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-interface.md) methods.</span></span> <span data-ttu-id="51e38-110">제공한 정보는 [COR_TYPE_LAYOUT](../../../../docs/framework/unmanaged-api/debugging/cor-type-layout-structure.md) 메서드에 의해 채워지는 구조입니다.</span><span class="sxs-lookup"><span data-stu-id="51e38-110">The information is provided by a [COR_TYPE_LAYOUT](../../../../docs/framework/unmanaged-api/debugging/cor-type-layout-structure.md) structure that is populated by the method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="51e38-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="51e38-111">Requirements</span></span>  
 <span data-ttu-id="51e38-112">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="51e38-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="51e38-113">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="51e38-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="51e38-114">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="51e38-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="51e38-115">**.NET Framework 버전:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="51e38-115">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="51e38-116">참고자료</span><span class="sxs-lookup"><span data-stu-id="51e38-116">See also</span></span>

- [<span data-ttu-id="51e38-117">COR_TYPE_LAYOUT 구조체</span><span class="sxs-lookup"><span data-stu-id="51e38-117">COR_TYPE_LAYOUT Structure</span></span>](../../../../docs/framework/unmanaged-api/debugging/cor-type-layout-structure.md)
- [<span data-ttu-id="51e38-118">ICorDebugProcess5 인터페이스</span><span class="sxs-lookup"><span data-stu-id="51e38-118">ICorDebugProcess5 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-interface.md)
- [<span data-ttu-id="51e38-119">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="51e38-119">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
