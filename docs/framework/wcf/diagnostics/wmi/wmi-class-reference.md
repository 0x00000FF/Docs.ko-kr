---
title: "WMI 클래스 참조"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b95a51f5-8251-4619-ae05-7de88cb90f9a
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 7a74f1d7e70b8664df5022d6f9f42cf04b88f930
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/02/2017
---
# <a name="wmi-class-reference"></a>WMI 클래스 참조
이 섹션에서는 [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] WMI 공급자가 노출하는 모든 WMI 클래스를 보여 줍니다.  
  
## <a name="accessing-wmi-instances"></a>WMI 인스턴스에 액세스  
 WMI 개체 참조에 나열된 모든 클래스는 Service, AppDomain, Contract, ServiceAppDomain, ServiceToEndpointAssociation 및 Endpoint를 제외하고 직접 인스턴스화할 수 없습니다. 다른 인스턴스에 액세스하려면 앞에서 설명한 최상위 클래스의 속성에 액세스합니다. 예를 들어 Endpoint 인스턴스 -> Binding -> BindingElements에서 TransportBindingElement 인스턴스에 액세스할 수 있습니다.  
  
## <a name="in-this-section"></a>단원 내용  
 [ActivityTransfer](../../../../../docs/framework/wcf/diagnostics/wmi/activitytransfer.md)  
  
 [AppDomainInfo](../../../../../docs/framework/wcf/diagnostics/wmi/appdomaininfo.md)  
  
 [AspNetCompatibilityRequirementsAttribute](../../../../../docs/framework/wcf/diagnostics/wmi/aspnetcompatibilityrequirementsattribute.md)  
  
 [Asymmetricsecuritybindingelement가](../../../../../docs/framework/wcf/diagnostics/wmi/asymmetricsecuritybindingelement.md)  
  
 "Behavior 클래스"  
  
 [BinaryMessageEncodingBindingElement](../../../../../docs/framework/wcf/diagnostics/wmi/binarymessageencodingbindingelement.md)  
  
 [바인딩](../../../../../docs/framework/wcf/diagnostics/wmi/binding.md)  
  
 [BindingElement](../../../../../docs/framework/wcf/diagnostics/wmi/bindingelement.md)  
  
 [CallbackBehavior](../../../../../docs/framework/wcf/diagnostics/wmi/callbackbehavior.md)  
  
 [Channel 클래스](../../../../../docs/framework/wcf/diagnostics/wmi/channel-class.md)  
  
 [ChannelPoolSettings](../../../../../docs/framework/wcf/diagnostics/wmi/channelpoolsettings.md)  
  
 [ClientCredentials](../../../../../docs/framework/wcf/diagnostics/wmi/clientcredentials.md)  
  
 [ClientViaBehavior](../../../../../docs/framework/wcf/diagnostics/wmi/clientviabehavior.md)  
  
 [CompositeDuplexBindingElement](../../../../../docs/framework/wcf/diagnostics/wmi/compositeduplexbindingelement.md)  
  
 [ConnectionOrientedTransportBindingElement](../../../../../docs/framework/wcf/diagnostics/wmi/connectionorientedtransportbindingelement.md)  
  
 [계약](../../../../../docs/framework/wcf/diagnostics/wmi/contract.md)  
  
 [CustomBindingElement](../../../../../docs/framework/wcf/diagnostics/wmi/custombindingelement.md)  
  
 [DeliveryRequirementsAttribute](../../../../../docs/framework/wcf/diagnostics/wmi/deliveryrequirementsattribute.md)  
  
 [끝점](../../../../../docs/framework/wcf/diagnostics/wmi/endpoint.md)  
  
 [HttpsTransportBindingElement](../../../../../docs/framework/wcf/diagnostics/wmi/httpstransportbindingelement.md)  
  
 [HttpTransportBindingElement](../../../../../docs/framework/wcf/diagnostics/wmi/httptransportbindingelement.md)  
  
 [LocalServiceSecuritySettings](../../../../../docs/framework/wcf/diagnostics/wmi/localservicesecuritysettings.md)  
  
 [MatchAllEndpointBehavior](../../../../../docs/framework/wcf/diagnostics/wmi/matchallendpointbehavior.md)  
  
 [MessageEncodingBindingElement](../../../../../docs/framework/wcf/diagnostics/wmi/messageencodingbindingelement.md)  
  
 [MsmqBindingElementBase](../../../../../docs/framework/wcf/diagnostics/wmi/msmqbindingelementbase.md)  
  
 [MsmqIntegrationBindingElement](../../../../../docs/framework/wcf/diagnostics/wmi/msmqintegrationbindingelement.md)  
  
 [MsmqTransportBindingElement](../../../../../docs/framework/wcf/diagnostics/wmi/msmqtransportbindingelement.md)  
  
 [MtomMessageEncodingBindingElement](../../../../../docs/framework/wcf/diagnostics/wmi/mtommessageencodingbindingelement.md)  
  
 [MustUnderstandBehavior](../../../../../docs/framework/wcf/diagnostics/wmi/mustunderstandbehavior.md)  
  
 [NamedPipeConnectionPoolSettings](../../../../../docs/framework/wcf/diagnostics/wmi/namedpipeconnectionpoolsettings.md)  
  
 [NamedPipeTransportBindingElement](../../../../../docs/framework/wcf/diagnostics/wmi/namedpipetransportbindingelement.md)  
  
 [OneWayBindingElement](../../../../../docs/framework/wcf/diagnostics/wmi/onewaybindingelement.md)  
  
 "작업 클래스"  
  
 [OperationBehaviorAttribute](../../../../../docs/framework/wcf/diagnostics/wmi/operationbehaviorattribute.md)  
  
 [PeerCustomResolverBindingElement](../../../../../docs/framework/wcf/diagnostics/wmi/peercustomresolverbindingelement.md)  
  
 [PeerResolverBindingElement](../../../../../docs/framework/wcf/diagnostics/wmi/peerresolverbindingelement.md)  
  
 [PeerSecuritySettings](../../../../../docs/framework/wcf/diagnostics/wmi/peersecuritysettings.md)  
  
 [PeerTransportBindingElement](../../../../../docs/framework/wcf/diagnostics/wmi/peertransportbindingelement.md)  
  
 [PeerTransportSecuritySettings](../../../../../docs/framework/wcf/diagnostics/wmi/peertransportsecuritysettings.md)  
  
 [PnrpPeerResolverBindingElement](../../../../../docs/framework/wcf/diagnostics/wmi/pnrppeerresolverbindingelement.md)  
  
 [PrivacyNoticeBindingElement](../../../../../docs/framework/wcf/diagnostics/wmi/privacynoticebindingelement.md)  
  
 [ReliableSessionBindingElement](../../../../../docs/framework/wcf/diagnostics/wmi/reliablesessionbindingelement.md)  
  
 [SecurityBindingElement](../../../../../docs/framework/wcf/diagnostics/wmi/securitybindingelement.md)  
  
 [서비스](../../../../../docs/framework/wcf/diagnostics/wmi/service.md)  
  
 [ServiceAppDomain](../../../../../docs/framework/wcf/diagnostics/wmi/serviceappdomain.md)  
  
 [ServiceAuthorizationBehavior](../../../../../docs/framework/wcf/diagnostics/wmi/serviceauthorizationbehavior.md)  
  
 [ServiceBehaviorAttribute](../../../../../docs/framework/wcf/diagnostics/wmi/servicebehaviorattribute.md)  
  
 [ServiceCredentials](../../../../../docs/framework/wcf/diagnostics/wmi/servicecredentials.md)  
  
 [ServiceDebugBehavior](../../../../../docs/framework/wcf/diagnostics/wmi/servicedebugbehavior.md)  
  
 [ServiceMetadataBehavior](../../../../../docs/framework/wcf/diagnostics/wmi/servicemetadatabehavior.md)  
  
 [ServiceSecurityAuditBehavior](../../../../../docs/framework/wcf/diagnostics/wmi/servicesecurityauditbehavior.md)  
  
 [ServiceThrottlingBehavior](../../../../../docs/framework/wcf/diagnostics/wmi/servicethrottlingbehavior.md)  
  
 [ServiceTimeoutsBehavior](../../../../../docs/framework/wcf/diagnostics/wmi/servicetimeoutsbehavior.md)  
  
 [ServiceToEndpointAssociation](../../../../../docs/framework/wcf/diagnostics/wmi/servicetoendpointassociation.md)  
  
 [SslStreamSecurityBindingElement](../../../../../docs/framework/wcf/diagnostics/wmi/sslstreamsecuritybindingelement.md)  
  
 [SymmetricSecurityBindingElement](../../../../../docs/framework/wcf/diagnostics/wmi/symmetricsecuritybindingelement.md)  
  
 [SynchronousReceiveBehavior](../../../../../docs/framework/wcf/diagnostics/wmi/synchronousreceivebehavior.md)  
  
 [TcpConnectionPoolSettings](../../../../../docs/framework/wcf/diagnostics/wmi/tcpconnectionpoolsettings.md)  
  
 [TcpTransportBindingElement](../../../../../docs/framework/wcf/diagnostics/wmi/tcptransportbindingelement.md)  
  
 [TextMessageEncodingBindingElement](../../../../../docs/framework/wcf/diagnostics/wmi/textmessageencodingbindingelement.md)  
  
 [TraceListener](../../../../../docs/framework/wcf/diagnostics/wmi/tracelistener.md)  
  
 [TraceListenerArgument](../../../../../docs/framework/wcf/diagnostics/wmi/tracelistenerargument.md)  
  
 [TransactedBatchingBehavior](../../../../../docs/framework/wcf/diagnostics/wmi/transactedbatchingbehavior.md)  
  
 [TransactionFlowAttribute](../../../../../docs/framework/wcf/diagnostics/wmi/transactionflowattribute.md)  
  
 [TransactionFlowBindingElement](../../../../../docs/framework/wcf/diagnostics/wmi/transactionflowbindingelement.md)  
  
 [바인딩에 transportbindingelement가](../../../../../docs/framework/wcf/diagnostics/wmi/transportbindingelement.md)  
  
 [Transportsecuritybindingelement가](../../../../../docs/framework/wcf/diagnostics/wmi/transportsecuritybindingelement.md)  
  
 [UseManagedPresentationBindingElement](../../../../../docs/framework/wcf/diagnostics/wmi/usemanagedpresentationbindingelement.md)  
  
 [WindowsStreamSecurityBindingElement](../../../../../docs/framework/wcf/diagnostics/wmi/windowsstreamsecuritybindingelement.md)  
  
 [WSAT_TraceEvent](../../../../../docs/framework/wcf/diagnostics/wmi/wsat-traceevent.md)  
  
 [WSAT_TraceProvider](../../../../../docs/framework/wcf/diagnostics/wmi/wsat-traceprovider.md)  
  
 [WSAT_TraceRecord](../../../../../docs/framework/wcf/diagnostics/wmi/wsat-tracerecord.md)  
  
 [XmlDictionaryReaderQuotas](../../../../../docs/framework/wcf/diagnostics/wmi/xmldictionaryreaderquotas.md)  
  
 [XmlSerializerOperationBehavior](../../../../../docs/framework/wcf/diagnostics/wmi/xmlserializeroperationbehavior.md)
