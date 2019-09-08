---
title: ASM_CACHE_FLAGS 열거형
ms.date: 03/30/2017
api_name:
- ASM_CACHE_FLAGS
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- ASM_CACHE_FLAGS
helpviewer_keywords:
- ASM_CACHE_FLAGS enumeration [.NET Framework fusion]
ms.assetid: 82e9a7da-321b-48b8-b239-52eaffda6be8
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 0e3e9da3db71d3e24b2a60ff032a631680055b88
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/07/2019
ms.locfileid: "70795279"
---
# <a name="asm_cache_flags-enumeration"></a><span data-ttu-id="ae78b-102">ASM_CACHE_FLAGS 열거형</span><span class="sxs-lookup"><span data-stu-id="ae78b-102">ASM_CACHE_FLAGS Enumeration</span></span>
<span data-ttu-id="ae78b-103">전역 어셈블리 캐시에서 [Iassemblycacheitem](iassemblycacheitem-interface.md) 이 나타내는 어셈블리의 원본을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="ae78b-103">Indicates the source of an assembly that is represented by [IAssemblyCacheItem](iassemblycacheitem-interface.md) in the global assembly cache.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ae78b-104">구문</span><span class="sxs-lookup"><span data-stu-id="ae78b-104">Syntax</span></span>  
  
```cpp  
typedef enum {  
    ASM_CACHE_ZAP       = 0x01,  
    ASM_CACHE_GAC       = 0x02,  
    ASM_CACHE_DOWNLOAD  = 0x04,  
    ASM_CACHE_ROOT      = 0x08,  
    ASM_CACHE_ROOT_EX   = 0x80  
} ASM_CACHE_FLAGS;  
```  
  
## <a name="members"></a><span data-ttu-id="ae78b-105">멤버</span><span class="sxs-lookup"><span data-stu-id="ae78b-105">Members</span></span>  
  
|<span data-ttu-id="ae78b-106">멤버</span><span class="sxs-lookup"><span data-stu-id="ae78b-106">Member</span></span>|<span data-ttu-id="ae78b-107">Description</span><span class="sxs-lookup"><span data-stu-id="ae78b-107">Description</span></span>|  
|------------|-----------------|  
|`ASM_CACHE_ZAP`|<span data-ttu-id="ae78b-108">Ngen.exe를 사용 하 여 미리 컴파일된 어셈블리의 캐시를 열거 합니다.</span><span class="sxs-lookup"><span data-stu-id="ae78b-108">Enumerates the cache of precompiled assemblies by using Ngen.exe.</span></span>|  
|`ASM_CACHE_GAC`|<span data-ttu-id="ae78b-109">전역 어셈블리 캐시를 열거 합니다.</span><span class="sxs-lookup"><span data-stu-id="ae78b-109">Enumerates the global assembly cache.</span></span>|  
|`ASM_CACHE_DOWNLOAD`|<span data-ttu-id="ae78b-110">요청 시 다운로드 되었거나 섀도 복사 된 어셈블리를 열거 합니다.</span><span class="sxs-lookup"><span data-stu-id="ae78b-110">Enumerates the assemblies that have been downloaded on demand or that have been shadow-copied.</span></span>|  
|`ASM_CACHE_ROOT`|<span data-ttu-id="ae78b-111">[Getcachepath](getcachepath-function.md) 함수가 CLR (공용 언어 런타임) 버전 2.0에 대 한 전역 어셈블리 캐시에 대 한 경로를 반환 해야 함을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="ae78b-111">Indicates that the [GetCachePath](getcachepath-function.md) function should return the path to the global assembly cache for the common language runtime (CLR) version 2.0.</span></span> <span data-ttu-id="ae78b-112">[Getcachepath](getcachepath-function.md)호출의 컨텍스트에서만 의미가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ae78b-112">Meaningful only in the context of a call to [GetCachePath](getcachepath-function.md).</span></span>|  
|`ASM_CACHE_ROOT_EX`|<span data-ttu-id="ae78b-113">[Getcachepath](getcachepath-function.md) 함수가 CLR 버전 4에 대 한 전역 어셈블리 캐시에 대 한 경로를 반환 해야 함을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="ae78b-113">Indicates that the [GetCachePath](getcachepath-function.md) function should return the path to the global assembly cache for CLR version 4.</span></span> <span data-ttu-id="ae78b-114">[Getcachepath](getcachepath-function.md)호출의 컨텍스트에서만 의미가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ae78b-114">Meaningful only in the context of a call to [GetCachePath](getcachepath-function.md).</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="ae78b-115">요구 사항</span><span class="sxs-lookup"><span data-stu-id="ae78b-115">Requirements</span></span>  
 <span data-ttu-id="ae78b-116">**플랫폼** [시스템 요구 사항](../../get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="ae78b-116">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ae78b-117">**헤더:** Fusion. h</span><span class="sxs-lookup"><span data-stu-id="ae78b-117">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="ae78b-118">**라이브러리** Mscoree.dll에 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ae78b-118">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="ae78b-119">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ae78b-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ae78b-120">참고자료</span><span class="sxs-lookup"><span data-stu-id="ae78b-120">See also</span></span>

- [<span data-ttu-id="ae78b-121">GetCachePath 함수</span><span class="sxs-lookup"><span data-stu-id="ae78b-121">GetCachePath Function</span></span>](getcachepath-function.md)
- [<span data-ttu-id="ae78b-122">IAssemblyCacheItem 인터페이스</span><span class="sxs-lookup"><span data-stu-id="ae78b-122">IAssemblyCacheItem Interface</span></span>](iassemblycacheitem-interface.md)
- [<span data-ttu-id="ae78b-123">Fusion 열거형</span><span class="sxs-lookup"><span data-stu-id="ae78b-123">Fusion Enumerations</span></span>](fusion-enumerations.md)
