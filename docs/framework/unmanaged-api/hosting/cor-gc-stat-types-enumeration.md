---
title: COR_GC_STAT_TYPES 열거형
ms.date: 03/30/2017
api_name:
- COR_GC_STAT_TYPES
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- COR_GC_STAT_TYPES
helpviewer_keywords:
- COR_GC_STAT_TYPES enumeration [.NET Framework hosting]
ms.assetid: fc51d6db-f7f8-408b-b93d-c166fc712c99
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 4bd12feb47352d9bb78aa8ef056072f9bdc6fba3
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54710328"
---
# <a name="corgcstattypes-enumeration"></a><span data-ttu-id="5a69d-102">COR_GC_STAT_TYPES 열거형</span><span class="sxs-lookup"><span data-stu-id="5a69d-102">COR_GC_STAT_TYPES Enumeration</span></span>
<span data-ttu-id="5a69d-103">가비지 컬렉션에 대 한 기록 통계를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="5a69d-103">Specifies the statistics to be recorded for a garbage collection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5a69d-104">구문</span><span class="sxs-lookup"><span data-stu-id="5a69d-104">Syntax</span></span>  
  
```  
typedef enum {  
    COR_GC_COUNTS                 = 0x00000001  
    COR_GC_MEMORYUSAGE            = 0x00000002  
} COR_GC_STAT_TYPES;  
```  
  
## <a name="remarks"></a><span data-ttu-id="5a69d-105">설명</span><span class="sxs-lookup"><span data-stu-id="5a69d-105">Remarks</span></span>  
 <span data-ttu-id="5a69d-106">이 열거형에는 통계를 지정 합니다 [COR_GC_STATS](../../../../docs/framework/unmanaged-api/hosting/cor-gc-stats-structure.md) 구조는 설정할 [iclrgcmanager:: Getstats](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager-getstats-method.md) 메서드.</span><span class="sxs-lookup"><span data-stu-id="5a69d-106">This enumeration specifies which statistics in the [COR_GC_STATS](../../../../docs/framework/unmanaged-api/hosting/cor-gc-stats-structure.md) structure are to be set by [ICLRGCManager::GetStats](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager-getstats-method.md) method.</span></span>  
  
## <a name="members"></a><span data-ttu-id="5a69d-107">멤버</span><span class="sxs-lookup"><span data-stu-id="5a69d-107">Members</span></span>  
  
|<span data-ttu-id="5a69d-108">멤버</span><span class="sxs-lookup"><span data-stu-id="5a69d-108">Member</span></span>|<span data-ttu-id="5a69d-109">설명</span><span class="sxs-lookup"><span data-stu-id="5a69d-109">Description</span></span>|  
|------------|-----------------|  
|`COR_GC_COUNTS`|<span data-ttu-id="5a69d-110">레코드 가비지 수집 횟수 각 세대에 대해 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="5a69d-110">Records the number of garbage collections performed for each generation.</span></span>|  
|`COR_GC_MEMORYUSAGE`|<span data-ttu-id="5a69d-111">레코드 메모리 사용 및 가비지 컬렉션 크기 통계입니다.</span><span class="sxs-lookup"><span data-stu-id="5a69d-111">Records memory usage and garbage collection size statistics.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="5a69d-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="5a69d-112">Requirements</span></span>  
 <span data-ttu-id="5a69d-113">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="5a69d-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5a69d-114">**헤더:** GCHost.idl, GCHost.h</span><span class="sxs-lookup"><span data-stu-id="5a69d-114">**Header:** GCHost.idl, GCHost.h</span></span>  
  
 <span data-ttu-id="5a69d-115">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5a69d-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5a69d-116">참고자료</span><span class="sxs-lookup"><span data-stu-id="5a69d-116">See also</span></span>
- [<span data-ttu-id="5a69d-117">COR_GC_STATS 구조체</span><span class="sxs-lookup"><span data-stu-id="5a69d-117">COR_GC_STATS Structure</span></span>](../../../../docs/framework/unmanaged-api/hosting/cor-gc-stats-structure.md)
- [<span data-ttu-id="5a69d-118">호스팅 열거형</span><span class="sxs-lookup"><span data-stu-id="5a69d-118">Hosting Enumerations</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
