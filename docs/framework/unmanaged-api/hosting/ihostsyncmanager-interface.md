---
title: IHostSyncManager 인터페이스
ms.date: 03/30/2017
api_name:
- IHostSyncManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostSyncManager
helpviewer_keywords:
- IHostSyncManager interface [.NET Framework hosting]
ms.assetid: 2e081a37-6a28-4c93-b7ab-1c96a464637c
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: fc58e5b7902195860505399b8222afc068fbfc23
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54713264"
---
# <a name="ihostsyncmanager-interface"></a><span data-ttu-id="d62b5-102">IHostSyncManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="d62b5-102">IHostSyncManager Interface</span></span>
<span data-ttu-id="d62b5-103">CLR (공용 언어 런타임)에서 Win32 동기화 함수를 사용 하는 대신 호스트를 호출 하 여 동기화 기본 형식을 만들 수 있도록 하는 메서드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="d62b5-103">Provides methods that allow the common language runtime (CLR) to create synchronization primitives by calling the host instead of using the Win32 synchronization functions.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="d62b5-104">메서드</span><span class="sxs-lookup"><span data-stu-id="d62b5-104">Methods</span></span>  
  
|<span data-ttu-id="d62b5-105">메서드</span><span class="sxs-lookup"><span data-stu-id="d62b5-105">Method</span></span>|<span data-ttu-id="d62b5-106">설명</span><span class="sxs-lookup"><span data-stu-id="d62b5-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="d62b5-107">CreateAutoEvent 메서드</span><span class="sxs-lookup"><span data-stu-id="d62b5-107">CreateAutoEvent Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-createautoevent-method.md)|<span data-ttu-id="d62b5-108">자동 재설정 이벤트 개체를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="d62b5-108">Creates an auto-reset event object.</span></span>|  
|[<span data-ttu-id="d62b5-109">CreateCrst 메서드</span><span class="sxs-lookup"><span data-stu-id="d62b5-109">CreateCrst Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-createcrst-method.md)|<span data-ttu-id="d62b5-110">동기화에 대 한 임계 영역 개체를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="d62b5-110">Creates a critical section object for synchronization.</span></span>|  
|[<span data-ttu-id="d62b5-111">CreateCrstWithSpinCount 메서드</span><span class="sxs-lookup"><span data-stu-id="d62b5-111">CreateCrstWithSpinCount Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-createcrstwithspincount-method.md)|<span data-ttu-id="d62b5-112">동기화에 대 한 스핀 수를 사용 하 여 임계 영역 개체를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="d62b5-112">Creates a critical section object with spin count for synchronization.</span></span>|  
|[<span data-ttu-id="d62b5-113">CreateManualEvent 메서드</span><span class="sxs-lookup"><span data-stu-id="d62b5-113">CreateManualEvent Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-createmanualevent-method.md)|<span data-ttu-id="d62b5-114">수동 재설정 이벤트 개체를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="d62b5-114">Creates a manual-reset event object.</span></span>|  
|[<span data-ttu-id="d62b5-115">CreateMonitorEvent 메서드</span><span class="sxs-lookup"><span data-stu-id="d62b5-115">CreateMonitorEvent Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-createmonitorevent-method.md)|<span data-ttu-id="d62b5-116">자동 재설정 이벤트를 모니터링 대상된 개체를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="d62b5-116">Creates a monitored auto-reset event object.</span></span>|  
|[<span data-ttu-id="d62b5-117">CreateRWLockReaderEvent 메서드</span><span class="sxs-lookup"><span data-stu-id="d62b5-117">CreateRWLockReaderEvent Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-createrwlockreaderevent-method.md)|<span data-ttu-id="d62b5-118">판독기 잠금 구현 하기 위한 수동 재설정 이벤트 개체를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="d62b5-118">Creates a manual-reset event object for the implementation of a reader lock.</span></span>|  
|[<span data-ttu-id="d62b5-119">CreateRWLockWriterEvent 메서드</span><span class="sxs-lookup"><span data-stu-id="d62b5-119">CreateRWLockWriterEvent Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-createrwlockwriterevent-method.md)|<span data-ttu-id="d62b5-120">기록기 잠금 구현에 대 한 자동 재설정 이벤트 개체를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="d62b5-120">Creates an auto-reset event object for the implementation of a writer lock.</span></span>|  
|[<span data-ttu-id="d62b5-121">CreateSemaphore 메서드</span><span class="sxs-lookup"><span data-stu-id="d62b5-121">CreateSemaphore Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-createsemaphore-method.md)|<span data-ttu-id="d62b5-122">만듭니다는 [IHostSemaphore](../../../../docs/framework/unmanaged-api/hosting/ihostsemaphore-interface.md) 대기 이벤트에 대 한 세마포를 사용 하 여 CLR에 대 한 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="d62b5-122">Creates an [IHostSemaphore](../../../../docs/framework/unmanaged-api/hosting/ihostsemaphore-interface.md) object for the CLR to use as a semaphore for wait events.</span></span>|  
|[<span data-ttu-id="d62b5-123">SetCLRSyncManager 메서드</span><span class="sxs-lookup"><span data-stu-id="d62b5-123">SetCLRSyncManager Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-setclrsyncmanager-method.md)|<span data-ttu-id="d62b5-124">집합의 [ICLRSyncManager](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md) 현재 연결할 인스턴스 `IHostSyncManager` 인스턴스.</span><span class="sxs-lookup"><span data-stu-id="d62b5-124">Sets the [ICLRSyncManager](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md) instance to associate with the current `IHostSyncManager` instance.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d62b5-125">설명</span><span class="sxs-lookup"><span data-stu-id="d62b5-125">Remarks</span></span>  
 <span data-ttu-id="d62b5-126">CLR은 호스트의 구현을 검색 `IHostSyncManager` 를 호출 하 여 합니다 [ihostcontrol:: Gethostmanager](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-gethostmanager-method.md) 메서드는 `IID` IID_IHostSyncManager의 합니다.</span><span class="sxs-lookup"><span data-stu-id="d62b5-126">The CLR discovers the host's implementation of `IHostSyncManager` by calling the [IHostControl::GetHostManager](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-gethostmanager-method.md) method with an `IID` of IID_IHostSyncManager.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d62b5-127">요구 사항</span><span class="sxs-lookup"><span data-stu-id="d62b5-127">Requirements</span></span>  
 <span data-ttu-id="d62b5-128">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="d62b5-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d62b5-129">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="d62b5-129">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="d62b5-130">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="d62b5-130">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="d62b5-131">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d62b5-131">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d62b5-132">참고자료</span><span class="sxs-lookup"><span data-stu-id="d62b5-132">See also</span></span>
- [<span data-ttu-id="d62b5-133">ICLRSyncManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="d62b5-133">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)
- [<span data-ttu-id="d62b5-134">호스팅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="d62b5-134">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
