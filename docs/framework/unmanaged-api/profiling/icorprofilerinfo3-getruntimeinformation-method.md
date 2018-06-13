---
title: ICorProfilerInfo3::GetRuntimeInformation 메서드
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo3.GetRuntimeInformation Method
api_location:
- Mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo3::GetRuntimeInformation
helpviewer_keywords:
- GetRuntimeInformation method [.NET Framework profiling]
- ICorProfilerInfo3::GetRuntimeInformation method [.NET Framework profiling]
ms.assetid: 4400fb8c-0407-4791-8557-f011fd2aee51
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 67e1d20f7faf38fa37083f1a5b1cc0c1060b7a32
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33461570"
---
# <a name="icorprofilerinfo3getruntimeinformation-method"></a><span data-ttu-id="d7a28-102">ICorProfilerInfo3::GetRuntimeInformation 메서드</span><span class="sxs-lookup"><span data-stu-id="d7a28-102">ICorProfilerInfo3::GetRuntimeInformation Method</span></span>
<span data-ttu-id="d7a28-103">프로 파일링 되 고 공용 언어 런타임 (CLR)에 대 한 버전 정보를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="d7a28-103">Provides version information about the common language runtime (CLR) that is being profiled.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d7a28-104">구문</span><span class="sxs-lookup"><span data-stu-id="d7a28-104">Syntax</span></span>  
  
```  
HRESULT GetRuntimeInformation(  
       [out] USHORT *pClrInstanceId,  
       [out] COR_PRF_RUNTIME_TYPE *pRuntimeType,  
       [out] USHORT *pMajorVersion,  
       [out] USHORT *pMinorVersion,  
       [out] USHORT *pBuildNumber,  
       [out] USHORT *pQFEVersion,  
       [in]  ULONG  cchVersionString,  
       [out] ULONG  *pcchVersionString,  
       [out, size_is(cchVersionString), length_is(*pcchVersionString)]  
                   WCHAR  szVersionString[]);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="d7a28-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="d7a28-105">Parameters</span></span>  
 `pClrInstanceId`  
 <span data-ttu-id="d7a28-106">[out] 프로세스에서 실행 중인 CLR 인스턴스의 담당자 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="d7a28-106">[out] The representative ID of a running CLR instance in a process.</span></span> <span data-ttu-id="d7a28-107">이와 동일는 `ClrInstanceID` 는 ETW (Windows) startup 이벤트 용 이벤트 추적을 보고 합니다.</span><span class="sxs-lookup"><span data-stu-id="d7a28-107">This is the same as the `ClrInstanceID` that the event tracing for Windows (ETW) startup event reports.</span></span>  
  
 `pRuntimeType`  
 <span data-ttu-id="d7a28-108">[out] 런타임 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="d7a28-108">[out] The runtime type.</span></span> <span data-ttu-id="d7a28-109">이 매개 변수 반환 `COR_PRF_DESKTOP_CLR` CLR의 데스크톱 버전에 대 한 또는 `COR_PRF_CORE_CLR` Silverlight에서 사용 하는 CLR의 핵심 버전에 대 한 합니다.</span><span class="sxs-lookup"><span data-stu-id="d7a28-109">This parameter returns `COR_PRF_DESKTOP_CLR` for the desktop version of the CLR, or `COR_PRF_CORE_CLR` for the core version of the CLR used in Silverlight.</span></span>  
  
 `pMajorVersion`  
 <span data-ttu-id="d7a28-110">[out] CLR의 주 버전 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="d7a28-110">[out] The major version number of the CLR.</span></span>  
  
 `pMinorVersion`  
 <span data-ttu-id="d7a28-111">[out] CLR의 부 버전 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="d7a28-111">[out] The minor version number of the CLR.</span></span>  
  
 `pBuildVersion`  
 <span data-ttu-id="d7a28-112">[out] Clr 빌드 버전 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="d7a28-112">[out] The build version number of the CLR.</span></span>  
  
 `pQFEVersion`  
 <span data-ttu-id="d7a28-113">[out] 소프트웨어 업데이트와 관련 된 CLR의 버전 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="d7a28-113">[out] The version number of the CLR that is associated with a software update.</span></span>  
  
 `cchVersionString`  
 <span data-ttu-id="d7a28-114">[in] 버퍼의 문자에서 길이 `szVersionString` 를 가리킵니다.</span><span class="sxs-lookup"><span data-stu-id="d7a28-114">[in] The length, in characters, of the buffer that `szVersionString` points to.</span></span>  
  
 `pcchVersionString`  
 <span data-ttu-id="d7a28-115">[out] 길이 문자의 `szVersionString`합니다.</span><span class="sxs-lookup"><span data-stu-id="d7a28-115">[out] The length, in characters, of `szVersionString`.</span></span>  
  
 `szVersionString`  
 <span data-ttu-id="d7a28-116">[out] CLR 버전 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="d7a28-116">[out] The CLR version string.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d7a28-117">설명</span><span class="sxs-lookup"><span data-stu-id="d7a28-117">Remarks</span></span>  
 <span data-ttu-id="d7a28-118">매개 변수에 대해 null을 전달할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d7a28-118">You may pass null for any parameter.</span></span> <span data-ttu-id="d7a28-119">그러나 `pcchVersionString` null 일 수 없습니다 하지 않는 한 `szVersionString` 도 null입니다.</span><span class="sxs-lookup"><span data-stu-id="d7a28-119">However, `pcchVersionString` cannot be null unless `szVersionString` is also null.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d7a28-120">요구 사항</span><span class="sxs-lookup"><span data-stu-id="d7a28-120">Requirements</span></span>  
 <span data-ttu-id="d7a28-121">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="d7a28-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d7a28-122">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="d7a28-122">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="d7a28-123">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d7a28-123">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d7a28-124">**.NET framework 버전:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d7a28-124">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d7a28-125">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d7a28-125">See Also</span></span>  
 [<span data-ttu-id="d7a28-126">ICorProfilerInfo3 인터페이스</span><span class="sxs-lookup"><span data-stu-id="d7a28-126">ICorProfilerInfo3 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-interface.md)  
 [<span data-ttu-id="d7a28-127">프로파일링 인터페이스</span><span class="sxs-lookup"><span data-stu-id="d7a28-127">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)  
 [<span data-ttu-id="d7a28-128">프로파일링</span><span class="sxs-lookup"><span data-stu-id="d7a28-128">Profiling</span></span>](../../../../docs/framework/unmanaged-api/profiling/index.md)
