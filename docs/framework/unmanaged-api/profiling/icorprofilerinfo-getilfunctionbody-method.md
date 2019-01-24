---
title: ICorProfilerInfo::GetILFunctionBody 메서드
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo.GetILFunctionBody
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo::GetILFunctionBody
helpviewer_keywords:
- GetILFunctionBody method [.NET Framework profiling]
- ICorProfilerInfo::GetILFunctionBody method [.NET Framework profiling]
ms.assetid: e29b46bc-5fdc-4894-b0c2-619df4b65ded
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: a9e1ef61271e5b413972b8ba40a8fe8bac60ceeb
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54566216"
---
# <a name="icorprofilerinfogetilfunctionbody-method"></a><span data-ttu-id="328de-102">ICorProfilerInfo::GetILFunctionBody 메서드</span><span class="sxs-lookup"><span data-stu-id="328de-102">ICorProfilerInfo::GetILFunctionBody Method</span></span>
<span data-ttu-id="328de-103">헤더부터 Microsoft MSIL (intermediate language) 코드에서 메서드 본문에 대 한 포인터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="328de-103">Gets a pointer to the body of a method in Microsoft intermediate language (MSIL) code, starting at its header.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="328de-104">구문</span><span class="sxs-lookup"><span data-stu-id="328de-104">Syntax</span></span>  
  
```  
HRESULT GetILFunctionBody(  
    [in]  ModuleID    moduleId,  
    [in]  mdMethodDef methodId,  
    [out] LPCBYTE     *ppMethodHeader,  
    [out] ULONG       *pcbMethodSize);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="328de-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="328de-105">Parameters</span></span>  
 `moduleId`  
 <span data-ttu-id="328de-106">[in] 함수가 상주 하는 모듈의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="328de-106">[in] The ID of the module in which the function resides.</span></span>  
  
 `methodId`  
 <span data-ttu-id="328de-107">[in] 메서드에 대 한 메타 데이터 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="328de-107">[in] The metadata token for the method.</span></span>  
  
 `ppMethodHeader`  
 <span data-ttu-id="328de-108">[out] 메서드 헤더에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="328de-108">[out] A pointer to the method's header.</span></span>  
  
 `pcbMethodSize`  
 <span data-ttu-id="328de-109">[out] 메서드의 크기를 지정하는 정수입니다.</span><span class="sxs-lookup"><span data-stu-id="328de-109">[out] An integer that specifies the size of the method.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="328de-110">설명</span><span class="sxs-lookup"><span data-stu-id="328de-110">Remarks</span></span>  
 <span data-ttu-id="328de-111">메서드는 거주 하는 모듈에 의해 범위가 지정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="328de-111">A method is scoped by the module in which it lives.</span></span> <span data-ttu-id="328de-112">때문에 `GetILFunctionBody` 메서드는 CLR (공용 언어 런타임)에서 로드 하기 전에 MSIL 코드로 도구 액세스를 제공 하도록 설계 되었습니다, 메서드의 메타 데이터 토큰을 사용 하 여 원하는 인스턴스를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="328de-112">Because the `GetILFunctionBody` method is designed to give a tool access to the MSIL code before it has been loaded by the common language runtime (CLR), it uses the metadata token of the method to find the desired instance.</span></span>  
  
 <span data-ttu-id="328de-113">`GetILFunctionBody` 경우에 CORPROF_E_FUNCTION_NOT_IL HRESULT를 반환할 수 있습니다는 `methodId` 모든 MSIL 코드 (예: 추상 메서드 또는 플랫폼 호출 (PInvoke) 메서드) 없이 메서드를 가리킵니다.</span><span class="sxs-lookup"><span data-stu-id="328de-113">`GetILFunctionBody` can return a CORPROF_E_FUNCTION_NOT_IL HRESULT if the `methodId` points to a method without any MSIL code (such as an abstract method, or a platform invoke (PInvoke) method).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="328de-114">요구 사항</span><span class="sxs-lookup"><span data-stu-id="328de-114">Requirements</span></span>  
 <span data-ttu-id="328de-115">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="328de-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="328de-116">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="328de-116">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="328de-117">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="328de-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="328de-118">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="328de-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="328de-119">참고자료</span><span class="sxs-lookup"><span data-stu-id="328de-119">See also</span></span>
- [<span data-ttu-id="328de-120">ICorProfilerInfo 인터페이스</span><span class="sxs-lookup"><span data-stu-id="328de-120">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
