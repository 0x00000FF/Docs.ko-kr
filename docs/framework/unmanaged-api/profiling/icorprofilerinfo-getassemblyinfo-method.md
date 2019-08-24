---
title: ICorProfilerInfo::GetAssemblyInfo 메서드
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo.GetAssemblyInfo
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- GetAssemblyInfo Method
helpviewer_keywords:
- GetAssemblyInfo method [.NET Framework profiling]
- ICorProfilerInfo::GetAssemblyInfo method [.NET Framework profiling]
ms.assetid: 7a3c97c3-1e31-47b1-bf23-386785c509c4
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 0b410ef46e96f75d98ee750c760b19d2a77eec2b
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/10/2019
ms.locfileid: "67780211"
---
# <a name="icorprofilerinfogetassemblyinfo-method"></a><span data-ttu-id="b1509-102">ICorProfilerInfo::GetAssemblyInfo 메서드</span><span class="sxs-lookup"><span data-stu-id="b1509-102">ICorProfilerInfo::GetAssemblyInfo Method</span></span>
<span data-ttu-id="b1509-103">어셈블리 ID를 받아서 어셈블리 이름 및 해당 매니페스트 모듈의 ID를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="b1509-103">Accepts an assembly ID, and returns the assembly's name and the ID of its manifest module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b1509-104">구문</span><span class="sxs-lookup"><span data-stu-id="b1509-104">Syntax</span></span>  
  
```cpp  
HRESULT GetAssemblyInfo(  
    [in]  AssemblyID  assemblyId,  
    [in]  ULONG       cchName,  
    [out] ULONG       *pcchName,  
    [out, size_is(cchName), length_is(*pcchName)]  
          WCHAR       szName[] ,  
    [out] AppDomainID *pAppDomainId,  
    [out] ModuleID    *pModuleId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b1509-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="b1509-105">Parameters</span></span>  
 `assemblyId`  
 <span data-ttu-id="b1509-106">[in] 어셈블리의 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="b1509-106">[in] The identifier of the assembly.</span></span>  
  
 `cchName`  
 <span data-ttu-id="b1509-107">[in] `szName`의 길이(문자)입니다.</span><span class="sxs-lookup"><span data-stu-id="b1509-107">[in] The length, in characters, of `szName`.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="b1509-108">[out] 어셈블리 이름의 총 문자 길이에 대한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="b1509-108">[out] A pointer to the total character length of the assembly's name.</span></span>  
  
 `szName`  
 <span data-ttu-id="b1509-109">[out] 호출자가 제공한 와이드 문자 버퍼입니다.</span><span class="sxs-lookup"><span data-stu-id="b1509-109">[out] A caller-provided wide character buffer.</span></span> <span data-ttu-id="b1509-110">함수가 반환되면 어셈블리 이름을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="b1509-110">When the function returns, it will contain the assembly's name.</span></span>  
  
 `pAppDomainId`  
 <span data-ttu-id="b1509-111">[out] 어셈블리를 포함하는 애플리케이션 도메인의 ID에 대한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="b1509-111">[out] A pointer to the ID of the application domain that contains the assembly.</span></span>  
  
 `pModuleId`  
 <span data-ttu-id="b1509-112">[out] 어셈블리 매니페스트 모듈의 ID에 대한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="b1509-112">[out] A pointer to the ID of the assembly's manifest module.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b1509-113">설명</span><span class="sxs-lookup"><span data-stu-id="b1509-113">Remarks</span></span>  
 <span data-ttu-id="b1509-114">이 메서드가 반환된 후 `szName` 버퍼가 모듈의 어셈블리의 전체 이름을 포함하기에 충분히 큰지 확인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b1509-114">After this method returns, you must verify that the `szName` buffer was large enough to contain the full name of the assembly.</span></span> <span data-ttu-id="b1509-115">이렇게 하려면 `pcchName`가 가리키는 값을 `cchName` 매개 변수의 값과 비교합니다.</span><span class="sxs-lookup"><span data-stu-id="b1509-115">To do this, compare the value that `pcchName` points to with the value of the `cchName` parameter.</span></span> <span data-ttu-id="b1509-116">`pcchName`이 `cchName`보다 큰 값을 가리키는 경우 더 큰 `szName` 버퍼를 할당하고 `cchName`을 더 큰 새 크기로 업데이트한 후 `GetAssemblyInfo`를 다시 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="b1509-116">If `pcchName` points to a value that is larger than `cchName`, allocate a larger `szName` buffer, update `cchName` with the new, larger size, and call `GetAssemblyInfo` again.</span></span>  
  
 <span data-ttu-id="b1509-117">또는 길이가 0인 `szName` 버퍼로 `GetAssemblyInfo`를 먼저 호출하여 올바른 버퍼 크기를 구합니다.</span><span class="sxs-lookup"><span data-stu-id="b1509-117">Alternatively, you can first call `GetAssemblyInfo` with a zero-length `szName` buffer to obtain the correct buffer size.</span></span> <span data-ttu-id="b1509-118">그런 다음 `pcchName`에 반환된 값에 따라 버퍼 크기를 조정하고 `GetAssemblyInfo`를 다시 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="b1509-118">You can then adjust the buffer size based on the value returned in `pcchName` and call `GetAssemblyInfo` again.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b1509-119">요구 사항</span><span class="sxs-lookup"><span data-stu-id="b1509-119">Requirements</span></span>  
 <span data-ttu-id="b1509-120">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="b1509-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b1509-121">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="b1509-121">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="b1509-122">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b1509-122">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b1509-123">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b1509-123">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b1509-124">참고자료</span><span class="sxs-lookup"><span data-stu-id="b1509-124">See also</span></span>

- [<span data-ttu-id="b1509-125">ICorProfilerInfo 인터페이스</span><span class="sxs-lookup"><span data-stu-id="b1509-125">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
- [<span data-ttu-id="b1509-126">프로파일링 인터페이스</span><span class="sxs-lookup"><span data-stu-id="b1509-126">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
- [<span data-ttu-id="b1509-127">프로파일링</span><span class="sxs-lookup"><span data-stu-id="b1509-127">Profiling</span></span>](../../../../docs/framework/unmanaged-api/profiling/index.md)
