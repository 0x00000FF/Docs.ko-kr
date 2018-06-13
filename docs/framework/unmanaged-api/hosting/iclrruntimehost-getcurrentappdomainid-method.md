---
title: ICLRRuntimeHost::GetCurrentAppDomainId 메서드
ms.date: 03/30/2017
api_name:
- ICLRRuntimeHost.GetCurrentAppDomainId
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRRuntimeHost::GetCurrentAppDomainId
helpviewer_keywords:
- ICLRRuntimeHost::GetCurrentAppDomainId method [.NET Framework hosting]
- GetCurrentAppDomainId method [.NET Framework hosting]
ms.assetid: 33800475-7815-4976-8aca-a1038761a2ef
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: cbe6ac3c9f03de2224f933a7e44325f578ded48b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33433913"
---
# <a name="iclrruntimehostgetcurrentappdomainid-method"></a><span data-ttu-id="0d99f-102">ICLRRuntimeHost::GetCurrentAppDomainId 메서드</span><span class="sxs-lookup"><span data-stu-id="0d99f-102">ICLRRuntimeHost::GetCurrentAppDomainId Method</span></span>
<span data-ttu-id="0d99f-103">숫자 식별자를 가져옵니다는 <xref:System.AppDomain> 현재 실행 중인 합니다.</span><span class="sxs-lookup"><span data-stu-id="0d99f-103">Gets the numeric identifier of the <xref:System.AppDomain> that is currently executing.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0d99f-104">구문</span><span class="sxs-lookup"><span data-stu-id="0d99f-104">Syntax</span></span>  
  
```  
HRESULT GetCurrentAppDomainId(  
    [out] DWORD* pdwAppDomainId  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="0d99f-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="0d99f-105">Parameters</span></span>  
 `pdwAppDomainId`  
 <span data-ttu-id="0d99f-106">[out] 숫자 식별자는 <xref:System.AppDomain> 현재 실행 중인 합니다.</span><span class="sxs-lookup"><span data-stu-id="0d99f-106">[out] The numeric identifier of the <xref:System.AppDomain> that is currently executing.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="0d99f-107">반환 값</span><span class="sxs-lookup"><span data-stu-id="0d99f-107">Return Value</span></span>  
  
|<span data-ttu-id="0d99f-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="0d99f-108">HRESULT</span></span>|<span data-ttu-id="0d99f-109">설명</span><span class="sxs-lookup"><span data-stu-id="0d99f-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="0d99f-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="0d99f-110">S_OK</span></span>|<span data-ttu-id="0d99f-111">`GetCurrentAppDomainId` 성공적으로 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="0d99f-111">`GetCurrentAppDomainId` returned successfully.</span></span>|  
|<span data-ttu-id="0d99f-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="0d99f-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="0d99f-113">공용 언어 런타임 (CLR) 프로세스에 로드 되지 않았습니다 또는 CLR 중인 상태를 관리 코드를 실행 하거나 호출을 처리할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="0d99f-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="0d99f-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="0d99f-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="0d99f-115">호출 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="0d99f-115">The call timed out.</span></span>|  
|<span data-ttu-id="0d99f-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="0d99f-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="0d99f-117">호출자에 게 잠금을 소유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0d99f-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="0d99f-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="0d99f-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="0d99f-119">차단 된 스레드 이벤트 취소 되었습니다 또는 파이버가 기다리던 합니다.</span><span class="sxs-lookup"><span data-stu-id="0d99f-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="0d99f-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="0d99f-120">E_FAIL</span></span>|<span data-ttu-id="0d99f-121">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="0d99f-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="0d99f-122">메서드가 E_FAIL을 반환 하는 경우 CLR을 하는 프로세스 내에서 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="0d99f-122">If a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="0d99f-123">호스팅 방법에 대 한 후속 호출 HOST_E_CLRNOTAVAILABLE를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="0d99f-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0d99f-124">설명</span><span class="sxs-lookup"><span data-stu-id="0d99f-124">Remarks</span></span>  
 <span data-ttu-id="0d99f-125">`pdwAppDomainId` 매개 변수가 값으로 설정 되는 <xref:System.AppDomain.Id%2A> 속성의는 <xref:System.AppDomain> 현재 스레드가 실행 중인에 합니다.</span><span class="sxs-lookup"><span data-stu-id="0d99f-125">The `pdwAppDomainId` parameter is set to the value of the <xref:System.AppDomain.Id%2A> property of the <xref:System.AppDomain> in which the current thread is executing.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0d99f-126">요구 사항</span><span class="sxs-lookup"><span data-stu-id="0d99f-126">Requirements</span></span>  
 <span data-ttu-id="0d99f-127">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="0d99f-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0d99f-128">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="0d99f-128">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="0d99f-129">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="0d99f-129">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="0d99f-130">**.NET framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0d99f-130">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0d99f-131">참고 항목</span><span class="sxs-lookup"><span data-stu-id="0d99f-131">See Also</span></span>  
 <xref:System.AppDomain>  
 <xref:System.AppDomainManager>  
 [<span data-ttu-id="0d99f-132">ICLRRuntimeHost 인터페이스</span><span class="sxs-lookup"><span data-stu-id="0d99f-132">ICLRRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md)
