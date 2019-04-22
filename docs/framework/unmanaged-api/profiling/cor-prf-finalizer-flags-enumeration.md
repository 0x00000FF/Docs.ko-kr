---
title: COR_PRF_FINALIZER_FLAGS 열거형
ms.date: 03/30/2017
api_name:
- COR_PRF_FINALIZER_FLAGS
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- COR_PRF_FINALIZER_FLAGS
helpviewer_keywords:
- COR_PRF_FINALIZER_FLAGS enumeration [.NET Framework profiling]
ms.assetid: 297d7721-3911-4f36-9e34-d9da0c33e22a
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: d5037f335e8d66c341d70d91d955a1ac7571b823
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59123762"
---
# <a name="corprffinalizerflags-enumeration"></a><span data-ttu-id="a7862-102">COR_PRF_FINALIZER_FLAGS 열거형</span><span class="sxs-lookup"><span data-stu-id="a7862-102">COR_PRF_FINALIZER_FLAGS Enumeration</span></span>
<span data-ttu-id="a7862-103">개체에 대한 종료자를 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="a7862-103">Describes the finalizer for an object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a7862-104">구문</span><span class="sxs-lookup"><span data-stu-id="a7862-104">Syntax</span></span>  
  
```  
typedef enum {  
    COR_PRF_FINALIZER_CRITICAL = 0x1  
} COR_PRF_FINALIZER_FLAGS;  
```  
  
## <a name="members"></a><span data-ttu-id="a7862-105">멤버</span><span class="sxs-lookup"><span data-stu-id="a7862-105">Members</span></span>  
  
|<span data-ttu-id="a7862-106">멤버</span><span class="sxs-lookup"><span data-stu-id="a7862-106">Member</span></span>|<span data-ttu-id="a7862-107">설명</span><span class="sxs-lookup"><span data-stu-id="a7862-107">Description</span></span>|  
|------------|-----------------|  
|`COR_PRF_FINALIZER_CRITICAL`|<span data-ttu-id="a7862-108">종료 자가 매우 중요 합니다.</span><span class="sxs-lookup"><span data-stu-id="a7862-108">The finalizer is critical.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a7862-109">설명</span><span class="sxs-lookup"><span data-stu-id="a7862-109">Remarks</span></span>  
 <span data-ttu-id="a7862-110">합니다 `COR_PRF_FINALIZER_FLAGS` 열거형에서 사용 되는 [ICorProfilerCallback2::FinalizeableObjectQueued](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-finalizeableobjectqueued-method.md) 개체에 대 한 종료자를 설명 하는 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="a7862-110">The `COR_PRF_FINALIZER_FLAGS` enumeration is used by the [ICorProfilerCallback2::FinalizeableObjectQueued](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-finalizeableobjectqueued-method.md) method to describe the finalizer for an object.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a7862-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="a7862-111">Requirements</span></span>  
 <span data-ttu-id="a7862-112">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="a7862-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a7862-113">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="a7862-113">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="a7862-114">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a7862-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a7862-115">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a7862-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a7862-116">참고자료</span><span class="sxs-lookup"><span data-stu-id="a7862-116">See also</span></span>

- [<span data-ttu-id="a7862-117">프로파일링 열거형</span><span class="sxs-lookup"><span data-stu-id="a7862-117">Profiling Enumerations</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-enumerations.md)
