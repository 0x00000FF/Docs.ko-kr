---
title: "ICLRTaskManager::GetCurrentTaskType 메서드"
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
- ICLRTaskManager.GetCurrentTaskType
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRTaskManager::GetCurrentTaskType
helpviewer_keywords:
- GetCurrentTaskType method [.NET Framework hosting]
- ICLRTaskManager::GetCurrentTaskType method [.NET Framework hosting]
ms.assetid: 6b0d9259-dbe2-45bb-b34d-990f60c73424
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: d34ec97c04f4e7871b63d8627903c81e244a30dc
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="iclrtaskmanagergetcurrenttasktype-method"></a><span data-ttu-id="2e715-102">ICLRTaskManager::GetCurrentTaskType 메서드</span><span class="sxs-lookup"><span data-stu-id="2e715-102">ICLRTaskManager::GetCurrentTaskType Method</span></span>
<span data-ttu-id="2e715-103">현재 실행 중인 작업의 유형을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="2e715-103">Gets the type of the task that is currently executing.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2e715-104">구문</span><span class="sxs-lookup"><span data-stu-id="2e715-104">Syntax</span></span>  
  
```  
HRESULT GetCurrentTaskType(  
    [out] ETaskType *pTaskType  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="2e715-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="2e715-105">Parameters</span></span>  
 `pTaskType`  
 <span data-ttu-id="2e715-106">[out] 값에 대 한 포인터는 [ETaskType](../../../../docs/framework/unmanaged-api/hosting/etasktype-enumeration.md) 현재 실행 중인 작업의 유형을 나타내는 열거형입니다.</span><span class="sxs-lookup"><span data-stu-id="2e715-106">[out] A pointer to a value of the [ETaskType](../../../../docs/framework/unmanaged-api/hosting/etasktype-enumeration.md) enumeration that indicates the type of task that is currently executing.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2e715-107">요구 사항</span><span class="sxs-lookup"><span data-stu-id="2e715-107">Requirements</span></span>  
 <span data-ttu-id="2e715-108">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="2e715-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2e715-109">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="2e715-109">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="2e715-110">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="2e715-110">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="2e715-111">**.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2e715-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2e715-112">참고 항목</span><span class="sxs-lookup"><span data-stu-id="2e715-112">See Also</span></span>  
 [<span data-ttu-id="2e715-113">ICLRTaskManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="2e715-113">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
