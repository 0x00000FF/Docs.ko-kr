---
title: "인코딩된 SOAP Serialization을 제어하는 특성"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- SOAP, XML serialization
- XML serialization, SOAP
- XML serialization, attributes
- attributes [.NET Framework], XML serialization
- serialization, attributes
ms.assetid: 93ee258c-9c0f-4a08-897c-c10db7a00f91
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: ae3193a2f9ef01f8e7f71235f15ed070e84ec11c
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/23/2017
---
# <a name="attributes-that-control-encoded-soap-serialization"></a><span data-ttu-id="86e26-102">인코딩된 SOAP Serialization을 제어하는 특성</span><span class="sxs-lookup"><span data-stu-id="86e26-102">Attributes That Control Encoded SOAP Serialization</span></span> 
<span data-ttu-id="86e26-103">World Wide Web 컨소시엄(www.w3.org) 문서 “SOAP(Simple Object Access Protocol) 1.1”에는 SOAP 매개 변수를 인코딩할 수 있는 방법을 설명하는 선택적 단원(5단원)이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="86e26-103">The World Wide Web Consortium (www.w3.org) document named "Simple Object Access Protocol (SOAP) 1.1" contains an optional section (section 5) that describes how SOAP parameters can be encoded.</span></span> <span data-ttu-id="86e26-104">사양의 5단원을 따르려면 <xref:System.Xml.Serialization> 네임스페이스에 속한 특별한 특성 집합을 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="86e26-104">To conform to section 5 of the specification, you must use a special set of attributes found in the <xref:System.Xml.Serialization> namespace.</span></span> <span data-ttu-id="86e26-105">이러한 특성을 클래스 및 클래스 멤버에 적절하게 적용한 다음 <xref:System.Xml.Serialization.XmlSerializer>를 사용하여 클래스의 인스턴스를 serialize합니다.</span><span class="sxs-lookup"><span data-stu-id="86e26-105">Apply those attributes as appropriate to classes and members of classes, and then use the <xref:System.Xml.Serialization.XmlSerializer> to serialize instances of the class or classes.</span></span>  
  
 <span data-ttu-id="86e26-106">다음 표에서는 특성, 해당 특성을 적용할 수 있는 위치 및 해당 특성이 수행하는 작업을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="86e26-106">The following table shows the attributes, where they can be applied, and what they do.</span></span> <span data-ttu-id="86e26-107">이러한 특성을 사용하여 XML serialization을 제어하는 방법에 대한 자세한 내용은 [방법: 개체를 SOAP 인코드된 XML 스트림으로 직렬화](../../../docs/standard/serialization/how-to-serialize-an-object-as-a-soap-encoded-xml-stream.md) 및 [방법: 인코드된 SOAP XML Serialization 재정의](../../../docs/standard/serialization/how-to-override-encoded-soap-xml-serialization.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="86e26-107">For more information about using these attributes to control XML serialization, see [How to: Serialize an Object as a SOAP-Encoded XML Stream](../../../docs/standard/serialization/how-to-serialize-an-object-as-a-soap-encoded-xml-stream.md) and [How to: Override Encoded SOAP XML Serialization](../../../docs/standard/serialization/how-to-override-encoded-soap-xml-serialization.md).</span></span>  
  
 <span data-ttu-id="86e26-108">특성에 대한 자세한 내용은 [특성](../../../docs/standard/attributes/index.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="86e26-108">For more information about attributes, see [Attributes](../../../docs/standard/attributes/index.md).</span></span>  
  
|<span data-ttu-id="86e26-109">특성</span><span class="sxs-lookup"><span data-stu-id="86e26-109">Attribute</span></span>|<span data-ttu-id="86e26-110">적용 대상</span><span class="sxs-lookup"><span data-stu-id="86e26-110">Applies to</span></span>|<span data-ttu-id="86e26-111">설명</span><span class="sxs-lookup"><span data-stu-id="86e26-111">Specifies</span></span>|  
|---------------|----------------|---------------|  
|<xref:System.Xml.Serialization.SoapAttributeAttribute>|<span data-ttu-id="86e26-112">public 필드, 속성, 매개 변수 또는 반환 값입니다.</span><span class="sxs-lookup"><span data-stu-id="86e26-112">Public field, property, parameter, or return value.</span></span>|<span data-ttu-id="86e26-113">클래스 멤버는 XML 특성으로 serialize됩니다.</span><span class="sxs-lookup"><span data-stu-id="86e26-113">The class member will be serialized as an XML attribute.</span></span>|  
|<xref:System.Xml.Serialization.SoapElementAttribute>|<span data-ttu-id="86e26-114">public 필드, 속성, 매개 변수 또는 반환 값입니다.</span><span class="sxs-lookup"><span data-stu-id="86e26-114">Public field, property, parameter, or return value.</span></span>|<span data-ttu-id="86e26-115">클래스는 XML 요소로 serialize됩니다.</span><span class="sxs-lookup"><span data-stu-id="86e26-115">The class will be serialized as an XML element.</span></span>|  
|<xref:System.Xml.Serialization.SoapEnumAttribute>|<span data-ttu-id="86e26-116">열거형 식별자인 public 필드입니다.</span><span class="sxs-lookup"><span data-stu-id="86e26-116">Public field that is an enumeration identifier.</span></span>|<span data-ttu-id="86e26-117">열거형 멤버의 요소 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="86e26-117">The element name of an enumeration member.</span></span>|  
|<xref:System.Xml.Serialization.SoapIgnoreAttribute>|<span data-ttu-id="86e26-118">public 속성 및 필드입니다.</span><span class="sxs-lookup"><span data-stu-id="86e26-118">Public properties and fields.</span></span>|<span data-ttu-id="86e26-119">속성 또는 필드는 포함 클래스가 serialize될 때 무시되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="86e26-119">The property or field should be ignored when the containing class is serialized.</span></span>|  
|<xref:System.Xml.Serialization.SoapIncludeAttribute>|<span data-ttu-id="86e26-120">WSDL(웹 서비스 설명 언어) 문서에 대한 공용 파생 클래스 선언 및 공용 메서드입니다.</span><span class="sxs-lookup"><span data-stu-id="86e26-120">Public-derived class declarations and public methods for Web Services Description Language (WSDL) documents.</span></span>|<span data-ttu-id="86e26-121">스키마를 생성할 때 형식을 포함해야 합니다(serialize될 때 인식되도록).</span><span class="sxs-lookup"><span data-stu-id="86e26-121">The type should be included when generating schemas (to be recognized when serialized).</span></span>|  
|<xref:System.Xml.Serialization.SoapTypeAttribute>|<span data-ttu-id="86e26-122">public 클래스 선언입니다.</span><span class="sxs-lookup"><span data-stu-id="86e26-122">Public class declarations.</span></span>|<span data-ttu-id="86e26-123">클래스는 XML 형식으로 serialize되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="86e26-123">The class should be serialized as an XML type.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="86e26-124">참고 항목</span><span class="sxs-lookup"><span data-stu-id="86e26-124">See Also</span></span>  
 [<span data-ttu-id="86e26-125">XML 및 SOAP serialization</span><span class="sxs-lookup"><span data-stu-id="86e26-125">XML and SOAP Serialization</span></span>](../../../docs/standard/serialization/xml-and-soap-serialization.md)  
 [<span data-ttu-id="86e26-126">방법: 개체를 SOAP 인코딩된 XML 스트림으로 직렬화</span><span class="sxs-lookup"><span data-stu-id="86e26-126">How to: Serialize an Object as a SOAP-Encoded XML Stream</span></span>](../../../docs/standard/serialization/how-to-serialize-an-object-as-a-soap-encoded-xml-stream.md)  
 [<span data-ttu-id="86e26-127">방법: 인코딩된 SOAP XML serialization 재정의</span><span class="sxs-lookup"><span data-stu-id="86e26-127">How to: Override Encoded SOAP XML Serialization</span></span>](../../../docs/standard/serialization/how-to-override-encoded-soap-xml-serialization.md)  
 [<span data-ttu-id="86e26-128">특성</span><span class="sxs-lookup"><span data-stu-id="86e26-128">Attributes</span></span>](../../../docs/standard/attributes/index.md)  
 <xref:System.Xml.Serialization.XmlSerializer>  
 [<span data-ttu-id="86e26-129">방법: 개체 직렬화</span><span class="sxs-lookup"><span data-stu-id="86e26-129">How to: Serialize an Object</span></span>](../../../docs/standard/serialization/how-to-serialize-an-object.md)  
 [<span data-ttu-id="86e26-130">방법: 개체 deserialize</span><span class="sxs-lookup"><span data-stu-id="86e26-130">How to: Deserialize an Object</span></span>](../../../docs/standard/serialization/how-to-deserialize-an-object.md)
