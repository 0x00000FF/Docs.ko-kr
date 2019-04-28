---
title: <disableFusionUpdatesFromADManager> 요소
ms.date: 03/30/2017
helpviewer_keywords:
- disableFusionUpdatesFromADManager element
- <disableFusionUpdatesFromADManager> element
ms.assetid: 58d2866c-37bd-4ffa-abaf-ff35926a2939
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 27c8c1cac68aca1c40826ff549d62d9636d9b0c6
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61704910"
---
# <a name="disablefusionupdatesfromadmanager-element"></a><span data-ttu-id="2c9be-102">\<disableFusionUpdatesFromADManager > 요소</span><span class="sxs-lookup"><span data-stu-id="2c9be-102">\<disableFusionUpdatesFromADManager> Element</span></span>
<span data-ttu-id="2c9be-103">런타임 호스트가 애플리케이션 도메인에 대한 구성 설정을 재정의할 수 있도록 허용하는 기본 동작을 사용하지 않도록 설정할지를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="2c9be-103">Specifies whether the default behavior, which is to allow the runtime host to override configuration settings for an application domain, is disabled.</span></span>  
  
 <span data-ttu-id="2c9be-104">\<구성 > 요소</span><span class="sxs-lookup"><span data-stu-id="2c9be-104">\<configuration> Element</span></span>  
<span data-ttu-id="2c9be-105">\<런타임 > 요소</span><span class="sxs-lookup"><span data-stu-id="2c9be-105">\<runtime> Element</span></span>  
<span data-ttu-id="2c9be-106">\<disableFusionUpdatesFromADManager></span><span class="sxs-lookup"><span data-stu-id="2c9be-106">\<disableFusionUpdatesFromADManager></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2c9be-107">구문</span><span class="sxs-lookup"><span data-stu-id="2c9be-107">Syntax</span></span>  
  
```xml  
<disableFusionUpdatesFromADManager enabled="0|1"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="2c9be-108">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="2c9be-108">Attributes and Elements</span></span>  
 <span data-ttu-id="2c9be-109">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="2c9be-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="2c9be-110">특성</span><span class="sxs-lookup"><span data-stu-id="2c9be-110">Attributes</span></span>  
  
|<span data-ttu-id="2c9be-111">특성</span><span class="sxs-lookup"><span data-stu-id="2c9be-111">Attribute</span></span>|<span data-ttu-id="2c9be-112">설명</span><span class="sxs-lookup"><span data-stu-id="2c9be-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="2c9be-113">사용</span><span class="sxs-lookup"><span data-stu-id="2c9be-113">enabled</span></span>|<span data-ttu-id="2c9be-114">필수 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="2c9be-114">Required attribute.</span></span><br /><br /> <span data-ttu-id="2c9be-115">Fusion 설정을 재정의 하는 기본 기능을 사용할 수 있는지 여부를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="2c9be-115">Specifies whether the default ability to override Fusion settings is disabled.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="2c9be-116">enabled 특성</span><span class="sxs-lookup"><span data-stu-id="2c9be-116">enabled Attribute</span></span>  
  
|<span data-ttu-id="2c9be-117">값</span><span class="sxs-lookup"><span data-stu-id="2c9be-117">Value</span></span>|<span data-ttu-id="2c9be-118">설명</span><span class="sxs-lookup"><span data-stu-id="2c9be-118">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="2c9be-119">0</span><span class="sxs-lookup"><span data-stu-id="2c9be-119">0</span></span>|<span data-ttu-id="2c9be-120">Fusion 설정을 재정의 하는 기능을 해제 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2c9be-120">Do not disable the ability to override Fusion settings.</span></span> <span data-ttu-id="2c9be-121">이 기본 동작을 사용 하 여 시작 된 [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)]합니다.</span><span class="sxs-lookup"><span data-stu-id="2c9be-121">This is the default behavior, starting with the [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)].</span></span>|  
|<span data-ttu-id="2c9be-122">1</span><span class="sxs-lookup"><span data-stu-id="2c9be-122">1</span></span>|<span data-ttu-id="2c9be-123">Fusion 설정을 재정의 하는 기능을 사용 하지 않도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="2c9be-123">Disable the ability to override Fusion settings.</span></span> <span data-ttu-id="2c9be-124">이.NET Framework의 이전 버전의 동작으로 돌아갑니다.</span><span class="sxs-lookup"><span data-stu-id="2c9be-124">This reverts to the behavior of earlier versions of the .NET Framework.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="2c9be-125">자식 요소</span><span class="sxs-lookup"><span data-stu-id="2c9be-125">Child Elements</span></span>  
 <span data-ttu-id="2c9be-126">없음</span><span class="sxs-lookup"><span data-stu-id="2c9be-126">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="2c9be-127">부모 요소</span><span class="sxs-lookup"><span data-stu-id="2c9be-127">Parent Elements</span></span>  
  
|<span data-ttu-id="2c9be-128">요소</span><span class="sxs-lookup"><span data-stu-id="2c9be-128">Element</span></span>|<span data-ttu-id="2c9be-129">설명</span><span class="sxs-lookup"><span data-stu-id="2c9be-129">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="2c9be-130">공용 언어 런타임 및 .NET Framework 애플리케이션에서 사용하는 모든 구성 파일의 루트 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="2c9be-130">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="2c9be-131">어셈블리 바인딩 및 가비지 컬렉션에 대한 정보를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="2c9be-131">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2c9be-132">설명</span><span class="sxs-lookup"><span data-stu-id="2c9be-132">Remarks</span></span>  
 <span data-ttu-id="2c9be-133">부터 [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)], 기본 동작은 허용 하는 <xref:System.AppDomainManager> 개체를 사용 하 여 구성 설정을 재정의 하려면를 <xref:System.AppDomainSetup.ConfigurationFile%2A> 속성 또는 <xref:System.AppDomainSetup.SetConfigurationBytes%2A> 메서드의 <xref:System.AppDomainSetup> 구현에 전달 되는 개체 <xref:System.AppDomainManager.InitializeNewDomain%2A?displayProperty=nameWithType> 의 서브 클래스에서 메서드를 <xref:System.AppDomainManager>입니다.</span><span class="sxs-lookup"><span data-stu-id="2c9be-133">Starting with the [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)], the default behavior is to allow the <xref:System.AppDomainManager> object to override configuration settings by using the <xref:System.AppDomainSetup.ConfigurationFile%2A> property or the <xref:System.AppDomainSetup.SetConfigurationBytes%2A> method of the <xref:System.AppDomainSetup> object that is passed to your implementation of the <xref:System.AppDomainManager.InitializeNewDomain%2A?displayProperty=nameWithType> method, in your subclass of <xref:System.AppDomainManager>.</span></span> <span data-ttu-id="2c9be-134">기본 응용 프로그램 도메인에 대 한 설정을 변경 하면 응용 프로그램 구성 파일에 지정 된 설정을 재정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="2c9be-134">For the default application domain, the settings you change override the settings that were specified by the application configuration file.</span></span> <span data-ttu-id="2c9be-135">에 전달 된 구성 설정을 다른 응용 프로그램 도메인에 대 한 재정의 <xref:System.AppDomainManager.CreateDomain%2A?displayProperty=nameWithType> 또는 <xref:System.AppDomain.CreateDomain%2A?displayProperty=nameWithType> 메서드.</span><span class="sxs-lookup"><span data-stu-id="2c9be-135">For other application domains, they override the configuration settings that were passed to the <xref:System.AppDomainManager.CreateDomain%2A?displayProperty=nameWithType> or <xref:System.AppDomain.CreateDomain%2A?displayProperty=nameWithType> method.</span></span>  
  
 <span data-ttu-id="2c9be-136">새 구성 정보를 전달 하거나 null을 전달 (`Nothing` Visual Basic에서)에 전달 된 구성 정보를 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="2c9be-136">You can either pass new configuration information, or pass null (`Nothing` in Visual Basic) to eliminate configuration information that was passed in.</span></span>  
  
 <span data-ttu-id="2c9be-137">둘 다에 구성 정보를 전달 하지 마십시오 합니다 <xref:System.AppDomainSetup.ConfigurationFile%2A> 속성 및 <xref:System.AppDomainSetup.SetConfigurationBytes%2A> 메서드.</span><span class="sxs-lookup"><span data-stu-id="2c9be-137">Do not pass configuration information to both the <xref:System.AppDomainSetup.ConfigurationFile%2A> property and the <xref:System.AppDomainSetup.SetConfigurationBytes%2A> method.</span></span> <span data-ttu-id="2c9be-138">둘 다에 구성 정보를 전달 하는 경우 정보를 전달 하는 <xref:System.AppDomainSetup.ConfigurationFile%2A> 때문에 속성이 무시 됩니다는 <xref:System.AppDomainSetup.SetConfigurationBytes%2A> 메서드는 응용 프로그램 구성 파일에서 구성 정보를 재정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="2c9be-138">If you pass configuration information to both, the information you pass to the <xref:System.AppDomainSetup.ConfigurationFile%2A> property is ignored, because the <xref:System.AppDomainSetup.SetConfigurationBytes%2A> method overrides configuration information from the application configuration file.</span></span> <span data-ttu-id="2c9be-139">사용 하는 경우는 <xref:System.AppDomainSetup.ConfigurationFile%2A> 속성에 null을 전달할 수 (`Nothing` Visual Basic의)에 <xref:System.AppDomainSetup.SetConfigurationBytes%2A> 메서드 호출에 지정 된 모든 구성 바이트를 제거 하는 <xref:System.AppDomainManager.CreateDomain%2A?displayProperty=nameWithType> 또는 <xref:System.AppDomain.CreateDomain%2A?displayProperty=nameWithType> 메서드.</span><span class="sxs-lookup"><span data-stu-id="2c9be-139">If you use the <xref:System.AppDomainSetup.ConfigurationFile%2A> property, you can pass null (`Nothing` in Visual Basic) to the <xref:System.AppDomainSetup.SetConfigurationBytes%2A> method to eliminate any configuration bytes that were specified in the call to the <xref:System.AppDomainManager.CreateDomain%2A?displayProperty=nameWithType> or <xref:System.AppDomain.CreateDomain%2A?displayProperty=nameWithType> method.</span></span>  
  
 <span data-ttu-id="2c9be-140">구성 정보 외에도 다음 설정에서 변경할 수 있습니다 합니다 <xref:System.AppDomainSetup> 의 구현에 전달 되는 개체를 <xref:System.AppDomainManager.InitializeNewDomain%2A?displayProperty=nameWithType> 메서드: <xref:System.AppDomainSetup.ApplicationBase%2A>, <xref:System.AppDomainSetup.ApplicationName%2A>를 <xref:System.AppDomainSetup.CachePath%2A>를 <xref:System.AppDomainSetup.DisallowApplicationBaseProbing%2A>, <xref:System.AppDomainSetup.DisallowBindingRedirects%2A> <xref:System.AppDomainSetup.DisallowCodeDownload%2A>, <xref:System.AppDomainSetup.DisallowPublisherPolicy%2A>, <xref:System.AppDomainSetup.DynamicBase%2A>, <xref:System.AppDomainSetup.LoaderOptimization%2A>를 <xref:System.AppDomainSetup.PrivateBinPath%2A>를 <xref:System.AppDomainSetup.PrivateBinPathProbe%2A>를 <xref:System.AppDomainSetup.ShadowCopyDirectories%2A>, 및 <xref:System.AppDomainSetup.ShadowCopyFiles%2A>합니다.</span><span class="sxs-lookup"><span data-stu-id="2c9be-140">In addition to configuration information, you can change the following settings on the <xref:System.AppDomainSetup> object that is passed to your implementation of the <xref:System.AppDomainManager.InitializeNewDomain%2A?displayProperty=nameWithType> method: <xref:System.AppDomainSetup.ApplicationBase%2A>, <xref:System.AppDomainSetup.ApplicationName%2A>, <xref:System.AppDomainSetup.CachePath%2A>, <xref:System.AppDomainSetup.DisallowApplicationBaseProbing%2A>, <xref:System.AppDomainSetup.DisallowBindingRedirects%2A>, <xref:System.AppDomainSetup.DisallowCodeDownload%2A>, <xref:System.AppDomainSetup.DisallowPublisherPolicy%2A>, <xref:System.AppDomainSetup.DynamicBase%2A>, <xref:System.AppDomainSetup.LoaderOptimization%2A>, <xref:System.AppDomainSetup.PrivateBinPath%2A>, <xref:System.AppDomainSetup.PrivateBinPathProbe%2A>, <xref:System.AppDomainSetup.ShadowCopyDirectories%2A>, and <xref:System.AppDomainSetup.ShadowCopyFiles%2A>.</span></span>  
  
 <span data-ttu-id="2c9be-141">사용 하 여 대 안으로 `<disableFusionUpdatesFromADManager>` 요소인 레지스트리 설정을 만들어 또는 환경 변수를 설정 하 여 기본 동작을 비활성화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2c9be-141">As an alternative to using the `<disableFusionUpdatesFromADManager>` element, you can disable the default behavior by creating a registry setting or by setting an environment variable.</span></span> <span data-ttu-id="2c9be-142">레지스트리에서 라는 dword를 만듭니다 `COMPLUS_disableFusionUpdatesFromADManager` 아래에서 `HKCU\Software\Microsoft\.NETFramework` 또는 `HKLM\Software\Microsoft\.NETFramework`, 값을 1로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="2c9be-142">In the registry, create a DWORD value named `COMPLUS_disableFusionUpdatesFromADManager` under `HKCU\Software\Microsoft\.NETFramework` or `HKLM\Software\Microsoft\.NETFramework`, and set the value to 1.</span></span> <span data-ttu-id="2c9be-143">명령줄에서 환경 변수를 설정 `COMPLUS_disableFusionUpdatesFromADManager` 1입니다.</span><span class="sxs-lookup"><span data-stu-id="2c9be-143">At the command line, set the environment variable `COMPLUS_disableFusionUpdatesFromADManager` to 1.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2c9be-144">예제</span><span class="sxs-lookup"><span data-stu-id="2c9be-144">Example</span></span>  
 <span data-ttu-id="2c9be-145">다음 예제에서는 사용 하 여 Fusion 설정을 재정의 하는 기능을 사용 하지 않도록 설정 하는 방법의 `<disableFusionUpdatesFromADManager>` 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="2c9be-145">The following example shows how to disable the ability to override Fusion settings by using the `<disableFusionUpdatesFromADManager>` element.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <disableFusionUpdatesFromADManager enabled="1" />  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="2c9be-146">참고자료</span><span class="sxs-lookup"><span data-stu-id="2c9be-146">See also</span></span>

- [<span data-ttu-id="2c9be-147">런타임 설정 스키마</span><span class="sxs-lookup"><span data-stu-id="2c9be-147">Runtime Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)
- [<span data-ttu-id="2c9be-148">구성 파일 스키마</span><span class="sxs-lookup"><span data-stu-id="2c9be-148">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)
- [<span data-ttu-id="2c9be-149">런타임에서 어셈블리를 찾는 방법</span><span class="sxs-lookup"><span data-stu-id="2c9be-149">How the Runtime Locates Assemblies</span></span>](../../../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md)
