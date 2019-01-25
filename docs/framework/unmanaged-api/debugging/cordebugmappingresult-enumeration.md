---
title: CorDebugMappingResult 열거형
ms.date: 03/30/2017
api_name:
- CorDebugMappingResult
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CorDebugMappingResult
helpviewer_keywords:
- CorDebugMappingResult enumeration [.NET Framework debugging]
ms.assetid: 701281dd-2936-45c8-a1f0-3bf7332b093b
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 16c4e03667d4af3ab5cc8b653d77f15eaef25843
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54691829"
---
# <a name="cordebugmappingresult-enumeration"></a><span data-ttu-id="cfb0f-102">CorDebugMappingResult 열거형</span><span class="sxs-lookup"><span data-stu-id="cfb0f-102">CorDebugMappingResult Enumeration</span></span>
<span data-ttu-id="cfb0f-103">IP(명령 포인터)의 값을 가져온 방법에 대한 세부 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="cfb0f-103">Provides the details of how the value of the instruction pointer (IP) was obtained.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cfb0f-104">구문</span><span class="sxs-lookup"><span data-stu-id="cfb0f-104">Syntax</span></span>  
  
```  
typedef enum CorDebugMappingResult {  
    MAPPING_PROLOG              = 0x1,  
    MAPPING_EPILOG              = 0x2,  
    MAPPING_NO_INFO             = 0x4,  
    MAPPING_UNMAPPED_ADDRESS    = 0x8,  
    MAPPING_EXACT               = 0x10,  
    MAPPING_APPROXIMATE         = 0x20,  
} CorDebugMappingResult;  
```  
  
## <a name="members"></a><span data-ttu-id="cfb0f-105">멤버</span><span class="sxs-lookup"><span data-stu-id="cfb0f-105">Members</span></span>  
  
|<span data-ttu-id="cfb0f-106">멤버</span><span class="sxs-lookup"><span data-stu-id="cfb0f-106">Member</span></span>|<span data-ttu-id="cfb0f-107">설명</span><span class="sxs-lookup"><span data-stu-id="cfb0f-107">Description</span></span>|  
|------------|-----------------|  
|`MAPPING_PROLOG`|<span data-ttu-id="cfb0f-108">네이티브 코드를 프롤로그에 이므로 IP의 값은 0입니다.</span><span class="sxs-lookup"><span data-stu-id="cfb0f-108">The native code is in the prolog, so the value of the IP is 0.</span></span>|  
|`MAPPING_EPILOG`|<span data-ttu-id="cfb0f-109">네이티브 코드 에필로그에서 이므로 IP의 값은 메서드의 마지막 명령의 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="cfb0f-109">The native code is in an epilog, so the value of the IP is the address of the last instruction of the method.</span></span>|  
|`MAPPING_NO_INFO`|<span data-ttu-id="cfb0f-110">매핑 정보가 없는 IP의 값이 0 이므로 메서드를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cfb0f-110">No mapping information is available for the method, so the value of the IP is 0.</span></span>|  
|`MAPPING_UNMAPPED_ADDRESS`|<span data-ttu-id="cfb0f-111">메서드에 대 한 매핑 정보에 경우에 현재 주소는 Microsoft intermediate language (MSIL) 코드에 매핑할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="cfb0f-111">Although there is mapping information for the method, the current address cannot be mapped to Microsoft intermediate language (MSIL) code.</span></span> <span data-ttu-id="cfb0f-112">IP의 값은 0입니다.</span><span class="sxs-lookup"><span data-stu-id="cfb0f-112">The value of the IP is 0.</span></span>|  
|`MAPPING_EXACT`|<span data-ttu-id="cfb0f-113">메서드는 MSIL 코드를 정확 하 게 매핑되어 있거나 프레임 IP의 값은 정확 하 게 해석 되었으므로 합니다.</span><span class="sxs-lookup"><span data-stu-id="cfb0f-113">Either the method maps exactly to MSIL code or the frame has been interpreted, so the value of the IP is accurate.</span></span>|  
|`MAPPING_APPROXIMATE`|<span data-ttu-id="cfb0f-114">메서드를 성공적으로 매핑되지만 IP의 값은 근사치일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cfb0f-114">The method was successfully mapped, but the value of the IP may be approximate.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="cfb0f-115">설명</span><span class="sxs-lookup"><span data-stu-id="cfb0f-115">Remarks</span></span>  
 <span data-ttu-id="cfb0f-116">사용할 수는 [icordebugilframe:: Getip](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-getip-method.md) 메서드 명령 포인터의 값을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="cfb0f-116">You can use the [ICorDebugILFrame::GetIP](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-getip-method.md) method to obtain the value of the instruction pointer.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cfb0f-117">요구 사항</span><span class="sxs-lookup"><span data-stu-id="cfb0f-117">Requirements</span></span>  
 <span data-ttu-id="cfb0f-118">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="cfb0f-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cfb0f-119">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="cfb0f-119">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="cfb0f-120">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="cfb0f-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="cfb0f-121">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cfb0f-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cfb0f-122">참고자료</span><span class="sxs-lookup"><span data-stu-id="cfb0f-122">See also</span></span>
- [<span data-ttu-id="cfb0f-123">디버깅 열거형</span><span class="sxs-lookup"><span data-stu-id="cfb0f-123">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
