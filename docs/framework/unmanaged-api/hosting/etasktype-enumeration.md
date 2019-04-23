---
title: ETaskType 열거형
ms.date: 03/30/2017
api_name:
- ETaskType
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ETaskType
helpviewer_keywords:
- ETaskType enumeration [.NET Framework hosting]
ms.assetid: aa527b31-89d4-41f2-ad6f-63b76950b7df
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f256195a4cd5b18f568e05156db867aa5dba9161
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59229825"
---
# <a name="etasktype-enumeration"></a><span data-ttu-id="c80cc-102">ETaskType 열거형</span><span class="sxs-lookup"><span data-stu-id="c80cc-102">ETaskType Enumeration</span></span>
<span data-ttu-id="c80cc-103">으로 표시 되는 작업의 형식을 나타내는 값을 포함 한 [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) 또는 [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md) 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="c80cc-103">Contains values that indicate the type of task that is represented by either an [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) or an [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md) interface.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c80cc-104">구문</span><span class="sxs-lookup"><span data-stu-id="c80cc-104">Syntax</span></span>  
  
```  
typedef enum ETaskType {  
    TT_DEBUGGERHELPER           = 0x1,  
    TT_GC                       = 0x2,  
    TT_FINALIZER                = 0x4,  
    TT_THREADPOOL_TIMER         = 0x8,  
    TT_THREADPOOL_GATE          = 0x10,  
    TT_THREADPOOL_WORKER        = 0x20,  
    TT_THREADPOOL_IOCOMPLETION  = 0x40,  
    TT_ADUNLOAD                 = 0x80,  
    TT_USER                     = 0x100,  
    TT_THREADPOOL_WAIT          = 0x200,  
    TT_UNKNOWN                  = 0x80000000  
} ETaskType;  
```  
  
## <a name="members"></a><span data-ttu-id="c80cc-105">멤버</span><span class="sxs-lookup"><span data-stu-id="c80cc-105">Members</span></span>  
  
|<span data-ttu-id="c80cc-106">멤버</span><span class="sxs-lookup"><span data-stu-id="c80cc-106">Member</span></span>|<span data-ttu-id="c80cc-107">설명</span><span class="sxs-lookup"><span data-stu-id="c80cc-107">Description</span></span>|  
|------------|-----------------|  
|`TT_ADUNLOAD`|<span data-ttu-id="c80cc-108">응용 프로그램 도메인 언로드 작업을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="c80cc-108">The interface represents an application domain unloading task.</span></span>|  
|`TT_DEBUGGERHELPER`|<span data-ttu-id="c80cc-109">디버거 도우미 작업을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="c80cc-109">The interface represents a debugger helper task.</span></span>|  
|`TT_FINALIZER`|<span data-ttu-id="c80cc-110">종료 자가 작업을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="c80cc-110">The interface represents a finalizer task.</span></span>|  
|`TT_GC`|<span data-ttu-id="c80cc-111">가비지 수집 작업을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="c80cc-111">The interface represents a garbage collection task.</span></span>|  
|`TT_THREADPOOL_GATE`|<span data-ttu-id="c80cc-112">게이트 스레드 작업을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="c80cc-112">The interface represents a gate thread task.</span></span>|  
|`TT_THREADPOOL_IOCOMPLETION`|<span data-ttu-id="c80cc-113">I/O 스레드 작업 또는 완료 포트 스레드 작업을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="c80cc-113">The interface represents an I/O thread task or a completion port thread task.</span></span>|  
|`TT_THREADPOOL_TIMER`|<span data-ttu-id="c80cc-114">타이머 스레드 작업을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="c80cc-114">The interface represents a timer thread task.</span></span>|  
|`TT_THREADPOOL_WAIT`|<span data-ttu-id="c80cc-115">대기 스레드 작업을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="c80cc-115">The interface represents a wait thread task.</span></span>|  
|`TT_THREADPOOL_WORKER`|<span data-ttu-id="c80cc-116">작업자 스레드 작업을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="c80cc-116">The interface represents a worker thread task.</span></span>|  
|`TT_UNKNOWN`|<span data-ttu-id="c80cc-117">알 수 없으면 작업 합니다.</span><span class="sxs-lookup"><span data-stu-id="c80cc-117">The task is unknown.</span></span>|  
|`TT_USER`|<span data-ttu-id="c80cc-118">사용자 작업을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="c80cc-118">The interface represents a user task.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="c80cc-119">요구 사항</span><span class="sxs-lookup"><span data-stu-id="c80cc-119">Requirements</span></span>  
 <span data-ttu-id="c80cc-120">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="c80cc-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c80cc-121">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="c80cc-121">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="c80cc-122">**라이브러리:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="c80cc-122">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="c80cc-123">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c80cc-123">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c80cc-124">참고자료</span><span class="sxs-lookup"><span data-stu-id="c80cc-124">See also</span></span>

- [<span data-ttu-id="c80cc-125">호스팅 열거형</span><span class="sxs-lookup"><span data-stu-id="c80cc-125">Hosting Enumerations</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
