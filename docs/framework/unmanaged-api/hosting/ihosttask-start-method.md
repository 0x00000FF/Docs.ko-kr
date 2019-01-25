---
title: IHostTask::Start 메서드
ms.date: 03/30/2017
api_name:
- IHostTask.Start
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostTask::Start
helpviewer_keywords:
- IHostTask::Start method [.NET Framework hosting]
- Start method, IHostTask interface [.NET Framework hosting]
ms.assetid: b18742b0-d8c4-401c-ae89-e6eccdaa81d0
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ec781a4b51b425225339c08ec8fa194da1972462
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54625703"
---
# <a name="ihosttaskstart-method"></a><span data-ttu-id="84902-102">IHostTask::Start 메서드</span><span class="sxs-lookup"><span data-stu-id="84902-102">IHostTask::Start Method</span></span>
<span data-ttu-id="84902-103">호스트 작업 요청 현재 [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md) 인스턴스를 일시 중단 된 활성 상태로 코드를 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="84902-103">Requests that the host move the task represented by the current [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md) instance from a suspended to a live state, in which code can be executed.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="84902-104">구문</span><span class="sxs-lookup"><span data-stu-id="84902-104">Syntax</span></span>  
  
```  
HRESULT Start ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="84902-105">반환 값</span><span class="sxs-lookup"><span data-stu-id="84902-105">Return Value</span></span>  
  
|<span data-ttu-id="84902-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="84902-106">HRESULT</span></span>|<span data-ttu-id="84902-107">설명</span><span class="sxs-lookup"><span data-stu-id="84902-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="84902-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="84902-108">S_OK</span></span>|<span data-ttu-id="84902-109">시작에서 성공적으로 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="84902-109">Start returned successfully.</span></span>|  
|<span data-ttu-id="84902-110">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="84902-110">E_FAIL</span></span>|<span data-ttu-id="84902-111">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="84902-111">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="84902-112">E_FAIL을 반환 하는 메서드는 CLR (공용 언어 런타임) 프로세스 내에서 사용 가능한 나타나지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="84902-112">When a method returns E_FAIL, the common language runtime (CLR) is no longer usable within the process.</span></span> <span data-ttu-id="84902-113">메서드를 호스트 하는 데 대 한 후속 호출 HOST_E_CLRNOTAVAILABLE를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="84902-113">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="84902-114">설명</span><span class="sxs-lookup"><span data-stu-id="84902-114">Remarks</span></span>  
 <span data-ttu-id="84902-115">`Start` 항상 치명적인 오류가 발생 하는 경우에서 S_OK HRESULT 값을 제외 하 고 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="84902-115">`Start` always returns an HRESULT value of S_OK, except in cases where a catastrophic failure has occurred.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="84902-116">요구 사항</span><span class="sxs-lookup"><span data-stu-id="84902-116">Requirements</span></span>  
 <span data-ttu-id="84902-117">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="84902-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="84902-118">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="84902-118">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="84902-119">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="84902-119">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="84902-120">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="84902-120">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="84902-121">참고자료</span><span class="sxs-lookup"><span data-stu-id="84902-121">See also</span></span>
- [<span data-ttu-id="84902-122">ICLRTask 인터페이스</span><span class="sxs-lookup"><span data-stu-id="84902-122">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="84902-123">ICLRTaskManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="84902-123">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="84902-124">IHostTask 인터페이스</span><span class="sxs-lookup"><span data-stu-id="84902-124">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="84902-125">IHostTaskManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="84902-125">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
