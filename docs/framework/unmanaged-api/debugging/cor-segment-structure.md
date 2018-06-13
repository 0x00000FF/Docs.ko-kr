---
title: COR_SEGMENT 구조체
ms.date: 03/30/2017
api_name:
- COR_SEGMENT
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- COR_SEGMENT
helpviewer_keywords:
- COR_SEGMENT structure [.NET Framework debugging]
ms.assetid: 93aeecb9-7fef-4545-8daf-f566dfc47084
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b816087f54e652f07dc791b7d66eb1af8f52f55e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33406509"
---
# <a name="corsegment-structure"></a><span data-ttu-id="2032e-102">COR_SEGMENT 구조체</span><span class="sxs-lookup"><span data-stu-id="2032e-102">COR_SEGMENT Structure</span></span>
<span data-ttu-id="2032e-103">관리되는 힙의 메모리 영역에 대한 정보를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="2032e-103">Contains information about a region of memory in the managed heap.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2032e-104">구문</span><span class="sxs-lookup"><span data-stu-id="2032e-104">Syntax</span></span>  
  
```  
typedef struct _COR_SEGMENT {  
    CORDB_ADDRESS start;            
    CORDB_ADDRESS end;              
    CorDebugGenerationTypes gen;    
    ULONG heap;                     
} COR_SEGMENT;  
```  
  
## <a name="members"></a><span data-ttu-id="2032e-105">멤버</span><span class="sxs-lookup"><span data-stu-id="2032e-105">Members</span></span>  
  
|<span data-ttu-id="2032e-106">멤버</span><span class="sxs-lookup"><span data-stu-id="2032e-106">Member</span></span>|<span data-ttu-id="2032e-107">설명</span><span class="sxs-lookup"><span data-stu-id="2032e-107">Description</span></span>|  
|------------|-----------------|  
|`start`|<span data-ttu-id="2032e-108">시작 주소 메모리 영역입니다.</span><span class="sxs-lookup"><span data-stu-id="2032e-108">The starting address of the memory region.</span></span>|  
|`end`|<span data-ttu-id="2032e-109">메모리 영역의 끝 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="2032e-109">The ending address of the memory region.</span></span>|  
|`gen`|<span data-ttu-id="2032e-110">A [CorDebugGenerationTypes](../../../../docs/framework/unmanaged-api/debugging/cordebuggenerationtypes-enumeration.md) 메모리 영역 생성을 나타내는 열거형 멤버입니다.</span><span class="sxs-lookup"><span data-stu-id="2032e-110">A [CorDebugGenerationTypes](../../../../docs/framework/unmanaged-api/debugging/cordebuggenerationtypes-enumeration.md) enumeration member that indicates the generation of the memory region.</span></span>|  
|`heap`|<span data-ttu-id="2032e-111">메모리 영역 프로시저가 있는 힙 수입니다.</span><span class="sxs-lookup"><span data-stu-id="2032e-111">The heap number in which the memory region resides.</span></span> <span data-ttu-id="2032e-112">자세한 내용은 설명 부분을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="2032e-112">See the Remarks section for more information.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2032e-113">설명</span><span class="sxs-lookup"><span data-stu-id="2032e-113">Remarks</span></span>  
 <span data-ttu-id="2032e-114">`COR_SEGMENTS` 구조체의 관리 되는 힙의 메모리 영역을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="2032e-114">The `COR_SEGMENTS` structure represents a region of memory in the managed heap.</span></span>  <span data-ttu-id="2032e-115">`COR_SEGMENTS` 개체의 멤버인는 [ICorDebugHeapRegionEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugheapsegmentenum-interface.md) 호출 하 여 되는 컬렉션 개체는[icordebugprocess5:: Enumerateheapregions](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enumerateheapregions-method.md) 메서드.</span><span class="sxs-lookup"><span data-stu-id="2032e-115">`COR_SEGMENTS` objects are members of the [ICorDebugHeapRegionEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugheapsegmentenum-interface.md) collection object, which is populated by calling the[ICorDebugProcess5::EnumerateHeapRegions](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enumerateheapregions-method.md) method.</span></span>  
  
 <span data-ttu-id="2032e-116">`heap` 필드는 보고 되 고 힙에 해당 하는 프로세서 수입니다.</span><span class="sxs-lookup"><span data-stu-id="2032e-116">The `heap` field is the processor number, which corresponds to the heap being reported.</span></span> <span data-ttu-id="2032e-117">워크스테이션 가비지 수집기에 대 한 해당 값은 항상 0 워크스테이션 가비지 수집 힙에서 하나만 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2032e-117">For workstation garbage collectors, its value is always zero, because workstations have only one garbage collection heap.</span></span> <span data-ttu-id="2032e-118">서버 가비지 수집기에 대 한 해당 값에 연결 된 힙 프로세서에 해당 합니다.</span><span class="sxs-lookup"><span data-stu-id="2032e-118">For server garbage collectors, its value corresponds to the processor the heap is attached to.</span></span> <span data-ttu-id="2032e-119">Note 있을 수 있음을 가비지 수집이 더 많거나 적은 실제 프로세서는 가비지 수집기의 구현 정보로 인해 보다 힙.</span><span class="sxs-lookup"><span data-stu-id="2032e-119">Note that there may be more or fewer garbage collection heaps than there are actual processors due to the implementation details of the garbage collector.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2032e-120">요구 사항</span><span class="sxs-lookup"><span data-stu-id="2032e-120">Requirements</span></span>  
 <span data-ttu-id="2032e-121">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="2032e-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2032e-122">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="2032e-122">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="2032e-123">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2032e-123">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2032e-124">**.NET framework 버전:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2032e-124">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2032e-125">참고 항목</span><span class="sxs-lookup"><span data-stu-id="2032e-125">See Also</span></span>  
 [<span data-ttu-id="2032e-126">디버깅 구조체</span><span class="sxs-lookup"><span data-stu-id="2032e-126">Debugging Structures</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)  
 [<span data-ttu-id="2032e-127">디버깅</span><span class="sxs-lookup"><span data-stu-id="2032e-127">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
