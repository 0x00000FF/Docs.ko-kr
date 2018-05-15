---
title: '&lt;endpointDiscovery&gt;'
ms.date: 03/30/2017
ms.assetid: 70812717-888a-4748-9640-0df6715ff029
ms.openlocfilehash: c5971ce79ac2f03fbdc91653d5d282804e98cf8a
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
---
# <a name="ltendpointdiscoverygt"></a><span data-ttu-id="d7f91-102">&lt;endpointDiscovery&gt;</span><span class="sxs-lookup"><span data-stu-id="d7f91-102">&lt;endpointDiscovery&gt;</span></span>
<span data-ttu-id="d7f91-103">검색 기능, 범위 및 해당 메타데이터에 대한 사용자 지정 확장명 등 끝점에 대한 다양한 검색 설정을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="d7f91-103">Specifies the various discovery settings for an endpoint, such as its discoverability, scopes, and any custom extensions to its metadata.</span></span>  
  
<span data-ttu-id="d7f91-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="d7f91-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="d7f91-105">\<동작 ></span><span class="sxs-lookup"><span data-stu-id="d7f91-105">\<behaviors></span></span>  
<span data-ttu-id="d7f91-106">\<endpointBehaviors></span><span class="sxs-lookup"><span data-stu-id="d7f91-106">\<endpointBehaviors></span></span>  
<span data-ttu-id="d7f91-107">\<동작 ></span><span class="sxs-lookup"><span data-stu-id="d7f91-107">\<behavior></span></span>  
<span data-ttu-id="d7f91-108">\<endpointDiscovery ></span><span class="sxs-lookup"><span data-stu-id="d7f91-108">\<endpointDiscovery></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d7f91-109">구문</span><span class="sxs-lookup"><span data-stu-id="d7f91-109">Syntax</span></span>  
  
```xml  
<behaviors>
  <endpointBehaviors>
    <behavior name="String">
      <endpointDiscovery enabled="Boolean">
        <scopes>
          <add scope="URI"/>
        </scopes>
        <extensions />
      </endpointDiscovery>
    </behavior>
  </endpointBehaviors>
</behaviors>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d7f91-110">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="d7f91-110">Attributes and Elements</span></span>  
 <span data-ttu-id="d7f91-111">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="d7f91-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d7f91-112">특성</span><span class="sxs-lookup"><span data-stu-id="d7f91-112">Attributes</span></span>  
  
|<span data-ttu-id="d7f91-113">특성</span><span class="sxs-lookup"><span data-stu-id="d7f91-113">Attribute</span></span>|<span data-ttu-id="d7f91-114">설명</span><span class="sxs-lookup"><span data-stu-id="d7f91-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="d7f91-115">사용</span><span class="sxs-lookup"><span data-stu-id="d7f91-115">enabled</span></span>|<span data-ttu-id="d7f91-116">이 끝점에서 검색 기능을 사용하는지 여부를 지정하는 부울 값입니다.</span><span class="sxs-lookup"><span data-stu-id="d7f91-116">A Boolean value that that specifies whether discoverability is enabled on this endpoint.</span></span> <span data-ttu-id="d7f91-117">기본값은 `false`입니다.</span><span class="sxs-lookup"><span data-stu-id="d7f91-117">The default is `false`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="d7f91-118">자식 요소</span><span class="sxs-lookup"><span data-stu-id="d7f91-118">Child Elements</span></span>  
  
|<span data-ttu-id="d7f91-119">요소</span><span class="sxs-lookup"><span data-stu-id="d7f91-119">Element</span></span>|<span data-ttu-id="d7f91-120">설명</span><span class="sxs-lookup"><span data-stu-id="d7f91-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="d7f91-121">\<범위 ></span><span class="sxs-lookup"><span data-stu-id="d7f91-121">\<scopes></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/scopes.md)|<span data-ttu-id="d7f91-122">끝점에 대한 범위 URI의 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="d7f91-122">A collection of scope URIs for the endpoint.</span></span> <span data-ttu-id="d7f91-123">단일 끝점에 둘 이상의 범위 URI를 연결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d7f91-123">More than one scope Uris can be associated with a single endpoint.</span></span>|  
|<span data-ttu-id="d7f91-124">[\<확장 >](../../../../../docs/framework/configure-apps/file-schema/wcf/extensions.md) [의 \<endpointDiscovery >]</span><span class="sxs-lookup"><span data-stu-id="d7f91-124">[\<extensions>](../../../../../docs/framework/configure-apps/file-schema/wcf/extensions.md) [of \<endpointDiscovery>]</span></span>|<span data-ttu-id="d7f91-125">끝점에 대해 게시되는 사용자 지정 메타데이터를 지정할 수 있는 XML 요소의 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="d7f91-125">A collection of XML elements that allows you to specify custom metadata to be published for an endpoint.</span></span>|  
|<span data-ttu-id="d7f91-126">\<유형 ></span><span class="sxs-lookup"><span data-stu-id="d7f91-126">\<types></span></span>|<span data-ttu-id="d7f91-127">검색할 인터페이스의 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="d7f91-127">A collection of interfaces to search for.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="d7f91-128">부모 요소</span><span class="sxs-lookup"><span data-stu-id="d7f91-128">Parent Elements</span></span>  
  
|<span data-ttu-id="d7f91-129">요소</span><span class="sxs-lookup"><span data-stu-id="d7f91-129">Element</span></span>|<span data-ttu-id="d7f91-130">설명</span><span class="sxs-lookup"><span data-stu-id="d7f91-130">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="d7f91-131">\<동작 ></span><span class="sxs-lookup"><span data-stu-id="d7f91-131">\<behavior></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|<span data-ttu-id="d7f91-132">동작 요소를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="d7f91-132">Specifies a behavior element.</span></span>|  
|||  
  
## <a name="remarks"></a><span data-ttu-id="d7f91-133">설명</span><span class="sxs-lookup"><span data-stu-id="d7f91-133">Remarks</span></span>  
 <span data-ttu-id="d7f91-134">끝점의 동작 구성에 추가되고 `enabled` 특성이 `true`로 설정되면 이 구성 요소에 대한 검색 기능을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d7f91-134">When added to the endpoint’s behavior configuration and with the `enabled` attribute set to `true`, this configuration element enables its discoverability.</span></span> <span data-ttu-id="d7f91-135">또한 사용할 수 있습니다는 [ \<범위 >](../../../../../docs/framework/configure-apps/file-schema/wcf/scopes.md)자식 요소가 사용자 지정 범위 쿼리 중 서비스 끝점을 필터링 하기 위해 사용할 수 있는 Uri를 지정 하는 것과 같이 [ \<확장 >](../../../../../docs/framework/configure-apps/file-schema/wcf/extensions.md) 표준 검색 가능 메타 데이터 (EPR, ContractTypeName, BindingName, 범위 및 ListenURI)와 함께 게시 해야 하는 사용자 지정 메타 데이터를 지정 하는 자식 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="d7f91-135">In addition, you can use the [\<scopes>](../../../../../docs/framework/configure-apps/file-schema/wcf/scopes.md)child element to specifying custom scope Uris that can be used to filter service endpoints during query, as well as the [\<extensions>](../../../../../docs/framework/configure-apps/file-schema/wcf/extensions.md) child element to specify custom metadata that should be published along with the standard discoverable metadata (EPR, ContractTypeName, BindingName, Scope and ListenURI).</span></span>  
  
 <span data-ttu-id="d7f91-136">이 구성 요소에 따라 달라 집니다.는 [ \<serviceDiscovery >](../../../../../docs/framework/configure-apps/file-schema/wcf/servicediscovery.md) 검색 기능의 서비스 수준 제어를 제공 하는 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="d7f91-136">This configuration element is dependent on the [\<serviceDiscovery>](../../../../../docs/framework/configure-apps/file-schema/wcf/servicediscovery.md) element that provides the service level control of discoverability.</span></span> <span data-ttu-id="d7f91-137">이 의미 하는 경우이 요소의 설정이 무시 됩니다 [ \<serviceDiscovery >](../../../../../docs/framework/configure-apps/file-schema/wcf/servicediscovery.md) 구성에 나타나지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d7f91-137">This means that this element’s settings are ignored if [\<serviceDiscovery>](../../../../../docs/framework/configure-apps/file-schema/wcf/servicediscovery.md) is not present in the configuration.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d7f91-138">예제</span><span class="sxs-lookup"><span data-stu-id="d7f91-138">Example</span></span>  
 <span data-ttu-id="d7f91-139">다음 구성 예제에서는 필터링 범위 및 끝점에 게시되는 확장명 메타데이터를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="d7f91-139">The following configuration example specifies filtering scopes and extension metadata to be published for an endpoint.</span></span>  
  
```xml  
<services>  
  <service name="CalculatorService"  
           behaviorConfiguration="CalculatorServiceBehavior">  
     <endpoint binding="basicHttpBinding"  
              address="calculator"  
              contract="ICalculatorService"  
              behaviorConfiguration="calculatorEndpointBehavior" />  
  </service>  
</services>  
<behaviors>  
  <serviceBehaviors>  
    <behavior name="CalculatorServiceBehavior">  
      <serviceDiscovery />  
    </behavior>  
  </serviceBehaviors>  
  <endpointBehaviors>  
    <behavior name="calculatorEndpointBehavior">  
      <endpointDiscovery enabled="true">  
        <scopes>  
          <add scope="http://contoso/test1"/>  
          <add scope="http://contoso/test2"/>  
        </scopes>  
        <extensions>  
          <e:Publisher xmlns:e="http://example.org">  
            <e:Name>The Example Organization</e:Name>  
            <e:Address>One Example Way, ExampleTown, EX 12345</e:Address>  
            <e:Contact>support@example.org</e:Contact>  
          </e:Publisher>  
          <AnotherCustomMetadata>Custom Metadata</AnotherCustomMetadata>  
        </extensions>  
      </endpointDiscovery>  
    </behavior>  
  </endpointBehaviors>  
</behaviors>  
```  
  
## <a name="see-also"></a><span data-ttu-id="d7f91-140">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d7f91-140">See Also</span></span>  
 <xref:System.ServiceModel.Discovery.EndpointDiscoveryBehavior>
