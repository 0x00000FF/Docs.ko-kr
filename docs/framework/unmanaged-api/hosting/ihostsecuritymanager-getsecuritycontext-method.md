---
title: IHostSecurityManager::GetSecurityContext 메서드
ms.date: 03/30/2017
api_name:
- IHostSecurityManager.GetSecurityContext
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostSecurityManager::GetSecurityContext
helpviewer_keywords:
- GetSecurityContext method [.NET Framework hosting]
- IHostSecurityManager::GetSecurityContext method [.NET Framework hosting]
ms.assetid: 958970d6-f6a2-4b84-b32a-f555cbaf8f61
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e11b447ebd03746730a86dbbcda31edd4196f13b
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54644952"
---
# <a name="ihostsecuritymanagergetsecuritycontext-method"></a><span data-ttu-id="053ba-102">IHostSecurityManager::GetSecurityContext 메서드</span><span class="sxs-lookup"><span data-stu-id="053ba-102">IHostSecurityManager::GetSecurityContext Method</span></span>
<span data-ttu-id="053ba-103">요청 된 가져옵니다 [IHostSecurityContext](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritycontext-interface.md) 호스트에서 합니다.</span><span class="sxs-lookup"><span data-stu-id="053ba-103">Gets the requested [IHostSecurityContext](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritycontext-interface.md) from the host.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="053ba-104">구문</span><span class="sxs-lookup"><span data-stu-id="053ba-104">Syntax</span></span>  
  
```  
HRESULT GetSecurityContext (  
    [in]  EContextType eContextType,   
    [out] IHostSecurityContext** ppSecurityContext  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="053ba-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="053ba-105">Parameters</span></span>  
 `eContextType`  
 <span data-ttu-id="053ba-106">[in] 중 하나는 [EContextType](../../../../docs/framework/unmanaged-api/hosting/econtexttype-enumeration.md) 유형을 반환 하는 보안 컨텍스트를 나타내는 값입니다.</span><span class="sxs-lookup"><span data-stu-id="053ba-106">[in] One of the [EContextType](../../../../docs/framework/unmanaged-api/hosting/econtexttype-enumeration.md) values, indicating what type of security context to return.</span></span>  
  
 `ppSecurityContext`  
 <span data-ttu-id="053ba-107">[out] 에 대 한 인터페이스 포인터의 주소를 `IHostSecurityContext` 의 `eContextType`합니다.</span><span class="sxs-lookup"><span data-stu-id="053ba-107">[out] The address of an interface pointer to the `IHostSecurityContext` of `eContextType`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="053ba-108">반환 값</span><span class="sxs-lookup"><span data-stu-id="053ba-108">Return Value</span></span>  
  
|<span data-ttu-id="053ba-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="053ba-109">HRESULT</span></span>|<span data-ttu-id="053ba-110">설명</span><span class="sxs-lookup"><span data-stu-id="053ba-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="053ba-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="053ba-111">S_OK</span></span>|<span data-ttu-id="053ba-112">`GetSecurityContext` 성공적으로 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="053ba-112">`GetSecurityContext` returned successfully.</span></span>|  
|<span data-ttu-id="053ba-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="053ba-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="053ba-114">프로세스에는 CLR (공용 언어 런타임)에 로드 되지 또는 CLR 상태인는 관리 코드를 실행 하거나 호출을 처리할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="053ba-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="053ba-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="053ba-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="053ba-116">호출 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="053ba-116">The call timed out.</span></span>|  
|<span data-ttu-id="053ba-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="053ba-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="053ba-118">호출자가 잠금을 소유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="053ba-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="053ba-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="053ba-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="053ba-120">이벤트가 차단 된 스레드가 취소 된 또는 파이버를 대기 하 고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="053ba-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="053ba-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="053ba-121">E_FAIL</span></span>|<span data-ttu-id="053ba-122">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="053ba-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="053ba-123">메서드 E_FAIL을 반환 하는 경우 CLR은 프로세스 내에서 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="053ba-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="053ba-124">메서드를 호스트 하는 데 대 한 후속 호출 HOST_E_CLRNOTAVAILABLE를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="053ba-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="053ba-125">설명</span><span class="sxs-lookup"><span data-stu-id="053ba-125">Remarks</span></span>  
 <span data-ttu-id="053ba-126">호스트는 CLR과 사용자 코드에서 스레드 토큰에 대 한 모든 코드 액세스를 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="053ba-126">A host can control all code access to thread tokens by both the CLR and user code.</span></span> <span data-ttu-id="053ba-127">전체 보안을 보장할 수도 있습니다 비동기 작업이 나 제한 된 코드 액세스를 사용 하 여 코드 포인트 컨텍스트 정보가 전달 됩니다.</span><span class="sxs-lookup"><span data-stu-id="053ba-127">It can also ensure that complete security context information is passed across asynchronous operations or code points with restricted code access.</span></span> <span data-ttu-id="053ba-128">`IHostSecurityContext` CLR에 불투명이 보안 컨텍스트 정보를 캡슐화 합니다.</span><span class="sxs-lookup"><span data-stu-id="053ba-128">`IHostSecurityContext` encapsulates this security context information, which is opaque to the CLR.</span></span> <span data-ttu-id="053ba-129">CLR이이 정보를 캡처하고 스레드 풀 작업자 항목 디스패치, 종료자 실행 및 모듈 및 클래스 생성으로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="053ba-129">The CLR captures this information and moves it across thread pool worker item dispatch, finalizer execution, and module and class construction.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="053ba-130">요구 사항</span><span class="sxs-lookup"><span data-stu-id="053ba-130">Requirements</span></span>  
 <span data-ttu-id="053ba-131">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="053ba-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="053ba-132">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="053ba-132">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="053ba-133">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="053ba-133">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="053ba-134">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="053ba-134">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="053ba-135">참고자료</span><span class="sxs-lookup"><span data-stu-id="053ba-135">See also</span></span>
- [<span data-ttu-id="053ba-136">EContextType 열거형</span><span class="sxs-lookup"><span data-stu-id="053ba-136">EContextType Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/econtexttype-enumeration.md)
- [<span data-ttu-id="053ba-137">IHostSecurityContext 인터페이스</span><span class="sxs-lookup"><span data-stu-id="053ba-137">IHostSecurityContext Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritycontext-interface.md)
- [<span data-ttu-id="053ba-138">IHostSecurityManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="053ba-138">IHostSecurityManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-interface.md)
