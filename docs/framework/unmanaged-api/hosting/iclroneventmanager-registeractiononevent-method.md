---
title: ICLROnEventManager::RegisterActionOnEvent 메서드
ms.date: 03/30/2017
api_name:
- ICLROnEventManager.RegisterActionOnEvent
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLROnEventManager::RegisterActionOnEvent
helpviewer_keywords:
- ICLROnEventManager::RegisterActionOnEvent method [.NET Framework hosting]
- RegisterActionOnEvent method [.NET Framework hosting]
ms.assetid: b944cf49-918d-4c4e-993b-77d097a52550
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 36d4b0692b112a66fea3dd878c7054a083fb68ff
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2019
ms.locfileid: "69951143"
---
# <a name="iclroneventmanagerregisteractiononevent-method"></a><span data-ttu-id="01929-102">ICLROnEventManager::RegisterActionOnEvent 메서드</span><span class="sxs-lookup"><span data-stu-id="01929-102">ICLROnEventManager::RegisterActionOnEvent Method</span></span>
<span data-ttu-id="01929-103">지정 된 이벤트에 대 한 콜백 포인터를 등록 합니다.</span><span class="sxs-lookup"><span data-stu-id="01929-103">Registers a callback pointer for the specified event.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="01929-104">구문</span><span class="sxs-lookup"><span data-stu-id="01929-104">Syntax</span></span>  
  
```cpp  
HRESULT RegisterActionOnEvent (  
    [in] EClrEvent event,  
    [in] IActionOnCLREvent *pAction  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="01929-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="01929-105">Parameters</span></span>  
 `event`  
 <span data-ttu-id="01929-106">진행 에 설명 `pAction`된 콜백 포인터를 등록할 이벤트를 나타내는 [EClrEvent](../../../../docs/framework/unmanaged-api/hosting/eclrevent-enumeration.md) 값 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="01929-106">[in] One of the [EClrEvent](../../../../docs/framework/unmanaged-api/hosting/eclrevent-enumeration.md) values, indicating the event for which to register the callback pointer described by `pAction`.</span></span>  
  
 `pAction`  
 <span data-ttu-id="01929-107">진행 등록 된 이벤트가 발생할 때 호출 되는 [IActionOnCLREvent](../../../../docs/framework/unmanaged-api/hosting/iactiononclrevent-interface.md) 개체에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="01929-107">[in] A pointer to an [IActionOnCLREvent](../../../../docs/framework/unmanaged-api/hosting/iactiononclrevent-interface.md) object that is called when the registered event fires.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="01929-108">반환 값</span><span class="sxs-lookup"><span data-stu-id="01929-108">Return Value</span></span>  
  
|<span data-ttu-id="01929-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="01929-109">HRESULT</span></span>|<span data-ttu-id="01929-110">Description</span><span class="sxs-lookup"><span data-stu-id="01929-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="01929-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="01929-111">S_OK</span></span>|<span data-ttu-id="01929-112">`RegisterActionOnEvent`성공적으로 반환 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="01929-112">`RegisterActionOnEvent` returned successfully.</span></span>|  
|<span data-ttu-id="01929-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="01929-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="01929-114">CLR (공용 언어 런타임)이 프로세스에 로드 되지 않았거나 CLR이 관리 코드를 실행할 수 없거나 호출을 성공적으로 처리할 수 없는 상태에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="01929-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="01929-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="01929-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="01929-116">호출 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="01929-116">The call timed out.</span></span>|  
|<span data-ttu-id="01929-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="01929-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="01929-118">호출자가 잠금을 소유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="01929-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="01929-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="01929-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="01929-120">차단 된 스레드나 파이버에서 대기 하는 동안 이벤트를 취소 했습니다.</span><span class="sxs-lookup"><span data-stu-id="01929-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="01929-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="01929-121">E_FAIL</span></span>|<span data-ttu-id="01929-122">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="01929-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="01929-123">메서드가 E_FAIL을 반환한 후에는 프로세스 내에서 CLR을 더 이상 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="01929-123">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="01929-124">호스팅 메서드에 대 한 후속 호출은 HOST_E_CLRNOTAVAILABLE을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="01929-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="01929-125">설명</span><span class="sxs-lookup"><span data-stu-id="01929-125">Remarks</span></span>  
 <span data-ttu-id="01929-126">호스트는에서 설명 하 `EClrEvent`는 두 이벤트 형식 중 하나 또는 둘 다에 대해 콜백을 등록할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="01929-126">The host can register callbacks for either or both of the two event types described by `EClrEvent`.</span></span> <span data-ttu-id="01929-127">호스트는 `ICLROnEventManager` [ICLRControl:: getclrmanager](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-getclrmanager-method.md) 메서드를 호출 하 여 인터페이스를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="01929-127">The host gets the `ICLROnEventManager` interface by calling the [ICLRControl::GetCLRManager](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-getclrmanager-method.md) method.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="01929-128">를 등록 하 `RegisterActionOnEvent` 는 이벤트는 여러 스레드에서 두 번 이상 발생 하 여 언로드 또는 CLR 비활성화를 알릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="01929-128">The events that `RegisterActionOnEvent` registers can be fired more than once and from different threads to signal an unload or the disabling of the CLR.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="01929-129">요구 사항</span><span class="sxs-lookup"><span data-stu-id="01929-129">Requirements</span></span>  
 <span data-ttu-id="01929-130">**플랫폼** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="01929-130">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="01929-131">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="01929-131">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="01929-132">**라이브러리** Mscoree.dll에 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="01929-132">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="01929-133">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="01929-133">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="01929-134">참고자료</span><span class="sxs-lookup"><span data-stu-id="01929-134">See also</span></span>

- [<span data-ttu-id="01929-135">EClrEvent 열거형</span><span class="sxs-lookup"><span data-stu-id="01929-135">EClrEvent Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/eclrevent-enumeration.md)
- [<span data-ttu-id="01929-136">IActionOnCLREvent 인터페이스</span><span class="sxs-lookup"><span data-stu-id="01929-136">IActionOnCLREvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iactiononclrevent-interface.md)
- [<span data-ttu-id="01929-137">ICLRControl 인터페이스</span><span class="sxs-lookup"><span data-stu-id="01929-137">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)
- [<span data-ttu-id="01929-138">ICLROnEventManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="01929-138">ICLROnEventManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclroneventmanager-interface.md)
