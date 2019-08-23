---
title: <cryptoClasses> 요소
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/mscorlib/cryptographySettings/cryptoNameMapping/cryptoClasses
- http://schemas.microsoft.com/.NetConfiguration/v2.0#cryptoClasses
helpviewer_keywords:
- <cryptoClasses> element
- cryptoClasses element
ms.assetid: 290d5f96-946d-4f02-babb-1d31ec0b8295
ms.openlocfilehash: 87e64ecd79ebc54a669d33550790781c87b5917c
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2019
ms.locfileid: "69921127"
---
# <a name="cryptoclasses-element"></a><span data-ttu-id="8dcf6-102">\<cryptoClasses > 요소</span><span class="sxs-lookup"><span data-stu-id="8dcf6-102">\<cryptoClasses> Element</span></span>
<span data-ttu-id="8dcf6-103">[\<nameEntry>](nameentry-element.md) 요소에 있는 이름에 매핑되는 암호화 클래스의 목록이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8dcf6-103">Contains a list of cryptography classes that have a mapping to a friendly name in the [\<nameEntry>](nameentry-element.md) element.</span></span>  
  
 <span data-ttu-id="8dcf6-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="8dcf6-104">\<configuration></span></span>  
<span data-ttu-id="8dcf6-105">\<mscorlib></span><span class="sxs-lookup"><span data-stu-id="8dcf6-105">\<mscorlib></span></span>  
<span data-ttu-id="8dcf6-106">\<cryptographySettings></span><span class="sxs-lookup"><span data-stu-id="8dcf6-106">\<cryptographySettings></span></span>  
<span data-ttu-id="8dcf6-107">\<cryptoNameMapping></span><span class="sxs-lookup"><span data-stu-id="8dcf6-107">\<cryptoNameMapping></span></span>  
<span data-ttu-id="8dcf6-108">\<cryptoClasses></span><span class="sxs-lookup"><span data-stu-id="8dcf6-108">\<cryptoClasses></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8dcf6-109">구문</span><span class="sxs-lookup"><span data-stu-id="8dcf6-109">Syntax</span></span>  
  
```xml  
<cryptoClasses>   
</cryptoClasses>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="8dcf6-110">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="8dcf6-110">Attributes and Elements</span></span>  
 <span data-ttu-id="8dcf6-111">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="8dcf6-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="8dcf6-112">특성</span><span class="sxs-lookup"><span data-stu-id="8dcf6-112">Attributes</span></span>  
 <span data-ttu-id="8dcf6-113">없음</span><span class="sxs-lookup"><span data-stu-id="8dcf6-113">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="8dcf6-114">자식 요소</span><span class="sxs-lookup"><span data-stu-id="8dcf6-114">Child Elements</span></span>  
  
|<span data-ttu-id="8dcf6-115">요소</span><span class="sxs-lookup"><span data-stu-id="8dcf6-115">Element</span></span>|<span data-ttu-id="8dcf6-116">설명</span><span class="sxs-lookup"><span data-stu-id="8dcf6-116">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="8dcf6-117">\<cryptoClass></span><span class="sxs-lookup"><span data-stu-id="8dcf6-117">\<cryptoClass></span></span>](cryptoclass-element.md)|<span data-ttu-id="8dcf6-118">**\<nameEntry>** 요소에 있는 이름에 매핑되는 암호화 클래스가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8dcf6-118">Contains a cryptography class that has a mapping to a friendly name in the **\<nameEntry>** element.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="8dcf6-119">부모 요소</span><span class="sxs-lookup"><span data-stu-id="8dcf6-119">Parent Elements</span></span>  
  
|<span data-ttu-id="8dcf6-120">요소</span><span class="sxs-lookup"><span data-stu-id="8dcf6-120">Element</span></span>|<span data-ttu-id="8dcf6-121">설명</span><span class="sxs-lookup"><span data-stu-id="8dcf6-121">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="8dcf6-122">공용 언어 런타임 및 .NET Framework 애플리케이션에서 사용하는 모든 구성 파일의 루트 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="8dcf6-122">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`cryptographySettings`|<span data-ttu-id="8dcf6-123">암호화 설정이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8dcf6-123">Contains cryptography settings.</span></span>|  
|`cryptoNameMapping`|<span data-ttu-id="8dcf6-124">이름에 대한 클래스의 매핑이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8dcf6-124">Contains mappings of classes to friendly names.</span></span>|  
|`mscorlib`|<span data-ttu-id="8dcf6-125">요소를 `cryptographySettings` 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="8dcf6-125">Contains the `cryptographySettings` element.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="8dcf6-126">예제</span><span class="sxs-lookup"><span data-stu-id="8dcf6-126">Example</span></span>  
 <span data-ttu-id="8dcf6-127">다음 예제에서는  **\<cryptoclass >** 요소를 사용 하 여 암호화 클래스를 참조 하 고 런타임을 구성 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="8dcf6-127">The following example shows how use the **\<cryptoClass>** element to reference a cryptography class and to configure the runtime.</span></span> <span data-ttu-id="8dcf6-128">그런 다음 "RSA" <xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A?displayProperty=nameWithType> 문자열을 메서드에 전달 하 고 <xref:System.Security.Cryptography.AsymmetricAlgorithm.Create%2A> 메서드를 사용 하 여 `MyCryptoRSAClass` 개체를 반환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8dcf6-128">You can then pass the string "RSA" to the <xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A?displayProperty=nameWithType> method and use the <xref:System.Security.Cryptography.AsymmetricAlgorithm.Create%2A> method to return a `MyCryptoRSAClass` object.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="8dcf6-129">참고자료</span><span class="sxs-lookup"><span data-stu-id="8dcf6-129">See also</span></span>

- <xref:System.Security.Cryptography>
- [<span data-ttu-id="8dcf6-130">구성 파일 스키마</span><span class="sxs-lookup"><span data-stu-id="8dcf6-130">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="8dcf6-131">암호화 설정 스키마</span><span class="sxs-lookup"><span data-stu-id="8dcf6-131">Cryptography Settings Schema</span></span>](index.md)
- [<span data-ttu-id="8dcf6-132">Cryptographic Services</span><span class="sxs-lookup"><span data-stu-id="8dcf6-132">Cryptographic Services</span></span>](../../../../standard/security/cryptographic-services.md)
- [<span data-ttu-id="8dcf6-133">System.Security.Cryptography.CryptoConfig.CreateFromName</span><span class="sxs-lookup"><span data-stu-id="8dcf6-133">System.Security.Cryptography.CryptoConfig.CreateFromName</span></span>](Overload:System.Security.Cryptography.CryptoConfig.CreateFromName)
- [<span data-ttu-id="8dcf6-134">암호화 클래스 구성</span><span class="sxs-lookup"><span data-stu-id="8dcf6-134">Configuring Cryptography Classes</span></span>](../../configure-cryptography-classes.md)
