---
title: ICorProfilerObjectEnum::Clone 메서드
ms.date: 03/30/2017
api_name:
- ICorProfilerObjectEnum.Clone
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerObjectEnum::Clone
helpviewer_keywords:
- Clone method, ICorProfilerObjectEnum interface [.NET Framework profiling]
- ICorProfilerObjectEnum::Clone method [.NET Framework profiling]
ms.assetid: b0b2facd-5991-4f4c-932d-c4937f45cef9
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: ea0484db53a94a3134b85f97b294c5eb7d1dc7e6
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/06/2019
ms.locfileid: "57500566"
---
# <a name="icorprofilerobjectenumclone-method"></a><span data-ttu-id="b18f9-102">ICorProfilerObjectEnum::Clone 메서드</span><span class="sxs-lookup"><span data-stu-id="b18f9-102">ICorProfilerObjectEnum::Clone Method</span></span>
<span data-ttu-id="b18f9-103">이 복사본에 인터페이스 포인터를 가져옵니다 [ICorProfilerObjectEnum](../../../../docs/framework/unmanaged-api/profiling/icorprofilerobjectenum-interface.md) 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="b18f9-103">Gets an interface pointer to a copy of this [ICorProfilerObjectEnum](../../../../docs/framework/unmanaged-api/profiling/icorprofilerobjectenum-interface.md) interface.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b18f9-104">구문</span><span class="sxs-lookup"><span data-stu-id="b18f9-104">Syntax</span></span>  
  
```  
HRESULT Clone (  
    [out] ICorProfilerObjectEnum   **ppEnum);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b18f9-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="b18f9-105">Parameters</span></span>  
 `ppEnum`  
 <span data-ttu-id="b18f9-106">[out] 이 복사본을 가리키고 있는 인터페이스 포인터에 대 한 포인터 `ICorProfilerObjectEnum` 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="b18f9-106">[out] A pointer to the interface pointer that in turn points to the copy of this `ICorProfilerObjectEnum` interface.</span></span> <span data-ttu-id="b18f9-107">복사본을이 별도로 자체 열거형의 상태를 유지 관리합니다.</span><span class="sxs-lookup"><span data-stu-id="b18f9-107">The copy maintains its own enumeration state separately from this one.</span></span> <span data-ttu-id="b18f9-108">그러나이 열거자의 현재 커서 위치와 동일 복사본의 초기 커서 위치가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b18f9-108">However, the copy's initial cursor position will be the same as this enumerator's current cursor position.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b18f9-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="b18f9-109">Requirements</span></span>  
 <span data-ttu-id="b18f9-110">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="b18f9-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b18f9-111">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="b18f9-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="b18f9-112">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b18f9-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b18f9-113">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b18f9-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b18f9-114">참고자료</span><span class="sxs-lookup"><span data-stu-id="b18f9-114">See also</span></span>
- [<span data-ttu-id="b18f9-115">ICorProfilerObjectEnum 인터페이스</span><span class="sxs-lookup"><span data-stu-id="b18f9-115">ICorProfilerObjectEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerobjectenum-interface.md)
