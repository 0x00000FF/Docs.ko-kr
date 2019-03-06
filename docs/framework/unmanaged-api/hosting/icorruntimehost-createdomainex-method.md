---
title: ICorRuntimeHost::CreateDomainEx 메서드
ms.date: 03/30/2017
api_name:
- ICorRuntimeHost.CreateDomainEx
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICorRuntimeHost::CreateDomainEx
helpviewer_keywords:
- ICorRuntimeHost::CreateDomainEx method [.NET Framework hosting]
- CreateDomainEx method [.NET Framework hosting]
ms.assetid: 1bdde382-f8ba-4cc8-94b2-d1ac919c585e
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 5ed45c3975c58331490f89d8ca705f080d01d74e
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/06/2019
ms.locfileid: "57466806"
---
# <a name="icorruntimehostcreatedomainex-method"></a><span data-ttu-id="ebdd4-102">ICorRuntimeHost::CreateDomainEx 메서드</span><span class="sxs-lookup"><span data-stu-id="ebdd4-102">ICorRuntimeHost::CreateDomainEx Method</span></span>
<span data-ttu-id="ebdd4-103">응용 프로그램 도메인을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="ebdd4-103">Creates an application domain.</span></span> <span data-ttu-id="ebdd4-104">호출자가 형식의 인터페이스 포인터를 받을 <xref:System._AppDomain>, 형식 인스턴스에 <xref:System.AppDomain?displayProperty=nameWithType>합니다.</span><span class="sxs-lookup"><span data-stu-id="ebdd4-104">The caller receives an interface pointer, of type <xref:System._AppDomain>, to an instance of type <xref:System.AppDomain?displayProperty=nameWithType>.</span></span> <span data-ttu-id="ebdd4-105">이 메서드는 호출자가 반환 된 추가 기능을 구성 하려면 IAppDomainSetup 인스턴스를 전달 하도록 허용 <xref:System._AppDomain> 인스턴스.</span><span class="sxs-lookup"><span data-stu-id="ebdd4-105">This method allows the caller to pass an IAppDomainSetup instance to configure additional features of the returned <xref:System._AppDomain> instance.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ebdd4-106">구문</span><span class="sxs-lookup"><span data-stu-id="ebdd4-106">Syntax</span></span>  
  
```  
HRESULT CreateDomainEx (  
    [in] LPCWSTR     pwzFriendlyName,  
    [in] IUnknown*   pSetup,  
    [in] IUnknown*   pIdentityArray,  
    [out] IUnknown** pAppDomain  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ebdd4-107">매개 변수</span><span class="sxs-lookup"><span data-stu-id="ebdd4-107">Parameters</span></span>  
 `pwzFriendlyName`  
 <span data-ttu-id="ebdd4-108">[in] 도메인에 친숙 한 이름을 지정 하는 데 사용 되는 선택적 매개 변수</span><span class="sxs-lookup"><span data-stu-id="ebdd4-108">[in] An optional parameter used to give a friendly name to the domain.</span></span> <span data-ttu-id="ebdd4-109">이 이름은 같은 도메인을 식별 하는 디버거 사용자 인터페이스에 표시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ebdd4-109">This friendly name can be displayed in user interfaces such as debuggers to identify the domain.</span></span>  
  
 `pSetup`  
 <span data-ttu-id="ebdd4-110">[in] 형식의 선택적 인터페이스 포인터 `IAppDomainSetup`를 호출 하 여 얻은, 합니다 [icorruntimehost:: Createdomainsetup](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-createdomainsetup-method.md) 메서드.</span><span class="sxs-lookup"><span data-stu-id="ebdd4-110">[in] An optional interface pointer of type `IAppDomainSetup`, obtained by a call to the [ICorRuntimeHost::CreateDomainSetup](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-createdomainsetup-method.md) method.</span></span>  
  
 `pIdentityArray`  
 <span data-ttu-id="ebdd4-111">[in] 에 대 한 포인터의 선택적 배열 `IIdentity` 권한 집합을 설정 하기 위해 보안 정책을 통해 매핑된 증명 정보를 나타내는 경우.</span><span class="sxs-lookup"><span data-stu-id="ebdd4-111">[in] An optional array of pointers to `IIdentity` instances that represent evidence mapped through security policy to establish a permission set.</span></span> <span data-ttu-id="ebdd4-112">`IIdentity` 개체를 호출 하 여 얻을 수는 [CreateEvidence](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-createevidence-method.md) 메서드.</span><span class="sxs-lookup"><span data-stu-id="ebdd4-112">An `IIdentity` object can be obtained by calling the [CreateEvidence](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-createevidence-method.md) method.</span></span>  
  
 `pAppDomain`  
 <span data-ttu-id="ebdd4-113">[out] 형식의 인터페이스 포인터를 <xref:System._AppDomain> 인스턴스에 <xref:System.AppDomain?displayProperty=nameWithType> 추가 도메인을 제어 하는데 사용할 수는 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ebdd4-113">[out] An interface pointer of type <xref:System._AppDomain> to an instance of <xref:System.AppDomain?displayProperty=nameWithType> that can be used to further control the domain.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ebdd4-114">반환 값</span><span class="sxs-lookup"><span data-stu-id="ebdd4-114">Return Value</span></span>  
  
|<span data-ttu-id="ebdd4-115">HRESULT</span><span class="sxs-lookup"><span data-stu-id="ebdd4-115">HRESULT</span></span>|<span data-ttu-id="ebdd4-116">설명</span><span class="sxs-lookup"><span data-stu-id="ebdd4-116">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="ebdd4-117">S_OK</span><span class="sxs-lookup"><span data-stu-id="ebdd4-117">S_OK</span></span>|<span data-ttu-id="ebdd4-118">작업에 성공 합니다.</span><span class="sxs-lookup"><span data-stu-id="ebdd4-118">The operation was successful.</span></span>|  
|<span data-ttu-id="ebdd4-119">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="ebdd4-119">S_FALSE</span></span>|<span data-ttu-id="ebdd4-120">작업을 완료 하지 못했습니다.</span><span class="sxs-lookup"><span data-stu-id="ebdd4-120">The operation failed to complete.</span></span>|  
|<span data-ttu-id="ebdd4-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="ebdd4-121">E_FAIL</span></span>|<span data-ttu-id="ebdd4-122">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="ebdd4-122">An unknown, catastrophic failure occurred.</span></span> <span data-ttu-id="ebdd4-123">E_FAIL을 반환 하는 메서드는 CLR (공용 언어 런타임) 더 이상 사용할 수 진행에서 합니다.</span><span class="sxs-lookup"><span data-stu-id="ebdd4-123">If a method returns E_FAIL, the common language runtime (CLR) is no longer usable in the process.</span></span> <span data-ttu-id="ebdd4-124">호스팅 Api에 대 한 후속 호출 HOST_E_CLRNOTAVAILABLE를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="ebdd4-124">Subsequent calls to any hosting APIs return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="ebdd4-125">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="ebdd4-125">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="ebdd4-126">CLR이 로드 된 프로세스에 또는 CLR 상태인는 관리 코드를 실행 하거나 호출을 처리할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ebdd4-126">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ebdd4-127">설명</span><span class="sxs-lookup"><span data-stu-id="ebdd4-127">Remarks</span></span>  
 <span data-ttu-id="ebdd4-128">`CreateDomainEx` 기능을 확장 [CreateDomain](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-createdomain-method.md) 호출자에 게 전달 함으로써는 `IAppDomainSetup` 응용 프로그램 도메인 구성에 대 한 속성 값을 사용 하 여 인스턴스.</span><span class="sxs-lookup"><span data-stu-id="ebdd4-128">`CreateDomainEx` extends the capabilities of [CreateDomain](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-createdomain-method.md) by allowing the caller to pass in an `IAppDomainSetup` instance with property values for configuring the application domain.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ebdd4-129">요구 사항</span><span class="sxs-lookup"><span data-stu-id="ebdd4-129">Requirements</span></span>  
 <span data-ttu-id="ebdd4-130">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="ebdd4-130">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ebdd4-131">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="ebdd4-131">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="ebdd4-132">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="ebdd4-132">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="ebdd4-133">**.NET framework 버전:** 1.0, 1.1</span><span class="sxs-lookup"><span data-stu-id="ebdd4-133">**.NET Framework Version:** 1.0, 1.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ebdd4-134">참고자료</span><span class="sxs-lookup"><span data-stu-id="ebdd4-134">See also</span></span>
- <xref:System._AppDomain>
- <xref:System.AppDomain>
- <xref:System.IAppDomainSetup?displayProperty=nameWithType>
- [<span data-ttu-id="ebdd4-135">CreateDomain 메서드</span><span class="sxs-lookup"><span data-stu-id="ebdd4-135">CreateDomain Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-createdomain-method.md)
- [<span data-ttu-id="ebdd4-136">ICorRuntimeHost 인터페이스</span><span class="sxs-lookup"><span data-stu-id="ebdd4-136">ICorRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)
