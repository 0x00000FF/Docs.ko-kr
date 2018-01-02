---
title: '&lt;system.identityModel&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 210ce7e9-d07b-400c-800f-5f525dcf95e8
caps.latest.revision: "5"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.workload: dotnet
ms.openlocfilehash: e5d26ab2ff3207b0905c33ba237bf71e623a103d
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="ltsystemidentitymodelgt"></a><span data-ttu-id="34c12-102">&lt;system.identityModel&gt;</span><span class="sxs-lookup"><span data-stu-id="34c12-102">&lt;system.identityModel&gt;</span></span>
<span data-ttu-id="34c12-103">응용 프로그램에서 Windows Identity Foundation (WIF) 옵션을 사용 하도록 설정 하는 것에 대 한 구성을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="34c12-103">Provides configuration for enabling Windows Identity Foundation (WIF) options in applications.</span></span>  
  
 <span data-ttu-id="34c12-104">\<system.identityModel ></span><span class="sxs-lookup"><span data-stu-id="34c12-104">\<system.identityModel></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="34c12-105">구문</span><span class="sxs-lookup"><span data-stu-id="34c12-105">Syntax</span></span>  
  
```xml  
<system.identityModel>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="34c12-106">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="34c12-106">Attributes and Elements</span></span>  
 <span data-ttu-id="34c12-107">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="34c12-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="34c12-108">특성</span><span class="sxs-lookup"><span data-stu-id="34c12-108">Attributes</span></span>  
 <span data-ttu-id="34c12-109">없음</span><span class="sxs-lookup"><span data-stu-id="34c12-109">None</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="34c12-110">자식 요소</span><span class="sxs-lookup"><span data-stu-id="34c12-110">Child Elements</span></span>  
  
|<span data-ttu-id="34c12-111">요소</span><span class="sxs-lookup"><span data-stu-id="34c12-111">Element</span></span>|<span data-ttu-id="34c12-112">설명</span><span class="sxs-lookup"><span data-stu-id="34c12-112">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="34c12-113">\<identityConfiguration ></span><span class="sxs-lookup"><span data-stu-id="34c12-113">\<identityConfiguration></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md)|<span data-ttu-id="34c12-114">서비스 수준 id 설정을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="34c12-114">Specifies service-level identity settings.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="34c12-115">부모 요소</span><span class="sxs-lookup"><span data-stu-id="34c12-115">Parent Elements</span></span>  
  
|<span data-ttu-id="34c12-116">요소</span><span class="sxs-lookup"><span data-stu-id="34c12-116">Element</span></span>|<span data-ttu-id="34c12-117">설명</span><span class="sxs-lookup"><span data-stu-id="34c12-117">Description</span></span>|  
|-------------|-----------------|  
|`<configuration>`|<span data-ttu-id="34c12-118">공용 언어 런타임 및 .NET Framework 응용 프로그램에서 사용하는 모든 구성 파일의 루트 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="34c12-118">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="34c12-119">설명</span><span class="sxs-lookup"><span data-stu-id="34c12-119">Remarks</span></span>  
 <span data-ttu-id="34c12-120">추가 `<system.identityModel>` 섹션 서비스 또는 응용 프로그램이 Windows Identity Foundation (WIF)를 사용 하도록 구성 하려면 구성 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="34c12-120">Add a `<system.identityModel>` section to the configuration file to configure a service or application to use Windows Identity Foundation (WIF).</span></span> <span data-ttu-id="34c12-121">`<system.identityModel>` 에서 요소가 표시 되는 <xref:System.IdentityModel.Configuration.SystemIdentityModelSection> 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="34c12-121">The `<system.identityModel>` element is represented by the <xref:System.IdentityModel.Configuration.SystemIdentityModelSection> class.</span></span>  
  
## <a name="example"></a><span data-ttu-id="34c12-122">예</span><span class="sxs-lookup"><span data-stu-id="34c12-122">Example</span></span>  
 <span data-ttu-id="34c12-123">추가 하는 방법을 보여 주는 다음 예제는 `<system.identityModel>` 구성 파일에 섹션.</span><span class="sxs-lookup"><span data-stu-id="34c12-123">The following example shows how to add a `<system.identityModel>` section to a configuration file.</span></span> <span data-ttu-id="34c12-124">구성 섹션 및 네임 스페이스 선언을 추가 해야는 `<configSections>` 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="34c12-124">You must first add the configuration section and namespace declaration under the `<configSections>` element.</span></span> <span data-ttu-id="34c12-125">추가 하 여는 `<system.IdentityModel>` 하나 이상의 id 구성을 지정 하려면 구성 파일 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="34c12-125">Then you can add the `<system.IdentityModel>` element to your configuration file to specify one or more identity configurations.</span></span>  
  
```xml  
<configuration>  
  <configSections>  
    <!--WIF 4.5 sections -->  
    <section name="system.identityModel" type="System.IdentityModel.Configuration.SystemIdentityModelSection, System.IdentityModel, Version=4.0.0.0, Culture=neutral, PublicKeyToken=B77A5C561934E089"/>  
    <section name="system.identityModel.services" type="System.IdentityModel.Services.Configuration.SystemIdentityModelServicesSection, System.IdentityModel.Services, Version=4.0.0.0, Culture=neutral, PublicKeyToken=B77A5C561934E089"/>  
  </configSections>  
  
  ...  
  
  <system.identityModel>  
    <identityConfiguration>  
      <audienceUris>  
        <add value="http://localhost/WebApplication1/" />  
      </audienceUris>  
      <issuerNameRegistry type="System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry, System.IdentityModel, Version=4.0.0.0, Culture=neutral, PublicKeyToken=B77A5C561934E089">  
        <trustedIssuers>  
          <add thumbprint="313D3B … 9106A9EC" name="SelfSTS" />  
        </trustedIssuers>  
      </issuerNameRegistry>  
      <certificateValidation certificateValidationMode="None"/>  
    </identityConfiguration>  
  </system.identityModel>  
  
  ...  
  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="34c12-126">참고 항목</span><span class="sxs-lookup"><span data-stu-id="34c12-126">See Also</span></span>  
 <xref:System.IdentityModel.Configuration.SystemIdentityModelSection>
