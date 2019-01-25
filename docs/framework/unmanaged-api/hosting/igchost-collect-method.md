---
title: IGCHost::Collect 메서드
ms.date: 03/30/2017
api_name:
- IGCHost.Collect
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- Collect
helpviewer_keywords:
- Collect method, IGCHost interface [.NET Framework hosting]
- IGCHost::Collect method [.NET Framework hosting]
ms.assetid: fc7d9448-3186-494d-9f0d-ea39717e9a82
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f911d99470b9870f5c42d4170a4024123c10e7f3
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54511123"
---
# <a name="igchostcollect-method"></a><span data-ttu-id="290da-102">IGCHost::Collect 메서드</span><span class="sxs-lookup"><span data-stu-id="290da-102">IGCHost::Collect Method</span></span>
<span data-ttu-id="290da-103">현재 가비지 컬렉션의 상태에 관계 없이 지정된 된 세대에 발생 하는 수집을 강제로 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="290da-103">Forces a collection to occur for the given generation, regardless of the state of the current garbage collection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="290da-104">구문</span><span class="sxs-lookup"><span data-stu-id="290da-104">Syntax</span></span>  
  
```  
HRESULT Collect (  
    [in] LONG Generation  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="290da-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="290da-105">Parameters</span></span>  
 `Generation`  
 <span data-ttu-id="290da-106">[in] 가비지 수집을 수행 하는 데 기반이 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="290da-106">[in] The generation on which to perform the garbage collection.</span></span> <span data-ttu-id="290da-107">값이-1 모든 세대는 가비지 수집이 실행을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="290da-107">A value of -1 indicates that all generations will undergo a garbage collection.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="290da-108">요구 사항</span><span class="sxs-lookup"><span data-stu-id="290da-108">Requirements</span></span>  
 <span data-ttu-id="290da-109">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="290da-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="290da-110">**헤더:** GCHost.idl, GCHost.h</span><span class="sxs-lookup"><span data-stu-id="290da-110">**Header:** GCHost.idl, GCHost.h</span></span>  
  
 <span data-ttu-id="290da-111">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="290da-111">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="290da-112">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="290da-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="290da-113">참고자료</span><span class="sxs-lookup"><span data-stu-id="290da-113">See also</span></span>
- [<span data-ttu-id="290da-114">IGCHost 인터페이스</span><span class="sxs-lookup"><span data-stu-id="290da-114">IGCHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/igchost-interface.md)
