---
title: 검색 알림 및 알림 클라이언트
ms.date: 03/30/2017
ms.assetid: 426c6437-f8d2-4968-b23a-18afd671aa4b
ms.openlocfilehash: 74362343dc1fd5df6d1b91537f7fed5bc08f8fe0
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2019
ms.locfileid: "69968825"
---
# <a name="discovery-announcements-and-announcement-client"></a><span data-ttu-id="23e3b-102">검색 알림 및 알림 클라이언트</span><span class="sxs-lookup"><span data-stu-id="23e3b-102">Discovery Announcements and Announcement Client</span></span>
<span data-ttu-id="23e3b-103">WCF 검색 기능을 사용 하면 구성 요소에서 해당 가용성을 알릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="23e3b-103">The WCF discovery feature enables components to announce their availability.</span></span> <span data-ttu-id="23e3b-104">이렇게 구성된 경우 서비스는 Hello 및 Bye 알림을 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="23e3b-104">If configured to do so, a service sends Hello and Bye announcements.</span></span> <span data-ttu-id="23e3b-105">클라이언트 또는 기타 구성 요소는 이러한 알림 메시지를 수신 대기하고 이에 대해 동작을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="23e3b-105">Clients or other components can listen for such announcement messages and act on them.</span></span> <span data-ttu-id="23e3b-106">이 기능은 클라이언트가 서비스를 인식하는 또 다른 방법을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="23e3b-106">This provides an alternative method for clients to be aware of services.</span></span> <span data-ttu-id="23e3b-107">알림 기능은 여러 가지 용도로 사용됩니다. 예를 들어 서비스가 빈번하게 네트워크에 들어왔다가 나가는 경우 알림을 사용하는 것이 서비스를 검색하는 것보다 더 효율적일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="23e3b-107">Announcement functionality has several uses, for example, if the services enter and leave a network frequently, announcements may be a better alternative than searching for services.</span></span> <span data-ttu-id="23e3b-108">이 방법을 사용하면 네트워크 트래픽이 줄어들고 클라이언트가 알림을 받는 즉시 해당 서비스가 있는지 여부를 알 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="23e3b-108">With this approach, the network traffic is reduced and the client can learn about the presence or departure of the service as soon as announcements are received.</span></span>  
  
## <a name="discovery-announcements"></a><span data-ttu-id="23e3b-109">검색 알림</span><span class="sxs-lookup"><span data-stu-id="23e3b-109">Discovery Announcements</span></span>  
 <span data-ttu-id="23e3b-110">알림을 받도록 구성된 서비스는 네트워크에 연결되어 검색 가능한 상태가 되면 수신 대기 중인 클라이언트에 자신의 가용성을 알리는 Hello 메시지를 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="23e3b-110">When a service configured for announcements joins a network and becomes discoverable, it sends a Hello message announcing its availability to listening clients.</span></span> <span data-ttu-id="23e3b-111">이 메시지에는 계약, 엔드포인트 주소, 연결된 범위 등 서비스에 대한 검색 관련 정보가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="23e3b-111">The message contains discovery related information about the service, such as its contract, endpoint address and associated scopes.</span></span> <span data-ttu-id="23e3b-112"><xref:System.ServiceModel.Discovery.AnnouncementEndpoint> 클래스를 사용하면 알림 메시지를 보낼 위치를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="23e3b-112">You can specify where the announcement message is sent with the <xref:System.ServiceModel.Discovery.AnnouncementEndpoint> class.</span></span> <span data-ttu-id="23e3b-113">알림 엔드포인트가 <xref:System.ServiceModel.Discovery.UdpAnnouncementEndpoint>이면 Hello 및 Bye가 적절히 멀티캐스트됩니다. 그러나 알림 엔드포인트가 유니캐스트이면 메시지가 지정된 엔드포인트에 직접 보내집니다.</span><span class="sxs-lookup"><span data-stu-id="23e3b-113">If the announcement endpoint is a <xref:System.ServiceModel.Discovery.UdpAnnouncementEndpoint> then the Hello and Bye are multicast appropriately, or if the announcement endpoint is unicast, the messages are sent directly to the specified endpoint.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="23e3b-114">알림은 서비스 호스트가 열리고 닫힐 때 보내집니다.</span><span class="sxs-lookup"><span data-stu-id="23e3b-114">Announcements are sent when the service host opens and closes.</span></span> <span data-ttu-id="23e3b-115">이러한 호출이 올바로 완료되지 않으면 알림 메시지가 보내지지 않을 수 있습니다. 예를 들어 서비스에서 오류가 발생해도 Bye 알림 메시지가 보내지지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="23e3b-115">If these calls do not finish properly the announcement message may not be sent out. For example if the service faults, then the Bye announcement message is not sent.</span></span>  
  
> [!TIP]
>  <span data-ttu-id="23e3b-116">선택할 때마다 알림을 보낼 수 있도록 알림 기능을 사용자 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="23e3b-116">You can customize the announcement functionality, allowing you to send announcements whenever you choose.</span></span>  
  
 [!INCLUDE[netfx_current_long](../../../../includes/netfx-current-long-md.md)]<span data-ttu-id="23e3b-117">에서는 서비스와 클라이언트에서 손쉽게 Hello 및 Bye 알림을 보낼 수 있도록 <xref:System.ServiceModel.Discovery.AnnouncementEndpoint> 및 <xref:System.ServiceModel.Discovery.UdpAnnouncementEndpoint>를 표준 엔드포인트로 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="23e3b-117">defines the <xref:System.ServiceModel.Discovery.AnnouncementEndpoint> and <xref:System.ServiceModel.Discovery.UdpAnnouncementEndpoint> as standard endpoints to allow services and clients to easily send Hello and Bye announcements.</span></span>  
  
### <a name="announcements-on-the-service"></a><span data-ttu-id="23e3b-118">서비스에서의 알림</span><span class="sxs-lookup"><span data-stu-id="23e3b-118">Announcements on the Service</span></span>  
 <span data-ttu-id="23e3b-119">알림을 보내도록 서비스를 구성하려면 알림 엔드포인트를 사용하여 <xref:System.ServiceModel.Discovery.ServiceDiscoveryBehavior>를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="23e3b-119">To configure the service to send announcements, add a <xref:System.ServiceModel.Discovery.ServiceDiscoveryBehavior> with an announcement endpoint.</span></span> <span data-ttu-id="23e3b-120">다음 예제에서는 프로그래밍 방식으로 이 동작을 서비스 호스트에 추가하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="23e3b-120">The following example shows how to programmatically add this behavior to the service host.</span></span> <span data-ttu-id="23e3b-121">이 예제에서는 `UdpAnnouncementEndpoint`를 사용하여 알림이 해당 표준 엔드포인트에 의해 지정된 위치에 멀티캐스트되도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="23e3b-121">This example uses the `UdpAnnouncementEndpoint`, which implies that the announcements are multicast to a location specified by that standard endpoint.</span></span>  
  
```  
ServiceDiscoveryBehavior serviceDiscoveryBehavior = new ServiceDiscoveryBehavior();
serviceDiscoveryBehavior.AnnouncementEndpoints.Add(new UdpAnnouncementEndpoint());
serviceHost.Description.Behaviors.Add(serviceDiscoveryBehavior);
```  
  
 <span data-ttu-id="23e3b-122">다음 예제와 같이 구성 파일에서 동작을 구성할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="23e3b-122">The behavior can be configured in the configuration file as well, as shown in the following example.</span></span>  
  
```xml  
<services>
  <service behaviorConfiguration="CalculatorBehavior" name="Microsoft.Samples.Discovery.CalculatorService">
    <!--Add Discovery Endpoint-->
    <endpoint name="udpDiscoveryEpt" kind="udpDiscoveryEndpoint" />
  </service>
</services>
<behaviors>
  <serviceBehaviors>
    <behavior name="CalculatorBehavior">
      <!--Add Discovery behavior-->
      <serviceDiscovery>
        <announcementEndpoints>
          <endpoint kind="udpAnnouncementEndpoint" />
        </announcementEndpoints>
      </serviceDiscovery>
    </behavior>
  </serviceBehaviors>
</behaviors>  
```  
  
 <span data-ttu-id="23e3b-123">위의 예제에서는 자동으로 알림 메시지를 보내도록 서비스를 구성했지만</span><span class="sxs-lookup"><span data-stu-id="23e3b-123">The preceding examples configure a service to automatically send announcement messages.</span></span> <span data-ttu-id="23e3b-124"><xref:System.ServiceModel.Discovery.AnnouncementClient> 클래스를 사용하여 알림 메시지를 명시적으로 보낼 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="23e3b-124">You can also send announcement messages explicitly by using the <xref:System.ServiceModel.Discovery.AnnouncementClient> class.</span></span>  
  
### <a name="announcements-on-the-client"></a><span data-ttu-id="23e3b-125">클라이언트에서의 알림</span><span class="sxs-lookup"><span data-stu-id="23e3b-125">Announcements on the Client</span></span>  
 <span data-ttu-id="23e3b-126">클라이언트 애플리케이션에서는 Hello 및 Bye 메시지에 응답하고 <xref:System.ServiceModel.Discovery.AnnouncementService.OnlineAnnouncementReceived> 및 <xref:System.ServiceModel.Discovery.AnnouncementService.OfflineAnnouncementReceived> 이벤트를 구독할 수 있도록 알림 서비스를 호스팅해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="23e3b-126">A client application must host an announcement service to respond to the Hello and Bye messages and subscribe to the <xref:System.ServiceModel.Discovery.AnnouncementService.OnlineAnnouncementReceived> and <xref:System.ServiceModel.Discovery.AnnouncementService.OfflineAnnouncementReceived> events.</span></span> <span data-ttu-id="23e3b-127">다음 예제에서는 이 작업을 수행하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="23e3b-127">The following example shows how to do this.</span></span>  
  
```  
// Create an AnnouncementService instance
AnnouncementService announcementService = new AnnouncementService();
  
// Subscribe the announcement events
announcementService.OnlineAnnouncementReceived += OnOnlineEvent;
announcementService.OfflineAnnouncementReceived += OnOfflineEvent;
  
// Create ServiceHost for the AnnouncementService
using (ServiceHost announcementServiceHost = new ServiceHost(announcementService))
{  
    // Listen for the announcements sent over UDP multicast
    announcementServiceHost.AddServiceEndpoint(new UdpAnnouncementEndpoint());
    announcementServiceHost.Open();
  
    Console.WriteLine("Press <ENTER> to terminate.");
    Console.ReadLine();
}  
```  
  
 <span data-ttu-id="23e3b-128">Hello 또는 Bye 메시지를 받으면 다음 예제와 같이 <xref:System.ServiceModel.Discovery.AnnouncementEventArgs>를 통해 엔드포인트 검색 메타데이터에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="23e3b-128">When a Hello or Bye message is received, you can access the endpoint discovery metadata through <xref:System.ServiceModel.Discovery.AnnouncementEventArgs> as shown in the following example.</span></span>  
  
```  
static void OnOnlineEvent(object sender, AnnouncementEventArgs e)
{
    Console.WriteLine("Received an online announcement from {0}", 
e.EndpointDiscoveryMetadata.Address);
}

static void OnOfflineEvent(object sender, AnnouncementEventArgs e)
{
    Console.WriteLine("Received an offline announcement from {0}", 
e.EndpointDiscoveryMetadata.Address);
}
```
