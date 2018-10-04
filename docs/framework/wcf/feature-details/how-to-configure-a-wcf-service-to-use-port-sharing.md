---
title: '방법: 포트 공유를 사용하도록 Windows Communication Foundation 서비스 구성'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 6400bc71-a858-4ac2-8d5a-caa72d3b5482
ms.openlocfilehash: d66da04715f96dd37b8f36599d81924ec2f8d5cc
ms.sourcegitcommit: 69229651598b427c550223d3c58aba82e47b3f82
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/04/2018
ms.locfileid: "48778694"
---
# <a name="how-to-configure-a-windows-communication-foundation-service-to-use-port-sharing"></a><span data-ttu-id="67a48-102">방법: 포트 공유를 사용하도록 Windows Communication Foundation 서비스 구성</span><span class="sxs-lookup"><span data-stu-id="67a48-102">How to: Configure a Windows Communication Foundation Service to Use Port Sharing</span></span>
<span data-ttu-id="67a48-103">Windows Communication Foundation (WCF) 응용 프로그램에서 공유 net.tcp:// 포트를 사용 하는 가장 쉬운 방법은 사용 하 여 서비스를 노출 하는 것은 <xref:System.ServiceModel.NetTcpBinding>합니다.</span><span class="sxs-lookup"><span data-stu-id="67a48-103">The easiest way to use net.tcp:// port sharing in your Windows Communication Foundation (WCF) application is to expose a service using the <xref:System.ServiceModel.NetTcpBinding>.</span></span>  
  
 <span data-ttu-id="67a48-104">이 바인딩에서는 이 바인딩을 사용하여 구성하는 서비스에 대해 net.tcp:// 포트 공유를 사용할지 여부를 제어하는 <xref:System.ServiceModel.NetTcpBinding.PortSharingEnabled%2A> 속성을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="67a48-104">This binding provides a <xref:System.ServiceModel.NetTcpBinding.PortSharingEnabled%2A> property that controls whether net.tcp:// port sharing is enabled for the service being configured with this binding.</span></span>  
  
 <span data-ttu-id="67a48-105">다음 절차에서는 <xref:System.ServiceModel.NetTcpBinding> 클래스를 사용하여 URI(Uniform Resource Identifier) net.tcp://localhost/MyService에서 엔드포인트를 여는 방법을 보여 줍니다. 코드와 구성 요소를 사용한 방법을 차례로 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="67a48-105">The following procedure shows how to use the <xref:System.ServiceModel.NetTcpBinding> class to open an endpoint at the Uniform Resource Identifier (URI) net.tcp://localhost/MyService, first in code and then by using configuration elements.</span></span>  
  
### <a name="to-enable-nettcp-port-sharing-on-a-nettcpbinding-in-code"></a><span data-ttu-id="67a48-106">코드로 NetTcpBinding에서 net.tcp:// 포트 공유를 사용하도록 설정하려면</span><span class="sxs-lookup"><span data-stu-id="67a48-106">To enable net.tcp:// port sharing on a NetTcpBinding in code</span></span>  
  
1.  <span data-ttu-id="67a48-107">라는 계약을 구현 하는 서비스를 만듭니다 `IMyService` 호출 `MyService`합니다.</span><span class="sxs-lookup"><span data-stu-id="67a48-107">Create a service to implement a contract called `IMyService` and call it `MyService`, .</span></span>  
  
     [!code-csharp[c_ConfigurePortSharing#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_configureportsharing/cs/source.cs#1)]
     [!code-vb[c_ConfigurePortSharing#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_configureportsharing/vb/source.vb#1)]  
  
2.  <span data-ttu-id="67a48-108"><xref:System.ServiceModel.NetTcpBinding> 클래스의 인스턴스를 만들고 <xref:System.ServiceModel.NetTcpBinding.PortSharingEnabled%2A> 속성을 `true`로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="67a48-108">Create an instance of the <xref:System.ServiceModel.NetTcpBinding> class and set the <xref:System.ServiceModel.NetTcpBinding.PortSharingEnabled%2A> property to `true`.</span></span>  
  
     [!code-csharp[c_ConfigurePortSharing#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_configureportsharing/cs/source.cs#2)]
     [!code-vb[c_ConfigurePortSharing#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_configureportsharing/vb/source.vb#2)]  
  
3.  <span data-ttu-id="67a48-109"><xref:System.ServiceModel.ServiceHost>를 만든 다음 포트 공유 사용 `MyService`을 사용하고 엔드포인트 주소 URI "net.tcp://localhost/MyService"에서 수신 대기하는 <xref:System.ServiceModel.NetTcpBinding>에 대해 서비스 엔드포인트를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="67a48-109">Create a <xref:System.ServiceModel.ServiceHost> and add the service endpoint to it for `MyService` that uses the port sharing-enabled <xref:System.ServiceModel.NetTcpBinding> and that listens at the endpoint address URI "net.tcp://localhost/MyService".</span></span>  
  
     [!code-csharp[c_ConfigurePortSharing#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_configureportsharing/cs/source.cs#3)]
     [!code-vb[c_ConfigurePortSharing#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_configureportsharing/vb/source.vb#3)]  
  
    > [!NOTE]
    >  <span data-ttu-id="67a48-110">엔드포인트 주소 URI에서 다른 포트 번호를 지정하지 않기 때문에 이 예제에서는 기본 TCP 포트 808을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="67a48-110">This example uses the default TCP port of 808 because the endpoint address URI does not specify a different port number.</span></span> <span data-ttu-id="67a48-111">전송 바인딩에서 포트 공유가 명시적으로 사용되기 때문에 이 서비스는 다른 프로세스의 다른 서비스와 포트 808을 공유할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="67a48-111">Because port sharing is explicitly enabled on the transport binding, this service can share port 808 with other services in other processes.</span></span> <span data-ttu-id="67a48-112">포트 공유가 허용되지 않고 다른 응용 프로그램에서 포트 808을 이미 사용하고 있는 경우 포트를 열면 이 서비스에서 <xref:System.ServiceModel.AddressAlreadyInUseException>을 throw합니다.</span><span class="sxs-lookup"><span data-stu-id="67a48-112">If port sharing were not allowed and another application were already using port 808, this service would throw an <xref:System.ServiceModel.AddressAlreadyInUseException> when it was opened.</span></span>  
  
### <a name="to-enable-nettcp-port-sharing-on-a-nettcpbinding-in-configuration"></a><span data-ttu-id="67a48-113">구성을 통해 NetTcpBinding에서 net.tcp:// 포트 공유를 사용하도록 설정하려면</span><span class="sxs-lookup"><span data-stu-id="67a48-113">To enable net.tcp:// port sharing on a NetTcpBinding in configuration</span></span>  
  
1.  <span data-ttu-id="67a48-114">다음 예제에서는 구성 요소를 사용하여 포트 공유를 사용하도록 설정하고 서비스 엔드포인트를 추가하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="67a48-114">The following example shows how to enable port sharing and add the service endpoint using configuration elements.</span></span>  
  
```xml  
<system.serviceModel>  
  <bindings>  
    <netTcpBinding name="portSharingBinding"   
                   portSharingEnabled="true" />  
  </bindings>  
  <services>  
    <service name="MyService">  
        <endpoint address="net.tcp://localhost/MyService"  
                  binding="netTcpBinding"  
                  contract="IMyService"  
                  bindingConfiguration="portSharingBinding" />  
    </service>  
  </services>  
</system.serviceModel>  
```  
  
## <a name="see-also"></a><span data-ttu-id="67a48-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="67a48-115">See Also</span></span>  
 [<span data-ttu-id="67a48-116">Net.TCP 포트 공유</span><span class="sxs-lookup"><span data-stu-id="67a48-116">Net.TCP Port Sharing</span></span>](../../../../docs/framework/wcf/feature-details/net-tcp-port-sharing.md)  
 [<span data-ttu-id="67a48-117">방법: Net.TCP Port Sharing Service 사용</span><span class="sxs-lookup"><span data-stu-id="67a48-117">How to: Enable the Net.TCP Port Sharing Service</span></span>](../../../../docs/framework/wcf/feature-details/how-to-enable-the-net-tcp-port-sharing-service.md)
