---
title: "Discovery 클라이언트 채널을 통해 사용자 지정 바인딩 사용"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 36f95e75-04f7-44f3-a995-a0d623624d7f
caps.latest.revision: "4"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 716dc09d38c778c49a1e2e5fa094ef1bf004eb46
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="using-a-custom-binding-with-the-discovery-client-channel"></a>Discovery 클라이언트 채널을 통해 사용자 지정 바인딩 사용
<xref:System.ServiceModel.Discovery.DiscoveryClientBindingElement>와 함께 사용자 지정 바인딩을 사용하는 경우 <xref:System.ServiceModel.Discovery.DiscoveryEndpointProvider> 인스턴스를 만드는 <xref:System.ServiceModel.Discovery.DiscoveryEndpoint>를 정의해야 합니다.  
  
## <a name="creating-a-discoveryendpointprovider"></a>DiscoveryEndpointProvider 만들기  
 <xref:System.ServiceModel.Discovery.DiscoveryEndpointProvider> 만드는 책임이 <xref:System.ServiceModel.Discovery.DiscoveryEndpoint> 필요에 따라 인스턴스. 검색 끝점 공급자를 정의하려면 <xref:System.ServiceModel.Discovery.DiscoveryEndpointProvider>에서 클래스를 파생시키고 <xref:System.ServiceModel.Discovery.DiscoveryEndpointProvider.GetDiscoveryEndpoint%2A> 메서드를 재정의한 다음 새 검색 끝점을 반환합니다. 다음 예제에서는 검색 끝점 공급자를 만드는 방법을 보여 줍니다.  
  
```  
// Extend DiscoveryEndpointProvider class to change the default DiscoveryEndpoint  
// to the DiscoveryClientBindingElement. The Discovery ClientChannel   
// uses this endpoint to send Probe message.  
public class UdpDiscoveryEndpointProvider : DiscoveryEndpointProvider  
{  
   public override DiscoveryEndpoint GetDiscoveryEndpoint()  
   {  
      return new UdpDiscoveryEndpoint(DiscoveryVersion.WSDiscoveryApril2005);  
   }  
}  
```  
  
 검색 끝점 공급자를 정의한 후에는 다음 예제와 같이 사용자 지정 바인딩을 만들고 검색 끝점 공급자를 참조하는 <xref:System.ServiceModel.Discovery.DiscoveryClientBindingElement>를 추가할 수 있습니다.  
  
```  
DiscoveryClientBindingElement discoveryBindingElement = new DiscoveryClientBindingElement();  
  
// Provide the search criteria and the endpoint over which the probe is sent.  
discoveryBindingElement.FindCriteria = new FindCriteria(typeof(ICalculatorService));  
discoveryBindingElement.DiscoveryEndpointProvider = new UdpDiscoveryEndpointProvider();  
  
CustomBinding customBinding = new CustomBinding(new NetTcpBinding());  
// Insert DiscoveryClientBindingElement at the top of the BindingElement stack.  
// An exception is thrown if this binding element is not at the top.  
customBinding.Elements.Insert(0, discoveryBindingElement);  
```  
  
 [!INCLUDE[crabout](../../../../includes/crabout-md.md)]discovery 클라이언트 채널을 사용 하 여 참조 [Discovery 클라이언트 채널을 사용 하 여](../../../../docs/framework/wcf/feature-details/using-the-discovery-client-channel.md)합니다. 전체 코드 예제를 보려면 [Discovery 바인딩 Element 샘플](../../../../docs/framework/wcf/samples/discovery-binding-element-sample.md)  
  
## <a name="see-also"></a>참고 항목  
 [WCF Discovery 개요](../../../../docs/framework/wcf/feature-details/wcf-discovery-overview.md)  
 [Discovery 클라이언트 채널을 사용 하 여](../../../../docs/framework/wcf/feature-details/using-the-discovery-client-channel.md)  
 [Discovery 바인딩 Element 샘플](../../../../docs/framework/wcf/samples/discovery-binding-element-sample.md)
