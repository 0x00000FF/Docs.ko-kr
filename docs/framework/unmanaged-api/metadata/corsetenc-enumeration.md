---
title: CorSetENC 열거형
ms.date: 03/30/2017
api_name:
- CorSetENC
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorSetENC
helpviewer_keywords:
- CorSetENC enumeration [.NET Framework metadata]
ms.assetid: fe4150e8-071d-43fb-8e06-c3c616dbeed2
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: bf1be8d5c709f3d6e5991e4d33dde2e923291a95
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54569416"
---
# <a name="corsetenc-enumeration"></a><span data-ttu-id="8ea68-102">CorSetENC 열거형</span><span class="sxs-lookup"><span data-stu-id="8ea68-102">CorSetENC Enumeration</span></span>
<span data-ttu-id="8ea68-103">메타데이터 생성 중의 동작에 영향을 주는 데 사용되는 값을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="8ea68-103">Contains values used to influence behavior during the generation of metadata.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8ea68-104">구문</span><span class="sxs-lookup"><span data-stu-id="8ea68-104">Syntax</span></span>  
  
```  
typedef enum CorSetENC {  
  
    MDSetENCOn                  = 0x00000001,  
    MDSetENCOff                 = 0x00000002,  
  
    MDUpdateENC                 = 0x00000001,  
    MDUpdateFull                = 0x00000002,  
    MDUpdateExtension           = 0x00000003,  
    MDUpdateIncremental         = 0x00000004,  
    MDUpdateDelta               = 0x00000005,  
    MDUpdateMask                = 0x00000007  
  
} CorSetENC;  
```  
  
## <a name="members"></a><span data-ttu-id="8ea68-105">멤버</span><span class="sxs-lookup"><span data-stu-id="8ea68-105">Members</span></span>  
  
|<span data-ttu-id="8ea68-106">멤버</span><span class="sxs-lookup"><span data-stu-id="8ea68-106">Member</span></span>|<span data-ttu-id="8ea68-107">설명</span><span class="sxs-lookup"><span data-stu-id="8ea68-107">Description</span></span>|  
|------------|-----------------|  
|`MDSetENCOn`|<span data-ttu-id="8ea68-108">사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8ea68-108">Obsolete.</span></span>|  
|`MDSetENCOff`|<span data-ttu-id="8ea68-109">사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8ea68-109">Obsolete.</span></span>|  
|`MDUpdateENC`|<span data-ttu-id="8ea68-110">메타 데이터를 업데이트할 수 있지만 토큰은 이동할 수 없음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="8ea68-110">Indicates that whereas metadata can be updated, tokens cannot be moved.</span></span>|  
|`MDUpdateFull`|<span data-ttu-id="8ea68-111">업데이트 하는 동안 토큰을 이동할 수 있는지를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="8ea68-111">Indicates that tokens can be moved during updates.</span></span>|  
|`MDUpdateExtension`|<span data-ttu-id="8ea68-112">업데이트 추가 이루어진 수를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="8ea68-112">Indicates that updates can consist only of additions.</span></span> <span data-ttu-id="8ea68-113">토큰을 이동할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="8ea68-113">Tokens cannot be moved.</span></span>|  
|`MDUpdateIncremental`|<span data-ttu-id="8ea68-114">증분 컴파일을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="8ea68-114">Indicates that compilation is incremental.</span></span>|  
|`MDUpdateDelta`|<span data-ttu-id="8ea68-115">해당만 변경 된 메타 데이터를 저장할 것을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="8ea68-115">Indicates that only changed metadata should be saved.</span></span>|  
|`MDUpdateMask`|<span data-ttu-id="8ea68-116">포함 `MDUpdateENC`하십시오 `MDUpdateFull` 및 `MDUpdateIncremental`합니다.</span><span class="sxs-lookup"><span data-stu-id="8ea68-116">Includes `MDUpdateENC`, `MDUpdateFull` and `MDUpdateIncremental`.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="8ea68-117">요구 사항</span><span class="sxs-lookup"><span data-stu-id="8ea68-117">Requirements</span></span>  
 <span data-ttu-id="8ea68-118">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="8ea68-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8ea68-119">**헤더:** CorHdr.h</span><span class="sxs-lookup"><span data-stu-id="8ea68-119">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="8ea68-120">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8ea68-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8ea68-121">참고자료</span><span class="sxs-lookup"><span data-stu-id="8ea68-121">See also</span></span>
- [<span data-ttu-id="8ea68-122">메타데이터 열거형</span><span class="sxs-lookup"><span data-stu-id="8ea68-122">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
