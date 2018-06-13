---
title: ICorDebugHeapSegmentEnum::Next 메서드
ms.date: 03/30/2017
api_name:
- Next
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugHeapSegmentEnum::Next
helpviewer_keywords:
- ICorDebugHeapSegmentEnum::Next method [.NET Framework debugging]
- Next method, ICorDebugHeapSegmentEnum interface [.NET Framework debugging]
ms.assetid: 51625fd0-7399-49c7-b22b-5dfb05451fe6
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3b63646b54b73c30abf0ddb9a06a982f1364ef87
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33417026"
---
# <a name="icordebugheapsegmentenumnext-method"></a><span data-ttu-id="f87ad-102">ICorDebugHeapSegmentEnum::Next 메서드</span><span class="sxs-lookup"><span data-stu-id="f87ad-102">ICorDebugHeapSegmentEnum::Next Method</span></span>
<span data-ttu-id="f87ad-103">지정된 된 수의 가져옵니다 [COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md) 관리 되는 힙의 메모리 영역에 대 한 정보가 포함 된 인스턴스.</span><span class="sxs-lookup"><span data-stu-id="f87ad-103">Gets the specified number of [COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md) instances that contain information about memory regions of the managed heap.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f87ad-104">구문</span><span class="sxs-lookup"><span data-stu-id="f87ad-104">Syntax</span></span>  
  
```  
HRESULT Next(  
    [in] ULONG celt,    [out, size_is(celt), length_is(*pceltFetched)] COR_SEGMENT segments[],   
    [out] ULONG *pceltFetched  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="f87ad-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="f87ad-105">Parameters</span></span>  
 <span data-ttu-id="f87ad-106">celt</span><span class="sxs-lookup"><span data-stu-id="f87ad-106">celt</span></span>  
 <span data-ttu-id="f87ad-107">[in] 검색할 세그먼트의 수입니다.</span><span class="sxs-lookup"><span data-stu-id="f87ad-107">[in] The number of segments to be retrieved.</span></span>  
  
 <span data-ttu-id="f87ad-108">세그먼트</span><span class="sxs-lookup"><span data-stu-id="f87ad-108">segments</span></span>  
 <span data-ttu-id="f87ad-109">[out] 각각 가리키는 포인터의 배열은 [COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md) 의 관리 되는 힙의 메모리 영역에 대 한 정보를 제공 하는 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="f87ad-109">[out] An array of pointers, each of which points to a [COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md) object that provides information about a region of memory in the managed heap.</span></span>  
  
 <span data-ttu-id="f87ad-110">pceltFetched</span><span class="sxs-lookup"><span data-stu-id="f87ad-110">pceltFetched</span></span>  
 <span data-ttu-id="f87ad-111">[out] 수에 대 한 포인터 [COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md) 에 실제로 반환 된 개체 `segments`합니다.</span><span class="sxs-lookup"><span data-stu-id="f87ad-111">[out] A pointer to the number of [COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md) objects actually returned in `segments`.</span></span> <span data-ttu-id="f87ad-112">`celt`가 1이면 이 값은 `null`일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f87ad-112">This value may be `null` if `celt` is 1.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f87ad-113">설명</span><span class="sxs-lookup"><span data-stu-id="f87ad-113">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f87ad-114">요구 사항</span><span class="sxs-lookup"><span data-stu-id="f87ad-114">Requirements</span></span>  
 <span data-ttu-id="f87ad-115">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="f87ad-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f87ad-116">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f87ad-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f87ad-117">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f87ad-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f87ad-118">**.NET framework 버전:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f87ad-118">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f87ad-119">참고 항목</span><span class="sxs-lookup"><span data-stu-id="f87ad-119">See Also</span></span>  
 [<span data-ttu-id="f87ad-120">ICorDebugHeapSegmentEnum 인터페이스</span><span class="sxs-lookup"><span data-stu-id="f87ad-120">ICorDebugHeapSegmentEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugheapsegmentenum-interface.md)  
 [<span data-ttu-id="f87ad-121">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="f87ad-121">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
