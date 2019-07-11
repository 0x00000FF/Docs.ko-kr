---
title: COR_GC_REFERENCE 구조체
ms.date: 03/30/2017
api_name:
- COR_GC_REFERENCE
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- COR_GC_REFERENCE
helpviewer_keywords:
- COR_GC_REFERENCE structure [.NET Framework debugging]
ms.assetid: 162e8179-0cd4-4110-8f06-5f387698bd62
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 61a9cad9d0ce807d62c811e77402b8cc6d8c6905
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/10/2019
ms.locfileid: "67740698"
---
# <a name="corgcreference-structure"></a><span data-ttu-id="9b80b-102">COR_GC_REFERENCE 구조체</span><span class="sxs-lookup"><span data-stu-id="9b80b-102">COR_GC_REFERENCE Structure</span></span>
<span data-ttu-id="9b80b-103">가비지 수집할 개체에 대한 정보를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="9b80b-103">Contains information about an object that is to be garbage-collected.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9b80b-104">구문</span><span class="sxs-lookup"><span data-stu-id="9b80b-104">Syntax</span></span>  
  
```cpp  
typedef struct _COR_GC_REFERENCE {  
    ICorDebugAppDomain *domain;   
    ICorDebugValue *location;  
    CorGCReferenceType type;  
    UINT64 extraData;  
} COR_GC_REFERENCE;  
```  
  
## <a name="members"></a><span data-ttu-id="9b80b-105">멤버</span><span class="sxs-lookup"><span data-stu-id="9b80b-105">Members</span></span>  
  
|<span data-ttu-id="9b80b-106">멤버</span><span class="sxs-lookup"><span data-stu-id="9b80b-106">Member</span></span>|<span data-ttu-id="9b80b-107">Description</span><span class="sxs-lookup"><span data-stu-id="9b80b-107">Description</span></span>|  
|------------|-----------------|  
|`domain`|<span data-ttu-id="9b80b-108">핸들 또는 개체가 속한 응용 프로그램 도메인에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="9b80b-108">A pointer to the application domain to which the handle or object belongs.</span></span> <span data-ttu-id="9b80b-109">해당 값 `null`합니다.</span><span class="sxs-lookup"><span data-stu-id="9b80b-109">Its value may be `null`.</span></span>|  
|`location`|<span data-ttu-id="9b80b-110">ICorDebugValue 또는 가비지 수집 개체에 해당 하는 ICorDebugReferenceValue 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="9b80b-110">Either an ICorDebugValue or an ICorDebugReferenceValue interface that corresponds to the object to be garbage-collected.</span></span>|  
|`type`|<span data-ttu-id="9b80b-111">A [CorGCReferenceType](../../../../docs/framework/unmanaged-api/debugging/corgcreferencetype-enumeration.md) 루트에서 발생 한 위치를 나타내는 열거형 값입니다.</span><span class="sxs-lookup"><span data-stu-id="9b80b-111">A [CorGCReferenceType](../../../../docs/framework/unmanaged-api/debugging/corgcreferencetype-enumeration.md) enumeration value that indicates where the root came from.</span></span> <span data-ttu-id="9b80b-112">자세한 내용은 설명 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9b80b-112">For more information, see the Remarks section.</span></span>|  
|`extraData`|<span data-ttu-id="9b80b-113">가비지 수집 되기를 개체에 대 한 추가 데이터입니다.</span><span class="sxs-lookup"><span data-stu-id="9b80b-113">Additional data about the object to be garbage-collected.</span></span> <span data-ttu-id="9b80b-114">명시 된 개체의 원본에 따라 달라 집니다이 정보는 `type` 필드입니다.</span><span class="sxs-lookup"><span data-stu-id="9b80b-114">This information depends on the source of the object, as indicated by the `type` field.</span></span> <span data-ttu-id="9b80b-115">자세한 내용은 설명 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9b80b-115">For more information, see the Remarks section.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9b80b-116">설명</span><span class="sxs-lookup"><span data-stu-id="9b80b-116">Remarks</span></span>  
 <span data-ttu-id="9b80b-117">합니다 `type` 필드를 [CorGCReferenceType](../../../../docs/framework/unmanaged-api/debugging/corgcreferencetype-enumeration.md) 참조에서 제공 하는 위치를 나타내는 열거형 값입니다.</span><span class="sxs-lookup"><span data-stu-id="9b80b-117">The `type` field is a [CorGCReferenceType](../../../../docs/framework/unmanaged-api/debugging/corgcreferencetype-enumeration.md) enumeration value that indicates where the reference came from.</span></span> <span data-ttu-id="9b80b-118">특정 `COR_GC_REFERENCE` 값에는 다음과 같은 유형의 관리 되는 개체를 반영할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9b80b-118">A particular `COR_GC_REFERENCE` value can reflect any of the following kinds of managed objects:</span></span>  
  
- <span data-ttu-id="9b80b-119">모든 관리 되는 스택 개체 (`CorGCReferenceType.CorReferenceStack`).</span><span class="sxs-lookup"><span data-stu-id="9b80b-119">Objects from all managed stacks (`CorGCReferenceType.CorReferenceStack`).</span></span> <span data-ttu-id="9b80b-120">공용 언어 런타임에서 생성 된 개체를 비롯 하 여 관리 코드에 대 한 라이브 참조가 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9b80b-120">This includes live references in managed code, as well as objects created by the common language runtime.</span></span>  
  
- <span data-ttu-id="9b80b-121">개체 핸들 테이블의 (`CorGCReferenceType.CorHandle*`).</span><span class="sxs-lookup"><span data-stu-id="9b80b-121">Objects from the handle table (`CorGCReferenceType.CorHandle*`).</span></span> <span data-ttu-id="9b80b-122">여기에 강력한 참조 (`HNDTYPE_STRONG` 및 `HNDTYPE_REFCOUNT`) 및 모듈의 정적 변수.</span><span class="sxs-lookup"><span data-stu-id="9b80b-122">This includes strong references (`HNDTYPE_STRONG` and `HNDTYPE_REFCOUNT`) and static variables in a module.</span></span>  
  
- <span data-ttu-id="9b80b-123">종료자 큐에서 개체 (`CorGCReferenceType.CorReferenceFinalizer`).</span><span class="sxs-lookup"><span data-stu-id="9b80b-123">Objects from the finalizer queue (`CorGCReferenceType.CorReferenceFinalizer`).</span></span> <span data-ttu-id="9b80b-124">종료자 큐는 종료 자가 실행 될 때까지 개체 루트입니다.</span><span class="sxs-lookup"><span data-stu-id="9b80b-124">The finalizer queue roots objects until the finalizer has run.</span></span>  
  
 <span data-ttu-id="9b80b-125">`extraData` 필드 참조의 원본 (또는 유형)에 따라 추가 데이터를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="9b80b-125">The `extraData` field contains extra data depending on the source (or type) of the reference.</span></span> <span data-ttu-id="9b80b-126">가능한 값은</span><span class="sxs-lookup"><span data-stu-id="9b80b-126">Possible values are:</span></span>  
  
- <span data-ttu-id="9b80b-127">`DependentSource`.</span><span class="sxs-lookup"><span data-stu-id="9b80b-127">`DependentSource`.</span></span> <span data-ttu-id="9b80b-128">경우는 `type` 됩니다 `CorGCREferenceType.CorHandleStrongDependent`,이 필드는 활성 상태로 유지 하는 경우 루트 개체에서 가비지 수집 되도록 하는 개체 `COR_GC_REFERENCE.Location`합니다.</span><span class="sxs-lookup"><span data-stu-id="9b80b-128">If the `type` is `CorGCREferenceType.CorHandleStrongDependent`, this field is the object that, if alive, roots the object to be garbage-collected at `COR_GC_REFERENCE.Location`.</span></span>  
  
- <span data-ttu-id="9b80b-129">`RefCount`.</span><span class="sxs-lookup"><span data-stu-id="9b80b-129">`RefCount`.</span></span> <span data-ttu-id="9b80b-130">경우는 `type` 는 `CorGCREferenceType.CorHandleStrongRefCount`,이 필드는 핸들의 참조 횟수입니다.</span><span class="sxs-lookup"><span data-stu-id="9b80b-130">If the `type` is `CorGCREferenceType.CorHandleStrongRefCount`, this field is the reference count of the handle.</span></span>  
  
- <span data-ttu-id="9b80b-131">`Size`.</span><span class="sxs-lookup"><span data-stu-id="9b80b-131">`Size`.</span></span> <span data-ttu-id="9b80b-132">경우는 `type` 는 `CorGCREferenceType.CorHandleStrongSizedByref`,이 필드는 가비지 수집기가 개체 루트 계산 되는 개체 트리의 마지막 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="9b80b-132">If the `type` is `CorGCREferenceType.CorHandleStrongSizedByref`, this field is the last size of the object tree for which the garbage collector calculated the object roots.</span></span> <span data-ttu-id="9b80b-133">이 계산은 반드시 최신는 참고 합니다.</span><span class="sxs-lookup"><span data-stu-id="9b80b-133">Note that this calculation is not necessarily up to date.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9b80b-134">요구 사항</span><span class="sxs-lookup"><span data-stu-id="9b80b-134">Requirements</span></span>  
 <span data-ttu-id="9b80b-135">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="9b80b-135">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9b80b-136">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="9b80b-136">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="9b80b-137">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9b80b-137">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9b80b-138">**.NET Framework 버전:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9b80b-138">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9b80b-139">참고자료</span><span class="sxs-lookup"><span data-stu-id="9b80b-139">See also</span></span>

- [<span data-ttu-id="9b80b-140">디버깅 구조체</span><span class="sxs-lookup"><span data-stu-id="9b80b-140">Debugging Structures</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)
- [<span data-ttu-id="9b80b-141">디버깅</span><span class="sxs-lookup"><span data-stu-id="9b80b-141">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
