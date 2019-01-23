---
title: '&lt;oidEntry&gt; Element'
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/mscorlib/cryptographySettings/oidMap/oidEntry
- http://schemas.microsoft.com/.NetConfiguration/v2.0#oidEntry
helpviewer_keywords:
- <oidEntry> element
- oidEntry element
ms.assetid: 22fb88b0-bf27-489c-9ca0-e65950ac136c
author: mcleblanc
ms.author: markl
ms.openlocfilehash: c891b5d67c7f2ef46682233ad555a1276f8e027d
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54606902"
---
# <a name="ltoidentrygt-element"></a><span data-ttu-id="ee50b-102">&lt;oidEntry&gt; Element</span><span class="sxs-lookup"><span data-stu-id="ee50b-102">&lt;oidEntry&gt; Element</span></span>
<span data-ttu-id="ee50b-103">ASN.1 OID(개체 식별자)를 이름에 매핑합니다.</span><span class="sxs-lookup"><span data-stu-id="ee50b-103">Maps an ASN.1 object identifier (OID) to a friendly name.</span></span>  
  
 <span data-ttu-id="ee50b-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="ee50b-104">\<configuration></span></span>  
<span data-ttu-id="ee50b-105">\<mscorlib></span><span class="sxs-lookup"><span data-stu-id="ee50b-105">\<mscorlib></span></span>  
<span data-ttu-id="ee50b-106">\<cryptographySettings></span><span class="sxs-lookup"><span data-stu-id="ee50b-106">\<cryptographySettings></span></span>  
<span data-ttu-id="ee50b-107">\<oidMap></span><span class="sxs-lookup"><span data-stu-id="ee50b-107">\<oidMap></span></span>  
<span data-ttu-id="ee50b-108">\<oidEntry></span><span class="sxs-lookup"><span data-stu-id="ee50b-108">\<oidEntry></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ee50b-109">구문</span><span class="sxs-lookup"><span data-stu-id="ee50b-109">Syntax</span></span>  
  
```xml  
<oidEntry OID="object identifier number" name="friendly name" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ee50b-110">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="ee50b-110">Attributes and Elements</span></span>  
 <span data-ttu-id="ee50b-111">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="ee50b-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ee50b-112">특성</span><span class="sxs-lookup"><span data-stu-id="ee50b-112">Attributes</span></span>  
  
|<span data-ttu-id="ee50b-113">특성</span><span class="sxs-lookup"><span data-stu-id="ee50b-113">Attribute</span></span>|<span data-ttu-id="ee50b-114">설명</span><span class="sxs-lookup"><span data-stu-id="ee50b-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="ee50b-115">**OID**</span><span class="sxs-lookup"><span data-stu-id="ee50b-115">**OID**</span></span>|<span data-ttu-id="ee50b-116">필수 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="ee50b-116">Required attribute.</span></span><br /><br /> <span data-ttu-id="ee50b-117">클래스에서 구현 되는 알고리즘에 해당 하는 ASN.1 OID를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="ee50b-117">Specifies the ASN.1 OID corresponding to the algorithm implemented by your class.</span></span>|  
|<span data-ttu-id="ee50b-118">**name**</span><span class="sxs-lookup"><span data-stu-id="ee50b-118">**name**</span></span>|<span data-ttu-id="ee50b-119">필수 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="ee50b-119">Required attribute.</span></span><br /><br /> <span data-ttu-id="ee50b-120">에 대 한 값을 지정 합니다 **이름** 특성을 [ \<nameEntry >](../../../../../docs/framework/configure-apps/file-schema/cryptography/nameentry-element.md) 태그 합니다.</span><span class="sxs-lookup"><span data-stu-id="ee50b-120">Specifies the value for the **name** attribute in the [\<nameEntry>](../../../../../docs/framework/configure-apps/file-schema/cryptography/nameentry-element.md) tag.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="ee50b-121">자식 요소</span><span class="sxs-lookup"><span data-stu-id="ee50b-121">Child Elements</span></span>  
 <span data-ttu-id="ee50b-122">없음</span><span class="sxs-lookup"><span data-stu-id="ee50b-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="ee50b-123">부모 요소</span><span class="sxs-lookup"><span data-stu-id="ee50b-123">Parent Elements</span></span>  
  
|<span data-ttu-id="ee50b-124">요소</span><span class="sxs-lookup"><span data-stu-id="ee50b-124">Element</span></span>|<span data-ttu-id="ee50b-125">설명</span><span class="sxs-lookup"><span data-stu-id="ee50b-125">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="ee50b-126">공용 언어 런타임 및 .NET Framework 애플리케이션에서 사용하는 모든 구성 파일의 루트 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="ee50b-126">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`cryptographySettings`|<span data-ttu-id="ee50b-127">암호화 설정이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ee50b-127">Contains cryptography settings.</span></span>|  
|`mscorlib`|<span data-ttu-id="ee50b-128">포함 된 `cryptographySettings` 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="ee50b-128">Contains the `cryptographySettings` element.</span></span>|  
|`oidMap`|<span data-ttu-id="ee50b-129">ASN.1 클래스 개체 식별자 (OID) 매핑이 들어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ee50b-129">Contains ASN.1 object identifier (OID) mappings to classes.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ee50b-130">설명</span><span class="sxs-lookup"><span data-stu-id="ee50b-130">Remarks</span></span>  
 <span data-ttu-id="ee50b-131">ASN.1 개체 식별자는 일부 암호화 형식에서 알고리즘을 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="ee50b-131">ASN.1 object identifiers identify algorithms in some cryptographic formats.</span></span> <span data-ttu-id="ee50b-132">개체 식별자를 식별 하려면 알고리즘 이름을 매핑하십시오.</span><span class="sxs-lookup"><span data-stu-id="ee50b-132">Map object identifiers to friendly names for the algorithms you want to identify.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ee50b-133">예제</span><span class="sxs-lookup"><span data-stu-id="ee50b-133">Example</span></span>  
 <span data-ttu-id="ee50b-134">다음 예제에서는 사용 하는 방법을 보여 줍니다 합니다  **\<oidEntry >** RIPEMD-160 해시 알고리즘에 대 한 개체 식별자는 해시 알고리즘의 구현에 매핑하는 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="ee50b-134">The following example shows how to use the **\<oidEntry>** element to map an object identifier for the RIPEMD-160 hash algorithm to an implementation of that hash algorithm.</span></span>  
  
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
            <oidEntry OID="1.3.36.3.2.1"   name="MyCryptoClass"/>  
         </oidMap>  
      </cryptographySettings>  
   </mscorlib>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="ee50b-135">참고자료</span><span class="sxs-lookup"><span data-stu-id="ee50b-135">See also</span></span>
- [<span data-ttu-id="ee50b-136">구성 파일 스키마</span><span class="sxs-lookup"><span data-stu-id="ee50b-136">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)
- [<span data-ttu-id="ee50b-137">암호화 설정 스키마</span><span class="sxs-lookup"><span data-stu-id="ee50b-137">Cryptography Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/cryptography/index.md)
- [<span data-ttu-id="ee50b-138">Cryptographic Services</span><span class="sxs-lookup"><span data-stu-id="ee50b-138">Cryptographic Services</span></span>](../../../../../docs/standard/security/cryptographic-services.md)
- [<span data-ttu-id="ee50b-139">암호화 클래스 구성</span><span class="sxs-lookup"><span data-stu-id="ee50b-139">Configuring Cryptography Classes</span></span>](../../../../../docs/framework/configure-apps/configure-cryptography-classes.md)
- [<span data-ttu-id="ee50b-140">개체 식별자를 암호화 알고리즘에 매핑</span><span class="sxs-lookup"><span data-stu-id="ee50b-140">Mapping Object Identifiers to Cryptography Algorithms</span></span>](../../../../../docs/framework/configure-apps/map-object-identifiers-to-cryptography-algorithms.md)
