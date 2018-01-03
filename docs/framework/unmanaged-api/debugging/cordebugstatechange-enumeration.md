---
title: "CorDebugStateChange 열거형"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CorDebugStateChange
api_location: mscordbi.dll
api_type: COM
ms.assetid: 1d4424ab-5143-4e50-a84a-ceeb4ddf3bba
topic_type: apiref
caps.latest.revision: "5"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: da9d2bb793340aa4736e0b26ab9bf9d5ec7c546a
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="cordebugstatechange-enumeration"></a><span data-ttu-id="0fa9c-102">CorDebugStateChange 열거형</span><span class="sxs-lookup"><span data-stu-id="0fa9c-102">CorDebugStateChange Enumeration</span></span>
<span data-ttu-id="0fa9c-103">프로세스에 대한 변경 내용을 기반으로 삭제해야 하는 캐시된 데이터의 양을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="0fa9c-103">Describes the amount of cached data that must be discarded based on changes to the process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0fa9c-104">구문</span><span class="sxs-lookup"><span data-stu-id="0fa9c-104">Syntax</span></span>  
  
```  
typedef enum CorDebugStateChange  
{  
    PROCESS_RUNNING = 0x0000001,   
    FLUSH_ALL       = 0x0000002,   
} CorDebugStateChange;  
```  
  
## <a name="members"></a><span data-ttu-id="0fa9c-105">멤버</span><span class="sxs-lookup"><span data-stu-id="0fa9c-105">Members</span></span>  
  
|<span data-ttu-id="0fa9c-106">멤버</span><span class="sxs-lookup"><span data-stu-id="0fa9c-106">Member</span></span>|<span data-ttu-id="0fa9c-107">설명</span><span class="sxs-lookup"><span data-stu-id="0fa9c-107">Description</span></span>|  
|------------|-----------------|  
|`PROCESS_RUNNING`|<span data-ttu-id="0fa9c-108">프로세스가 정방향 실행을 통해 새로운 메모리 상태에 도달했습니다.</span><span class="sxs-lookup"><span data-stu-id="0fa9c-108">The process reached a new memory state via forward execution.</span></span>|  
|`SET_CONTEXT_FLAG_UNWIND_FRAME`|<span data-ttu-id="0fa9c-109">프로세스의 메모리가 이전과 임의적으로 달라질 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0fa9c-109">The process' memory may be arbitrarily different than it was previously.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0fa9c-110">설명</span><span class="sxs-lookup"><span data-stu-id="0fa9c-110">Remarks</span></span>  
 <span data-ttu-id="0fa9c-111">멤버는 `CorDebugStateChange` 열거형 디버거를 호출 하는 경우는 인수로 제공 되는 [ProcessStateChanged](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-processstatechanged-method.md) 메서드</span><span class="sxs-lookup"><span data-stu-id="0fa9c-111">A member of the `CorDebugStateChange` enumeration is provided as an argument when the debugger calls the [ProcessStateChanged](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-processstatechanged-method.md) method</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="0fa9c-112">이 열거형은 .NET 네이티브 디버깅 시나리오에서만 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="0fa9c-112">This enumeration is intended for use in .NET Native debugging scenarios only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0fa9c-113">요구 사항</span><span class="sxs-lookup"><span data-stu-id="0fa9c-113">Requirements</span></span>  
 <span data-ttu-id="0fa9c-114">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="0fa9c-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0fa9c-115">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="0fa9c-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="0fa9c-116">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0fa9c-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0fa9c-117">**.NET framework 버전:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0fa9c-117">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0fa9c-118">참고 항목</span><span class="sxs-lookup"><span data-stu-id="0fa9c-118">See Also</span></span>  
 [<span data-ttu-id="0fa9c-119">디버깅 열거형</span><span class="sxs-lookup"><span data-stu-id="0fa9c-119">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)  
 [<span data-ttu-id="0fa9c-120">디버깅</span><span class="sxs-lookup"><span data-stu-id="0fa9c-120">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
