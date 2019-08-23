---
title: IHostIoCompletionManager::GetHostOverlappedSize 메서드
ms.date: 03/30/2017
api_name:
- IHostIoCompletionManager.GetHostOverlappedSize
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostIoCompletionManager::GetHostOverlappedSize
helpviewer_keywords:
- IHostIoCompletionManager::GetHostOverlappedSize method [.NET Framework hosting]
- GetHostOverlappedSize method [.NET Framework hosting]
ms.assetid: 2902578b-d5e2-4f8d-a103-0c7b6dceda9e
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c43f906961b9e76d5f0f34ba5a5b2f656f5b1488
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2019
ms.locfileid: "69937510"
---
# <a name="ihostiocompletionmanagergethostoverlappedsize-method"></a><span data-ttu-id="9535d-102">IHostIoCompletionManager::GetHostOverlappedSize 메서드</span><span class="sxs-lookup"><span data-stu-id="9535d-102">IHostIoCompletionManager::GetHostOverlappedSize Method</span></span>
<span data-ttu-id="9535d-103">호스트가 i/o 요청에 추가 하려는 사용자 지정 데이터의 크기를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="9535d-103">Gets the size of any custom data the host intends to append to I/O requests.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9535d-104">구문</span><span class="sxs-lookup"><span data-stu-id="9535d-104">Syntax</span></span>  
  
```cpp  
HRESULT GetHostOverlappedSize (  
    [out] DWORD *pcbSize  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9535d-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="9535d-105">Parameters</span></span>  
 `pcbSize`  
 <span data-ttu-id="9535d-106">제한이 CLR (공용 언어 런타임)에서 Win32 `OVERLAPPED` 개체의 크기와 함께 할당 해야 하는 바이트 수에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="9535d-106">[out] A pointer to the number of bytes that the common language runtime (CLR) should allocate in addition to the size of the Win32 `OVERLAPPED` object.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="9535d-107">반환 값</span><span class="sxs-lookup"><span data-stu-id="9535d-107">Return Value</span></span>  
  
|<span data-ttu-id="9535d-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="9535d-108">HRESULT</span></span>|<span data-ttu-id="9535d-109">설명</span><span class="sxs-lookup"><span data-stu-id="9535d-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="9535d-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="9535d-110">S_OK</span></span>|<span data-ttu-id="9535d-111">`GetHostOverlappedSize`성공적으로 반환 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="9535d-111">`GetHostOverlappedSize` returned successfully.</span></span>|  
|<span data-ttu-id="9535d-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="9535d-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="9535d-113">CLR이 프로세스에 로드 되지 않았거나 CLR이 관리 코드를 실행할 수 없거나 호출을 성공적으로 처리할 수 없는 상태에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9535d-113">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="9535d-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="9535d-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="9535d-115">호출 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="9535d-115">The call timed out.</span></span>|  
|<span data-ttu-id="9535d-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="9535d-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="9535d-117">호출자가 잠금을 소유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9535d-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="9535d-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="9535d-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="9535d-119">차단 된 스레드나 파이버에서 대기 하는 동안 이벤트를 취소 했습니다.</span><span class="sxs-lookup"><span data-stu-id="9535d-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="9535d-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="9535d-120">E_FAIL</span></span>|<span data-ttu-id="9535d-121">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="9535d-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="9535d-122">메서드가 E_FAIL을 반환 하는 경우 프로세스 내에서 더 이상 CLR을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="9535d-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="9535d-123">호스팅 메서드에 대 한 후속 호출은 HOST_E_CLRNOTAVAILABLE을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="9535d-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9535d-124">설명</span><span class="sxs-lookup"><span data-stu-id="9535d-124">Remarks</span></span>  
 <span data-ttu-id="9535d-125">Windows 플랫폼 api에 대 한 모든 비동기 i/o 호출은 파일 포인터 위치 `OVERLAPPED` 와 같은 정보를 제공 하는 Win32 개체를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="9535d-125">All asynchronous I/O calls to Windows Platform APIs take a Win32 `OVERLAPPED` object, which provides information such as the file pointer position.</span></span> <span data-ttu-id="9535d-126">상태를 유지 하기 위해 비동기 i/o 호출을 수행 하는 응용 프로그램은 일반적으로 사용자 지정 데이터를 구조체에 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="9535d-126">To maintain state, applications that make asynchronous I/O calls typically add custom data to the structure.</span></span> <span data-ttu-id="9535d-127">`GetHostOverlappedSize`및 [IHostIoCompletionManager:: InitializeHostOverlapped](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-initializehostoverlapped-method.md) 는 호스트에 이러한 사용자 지정 데이터를 포함할 수 있는 기회를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="9535d-127">`GetHostOverlappedSize` and [IHostIoCompletionManager::InitializeHostOverlapped](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-initializehostoverlapped-method.md) provide an opportunity for the host to include such custom data.</span></span>  
  
 <span data-ttu-id="9535d-128">CLR은 메서드를 `GetHostOverlappedSize` 호출 하 여 호스트가 `OVERLAPPED` 개체에 추가 하려는 사용자 지정 데이터의 크기를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="9535d-128">The CLR calls the `GetHostOverlappedSize` method to determine the size of the custom data that the host intends to append to the `OVERLAPPED` object.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="9535d-129">`GetHostOverlappedSize`는 한 번만 호출 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9535d-129">`GetHostOverlappedSize` is called only once.</span></span> <span data-ttu-id="9535d-130">호스트의 사용자 지정 데이터는 모든 i/o 요청에 대해 동일한 크기 여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9535d-130">The host's custom data must be the same size for every I/O request.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="9535d-131">`OVERLAPPED` 개체 자체의 크기는의 `pcbSize`값에 포함 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9535d-131">The size of the `OVERLAPPED` object itself is not included in the value of `pcbSize`.</span></span>  
  
 <span data-ttu-id="9535d-132">`OVERLAPPED` 구조에 대 한 자세한 내용은 Windows 플랫폼 설명서를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="9535d-132">For more information about the `OVERLAPPED` structure, see the Windows Platform documentation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9535d-133">요구 사항</span><span class="sxs-lookup"><span data-stu-id="9535d-133">Requirements</span></span>  
 <span data-ttu-id="9535d-134">**플랫폼** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="9535d-134">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9535d-135">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="9535d-135">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="9535d-136">**라이브러리** Mscoree.dll에 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9535d-136">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="9535d-137">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9535d-137">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9535d-138">참고자료</span><span class="sxs-lookup"><span data-stu-id="9535d-138">See also</span></span>

- <xref:System.Threading.NativeOverlapped>
- [<span data-ttu-id="9535d-139">ICLRIoCompletionManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="9535d-139">ICLRIoCompletionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-interface.md)
- [<span data-ttu-id="9535d-140">IHostIoCompletionManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="9535d-140">IHostIoCompletionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-interface.md)
