---
title: ICorProfilerInfo::GetClassIDInfo 메서드
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo.GetClassIDInfo
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo::GetClassIDInfo
helpviewer_keywords:
- GetClassIDInfo method [.NET Framework profiling]
- ICorProfilerInfo::GetClassIDInfo method [.NET Framework profiling]
ms.assetid: 9e93b99e-5aca-415c-8e37-7f33753b612d
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 45abb39fa7266e19bbd375b476f2ab48bfc5914d
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59130002"
---
# <a name="icorprofilerinfogetclassidinfo-method"></a><span data-ttu-id="0239c-102">ICorProfilerInfo::GetClassIDInfo 메서드</span><span class="sxs-lookup"><span data-stu-id="0239c-102">ICorProfilerInfo::GetClassIDInfo Method</span></span>
<span data-ttu-id="0239c-103">지정된 된 클래스에 대 한 부모 모듈 및 메타 데이터 토큰을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="0239c-103">Gets the parent module and the metadata token for the specified class.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0239c-104">구문</span><span class="sxs-lookup"><span data-stu-id="0239c-104">Syntax</span></span>  
  
```  
HRESULT GetClassIDInfo(  
    [in]  ClassID   classId,  
    [out] ModuleID  *pModuleId,  
    [out] mdTypeDef *pTypeDefToken);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0239c-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="0239c-105">Parameters</span></span>  
 `classId`  
 <span data-ttu-id="0239c-106">[in] ID 정보를 가져올 수 있는 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="0239c-106">[in] The ID of the class for which to get the information.</span></span>  
  
 `pModuleId`  
 <span data-ttu-id="0239c-107">[out] 클래스의 부모 모듈의 ID에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="0239c-107">[out] A pointer to the ID of the parent module of the class.</span></span>  
  
 `pTypeDefToken`  
 <span data-ttu-id="0239c-108">[out] 클래스에 대 한 메타 데이터 토큰에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="0239c-108">[out] A pointer to the metadata token for the class.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0239c-109">설명</span><span class="sxs-lookup"><span data-stu-id="0239c-109">Remarks</span></span>  
 <span data-ttu-id="0239c-110">프로파일러 코드를 호출할 수 있습니다 [icorprofilerinfo:: Getmodulemetadata](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getmodulemetadata-method.md) 지정 된 모듈에 대 한 메타 데이터 인터페이스를 가져오려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="0239c-110">The profiler code can call [ICorProfilerInfo::GetModuleMetaData](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getmodulemetadata-method.md) to obtain a metadata interface for a given module.</span></span> <span data-ttu-id="0239c-111">그런 다음 `pTypeDefToken`에서 참조된 위치로 반환되는 메타데이터 토큰을 사용하여 클래스에 대한 메타데이터에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0239c-111">The metadata token that is returned to the location referenced by `pTypeDefToken` can then be used to access the metadata for the class.</span></span>  
  
 <span data-ttu-id="0239c-112">제네릭 형식에 대 한 자세한 정보를 가져오려면 [ICorProfilerInfo2::GetClassIDInfo2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getclassidinfo2-method.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="0239c-112">To get more information for generic types, use [ICorProfilerInfo2::GetClassIDInfo2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getclassidinfo2-method.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0239c-113">요구 사항</span><span class="sxs-lookup"><span data-stu-id="0239c-113">Requirements</span></span>  
 <span data-ttu-id="0239c-114">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="0239c-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0239c-115">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="0239c-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="0239c-116">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0239c-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0239c-117">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0239c-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0239c-118">참고자료</span><span class="sxs-lookup"><span data-stu-id="0239c-118">See also</span></span>

- [<span data-ttu-id="0239c-119">ICorProfilerInfo 인터페이스</span><span class="sxs-lookup"><span data-stu-id="0239c-119">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
