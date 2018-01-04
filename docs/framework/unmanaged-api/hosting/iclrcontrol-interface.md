---
title: "ICLRControl 인터페이스"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRControl
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRControl
helpviewer_keywords: ICLRControl interface [.NET Framework hosting]
ms.assetid: a24fd905-1fa6-45a0-ad65-e9e2ee58861e
topic_type: apiref
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: b93d87107e1a69b0a047dbf156124fe49cd95d16
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="iclrcontrol-interface"></a><span data-ttu-id="80739-102">ICLRControl 인터페이스</span><span class="sxs-lookup"><span data-stu-id="80739-102">ICLRControl Interface</span></span>
<span data-ttu-id="80739-103">참조 하는 데 사용 하 고 공용 언어 런타임 (CLR)의 다양 한 측면을 구성 하는 메서드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="80739-103">Provides methods that allow a host to get references to, and configure aspects of, the common language runtime (CLR).</span></span>  
  
## <a name="methods"></a><span data-ttu-id="80739-104">메서드</span><span class="sxs-lookup"><span data-stu-id="80739-104">Methods</span></span>  
  
|<span data-ttu-id="80739-105">메서드</span><span class="sxs-lookup"><span data-stu-id="80739-105">Method</span></span>|<span data-ttu-id="80739-106">설명</span><span class="sxs-lookup"><span data-stu-id="80739-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="80739-107">GetCLRManager 메서드</span><span class="sxs-lookup"><span data-stu-id="80739-107">GetCLRManager Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-getclrmanager-method.md)|<span data-ttu-id="80739-108">CLR을 구성 하는 호스트 צ ְ ײ 관리자 형식의 모든 인스턴스에 대 한 인터페이스 포인터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="80739-108">Gets an interface pointer to an instance of any of the manager types the host can use to configure the CLR.</span></span>|  
|[<span data-ttu-id="80739-109">SetAppDomainManagerType 메서드</span><span class="sxs-lookup"><span data-stu-id="80739-109">SetAppDomainManagerType Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-setappdomainmanagertype-method.md)|<span data-ttu-id="80739-110">파생 된 형식을 설정 <xref:System.AppDomainManager> 응용 프로그램 도메인 관리자에 대 한 형식으로.</span><span class="sxs-lookup"><span data-stu-id="80739-110">Sets a type derived from <xref:System.AppDomainManager> as the type for application domain managers.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="80739-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="80739-111">Requirements</span></span>  
 <span data-ttu-id="80739-112">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="80739-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="80739-113">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="80739-113">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="80739-114">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="80739-114">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="80739-115">**.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="80739-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="80739-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="80739-116">See Also</span></span>  
 [<span data-ttu-id="80739-117">ICLRAssemblyIdentityManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="80739-117">ICLRAssemblyIdentityManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-interface.md)  
 [<span data-ttu-id="80739-118">ICLRDebugManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="80739-118">ICLRDebugManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-interface.md)  
 [<span data-ttu-id="80739-119">ICLRGCManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="80739-119">ICLRGCManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager-interface.md)  
 [<span data-ttu-id="80739-120">ICLRHostBindingPolicyManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="80739-120">ICLRHostBindingPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrhostbindingpolicymanager-interface.md)  
 [<span data-ttu-id="80739-121">ICLRHostProtectionManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="80739-121">ICLRHostProtectionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrhostprotectionmanager-interface.md)  
 [<span data-ttu-id="80739-122">ICLROnEventManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="80739-122">ICLROnEventManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclroneventmanager-interface.md)  
 [<span data-ttu-id="80739-123">ICLRPolicyManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="80739-123">ICLRPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-interface.md)  
 [<span data-ttu-id="80739-124">IHostControl 인터페이스</span><span class="sxs-lookup"><span data-stu-id="80739-124">IHostControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-interface.md)  
 [<span data-ttu-id="80739-125">호스팅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="80739-125">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
