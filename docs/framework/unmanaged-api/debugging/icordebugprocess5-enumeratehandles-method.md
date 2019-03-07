---
title: ICorDebugProcess5::EnumerateHandles 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugProcess5.EnumerateHandles
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess5::EnumerateHandles
helpviewer_keywords:
- EnumerateHandles method, ICorDebugProcess5 interface [.NET Framework debugging]
- ICorDebugProcess5::EnumerateHandles method [.NET Framework debugging]
ms.assetid: 7d7fa796-0dc6-4ee8-9d56-40166246d91d
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9d031754c22a62cb8d37cd5f591619d985773727
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/06/2019
ms.locfileid: "57498863"
---
# <a name="icordebugprocess5enumeratehandles-method"></a><span data-ttu-id="24aa7-102">ICorDebugProcess5::EnumerateHandles 메서드</span><span class="sxs-lookup"><span data-stu-id="24aa7-102">ICorDebugProcess5::EnumerateHandles Method</span></span>
<span data-ttu-id="24aa7-103">프로세스에서 개체 핸들에 대 한 열거자를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="24aa7-103">Gets an enumerator for object handles in a process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="24aa7-104">구문</span><span class="sxs-lookup"><span data-stu-id="24aa7-104">Syntax</span></span>  
  
```  
HRESULT EnumerateHandles(     [in] CorGCReferenceType types,  
    [out] ICorDebugGCReferenceEnum **ppEnum);  
```  
  
## <a name="parameters"></a><span data-ttu-id="24aa7-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="24aa7-105">Parameters</span></span>  
 `types`  
 <span data-ttu-id="24aa7-106">[in] 비트 조합 [CorGCReferenceType](../../../../docs/framework/unmanaged-api/debugging/corgcreferencetype-enumeration.md) 컬렉션에 포함 하는 핸들의 형식을 지정 하는 값입니다.</span><span class="sxs-lookup"><span data-stu-id="24aa7-106">[in] A bitwise combination of [CorGCReferenceType](../../../../docs/framework/unmanaged-api/debugging/corgcreferencetype-enumeration.md) values that specifies the type of handles to include in the collection.</span></span>  
  
 `ppENum`  
 <span data-ttu-id="24aa7-107">[out] 주소에 대 한 포인터를 [ICorDebugGCReferenceEnum](../../../../docs/framework/unmanaged-api/debugging/icordebuggcreferenceenum-interface.md) 즉 열거자 개체에 대 한 가비지 수집 되도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="24aa7-107">[out] A pointer to the address of an [ICorDebugGCReferenceEnum](../../../../docs/framework/unmanaged-api/debugging/icordebuggcreferenceenum-interface.md) that is an enumerator for the objects to be garbage-collected.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="24aa7-108">설명</span><span class="sxs-lookup"><span data-stu-id="24aa7-108">Remarks</span></span>  
 <span data-ttu-id="24aa7-109">`EnumerateHandles` 핸들 테이블의 검사를 지 원하는 도우미 함수입니다.</span><span class="sxs-lookup"><span data-stu-id="24aa7-109">`EnumerateHandles` is a helper function that supports inspection of the handle table.</span></span> <span data-ttu-id="24aa7-110">비슷합니다는 [ICorDebugProcess5::EnumerateGCReferences](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enumerategcreferences-method.md) 메서드 대신 채우기는 [ICorDebugGCReferenceEnum](../../../../docs/framework/unmanaged-api/debugging/icordebuggcreferenceenum-interface.md) 가비지 수집 되도록 모든 개체를 사용 하 여 컬렉션 것 핸들 테이블의 핸들이 있는 개체만을 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="24aa7-110">It is similar to the [ICorDebugProcess5::EnumerateGCReferences](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enumerategcreferences-method.md) method, except that rather than populating an [ICorDebugGCReferenceEnum](../../../../docs/framework/unmanaged-api/debugging/icordebuggcreferenceenum-interface.md) collection with all objects to be garbage-collected, it includes only objects that have handles from the handle table.</span></span>  
  
 <span data-ttu-id="24aa7-111">`types` 매개 변수 컬렉션에 포함할 핸들 형식을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="24aa7-111">The `types` parameter specifies the handle types to include in the collection.</span></span> <span data-ttu-id="24aa7-112">`types` 다음 세 가지 멤버 중 하나일 수 있습니다 합니다 [CorGCReferenceType](../../../../docs/framework/unmanaged-api/debugging/corgcreferencetype-enumeration.md) 열거형:</span><span class="sxs-lookup"><span data-stu-id="24aa7-112">`types` can be any of the following three members of the [CorGCReferenceType](../../../../docs/framework/unmanaged-api/debugging/corgcreferencetype-enumeration.md) enumeration:</span></span>  
  
-   <span data-ttu-id="24aa7-113">`CorHandleStrongOnly` (핸들 강력한 참조의 경우에 해당)입니다.</span><span class="sxs-lookup"><span data-stu-id="24aa7-113">`CorHandleStrongOnly` (handles to strong references only).</span></span>  
  
-   <span data-ttu-id="24aa7-114">`CorHandleWeakOnly` (핸들 약한 참조의 경우에 해당)입니다.</span><span class="sxs-lookup"><span data-stu-id="24aa7-114">`CorHandleWeakOnly` (handles to weak references only).</span></span>  
  
-   <span data-ttu-id="24aa7-115">`CorHandleAll` (모든 핸들)입니다.</span><span class="sxs-lookup"><span data-stu-id="24aa7-115">`CorHandleAll` (all handles).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="24aa7-116">요구 사항</span><span class="sxs-lookup"><span data-stu-id="24aa7-116">Requirements</span></span>  
 <span data-ttu-id="24aa7-117">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="24aa7-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="24aa7-118">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="24aa7-118">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="24aa7-119">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="24aa7-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="24aa7-120">**.NET Framework 버전:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="24aa7-120">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="24aa7-121">참고자료</span><span class="sxs-lookup"><span data-stu-id="24aa7-121">See also</span></span>
- [<span data-ttu-id="24aa7-122">디버깅 구조체</span><span class="sxs-lookup"><span data-stu-id="24aa7-122">Debugging Structures</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)
- [<span data-ttu-id="24aa7-123">디버깅</span><span class="sxs-lookup"><span data-stu-id="24aa7-123">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
