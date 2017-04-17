---
title: "리소스 사용 제어 및 성능 향상 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 9a829669-5f76-4c88-80ec-92d0c62c0660
caps.latest.revision: 18
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 18
---
# 리소스 사용 제어 및 성능 향상
이 항목에서는 리소스 사용을 제어하고 성능 메트릭에 영향을 주는 [!INCLUDE[indigo1](../../../includes/indigo1-md.md)] 아키텍처의 다른 영역에 있는 여러 속성에 대해 설명합니다.  
  
## WCF에서 리소스 사용을 제한하는 속성  
 [!INCLUDE[indigo1](../../../includes/indigo1-md.md)]에서는 보안이나 성능 향상을 위해 특정 유형의 프로세스에 제약 조건을 적용합니다.이러한 제약 조건은 할당량이나 스로틀 같은 두 가지 기본 형태로 나타납니다.*할당량*은 도달 또는 초과 시 시스템의 일부 지점에서 즉각적인 예외를 트리거하는 한계입니다.*스로틀*은 예외가 즉시 throw되지 않도록 하는 한계입니다.대신 스로틀 한계에 도달하면 프로세스는 해당 스로틀 값으로 설정된 한계 내에서만 계속 수행됩니다.이러한 제한된 처리로 다른 위치에 예외가 트리거될 수 있지만, 응용 프로그램에 따라 다릅니다.  
  
 할당량과 스로틀 간의 차이 외에도 제약 속성 중 일부는 serialization 수준에, 일부는 전송 수준에, 일부는 응용 프로그램 수준에 있는 등 차이가 있습니다.예를 들어, 모든 시스템 제공 전송 바인딩 요소에 의해 구현되는 할당량인 <xref:System.ServiceModel.Channels.TransportBindingElement.MaxReceivedMessageSize%2A?displayProperty=fullName>는 악의적인 클라이언트가 메모리를 과도하게 사용하여 서비스에 대한 서비스 거부 공격을 하지 못하도록 기본적으로 65,536바이트로 설정됩니다.일반적으로 이 값을 낮추면 성능이 향상됩니다.  
  
 serialization 할당량의 예로는 <xref:System.Runtime.Serialization.DataContractSerializer.MaxItemsInObjectGraph%2A?displayProperty=fullName> 속성이 있으며, 이 속성은 serializer가 단일 <xref:System.Runtime.Serialization.DataContractSerializer.ReadObject%2A> 메서드 호출에서 serialize하거나 deserialize하는 최대 개체 수를 지정합니다.응용 프로그램 수준 스로틀의 예로는 <xref:System.ServiceModel.Dispatcher.ServiceThrottle.MaxConcurrentSessions%2A?displayProperty=fullName> 속성이 있으며, 기본적으로 이 속성은 동시 세션 채널 연결의 수를 10으로 제한합니다.할당량과 달리 스로틀 값에 도달하면 응용 프로그램에서는 처리를 계속 수행하지만 새 세션 채널을 허용하지는 않습니다. 따라서 다른 세션 채널 중 하나가 종료될 때까지 새 클라이언트에 연결되지 않습니다.  
  
 이러한 제어는 특정 유형의 공격에 대해 즉각적인 완화를 제공하거나 메모리 사용 공간, 시작 시간 등과 같은 성능 메트릭을 향상하기 위해 디자인되었습니다.그러나 응용 프로그램에 따라 이러한 제어로 인해 서비스 응용 프로그램 성능이 저하되거나 응용 프로그램이 전혀 작동하지 않을 수 있습니다.예를 들어, 비디오 스트리밍을 위해 개발된 응용 프로그램은 기본 <xref:System.ServiceModel.Channels.TransportBindingElement.MaxReceivedMessageSize%2A?displayProperty=fullName> 속성을 쉽게 초과할 수 있습니다.이 항목에서는 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]의 모든 수준에서 응용 프로그램에 적용되는 여러 제어에 대해 간략하게 설명하며, 설정으로 인해 응용 프로그램의 성능이 저하되는지 여부에 대한 자세한 정보를 가져오는 다양한 방법 및 여러 문제를 해결하는 방법에 대해 설명합니다.기본 속성이 serialization이나 전송 제약 조건이더라도 응용 프로그램 수준에서 대부분의 스로틀 및 일부 할당량을 사용할 수 있습니다.예를 들어, 서비스 클래스의 <xref:System.ServiceModel.ServiceBehaviorAttribute.MaxItemsInObjectGraph%2A?displayProperty=fullName> 속성을 사용하여 <xref:System.Runtime.Serialization.DataContractSerializer.MaxItemsInObjectGraph%2A?displayProperty=fullName> 속성을 설정할 수 있습니다.  
  
> [!NOTE]
>  특정 문제가 있는 경우에는 먼저 [WCF 문제 해결 퀵 스타트](../../../docs/framework/wcf/wcf-troubleshooting-quickstart.md)를 읽고 문제 및 해결 방법이 있는지 알아 봅니다.  
  
 serialization 프로세스를 제한하는 속성은 [데이터에 대한 보안 고려 사항](../../../docs/framework/wcf/feature-details/security-considerations-for-data.md)에 나열되어 있습니다.전송과 관련된 리소스 사용을 제한하는 속성은 [전송 할당량](../../../docs/framework/wcf/feature-details/transport-quotas.md)에 나열되어 있습니다.응용 프로그램 계층에서 리소스 사용을 제한하는 속성은 <xref:System.ServiceModel.Dispatcher.ServiceThrottle> 클래스의 멤버입니다.  
  
## 할당량 설정과 관련된 응용 프로그램 및 성능 문제 검색  
 일반적인 보안 문제에 대해 기본 보호를 제공하면서 다양한 종류의 응용 프로그램에서 기본 응용 프로그램 기능을 사용할 수 있도록 이전 기본값이 선택되어 있습니다.그러나 응용 프로그램이 안전하고 개발된 대로 작동하더라도 다른 응용 프로그램 디자인에서 하나 이상의 스로틀 설정을 초과할 수 있습니다.이러한 경우 어떤 수준에서 어떤 스로틀 값이 초과되었는지 식별하여 응용 프로그램 처리량을 늘리기 위해 수행할 적합한 작업을 결정해야 합니다.  
  
 일반적으로 응용 프로그램을 작성하고 이를 디버깅할 때 구성 파일에서 또는 프로그래밍 방식으로 <xref:System.ServiceModel.Description.ServiceDebugBehavior.IncludeExceptionDetailInFaults%2A?displayProperty=fullName> 속성을 `true`로 설정합니다.그러면 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]에서 서비스 예외 스택 추적을 볼 수 있도록 클라이언트 응용 프로그램에 반환합니다.이 기능은 관련이 있을 수 있는 할당량 설정을 표시하는 방식으로\(이 설정이 문제인 경우\) 대부분의 응용 프로그램 수준 예외를 보고합니다.  
  
 일부 예외는 런타임에 응용 프로그램 계층의 표시 범위 아래에서 발생하고, 이 메커니즘을 사용하여 반환되지 않으며, 사용자 지정 <xref:System.ServiceModel.Dispatcher.IErrorHandler?displayProperty=fullName> 구현에 의해 처리될 수 없습니다.Microsoft Visual Studio와 같은 개발 환경을 사용하는 경우 이러한 예외의 대부분이 자동으로 표시됩니다.그러나 일부 예외는 Visual Studio 2005의 [Just My Code Debugging](http://go.microsoft.com/fwlink/?LinkId=82174) 설정과 같은 개발 환경 설정으로 마스킹될 수 있습니다.  
  
 개발 환경의 기능과 관계없이 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 추적 및 메시지 로깅 기능을 사용하여 모든 예외를 디버깅하고 응용 프로그램의 성능을 조정할 수 있습니다.자세한 내용은 [추적을 사용하여 응용 프로그램 문제 해결](../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)을 참조하십시오.  
  
## 성능 문제 및 XmlSerializer  
 <xref:System.Xml.Serialization.XmlSerializer>를 사용하여 serialize할 수 있는 데이터 형식을 사용하는 서비스 및 클라이언트 응용 프로그램은 런타임에 해당 데이터 형식에 대한 serialization 코드를 생성하고 컴파일합니다. 이로 인해 시작 시 성능이 저하될 수 있습니다.  
  
> [!NOTE]
>  미리 생성된 serialization 코드는 서비스가 아닌 클라이언트 응용 프로그램에서만 사용될 수 있습니다.  
  
 [ServiceModel Metadata 유틸리티 도구\(Svcutil.exe\)](../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md)를 사용하면 응용 프로그램에 대해 컴파일된 어셈블리로부터 필요한 serialization 코드를 생성하여 이러한 응용 프로그램의 시작 성능을 향상시킬 수 있습니다.자세한 내용은 [방법: XmlSerializer를 사용하여 WCF 클라이언트 응용 프로그램의 시작 시간 개선](../../../docs/framework/wcf/feature-details/startup-time-of-wcf-client-applications-using-the-xmlserializer.md)을 참조하십시오.  
  
## WCF 서비스를 ASP.NET 호스팅할 때의 성능 문제  
 WCF 서비스를 IIS 및 ASP.NET에 호스팅하는 경우 IIS 및 ASP.NET의 구성 설정이 WCF 서비스의 처리량 및 메모리 사용 공간에 영향을 줄 수 있습니다.ASP.NET 성능[!INCLUDE[crabout](../../../includes/crabout-md.md)][Chapter 6 \- Improving ASP.NET Performance](http://go.microsoft.com/fwlink/?LinkId=186462)를 참조하십시오.예상치 않은 결과를 일으킬 수 있는 설정 중 하나는 <xref:System.Web.Configuration.ProcessModelSection>의 속성인 <xref:System.Web.Configuration.ProcessModelSection.MinWorkerThreads%2A>입니다.응용 프로그램의 클라이언트 수가 고정되어 있거나 적은 경우 <xref:System.Web.Configuration.ProcessModelSection.MinWorkerThreads%2A>를 2로 설정하면 다중 프로세서 컴퓨터에서 처리량이 크게 높아져 CPU 사용률이 100%에 가깝게 됩니다.이러한 성능 증가는 비용을 초래합니다. 또한 메모리 사용량도 증가하여 확장성이 저하됩니다.  
  
## 참고 항목  
 [관리 및 진단](../../../docs/framework/wcf/diagnostics/index.md)   
 [큰 데이터 및 스트리밍](../../../docs/framework/wcf/feature-details/large-data-and-streaming.md)