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
ms.openlocfilehash: 28d1655bdc3746dab87acef2e2aac6758883e74a
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59096214"
---
# <a name="iclrruntimehostgetcurrentappdomainid-method"></a><span data-ttu-id="673c8-102">ICLRRuntimeHost::GetCurrentAppDomainId 메서드</span><span class="sxs-lookup"><span data-stu-id="673c8-102">ICLRRuntimeHost::GetCurrentAppDomainId Method</span></span>
<span data-ttu-id="673c8-103">숫자 식별자를 가져옵니다는 <xref:System.AppDomain> 현재 실행 되는 합니다.</span><span class="sxs-lookup"><span data-stu-id="673c8-103">Gets the numeric identifier of the <xref:System.AppDomain> that is currently executing.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="673c8-104">구문</span><span class="sxs-lookup"><span data-stu-id="673c8-104">Syntax</span></span>  
  
```  
HRESULT GetCurrentAppDomainId(  
    [out] DWORD* pdwAppDomainId  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="673c8-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="673c8-105">Parameters</span></span>  
 `pdwAppDomainId`  
 <span data-ttu-id="673c8-106">[out] 숫자 식별자를 <xref:System.AppDomain> 현재 실행 되는 합니다.</span><span class="sxs-lookup"><span data-stu-id="673c8-106">[out] The numeric identifier of the <xref:System.AppDomain> that is currently executing.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="673c8-107">반환 값</span><span class="sxs-lookup"><span data-stu-id="673c8-107">Return Value</span></span>  
  
|<span data-ttu-id="673c8-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="673c8-108">HRESULT</span></span>|<span data-ttu-id="673c8-109">설명</span><span class="sxs-lookup"><span data-stu-id="673c8-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="673c8-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="673c8-110">S_OK</span></span>|`GetCurrentAppDomainId` <span data-ttu-id="673c8-111">성공적으로 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="673c8-111">returned successfully.</span></span>|  
|<span data-ttu-id="673c8-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="673c8-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="673c8-113">프로세스에는 CLR (공용 언어 런타임)에 로드 되지 또는 CLR 상태인는 관리 코드를 실행 하거나 호출을 처리할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="673c8-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="673c8-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="673c8-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="673c8-115">호출 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="673c8-115">The call timed out.</span></span>|  
|<span data-ttu-id="673c8-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="673c8-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="673c8-117">호출자가 잠금을 소유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="673c8-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="673c8-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="673c8-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="673c8-119">이벤트가 차단 된 스레드가 취소 된 또는 파이버를 대기 하 고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="673c8-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="673c8-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="673c8-120">E_FAIL</span></span>|<span data-ttu-id="673c8-121">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="673c8-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="673c8-122">메서드가 E_FAIL을 반환 하는 경우 CLR은 프로세스 내에서 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="673c8-122">If a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="673c8-123">메서드를 호스트 하는 데 대 한 후속 호출 HOST_E_CLRNOTAVAILABLE를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="673c8-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="673c8-124">설명</span><span class="sxs-lookup"><span data-stu-id="673c8-124">Remarks</span></span>  
 <span data-ttu-id="673c8-125">`pdwAppDomainId` 매개 변수 값으로 설정 합니다 <xref:System.AppDomain.Id%2A> 의 속성은 <xref:System.AppDomain> 현재 스레드에서 실행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="673c8-125">The `pdwAppDomainId` parameter is set to the value of the <xref:System.AppDomain.Id%2A> property of the <xref:System.AppDomain> in which the current thread is executing.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="673c8-126">요구 사항</span><span class="sxs-lookup"><span data-stu-id="673c8-126">Requirements</span></span>  
 <span data-ttu-id="673c8-127">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="673c8-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="673c8-128">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="673c8-128">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="673c8-129">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="673c8-129">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="673c8-130">.NET Framework 버전:</span><span class="sxs-lookup"><span data-stu-id="673c8-130">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="673c8-131">참고자료</span><span class="sxs-lookup"><span data-stu-id="673c8-131">See also</span></span>

- <xref:System.AppDomain>
- <xref:System.AppDomainManager>
- [<span data-ttu-id="673c8-132">ICLRRuntimeHost 인터페이스</span><span class="sxs-lookup"><span data-stu-id="673c8-132">ICLRRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md)
