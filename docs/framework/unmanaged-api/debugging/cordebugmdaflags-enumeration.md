---
title: CorDebugMDAFlags 열거형
ms.date: 03/30/2017
api_name:
- CorDebugMDAFlags
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CorDebugMDAFlags
helpviewer_keywords:
- CorDebugMDAFlags enumeration [.NET Framework debugging]
ms.assetid: 7c0c92fe-8bd2-477f-b307-aca0143732ca
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: bf9f7f3d3419efc9e1dc7d75fc7272432c0cf5d0
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/10/2019
ms.locfileid: "67739699"
---
# <a name="cordebugmdaflags-enumeration"></a><span data-ttu-id="3feef-102">CorDebugMDAFlags 열거형</span><span class="sxs-lookup"><span data-stu-id="3feef-102">CorDebugMDAFlags Enumeration</span></span>
<span data-ttu-id="3feef-103">MDA(관리 디버깅 도우미)가 실행된 스레드의 상태를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="3feef-103">Specifies the status of the thread on which the managed debugging assistant (MDA) is fired.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3feef-104">구문</span><span class="sxs-lookup"><span data-stu-id="3feef-104">Syntax</span></span>  
  
```cpp  
typedef enum CorDebugMDAFlags {  
    MDA_FLAG_SLIP = 0x2  
} CorDebugMDAFlags;  
```  
  
## <a name="members"></a><span data-ttu-id="3feef-105">멤버</span><span class="sxs-lookup"><span data-stu-id="3feef-105">Members</span></span>  
  
|<span data-ttu-id="3feef-106">멤버</span><span class="sxs-lookup"><span data-stu-id="3feef-106">Member</span></span>|<span data-ttu-id="3feef-107">설명</span><span class="sxs-lookup"><span data-stu-id="3feef-107">Description</span></span>|  
|------------|-----------------|  
|`MDA_FLAG_SLIP`|<span data-ttu-id="3feef-108">MDA가 실행 스레드는 MDA가 실행 되므로 일로 변경 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="3feef-108">The thread on which the MDA was fired has slipped since the MDA was fired.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3feef-109">설명</span><span class="sxs-lookup"><span data-stu-id="3feef-109">Remarks</span></span>  
 <span data-ttu-id="3feef-110">호출 스택에서 더 이상 MDA를 처음으로 발생 설명, 스레드가 있는 것으로 간주 *일로 변경*합니다.</span><span class="sxs-lookup"><span data-stu-id="3feef-110">When the call stack no longer describes where the MDA was originally raised, the thread is considered to have *slipped*.</span></span> <span data-ttu-id="3feef-111">이 스레드의 실행을 끝낼 때 잘못 된 작업을 통해 비정상적인 상황입니다.</span><span class="sxs-lookup"><span data-stu-id="3feef-111">This is an unusual circumstance brought about by the thread's execution of an invalid operation upon exiting.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3feef-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="3feef-112">Requirements</span></span>  
 <span data-ttu-id="3feef-113">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="3feef-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3feef-114">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="3feef-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="3feef-115">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3feef-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3feef-116">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3feef-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3feef-117">참고자료</span><span class="sxs-lookup"><span data-stu-id="3feef-117">See also</span></span>

- [<span data-ttu-id="3feef-118">디버깅 열거형</span><span class="sxs-lookup"><span data-stu-id="3feef-118">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
