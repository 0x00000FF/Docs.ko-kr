---
title: <udpAnnouncementEndpoint>
ms.date: 03/30/2017
ms.assetid: 5b3fa9c5-f372-4df9-a9d6-1e426063b721
ms.openlocfilehash: 04f5fb27a0da7e553ff3c0308f7fb2e2df2e0b20
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61788260"
---
# <a name="udpannouncementendpoint"></a><span data-ttu-id="00709-101">\<udpAnnouncementEndpoint></span><span class="sxs-lookup"><span data-stu-id="00709-101">\<udpAnnouncementEndpoint></span></span>
<span data-ttu-id="00709-102">이 구성 요소는 서비스에서 UDP 바인딩을 통해 알림 메시지를 보내기 위해 사용하는 표준 엔드포인트를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="00709-102">This configuration element defines a standard endpoint that is used by services to send announcement messages over a UDP binding.</span></span> <span data-ttu-id="00709-103">고정된 계약이 있으며 두 가지 버전의 검색을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="00709-103">It has a fixed contract and supports two discovery versions.</span></span> <span data-ttu-id="00709-104">또한 WS-Discovery 사양(WS-Discovery April 2005 또는 WS-Discovery 버전 1.1)에 지정된 고정된 UDP 바인딩 및 기본 주소 값이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="00709-104">In addition it has a fixed UDP binding and a default address value as specified in the WS-Discovery specifications (WS-Discovery April 2005 or WS-Discovery version 1.1).</span></span> <span data-ttu-id="00709-105">알림 메시지를 보내고 받는 데 사용할 멀티캐스트 주소를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="00709-105">You can specify the multicast address to use for sending and receiving the announcement messages.</span></span>  
  
<span data-ttu-id="00709-106">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="00709-106">\<system.ServiceModel></span></span>  
<span data-ttu-id="00709-107">\<standardEndpoints></span><span class="sxs-lookup"><span data-stu-id="00709-107">\<standardEndpoints></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="00709-108">구문</span><span class="sxs-lookup"><span data-stu-id="00709-108">Syntax</span></span>  
  
```xml  
<system.serviceModel>
  <standardEndpoints>
    <announcementEndpoint>
      <standardEndpoint discoveryVersion="WSDiscovery11/WSDiscoveryApril2005"
                        maxAnnouncementDelay="Timespan"
                        multicastAddress="Uri"
                        name="String" />
    </announcementEndpoint>
  </standardEndpoints>
</system.serviceModel>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="00709-109">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="00709-109">Attributes and Elements</span></span>  
 <span data-ttu-id="00709-110">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="00709-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="00709-111">특성</span><span class="sxs-lookup"><span data-stu-id="00709-111">Attributes</span></span>  
  
|<span data-ttu-id="00709-112">특성</span><span class="sxs-lookup"><span data-stu-id="00709-112">Attribute</span></span>|<span data-ttu-id="00709-113">설명</span><span class="sxs-lookup"><span data-stu-id="00709-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="00709-114">discoveryVersion</span><span class="sxs-lookup"><span data-stu-id="00709-114">discoveryVersion</span></span>|<span data-ttu-id="00709-115">WS-Discovery 프로토콜의 두 버전 중 하나를 지정하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="00709-115">A string that specifies one of the two versions of WS-Discovery protocol.</span></span> <span data-ttu-id="00709-116">유효한 값은 WSDiscovery11 및 WSDiscoveryApril2005입니다.</span><span class="sxs-lookup"><span data-stu-id="00709-116">Valid values are WSDiscovery11 and WSDiscoveryApril2005.</span></span> <span data-ttu-id="00709-117">이 값은 <xref:System.ServiceModel.Discovery.Configuration.AnnouncementEndpointElement.DiscoveryVersion> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="00709-117">This value is of type <xref:System.ServiceModel.Discovery.Configuration.AnnouncementEndpointElement.DiscoveryVersion>.</span></span>|  
|<span data-ttu-id="00709-118">maxAnnouncementDelay</span><span class="sxs-lookup"><span data-stu-id="00709-118">maxAnnouncementDelay</span></span>|<span data-ttu-id="00709-119">검색 프로토콜이 Hello 메시지가 전송될 때까지 대기하는 최대 지연 값을 지정하는 Timespan 값입니다.</span><span class="sxs-lookup"><span data-stu-id="00709-119">A Timespan value that specifies the maximum value for the delay the Discovery protocol will wait before sending a Hello message.</span></span> <span data-ttu-id="00709-120">메시지는 전송되기 전에 0에서 이 특성에 지정된 값 사이의 임의 시간 값 동안 대기합니다.</span><span class="sxs-lookup"><span data-stu-id="00709-120">The messages will wait for a random time value between 0 and the value of this attribute before being sent.</span></span> <span data-ttu-id="00709-121">이 특성은 네트워크에 장애가 발생했다가 모든 서비스가 동시에 온라인 상태로 복구되는 경우에 네트워크 폭주가 발생하는 것을 방지하기 위해 임의의 짧은 지연 간격을 설정하기 위해 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="00709-121">This attribute is used to set a small, random delay to prevent network storms when a network goes out and all services come back online at the same time.</span></span>|  
|<span data-ttu-id="00709-122">multicastAddress</span><span class="sxs-lookup"><span data-stu-id="00709-122">multicastAddress</span></span>|<span data-ttu-id="00709-123">검색 메시지를 보내고 받는 데 사용할 멀티캐스트 주소를 지정하는 URI입니다.</span><span class="sxs-lookup"><span data-stu-id="00709-123">A URI that specifies a multicast address to use for sending and receiving the discovery messages.</span></span> <span data-ttu-id="00709-124">기본값은 프로토콜 사양을 따르는 멀티캐스트 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="00709-124">The default value is the multicast address as conformant to the protocol specification.</span></span>|  
|<span data-ttu-id="00709-125">name</span><span class="sxs-lookup"><span data-stu-id="00709-125">name</span></span>|<span data-ttu-id="00709-126">표준 엔드포인트의 구성 이름을 지정하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="00709-126">A String that specifies the name of the configuration of the standard endpoint.</span></span> <span data-ttu-id="00709-127">이 이름은 서비스 엔드포인트의 `endpointConfiguration` 특성에서 표준 엔드포인트를 해당 구성에 연결하기 위해 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="00709-127">The name is used in the `endpointConfiguration` attribute of the service endpoint to link a standard endpoint to its configuration.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="00709-128">자식 요소</span><span class="sxs-lookup"><span data-stu-id="00709-128">Child Elements</span></span>  
  
|<span data-ttu-id="00709-129">요소</span><span class="sxs-lookup"><span data-stu-id="00709-129">Element</span></span>|<span data-ttu-id="00709-130">설명</span><span class="sxs-lookup"><span data-stu-id="00709-130">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="00709-131">\<udpTransportSettings></span><span class="sxs-lookup"><span data-stu-id="00709-131">\<udpTransportSettings></span></span>](udptransportsettings.md)|<span data-ttu-id="00709-132">UDP 엔드포인트에 대한 UDP 전송을 구성할 수 있도록 하는 설정의 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="00709-132">A collection of settings that allow you to configure UDP transport for the UDP endpoint.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="00709-133">부모 요소</span><span class="sxs-lookup"><span data-stu-id="00709-133">Parent Elements</span></span>  
  
|<span data-ttu-id="00709-134">요소</span><span class="sxs-lookup"><span data-stu-id="00709-134">Element</span></span>|<span data-ttu-id="00709-135">설명</span><span class="sxs-lookup"><span data-stu-id="00709-135">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="00709-136">\<standardEndpoints></span><span class="sxs-lookup"><span data-stu-id="00709-136">\<standardEndpoints></span></span>](standardendpoints.md)|<span data-ttu-id="00709-137">하나 이상의 속성(주소, 바인딩, 계약)이 고정된 미리 정의된 엔드포인트인 표준 엔드포인트의 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="00709-137">A collection of standard endpoints that are pre-defined endpoints with one or more of their properties (address, binding, contract) fixed.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="00709-138">예제</span><span class="sxs-lookup"><span data-stu-id="00709-138">Example</span></span>  
 <span data-ttu-id="00709-139">다음 예제에서는 기본 멀티캐스트 주소를 사용하는 UDP 멀티캐스트 전송 및 지정된 멀티캐스트 주소를 사용하는 UDP 멀티캐스트 전송을 통해 알림을 수신하는 클라이언트를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="00709-139">The following example demonstrates a client listening for announcement over a UDP multicast transport with default multicast address, and UDP multicast transport with specified multicast address.</span></span>  
  
```xml  
<services>
  <service name="ServiceAnnouncementListener">
    <endpoint name="udpAnnouncementEndpointStandard"
              kind="udpAnnouncementEndpoint"
              bindingConfiguration="..." />
    <endpoint name="udpAnnouncementEndpoint2"
              kind="udpAnnouncementEndpoint"
              endpointConfiguration="AnnouncementConfiguration3702"
              bindingConfiguration="..." />
    ...
  </service>
</services>
<standardEndpoints>
  <udpAnnouncementEndpoint>
    <standardEndpoint name="AnnouncementConfiguration2"
                      version="WSDiscoveryApril2005"
                      multicastAddress="soap.udp://239.255.255.250:3703"/>
  </udpAnnouncementEndpoint>
</standardEndpoints>
```  
  
## <a name="see-also"></a><span data-ttu-id="00709-140">참고자료</span><span class="sxs-lookup"><span data-stu-id="00709-140">See also</span></span>

- <xref:System.ServiceModel.Discovery.UdpAnnouncementEndpoint>
