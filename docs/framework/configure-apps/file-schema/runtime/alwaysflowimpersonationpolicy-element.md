---
title: '&lt;alwaysFlowImpersonationPolicy&gt; Element'
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/runtime/alwaysFlowImpersonationPolicy
- http://schemas.microsoft.com/.NetConfiguration/v2.0#alwaysFlowImpersonationPolicy
helpviewer_keywords:
- alwaysFlowImpersonationPolicy element
- <alwaysFlowImpersonationPolicy> element
ms.assetid: ee622801-9e46-470b-85ab-88c4b1dd2ee1
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: fcad683ace327caf06a4a9a6ef5b7cf1d9a9334f
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54596438"
---
# <a name="ltalwaysflowimpersonationpolicygt-element"></a><span data-ttu-id="87df5-102">&lt;alwaysFlowImpersonationPolicy&gt; Element</span><span class="sxs-lookup"><span data-stu-id="87df5-102">&lt;alwaysFlowImpersonationPolicy&gt; Element</span></span>
<span data-ttu-id="87df5-103">가장을 수행하는 방법과 관계없이 Windows ID가 항상 비동기 지점 간을 흐르도록 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="87df5-103">Specifies that the Windows identity always flows across asynchronous points, regardless of how impersonation was performed.</span></span>  
  
 <span data-ttu-id="87df5-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="87df5-104">\<configuration></span></span>  
<span data-ttu-id="87df5-105">\<runtime></span><span class="sxs-lookup"><span data-stu-id="87df5-105">\<runtime></span></span>  
<span data-ttu-id="87df5-106">\<alwaysFlowImpersonationPolicy></span><span class="sxs-lookup"><span data-stu-id="87df5-106">\<alwaysFlowImpersonationPolicy></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="87df5-107">구문</span><span class="sxs-lookup"><span data-stu-id="87df5-107">Syntax</span></span>  
  
```xml  
<alwaysFlowImpersonationPolicy    
  enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="87df5-108">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="87df5-108">Attributes and Elements</span></span>  
 <span data-ttu-id="87df5-109">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="87df5-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="87df5-110">특성</span><span class="sxs-lookup"><span data-stu-id="87df5-110">Attributes</span></span>  
  
|<span data-ttu-id="87df5-111">특성</span><span class="sxs-lookup"><span data-stu-id="87df5-111">Attribute</span></span>|<span data-ttu-id="87df5-112">설명</span><span class="sxs-lookup"><span data-stu-id="87df5-112">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="87df5-113">필수 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="87df5-113">Required attribute.</span></span><br /><br /> <span data-ttu-id="87df5-114">Windows id 비동기 지점 간을 흐르도록 여부를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="87df5-114">Indicates whether the Windows identity flows across asynchronous points.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="87df5-115">enabled 특성</span><span class="sxs-lookup"><span data-stu-id="87df5-115">enabled Attribute</span></span>  
  
|<span data-ttu-id="87df5-116">값</span><span class="sxs-lookup"><span data-stu-id="87df5-116">Value</span></span>|<span data-ttu-id="87df5-117">설명</span><span class="sxs-lookup"><span data-stu-id="87df5-117">Description</span></span>|  
|-----------|-----------------|  
|`false`|<span data-ttu-id="87df5-118">Identity를 통해 가장이 수행 하는 경우가 아니면 비동기 지점 간을 흐르지 않는 Windows 같은 관리 되는 메서드 <xref:System.Security.Principal.WindowsIdentity.Impersonate%2A>합니다.</span><span class="sxs-lookup"><span data-stu-id="87df5-118">The Windows identity does not flow across asynchronous points, unless the impersonation is performed through managed methods such as <xref:System.Security.Principal.WindowsIdentity.Impersonate%2A>.</span></span> <span data-ttu-id="87df5-119">이 값이 기본값입니다.</span><span class="sxs-lookup"><span data-stu-id="87df5-119">This is the default.</span></span>|  
|`true`|<span data-ttu-id="87df5-120">Windows id는 항상 가장이 수행 하는 방법에 관계 없이 비동기 지점 간을 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="87df5-120">The Windows identity always flows across asynchronous points, regardless of how impersonation was performed.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="87df5-121">자식 요소</span><span class="sxs-lookup"><span data-stu-id="87df5-121">Child Elements</span></span>  
 <span data-ttu-id="87df5-122">없음</span><span class="sxs-lookup"><span data-stu-id="87df5-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="87df5-123">부모 요소</span><span class="sxs-lookup"><span data-stu-id="87df5-123">Parent Elements</span></span>  
  
|<span data-ttu-id="87df5-124">요소</span><span class="sxs-lookup"><span data-stu-id="87df5-124">Element</span></span>|<span data-ttu-id="87df5-125">설명</span><span class="sxs-lookup"><span data-stu-id="87df5-125">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="87df5-126">공용 언어 런타임 및 .NET Framework 애플리케이션에서 사용하는 모든 구성 파일의 루트 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="87df5-126">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="87df5-127">어셈블리 바인딩 및 가비지 컬렉션에 대한 정보를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="87df5-127">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="87df5-128">설명</span><span class="sxs-lookup"><span data-stu-id="87df5-128">Remarks</span></span>  
 <span data-ttu-id="87df5-129">.NET Framework 버전 1.0 및 1.1에서는 Windows id 비동기 지점 간을 흐르지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="87df5-129">In the .NET Framework versions 1.0 and 1.1, the Windows identity does not flow across asynchronous points.</span></span> <span data-ttu-id="87df5-130">.NET Framework 버전 2.0에는 <xref:System.Threading.ExecutionContext> 개체는 현재 실행 중인 스레드에 대 한 정보를 포함 하 고 응용 프로그램 도메인 내에서 비동기 지점 간을 흐르도록 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="87df5-130">In the .NET Framework version 2.0, there is an <xref:System.Threading.ExecutionContext> object that contains information about the currently executing thread, and flows it across asynchronous points within an application domain.</span></span> <span data-ttu-id="87df5-131"><xref:System.Security.Principal.WindowsIdentity> 도 사용 하 여 가장이 수행 하는 제공 된 비동기 지점 간을 흐르도록 하는 정보의 일부로 흐름 관리 되는 메서드 같은 <xref:System.Security.Principal.WindowsIdentity.Impersonate%2A> platform와 같은 다른 방법을 통해서가 아니라 네이티브 메서드를 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="87df5-131">The <xref:System.Security.Principal.WindowsIdentity> also flows as part of the information that flows across the asynchronous points, provided the impersonation was achieved using managed methods such as <xref:System.Security.Principal.WindowsIdentity.Impersonate%2A> and not through other means such as platform invoke to native methods.</span></span> <span data-ttu-id="87df5-132">이 요소를 사용 하 여 Windows id에 가장이 수행 하는 방법에 관계 없이 비동기 지점 간을 흐름을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="87df5-132">This element is used to specify that the Windows identity does flow across asynchronous points, regardless of how the impersonation was achieved.</span></span>  
  
 <span data-ttu-id="87df5-133">다른 두 가지 방법으로이 기본 동작을 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="87df5-133">You can alter this default behavior in two other ways:</span></span>  
  
1.  <span data-ttu-id="87df5-134">스레드별 기준 관리 되는 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="87df5-134">In managed code on a per-thread basis.</span></span>  
  
     <span data-ttu-id="87df5-135">스레드별 기준 흐름을 수정 하 여 무시할 수 있습니다는 <xref:System.Threading.ExecutionContext> 및 <xref:System.Security.SecurityContext> 를 사용 하 여 설정 합니다 <xref:System.Threading.ExecutionContext.SuppressFlow%2A?displayProperty=nameWithType>, <xref:System.Security.SecurityContext.SuppressFlowWindowsIdentity%2A?displayProperty=nameWithType>, 또는 <xref:System.Security.SecurityContext.SuppressFlow%2A?displayProperty=nameWithType> 메서드.</span><span class="sxs-lookup"><span data-stu-id="87df5-135">You can suppress the flow on a per-thread basis by modifying the <xref:System.Threading.ExecutionContext> and <xref:System.Security.SecurityContext> settings by using the <xref:System.Threading.ExecutionContext.SuppressFlow%2A?displayProperty=nameWithType>, <xref:System.Security.SecurityContext.SuppressFlowWindowsIdentity%2A?displayProperty=nameWithType>, or <xref:System.Security.SecurityContext.SuppressFlow%2A?displayProperty=nameWithType> method.</span></span>  
  
2.  <span data-ttu-id="87df5-136">로드 된 CLR (공용 언어 런타임) 관리 되지 않는 호스팅 인터페이스를 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="87df5-136">In the call to the unmanaged hosting interface to load the common language runtime (CLR).</span></span>  
  
     <span data-ttu-id="87df5-137">관리 되지 않는 호스팅 인터페이스 (대신 간단한 관리 되는 실행 파일)를 사용 하 여 CLR을 로드 하, 경우에 대 한 호출에서 특수 플래그를 지정할 수 있습니다 합니다 [CorBindToRuntimeEx 함수](../../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) 함수입니다.</span><span class="sxs-lookup"><span data-stu-id="87df5-137">If an unmanaged hosting interface (instead of a simple managed executable) is used to load the CLR, you can specify a special flag in the call to the [CorBindToRuntimeEx Function](../../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) function.</span></span> <span data-ttu-id="87df5-138">전체 프로세스에 대 한 호환성 모드를 사용 하려면 다음을 설정 합니다 `flags` 에 대 한 매개 변수 [CorBindToRuntimeEx 함수](../../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) 에 `STARTUP_ALWAYSFLOW_IMPERSONATION`합니다.</span><span class="sxs-lookup"><span data-stu-id="87df5-138">To enable the compatibility mode for the entire process, set the `flags` parameter for [CorBindToRuntimeEx Function](../../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) to `STARTUP_ALWAYSFLOW_IMPERSONATION`.</span></span>  
  
## <a name="configuration-file"></a><span data-ttu-id="87df5-139">구성 파일</span><span class="sxs-lookup"><span data-stu-id="87df5-139">Configuration File</span></span>  
 <span data-ttu-id="87df5-140">.NET Framework 응용 프로그램에서이 요소는 응용 프로그램 구성 파일에만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="87df5-140">In a .NET Framework application, this element can be used only in the application configuration file.</span></span>  
  
 <span data-ttu-id="87df5-141">ASP.NET 응용 프로그램에서 가장 흐름이 있는 aspnet.config 파일에서 구성할 수 있습니다는 \<Windows 폴더 > \Microsoft.NET\Framework\vx.x.xxxx 디렉터리입니다.</span><span class="sxs-lookup"><span data-stu-id="87df5-141">For an ASP.NET application, the impersonation flow can be configured in the aspnet.config file found in the \<Windows Folder>\Microsoft.NET\Framework\vx.x.xxxx directory.</span></span>  
  
 <span data-ttu-id="87df5-142">기본적으로 ASP.NET에는 다음 구성 설정을 사용 하 여 aspnet.config 파일에서 가장 흐름을 비활성화 합니다.</span><span class="sxs-lookup"><span data-stu-id="87df5-142">ASP.NET by default disables the impersonation flow in the aspnet.config file by using the following configuration settings:</span></span>  
  
```xml
<configuration>  
   <runtime>  
      <legacyImpersonationPolicy enabled="true"/>  
      <alwaysFlowImpersonationPolicy enabled="false"/>  
   </runtime>  
</configuration>  
```  
  
 <span data-ttu-id="87df5-143">ASP.NET에서 가장의 흐름을 대신 허용 하려면 다음 구성 설정을 사용 해야 합니다 명시적으로.</span><span class="sxs-lookup"><span data-stu-id="87df5-143">In ASP.NET, if you want to allow the flow of impersonation instead, you must explicitly use the following configuration settings:</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <legacyImpersonationPolicy enabled="false"/>  
      <alwaysFlowImpersonationPolicy enabled="true"/>  
   </runtime>  
</configuration>  
```  
  
## <a name="example"></a><span data-ttu-id="87df5-144">예제</span><span class="sxs-lookup"><span data-stu-id="87df5-144">Example</span></span>  
 <span data-ttu-id="87df5-145">다음 예제에서는 관리 되는 메서드 이외의 수단을 통해 가장이 수행 하는 경우에 비동기 지점 간을 Windows id가 전달 되도록 지정 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="87df5-145">The following example shows how to specify that the Windows identity flows across asynchronous points, even when the impersonation is achieved through means other than managed methods.</span></span>  
  
```xml  
<configuration>  
  <runtime>  
    <alwaysFlowImpersonationPolicy enabled="true"/>  
  </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="87df5-146">참고자료</span><span class="sxs-lookup"><span data-stu-id="87df5-146">See also</span></span>
- [<span data-ttu-id="87df5-147">런타임 설정 스키마</span><span class="sxs-lookup"><span data-stu-id="87df5-147">Runtime Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)
- [<span data-ttu-id="87df5-148">구성 파일 스키마</span><span class="sxs-lookup"><span data-stu-id="87df5-148">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)
- [<span data-ttu-id="87df5-149">\<legacyImpersonationPolicy > 요소</span><span class="sxs-lookup"><span data-stu-id="87df5-149">\<legacyImpersonationPolicy> Element</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/legacyimpersonationpolicy-element.md)
