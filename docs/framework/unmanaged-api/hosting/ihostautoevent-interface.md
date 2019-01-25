---
title: IHostAutoEvent 인터페이스
ms.date: 03/30/2017
api_name:
- IHostAutoEvent
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostAutoEvent
helpviewer_keywords:
- IHostAutoEvent interface [.NET Framework hosting]
ms.assetid: 6c1d15c1-a80a-4ee9-b1e4-6e859db6575a
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2b8cccf395e77c7dfefb85302b522d7e9398ffca
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54730024"
---
# <a name="ihostautoevent-interface"></a><span data-ttu-id="938d3-102">IHostAutoEvent 인터페이스</span><span class="sxs-lookup"><span data-stu-id="938d3-102">IHostAutoEvent Interface</span></span>
<span data-ttu-id="938d3-103">자동 재설정 이벤트의 호스트의 구현에 대 한 표현을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="938d3-103">Provides a representation of the host's implementation of an auto-reset event.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="938d3-104">메서드</span><span class="sxs-lookup"><span data-stu-id="938d3-104">Methods</span></span>  
  
|<span data-ttu-id="938d3-105">메서드</span><span class="sxs-lookup"><span data-stu-id="938d3-105">Method</span></span>|<span data-ttu-id="938d3-106">설명</span><span class="sxs-lookup"><span data-stu-id="938d3-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="938d3-107">Set 메서드</span><span class="sxs-lookup"><span data-stu-id="938d3-107">Set Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostautoevent-set-method.md)|<span data-ttu-id="938d3-108">에서는 현재 `IHostAutoEvent` 신호를 받은 상태 인스턴스입니다.</span><span class="sxs-lookup"><span data-stu-id="938d3-108">Sets the current `IHostAutoEvent` instance to a signaled state.</span></span>|  
|[<span data-ttu-id="938d3-109">Wait 메서드</span><span class="sxs-lookup"><span data-stu-id="938d3-109">Wait Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostautoevent-wait-method.md)|<span data-ttu-id="938d3-110">현재 `IHostAutoEvent` 이벤트가 소유 될 때까지 대기 하는 인스턴스 또는 지정된 된 시간 간격이 경과 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="938d3-110">Causes the current `IHostAutoEvent` instance to wait until the event is owned or a specified amount of time elapses.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="938d3-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="938d3-111">Requirements</span></span>  
 <span data-ttu-id="938d3-112">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="938d3-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="938d3-113">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="938d3-113">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="938d3-114">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="938d3-114">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="938d3-115">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="938d3-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="938d3-116">참고자료</span><span class="sxs-lookup"><span data-stu-id="938d3-116">See also</span></span>
- [<span data-ttu-id="938d3-117">ICLRSyncManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="938d3-117">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)
- [<span data-ttu-id="938d3-118">IHostManualEvent 인터페이스</span><span class="sxs-lookup"><span data-stu-id="938d3-118">IHostManualEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-interface.md)
- [<span data-ttu-id="938d3-119">IHostSyncManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="938d3-119">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)
- [<span data-ttu-id="938d3-120">호스팅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="938d3-120">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
