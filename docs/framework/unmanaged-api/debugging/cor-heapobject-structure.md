---
title: COR_HEAPOBJECT 구조체
ms.date: 03/30/2017
api_name:
- COR_HEAPOBJECT
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- COR_HEAPOBJECT
helpviewer_keywords:
- COR_HEAPOBJECT structure [.NET Framework debugging]
ms.assetid: a92fdf95-492b-49ae-a741-2186e5c1d7c5
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f179b58ff8eb51e2843780d3212cf38ed7d13216
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59168833"
---
# <a name="corheapobject-structure"></a><span data-ttu-id="6cb91-102">COR_HEAPOBJECT 구조체</span><span class="sxs-lookup"><span data-stu-id="6cb91-102">COR_HEAPOBJECT Structure</span></span>
<span data-ttu-id="6cb91-103">관리되는 힙의 개체에 대한 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="6cb91-103">Provides information about an object on the managed heap.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6cb91-104">구문</span><span class="sxs-lookup"><span data-stu-id="6cb91-104">Syntax</span></span>  
  
```  
typedef struct _COR_HEAPOBJECT {  
    CORDB_ADDRESS address;    
    ULONG64 size;             
    COR_TYPEID type;          
} COR_HEAPOBJECT;  
```  
  
## <a name="members"></a><span data-ttu-id="6cb91-105">멤버</span><span class="sxs-lookup"><span data-stu-id="6cb91-105">Members</span></span>  
  
|<span data-ttu-id="6cb91-106">멤버</span><span class="sxs-lookup"><span data-stu-id="6cb91-106">Member</span></span>|<span data-ttu-id="6cb91-107">설명</span><span class="sxs-lookup"><span data-stu-id="6cb91-107">Description</span></span>|  
|------------|-----------------|  
|`address`|<span data-ttu-id="6cb91-108">메모리에 있는 개체의 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="6cb91-108">The address of the object in memory.</span></span>|  
|`size`|<span data-ttu-id="6cb91-109">총 크기 (바이트)는 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="6cb91-109">The total size of the object, in bytes.</span></span>|  
|`type`|<span data-ttu-id="6cb91-110">A [COR_TYPEID](../../../../docs/framework/unmanaged-api/debugging/cor-typeid-structure.md) 개체의 형식을 나타내는 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="6cb91-110">A [COR_TYPEID](../../../../docs/framework/unmanaged-api/debugging/cor-typeid-structure.md) token that represents the type of the object.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6cb91-111">설명</span><span class="sxs-lookup"><span data-stu-id="6cb91-111">Remarks</span></span>  
 <span data-ttu-id="6cb91-112">`COR_HEAPOBJECT` 인스턴스를 열거 하 여 검색할 수는 [ICorDebugHeapEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugheapenum-interface.md) 를 호출 하 여 채워지는 인터페이스 개체를 [ICorDebugProcess5::EnumerateHeap](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enumerateheap-method.md) 메서드.</span><span class="sxs-lookup"><span data-stu-id="6cb91-112">`COR_HEAPOBJECT` instances can be retrieved by enumerating an [ICorDebugHeapEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugheapenum-interface.md) interface object that is populated by calling the [ICorDebugProcess5::EnumerateHeap](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enumerateheap-method.md) method.</span></span>  
  
 <span data-ttu-id="6cb91-113">`COR_HEAPOBJECT` 인스턴스 또는 관리 되는 힙에 대 한 활성 개체에 대 한 모든 개체에서 루 팅 되지 않지만 가비지 수집기에 의해 아직 수집 되지 않았습니다 하는 개체에 대 한 정보를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="6cb91-113">A `COR_HEAPOBJECT` instance provides information either about a live object on the managed heap, or about an object that is not rooted by any object but has not yet been collected by the garbage collector.</span></span>  
  
 <span data-ttu-id="6cb91-114">성능 향상을 위해 합니다 `COR_HEAPOBJECT.address` 필드는는 `CORDB_ADDRESS` 는 ICorDebugValue이 아닌 값 인터페이스 디버깅 API의 대부분에서 사용 되는 값입니다.</span><span class="sxs-lookup"><span data-stu-id="6cb91-114">For better performance, the `COR_HEAPOBJECT.address` field is a `CORDB_ADDRESS` value rather than the ICorDebugValue interface value used in much of the debugging API.</span></span> <span data-ttu-id="6cb91-115">ICorDebugValue 개체에 지정 된 개체 주소를 가져오려면 전달할 수 있습니다 합니다 `CORDB_ADDRESS` 값을 [ICorDebugProcess5::GetObject](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-getobject-method.md) 메서드.</span><span class="sxs-lookup"><span data-stu-id="6cb91-115">To obtain an ICorDebugValue object for a given object address, you can pass the `CORDB_ADDRESS` value to the [ICorDebugProcess5::GetObject](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-getobject-method.md) method.</span></span>  
  
 <span data-ttu-id="6cb91-116">성능 향상을 위해 합니다 `COR_HEAPOBJECT.type` 필드는는 `COR_TYPEID` ICorDebugType이 아닌 값 인터페이스 디버깅 API의 대부분에서 사용 되는 값입니다.</span><span class="sxs-lookup"><span data-stu-id="6cb91-116">For better performance, the `COR_HEAPOBJECT.type` field is a `COR_TYPEID` value rather than the ICorDebugType interface value used in much of the debugging API.</span></span> <span data-ttu-id="6cb91-117">ICorDebugType 개체로 지정 된 형식 id를 가져오려면 전달할 수 있습니다 합니다 `COR_TYPEID` 값을 [ICorDebugProcess5::GetTypeForTypeID](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-gettypefortypeid-method.md) 메서드.</span><span class="sxs-lookup"><span data-stu-id="6cb91-117">To obtain an ICorDebugType object for a given type ID, you can pass the `COR_TYPEID` value to the [ICorDebugProcess5::GetTypeForTypeID](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-gettypefortypeid-method.md) method.</span></span>  
  
 <span data-ttu-id="6cb91-118">`COR_HEAPOBJECT` 구조 참조 횟수가 계산 되는 COM 인터페이스를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="6cb91-118">The `COR_HEAPOBJECT` structure includes a reference-counted COM interface.</span></span> <span data-ttu-id="6cb91-119">검색 하는 경우는 `COR_HEAPOBJECT` 를 호출 하 여 열거자 인스턴스를 [icordebugheapenum:: Next](../../../../docs/framework/unmanaged-api/debugging/icordebugheapenum-next-method.md) 메서드를 이후에 대 한 참조를 해제 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6cb91-119">If you retrieve a `COR_HEAPOBJECT` instance from the enumerator by calling the [ICorDebugHeapEnum::Next](../../../../docs/framework/unmanaged-api/debugging/icordebugheapenum-next-method.md) method, you must subsequently release the reference.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6cb91-120">요구 사항</span><span class="sxs-lookup"><span data-stu-id="6cb91-120">Requirements</span></span>  
 <span data-ttu-id="6cb91-121">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="6cb91-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6cb91-122">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="6cb91-122">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="6cb91-123">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6cb91-123">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6cb91-124">**.NET Framework 버전:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6cb91-124">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6cb91-125">참고자료</span><span class="sxs-lookup"><span data-stu-id="6cb91-125">See also</span></span>

- [<span data-ttu-id="6cb91-126">디버깅 구조체</span><span class="sxs-lookup"><span data-stu-id="6cb91-126">Debugging Structures</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)
- [<span data-ttu-id="6cb91-127">디버깅</span><span class="sxs-lookup"><span data-stu-id="6cb91-127">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
