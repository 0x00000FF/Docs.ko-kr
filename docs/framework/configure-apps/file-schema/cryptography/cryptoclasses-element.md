---
title: '&lt;cryptoClasses&gt; 요소'
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/mscorlib/cryptographySettings/cryptoNameMapping/cryptoClasses
- http://schemas.microsoft.com/.NetConfiguration/v2.0#cryptoClasses
helpviewer_keywords:
- <cryptoClasses> element
- cryptoClasses element
ms.assetid: 290d5f96-946d-4f02-babb-1d31ec0b8295
author: mcleblanc
ms.author: markl
ms.openlocfilehash: 8363351efd0b6cbcfee5b137cf9f222e16dcc425
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2018
ms.locfileid: "50188744"
---
# <a name="ltcryptoclassesgt-element"></a><span data-ttu-id="842e9-102">&lt;cryptoClasses&gt; 요소</span><span class="sxs-lookup"><span data-stu-id="842e9-102">&lt;cryptoClasses&gt; Element</span></span>
<span data-ttu-id="842e9-103">[\<nameEntry>](../../../../../docs/framework/configure-apps/file-schema/cryptography/nameentry-element.md) 요소에 있는 이름에 매핑되는 암호화 클래스의 목록이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="842e9-103">Contains a list of cryptography classes that have a mapping to a friendly name in the [\<nameEntry>](../../../../../docs/framework/configure-apps/file-schema/cryptography/nameentry-element.md) element.</span></span>  
  
 <span data-ttu-id="842e9-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="842e9-104">\<configuration></span></span>  
<span data-ttu-id="842e9-105">\<mscorlib ></span><span class="sxs-lookup"><span data-stu-id="842e9-105">\<mscorlib></span></span>  
<span data-ttu-id="842e9-106">\<cryptographySettings ></span><span class="sxs-lookup"><span data-stu-id="842e9-106">\<cryptographySettings></span></span>  
<span data-ttu-id="842e9-107">\<cryptoNameMapping ></span><span class="sxs-lookup"><span data-stu-id="842e9-107">\<cryptoNameMapping></span></span>  
<span data-ttu-id="842e9-108">\<cryptoClasses ></span><span class="sxs-lookup"><span data-stu-id="842e9-108">\<cryptoClasses></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="842e9-109">구문</span><span class="sxs-lookup"><span data-stu-id="842e9-109">Syntax</span></span>  
  
```xml  
<cryptoClasses>   
</cryptoClasses>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="842e9-110">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="842e9-110">Attributes and Elements</span></span>  
 <span data-ttu-id="842e9-111">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="842e9-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="842e9-112">특성</span><span class="sxs-lookup"><span data-stu-id="842e9-112">Attributes</span></span>  
 <span data-ttu-id="842e9-113">없음</span><span class="sxs-lookup"><span data-stu-id="842e9-113">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="842e9-114">자식 요소</span><span class="sxs-lookup"><span data-stu-id="842e9-114">Child Elements</span></span>  
  
|<span data-ttu-id="842e9-115">요소</span><span class="sxs-lookup"><span data-stu-id="842e9-115">Element</span></span>|<span data-ttu-id="842e9-116">설명</span><span class="sxs-lookup"><span data-stu-id="842e9-116">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="842e9-117">\<cryptoClass ></span><span class="sxs-lookup"><span data-stu-id="842e9-117">\<cryptoClass></span></span>](../../../../../docs/framework/configure-apps/file-schema/cryptography/cryptoclass-element.md)|<span data-ttu-id="842e9-118">**\<nameEntry>** 요소에 있는 이름에 매핑되는 암호화 클래스가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="842e9-118">Contains a cryptography class that has a mapping to a friendly name in the **\<nameEntry>** element.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="842e9-119">부모 요소</span><span class="sxs-lookup"><span data-stu-id="842e9-119">Parent Elements</span></span>  
  
|<span data-ttu-id="842e9-120">요소</span><span class="sxs-lookup"><span data-stu-id="842e9-120">Element</span></span>|<span data-ttu-id="842e9-121">설명</span><span class="sxs-lookup"><span data-stu-id="842e9-121">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="842e9-122">공용 언어 런타임 및 .NET Framework 응용 프로그램에서 사용하는 모든 구성 파일의 루트 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="842e9-122">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`cryptographySettings`|<span data-ttu-id="842e9-123">암호화 설정이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="842e9-123">Contains cryptography settings.</span></span>|  
|`cryptoNameMapping`|<span data-ttu-id="842e9-124">이름에 대한 클래스의 매핑이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="842e9-124">Contains mappings of classes to friendly names.</span></span>|  
|`mscorlib`|<span data-ttu-id="842e9-125">포함 된 `cryptographySettings` 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="842e9-125">Contains the `cryptographySettings` element.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="842e9-126">예제</span><span class="sxs-lookup"><span data-stu-id="842e9-126">Example</span></span>  
 <span data-ttu-id="842e9-127">다음 방법을 보여 주는 예제는  **\<cryptoClass >** 암호화 클래스를 참조 하 고 런타임 구성 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="842e9-127">The following example shows how use the **\<cryptoClass>** element to reference a cryptography class and to configure the runtime.</span></span> <span data-ttu-id="842e9-128">"RSA" 문자열을 전달할 수 있습니다는 <xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A?displayProperty=nameWithType> 메서드 및 사용법을 <xref:System.Security.Cryptography.AsymmetricAlgorithm.Create%2A> 반환 하는 방법을 `MyCryptoRSAClass` 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="842e9-128">You can then pass the string "RSA" to the <xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A?displayProperty=nameWithType> method and use the <xref:System.Security.Cryptography.AsymmetricAlgorithm.Create%2A> method to return a `MyCryptoRSAClass` object.</span></span>  
  
```xml  
<configuration>  
   <mscorlib>  
      <cryptographySettings>  
         <cryptoNameMapping>  
            <cryptoClasses>  
               <cryptoClass   MyCryptoRSA="MyCryptoRSAClass, MyAssembly  
                  Culture=neutral, PublicKeyToken=a5d015c7d5a0b012,  
                  Version=1.0.0.0"/>  
               <!-- Other cryptography classes go here. -->  
            </cryptoClasses>  
            <nameEntry name="RSA" class="MyCryptoRSA"/>  
            <nameEntry name="System.Security.Cryptography.AsymmetricAlgorithm"  
                       class="MyCryptoRSA"/>  
             <!-- Mappings to other cryptography classes go here. -->  
         </cryptoNameMapping>  
      </cryptographySettings>  
   </mscorlib>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="842e9-129">참고 항목</span><span class="sxs-lookup"><span data-stu-id="842e9-129">See Also</span></span>  
- <xref:System.Security.Cryptography>  
- [<span data-ttu-id="842e9-130">구성 파일 스키마</span><span class="sxs-lookup"><span data-stu-id="842e9-130">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)  
- [<span data-ttu-id="842e9-131">암호화 설정 스키마</span><span class="sxs-lookup"><span data-stu-id="842e9-131">Cryptography Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/cryptography/index.md)  
- [<span data-ttu-id="842e9-132">Cryptographic Services</span><span class="sxs-lookup"><span data-stu-id="842e9-132">Cryptographic Services</span></span>](../../../../../docs/standard/security/cryptographic-services.md)  
- [<span data-ttu-id="842e9-133">System.Security.Cryptography.CryptoConfig.CreateFromName</span><span class="sxs-lookup"><span data-stu-id="842e9-133">System.Security.Cryptography.CryptoConfig.CreateFromName</span></span>](Overload:System.Security.Cryptography.CryptoConfig.CreateFromName)  
- [<span data-ttu-id="842e9-134">암호화 클래스 구성</span><span class="sxs-lookup"><span data-stu-id="842e9-134">Configuring Cryptography Classes</span></span>](../../../../../docs/framework/configure-apps/configure-cryptography-classes.md)
