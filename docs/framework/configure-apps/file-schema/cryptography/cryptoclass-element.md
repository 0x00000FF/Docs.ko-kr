---
title: <cryptoClass> 요소
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/mscorlib/cryptographySettings/cryptoNameMapping/cryptoClasses/cryptoClass
- http://schemas.microsoft.com/.NetConfiguration/v2.0#cryptoClass
helpviewer_keywords:
- cryptoClass element
- <cryptoClass> element
ms.assetid: 03db52ef-010e-44ea-b6fd-b9c900ecad50
ms.openlocfilehash: c8076fba1ebae693aa5e4c80e822b9ae840ff1c5
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/21/2019
ms.locfileid: "69664330"
---
# <a name="cryptoclass-element"></a><span data-ttu-id="7785d-102">\<cryptoClass > 요소</span><span class="sxs-lookup"><span data-stu-id="7785d-102">\<cryptoClass> Element</span></span>
<span data-ttu-id="7785d-103">[\<nameEntry>](nameentry-element.md) 요소에 있는 이름에 매핑되는 암호화 클래스가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7785d-103">Contains a cryptography class that has a mapping to a friendly name in the [\<nameEntry>](nameentry-element.md) element.</span></span>  
  
 <span data-ttu-id="7785d-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="7785d-104">\<configuration></span></span>  
<span data-ttu-id="7785d-105">\<mscorlib></span><span class="sxs-lookup"><span data-stu-id="7785d-105">\<mscorlib></span></span>  
<span data-ttu-id="7785d-106">\<cryptographySettings></span><span class="sxs-lookup"><span data-stu-id="7785d-106">\<cryptographySettings></span></span>  
<span data-ttu-id="7785d-107">\<cryptoNameMapping></span><span class="sxs-lookup"><span data-stu-id="7785d-107">\<cryptoNameMapping></span></span>  
<span data-ttu-id="7785d-108">\<cryptoClasses></span><span class="sxs-lookup"><span data-stu-id="7785d-108">\<cryptoClasses></span></span>  
<span data-ttu-id="7785d-109">\<cryptoClass></span><span class="sxs-lookup"><span data-stu-id="7785d-109">\<cryptoClass></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7785d-110">구문</span><span class="sxs-lookup"><span data-stu-id="7785d-110">Syntax</span></span>  
  
```xml  
<cryptoClass customClassName="fully qualified type name" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="7785d-111">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="7785d-111">Attributes and Elements</span></span>  
 <span data-ttu-id="7785d-112">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="7785d-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="7785d-113">특성</span><span class="sxs-lookup"><span data-stu-id="7785d-113">Attributes</span></span>  
  
|<span data-ttu-id="7785d-114">특성</span><span class="sxs-lookup"><span data-stu-id="7785d-114">Attribute</span></span>|<span data-ttu-id="7785d-115">설명</span><span class="sxs-lookup"><span data-stu-id="7785d-115">Description</span></span>|  
|---------------|-----------------|  
|`customClassName`|<span data-ttu-id="7785d-116">필수 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="7785d-116">Required attribute.</span></span><br /><br /> <span data-ttu-id="7785d-117">암호화 클래스에 대 한 정보를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="7785d-117">Contains the information for the cryptography class.</span></span> <span data-ttu-id="7785d-118">클래스에 짧은 이름을 제공 하려면이 특성을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="7785d-118">Use this attribute to provide a short name for your class.</span></span> <span data-ttu-id="7785d-119">정규화 된 [형식 이름 지정](../../../reflection-and-codedom/specifying-fully-qualified-type-names.md)에 지정 된 요구 사항을 충족 하는 문자열을 지정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7785d-119">You must specify a string that meets the requirements specified in [Specifying Fully Qualified Type Names](../../../reflection-and-codedom/specifying-fully-qualified-type-names.md).</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="7785d-120">자식 요소</span><span class="sxs-lookup"><span data-stu-id="7785d-120">Child Elements</span></span>  
 <span data-ttu-id="7785d-121">없음</span><span class="sxs-lookup"><span data-stu-id="7785d-121">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="7785d-122">부모 요소</span><span class="sxs-lookup"><span data-stu-id="7785d-122">Parent Elements</span></span>  
  
|<span data-ttu-id="7785d-123">요소</span><span class="sxs-lookup"><span data-stu-id="7785d-123">Element</span></span>|<span data-ttu-id="7785d-124">설명</span><span class="sxs-lookup"><span data-stu-id="7785d-124">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="7785d-125">공용 언어 런타임 및 .NET Framework 애플리케이션에서 사용하는 모든 구성 파일의 루트 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="7785d-125">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`cryptoClasses`|<span data-ttu-id="7785d-126">[\<nameEntry>](nameentry-element.md) 요소에 있는 이름에 매핑되는 암호화 클래스의 목록이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7785d-126">Contains a list of cryptography classes that have a mapping to a friendly name in the [\<nameEntry>](nameentry-element.md) element.</span></span>|  
|`cryptographySettings`|<span data-ttu-id="7785d-127">암호화 설정이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7785d-127">Contains cryptography settings.</span></span>|  
|`cryptoNameMapping`|<span data-ttu-id="7785d-128">이름에 대한 클래스의 매핑이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7785d-128">Contains mappings of classes to friendly names.</span></span>|  
|`mscorlib`|<span data-ttu-id="7785d-129">[\<cryptographySettings>](cryptographysettings-element.md) 요소가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7785d-129">Contains the [\<cryptographySettings>](cryptographysettings-element.md) element.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="7785d-130">예제</span><span class="sxs-lookup"><span data-stu-id="7785d-130">Example</span></span>  
 <span data-ttu-id="7785d-131">다음 예제에서는  **\<cryptoclass >** 요소를 사용 하 여 암호화 클래스를 참조 하 고 런타임을 구성 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="7785d-131">The following example shows how use the **\<cryptoClass>** element to reference a cryptography class and to configure the runtime.</span></span> <span data-ttu-id="7785d-132">그런 다음 "RSA" <xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A?displayProperty=nameWithType> 문자열을 메서드에 전달 하 고 <xref:System.Security.Cryptography.AsymmetricAlgorithm.Create%2A> 메서드를 사용 하 여 `MyCryptoRSAClass` 개체를 반환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7785d-132">You can then pass the string "RSA" to the <xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A?displayProperty=nameWithType> method and use the <xref:System.Security.Cryptography.AsymmetricAlgorithm.Create%2A> method to return a `MyCryptoRSAClass` object.</span></span>  
  
```xml  
<configuration>  
   <mscorlib>  
      <cryptographySettings>  
         <cryptoNameMapping>  
            <cryptoClasses>  
               <cryptoClass   MyCryptoRSA="MyCryptoRSAClass, MyAssembly  
                  Culture=neutral, PublicKeyToken=a5d015c7d5a0b012,  
                  Version=1.0.0.0"/>  
            </cryptoClasses>  
            <nameEntry name="RSA" class="MyCryptoRSA"/>  
            <nameEntry name="System.Security.Cryptography.AsymmetricAlgorithm"  
                       class="MyCryptoRSA"/>  
         </cryptoNameMapping>  
      </cryptographySettings>  
   </mscorlib>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="7785d-133">참고자료</span><span class="sxs-lookup"><span data-stu-id="7785d-133">See also</span></span>

- [<span data-ttu-id="7785d-134">구성 파일 스키마</span><span class="sxs-lookup"><span data-stu-id="7785d-134">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="7785d-135">암호화 설정 스키마</span><span class="sxs-lookup"><span data-stu-id="7785d-135">Cryptography Settings Schema</span></span>](index.md)
- [<span data-ttu-id="7785d-136">Cryptographic Services</span><span class="sxs-lookup"><span data-stu-id="7785d-136">Cryptographic Services</span></span>](../../../../../docs/standard/security/cryptographic-services.md)
- [<span data-ttu-id="7785d-137">암호화 클래스 구성</span><span class="sxs-lookup"><span data-stu-id="7785d-137">Configuring Cryptography Classes</span></span>](../../configure-cryptography-classes.md)
