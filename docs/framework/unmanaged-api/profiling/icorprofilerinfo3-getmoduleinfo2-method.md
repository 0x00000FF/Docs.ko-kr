---
title: ICorProfilerInfo3::GetModuleInfo2 메서드
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo3.GetModuleInfo2
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo3::GetModuleInfo2
helpviewer_keywords:
- ICorProfilerInfo3::GetModuleInfo2 method [.NET Framework profiling]
- GetModuleInfo2 method [.NET Framework profiling]
ms.assetid: f1f6b8f3-dcfc-49e8-be76-ea50ea90d5a7
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 8fadca931ca4a57c83257f24e34e847870c9f493
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59107486"
---
# <a name="icorprofilerinfo3getmoduleinfo2-method"></a><span data-ttu-id="ccb38-102">ICorProfilerInfo3::GetModuleInfo2 메서드</span><span class="sxs-lookup"><span data-stu-id="ccb38-102">ICorProfilerInfo3::GetModuleInfo2 Method</span></span>
<span data-ttu-id="ccb38-103">모듈 ID가 지정된 경우 모듈의 파일 이름, 모듈의 부모 어셈블리 ID 및 모듈 속성을 설명하는 비트 마스크를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="ccb38-103">Given a module ID, returns the file name of the module, the ID of the module's parent assembly, and a bitmask that describes the properties of the module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ccb38-104">구문</span><span class="sxs-lookup"><span data-stu-id="ccb38-104">Syntax</span></span>  
  
```  
HRESULT GetModuleInfo2(  
    [in]  ModuleID   moduleId,  
    [out] LPCBYTE    *ppBaseLoadAddress,  
    [in]  ULONG      cchName,  
    [out] ULONG      *pcchName,  
    [out, annotation("__out_ecount_part(cchName, *pcchName)")]  
          WCHAR      szName[] ,  
    [out] AssemblyID *pAssemblyId);  
    [out] DWORD                 *pdwModuleFlags);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ccb38-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="ccb38-105">Parameters</span></span>  
 `moduleId`  
 <span data-ttu-id="ccb38-106">[in] 정보가 검색되는 모듈의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="ccb38-106">[in] The ID of the module for which information will be retrieved.</span></span>  
  
 `ppBaseLoadAddress`  
 <span data-ttu-id="ccb38-107">[out] 모듈이 로드되는 기본 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="ccb38-107">[out] The base address at which the module is loaded.</span></span>  
  
 `cchName`  
 <span data-ttu-id="ccb38-108">[in] `szName` 반환 버퍼의 길이(문자)입니다.</span><span class="sxs-lookup"><span data-stu-id="ccb38-108">[in] The length, in characters, of the `szName` return buffer.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="ccb38-109">[out] 반환되는 모듈 파일 이름의 총 문자 길이에 대한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="ccb38-109">[out] A pointer to the total character length of the module's file name that is returned.</span></span>  
  
 `szName`  
 <span data-ttu-id="ccb38-110">[out] 호출자가 제공한 와이드 문자 버퍼입니다.</span><span class="sxs-lookup"><span data-stu-id="ccb38-110">[out] A caller-provided wide character buffer.</span></span> <span data-ttu-id="ccb38-111">메서드가 반환되면 이 버퍼에 모듈의 파일 이름이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="ccb38-111">When the method returns, this buffer contains the file name of the module.</span></span>  
  
 `pAssemblyId`  
 <span data-ttu-id="ccb38-112">[out] 모듈의 부모 어셈블리 ID에 대한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="ccb38-112">[out] A pointer to the ID of the module's parent assembly.</span></span>  
  
 `pdwModuleFlags`  
 <span data-ttu-id="ccb38-113">[out] 값의 비트 마스크를 [COR_PRF_MODULE_FLAGS](../../../../docs/framework/unmanaged-api/profiling/cor-prf-module-flags-enumeration.md) 모듈의 속성을 지정 하는 열거형입니다.</span><span class="sxs-lookup"><span data-stu-id="ccb38-113">[out] A bitmask of values from the [COR_PRF_MODULE_FLAGS](../../../../docs/framework/unmanaged-api/profiling/cor-prf-module-flags-enumeration.md) enumeration that specify the properties of the module.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ccb38-114">설명</span><span class="sxs-lookup"><span data-stu-id="ccb38-114">Remarks</span></span>  
 <span data-ttu-id="ccb38-115">동적 모듈의 경우 `szName` 매개 변수는 모듈의 메타데이터 이름이고 기본 주소는 0입니다.</span><span class="sxs-lookup"><span data-stu-id="ccb38-115">For dynamic modules, the `szName` parameter is the metadata name of the module, and the base address is 0 (zero).</span></span> <span data-ttu-id="ccb38-116">메타데이터 이름은 메타데이터 내부에서 Module 테이블의 Name 열에 있는 값입니다.</span><span class="sxs-lookup"><span data-stu-id="ccb38-116">The metadata name is the value in the Name column from the Module table inside metadata.</span></span> <span data-ttu-id="ccb38-117">도 노출 됩니다는 <xref:System.Reflection.Module.ScopeName%2A?displayProperty=nameWithType> 속성으로 관리 되는 코드에는 `szName` 의 매개 변수를 [imetadataimport:: Getscopeprops](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-getscopeprops-method.md) 관리 되지 않는 메타 데이터 클라이언트 코드에 메서드.</span><span class="sxs-lookup"><span data-stu-id="ccb38-117">This is also exposed as the <xref:System.Reflection.Module.ScopeName%2A?displayProperty=nameWithType> property to managed code, and as the `szName` parameter of the [IMetaDataImport::GetScopeProps](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-getscopeprops-method.md) method to unmanaged metadata client code.</span></span>  
  
 <span data-ttu-id="ccb38-118">하지만 합니다 `GetModuleInfo2` 모듈의 ID가 즉시 메서드를 호출할 수 있습니다, 프로파일러를 받을 때까지 부모 어셈블리의 ID를 사용할 수 없습니다 합니다 [icorprofilercallback:: Moduleattachedtoassembly](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleattachedtoassembly-method.md) 콜백 합니다.</span><span class="sxs-lookup"><span data-stu-id="ccb38-118">Although the `GetModuleInfo2` method may be called as soon as the module's ID exists, the ID of the parent assembly will not be available until the profiler receives the [ICorProfilerCallback::ModuleAttachedToAssembly](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleattachedtoassembly-method.md) callback.</span></span>  
  
 <span data-ttu-id="ccb38-119">`GetModuleInfo2`가 반환된 후 `szName` 버퍼가 모듈의 전체 파일 이름을 포함하기에 충분히 큰지 확인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ccb38-119">When `GetModuleInfo2` returns, you must verify that the `szName` buffer was large enough to contain the full file name of the module.</span></span> <span data-ttu-id="ccb38-120">이렇게 하려면 `pcchName`가 가리키는 값을 `cchName` 매개 변수의 값과 비교합니다.</span><span class="sxs-lookup"><span data-stu-id="ccb38-120">To do this, compare the value that `pcchName` points to with the value of the `cchName` parameter.</span></span> <span data-ttu-id="ccb38-121">`pcchName`이 `cchName`보다 큰 값을 가리키는 경우 더 큰 `szName` 버퍼를 할당하고 `cchName`을 더 큰 새 크기로 업데이트한 후 `GetModuleInfo2`를 다시 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="ccb38-121">If `pcchName` points to a value that is larger than `cchName`, allocate a larger `szName` buffer, update `cchName` with the new, larger size, and call `GetModuleInfo2` again.</span></span>  
  
 <span data-ttu-id="ccb38-122">또는 길이가 0인 `szName` 버퍼로 `GetModuleInfo2`를 먼저 호출하여 올바른 버퍼 크기를 구합니다.</span><span class="sxs-lookup"><span data-stu-id="ccb38-122">Alternatively, you can first call `GetModuleInfo2` with a zero-length `szName` buffer to obtain the correct buffer size.</span></span> <span data-ttu-id="ccb38-123">그런 다음 버퍼 크기를 `pcchName`에 반환된 값으로 설정하고 `GetModuleInfo2`을 다시 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="ccb38-123">You can then set the buffer size to the value returned in `pcchName` and call `GetModuleInfo2` again.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ccb38-124">요구 사항</span><span class="sxs-lookup"><span data-stu-id="ccb38-124">Requirements</span></span>  
 <span data-ttu-id="ccb38-125">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="ccb38-125">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ccb38-126">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="ccb38-126">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="ccb38-127">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ccb38-127">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="ccb38-128">.NET Framework 버전:</span><span class="sxs-lookup"><span data-stu-id="ccb38-128">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="ccb38-129">참고자료</span><span class="sxs-lookup"><span data-stu-id="ccb38-129">See also</span></span>

- [<span data-ttu-id="ccb38-130">ICorProfilerInfo 인터페이스</span><span class="sxs-lookup"><span data-stu-id="ccb38-130">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
- [<span data-ttu-id="ccb38-131">프로파일링 인터페이스</span><span class="sxs-lookup"><span data-stu-id="ccb38-131">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
- [<span data-ttu-id="ccb38-132">프로파일링</span><span class="sxs-lookup"><span data-stu-id="ccb38-132">Profiling</span></span>](../../../../docs/framework/unmanaged-api/profiling/index.md)
