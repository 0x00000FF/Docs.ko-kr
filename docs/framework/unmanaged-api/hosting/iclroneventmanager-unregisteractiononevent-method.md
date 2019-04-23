---
title: ICLROnEventManager::UnregisterActionOnEvent 메서드
ms.date: 03/30/2017
api_name:
- ICLROnEventManager.UnregisterActionOnEvent
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLROnEventManager::UnregisterActionOnEvent
helpviewer_keywords:
- UnRegisterActionOnEvent method [.NET Framework hosting]
- ICLROnEventManager::UnRegisterActionOnEvent method [.NET Framework hosting]
ms.assetid: 4c02ec37-cdf0-46b2-890e-235092741236
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 54abd54662d4e99881dddf15876b596a4a705f70
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59108903"
---
# <a name="iclroneventmanagerunregisteractiononevent-method"></a><span data-ttu-id="0c76c-102">ICLROnEventManager::UnregisterActionOnEvent 메서드</span><span class="sxs-lookup"><span data-stu-id="0c76c-102">ICLROnEventManager::UnregisterActionOnEvent Method</span></span>
<span data-ttu-id="0c76c-103">지정된 된 이벤트에 대 한 이전에 등록 된 콜백 포인터를 등록 취소합니다.</span><span class="sxs-lookup"><span data-stu-id="0c76c-103">Unregisters a previously registered callback pointer for the specified event.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0c76c-104">구문</span><span class="sxs-lookup"><span data-stu-id="0c76c-104">Syntax</span></span>  
  
```  
HRESULT UnregisterActionOnEvent (  
    [in] EClrEvent event,  
    [in] IActionOnCLREvent *pAction  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0c76c-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="0c76c-105">Parameters</span></span>  
 `event`  
 <span data-ttu-id="0c76c-106">[in] 중 하나는 [EClrEvent](../../../../docs/framework/unmanaged-api/hosting/eclrevent-enumeration.md) 에 설명 된 콜백 포인터를 등록 취소 하려는 이벤트를 나타내는 값을 `pAction`입니다.</span><span class="sxs-lookup"><span data-stu-id="0c76c-106">[in] One of the [EClrEvent](../../../../docs/framework/unmanaged-api/hosting/eclrevent-enumeration.md) values, indicating the event for which to unregister the callback pointer described by `pAction`.</span></span>  
  
 `pAction`  
 <span data-ttu-id="0c76c-107">[in] 에 대 한 포인터를 [IActionOnCLREvent](../../../../docs/framework/unmanaged-api/hosting/iactiononclrevent-interface.md) 매개 변수로 전달 된 개체를 [RegisterActionOnEvent](../../../../docs/framework/unmanaged-api/hosting/iclroneventmanager-registeractiononevent-method.md) 메서드.</span><span class="sxs-lookup"><span data-stu-id="0c76c-107">[in] A pointer to an [IActionOnCLREvent](../../../../docs/framework/unmanaged-api/hosting/iactiononclrevent-interface.md) object that was passed as a parameter to the [RegisterActionOnEvent](../../../../docs/framework/unmanaged-api/hosting/iclroneventmanager-registeractiononevent-method.md) method.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="0c76c-108">반환 값</span><span class="sxs-lookup"><span data-stu-id="0c76c-108">Return Value</span></span>  
  
|<span data-ttu-id="0c76c-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="0c76c-109">HRESULT</span></span>|<span data-ttu-id="0c76c-110">설명</span><span class="sxs-lookup"><span data-stu-id="0c76c-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="0c76c-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="0c76c-111">S_OK</span></span>|<span data-ttu-id="0c76c-112">`UnregisterActionOnEvent` 성공적으로 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="0c76c-112">`UnregisterActionOnEvent` returned successfully.</span></span>|  
|<span data-ttu-id="0c76c-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="0c76c-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="0c76c-114">프로세스에는 CLR (공용 언어 런타임)에 로드 되지 또는 CLR 상태인는 관리 코드를 실행 하거나 호출을 처리할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="0c76c-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="0c76c-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="0c76c-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="0c76c-116">호출 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="0c76c-116">The call timed out.</span></span>|  
|<span data-ttu-id="0c76c-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="0c76c-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="0c76c-118">호출자가 잠금을 소유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0c76c-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="0c76c-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="0c76c-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="0c76c-120">이벤트가 차단 된 스레드가 취소 된 또는 파이버를 대기 하 고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0c76c-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="0c76c-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="0c76c-121">E_FAIL</span></span>|<span data-ttu-id="0c76c-122">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="0c76c-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="0c76c-123">E_FAIL을 반환 하는 메서드를 CLR 더 이상 프로세스 내에서 사용 가능 합니다.</span><span class="sxs-lookup"><span data-stu-id="0c76c-123">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="0c76c-124">메서드를 호스트 하는 데 대 한 후속 호출 HOST_E_CLRNOTAVAILABLE를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="0c76c-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="0c76c-125">요구 사항</span><span class="sxs-lookup"><span data-stu-id="0c76c-125">Requirements</span></span>  
 <span data-ttu-id="0c76c-126">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="0c76c-126">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0c76c-127">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="0c76c-127">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="0c76c-128">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="0c76c-128">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="0c76c-129">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0c76c-129">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0c76c-130">참고자료</span><span class="sxs-lookup"><span data-stu-id="0c76c-130">See also</span></span>

- [<span data-ttu-id="0c76c-131">EClrEvent 열거형</span><span class="sxs-lookup"><span data-stu-id="0c76c-131">EClrEvent Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/eclrevent-enumeration.md)
- [<span data-ttu-id="0c76c-132">IActionOnCLREvent 인터페이스</span><span class="sxs-lookup"><span data-stu-id="0c76c-132">IActionOnCLREvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iactiononclrevent-interface.md)
- [<span data-ttu-id="0c76c-133">ICLRControl 인터페이스</span><span class="sxs-lookup"><span data-stu-id="0c76c-133">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)
- [<span data-ttu-id="0c76c-134">ICLROnEventManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="0c76c-134">ICLROnEventManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclroneventmanager-interface.md)
