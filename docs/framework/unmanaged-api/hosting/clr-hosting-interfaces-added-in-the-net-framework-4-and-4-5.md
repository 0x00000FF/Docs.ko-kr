---
title: .NET Framework 4 및 4.5에 추가된 CLR 호스팅 인터페이스
ms.date: 03/30/2017
helpviewer_keywords:
- hosting interfaces [.NET Framework], version 4
- .NET Framework 4, hosting interfaces
- interfaces [.NET Framework hosting], version 4
ms.assetid: f6af6116-f5b0-4bda-a276-fffdba70893d
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e9086502968fb9046237e77b76b4038a9f32f4ef
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/09/2018
ms.locfileid: "44253093"
---
# <a name="clr-hosting-interfaces-added-in-the-net-framework-4-and-45"></a><span data-ttu-id="0cf63-102">.NET Framework 4 및 4.5에 추가된 CLR 호스팅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="0cf63-102">CLR Hosting Interfaces Added in the .NET Framework 4 and 4.5</span></span>
<span data-ttu-id="0cf63-103">이 섹션에서는 관리 되지 않는 인터페이스를 설명 합니다. 호스트에는 CLR (공용 언어 런타임) 통합을 사용할 수는 [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)], [!INCLUDE[net_v45](../../../../includes/net-v45-md.md)], 응용 프로그램에 이상 버전.</span><span class="sxs-lookup"><span data-stu-id="0cf63-103">This section describes interfaces that unmanaged hosts can use to integrate the common language runtime (CLR) in the [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)], [!INCLUDE[net_v45](../../../../includes/net-v45-md.md)], and later versions into their applications.</span></span> <span data-ttu-id="0cf63-104">이러한 인터페이스는 구성 프로세스에 런타임을 로드 하는 호스트에 대 한 메서드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="0cf63-104">These interfaces provide methods for a host to configure and load the runtime into a process.</span></span>  
  
 <span data-ttu-id="0cf63-105">부터 [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)]모든 호스팅, 인터페이스는 다음과 같은 특징이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0cf63-105">Starting with the [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)], all hosting interfaces have the following characteristics:</span></span>  
  
-   <span data-ttu-id="0cf63-106">수명 관리 사용 (`AddRef` 하 고 `Release`)를 캡슐화 (암시적 컨텍스트) 및 `QueryInterface` com</span><span class="sxs-lookup"><span data-stu-id="0cf63-106">They use lifetime management (`AddRef` and `Release`), encapsulation (implicit context) and `QueryInterface` from COM.</span></span>  
  
-   <span data-ttu-id="0cf63-107">사용 하지 않습니다 COM 형식을 같은 `BSTR`, `SAFEARRAY`, 또는 `VARIANT`합니다.</span><span class="sxs-lookup"><span data-stu-id="0cf63-107">There do not use COM types such as `BSTR`, `SAFEARRAY`, or `VARIANT`.</span></span>  
  
-   <span data-ttu-id="0cf63-108">아파트 모델, 집계 또는 없습니다 레지스트리 정품 인증을 사용 하는 합니다 [CoCreateInstance 함수](https://go.microsoft.com/fwlink/?LinkId=142894)합니다.</span><span class="sxs-lookup"><span data-stu-id="0cf63-108">There are no apartment models, aggregation, or registry activation that use the [CoCreateInstance function](https://go.microsoft.com/fwlink/?LinkId=142894).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="0cf63-109">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="0cf63-109">In This Section</span></span>  
 [<span data-ttu-id="0cf63-110">ICLRAppDomainResourceMonitor 인터페이스</span><span class="sxs-lookup"><span data-stu-id="0cf63-110">ICLRAppDomainResourceMonitor Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrappdomainresourcemonitor-interface.md)  
 <span data-ttu-id="0cf63-111">응용 프로그램 도메인의 메모리 및 CPU 사용량을 검사 하는 방법을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="0cf63-111">Provides methods that inspect an application domain's memory and CPU usage.</span></span>  
  
 [<span data-ttu-id="0cf63-112">ICLRDomainManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="0cf63-112">ICLRDomainManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrdomainmanager-interface.md)  
 <span data-ttu-id="0cf63-113">호스트를에서 기본 응용 프로그램 도메인을 초기화 하 고 초기화 속성을 지정 하는 응용 프로그램 도메인 관리자를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0cf63-113">Enables the host to specify the application domain manager that will be used to initialize the default application domain, and to specify initialization properties.</span></span>  
  
 [<span data-ttu-id="0cf63-114">ICLRGCManager2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="0cf63-114">ICLRGCManager2 Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager2-interface.md)  
 <span data-ttu-id="0cf63-115">제공 된 [SetGCStartupLimitsEx](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager2-setgcstartuplimitsex-method.md) 메서드를 사용 하면 가비지 수집 세그먼트의 크기 및 가비지 컬렉션 시스템의 0 세대의 최대 크기 이상으로 설정 값을 호스트 하는 `DWORD`합니다.</span><span class="sxs-lookup"><span data-stu-id="0cf63-115">Provides the [SetGCStartupLimitsEx](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager2-setgcstartuplimitsex-method.md) method, which enables a host to set the size of the garbage collection segment and the maximum size of the garbage collection system's generation 0 to values greater than `DWORD`.</span></span>  
  
 [<span data-ttu-id="0cf63-116">ICLRMetaHost 인터페이스</span><span class="sxs-lookup"><span data-stu-id="0cf63-116">ICLRMetaHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-interface.md)  
 <span data-ttu-id="0cf63-117">CLR의 특정 버전을 반환, 모든 설치 된 Clr 목록, 모든 프로세스에서 런타임을 나열, 정품 인증 인터페이스를 반환 되며 어셈블리로 컴파일하는 데 사용 되는 CLR 버전을 검색 하는 방법을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="0cf63-117">Provides methods that return a specific version of the CLR, list all installed CLRs, list all in-process runtimes, return the activation interface, and discover the CLR version used to compile an assembly.</span></span>  
  
 [<span data-ttu-id="0cf63-118">ICLRMetaHostPolicy 인터페이스</span><span class="sxs-lookup"><span data-stu-id="0cf63-118">ICLRMetaHostPolicy Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrmetahostpolicy-interface.md)  
 <span data-ttu-id="0cf63-119">제공 된 [GetRequestedRuntime](../../../../docs/framework/unmanaged-api/hosting/iclrmetahostpolicy-getrequestedruntime-method.md) 정책 기준, 관리 되는 어셈블리, 버전 및 구성 파일을 기반으로 CLR 인터페이스를 제공 하는 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="0cf63-119">Provides the [GetRequestedRuntime](../../../../docs/framework/unmanaged-api/hosting/iclrmetahostpolicy-getrequestedruntime-method.md) method that provides a CLR interface based on policy criteria, managed assembly, version, and configuration file.</span></span>  
  
 [<span data-ttu-id="0cf63-120">ICLRRuntimeInfo 인터페이스</span><span class="sxs-lookup"><span data-stu-id="0cf63-120">ICLRRuntimeInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md)  
 <span data-ttu-id="0cf63-121">특정 런타임 버전, 디렉터리 및 부하 상태를 포함 하 여에 대 한 정보를 반환 하는 메서드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="0cf63-121">Provides methods that return information about a specific runtime, including version, directory, and load status.</span></span>  
  
 [<span data-ttu-id="0cf63-122">ICLRStrongName 인터페이스</span><span class="sxs-lookup"><span data-stu-id="0cf63-122">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)  
 <span data-ttu-id="0cf63-123">강력한 이름의 어셈블리를 서명 하는 기본 전역 정적 함수를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="0cf63-123">Provides basic global static functions for signing assemblies with strong names.</span></span> <span data-ttu-id="0cf63-124">모든 합니다 [ICLRStrongName](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md) 메서드는 표준 COM HRESULTs를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="0cf63-124">All the [ICLRStrongName](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md) methods return standard COM HRESULTs.</span></span>  
  
 [<span data-ttu-id="0cf63-125">ICLRStrongName2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="0cf63-125">ICLRStrongName2 Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname2-interface.md)  
 <span data-ttu-id="0cf63-126">보안 해시 알고리즘 (SHA-256, SHA-384 및 SHA-512)의 sha-2 그룹을 사용 하 여 강력한 이름을 만드는 기능을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="0cf63-126">Provides the ability to create strong names using the SHA-2 group of Secure Hash Algorithms (SHA-256, SHA-384, and SHA-512).</span></span>  
  
 [<span data-ttu-id="0cf63-127">ICLRTask2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="0cf63-127">ICLRTask2 Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask2-interface.md)  
 <span data-ttu-id="0cf63-128">모든 기능을 제공 합니다 [ICLRTask 인터페이스](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)를 현재 스레드에서 지연 될 스레드 중단을 허용 하는 메서드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="0cf63-128">Provides all the functionality of the [ICLRTask Interface](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md); in addition, provides methods that allow thread aborts to be delayed on the current thread.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="0cf63-129">관련 단원</span><span class="sxs-lookup"><span data-stu-id="0cf63-129">Related Sections</span></span>  
 [<span data-ttu-id="0cf63-130">사용되지 않는 CLR 호스팅 인터페이스 및 Coclass</span><span class="sxs-lookup"><span data-stu-id="0cf63-130">Deprecated CLR Hosting Interfaces and Coclasses</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-interfaces-and-coclasses.md)  
 <span data-ttu-id="0cf63-131">.NET Framework 버전 1.0 및 1.1을 사용 하 여 제공 하는 호스팅 인터페이스를 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="0cf63-131">Describes the hosting interfaces provided with the .NET Framework versions 1.0 and 1.1.</span></span>  
  
 [<span data-ttu-id="0cf63-132">CLR 호스팅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="0cf63-132">CLR Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/clr-hosting-interfaces.md)  
 <span data-ttu-id="0cf63-133">.NET Framework 버전 2.0, 3.0 및 3.5를 사용 하 여 제공 하는 호스팅 인터페이스를 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="0cf63-133">Describes the hosting interfaces provided with the .NET Framework versions 2.0, 3.0, and 3.5.</span></span>  
  
 [<span data-ttu-id="0cf63-134">호스팅</span><span class="sxs-lookup"><span data-stu-id="0cf63-134">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)  
 <span data-ttu-id="0cf63-135">.NET Framework에서 호스팅 소개 합니다.</span><span class="sxs-lookup"><span data-stu-id="0cf63-135">Introduces hosting in the .NET Framework.</span></span>
