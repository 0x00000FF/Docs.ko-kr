---
title: ICorProfilerInfo::GetClassFromToken 메서드
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo.GetClassFromToken
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo::GetClassFromToken
helpviewer_keywords:
- ICorProfilerInfo::GetClassFromToken method [.NET Framework profiling]
- GetClassFromToken method, ICorProfilerInfo interface [.NET Framework profiling]
ms.assetid: 0afc1197-2a5b-424f-8b82-9cb59a7e00db
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 12524de994264d83abf5b5338654e89a0964adff
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54667702"
---
# <a name="icorprofilerinfogetclassfromtoken-method"></a><span data-ttu-id="5db57-102">ICorProfilerInfo::GetClassFromToken 메서드</span><span class="sxs-lookup"><span data-stu-id="5db57-102">ICorProfilerInfo::GetClassFromToken Method</span></span>
<span data-ttu-id="5db57-103">메타 데이터 토큰을 지정 하는 클래스의 ID를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="5db57-103">Gets the ID of the class, given the metadata token.</span></span> <span data-ttu-id="5db57-104">이 메서드는.NET Framework 버전 2.0에서에서 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5db57-104">This method is obsolete in the .NET Framework version 2.0.</span></span> <span data-ttu-id="5db57-105">사용 하 여 [ICorProfilerInfo2::GetClassFromTokenAndTypeArgs](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getclassfromtokenandtypeargs-method.md) 대신 합니다.</span><span class="sxs-lookup"><span data-stu-id="5db57-105">Use [ICorProfilerInfo2::GetClassFromTokenAndTypeArgs](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getclassfromtokenandtypeargs-method.md) instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5db57-106">구문</span><span class="sxs-lookup"><span data-stu-id="5db57-106">Syntax</span></span>  
  
```  
HRESULT GetClassFromToken(  
    [in]  ModuleID  moduleId,  
    [in]  mdTypeDef typeDef,  
    [out] ClassID   *pClassId);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="5db57-107">매개 변수</span><span class="sxs-lookup"><span data-stu-id="5db57-107">Parameters</span></span>  
 `moduleID`  
 <span data-ttu-id="5db57-108">[in] 클래스를 포함 하는 모듈의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="5db57-108">[in] The ID of the module that contains the class.</span></span>  
  
 `typeDef`  
 <span data-ttu-id="5db57-109">[in] `mdTypeDef` 클래스를 참조 하는 메타 데이터 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="5db57-109">[in] An `mdTypeDef` metadata token that references the class.</span></span>  
  
 `cTypeArgs`  
 <span data-ttu-id="5db57-110">[out] 클래스 ID에 대 한 포인터</span><span class="sxs-lookup"><span data-stu-id="5db57-110">[out] A pointer to the class ID.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5db57-111">설명</span><span class="sxs-lookup"><span data-stu-id="5db57-111">Remarks</span></span>  
 <span data-ttu-id="5db57-112">이 메서드는 사용 되지 않습니다. 대신 `ICorProfilerInfo2::GetClassFromTokenAndTypeArgs` 모든 형식에 대 한 합니다.</span><span class="sxs-lookup"><span data-stu-id="5db57-112">This method is obsolete; instead, use `ICorProfilerInfo2::GetClassFromTokenAndTypeArgs` for all types.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5db57-113">요구 사항</span><span class="sxs-lookup"><span data-stu-id="5db57-113">Requirements</span></span>  
 <span data-ttu-id="5db57-114">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="5db57-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5db57-115">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="5db57-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="5db57-116">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5db57-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5db57-117">**.NET framework 버전:** 1.0, 1.1</span><span class="sxs-lookup"><span data-stu-id="5db57-117">**.NET Framework Versions:** 1.0, 1.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5db57-118">참고자료</span><span class="sxs-lookup"><span data-stu-id="5db57-118">See also</span></span>
- [<span data-ttu-id="5db57-119">ICorProfilerInfo 인터페이스</span><span class="sxs-lookup"><span data-stu-id="5db57-119">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
