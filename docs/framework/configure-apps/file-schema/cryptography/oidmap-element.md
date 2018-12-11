---
title: '&lt;oidMap&gt; 요소'
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#oidMap
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/mscorlib/cryptographySettings/oidMap
helpviewer_keywords:
- <oidMap> element
- oidMap element
ms.assetid: 7f0c2246-c070-4748-b96a-2f66a296c539
author: mcleblanc
ms.author: markl
ms.openlocfilehash: badab8200a4b10fdc13987dfe39ebfebd4d1f7cf
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/10/2018
ms.locfileid: "53143170"
---
# <a name="ltoidmapgt-element"></a><span data-ttu-id="7884c-102">&lt;oidMap&gt; 요소</span><span class="sxs-lookup"><span data-stu-id="7884c-102">&lt;oidMap&gt; Element</span></span>
<span data-ttu-id="7884c-103">ASN.1 클래스 개체 식별자 (OID) 매핑이 들어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7884c-103">Contains ASN.1 object identifier (OID) mappings to classes.</span></span>  
  
 <span data-ttu-id="7884c-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="7884c-104">\<configuration></span></span>  
<span data-ttu-id="7884c-105">\<mscorlib ></span><span class="sxs-lookup"><span data-stu-id="7884c-105">\<mscorlib></span></span>  
<span data-ttu-id="7884c-106">\<cryptographySettings ></span><span class="sxs-lookup"><span data-stu-id="7884c-106">\<cryptographySettings></span></span>  
<span data-ttu-id="7884c-107">\<oidMap ></span><span class="sxs-lookup"><span data-stu-id="7884c-107">\<oidMap></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7884c-108">구문</span><span class="sxs-lookup"><span data-stu-id="7884c-108">Syntax</span></span>  
  
```xml  
<oidMap>   
</oidMap>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="7884c-109">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="7884c-109">Attributes and Elements</span></span>  
 <span data-ttu-id="7884c-110">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="7884c-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="7884c-111">특성</span><span class="sxs-lookup"><span data-stu-id="7884c-111">Attributes</span></span>  
 <span data-ttu-id="7884c-112">없음</span><span class="sxs-lookup"><span data-stu-id="7884c-112">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="7884c-113">자식 요소</span><span class="sxs-lookup"><span data-stu-id="7884c-113">Child Elements</span></span>  
  
|<span data-ttu-id="7884c-114">요소</span><span class="sxs-lookup"><span data-stu-id="7884c-114">Element</span></span>|<span data-ttu-id="7884c-115">설명</span><span class="sxs-lookup"><span data-stu-id="7884c-115">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="7884c-116">\<oidEntry ></span><span class="sxs-lookup"><span data-stu-id="7884c-116">\<oidEntry></span></span>](../../../../../docs/framework/configure-apps/file-schema/cryptography/oidentry-element.md)|<span data-ttu-id="7884c-117">ASN.1 OID 이름에 매핑됩니다.</span><span class="sxs-lookup"><span data-stu-id="7884c-117">Maps an ASN.1 OID to a friendly name.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="7884c-118">부모 요소</span><span class="sxs-lookup"><span data-stu-id="7884c-118">Parent Elements</span></span>  
  
|<span data-ttu-id="7884c-119">요소</span><span class="sxs-lookup"><span data-stu-id="7884c-119">Element</span></span>|<span data-ttu-id="7884c-120">설명</span><span class="sxs-lookup"><span data-stu-id="7884c-120">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="7884c-121">공용 언어 런타임 및 .NET Framework 응용 프로그램에서 사용하는 모든 구성 파일의 루트 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="7884c-121">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`cryptographySettings`|<span data-ttu-id="7884c-122">암호화 설정이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7884c-122">Contains cryptography settings.</span></span>|  
|`mscorlib`|<span data-ttu-id="7884c-123">포함 된 `cryptographySettings` 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="7884c-123">Contains the `cryptographySettings` element.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="7884c-124">예제</span><span class="sxs-lookup"><span data-stu-id="7884c-124">Example</span></span>  
 <span data-ttu-id="7884c-125">다음 예제에서는 사용 하는 방법을 보여 줍니다 합니다  **\<oidMap >** 해당 해시 알고리즘의 구현에 RIPEMD-160 해시 알고리즘의 OID의 매핑을 포함 하는 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="7884c-125">The following example shows how to use the **\<oidMap>** element to contain a mapping of an OID for the RIPEMD-160 hash algorithm to an implementation of that hash algorithm.</span></span>  
  
```xml  
<configuration>  
   <mscorlib>  
      <cryptographySettings>  
         <cryptoNameMapping>  
            <cryptoClasses>  
               <cryptoClass   MyCrypto="MyCryptoClass, MyAssembly  
                  Culture=neutral, PublicKeyToken=a5d015c7d5a0b012,  
                  Version=1.0.0.0"/>  
            </cryptoClasses>  
            <nameEntry name="RIPEMD-160" class="MyCrypto"/>  
         </cryptoNameMapping>  
         <oidMap>  
            <oidEntry OID="1.3.36.3.2.1"  name="MyCryptoClass"/>  
         </oidMap>  
      </cryptographySettings>  
   </mscorlib>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="7884c-126">참고 항목</span><span class="sxs-lookup"><span data-stu-id="7884c-126">See Also</span></span>  
- [<span data-ttu-id="7884c-127">구성 파일 스키마</span><span class="sxs-lookup"><span data-stu-id="7884c-127">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)  
- [<span data-ttu-id="7884c-128">암호화 설정 스키마</span><span class="sxs-lookup"><span data-stu-id="7884c-128">Cryptography Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/cryptography/index.md)  
- [<span data-ttu-id="7884c-129">Cryptographic Services</span><span class="sxs-lookup"><span data-stu-id="7884c-129">Cryptographic Services</span></span>](../../../../../docs/standard/security/cryptographic-services.md)  
- [<span data-ttu-id="7884c-130">암호화 클래스 구성</span><span class="sxs-lookup"><span data-stu-id="7884c-130">Configuring Cryptography Classes</span></span>](../../../../../docs/framework/configure-apps/configure-cryptography-classes.md)  
- [<span data-ttu-id="7884c-131">개체 식별자를 암호화 알고리즘에 매핑</span><span class="sxs-lookup"><span data-stu-id="7884c-131">Mapping Object Identifiers to Cryptography Algorithms</span></span>](../../../../../docs/framework/configure-apps/map-object-identifiers-to-cryptography-algorithms.md)
