---
title: IHostAssemblyManager::GetNonHostStoreAssemblies 메서드
ms.date: 03/30/2017
api_name:
- IHostAssemblyManager.GetNonHostStoreAssemblies
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostAssemblyManager::GetNonHostStoreAssemblies
helpviewer_keywords:
- IHostAssemblyManager::GetNonHostStoreAssemblies method [.NET Framework hosting]
- GetNonHostStoreAssemblies method [.NET Framework hosting]
ms.assetid: d2250b38-c76a-40ce-80c8-ba45149886e8
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b90ddefb082b9017246bf644b79aa63c5d7444b4
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54600182"
---
# <a name="ihostassemblymanagergetnonhoststoreassemblies-method"></a><span data-ttu-id="dfb74-102">IHostAssemblyManager::GetNonHostStoreAssemblies 메서드</span><span class="sxs-lookup"><span data-stu-id="dfb74-102">IHostAssemblyManager::GetNonHostStoreAssemblies Method</span></span>
<span data-ttu-id="dfb74-103">한 인터페이스 포인터를 가져옵니다는 [ICLRAssemblyReferenceList](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md) 호스트에서 예상 하는 CLR (공용 언어 런타임)를 로드 하는 어셈블리의 목록을 나타내는입니다.</span><span class="sxs-lookup"><span data-stu-id="dfb74-103">Gets an interface pointer to an [ICLRAssemblyReferenceList](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md) that represents the list of assemblies that the host expects the common language runtime (CLR) to load.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dfb74-104">구문</span><span class="sxs-lookup"><span data-stu-id="dfb74-104">Syntax</span></span>  
  
```  
HRESULT GetNonHostStoreAssemblies (  
    [out] ICLRAssemblyReferenceList **ppReferenceList  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="dfb74-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="dfb74-105">Parameters</span></span>  
 `ppReferenceList`  
 <span data-ttu-id="dfb74-106">[out] 주소에 대 한 포인터는 `ICLRAssemblyReferenceList` 호스트 로드 하기 위해 CLR에서 예상 하는 어셈블리에 대 한 참조의 목록을 포함 하는 합니다.</span><span class="sxs-lookup"><span data-stu-id="dfb74-106">[out] A pointer to the address of an `ICLRAssemblyReferenceList` that contains a list of references to assemblies that the host expects the CLR to load.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="dfb74-107">반환 값</span><span class="sxs-lookup"><span data-stu-id="dfb74-107">Return Value</span></span>  
  
|<span data-ttu-id="dfb74-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="dfb74-108">HRESULT</span></span>|<span data-ttu-id="dfb74-109">설명</span><span class="sxs-lookup"><span data-stu-id="dfb74-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="dfb74-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="dfb74-110">S_OK</span></span>|<span data-ttu-id="dfb74-111">`GetNonHostStoreAssemblies` 성공적으로 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="dfb74-111">`GetNonHostStoreAssemblies` returned successfully.</span></span>|  
|<span data-ttu-id="dfb74-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="dfb74-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="dfb74-113">CLR이 로드 된 프로세스에 또는 CLR 상태인는 관리 코드를 실행 하거나 호출을 처리할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="dfb74-113">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="dfb74-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="dfb74-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="dfb74-115">호출 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="dfb74-115">The call timed out.</span></span>|  
|<span data-ttu-id="dfb74-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="dfb74-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="dfb74-117">호출자가 잠금을 소유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="dfb74-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="dfb74-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="dfb74-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="dfb74-119">이벤트가 차단 된 스레드가 취소 된 또는 파이버를 대기 하 고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dfb74-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="dfb74-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="dfb74-120">E_FAIL</span></span>|<span data-ttu-id="dfb74-121">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="dfb74-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="dfb74-122">메서드 E_FAIL을 반환 하는 경우 CLR은 프로세스 내에서 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="dfb74-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="dfb74-123">메서드를 호스트 하는 데 대 한 후속 호출 HOST_E_CLRNOTAVAILABLE를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="dfb74-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="dfb74-124">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="dfb74-124">E_OUTOFMEMORY</span></span>|<span data-ttu-id="dfb74-125">요청 된 작업에 대 한 참조 목록을 만드는 데 사용할 수 있는 메모리가 충분 하지 않습니다 `ICLRAssemblyReferenceList`합니다.</span><span class="sxs-lookup"><span data-stu-id="dfb74-125">Not enough memory was available to create the list of references for the requested `ICLRAssemblyReferenceList`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="dfb74-126">설명</span><span class="sxs-lookup"><span data-stu-id="dfb74-126">Remarks</span></span>  
 <span data-ttu-id="dfb74-127">다음 지침을 사용 하 여 참조를 확인 하는 CLR:</span><span class="sxs-lookup"><span data-stu-id="dfb74-127">The CLR resolves references using the following set of guidelines:</span></span>  
  
-   <span data-ttu-id="dfb74-128">반환 하는 어셈블리 참조의 목록을 확인 먼저 `GetNonHostStoreAssemblies`합니다.</span><span class="sxs-lookup"><span data-stu-id="dfb74-128">First, it consults the list of assembly references returned by `GetNonHostStoreAssemblies`.</span></span>  
  
-   <span data-ttu-id="dfb74-129">어셈블리 목록에 있으면 CLR에 정상적으로 바인딩합니다.</span><span class="sxs-lookup"><span data-stu-id="dfb74-129">If the assembly appears in the list, the CLR binds to it normally.</span></span>  
  
-   <span data-ttu-id="dfb74-130">어셈블리 목록에 나타나지 않습니다 하 고 호스트의 구현을 제공 했습니다 [IHostAssemblyStore](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-interface.md), CLR 호출 [ihostassemblystore:: Provideassembly](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-provideassembly-method.md) 호스트가 제공 하는 바인딩할 어셈블리입니다.</span><span class="sxs-lookup"><span data-stu-id="dfb74-130">If the assembly does not appear in the list and the host has provided an implementation of [IHostAssemblyStore](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-interface.md), the CLR calls [IHostAssemblyStore::ProvideAssembly](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-provideassembly-method.md) to allow the host to supply the assembly to bind to.</span></span>  
  
-   <span data-ttu-id="dfb74-131">그렇지 않으면 CLR 어셈블리에 바인딩할 실패 합니다.</span><span class="sxs-lookup"><span data-stu-id="dfb74-131">Otherwise, the CLR fails to bind to the assembly.</span></span>  
  
 <span data-ttu-id="dfb74-132">호스트 설정 하는 경우 `ppReferenceList` null이 고, CLR 첫 번째 프로브를 전역 어셈블리 캐시에는 다음과 같이 호출 됩니다. `ProvideAssembly`, 및 다음 어셈블리 참조를 확인 하는 응용 프로그램 기준 위치를 프로브 합니다.</span><span class="sxs-lookup"><span data-stu-id="dfb74-132">If the host sets `ppReferenceList` to null, the CLR first probes the global assembly cache, calls `ProvideAssembly`, and then probes the application base to resolve an assembly reference.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="dfb74-133">초기화 하면 CLR은 호출 `GetNonHostStoreAssemblies` 한 번만 합니다.</span><span class="sxs-lookup"><span data-stu-id="dfb74-133">Upon initialization, the CLR calls `GetNonHostStoreAssemblies` only once.</span></span> <span data-ttu-id="dfb74-134">메서드를 다시 호출 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="dfb74-134">The method is not called again.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="dfb74-135">요구 사항</span><span class="sxs-lookup"><span data-stu-id="dfb74-135">Requirements</span></span>  
 <span data-ttu-id="dfb74-136">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="dfb74-136">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="dfb74-137">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="dfb74-137">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="dfb74-138">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="dfb74-138">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="dfb74-139">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="dfb74-139">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dfb74-140">참고자료</span><span class="sxs-lookup"><span data-stu-id="dfb74-140">See also</span></span>
- [<span data-ttu-id="dfb74-141">ICLRAssemblyReferenceList 인터페이스</span><span class="sxs-lookup"><span data-stu-id="dfb74-141">ICLRAssemblyReferenceList Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md)
- [<span data-ttu-id="dfb74-142">IHostAssemblyManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="dfb74-142">IHostAssemblyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostassemblymanager-interface.md)
- [<span data-ttu-id="dfb74-143">IHostAssemblyStore 인터페이스</span><span class="sxs-lookup"><span data-stu-id="dfb74-143">IHostAssemblyStore Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-interface.md)
