---
title: COR_PRF_JIT_CACHE 열거형
ms.date: 03/30/2017
api_name:
- COR_PRF_JIT_CACHE
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- COR_PRF_JIT_CACHE
helpviewer_keywords:
- COR_PRF_JIT_CACHE enumeration [.NET Framework profiling]
ms.assetid: e7b8f6b4-95bc-4ba5-b9eb-f5590a7326a4
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 6aaa334c83aff18886c0c2db4462d6baaa4cd70f
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54687416"
---
# <a name="corprfjitcache-enumeration"></a><span data-ttu-id="c30f5-102">COR_PRF_JIT_CACHE 열거형</span><span class="sxs-lookup"><span data-stu-id="c30f5-102">COR_PRF_JIT_CACHE Enumeration</span></span>
<span data-ttu-id="c30f5-103">캐시된 함수 검색의 결과를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="c30f5-103">Indicates the result of a cached function search.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c30f5-104">`COR_PRF_CACHED_FUNCTION_FOUND` 값이 0 이면 높으므로 `COR_PRF_JIT_CACHE` 를 부울 대신 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c30f5-104">`COR_PRF_CACHED_FUNCTION_FOUND` has a value of zero, so `COR_PRF_JIT_CACHE` cannot be used as a Boolean surrogate.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c30f5-105">구문</span><span class="sxs-lookup"><span data-stu-id="c30f5-105">Syntax</span></span>  
  
```  
typedef enum {  
    COR_PRF_CACHED_FUNCTION_FOUND,  
    COR_PRF_CACHED_FUNCTION_NOT_FOUND  
} COR_PRF_JIT_CACHE;  
```  
  
## <a name="members"></a><span data-ttu-id="c30f5-106">멤버</span><span class="sxs-lookup"><span data-stu-id="c30f5-106">Members</span></span>  
  
|<span data-ttu-id="c30f5-107">멤버</span><span class="sxs-lookup"><span data-stu-id="c30f5-107">Member</span></span>|<span data-ttu-id="c30f5-108">설명</span><span class="sxs-lookup"><span data-stu-id="c30f5-108">Description</span></span>|  
|------------|-----------------|  
|`COR_PRF_FUNCTION_FOUND`|<span data-ttu-id="c30f5-109">검색 함수를 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c30f5-109">The search found the function.</span></span>|  
|`COR_PRF_FUNCTION_NOT_FOUND`|<span data-ttu-id="c30f5-110">검색 함수를 찾을 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c30f5-110">The search did not find the function.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="c30f5-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="c30f5-111">Requirements</span></span>  
 <span data-ttu-id="c30f5-112">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="c30f5-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c30f5-113">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="c30f5-113">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="c30f5-114">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c30f5-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c30f5-115">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c30f5-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c30f5-116">참고자료</span><span class="sxs-lookup"><span data-stu-id="c30f5-116">See also</span></span>
- [<span data-ttu-id="c30f5-117">프로파일링 열거형</span><span class="sxs-lookup"><span data-stu-id="c30f5-117">Profiling Enumerations</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-enumerations.md)
