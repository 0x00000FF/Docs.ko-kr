---
title: EContextType 열거형
ms.date: 03/30/2017
api_name:
- EContextType
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- EContextType
helpviewer_keywords:
- EContextType enumeration [.NET Framework hosting]
ms.assetid: 92b926a9-b87e-408a-9036-df7b752c9492
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7a261d9164e8714531eab1fe9fc8148304e6d5bb
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33432884"
---
# <a name="econtexttype-enumeration"></a><span data-ttu-id="9a843-102">EContextType 열거형</span><span class="sxs-lookup"><span data-stu-id="9a843-102">EContextType Enumeration</span></span>
<span data-ttu-id="9a843-103">현재 실행 중인 스레드의 보안 컨텍스트를 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="9a843-103">Describes the security context of the currently executing thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9a843-104">구문</span><span class="sxs-lookup"><span data-stu-id="9a843-104">Syntax</span></span>  
  
```  
typedef enum {  
    eCurrentContext    = 0x00,  
    eRestrictedContext = 0x01  
} EContextType;  
```  
  
## <a name="members"></a><span data-ttu-id="9a843-105">멤버</span><span class="sxs-lookup"><span data-stu-id="9a843-105">Members</span></span>  
  
|<span data-ttu-id="9a843-106">멤버</span><span class="sxs-lookup"><span data-stu-id="9a843-106">Member</span></span>|<span data-ttu-id="9a843-107">설명</span><span class="sxs-lookup"><span data-stu-id="9a843-107">Description</span></span>|  
|------------|-----------------|  
|`eCurrentContext`|<span data-ttu-id="9a843-108">공용 언어 런타임 (CLR)를 호출 시 현재 스레드에서 컨텍스트를 나타내는 [ihostsecuritymanager:: Getsecuritycontext](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-getsecuritycontext-method.md) 메서드나에 대 한 호출에서 CLR에서 요청 컨텍스트는 [ Ihostsecuritymanager:: Setsecuritycontext](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-setsecuritycontext-method.md) 메서드.</span><span class="sxs-lookup"><span data-stu-id="9a843-108">Indicates the context on the current thread at the time the common language runtime (CLR) calls the [IHostSecurityManager::GetSecurityContext](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-getsecuritycontext-method.md) method, or the context requested by the CLR in a call to the [IHostSecurityManager::SetSecurityContext](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-setsecuritycontext-method.md) method.</span></span>|  
|`eRestrictedContext`|<span data-ttu-id="9a843-109">호스트에는 가비지 수집기 또는 클래스나 모듈 생성자와 같이 더 낮은 권한 컨텍스트를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="9a843-109">Indicates a context over which the host has lower privileges, such as the garbage collector, or class or module constructors.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9a843-110">설명</span><span class="sxs-lookup"><span data-stu-id="9a843-110">Remarks</span></span>  
 <span data-ttu-id="9a843-111">CLR 제공 중 하나는 `EContextType` 값에 대 한 호출에 매개 변수 값으로는 `IHostSecurityManager::GetSecurityContext` 및 `IHostSecurityManager::SetSecurityContext` 메서드.</span><span class="sxs-lookup"><span data-stu-id="9a843-111">The CLR supplies one of the `EContextType` values as a parameter value in calls to the `IHostSecurityManager::GetSecurityContext` and `IHostSecurityManager::SetSecurityContext` methods.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9a843-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="9a843-112">Requirements</span></span>  
 <span data-ttu-id="9a843-113">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="9a843-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9a843-114">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="9a843-114">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="9a843-115">**라이브러리:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="9a843-115">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="9a843-116">**.NET framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9a843-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9a843-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="9a843-117">See Also</span></span>  
 [<span data-ttu-id="9a843-118">IHostSecurityContext 인터페이스</span><span class="sxs-lookup"><span data-stu-id="9a843-118">IHostSecurityContext Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritycontext-interface.md)  
 [<span data-ttu-id="9a843-119">IHostSecurityManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="9a843-119">IHostSecurityManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-interface.md)  
 [<span data-ttu-id="9a843-120">호스팅 열거형</span><span class="sxs-lookup"><span data-stu-id="9a843-120">Hosting Enumerations</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
