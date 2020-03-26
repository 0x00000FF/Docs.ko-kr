---
title: <xmlSerializer> 요소
ms.date: 03/30/2017
helpviewer_keywords:
- <xmlSerializer> element
- XML serialization, configuration
- xmlSerializer element
ms.assetid: d129d10c-3eb7-45d9-8098-5fa853825e47
ms.openlocfilehash: b83ecda30bba8af1f3175eb6ad08593b07a80e6c
ms.sourcegitcommit: 99b153b93bf94d0fecf7c7bcecb58ac424dfa47c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/25/2020
ms.locfileid: "80249541"
---
# <a name="xmlserializer-element"></a><span data-ttu-id="f1e98-102">\<xml 직렬화기> 요소</span><span class="sxs-lookup"><span data-stu-id="f1e98-102">\<xmlSerializer> Element</span></span>
<span data-ttu-id="f1e98-103"><xref:System.Xml.Serialization.XmlSerializer>의 진행에 대한 추가 검사가 수행되었는지 여부를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="f1e98-103">Specifies whether an additional check of progress of the <xref:System.Xml.Serialization.XmlSerializer> is done.</span></span>  
  
 <span data-ttu-id="f1e98-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="f1e98-104">\<configuration></span></span>  
<span data-ttu-id="f1e98-105">\<system.xml.serialization></span><span class="sxs-lookup"><span data-stu-id="f1e98-105">\<system.xml.serialization></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f1e98-106">구문</span><span class="sxs-lookup"><span data-stu-id="f1e98-106">Syntax</span></span>  
  
```xml  
<xmlSerializer checkDeserializerAdvance = "true|false" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f1e98-107">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="f1e98-107">Attributes and Elements</span></span>  
 <span data-ttu-id="f1e98-108">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="f1e98-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f1e98-109">특성</span><span class="sxs-lookup"><span data-stu-id="f1e98-109">Attributes</span></span>  
  
|<span data-ttu-id="f1e98-110">특성</span><span class="sxs-lookup"><span data-stu-id="f1e98-110">Attribute</span></span>|<span data-ttu-id="f1e98-111">설명</span><span class="sxs-lookup"><span data-stu-id="f1e98-111">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="f1e98-112">**checkDeserializeAdvances**</span><span class="sxs-lookup"><span data-stu-id="f1e98-112">**checkDeserializeAdvances**</span></span>|<span data-ttu-id="f1e98-113"><xref:System.Xml.Serialization.XmlSerializer>의 진행률이 검사되었는지 여부를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="f1e98-113">Specifies whether the progress of the <xref:System.Xml.Serialization.XmlSerializer> is checked.</span></span> <span data-ttu-id="f1e98-114">특성을 "true" 또는 "false"로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="f1e98-114">Set the attribute to "true" or "false".</span></span> <span data-ttu-id="f1e98-115">기본값은 "true"입니다.</span><span class="sxs-lookup"><span data-stu-id="f1e98-115">The default is "true".</span></span>|  
|<span data-ttu-id="f1e98-116">**useLegacySerializationGeneration**</span><span class="sxs-lookup"><span data-stu-id="f1e98-116">**useLegacySerializationGeneration**</span></span>|<span data-ttu-id="f1e98-117"><xref:System.Xml.Serialization.XmlSerializer>가 C# 코드를 파일에 쓴 다음 어셈블리로 컴파일하여 어셈블리를 생성하는 레거시 serialization 생성을 사용하는지 여부를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="f1e98-117">Specifies whether the <xref:System.Xml.Serialization.XmlSerializer> uses legacy serialization generation which generates assemblies by writing C# code to a file and then compiling it to an assembly.</span></span> <span data-ttu-id="f1e98-118">기본값은 **false입니다.**</span><span class="sxs-lookup"><span data-stu-id="f1e98-118">The default is **false**.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="f1e98-119">자식 요소</span><span class="sxs-lookup"><span data-stu-id="f1e98-119">Child Elements</span></span>  
 <span data-ttu-id="f1e98-120">없음</span><span class="sxs-lookup"><span data-stu-id="f1e98-120">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="f1e98-121">부모 요소</span><span class="sxs-lookup"><span data-stu-id="f1e98-121">Parent Elements</span></span>  
  
|<span data-ttu-id="f1e98-122">요소</span><span class="sxs-lookup"><span data-stu-id="f1e98-122">Element</span></span>|<span data-ttu-id="f1e98-123">설명</span><span class="sxs-lookup"><span data-stu-id="f1e98-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="f1e98-124">\<시스템.xml.직렬화> 요소</span><span class="sxs-lookup"><span data-stu-id="f1e98-124">\<system.xml.serialization> Element</span></span>](../../../docs/standard/serialization/system-xml-serialization-element.md)|<span data-ttu-id="f1e98-125"><xref:System.Xml.Serialization.XmlSerializer> 및 <xref:System.Xml.Serialization.XmlSchemaImporter> 클래스에 대한 구성 설정을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="f1e98-125">Contains configuration settings for the <xref:System.Xml.Serialization.XmlSerializer> and <xref:System.Xml.Serialization.XmlSchemaImporter> classes.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f1e98-126">설명</span><span class="sxs-lookup"><span data-stu-id="f1e98-126">Remarks</span></span>  
 <span data-ttu-id="f1e98-127">기본적으로 <xref:System.Xml.Serialization.XmlSerializer>는 신뢰할 수 없는 데이터를 역직렬화할 때 잠재적 서비스 거부 공격에 대한 추가 보안 계층을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="f1e98-127">By default, the <xref:System.Xml.Serialization.XmlSerializer> provides an additional layer of security against potential denial of service attacks when deserializing untrusted data.</span></span> <span data-ttu-id="f1e98-128">deserialization 도중 무한 루프의 탐지를 시도하여 이러한 보안을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="f1e98-128">It does so by attempting to detect infinite loops during deserialization.</span></span> <span data-ttu-id="f1e98-129">이러한 조건이 발견되면 “내부 오류: 내부 스트림으로 진행하지 못하여 deserialization하지 못했습니다”라는 메시지와 함께 예외가 throw됩니다.</span><span class="sxs-lookup"><span data-stu-id="f1e98-129">If such a condition is detected, an exception is thrown with the following message: "Internal error: deserialization failed to advance over underlying stream."</span></span>  
  
 <span data-ttu-id="f1e98-130">이 메시지가 반드시 서비스 거부 공격이 진행 중임을 의미하는 것은 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="f1e98-130">Receiving this message does not necessarily indicate that a denial of service attack is in progress.</span></span> <span data-ttu-id="f1e98-131">드문 경우지만 무한 루프 검색 메커니즘이 가양성(false positive)을 생성하여 적법한 들어오는 메시지에 대해 예외가 throw될 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f1e98-131">In some rare circumstances, the infinite loop detection mechanism produces a false positive and the exception is thrown for a legitimate incoming message.</span></span> <span data-ttu-id="f1e98-132">특정 애플리케이션에서 적법한 메시지가 이러한 추가 보호 계층에 의해 거부된 경우 **checkDeserializeAdvances** 특성을 “false”로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="f1e98-132">If you find that in your particular application legitimate messages are being rejected by this extra layer of protection, set **checkDeserializeAdvances** attribute to "false".</span></span>  
  
## <a name="example"></a><span data-ttu-id="f1e98-133">예제</span><span class="sxs-lookup"><span data-stu-id="f1e98-133">Example</span></span>  
 <span data-ttu-id="f1e98-134">다음 코드 예제에서는 **checkDeserializeAdvances** 특성을 “false”로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="f1e98-134">The following code example sets the **checkDeserializeAdvances** attribute to "false".</span></span>  
  
```xml  
<configuration>  
  <system.xml.serialization>  
    <xmlSerializer checkDeserializeAdvances="false" />  
  </system.xml.serialization>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="f1e98-135">참조</span><span class="sxs-lookup"><span data-stu-id="f1e98-135">See also</span></span>

- <xref:System.Xml.Serialization.XmlSerializer>
- [<span data-ttu-id="f1e98-136">\<시스템.xml.직렬화> 요소</span><span class="sxs-lookup"><span data-stu-id="f1e98-136">\<system.xml.serialization> Element</span></span>](../../../docs/standard/serialization/system-xml-serialization-element.md)
- [<span data-ttu-id="f1e98-137">XML 및 SOAP Serialization</span><span class="sxs-lookup"><span data-stu-id="f1e98-137">XML and SOAP Serialization</span></span>](../../../docs/standard/serialization/xml-and-soap-serialization.md)
