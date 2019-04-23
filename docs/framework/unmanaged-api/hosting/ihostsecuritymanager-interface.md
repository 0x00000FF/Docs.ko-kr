---
title: IHostSecurityManager 인터페이스
ms.date: 03/30/2017
api_name:
- IHostSecurityManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostSecurityManager
helpviewer_keywords:
- IHostSecurityManager interface [.NET Framework hosting]
ms.assetid: c3be2cbd-2d93-438b-9888-9a0251b63c03
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f45379fe8640ef7e7b3917bac8d10ca956d75ffb
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59223760"
---
# <a name="ihostsecuritymanager-interface"></a><span data-ttu-id="d8fbe-102">IHostSecurityManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="d8fbe-102">IHostSecurityManager Interface</span></span>
<span data-ttu-id="d8fbe-103">에 대 한 액세스 및 현재 실행 중인 스레드의 보안 컨텍스트를 제어할 수 있는 방법을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="d8fbe-103">Provides methods that allow access to and control over the security context of the currently executing thread.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="d8fbe-104">메서드</span><span class="sxs-lookup"><span data-stu-id="d8fbe-104">Methods</span></span>  
  
|<span data-ttu-id="d8fbe-105">메서드</span><span class="sxs-lookup"><span data-stu-id="d8fbe-105">Method</span></span>|<span data-ttu-id="d8fbe-106">설명</span><span class="sxs-lookup"><span data-stu-id="d8fbe-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="d8fbe-107">GetSecurityContext 메서드</span><span class="sxs-lookup"><span data-stu-id="d8fbe-107">GetSecurityContext Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-getsecuritycontext-method.md)|<span data-ttu-id="d8fbe-108">요청 된 가져옵니다 [IHostSecurityContext](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritycontext-interface.md) 호스트에서 합니다.</span><span class="sxs-lookup"><span data-stu-id="d8fbe-108">Gets the requested [IHostSecurityContext](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritycontext-interface.md) from the host.</span></span>|  
|[<span data-ttu-id="d8fbe-109">ImpersonateLoggedOnUser 메서드</span><span class="sxs-lookup"><span data-stu-id="d8fbe-109">ImpersonateLoggedOnUser Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-impersonateloggedonuser-method.md)|<span data-ttu-id="d8fbe-110">요청 된 현재 사용자 id의 자격 증명을 사용 하 여 코드를 실행 하는 합니다.</span><span class="sxs-lookup"><span data-stu-id="d8fbe-110">Requests that code be executed using the credentials of the current user identity.</span></span>|  
|[<span data-ttu-id="d8fbe-111">OpenThreadToken 메서드</span><span class="sxs-lookup"><span data-stu-id="d8fbe-111">OpenThreadToken Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-openthreadtoken-method.md)|<span data-ttu-id="d8fbe-112">현재 스레드와 연결 된 임의 액세스 토큰을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="d8fbe-112">Opens the discretionary access token associated with the current thread.</span></span>|  
|[<span data-ttu-id="d8fbe-113">RevertToSelf 메서드</span><span class="sxs-lookup"><span data-stu-id="d8fbe-113">RevertToSelf Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-reverttoself-method.md)|<span data-ttu-id="d8fbe-114">현재 사용자 id의 가장을 종료 하 고 원래 스레드 토큰을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="d8fbe-114">Terminates impersonation of the current user identity and returns the original thread token.</span></span>|  
|[<span data-ttu-id="d8fbe-115">SetSecurityContext 메서드</span><span class="sxs-lookup"><span data-stu-id="d8fbe-115">SetSecurityContext Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-setsecuritycontext-method.md)|<span data-ttu-id="d8fbe-116">현재 실행 중인 스레드에 대 한 보안 컨텍스트를 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="d8fbe-116">Sets the security context for the currently executing thread.</span></span>|  
|[<span data-ttu-id="d8fbe-117">SetThreadToken 메서드</span><span class="sxs-lookup"><span data-stu-id="d8fbe-117">SetThreadToken Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-setthreadtoken-method.md)|<span data-ttu-id="d8fbe-118">현재 실행 중인 스레드에 대 한 핸들을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="d8fbe-118">Sets a handle for the currently executing thread.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d8fbe-119">설명</span><span class="sxs-lookup"><span data-stu-id="d8fbe-119">Remarks</span></span>  
 <span data-ttu-id="d8fbe-120">호스트는 CLR (공용 언어 런타임)와 사용자 코드에서 스레드 토큰에 대 한 모든 코드 액세스를 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d8fbe-120">A host can control all code access to thread tokens by both the common language runtime (CLR) and user code.</span></span> <span data-ttu-id="d8fbe-121">전체 보안을 보장할 수도 있습니다 비동기 작업이 나 제한 된 코드 액세스를 사용 하 여 코드 포인트 컨텍스트 정보가 전달 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d8fbe-121">It can also ensure that complete security context information is passed across asynchronous operations or code points with restricted code access.</span></span> <span data-ttu-id="d8fbe-122">`IHostSecurityContext` CLR에 불투명이 보안 컨텍스트 정보를 캡슐화 합니다.</span><span class="sxs-lookup"><span data-stu-id="d8fbe-122">`IHostSecurityContext` encapsulates this security context information, which is opaque to the CLR.</span></span>  
  
 <span data-ttu-id="d8fbe-123">CLR 관리 되는 스레드 컨텍스트를 내부적으로 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="d8fbe-123">The CLR handles managed thread context internally.</span></span> <span data-ttu-id="d8fbe-124">프로세스 관련 쿼리 `IHostSecurityManager` 다음과 같은 경우에서:</span><span class="sxs-lookup"><span data-stu-id="d8fbe-124">It queries the process-specific `IHostSecurityManager` in the following situations:</span></span>  
  
-   <span data-ttu-id="d8fbe-125">종료자 스레드 종료 자가 실행 중입니다.</span><span class="sxs-lookup"><span data-stu-id="d8fbe-125">On the finalizer thread, during finalizer execution.</span></span>  
  
-   <span data-ttu-id="d8fbe-126">클래스 및 모듈 생성자 실행 중</span><span class="sxs-lookup"><span data-stu-id="d8fbe-126">During class and module constructor execution.</span></span>  
  
-   <span data-ttu-id="d8fbe-127">작업자 스레드에 대 한 호출에 비동기 지점에는 [ihostthreadpoolmanager:: Queueuserworkitem](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-queueuserworkitem-method.md) 메서드.</span><span class="sxs-lookup"><span data-stu-id="d8fbe-127">At asynchronous points on the worker thread, in calls to the [IHostThreadPoolManager::QueueUserWorkItem](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-queueuserworkitem-method.md) method.</span></span>  
  
-   <span data-ttu-id="d8fbe-128">I/O 완료 포트의 서비스입니다.</span><span class="sxs-lookup"><span data-stu-id="d8fbe-128">In servicing of I/O completion ports.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d8fbe-129">요구 사항</span><span class="sxs-lookup"><span data-stu-id="d8fbe-129">Requirements</span></span>  
 <span data-ttu-id="d8fbe-130">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="d8fbe-130">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d8fbe-131">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="d8fbe-131">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="d8fbe-132">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="d8fbe-132">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="d8fbe-133">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d8fbe-133">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d8fbe-134">참고자료</span><span class="sxs-lookup"><span data-stu-id="d8fbe-134">See also</span></span>

- [<span data-ttu-id="d8fbe-135">IHostSecurityContext 인터페이스</span><span class="sxs-lookup"><span data-stu-id="d8fbe-135">IHostSecurityContext Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritycontext-interface.md)
- [<span data-ttu-id="d8fbe-136">호스팅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="d8fbe-136">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
