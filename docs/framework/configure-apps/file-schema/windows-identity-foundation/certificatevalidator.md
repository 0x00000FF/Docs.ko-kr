---
title: '&lt;certificateValidator&gt;'
ms.date: 03/30/2017
ms.assetid: 86161897-c20f-4ad8-9d7f-050c247251bf
author: BrucePerlerMS
ms.openlocfilehash: 65b8aa6fa4422579ce0d1c5e33d3418ea051612a
ms.sourcegitcommit: 69229651598b427c550223d3c58aba82e47b3f82
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/04/2018
ms.locfileid: "48776885"
---
# <a name="ltcertificatevalidatorgt"></a><span data-ttu-id="46e03-102">&lt;certificateValidator&gt;</span><span class="sxs-lookup"><span data-stu-id="46e03-102">&lt;certificateValidator&gt;</span></span>
<span data-ttu-id="46e03-103">인증서 유효성 검사에 대 한 사용자 지정 형식을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="46e03-103">Specifies a custom type for certificate validation.</span></span> <span data-ttu-id="46e03-104">이 이와 같은 경우에 사용 됩니다 합니다 `certificateValidationMode` 특성을 [ \<certificateValidation >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/certificatevalidation.md) 요소 "Custom"으로 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="46e03-104">This type is used only if the `certificateValidationMode` attribute of the [\<certificateValidation>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/certificatevalidation.md) element is set to "Custom".</span></span>  
  
 <span data-ttu-id="46e03-105">\<system.identityModel></span><span class="sxs-lookup"><span data-stu-id="46e03-105">\<system.identityModel></span></span>  
<span data-ttu-id="46e03-106">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="46e03-106">\<identityConfiguration></span></span>  
<span data-ttu-id="46e03-107">\<certificateValidation ></span><span class="sxs-lookup"><span data-stu-id="46e03-107">\<certificateValidation></span></span>  
<span data-ttu-id="46e03-108">\<certificateValidator ></span><span class="sxs-lookup"><span data-stu-id="46e03-108">\<certificateValidator></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="46e03-109">구문</span><span class="sxs-lookup"><span data-stu-id="46e03-109">Syntax</span></span>  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <certificateValidation>  
      <certificateValidator type=xs:string>  
      </certificateValidator>  
    </certificateValidation>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="46e03-110">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="46e03-110">Attributes and Elements</span></span>  
 <span data-ttu-id="46e03-111">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="46e03-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="46e03-112">특성</span><span class="sxs-lookup"><span data-stu-id="46e03-112">Attributes</span></span>  
  
|<span data-ttu-id="46e03-113">특성</span><span class="sxs-lookup"><span data-stu-id="46e03-113">Attribute</span></span>|<span data-ttu-id="46e03-114">설명</span><span class="sxs-lookup"><span data-stu-id="46e03-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="46e03-115">type</span><span class="sxs-lookup"><span data-stu-id="46e03-115">type</span></span>|<span data-ttu-id="46e03-116">파생 되는 사용자 지정 형식 지정을 <xref:System.IdentityModel.Selectors.X509CertificateValidator> 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="46e03-116">Specifies a custom type that derives from the <xref:System.IdentityModel.Selectors.X509CertificateValidator> class.</span></span> <span data-ttu-id="46e03-117">설정 합니다 `certificateValidationMode` 특성을 [ \<certificateValidation >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/certificatevalidation.md) "custom"이이 유형을 사용 하는 요소.</span><span class="sxs-lookup"><span data-stu-id="46e03-117">Set the `certificateValidationMode` attribute of the [\<certificateValidation>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/certificatevalidation.md) element to "Custom" to use this type.</span></span> <span data-ttu-id="46e03-118">지정 하는 방법에 대 한 자세한 내용은 합니다 `type` 특성을 참조 하십시오 [사용자 지정 형식 참조](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/index.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="46e03-118">For more information about how to specify the `type` attribute, see [Custom Type References](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/index.md).</span></span> <span data-ttu-id="46e03-119">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="46e03-119">Optional.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="46e03-120">자식 요소</span><span class="sxs-lookup"><span data-stu-id="46e03-120">Child Elements</span></span>  
 <span data-ttu-id="46e03-121">없음</span><span class="sxs-lookup"><span data-stu-id="46e03-121">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="46e03-122">부모 요소</span><span class="sxs-lookup"><span data-stu-id="46e03-122">Parent Elements</span></span>  
  
|<span data-ttu-id="46e03-123">요소</span><span class="sxs-lookup"><span data-stu-id="46e03-123">Element</span></span>|<span data-ttu-id="46e03-124">설명</span><span class="sxs-lookup"><span data-stu-id="46e03-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="46e03-125">\<certificateValidation ></span><span class="sxs-lookup"><span data-stu-id="46e03-125">\<certificateValidation></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/certificatevalidation.md)|<span data-ttu-id="46e03-126">토큰 처리기 인증서의 유효성을 검사 하는 데 사용 되는 설정을 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="46e03-126">Controls the settings that token handlers use to validate certificates.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="46e03-127">예제</span><span class="sxs-lookup"><span data-stu-id="46e03-127">Example</span></span>  
  
```xml  
<certificateValidation certificateValidationMode="Custom"  
                       revocationMode="Online"  
                       trustedStoreLocation="LocalMachine">  
    <certificateValidator type="MyNamespace.CustomValidator, MyAssembly" />    
</certificateValidation>        
```
