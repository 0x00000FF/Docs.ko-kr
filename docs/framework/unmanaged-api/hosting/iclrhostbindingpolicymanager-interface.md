---
title: ICLRHostBindingPolicyManager 인터페이스
ms.date: 03/30/2017
api_name:
- ICLRHostBindingPolicyManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRHostBindingPolicyManager
helpviewer_keywords:
- ICLRHostBindingPolicyManager interface [.NET Framework hosting]
ms.assetid: f9da168b-366b-4b2b-bdb9-330b6bad5a6b
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 637803c509935fdff080802f66f9f73ab8cf25e0
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33431990"
---
# <a name="iclrhostbindingpolicymanager-interface"></a><span data-ttu-id="ffbe5-102">ICLRHostBindingPolicyManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="ffbe5-102">ICLRHostBindingPolicyManager Interface</span></span>
<span data-ttu-id="ffbe5-103">현재 바인딩 정책을 평가 하 고 지정된 된 어셈블리에 대 한 정책 변경 내용을 통신 하기 위해 호스트에 대 한 메서드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="ffbe5-103">Provides methods for the host to evaluate current binding policy and communicate policy changes for a specified assembly.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="ffbe5-104">메서드</span><span class="sxs-lookup"><span data-stu-id="ffbe5-104">Methods</span></span>  
  
|<span data-ttu-id="ffbe5-105">메서드</span><span class="sxs-lookup"><span data-stu-id="ffbe5-105">Method</span></span>|<span data-ttu-id="ffbe5-106">설명</span><span class="sxs-lookup"><span data-stu-id="ffbe5-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="ffbe5-107">EvaluatePolicy 메서드</span><span class="sxs-lookup"><span data-stu-id="ffbe5-107">EvaluatePolicy Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrhostbindingpolicymanager-evaluatepolicy-method.md)|<span data-ttu-id="ffbe5-108">호스트를 대신 하 여 바인딩 정책을 평가합니다.</span><span class="sxs-lookup"><span data-stu-id="ffbe5-108">Evaluates binding policy on behalf of the host.</span></span>|  
|[<span data-ttu-id="ffbe5-109">ModifyApplicationPolicy 메서드</span><span class="sxs-lookup"><span data-stu-id="ffbe5-109">ModifyApplicationPolicy Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrhostbindingpolicymanager-modifyapplicationpolicy-method.md)|<span data-ttu-id="ffbe5-110">지정된 된 어셈블리에 대 한 바인딩 정책 수정 하 고 정책의 새 버전을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="ffbe5-110">Modifies the binding policy for the specified assembly, and creates a new version of the policy.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="ffbe5-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="ffbe5-111">Requirements</span></span>  
 <span data-ttu-id="ffbe5-112">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="ffbe5-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ffbe5-113">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="ffbe5-113">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="ffbe5-114">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="ffbe5-114">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="ffbe5-115">**.NET framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ffbe5-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ffbe5-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ffbe5-116">See Also</span></span>  
 [<span data-ttu-id="ffbe5-117">ICLRAssemblyIdentityManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="ffbe5-117">ICLRAssemblyIdentityManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-interface.md)  
 [<span data-ttu-id="ffbe5-118">IHostAssemblyStore 인터페이스</span><span class="sxs-lookup"><span data-stu-id="ffbe5-118">IHostAssemblyStore Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-interface.md)  
 [<span data-ttu-id="ffbe5-119">호스팅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="ffbe5-119">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
