---
title: "ICorProfilerInfo2::GetStringLayout 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerInfo2.GetStringLayout
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerInfo2::GetStringLayout
helpviewer_keywords:
- GetStringLayout method [.NET Framework profiling]
- ICorProfilerInfo2::GetStringLayout method [.NET Framework profiling]
ms.assetid: 43189651-a535-4803-a1d1-f1c427ace2ca
topic_type: apiref
caps.latest.revision: "17"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 52a1b9218feb76f7653f747aa52c44284293221f
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="icorprofilerinfo2getstringlayout-method"></a><span data-ttu-id="317e8-102">ICorProfilerInfo2::GetStringLayout 메서드</span><span class="sxs-lookup"><span data-stu-id="317e8-102">ICorProfilerInfo2::GetStringLayout Method</span></span>
<span data-ttu-id="317e8-103">문자열 개체의 레이아웃 정보를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="317e8-103">Gets information about the layout of a string object.</span></span> <span data-ttu-id="317e8-104">이 메서드는 사용 되지 않습니다는 [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)], 않으며로 대체는 [icorprofilerinfo3:: Getstringlayout2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-getstringlayout2-method.md) 메서드.</span><span class="sxs-lookup"><span data-stu-id="317e8-104">This method is deprecated in the [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)], and is superseded by the [ICorProfilerInfo3::GetStringLayout2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-getstringlayout2-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="317e8-105">구문</span><span class="sxs-lookup"><span data-stu-id="317e8-105">Syntax</span></span>  
  
```  
HRESULT GetStringLayout(  
    [out] ULONG *pBufferLengthOffset,  
    [out] ULONG *pStringLengthOffset,  
    [out] ULONG *pBufferOffset);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="317e8-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="317e8-106">Parameters</span></span>  
 `pBufferLengthOffset`  
 <span data-ttu-id="317e8-107">[out] 에 대 한 상대 위치 오프셋에 대 한 포인터는 `ObjectID` 문자열의 길이 저장 하는 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="317e8-107">[out] A pointer to the offset of the location, relative to the `ObjectID` pointer, that stores the length of the string.</span></span> <span data-ttu-id="317e8-108">로 저장 되는 `DWORD`합니다.</span><span class="sxs-lookup"><span data-stu-id="317e8-108">The length is stored as a `DWORD`.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="317e8-109">이 매개 변수 버퍼의 길이가 아닌 문자열 자체의 길이 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="317e8-109">This parameter returns the length of the string itself, not the length of the buffer.</span></span> <span data-ttu-id="317e8-110">버퍼의 길이 더 이상 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="317e8-110">The length of the buffer is no longer available.</span></span>  
  
 `PStringLengthOffset`  
 <span data-ttu-id="317e8-111">[out] 에 대 한 상대 위치 오프셋에 대 한 포인터는 `ObjectID` 문자열 자체의 길이 저장 하는 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="317e8-111">[out] A pointer to the offset of the location, relative to the `ObjectID` pointer, that stores the length of the string itself.</span></span> <span data-ttu-id="317e8-112">로 저장 되는 `DWORD`합니다.</span><span class="sxs-lookup"><span data-stu-id="317e8-112">The length is stored as a `DWORD`.</span></span>  
  
 `pBufferOffset`  
 <span data-ttu-id="317e8-113">[out] 에 대 한 상대 버퍼의 오프셋에 대 한 포인터는 `ObjectID` 와이드 문자의 문자열을 저장 하는 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="317e8-113">[out] A pointer to the offset of the buffer, relative to the `ObjectID` pointer, that stores the string of wide characters.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="317e8-114">설명</span><span class="sxs-lookup"><span data-stu-id="317e8-114">Remarks</span></span>  
 <span data-ttu-id="317e8-115">`GetStringLayout` 메서드 상대적으로 오프셋을 가져옵니다는 `ObjectID` 포인터의 다음 저장 된 위치:</span><span class="sxs-lookup"><span data-stu-id="317e8-115">The `GetStringLayout` method gets the offsets, relative to the `ObjectID` pointer, of the locations in which the following are stored:</span></span>  
  
-   <span data-ttu-id="317e8-116">문자열의 버퍼의 길이입니다.</span><span class="sxs-lookup"><span data-stu-id="317e8-116">The length of the string's buffer.</span></span>  
  
-   <span data-ttu-id="317e8-117">문자열 자체의 길이입니다.</span><span class="sxs-lookup"><span data-stu-id="317e8-117">The length of the string itself.</span></span>  
  
-   <span data-ttu-id="317e8-118">와이드 문자의 실제 문자열을 포함 하는 버퍼입니다.</span><span class="sxs-lookup"><span data-stu-id="317e8-118">The buffer that contains the actual string of wide characters.</span></span>  
  
 <span data-ttu-id="317e8-119">Null로 끝나는 문자열 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="317e8-119">Strings may be null-terminated.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="317e8-120">요구 사항</span><span class="sxs-lookup"><span data-stu-id="317e8-120">Requirements</span></span>  
 <span data-ttu-id="317e8-121">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="317e8-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="317e8-122">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="317e8-122">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="317e8-123">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="317e8-123">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="317e8-124">**.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="317e8-124">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="317e8-125">참고 항목</span><span class="sxs-lookup"><span data-stu-id="317e8-125">See Also</span></span>  
 [<span data-ttu-id="317e8-126">ICorProfilerInfo 인터페이스</span><span class="sxs-lookup"><span data-stu-id="317e8-126">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)  
 [<span data-ttu-id="317e8-127">ICorProfilerInfo2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="317e8-127">ICorProfilerInfo2 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-interface.md)
