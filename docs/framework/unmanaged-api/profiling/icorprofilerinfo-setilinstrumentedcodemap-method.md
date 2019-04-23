---
title: ICorProfilerInfo::SetILInstrumentedCodeMap 메서드
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo.SetILInstrumentedCodeMap
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo::SetILInstrumentedCodeMap
helpviewer_keywords:
- ICorProfilerInfo::SetILInstrumentedCodeMap method [.NET Framework profiling]
- SetILInstrumentedCodeMap method [.NET Framework profiling]
ms.assetid: bce1dcf8-b4ec-4e73-a917-f2df1ad49c8a
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 3a574a04e5746a8b2c9c32160e82aa503b392729
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59154195"
---
# <a name="icorprofilerinfosetilinstrumentedcodemap-method"></a><span data-ttu-id="fc4c9-102">ICorProfilerInfo::SetILInstrumentedCodeMap 메서드</span><span class="sxs-lookup"><span data-stu-id="fc4c9-102">ICorProfilerInfo::SetILInstrumentedCodeMap Method</span></span>
<span data-ttu-id="fc4c9-103">지정한 Microsoft 중간 언어 (MSIL) 맵 항목을 사용 하 여 지정된 된 함수에 대 한 코드 맵을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="fc4c9-103">Sets a code map for the specified function using the specified Microsoft intermediate language (MSIL) map entries.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="fc4c9-104">호출.NET framework 버전 2.0 `SetILInstrumentedCodeMap` 에 `FunctionID` 는 특정 응용 프로그램 도메인에서 제네릭 함수를 나타내는 모든 인스턴스에 적용 됩니다 응용 프로그램 도메인에서 해당 함수의 합니다.</span><span class="sxs-lookup"><span data-stu-id="fc4c9-104">In the .NET Framework version 2.0, calling `SetILInstrumentedCodeMap` on a `FunctionID` that represents a generic function in a particular application domain will affect all instances of that function in the application domain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fc4c9-105">구문</span><span class="sxs-lookup"><span data-stu-id="fc4c9-105">Syntax</span></span>  
  
```  
HRESULT SetILInstrumentedCodeMap(  
    [in]  FunctionID functionId,  
    [in]  BOOL       fStartJit,  
    [in]  ULONG      cILMapEntries,  
    [in, size_is(cILMapEntries)] COR_IL_MAP rgILMapEntries[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="fc4c9-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="fc4c9-106">Parameters</span></span>  
 `functionId`  
 <span data-ttu-id="fc4c9-107">[in] 코드 맵 설정 하려는 함수의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="fc4c9-107">[in] The ID of the function for which to set the code map.</span></span>  
  
 `fStartJit`  
 <span data-ttu-id="fc4c9-108">[in] 지정 하는 부울 값 여부를 호출 합니다 `SetILInstrumentedCodeMap` 메서드는 특정 작업에 대해 첫 번째 `FunctionID`.</span><span class="sxs-lookup"><span data-stu-id="fc4c9-108">[in] A Boolean value that indicates whether the call to the `SetILInstrumentedCodeMap` method is the first for a particular `FunctionID`.</span></span> <span data-ttu-id="fc4c9-109">설정 `fStartJit` 하 `true` 첫 번째 호출에서 `SetILInstrumentedCodeMap` 에 대 한을 지정 `FunctionID`, 및 `false` 이후입니다.</span><span class="sxs-lookup"><span data-stu-id="fc4c9-109">Set `fStartJit` to `true` in the first call to `SetILInstrumentedCodeMap` for a given `FunctionID`, and to `false` thereafter.</span></span>  
  
 `cILMapEntries`  
 <span data-ttu-id="fc4c9-110">[in] 요소 수를 `cILMapEntries` 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="fc4c9-110">[in] The number of elements in the `cILMapEntries` array.</span></span>  
  
 `rgILMapEntries`  
 <span data-ttu-id="fc4c9-111">[in] MSIL 오프셋을 지정 하는 각 COR_IL_MAP 구조체의 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="fc4c9-111">[in] An array of COR_IL_MAP structures, each of which specifies an MSIL offset.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="fc4c9-112">설명</span><span class="sxs-lookup"><span data-stu-id="fc4c9-112">Remarks</span></span>  
 <span data-ttu-id="fc4c9-113">프로파일러 (예: 지정 된 소스 줄에 도달 하면 알림) 계측을 위해 메서드의 소스 코드 내에서 문을 삽입 하는 경우가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fc4c9-113">A profiler often inserts statements within the source code of a method in order to instrument that method (for example, to notify when a given source line is reached).</span></span> <span data-ttu-id="fc4c9-114">`SetILInstrumentedCodeMap` 프로파일러를 원래 MSIL 명령을 새 위치로 매핑할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fc4c9-114">`SetILInstrumentedCodeMap` enables a profiler to map the original MSIL instructions to their new locations.</span></span> <span data-ttu-id="fc4c9-115">프로파일러를 사용 하 여 수를 [icorprofilerinfo:: Getiltonativemapping](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getiltonativemapping-method.md) 메서드는 지정 된 네이티브 오프셋에 대 한 원래 MSIL 오프셋을 가져올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fc4c9-115">A profiler can use the [ICorProfilerInfo::GetILToNativeMapping](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getiltonativemapping-method.md) method to get the original MSIL offset for a given native offset.</span></span>  
  
 <span data-ttu-id="fc4c9-116">디버거에서 msil 오프셋 원래, 수정 되지 않은 MSIL 코드 내에서 각 이전 오프셋 나타내며 각 새 오프셋 새, 계측 된 코드 내에서 MSIL 오프셋 가리킵니다 가정 합니다.</span><span class="sxs-lookup"><span data-stu-id="fc4c9-116">The debugger will assume that each old offset refers to an MSIL offset within the original, unmodified MSIL code, and that each new offset refers to the MSIL offset within the new, instrumented code.</span></span> <span data-ttu-id="fc4c9-117">지도 오름차순으로 정렬 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fc4c9-117">The map should be sorted in increasing order.</span></span> <span data-ttu-id="fc4c9-118">단계별 코드 실행이 제대로 작동 하려면, 다음이 지침을 따르세요.</span><span class="sxs-lookup"><span data-stu-id="fc4c9-118">For stepping to work properly, follow these guidelines:</span></span>  
  
-   <span data-ttu-id="fc4c9-119">계측 된 MSIL 코드 순서를 변경 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="fc4c9-119">Do not reorder instrumented MSIL code.</span></span>  
  
-   <span data-ttu-id="fc4c9-120">원래 MSIL 코드를 제거 하지 마십시오.</span><span class="sxs-lookup"><span data-stu-id="fc4c9-120">Do not remove the original MSIL code.</span></span>  
  
-   <span data-ttu-id="fc4c9-121">지도에 프로그램 데이터베이스 (PDB) 파일에서 모든 시퀀스 위치에 대 한 항목을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="fc4c9-121">Include entries for all the sequence points from the program database (PDB) file in the map.</span></span> <span data-ttu-id="fc4c9-122">지도 누락 된 항목을 보간하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="fc4c9-122">The map does not interpolate missing entries.</span></span> <span data-ttu-id="fc4c9-123">따라서 다음과 같은 맵을 지정:</span><span class="sxs-lookup"><span data-stu-id="fc4c9-123">So, given the following map:</span></span>  
  
     <span data-ttu-id="fc4c9-124">(0, 이전 0 새)</span><span class="sxs-lookup"><span data-stu-id="fc4c9-124">(0 old, 0 new)</span></span>  
  
     <span data-ttu-id="fc4c9-125">(5 오래 10 새)</span><span class="sxs-lookup"><span data-stu-id="fc4c9-125">(5 old, 10 new)</span></span>  
  
     <span data-ttu-id="fc4c9-126">(9 이전, 20 새)</span><span class="sxs-lookup"><span data-stu-id="fc4c9-126">(9 old, 20 new)</span></span>  
  
    -   <span data-ttu-id="fc4c9-127">이전 오프셋 0, 1, 2, 3 또는 4의 새 오프셋 0에 매핑됩니다.</span><span class="sxs-lookup"><span data-stu-id="fc4c9-127">An old offset of 0, 1, 2, 3, or 4 will be mapped to new offset 0.</span></span>  
  
    -   <span data-ttu-id="fc4c9-128">5, 6, 7 또는 8 이전 오프셋 새 오프셋 10으로 매핑됩니다.</span><span class="sxs-lookup"><span data-stu-id="fc4c9-128">An old offset of 5, 6, 7, or 8 will be mapped to new offset 10.</span></span>  
  
    -   <span data-ttu-id="fc4c9-129">9 이상 이전 오프셋 20 새 오프셋에 매핑됩니다.</span><span class="sxs-lookup"><span data-stu-id="fc4c9-129">An old offset of 9 or higher will be mapped to new offset 20.</span></span>  
  
    -   <span data-ttu-id="fc4c9-130">새 오프셋 0, 1, 2, 3, 4, 5, 6, 7, 8 또는 9 이전 오프셋 0에 매핑됩니다.</span><span class="sxs-lookup"><span data-stu-id="fc4c9-130">A new offset of 0, 1, 2, 3, 4, 5, 6, 7, 8, or 9 will be mapped to old offset 0.</span></span>  
  
    -   <span data-ttu-id="fc4c9-131">10, 11, 12, 13, 14, 15, 16, 17, 18 또는 19 새 오프셋 5 이전 오프셋에 매핑됩니다.</span><span class="sxs-lookup"><span data-stu-id="fc4c9-131">A new offset of 10, 11, 12, 13, 14, 15, 16, 17, 18, or 19 will be mapped to old offset 5.</span></span>  
  
    -   <span data-ttu-id="fc4c9-132">20 이상의 새 오프셋을 9 이전 오프셋에 매핑됩니다.</span><span class="sxs-lookup"><span data-stu-id="fc4c9-132">A new offset of 20 or higher will be mapped to old offset 9.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fc4c9-133">요구 사항</span><span class="sxs-lookup"><span data-stu-id="fc4c9-133">Requirements</span></span>  
 <span data-ttu-id="fc4c9-134">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="fc4c9-134">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fc4c9-135">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="fc4c9-135">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="fc4c9-136">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="fc4c9-136">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="fc4c9-137">**.NET Framework 버전:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fc4c9-137">**.NET Framework Versions:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fc4c9-138">참고자료</span><span class="sxs-lookup"><span data-stu-id="fc4c9-138">See also</span></span>

- [<span data-ttu-id="fc4c9-139">ICorProfilerInfo 인터페이스</span><span class="sxs-lookup"><span data-stu-id="fc4c9-139">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
