---
title: DacpReJitData 구조
ms.date: 02/01/2019
api.name:
- DacpReJitData Structure
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- DacpReJitData Structure
helpviewer.keywords:
- DacpReJitData Structure [.NET Framework debugging]
topic_type:
- apiref
author: hoyosjs
ms.author: juhoyosa
ms.openlocfilehash: 974b99da085a5cb969ab37cddb0f2f2c62010d14
ms.sourcegitcommit: 3500c4845f96a91a438a02ef2c6b4eef45a5e2af
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/07/2019
ms.locfileid: "55828688"
---
# <a name="dacprejitdata-structure"></a><span data-ttu-id="e1085-102">DacpReJitData 구조</span><span class="sxs-lookup"><span data-stu-id="e1085-102">DacpReJitData Structure</span></span>

<span data-ttu-id="e1085-103">지정 된 프로파일러가 계측 메서드에 대 한 기본 정보를 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1085-103">Defines the basic information about a given profiler-instrumented method.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="e1085-104">구문</span><span class="sxs-lookup"><span data-stu-id="e1085-104">Syntax</span></span>

```
struct MSLAYOUT DacpReJitData
{
    enum Flags
    {
        kUnknown,
        kRequested,
        kActive,
        kReverted,
    };

    CLRDATA_ADDRESS                 rejitID;
    Flags                           flags;
    CLRDATA_ADDRESS                 NativeCodeAddr;
};
```

## <a name="members"></a><span data-ttu-id="e1085-105">멤버</span><span class="sxs-lookup"><span data-stu-id="e1085-105">Members</span></span>

| <span data-ttu-id="e1085-106">멤버</span><span class="sxs-lookup"><span data-stu-id="e1085-106">Member</span></span>           | <span data-ttu-id="e1085-107">설명</span><span class="sxs-lookup"><span data-stu-id="e1085-107">Description</span></span>                                                                                      |
| ---------------- | ------------------------------------------------------------------------------------------------ |
| `rejitID`        | <span data-ttu-id="e1085-108">메서드에 대 한 ReJit 수정 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="e1085-108">The ReJit revision number for a method.</span></span>                                                          |
| `flags`          | <span data-ttu-id="e1085-109">지정된 된 버전에 대 한 메서드의 ReJit 계측의 현재 상태를 나타내는 플래그입니다.</span><span class="sxs-lookup"><span data-stu-id="e1085-109">A flag indicating the current state of the method's ReJit instrumentation for the given version.</span></span> |
| `NativeCodeAddr` | <span data-ttu-id="e1085-110">메서드의 rejitted 구현의 기본 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="e1085-110">The base address of the method's rejitted implementation.</span></span>                                         |


## <a name="remarks"></a><span data-ttu-id="e1085-111">설명</span><span class="sxs-lookup"><span data-stu-id="e1085-111">Remarks</span></span>

<span data-ttu-id="e1085-112">이 구조는 런타임 내에서 있으며 모든 헤더 또는 라이브러리 파일을 통해 노출 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e1085-112">This structure lives inside the runtime and is not exposed through any headers or library files.</span></span> <span data-ttu-id="e1085-113">를 사용 하려면 위에서 지정한 대로 구조를 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1085-113">To use it, define the structure as specified above.</span></span> <span data-ttu-id="e1085-114">사용 하 여 구조 정의 해야 `ms_struct` 압축 사용 하지 않는 경우 Microsoft 컴파일러.</span><span class="sxs-lookup"><span data-stu-id="e1085-114">The structure must also be defined using `ms_struct` packing if not using the Microsoft compilers.</span></span>

## <a name="requirements"></a><span data-ttu-id="e1085-115">요구 사항</span><span class="sxs-lookup"><span data-stu-id="e1085-115">Requirements</span></span>
<span data-ttu-id="e1085-116">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="e1085-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
<span data-ttu-id="e1085-117">**헤더:** 없음</span><span class="sxs-lookup"><span data-stu-id="e1085-117">**Header:** None</span></span>  
<span data-ttu-id="e1085-118">**라이브러리:** 없음</span><span class="sxs-lookup"><span data-stu-id="e1085-118">**Library:** None</span></span>  
<span data-ttu-id="e1085-119">**.NET Framework 버전:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="e1085-119">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="e1085-120">참고자료</span><span class="sxs-lookup"><span data-stu-id="e1085-120">See also</span></span>
- [<span data-ttu-id="e1085-121">디버깅</span><span class="sxs-lookup"><span data-stu-id="e1085-121">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
- [<span data-ttu-id="e1085-122">디버깅 구조체</span><span class="sxs-lookup"><span data-stu-id="e1085-122">Debugging Structures</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)
