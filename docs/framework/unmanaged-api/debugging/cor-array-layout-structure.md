---
title: COR_ARRAY_LAYOUT 구조체
ms.date: 03/30/2017
api_name:
- COR_ARRAY_LAYOUT
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- COR_ARRAY_LAYOUT
helpviewer_keywords:
- COR_DEBUG_IL_TO_NATIVE_MAP structure [.NET Framework debugging]
ms.assetid: aa20ac3d-6f60-4aa2-91c5-f3a86f82eba8
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e6fee91146e99ba1f63ecafcbbdaae9d42675848
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54731142"
---
# <a name="corarraylayout-structure"></a><span data-ttu-id="d839b-102">COR_ARRAY_LAYOUT 구조체</span><span class="sxs-lookup"><span data-stu-id="d839b-102">COR_ARRAY_LAYOUT Structure</span></span>
<span data-ttu-id="d839b-103">메모리 내 배열 개체의 레이아웃에 대한 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="d839b-103">Provides information about the layout of an array object in memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d839b-104">구문</span><span class="sxs-lookup"><span data-stu-id="d839b-104">Syntax</span></span>  
  
```  
typedef struct COR_ARRAY_LAYOUT {  
    COR_TYPEID componentID;  
    CorElementType componentType;  
    ULONG32 firstElementOffset;  
    ULONG32 elementSize;  
    ULONG32 countOffset;   
    ULONG32 rankSize;   
    ULONG32 numRanks;   
    ULONG32 rankOffset;   
} COR_ARRAY_LAYOUT;  
```  
  
## <a name="members"></a><span data-ttu-id="d839b-105">멤버</span><span class="sxs-lookup"><span data-stu-id="d839b-105">Members</span></span>  
  
|<span data-ttu-id="d839b-106">멤버</span><span class="sxs-lookup"><span data-stu-id="d839b-106">Member</span></span>|<span data-ttu-id="d839b-107">설명</span><span class="sxs-lookup"><span data-stu-id="d839b-107">Description</span></span>|  
|------------|-----------------|  
|`componentID`|<span data-ttu-id="d839b-108">배열에 포함 된 개체 형식의 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="d839b-108">The identifier of the type of objects that the array contains.</span></span>|  
|`componentType`|<span data-ttu-id="d839b-109">가비지 컬렉션 참조, 값 클래스 또는 기본 구성 요소 인지 여부를 나타내는 CorElementType 열거형 값입니다.</span><span class="sxs-lookup"><span data-stu-id="d839b-109">A CorElementType enumeration value that indicates whether the component is a garbage collection reference, a value class, or a primitive.</span></span>|  
|`firstElementOffset`|<span data-ttu-id="d839b-110">배열의 첫 번째 요소 오프셋입니다.</span><span class="sxs-lookup"><span data-stu-id="d839b-110">The offset to the first element in the array.</span></span>|  
|`elementSize`|<span data-ttu-id="d839b-111">각 요소의 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="d839b-111">The size of each element.</span></span>|  
|`countOffset`|<span data-ttu-id="d839b-112">오프셋 배열에서 요소의 수입니다.</span><span class="sxs-lookup"><span data-stu-id="d839b-112">The offset to the number of elements in the array.</span></span>|  
|`rankSize`|<span data-ttu-id="d839b-113">크기 (바이트)에서 순위입니다.</span><span class="sxs-lookup"><span data-stu-id="d839b-113">The size of the rank, in bytes.</span></span>|  
|`numRanks`|<span data-ttu-id="d839b-114">배열의 순위 횟수입니다.</span><span class="sxs-lookup"><span data-stu-id="d839b-114">The number of ranks in the array.</span></span>|  
|`rankOffset`|<span data-ttu-id="d839b-115">순위는 시작 오프셋입니다.</span><span class="sxs-lookup"><span data-stu-id="d839b-115">The offset at which the ranks start.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d839b-116">설명</span><span class="sxs-lookup"><span data-stu-id="d839b-116">Remarks</span></span>  
 <span data-ttu-id="d839b-117">`rankSize` 필드 다차원 배열의 순위의 크기를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="d839b-117">The `rankSize` field specifies the size of a rank in a multi-dimensional array.</span></span> <span data-ttu-id="d839b-118">것도 1 차원 배열에 대해 정확 합니다.</span><span class="sxs-lookup"><span data-stu-id="d839b-118">It is accurate for single-dimensional arrays as well.</span></span>  
  
 <span data-ttu-id="d839b-119">변수의 `numRanks` 는 1 차원 배열에 대 한 1 및 `N` 다차원 배열에 `N` 차원입니다.</span><span class="sxs-lookup"><span data-stu-id="d839b-119">The value of `numRanks` is 1 for a single-dimensional array and `N` for a multi-dimensional array of `N` dimensions.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d839b-120">요구 사항</span><span class="sxs-lookup"><span data-stu-id="d839b-120">Requirements</span></span>  
 <span data-ttu-id="d839b-121">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="d839b-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d839b-122">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d839b-122">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d839b-123">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d839b-123">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d839b-124">**.NET Framework 버전:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d839b-124">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d839b-125">참고자료</span><span class="sxs-lookup"><span data-stu-id="d839b-125">See also</span></span>
- [<span data-ttu-id="d839b-126">디버깅 구조체</span><span class="sxs-lookup"><span data-stu-id="d839b-126">Debugging Structures</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)
- [<span data-ttu-id="d839b-127">디버깅</span><span class="sxs-lookup"><span data-stu-id="d839b-127">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
