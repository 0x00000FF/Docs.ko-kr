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
ms.openlocfilehash: 841953625235406f013e9f140ad91c7b65680e47
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/29/2020
ms.locfileid: "76863955"
---
# <a name="icorprofilerinfogetclassfromtoken-method"></a><span data-ttu-id="20d1b-102">ICorProfilerInfo::GetClassFromToken 메서드</span><span class="sxs-lookup"><span data-stu-id="20d1b-102">ICorProfilerInfo::GetClassFromToken Method</span></span>
<span data-ttu-id="20d1b-103">메타 데이터 토큰이 지정 된 경우 클래스의 ID를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="20d1b-103">Gets the ID of the class, given the metadata token.</span></span> <span data-ttu-id="20d1b-104">이 메서드는 .NET Framework 버전 2.0에서 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="20d1b-104">This method is obsolete in the .NET Framework version 2.0.</span></span> <span data-ttu-id="20d1b-105">대신 [ICorProfilerInfo2:: GetClassFromTokenAndTypeArgs](icorprofilerinfo2-getclassfromtokenandtypeargs-method.md) 를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="20d1b-105">Use [ICorProfilerInfo2::GetClassFromTokenAndTypeArgs](icorprofilerinfo2-getclassfromtokenandtypeargs-method.md) instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="20d1b-106">구문</span><span class="sxs-lookup"><span data-stu-id="20d1b-106">Syntax</span></span>  
  
```cpp  
HRESULT GetClassFromToken(  
    [in]  ModuleID  moduleId,  
    [in]  mdTypeDef typeDef,  
    [out] ClassID   *pClassId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="20d1b-107">매개 변수</span><span class="sxs-lookup"><span data-stu-id="20d1b-107">Parameters</span></span>  
 `moduleID`  
 <span data-ttu-id="20d1b-108">진행 클래스가 포함 된 모듈의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="20d1b-108">[in] The ID of the module that contains the class.</span></span>  
  
 `typeDef`  
 <span data-ttu-id="20d1b-109">진행 클래스를 참조 하는 `mdTypeDef` 메타 데이터 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="20d1b-109">[in] An `mdTypeDef` metadata token that references the class.</span></span>  
  
 `cTypeArgs`  
 <span data-ttu-id="20d1b-110">제한이 클래스 ID에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="20d1b-110">[out] A pointer to the class ID.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="20d1b-111">주의</span><span class="sxs-lookup"><span data-stu-id="20d1b-111">Remarks</span></span>  
 <span data-ttu-id="20d1b-112">이 메서드는 사용 되지 않습니다. 대신 모든 형식에 대해 `ICorProfilerInfo2::GetClassFromTokenAndTypeArgs`를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="20d1b-112">This method is obsolete; instead, use `ICorProfilerInfo2::GetClassFromTokenAndTypeArgs` for all types.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="20d1b-113">요구 사항</span><span class="sxs-lookup"><span data-stu-id="20d1b-113">Requirements</span></span>  
 <span data-ttu-id="20d1b-114">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="20d1b-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="20d1b-115">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="20d1b-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="20d1b-116">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="20d1b-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="20d1b-117">**.NET Framework 버전:** 1.0, 1.1</span><span class="sxs-lookup"><span data-stu-id="20d1b-117">**.NET Framework Versions:** 1.0, 1.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="20d1b-118">참조</span><span class="sxs-lookup"><span data-stu-id="20d1b-118">See also</span></span>

- [<span data-ttu-id="20d1b-119">ICorProfilerInfo 인터페이스</span><span class="sxs-lookup"><span data-stu-id="20d1b-119">ICorProfilerInfo Interface</span></span>](icorprofilerinfo-interface.md)
