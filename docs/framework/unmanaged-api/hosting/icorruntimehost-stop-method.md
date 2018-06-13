---
title: ICorRuntimeHost::Stop 메서드
ms.date: 03/30/2017
api_name:
- ICorRuntimeHost.Stop
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICorRuntimeHost::Stop
helpviewer_keywords:
- Stop method, ICorRuntimeHost interface [.NET Framework hosting]
- ICorRuntimeHost::Stop method [.NET Framework hosting]
ms.assetid: 46a0d450-b516-4bef-8b71-8d3bf265cbed
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 1aea8cb4c180477fdd763a8af2f251db2d37d066
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33436639"
---
# <a name="icorruntimehoststop-method"></a><span data-ttu-id="fbe78-102">ICorRuntimeHost::Stop 메서드</span><span class="sxs-lookup"><span data-stu-id="fbe78-102">ICorRuntimeHost::Stop Method</span></span>
<span data-ttu-id="fbe78-103">현재 프로세스에 대해 런타임에서 코드의 실행을 중지합니다.</span><span class="sxs-lookup"><span data-stu-id="fbe78-103">Stops the execution of code in the runtime for the current process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fbe78-104">구문</span><span class="sxs-lookup"><span data-stu-id="fbe78-104">Syntax</span></span>  
  
```  
HRESULT Stop ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="fbe78-105">반환 값</span><span class="sxs-lookup"><span data-stu-id="fbe78-105">Return Value</span></span>  
  
|<span data-ttu-id="fbe78-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="fbe78-106">HRESULT</span></span>|<span data-ttu-id="fbe78-107">설명</span><span class="sxs-lookup"><span data-stu-id="fbe78-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="fbe78-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="fbe78-108">S_OK</span></span>|<span data-ttu-id="fbe78-109">작업이 성공 했습니다.</span><span class="sxs-lookup"><span data-stu-id="fbe78-109">The operation was successful.</span></span>|  
|<span data-ttu-id="fbe78-110">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="fbe78-110">S_FALSE</span></span>|<span data-ttu-id="fbe78-111">작업을 완료 하지 못했습니다.</span><span class="sxs-lookup"><span data-stu-id="fbe78-111">The operation failed to complete.</span></span>|  
|<span data-ttu-id="fbe78-112">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="fbe78-112">E_FAIL</span></span>|<span data-ttu-id="fbe78-113">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="fbe78-113">An unknown, catastrophic failure occurred.</span></span> <span data-ttu-id="fbe78-114">메서드가 E_FAIL을 반환 하는 경우 공용 언어 런타임 (CLR)을 하는 프로세스에서 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="fbe78-114">If a method returns E_FAIL, the common language runtime (CLR) is no longer usable in the process.</span></span> <span data-ttu-id="fbe78-115">호스팅 Api에 대 한 후속 호출 HOST_E_CLRNOTAVAILABLE를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="fbe78-115">Subsequent calls to any hosting APIs return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="fbe78-116">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="fbe78-116">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="fbe78-117">CLR은 프로세스에 로드 되지 않았습니다 또는 CLR 중인 상태를 관리 코드를 실행 하거나 호출을 처리할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="fbe78-117">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="fbe78-118">설명</span><span class="sxs-lookup"><span data-stu-id="fbe78-118">Remarks</span></span>  
 <span data-ttu-id="fbe78-119">일반적으로 호출할 필요가 없다는 `Stop` 메서드를 코드는 프로세스가 종료 될 때 실행이 중지 하기 때문에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fbe78-119">It is typically unnecessary to call the `Stop` method, because the code stops executing when the process exits.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="fbe78-120">호출한 후 `Stop`, 동일한 프로세스에 CLR을 다시 초기화할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="fbe78-120">After a call to `Stop`, the CLR cannot be reinitialized into the same process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fbe78-121">요구 사항</span><span class="sxs-lookup"><span data-stu-id="fbe78-121">Requirements</span></span>  
 <span data-ttu-id="fbe78-122">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="fbe78-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fbe78-123">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="fbe78-123">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="fbe78-124">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="fbe78-124">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="fbe78-125">**.NET framework 버전:** 1.0, 1.1</span><span class="sxs-lookup"><span data-stu-id="fbe78-125">**.NET Framework Versions:** 1.0, 1.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fbe78-126">참고 항목</span><span class="sxs-lookup"><span data-stu-id="fbe78-126">See Also</span></span>  
 [<span data-ttu-id="fbe78-127">ICorRuntimeHost 인터페이스</span><span class="sxs-lookup"><span data-stu-id="fbe78-127">ICorRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)
