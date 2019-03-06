---
title: IGCHost::GetStats 메서드
ms.date: 03/30/2017
api_name:
- IGCHost.GetStats
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- GetStats
helpviewer_keywords:
- GetStats method, IGCHost interface [.NET Framework hosting]
- IGCHost::GetStats method [.NET Framework hosting]
ms.assetid: c4ae022c-46ac-4f19-9ddd-09b955f19412
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 1b8af1de3daf08a8389a5b0e6ebb278646345f9b
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/06/2019
ms.locfileid: "57482615"
---
# <a name="igchostgetstats-method"></a><span data-ttu-id="961c7-102">IGCHost::GetStats 메서드</span><span class="sxs-lookup"><span data-stu-id="961c7-102">IGCHost::GetStats Method</span></span>
<span data-ttu-id="961c7-103">가비지 컬렉션 시스템의 현재 상태에 대 한 통계를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="961c7-103">Gets the statistics for the current state of the garbage collection system.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="961c7-104">구문</span><span class="sxs-lookup"><span data-stu-id="961c7-104">Syntax</span></span>  
  
```  
HRESULT GetStats (  
    [in, out] COR_GC_STATS *pStats  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="961c7-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="961c7-105">Parameters</span></span>  
 `pStats`  
 <span data-ttu-id="961c7-106">[out에서] 에 대 한 포인터를 [COR_GC_STATS](../../../../docs/framework/unmanaged-api/hosting/cor-gc-stats-structure.md) 가비지 컬렉션 시스템의 현재 상태에 대 한 통계를 포함 하는 구조입니다.</span><span class="sxs-lookup"><span data-stu-id="961c7-106">[in, out] A pointer to a [COR_GC_STATS](../../../../docs/framework/unmanaged-api/hosting/cor-gc-stats-structure.md) structure that contains the statistics for the current state of the garbage collection system.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="961c7-107">설명</span><span class="sxs-lookup"><span data-stu-id="961c7-107">Remarks</span></span>  
 <span data-ttu-id="961c7-108">통계를 가비지 수집 시스템이 작동 하는 데 스마트 할당 시스템에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="961c7-108">The statistics can be used by a smart allocation system to help the garbage collection system operate.</span></span> <span data-ttu-id="961c7-109">예를 들어, 더 많은 메모리를 추가 하거나 수집을 강제 실행 해야 하는 통계를 검토 한 후 할당 시스템 결정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="961c7-109">For example, the allocation system may determine, after reviewing the statistics, that it needs to add more memory or force a collection.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="961c7-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="961c7-110">Requirements</span></span>  
 <span data-ttu-id="961c7-111">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="961c7-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="961c7-112">**헤더:** GCHost.idl, GCHost.h</span><span class="sxs-lookup"><span data-stu-id="961c7-112">**Header:** GCHost.idl, GCHost.h</span></span>  
  
 <span data-ttu-id="961c7-113">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="961c7-113">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="961c7-114">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="961c7-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="961c7-115">참고자료</span><span class="sxs-lookup"><span data-stu-id="961c7-115">See also</span></span>
- [<span data-ttu-id="961c7-116">IGCHost 인터페이스</span><span class="sxs-lookup"><span data-stu-id="961c7-116">IGCHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/igchost-interface.md)
