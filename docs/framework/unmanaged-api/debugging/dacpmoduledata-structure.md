---
title: DacpModuleData 구조
ms.date: 02/01/2019
api.name:
- DacpModuleData Structure
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- DacpModuleData Structure
helpviewer.keywords:
- DacpModuleData Structure [.NET Framework debugging]
topic_type:
- apiref
author: hoyosjs
ms.author: juhoyosa
ms.openlocfilehash: db3fdaa768e3d1b445f08c3964521570631f0965
ms.sourcegitcommit: 3500c4845f96a91a438a02ef2c6b4eef45a5e2af
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/07/2019
ms.locfileid: "55828668"
---
# <a name="dacpmoduledata-structure"></a><span data-ttu-id="6b4a9-102">DacpModuleData 구조</span><span class="sxs-lookup"><span data-stu-id="6b4a9-102">DacpModuleData Structure</span></span>

<span data-ttu-id="6b4a9-103">모듈의 런타임 정보에 대 한 전송 버퍼를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="6b4a9-103">Defines a transport buffer for a module's runtime information.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="6b4a9-104">구문</span><span class="sxs-lookup"><span data-stu-id="6b4a9-104">Syntax</span></span>

```
struct DacpModuleData
{
    CLRDATA_ADDRESS Address;
    CLRDATA_ADDRESS File; 
    CLRDATA_ADDRESS  ilBase;
    char payLoad[132];
};
```

## <a name="members"></a><span data-ttu-id="6b4a9-105">멤버</span><span class="sxs-lookup"><span data-stu-id="6b4a9-105">Members</span></span>

| <span data-ttu-id="6b4a9-106">멤버</span><span class="sxs-lookup"><span data-stu-id="6b4a9-106">Member</span></span>    | <span data-ttu-id="6b4a9-107">설명</span><span class="sxs-lookup"><span data-stu-id="6b4a9-107">Description</span></span>                                                             |
| --------- | ----------------------------------------------------------------------- |
| `Address` | <span data-ttu-id="6b4a9-108">모듈 개체의 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="6b4a9-108">Address of the module object.</span></span>                                           |
| `File`    | <span data-ttu-id="6b4a9-109">Pe (이식 가능) 파일에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="6b4a9-109">A pointer to the portable executable (PE) file.</span></span>                       |
| `ilBase`  | <span data-ttu-id="6b4a9-110">로드 된 이미지의 주소의 기본입니다.</span><span class="sxs-lookup"><span data-stu-id="6b4a9-110">The address of the loaded image's base.</span></span>                                 |
| `payLoad` | <span data-ttu-id="6b4a9-111">런타임에서 사용 되는 추가 모듈 정보에 대 한 페이로드 버퍼입니다.</span><span class="sxs-lookup"><span data-stu-id="6b4a9-111">A payload buffer for additional module information used by the runtime.</span></span> |


## <a name="remarks"></a><span data-ttu-id="6b4a9-112">설명</span><span class="sxs-lookup"><span data-stu-id="6b4a9-112">Remarks</span></span>

<span data-ttu-id="6b4a9-113">이 구조는 런타임 내에서 있으며 모든 헤더 또는 라이브러리 파일을 통해 노출 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6b4a9-113">This structure lives inside the runtime and is not exposed through any headers or library files.</span></span> <span data-ttu-id="6b4a9-114">를 사용 하려면 위에서 지정한 대로 구조를 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="6b4a9-114">To use it, define the structure as specified above.</span></span>

## <a name="requirements"></a><span data-ttu-id="6b4a9-115">요구 사항</span><span class="sxs-lookup"><span data-stu-id="6b4a9-115">Requirements</span></span>
<span data-ttu-id="6b4a9-116">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="6b4a9-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
<span data-ttu-id="6b4a9-117">**헤더:** 없음</span><span class="sxs-lookup"><span data-stu-id="6b4a9-117">**Header:** None</span></span>  
<span data-ttu-id="6b4a9-118">**라이브러리:** 없음</span><span class="sxs-lookup"><span data-stu-id="6b4a9-118">**Library:** None</span></span>  
<span data-ttu-id="6b4a9-119">**.NET Framework 버전:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="6b4a9-119">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="6b4a9-120">참고자료</span><span class="sxs-lookup"><span data-stu-id="6b4a9-120">See also</span></span>
- [<span data-ttu-id="6b4a9-121">디버깅</span><span class="sxs-lookup"><span data-stu-id="6b4a9-121">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
- [<span data-ttu-id="6b4a9-122">디버깅 구조체</span><span class="sxs-lookup"><span data-stu-id="6b4a9-122">Debugging Structures</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)
