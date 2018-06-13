---
title: '&lt;메타 데이터&gt;'
ms.date: 03/30/2017
ms.assetid: d09653eb-e355-4c73-b87b-28f93d56480d
ms.openlocfilehash: 7e314ae56ed7a1b532bb8946fbb28802e72d3e20
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32747855"
---
# <a name="ltmetadatagt"></a><span data-ttu-id="f3904-102">&lt;메타 데이터&gt;</span><span class="sxs-lookup"><span data-stu-id="f3904-102">&lt;metadata&gt;</span></span>
<span data-ttu-id="f3904-103">서비스 메타데이터를 처리할 수 있는 방법을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="f3904-103">Specifies how service metadata can be processed.</span></span>  
  
 <span data-ttu-id="f3904-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="f3904-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="f3904-105">\<client></span><span class="sxs-lookup"><span data-stu-id="f3904-105">\<client></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f3904-106">구문</span><span class="sxs-lookup"><span data-stu-id="f3904-106">Syntax</span></span>  
  
```xml  
<system.serviceModel>  
    <client>  
        <metadata>  
                   <policyImporters>  
                          <policyImporter type="string" />  
                   </policyImporters  
                 <wsdlImporters>  
                      <wsdlImporter type="string" />  
                 </wsdlImporters>  
        </metadata>  
    </client>  
</system.serviceModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f3904-107">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="f3904-107">Attributes and Elements</span></span>  
 <span data-ttu-id="f3904-108">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="f3904-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f3904-109">특성</span><span class="sxs-lookup"><span data-stu-id="f3904-109">Attributes</span></span>  
 <span data-ttu-id="f3904-110">없음</span><span class="sxs-lookup"><span data-stu-id="f3904-110">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="f3904-111">자식 요소</span><span class="sxs-lookup"><span data-stu-id="f3904-111">Child Elements</span></span>  
  
|<span data-ttu-id="f3904-112">요소</span><span class="sxs-lookup"><span data-stu-id="f3904-112">Element</span></span>|<span data-ttu-id="f3904-113">설명</span><span class="sxs-lookup"><span data-stu-id="f3904-113">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="f3904-114">\<policyImporters ></span><span class="sxs-lookup"><span data-stu-id="f3904-114">\<policyImporters></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/policyimporters.md)|<span data-ttu-id="f3904-115">바인딩에 대한 사용자 지정 정책 어설션의 가져오기를 제어하는 모든 정책 가져오기를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="f3904-115">Specifies all the policy importers that control the import of custom policy assertions about bindings.</span></span> <span data-ttu-id="f3904-116">정책 가져오기는, 바인딩 기능에 대한 사용자 지정 정책 어설션을 검색하거나 어설션에서 요구하는 기능을 구현하는 사용자 지정 바인딩 요소를 연결하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="f3904-116">A policy importer is used to search custom policy assertions about binding features, as well as attach a custom binding element that implements the features the assertion requires.</span></span>|  
|[<span data-ttu-id="f3904-117">\<wsdlImporters ></span><span class="sxs-lookup"><span data-stu-id="f3904-117">\<wsdlImporters></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/wsdlimporters.md)|<span data-ttu-id="f3904-118">WS-Policy 첨부 파일과 함께 WSDL(웹 서비스 기술 언어) 1.1 메타데이터를 가져오는 모든 WSDL 가져오기를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="f3904-118">Specifies all the WSDL importers that import Web Services Description Language (WSDL) 1.1 metadata with WS-Policy attachments.</span></span> <span data-ttu-id="f3904-119">WSDL 가져오기는 메타데이터를 가져오고 그 정보를 계약 및 끝점 정보를 나타내는 다양한 클래스로 변환하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="f3904-119">A WSDL importer is used to import metadata as well as convert that information into various classes that represent contract and endpoint information.</span></span> <span data-ttu-id="f3904-120">가져오기 오류를 공개하는 속성 및 계약과 끝점 정보를 가져오고, 가져오기 및 변환 프로세스와 관련된 형식 정보를 받을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f3904-120">It can selectively import contract and endpoint information and properties that expose any import errors and accept type information relevant to the import and conversion process.</span></span> <span data-ttu-id="f3904-121">또한 정책 문서, WSDL 문서, WSDL 확장명 및 XML 스키마 문서에 대한 액세스를 제공하는 바인딩 정보와 속성의 가져오기도 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="f3904-121">It also supports importing binding information and properties that provide access to any policy documents, WSDL documents, WSDL extensions, and XML schema documents.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="f3904-122">부모 요소</span><span class="sxs-lookup"><span data-stu-id="f3904-122">Parent Elements</span></span>  
  
|<span data-ttu-id="f3904-123">요소</span><span class="sxs-lookup"><span data-stu-id="f3904-123">Element</span></span>|<span data-ttu-id="f3904-124">설명</span><span class="sxs-lookup"><span data-stu-id="f3904-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="f3904-125">\<클라이언트 ></span><span class="sxs-lookup"><span data-stu-id="f3904-125">\<client></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/client.md)|<span data-ttu-id="f3904-126">클라이언트 섹션은 클라이언트가 연결할 수 있는 끝점 목록을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="f3904-126">The client section defines a list of endpoints that a client can connect to.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="f3904-127">참고 항목</span><span class="sxs-lookup"><span data-stu-id="f3904-127">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.MetadataElement>  
 <xref:System.ServiceModel.Configuration.PolicyImporterElementCollection>  
 <xref:System.ServiceModel.Configuration.WsdlImporterElementCollection>  
 <xref:System.ServiceModel.Description.MetadataImporter>  
 <xref:System.ServiceModel.Description.WsdlImporter>  
 [<span data-ttu-id="f3904-128">WCF 클라이언트 구성</span><span class="sxs-lookup"><span data-stu-id="f3904-128">WCF Client Configuration</span></span>](../../../../../docs/framework/wcf/feature-details/client-configuration.md)  
 [<span data-ttu-id="f3904-129">클라이언트</span><span class="sxs-lookup"><span data-stu-id="f3904-129">Clients</span></span>](../../../../../docs/framework/wcf/feature-details/clients.md)
