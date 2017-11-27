---
title: "StackTrace_SimpleContext 구조체"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: StackTrace_SimpleContext
api_location: diasymreader.dll
api_type: COM
f1_keywords: SimpleContext
helpviewer_keywords:
- SimpleContext structure [.NET Framework debugging]
- StackTrace_SimpleContext structure [.NET Framework debugging]
ms.assetid: d4cef11f-a8ca-49bc-a1b8-6631f9e28f3e
topic_type: apiref
caps.latest.revision: "13"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 87ce3d50d6da6a7c23b13fa10123033efbb6c52c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="stacktracesimplecontext-structure"></a><span data-ttu-id="0a645-102">StackTrace_SimpleContext 구조체</span><span class="sxs-lookup"><span data-stu-id="0a645-102">StackTrace_SimpleContext Structure</span></span>
<span data-ttu-id="0a645-103">전체 `CONTEXT` 구조체 대신 사용할 수 있는 단순 컨텍스트를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="0a645-103">Provides a simple context that can be used in place of a full `CONTEXT` structure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0a645-104">구문</span><span class="sxs-lookup"><span data-stu-id="0a645-104">Syntax</span></span>  
  
```  
struct StackTrace_SimpleContext  
{  
    ULONG64 StackOffset;       // ESP on x86  
    ULONG64 FrameOffset;       // EBP on x86  
    ULONG64 InstructionOffset; // EIP on x86  
};  
```  
  
## <a name="members"></a><span data-ttu-id="0a645-105">멤버</span><span class="sxs-lookup"><span data-stu-id="0a645-105">Members</span></span>  
  
|<span data-ttu-id="0a645-106">멤버</span><span class="sxs-lookup"><span data-stu-id="0a645-106">Member</span></span>|<span data-ttu-id="0a645-107">설명</span><span class="sxs-lookup"><span data-stu-id="0a645-107">Description</span></span>|  
|------------|-----------------|  
|`StackOffset`|<span data-ttu-id="0a645-108">스택 포인터 또는 enter 스택 포인터 (ESP) x86 플랫폼입니다.</span><span class="sxs-lookup"><span data-stu-id="0a645-108">The stack pointer, or the enter stack pointer (ESP) on x86 platforms.</span></span>|  
|`FrameOffset`|<span data-ttu-id="0a645-109">프레임 오프셋 또는 EBP 레지스터 x86 플랫폼입니다.</span><span class="sxs-lookup"><span data-stu-id="0a645-109">The frame offset, or the EBP register on x86 platforms.</span></span>|  
|`InstructionOffset`|<span data-ttu-id="0a645-110">명령 포인터 또는 enter 명령 포인터 (EIP) x86 플랫폼입니다.</span><span class="sxs-lookup"><span data-stu-id="0a645-110">The instruction pointer, or the enter instruction pointer (EIP) on x86 platforms.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0a645-111">설명</span><span class="sxs-lookup"><span data-stu-id="0a645-111">Remarks</span></span>  
 <span data-ttu-id="0a645-112">선택적으로 사용할 수 스택 추적 기능 일반적으로 필요로 하므로 주소, 프레임 오프셋 및 스택 주소 반환 하는 `SimpleContext` 큰 아니라 구조가 `CONTEXT` 구조입니다.</span><span class="sxs-lookup"><span data-stu-id="0a645-112">Because stack trace functions typically need to return only the address, frame offset, and stack address, you can optionally use the `SimpleContext` structure instead of a large `CONTEXT` structure.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0a645-113">요구 사항</span><span class="sxs-lookup"><span data-stu-id="0a645-113">Requirements</span></span>  
 <span data-ttu-id="0a645-114">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="0a645-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0a645-115">**헤더:** SOS_Stacktrace.h</span><span class="sxs-lookup"><span data-stu-id="0a645-115">**Header:** SOS_Stacktrace.h</span></span>  
  
 <span data-ttu-id="0a645-116">**.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0a645-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0a645-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="0a645-117">See Also</span></span>  
 [<span data-ttu-id="0a645-118">디버깅 구조체</span><span class="sxs-lookup"><span data-stu-id="0a645-118">Debugging Structures</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)  
 [<span data-ttu-id="0a645-119">디버깅</span><span class="sxs-lookup"><span data-stu-id="0a645-119">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
