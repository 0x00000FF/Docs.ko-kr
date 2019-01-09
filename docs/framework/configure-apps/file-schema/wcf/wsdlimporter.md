---
title: '&lt;wsdlImporter&gt;'
ms.date: 03/30/2017
ms.assetid: 986b2165-8430-4dba-b1b8-00396841bb96
ms.openlocfilehash: 43c1a50c740cd9c75ee641e4ac4d0fa8ea3ca36b
ms.sourcegitcommit: 4ac80713f6faa220e5a119d5165308a58f7ccdc8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/09/2019
ms.locfileid: "54144992"
---
# <a name="ltwsdlimportergt"></a><span data-ttu-id="b0188-102">&lt;wsdlImporter&gt;</span><span class="sxs-lookup"><span data-stu-id="b0188-102">&lt;wsdlImporter&gt;</span></span>
<span data-ttu-id="b0188-103">WS-Policy 첨부 파일과 함께 WSDL(웹 서비스 기술 언어) 1.1 메타데이터를 가져오는 모든 WSDL 가져오기를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="b0188-103">Specifies all the WSDL importers that imports Web Services Description Language (WSDL) 1.1 metadata with WS-Policy attachments.</span></span>  
  
<span data-ttu-id="b0188-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="b0188-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="b0188-105">\<client></span><span class="sxs-lookup"><span data-stu-id="b0188-105">\<client></span></span>  
<span data-ttu-id="b0188-106">\<메타 데이터 ></span><span class="sxs-lookup"><span data-stu-id="b0188-106">\<metadata></span></span>  
<span data-ttu-id="b0188-107">\<wsdlImporters ></span><span class="sxs-lookup"><span data-stu-id="b0188-107">\<wsdlImporters></span></span>  
<span data-ttu-id="b0188-108">\<wsdlImporter ></span><span class="sxs-lookup"><span data-stu-id="b0188-108">\<wsdlImporter></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b0188-109">구문</span><span class="sxs-lookup"><span data-stu-id="b0188-109">Syntax</span></span>  
  
```xml  
<metadata>
  <wsdlImporters>
    <wsdlImporter type="string" />
  </wsdlImporters>
</metadata>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b0188-110">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="b0188-110">Attributes and Elements</span></span>  
 <span data-ttu-id="b0188-111">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="b0188-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b0188-112">특성</span><span class="sxs-lookup"><span data-stu-id="b0188-112">Attributes</span></span>  
  
|<span data-ttu-id="b0188-113">특성</span><span class="sxs-lookup"><span data-stu-id="b0188-113">Attribute</span></span>|<span data-ttu-id="b0188-114">설명</span><span class="sxs-lookup"><span data-stu-id="b0188-114">Description</span></span>|  
|---------------|-----------------|  
|`type`|<span data-ttu-id="b0188-115">이 요소의 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="b0188-115">The type of this element.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="b0188-116">자식 요소</span><span class="sxs-lookup"><span data-stu-id="b0188-116">Child Elements</span></span>  
 <span data-ttu-id="b0188-117">없음</span><span class="sxs-lookup"><span data-stu-id="b0188-117">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="b0188-118">부모 요소</span><span class="sxs-lookup"><span data-stu-id="b0188-118">Parent Elements</span></span>  
  
|<span data-ttu-id="b0188-119">요소</span><span class="sxs-lookup"><span data-stu-id="b0188-119">Element</span></span>|<span data-ttu-id="b0188-120">설명</span><span class="sxs-lookup"><span data-stu-id="b0188-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="b0188-121">\<wsdlImporters ></span><span class="sxs-lookup"><span data-stu-id="b0188-121">\<wsdlImporters></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/wsdlimporters.md)|<span data-ttu-id="b0188-122">WS-Policy 첨부 파일과 함께 WSDL(웹 서비스 기술 언어) 1.1 메타데이터를 가져오는 모든 WSDL 가져오기를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="b0188-122">Specifies all the WSDL importers that imports Web Services Description Language (WSDL) 1.1 metadata with WS-Policy attachments.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b0188-123">설명</span><span class="sxs-lookup"><span data-stu-id="b0188-123">Remarks</span></span>  
 <span data-ttu-id="b0188-124">WSDL 가져오기는 메타데이터를 가져오고 그 정보를 계약 및 엔드포인트 정보를 나타내는 다양한 클래스로 변환하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="b0188-124">A WSDL importer is used to import metadata as well as convert that information into various classes that represent contract and endpoint information.</span></span> <span data-ttu-id="b0188-125">가져오기 오류를 공개하는 속성 및 계약과 끝점 정보를 가져오고, 가져오기 및 변환 프로세스와 관련된 형식 정보를 받을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b0188-125">It can selectively import contract and endpoint information and properties that expose any import errors and accept type information relevant to the import and conversion process.</span></span> <span data-ttu-id="b0188-126">또한 정책 문서, WSDL 문서, WSDL 확장명 및 XML 스키마 문서에 대한 액세스를 제공하는 바인딩 정보와 속성의 가져오기도 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="b0188-126">It also supports importing binding information and properties that provide access to any policy documents, WSDL documents, WSDL extensions, and XML schema documents.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b0188-127">참고 항목</span><span class="sxs-lookup"><span data-stu-id="b0188-127">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.WsdlImporterElement>  
 <xref:System.ServiceModel.Configuration.MetadataElement>  
 <xref:System.ServiceModel.Configuration.WsdlImporterElementCollection>  
 <xref:System.ServiceModel.Description.MetadataImporter>  
 <xref:System.ServiceModel.Description.WsdlImporter>  
 [<span data-ttu-id="b0188-128">WCF 클라이언트 구성</span><span class="sxs-lookup"><span data-stu-id="b0188-128">WCF Client Configuration</span></span>](../../../../../docs/framework/wcf/feature-details/client-configuration.md)  
 [<span data-ttu-id="b0188-129">클라이언트</span><span class="sxs-lookup"><span data-stu-id="b0188-129">Clients</span></span>](../../../../../docs/framework/wcf/feature-details/clients.md)
