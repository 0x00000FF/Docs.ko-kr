---
title: "ICLRRuntimeHost::Stop 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- ICLRRuntimeHost.Stop
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRRuntimeHost::Stop
helpviewer_keywords:
- ICLRRuntimeHost::Stop method [.NET Framework hosting]
- Stop method, ICLRRuntimeHost interface [.NET Framework hosting]
ms.assetid: b8fd7daf-8f8d-4ad7-92ae-019db244cec1
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 3cb9eaecdec661ae56727e5fd38c7e9a3b9621d8
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="iclrruntimehoststop-method"></a><span data-ttu-id="0168c-102">ICLRRuntimeHost::Stop 메서드</span><span class="sxs-lookup"><span data-stu-id="0168c-102">ICLRRuntimeHost::Stop Method</span></span>
<span data-ttu-id="0168c-103">공용 언어 런타임 (CLR) 하 여 코드의 실행을 중지 합니다.</span><span class="sxs-lookup"><span data-stu-id="0168c-103">Stops the execution of code by the common language runtime (CLR).</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="0168c-104">이 메서드는 없는 호스트에 리소스를 해제, 응용 프로그램 도메인, 언로드 또는 스레드를 삭제 합니다.</span><span class="sxs-lookup"><span data-stu-id="0168c-104">This method does not release resources to the host, unload application domains, or destroy threads.</span></span> <span data-ttu-id="0168c-105">이러한 리소스를 해제 하는 프로세스를 종료 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0168c-105">You must terminate the process to release these resources.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0168c-106">구문</span><span class="sxs-lookup"><span data-stu-id="0168c-106">Syntax</span></span>  
  
```  
HRESULT Stop();  
```  
  
## <a name="return-value"></a><span data-ttu-id="0168c-107">반환 값</span><span class="sxs-lookup"><span data-stu-id="0168c-107">Return Value</span></span>  
  
|<span data-ttu-id="0168c-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="0168c-108">HRESULT</span></span>|<span data-ttu-id="0168c-109">설명</span><span class="sxs-lookup"><span data-stu-id="0168c-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="0168c-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="0168c-110">S_OK</span></span>|<span data-ttu-id="0168c-111">`Stop`성공적으로 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="0168c-111">`Stop` returned successfully.</span></span>|  
|<span data-ttu-id="0168c-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="0168c-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="0168c-113">CLR은 프로세스에 로드 되지 않았습니다 또는 CLR 중인 상태를 관리 코드를 실행 하거나 호출을 처리할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="0168c-113">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="0168c-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="0168c-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="0168c-115">호출 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="0168c-115">The call timed out.</span></span>|  
|<span data-ttu-id="0168c-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="0168c-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="0168c-117">호출자에 게 잠금을 소유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0168c-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="0168c-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="0168c-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="0168c-119">차단 된 스레드 이벤트 취소 되었습니다 또는 파이버가 기다리던 합니다.</span><span class="sxs-lookup"><span data-stu-id="0168c-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="0168c-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="0168c-120">E_FAIL</span></span>|<span data-ttu-id="0168c-121">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="0168c-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="0168c-122">메서드가 E_FAIL을 반환 하는 경우 CLR을 하는 프로세스 내에서 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="0168c-122">If a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="0168c-123">호스팅 방법에 대 한 후속 호출 HOST_E_CLRNOTAVAILABLE를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="0168c-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="0168c-124">요구 사항</span><span class="sxs-lookup"><span data-stu-id="0168c-124">Requirements</span></span>  
 <span data-ttu-id="0168c-125">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="0168c-125">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0168c-126">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="0168c-126">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="0168c-127">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="0168c-127">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="0168c-128">**.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0168c-128">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0168c-129">참고 항목</span><span class="sxs-lookup"><span data-stu-id="0168c-129">See Also</span></span>  
 [<span data-ttu-id="0168c-130">ICLRRuntimeHost 인터페이스</span><span class="sxs-lookup"><span data-stu-id="0168c-130">ICLRRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md)
