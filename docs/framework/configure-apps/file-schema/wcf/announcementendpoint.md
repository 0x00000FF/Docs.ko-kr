---
title: '&lt;AnnouncementEndpoint&gt;'
ms.date: 03/30/2017
ms.assetid: 034b7c69-a770-4502-8cef-38007bbcd025
ms.openlocfilehash: fe278da539af59a32edf5a626461dbec0ba3887d
ms.sourcegitcommit: 4ac80713f6faa220e5a119d5165308a58f7ccdc8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/09/2019
ms.locfileid: "54151646"
---
# <a name="ltannouncementendpointgt"></a><span data-ttu-id="ef270-102">&lt;AnnouncementEndpoint&gt;</span><span class="sxs-lookup"><span data-stu-id="ef270-102">&lt;announcementEndpoint&gt;</span></span>
<span data-ttu-id="ef270-103">이 구성 요소는 고정 알림 계약이 있는 표준 엔드포인트를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="ef270-103">This configuration element defines a standard endpoint with a fixed announcement contract.</span></span> <span data-ttu-id="ef270-104">서비스에서는 선택적으로 서비스가 열리거나 닫힐 때 각각 온라인 및 오프라인 알림 메시지를 보내 가용성을 알릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ef270-104">A service can optionally announce its availability by sending an online and offline announcement message when it is opened or closed respectively.</span></span> <span data-ttu-id="ef270-105">Windows Communication Foundation (WCF) 서비스에서 알림 끝점을 지정 합니다 [ \<serviceDiscovery >](../../../../../docs/framework/configure-apps/file-schema/wcf/servicediscovery.md) AnnouncementClient 발표 하는 데 사용 하 여 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="ef270-105">A Windows Communication Foundation (WCF) service specifies the announcement endpoints in the [\<serviceDiscovery>](../../../../../docs/framework/configure-apps/file-schema/wcf/servicediscovery.md) element and uses the AnnouncementClient to perform the announcements.</span></span> <span data-ttu-id="ef270-106">WCF 서비스를 실제로 다른 서비스에서 알림을 수신 하려는 클라이언트는 역할을 하합니다 따라서 해당 클라이언트에 대 한 알림 끝점을 구성 해야 합니다 [ \<services >](../../../../../docs/framework/configure-apps/file-schema/wcf/services.md) 섹션입니다.</span><span class="sxs-lookup"><span data-stu-id="ef270-106">A client wishing to listen for the announcement from other service is actually acting as a WCF service; thus you have to configure the announcement endpoints for that client in the [\<services>](../../../../../docs/framework/configure-apps/file-schema/wcf/services.md) section.</span></span>  
  
<span data-ttu-id="ef270-107">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="ef270-107">\<system.ServiceModel></span></span>  
<span data-ttu-id="ef270-108">\<standardEndpoints ></span><span class="sxs-lookup"><span data-stu-id="ef270-108">\<standardEndpoints></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ef270-109">구문</span><span class="sxs-lookup"><span data-stu-id="ef270-109">Syntax</span></span>  
  
```xml  
<system.serviceModel>
  <standardEndpoints>
    <announcementEndpoint>
      <standardEndpoint discoveryVersion="WSDiscovery11/WSDiscoveryApril2005"
                        maxAnnouncementDelay="Timespan"
                        name="String" />
    </announcementEndpoint>
  </standardEndpoints>
</system.serviceModel>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ef270-110">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="ef270-110">Attributes and Elements</span></span>  
 <span data-ttu-id="ef270-111">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="ef270-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ef270-112">특성</span><span class="sxs-lookup"><span data-stu-id="ef270-112">Attributes</span></span>  
  
|<span data-ttu-id="ef270-113">특성</span><span class="sxs-lookup"><span data-stu-id="ef270-113">Attribute</span></span>|<span data-ttu-id="ef270-114">설명</span><span class="sxs-lookup"><span data-stu-id="ef270-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="ef270-115">discoveryVersion</span><span class="sxs-lookup"><span data-stu-id="ef270-115">discoveryVersion</span></span>|<span data-ttu-id="ef270-116">WS-Discovery 프로토콜의 두 버전 중 하나를 지정하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="ef270-116">A string that specifies one of the two versions of WS-Discovery protocol.</span></span> <span data-ttu-id="ef270-117">유효한 값은 WSDiscovery11 및 WSDiscoveryApril2005입니다.</span><span class="sxs-lookup"><span data-stu-id="ef270-117">Valid values are WSDiscovery11 and WSDiscoveryApril2005.</span></span> <span data-ttu-id="ef270-118">이 값은 <xref:System.ServiceModel.Discovery.Configuration.AnnouncementEndpointElement.DiscoveryVersion> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="ef270-118">This value is of type <xref:System.ServiceModel.Discovery.Configuration.AnnouncementEndpointElement.DiscoveryVersion>.</span></span>|  
|<span data-ttu-id="ef270-119">maxAnnouncementDelay</span><span class="sxs-lookup"><span data-stu-id="ef270-119">maxAnnouncementDelay</span></span>|<span data-ttu-id="ef270-120">검색 프로토콜이 Hello 메시지가 전송될 때까지 대기하는 최대 지연 값을 지정하는 Timespan 값입니다.</span><span class="sxs-lookup"><span data-stu-id="ef270-120">A Timespan value that specifies the maximum value for the delay the Discovery protocol will wait before sending a Hello message.</span></span> <span data-ttu-id="ef270-121">메시지는 전송되기 전에 0에서 이 특성에 지정된 값 사이의 임의 시간 값 동안 대기합니다.</span><span class="sxs-lookup"><span data-stu-id="ef270-121">The messages will wait for a random time value between 0 and the value of this attribute before being sent.</span></span> <span data-ttu-id="ef270-122">이 특성은 네트워크에 장애가 발생했다가 모든 서비스가 동시에 온라인 상태로 복구되는 경우에 네트워크 폭주가 발생하는 것을 방지하기 위해 임의의 짧은 지연 간격을 설정하기 위해 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="ef270-122">This attribute is used to set a small, random delay to prevent network storms when a network goes out and all services come back online at the same time.</span></span>|  
|<span data-ttu-id="ef270-123">name</span><span class="sxs-lookup"><span data-stu-id="ef270-123">name</span></span>|<span data-ttu-id="ef270-124">표준 끝점의 구성 이름을 지정하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="ef270-124">A String that specifies the name of the configuration of the standard endpoint.</span></span> <span data-ttu-id="ef270-125">이 이름은 서비스 엔드포인트의 `endpointConfiguration` 특성에서 표준 엔드포인트를 해당 구성에 연결하기 위해 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="ef270-125">The name is used in the `endpointConfiguration` attribute of the service endpoint to link a standard endpoint to its configuration.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="ef270-126">자식 요소</span><span class="sxs-lookup"><span data-stu-id="ef270-126">Child Elements</span></span>  
 <span data-ttu-id="ef270-127">없음</span><span class="sxs-lookup"><span data-stu-id="ef270-127">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="ef270-128">부모 요소</span><span class="sxs-lookup"><span data-stu-id="ef270-128">Parent Elements</span></span>  
  
|<span data-ttu-id="ef270-129">요소</span><span class="sxs-lookup"><span data-stu-id="ef270-129">Element</span></span>|<span data-ttu-id="ef270-130">설명</span><span class="sxs-lookup"><span data-stu-id="ef270-130">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="ef270-131">\<standardEndpoints ></span><span class="sxs-lookup"><span data-stu-id="ef270-131">\<standardEndpoints></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/standardendpoints.md)|<span data-ttu-id="ef270-132">하나 이상의 속성(주소, 바인딩, 계약)이 고정된 미리 정의된 엔드포인트인 표준 엔드포인트의 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="ef270-132">A collection of standard endpoints that are pre-defined endpoints with one or more of their properties (address, binding, contract) fixed.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="ef270-133">예제</span><span class="sxs-lookup"><span data-stu-id="ef270-133">Example</span></span>  
 <span data-ttu-id="ef270-134">다음 예제에서는 http 및 peernet을 통해 알림 메시지를 수신하는 클라이언트를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="ef270-134">The following example demonstrates a client listening for announcements messages over http and peernet.</span></span>  
  
```xml  
<services>
  <service name="ServiceAnnouncementListener">
    <endpoint name="httpAnnouncementEndpoint"
              kind="announcementEndpoint"
              binding="basicHttpBinding"
              address="announcements" />
    <endpoint name="peerNetAnnouncementEndpoint"
              kind="announcementEndpoint"
              binding="peerTcpBinding"
              address="net.p2p://discoveryMesh/multicast"
              bindingConfiguration="discoveryPeerTcpBindingConfig" />
  ...
  </service>
</services>

<standardEndpoints>
  <announcementEndpoint>
    <standardEndpoint name="httpAnnouncementEndpoint"
                      version="WSDiscoveryApril2005" />
    <standardEndpoint name="peerNetAnnouncementEndpoint"
                      version="WSDiscoveryApril2005" />
  </announcementEndpoint>
</standardEndpoints>
```  
  
## <a name="see-also"></a><span data-ttu-id="ef270-135">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ef270-135">See Also</span></span>  
 <xref:System.ServiceModel.Discovery.AnnouncementEndpoint>
