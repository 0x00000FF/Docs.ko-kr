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
ms.openlocfilehash: ac4a8a0c13ba6aa0d5c65ec7fa1aa3b771c964eb
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33404861"
---
# <a name="cordebugmdaflags-enumeration"></a><span data-ttu-id="c0ac7-102">CorDebugMDAFlags 열거형</span><span class="sxs-lookup"><span data-stu-id="c0ac7-102">CorDebugMDAFlags Enumeration</span></span>
<span data-ttu-id="c0ac7-103">MDA(관리 디버깅 도우미)가 실행된 스레드의 상태를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="c0ac7-103">Specifies the status of the thread on which the managed debugging assistant (MDA) is fired.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c0ac7-104">구문</span><span class="sxs-lookup"><span data-stu-id="c0ac7-104">Syntax</span></span>  
  
```  
typedef enum CorDebugMDAFlags {  
    MDA_FLAG_SLIP = 0x2  
} CorDebugMDAFlags;  
```  
  
## <a name="members"></a><span data-ttu-id="c0ac7-105">멤버</span><span class="sxs-lookup"><span data-stu-id="c0ac7-105">Members</span></span>  
  
|<span data-ttu-id="c0ac7-106">멤버</span><span class="sxs-lookup"><span data-stu-id="c0ac7-106">Member</span></span>|<span data-ttu-id="c0ac7-107">설명</span><span class="sxs-lookup"><span data-stu-id="c0ac7-107">Description</span></span>|  
|------------|-----------------|  
|`MDA_FLAG_SLIP`|<span data-ttu-id="c0ac7-108">MDA가 실행 스레드 MDA가 실행 한 후 누락입니다.</span><span class="sxs-lookup"><span data-stu-id="c0ac7-108">The thread on which the MDA was fired has slipped since the MDA was fired.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c0ac7-109">설명</span><span class="sxs-lookup"><span data-stu-id="c0ac7-109">Remarks</span></span>  
 <span data-ttu-id="c0ac7-110">스레드가 것으로 간주 됩니다 호출 스택에서 더 이상 MDA 원래 발생 설명, *지연*합니다.</span><span class="sxs-lookup"><span data-stu-id="c0ac7-110">When the call stack no longer describes where the MDA was originally raised, the thread is considered to have *slipped*.</span></span> <span data-ttu-id="c0ac7-111">이 스레드를 종료할 때 잘못 된 작업 실행 하 여 일으킵니다 비정상적인 상황입니다.</span><span class="sxs-lookup"><span data-stu-id="c0ac7-111">This is an unusual circumstance brought about by the thread's execution of an invalid operation upon exiting.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c0ac7-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="c0ac7-112">Requirements</span></span>  
 <span data-ttu-id="c0ac7-113">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="c0ac7-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c0ac7-114">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c0ac7-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c0ac7-115">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c0ac7-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c0ac7-116">**.NET framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c0ac7-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c0ac7-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c0ac7-117">See Also</span></span>  
 [<span data-ttu-id="c0ac7-118">디버깅 열거형</span><span class="sxs-lookup"><span data-stu-id="c0ac7-118">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
