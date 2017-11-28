---
title: "&lt;bindingRedirect&gt; 요소"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/runtime/assemblyBinding/dependentAssembly/bindingRedirect
- http://schemas.microsoft.com/.NetConfiguration/v2.0#bindingRedirect
helpviewer_keywords:
- <bindingRedirect> element
- container tags, <bindingRedirect> element
- bindingRedirect element
ms.assetid: 67784ecd-9663-434e-bd6a-26975e447ac0
caps.latest.revision: "12"
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: 3bc8abc019ddb271c8c1246b280be754585bfd61
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="ltbindingredirectgt-element"></a><span data-ttu-id="a3eda-102">&lt;bindingRedirect&gt; 요소</span><span class="sxs-lookup"><span data-stu-id="a3eda-102">&lt;bindingRedirect&gt; Element</span></span>
<span data-ttu-id="a3eda-103">어셈블리 버전을 다른 버전으로 리디렉션합니다.</span><span class="sxs-lookup"><span data-stu-id="a3eda-103">Redirects one assembly version to another.</span></span>  
  
 <span data-ttu-id="a3eda-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="a3eda-104">\<configuration></span></span>  
<span data-ttu-id="a3eda-105">\<런타임 ></span><span class="sxs-lookup"><span data-stu-id="a3eda-105">\<runtime></span></span>  
<span data-ttu-id="a3eda-106">\<assemblyBinding ></span><span class="sxs-lookup"><span data-stu-id="a3eda-106">\<assemblyBinding></span></span>  
<span data-ttu-id="a3eda-107">\<dependentAssembly ></span><span class="sxs-lookup"><span data-stu-id="a3eda-107">\<dependentAssembly></span></span>  
<span data-ttu-id="a3eda-108">\<bindingRedirect ></span><span class="sxs-lookup"><span data-stu-id="a3eda-108">\<bindingRedirect></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a3eda-109">구문</span><span class="sxs-lookup"><span data-stu-id="a3eda-109">Syntax</span></span>  
  
```xml  
   <bindingRedirect    
oldVersion="existing assembly version"  
newVersion="new assembly version"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a3eda-110">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="a3eda-110">Attributes and Elements</span></span>  
 <span data-ttu-id="a3eda-111">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="a3eda-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a3eda-112">특성</span><span class="sxs-lookup"><span data-stu-id="a3eda-112">Attributes</span></span>  
  
|<span data-ttu-id="a3eda-113">특성</span><span class="sxs-lookup"><span data-stu-id="a3eda-113">Attribute</span></span>|<span data-ttu-id="a3eda-114">설명</span><span class="sxs-lookup"><span data-stu-id="a3eda-114">Description</span></span>|  
|---------------|-----------------|  
|`oldVersion`|<span data-ttu-id="a3eda-115">필수 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="a3eda-115">Required attribute.</span></span><br /><br /> <span data-ttu-id="a3eda-116">원래 요청된 어셈블리 버전을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="a3eda-116">Specifies the version of the assembly that was originally requested.</span></span> <span data-ttu-id="a3eda-117">어셈블리 버전 번호의 형식은 *major.minor.build.revision*합니다.</span><span class="sxs-lookup"><span data-stu-id="a3eda-117">The format of an assembly version number is *major.minor.build.revision*.</span></span> <span data-ttu-id="a3eda-118">이 버전 번호의 각 부분에 사용할 수 있는 값은 0부터 65535까지입니다.</span><span class="sxs-lookup"><span data-stu-id="a3eda-118">Valid values for each part of this version number are 0 to 65535.</span></span><br /><br /> <span data-ttu-id="a3eda-119">다음 형식으로 다양한 버전을 지정할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a3eda-119">You can also specify a range of versions in the following format:</span></span><br /><br /> <span data-ttu-id="a3eda-120">*n.n.n.n-n.n.n.n*</span><span class="sxs-lookup"><span data-stu-id="a3eda-120">*n.n.n.n - n.n.n.n*</span></span>|  
|`newVersion`|<span data-ttu-id="a3eda-121">필수 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="a3eda-121">Required attribute.</span></span><br /><br /> <span data-ttu-id="a3eda-122">원래 요청 된 버전 형식에서 대신 사용할 어셈블리의 버전을 지정: *n.n.n.n*</span><span class="sxs-lookup"><span data-stu-id="a3eda-122">Specifies the version of the assembly to use instead of the originally requested version in the format: *n.n.n.n*</span></span><br /><br /> <span data-ttu-id="a3eda-123">이 값은 `oldVersion`보다 이전 버전을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a3eda-123">This value can specify an earlier version than `oldVersion`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="a3eda-124">자식 요소</span><span class="sxs-lookup"><span data-stu-id="a3eda-124">Child Elements</span></span>  
  
|<span data-ttu-id="a3eda-125">요소</span><span class="sxs-lookup"><span data-stu-id="a3eda-125">Element</span></span>|<span data-ttu-id="a3eda-126">설명</span><span class="sxs-lookup"><span data-stu-id="a3eda-126">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="a3eda-127">없음</span><span class="sxs-lookup"><span data-stu-id="a3eda-127">None</span></span>||  
  
### <a name="parent-elements"></a><span data-ttu-id="a3eda-128">부모 요소</span><span class="sxs-lookup"><span data-stu-id="a3eda-128">Parent Elements</span></span>  
  
|<span data-ttu-id="a3eda-129">요소</span><span class="sxs-lookup"><span data-stu-id="a3eda-129">Element</span></span>|<span data-ttu-id="a3eda-130">설명</span><span class="sxs-lookup"><span data-stu-id="a3eda-130">Description</span></span>|  
|-------------|-----------------|  
|`assemblyBinding`|<span data-ttu-id="a3eda-131">어셈블리 버전 리디렉션 및 어셈블리 위치에 대한 정보를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="a3eda-131">Contains information about assembly version redirection and the locations of assemblies.</span></span>|  
|`configuration`|<span data-ttu-id="a3eda-132">공용 언어 런타임 및 .NET Framework 응용 프로그램에서 사용하는 모든 구성 파일의 루트 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="a3eda-132">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`dependentAssembly`|<span data-ttu-id="a3eda-133">각 어셈블리에 대한 바인딩 정책 및 어셈블리 위치를 캡슐화합니다.</span><span class="sxs-lookup"><span data-stu-id="a3eda-133">Encapsulates binding policy and assembly location for each assembly.</span></span> <span data-ttu-id="a3eda-134">각 어셈블리에 dependentAssembly 요소를 하나만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a3eda-134">Use one dependentAssembly element for each assembly.</span></span>|  
|`runtime`|<span data-ttu-id="a3eda-135">어셈블리 바인딩 및 가비지 컬렉션에 대한 정보를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="a3eda-135">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a3eda-136">설명</span><span class="sxs-lookup"><span data-stu-id="a3eda-136">Remarks</span></span>  
 <span data-ttu-id="a3eda-137">강력한 이름의 어셈블리에 대해 .NET Framework 응용 프로그램을 빌드하면, 응용 프로그램은 새 버전이 있는 경우에도 런타임에 기본적으로 어셈블리의 원래 버전을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="a3eda-137">When you build a .NET Framework application against a strong-named assembly, the application uses that version of the assembly at run time by default, even if a new version is available.</span></span> <span data-ttu-id="a3eda-138">그러나 어셈블리의 새 버전을 사용하도록 응용 프로그램을 구성할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a3eda-138">However, you can configure the application to run against a newer version of the assembly.</span></span> <span data-ttu-id="a3eda-139">런타임에서 사용할 어셈블리 버전을 결정 하려면 이러한 파일을 사용 하는 방법에 대 한 세부 정보를 참조 하십시오. [런타임에서 어셈블리를 찾는 방법을](../../../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="a3eda-139">For details on how the runtime uses these files to determine which assembly version to use, see [How the Runtime Locates Assemblies](../../../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md).</span></span>  
  
 <span data-ttu-id="a3eda-140">`bindingRedirect` 요소에 여러 개의 `dependentAssembly` 요소를 사용하면 둘 이상의 어셈블리 버전을 리디렉션할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a3eda-140">You can redirect more than one assembly version by including multiple `bindingRedirect` elements in a `dependentAssembly` element.</span></span> <span data-ttu-id="a3eda-141">어셈블리의 새 버전에서 이전 버전으로 리디렉션할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a3eda-141">You can also redirect from a newer version to an older version of the assembly.</span></span>  
  
 <span data-ttu-id="a3eda-142">응용 프로그램 구성 파일에서 어셈블리 바인딩을 명시적으로 리디렉션하려면 보안 권한이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="a3eda-142">Explicit assembly binding redirection in an application configuration file requires a security permission.</span></span> <span data-ttu-id="a3eda-143">이는 .NET Framework 어셈블리와 타사 어셈블리의 리디렉션 모두에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="a3eda-143">This applies to redirection of .NET Framework assemblies and assemblies from third parties.</span></span> <span data-ttu-id="a3eda-144">설정 하 여 권한 부여는 <xref:System.Security.Permissions.SecurityPermissionFlag> 에 플래그는 <xref:System.Security.Permissions.SecurityPermission>합니다.</span><span class="sxs-lookup"><span data-stu-id="a3eda-144">The permission is granted by setting the <xref:System.Security.Permissions.SecurityPermissionFlag> flag on the <xref:System.Security.Permissions.SecurityPermission>.</span></span> <span data-ttu-id="a3eda-145">자세한 내용은 참조 [어셈블리 바인딩 리디렉션 보안 권한](../../../../../docs/framework/configure-apps/assembly-binding-redirection-security-permission.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="a3eda-145">For more information, see [Assembly Binding Redirection Security Permission](../../../../../docs/framework/configure-apps/assembly-binding-redirection-security-permission.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="a3eda-146">예제</span><span class="sxs-lookup"><span data-stu-id="a3eda-146">Example</span></span>  
 <span data-ttu-id="a3eda-147">다음 예제에서는 어셈블리 버전을 다른 버전으로 리디렉션하는 방법을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="a3eda-147">The following example shows how to redirect one assembly version to another.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">  
         <dependentAssembly>  
            <assemblyIdentity name="myAssembly"  
                              publicKeyToken="32ab4ba45e0a69a1"  
                              culture="neutral" />  
            <bindingRedirect oldVersion="1.0.0.0"  
                             newVersion="2.0.0.0"/>  
         </dependentAssembly>  
      </assemblyBinding>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="a3eda-148">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a3eda-148">See Also</span></span>  
 [<span data-ttu-id="a3eda-149">런타임 설정 스키마</span><span class="sxs-lookup"><span data-stu-id="a3eda-149">Runtime Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)  
 [<span data-ttu-id="a3eda-150">구성 파일 스키마</span><span class="sxs-lookup"><span data-stu-id="a3eda-150">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)  
 [<span data-ttu-id="a3eda-151">어셈블리 버전 리디렉션</span><span class="sxs-lookup"><span data-stu-id="a3eda-151">Redirecting Assembly Versions</span></span>](../../../../../docs/framework/configure-apps/redirect-assembly-versions.md)
