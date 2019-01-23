---
title: COR_IL_MAP 구조체
ms.date: 03/30/2017
api_name:
- COR_IL_MAP
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- COR_IL_MAP
helpviewer_keywords:
- COR_IL_MAP structure [.NET Framework debugging]
ms.assetid: 534ebc17-963d-4b26-8375-8cd940281db3
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c7452b76509d5eca592cc3b95df1f77703ec1111
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54561831"
---
# <a name="corilmap-structure"></a><span data-ttu-id="18f15-102">COR_IL_MAP 구조체</span><span class="sxs-lookup"><span data-stu-id="18f15-102">COR_IL_MAP Structure</span></span>
<span data-ttu-id="18f15-103">함수의 상대 오프셋 변경 내용을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="18f15-103">Specifies changes in the relative offset of a function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="18f15-104">구문</span><span class="sxs-lookup"><span data-stu-id="18f15-104">Syntax</span></span>  
  
```  
typedef struct _COR_IL_MAP {  
    ULONG32 oldOffset;   
    ULONG32 newOffset;   
    BOOL    fAccurate;  
} COR_IL_MAP;  
```  
  
## <a name="members"></a><span data-ttu-id="18f15-105">멤버</span><span class="sxs-lookup"><span data-stu-id="18f15-105">Members</span></span>  
  
|<span data-ttu-id="18f15-106">멤버</span><span class="sxs-lookup"><span data-stu-id="18f15-106">Member</span></span>|<span data-ttu-id="18f15-107">설명</span><span class="sxs-lookup"><span data-stu-id="18f15-107">Description</span></span>|  
|------------|-----------------|  
|`oldOffset`|<span data-ttu-id="18f15-108">이전 Microsoft 중간 언어 (MSIL) 함수의 시작 부분에 상대적으로 오프셋입니다.</span><span class="sxs-lookup"><span data-stu-id="18f15-108">The old Microsoft intermediate language (MSIL) offset relative to the beginning of the function.</span></span>|  
|`newOffset`|<span data-ttu-id="18f15-109">함수 시작을 기준으로 새 MSIL 오프셋입니다.</span><span class="sxs-lookup"><span data-stu-id="18f15-109">The new MSIL offset relative to the beginning of the function.</span></span>|  
|`fAccurate`|<span data-ttu-id="18f15-110">`true` 매핑이; 정확 하 게 하는 경우 그렇지 않으면 `false`합니다.</span><span class="sxs-lookup"><span data-stu-id="18f15-110">`true` if the mapping is known to be accurate; otherwise, `false`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="18f15-111">설명</span><span class="sxs-lookup"><span data-stu-id="18f15-111">Remarks</span></span>  
 <span data-ttu-id="18f15-112">Map의 형식은 다음과 같습니다. 디버거는 가정 `oldOffset` 원래, 수정 되지 않은 MSIL 코드 내에서 MSIL 오프셋을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="18f15-112">The format of the map is as follows: The debugger will assume that `oldOffset` refers to an MSIL offset within the original, unmodified MSIL code.</span></span> <span data-ttu-id="18f15-113">`newOffset` 매개 변수는 새 계측 된 코드 내에서 해당 MSIL 오프셋을 가리킵니다.</span><span class="sxs-lookup"><span data-stu-id="18f15-113">The `newOffset` parameter refers to the corresponding MSIL offset within the new, instrumented code.</span></span>  
  
 <span data-ttu-id="18f15-114">단계별 코드 실행이 제대로 작동 하려면, 다음 요구 사항은 충족 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="18f15-114">For stepping to work properly, the following requirements should be met:</span></span>  
  
-   <span data-ttu-id="18f15-115">지도 오름차순 정렬 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="18f15-115">The map should be sorted in ascending order.</span></span>  
  
-   <span data-ttu-id="18f15-116">계측 된 MSIL 코드를 다시 정렬할 수 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="18f15-116">Instrumented MSIL code should not be reordered.</span></span>  
  
-   <span data-ttu-id="18f15-117">원래 MSIL 코드를 제거 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="18f15-117">Original MSIL code should not be removed.</span></span>  
  
-   <span data-ttu-id="18f15-118">지도는 프로그램 데이터베이스 (PDB) 파일에서 모든 시퀀스 위치를 매핑하는 항목이 포함 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="18f15-118">The map should include entries to map all the sequence points from the program database (PDB) file.</span></span>  
  
 <span data-ttu-id="18f15-119">지도 누락 된 항목을 보간하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="18f15-119">The map does not interpolate missing entries.</span></span> <span data-ttu-id="18f15-120">다음 예제에서는 지도 및 해당 결과 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="18f15-120">The following example shows a map and its results.</span></span>  
  
 <span data-ttu-id="18f15-121">매핑하십시오.</span><span class="sxs-lookup"><span data-stu-id="18f15-121">Map:</span></span>  
  
-   <span data-ttu-id="18f15-122">이전 오프셋 0, 0 새 오프셋</span><span class="sxs-lookup"><span data-stu-id="18f15-122">0 old offset, 0 new offset</span></span>  
  
-   <span data-ttu-id="18f15-123">이전 오프셋 5, 10 개의 새 오프셋</span><span class="sxs-lookup"><span data-stu-id="18f15-123">5 old offset, 10 new offset</span></span>  
  
-   <span data-ttu-id="18f15-124">이전 오프셋 9, 20 새 오프셋</span><span class="sxs-lookup"><span data-stu-id="18f15-124">9 old offset, 20 new offset</span></span>  
  
 <span data-ttu-id="18f15-125">결과:</span><span class="sxs-lookup"><span data-stu-id="18f15-125">Results:</span></span>  
  
-   <span data-ttu-id="18f15-126">0, 1, 2, 3 또는 4 이전 오프셋 0 새 오프셋에 매핑됩니다.</span><span class="sxs-lookup"><span data-stu-id="18f15-126">An old offset of 0, 1, 2, 3, or 4 will be mapped to a new offset of 0.</span></span>  
  
-   <span data-ttu-id="18f15-127">5, 6, 7 또는 8 이전 오프셋 새 오프셋 10으로 매핑됩니다.</span><span class="sxs-lookup"><span data-stu-id="18f15-127">An old offset of 5, 6, 7, or 8 will be mapped to new offset 10.</span></span>  
  
-   <span data-ttu-id="18f15-128">9 이상 이전 오프셋 20 새 오프셋에 매핑됩니다.</span><span class="sxs-lookup"><span data-stu-id="18f15-128">An old offset of 9 or higher will be mapped to new offset 20.</span></span>  
  
-   <span data-ttu-id="18f15-129">새 오프셋 0, 1, 2, 3, 4, 5, 6, 7, 8 또는 9 이전 오프셋 0에 매핑됩니다.</span><span class="sxs-lookup"><span data-stu-id="18f15-129">A new offset of 0, 1, 2, 3, 4, 5, 6, 7, 8, or 9 will be mapped to old offset 0.</span></span>  
  
-   <span data-ttu-id="18f15-130">10, 11, 12, 13, 14, 15, 16, 17, 18 또는 19 새 오프셋 5 이전 오프셋에 매핑됩니다.</span><span class="sxs-lookup"><span data-stu-id="18f15-130">A new offset of 10, 11, 12, 13, 14, 15, 16, 17, 18, or 19 will be mapped to old offset 5.</span></span>  
  
-   <span data-ttu-id="18f15-131">20 이상의 새 오프셋을 9 이전 오프셋에 매핑됩니다.</span><span class="sxs-lookup"><span data-stu-id="18f15-131">A new offset of 20 or higher will be mapped to old offset 9.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="18f15-132">요구 사항</span><span class="sxs-lookup"><span data-stu-id="18f15-132">Requirements</span></span>  
 <span data-ttu-id="18f15-133">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="18f15-133">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="18f15-134">**헤더:** CorDebug.idl, CorProf.idl</span><span class="sxs-lookup"><span data-stu-id="18f15-134">**Header:** CorDebug.idl, CorProf.idl</span></span>  
  
 <span data-ttu-id="18f15-135">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="18f15-135">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="18f15-136">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="18f15-136">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="18f15-137">참고자료</span><span class="sxs-lookup"><span data-stu-id="18f15-137">See also</span></span>
- [<span data-ttu-id="18f15-138">디버깅 구조체</span><span class="sxs-lookup"><span data-stu-id="18f15-138">Debugging Structures</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)
- [<span data-ttu-id="18f15-139">디버깅</span><span class="sxs-lookup"><span data-stu-id="18f15-139">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
