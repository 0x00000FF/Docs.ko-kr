---
title: "클라이언트 확장 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "프록시 확장 [WCF]"
ms.assetid: 1328c61c-06e5-455f-9ebd-ceefb59d3867
caps.latest.revision: 17
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 17
---
# 클라이언트 확장
호출 응용 프로그램에서 서비스 모델 계층은 응용 프로그램 코드의 메서드 호출을 아웃바운드 메시지로 변환하고, 이를 기본 채널에 제공하며, 결과를 다시 응용 프로그램 코드의 반환 값 및 out 매개 변수로 변환한 후 결과를 다시 호출자에게 반환하는 역할을 합니다.서비스 모델 확장은 클라이언트 또는 디스패처 기능, 사용자 지정 동작, 메시지 및 매개 변수 가로채기 그리고 다른 확장 기능이 포함된 통신 동작 및 기능 또는 실행을 수정하거나 구현합니다.  
  
 이 항목에서는 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 클라이언트 응용 프로그램에서 <xref:System.ServiceModel.Dispatcher.ClientRuntime> 및 <xref:System.ServiceModel.Dispatcher.ClientOperation> 클래스를 사용하여 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 클라이언트의 기본 실행 동작을 수정하는 방법과 메시지, 매개 변수 또는 반환 값을 채널 계층에서 보내거나 검색하기 이전 또는 이후에 이를 가로채거나 수정하는 방법에 대해 설명합니다.서비스 런타임 확장에 대한 자세한 내용은 [디스패처 확장](../../../../docs/framework/wcf/extending/extending-dispatchers.md)을 참조하십시오.사용자 지정 개체를 수정하고 이를 클라이언트 런타임에 삽입하는 동작에 대한 자세한 내용은 [동작을 사용하여 런타임 구성 및 확장](../../../../docs/framework/wcf/extending/configuring-and-extending-the-runtime-with-behaviors.md)을 참조하십시오.  
  
## 클라이언트  
 클라이언트의 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 클라이언트 개체 또는 클라이언트 채널은 메서드 호출을 나가는 메시지로 변환하고 들어오는 메시지를 호출 응용 프로그램에 반환되는 작업 결과로 변환합니다.클라이언트 형식에 대한 자세한 내용은 [WCF 클라이언트 아키텍처](../../../../docs/framework/wcf/feature-details/client-architecture.md)를 참조하십시오.  
  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 클라이언트 형식에는 끝점 수준 및 작업 수준의 기능을 처리하는 런타임 형식이 있습니다.응용 프로그램에서 작업을 호출하면 <xref:System.ServiceModel.Dispatcher.ClientOperation>은 아웃바운드 개체를 메시지로 변환하고 인터셉터를 처리하며, 아웃바운드 호출이 대상 계약을 따르는지 확인한 후 아웃바운드 메시지를 <xref:System.ServiceModel.Dispatcher.ClientRuntime>에 전달합니다. 이 ClientRuntime 클래스는 아웃바운드 채널 및 인바운드 채널\(이중 서비스의 경우\)을 생성 및 관리하고, 헤더 수정과 같은 추가 아웃바운드 메시지 프로세스를 처리하며, 양방향으로 메시지 인터셉터를 처리할 뿐 아니라 인바운드 이중 호출을 적절한 클라이언트 측<xref:System.ServiceModel.Dispatcher.DispatchRuntime> 개체에 라우트하는 역할도 합니다.<xref:System.ServiceModel.Dispatcher.ClientOperation>과 <xref:System.ServiceModel.Dispatcher.ClientRuntime>은 모두 오류를 포함한 메시지가 클라이언트에 반환될 때 비슷한 서비스를 제공합니다.  
  
 이 두 개의 런타임 클래스는 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 클라이언트 개체와 채널 처리를 사용자 지정하기 위한 주요 확장 클래스입니다.<xref:System.ServiceModel.Dispatcher.ClientRuntime> 클래스를 사용하면 계약의 모든 메시지에 대해 클라이언트 실행을 가로채 확장할 수 있으며,<xref:System.ServiceModel.Dispatcher.ClientOperation> 클래스를 사용하면 지정된 작업의 모든 메시지에 대해 클라이언트 실행을 가로채 확장할 수 있습니다.  
  
 속성 수정이나 사용자 지정 삽입 작업은 계약, 끝점 및 작업 동작을 통해 수행됩니다.이러한 동작 유형을 사용하여 클라이언트 런타임 사용자 지정을 수행하는 방법에 대한 자세한 내용은 [동작을 사용하여 런타임 구성 및 확장](../../../../docs/framework/wcf/extending/configuring-and-extending-the-runtime-with-behaviors.md)을 참조하십시오.  
  
## 시나리오  
 클라이언트 시스템을 확장하는 데에는 다음과 같은 여러 가지 이유가 있습니다.  
  
-   사용자 지정 메시지 유효성 확인 \-메시지가 특정 스키마에 유효하도록 지정하고자 할 수 있습니다.이 작업은 <xref:System.ServiceModel.Dispatcher.IClientMessageInspector> 인터페이스를 구현한 다음 <xref:System.ServiceModel.Dispatcher.DispatchRuntime.MessageInspectors%2A> 속성에 할당하여 수행할 수 있습니다.예제를 보려면 [방법: 클라이언트에서 메시지 검사 또는 수정](../../../../docs/framework/wcf/extending/how-to-inspect-or-modify-messages-on-the-client.md) 및 [방법: 클라이언트에서 메시지 검사 또는 수정](../../../../docs/framework/wcf/extending/how-to-inspect-or-modify-messages-on-the-client.md)를 참조하십시오.  
  
-   사용자 지정 메시지 로깅 \-끝점을 통해 이동하는 응용 프로그램 메시지의 일부를 검사하고 기록하도록 지정하고자 할 수 있습니다.이 작업도 메시지 인터셉터 인터페이스를 통해 수행할 수 있습니다.  
  
-   사용자 지정 메시지 변환 \-응용 프로그램 코드를 수정하기 보다는 특정 변환을 런타임에 메시지에 적용하도록 지정하고자 할 수 있습니다\(예: 버전 관리\).이 작업도 메시지 인터셉터 인터페이스를 통해 수행할 수 있습니다.  
  
-   사용자 지정 데이터 모델 \-[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]에서 기본적으로 지원되는 데이터 또는 serialization 모델\(즉, <xref:System.Runtime.Serialization.DataContractSerializer?displayProperty=fullName>, <xref:System.Xml.Serialization.XmlSerializer?displayProperty=fullName> 및 <xref:System.ServiceModel.Channels.Message?displayProperty=fullName> 개체\) 이외의 데이터 또는 serialization 모델을 가지고자 할 수 있습니다.이 작업은 메시지 포맷터 인터페이스를 구현하여 수행할 수 있습니다.자세한 내용은 <xref:System.ServiceModel.Dispatcher.IClientMessageFormatter?displayProperty=fullName> 및 <xref:System.ServiceModel.Dispatcher.ClientOperation.Formatter%2A?displayProperty=fullName> 속성을 참조하십시오.  
  
-   사용자 지정 매개 변수 유효성 검사 \-XML 형식이 아닌 다른 형식의 매개 변수가 유효하도록 지정하고자 할 수 있습니다.이 작업은 매개 변수 검사자 인터페이스를 사용하여 수행할 수 있습니다.예제를 보려면 [방법: 매개 변수 검사 또는 수정](../../../../docs/framework/wcf/extending/how-to-inspect-or-modify-parameters.md) 또는 [Client Validation](../../../../docs/framework/wcf/samples/client-validation.md)를 참조하십시오.  
  
### ClientRuntime 클래스 사용  
 <xref:System.ServiceModel.Dispatcher.ClientRuntime> 클래스는 메시지를 가로채서 클라이언트 동작을 확장하는 확장 개체를 추가할 수 있는 확장성 지점입니다.가로채기 개체는 특정 계약의 모든 메시지를 처리하고, 특정 작업의 메시지만 처리하며, 사용자 지정 채널 초기화를 수행하고, 다른 사용자 지정 클라이언트 응용 프로그램 동작을 구현할 수 있습니다.  
  
-   <xref:System.ServiceModel.Dispatcher.ClientRuntime.CallbackDispatchRuntime%2A> 속성은 서비스 개시 콜백 클라이언트에 대한 디스패치 런타임 개체를 반환합니다.  
  
-   <xref:System.ServiceModel.Dispatcher.ClientRuntime.OperationSelector%2A> 속성은 사용자 지정 작업 선택자 개체를 적용합니다.  
  
-   <xref:System.ServiceModel.Dispatcher.ClientRuntime.ChannelInitializers%2A> 속성을 사용하면 클라이언트 채널을 검사하거나 수정할 수 있는 채널 이니셜라이저를 추가할 수 있습니다.  
  
-   <xref:System.ServiceModel.Dispatcher.ClientRuntime.Operations%2A> 속성은 해당 작업의 메시지에 특정한 기능을 제공하는 사용자 지정 메시지 인터셉터를 추가할 수 있는 <xref:System.ServiceModel.Dispatcher.ClientOperation> 개체의 컬렉션을 가져옵니다.  
  
-   <xref:System.ServiceModel.Dispatcher.ClientRuntime.ManualAddressing%2A> 속성을 사용하면 응용 프로그램에서 일부 자동 주소 헤더를 비활성화하고 주소를 직접 제어할 수 있습니다.  
  
-   <xref:System.ServiceModel.Dispatcher.ClientRuntime.Via%2A> 속성은 중간 매개자와 기타 시나리오를 지원하도록 전송 수준에서 메시지 대상 값을 설정합니다.  
  
-   <xref:System.ServiceModel.Dispatcher.ClientRuntime.MessageInspectors%2A> 속성은 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 클라이언트를 통해 이동하는 모든 메시지에 대한 사용자 지정 메시지 인터셉터를 추가할 수 있는 <xref:System.ServiceModel.Dispatcher.IClientMessageInspector> 개체 컬렉션을 가져옵니다.  
  
 또한 계약 정보를 검색하는 다음과 같은 몇 가지 속성이 있습니다.  
  
-   <xref:System.ServiceModel.Dispatcher.ClientRuntime.ContractName%2A>  
  
-   <xref:System.ServiceModel.Dispatcher.ClientRuntime.ContractNamespace%2A>  
  
-   <xref:System.ServiceModel.Dispatcher.ClientRuntime.ContractClientType%2A>  
  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 클라이언트가 이중 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 클라이언트인 경우 다음 속성도 콜백 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 클라이언트 정보를 검색합니다.  
  
-   <xref:System.ServiceModel.Dispatcher.ClientRuntime.CallbackClientType%2A>  
  
-   <xref:System.ServiceModel.Dispatcher.ClientRuntime.CallbackDispatchRuntime%2A>  
  
 전체 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 클라이언트에서 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 클라이언트 실행을 확장하려면, <xref:System.ServiceModel.Dispatcher.ClientRuntime> 클래스에서 사용할 수 있는 속성을 검토하여 속성 수정이나 인터페이스 구현 및 이를 속성에 추가하는 방식으로 원하는 기능을 만들 수 있는지 확인합니다.빌드하려는 특정 확장을 선택했으면, 호출 시 <xref:System.ServiceModel.Dispatcher.ClientRuntime> 클래스에 대한 액세스를 제공하는 클라이언트 동작을 구현하여 적합한<xref:System.ServiceModel.Dispatcher.ClientRuntime> 속성에 확장을 삽입합니다.  
  
 작업 동작\(<xref:System.ServiceModel.Description.IOperationBehavior>를 구현하는 개체\), 계약 동작\(<xref:System.ServiceModel.Description.IContractBehavior>를 구현하는 개체\) 또는 끝점 동작\(<xref:System.ServiceModel.Description.IEndpointBehavior>를 구현하는 개체\)을 사용하여 사용자 지정 확장 개체를 컬렉션에 삽입할 수 있습니다.설치 동작 개체는 사용자 지정 특성을 구현하여 프로그래밍의 선언적 방식으로 또는 사용자 지정 <xref:System.ServiceModel.Configuration.BehaviorExtensionElement> 개체를 구현하여 적합한 동작 컬렉션에 추가되기 때문에, 응용 프로그램 구성 파일을 통해 동작 삽입이 가능합니다.자세한 내용은 [동작을 사용하여 런타임 구성 및 확장](../../../../docs/framework/wcf/extending/configuring-and-extending-the-runtime-with-behaviors.md)를 참조하십시오.  
  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 클라이언트에서의 가로채기 방법을 보여 주는 예제는 [방법: 클라이언트에서 메시지 검사 또는 수정](../../../../docs/framework/wcf/extending/how-to-inspect-or-modify-messages-on-the-client.md)을 참조하십시오.  
  
### ClientOperation 클래스 사용  
 <xref:System.ServiceModel.Dispatcher.ClientOperation> 클래스는 하나의 서비스 작업으로 범위가 제한된 사용자 지정 확장에 대한 클라이언트 런타임 수정 및 삽입 지점의 위치입니다.계약의 모든 메시지에 대한 클라이언트 런타임 동작을 수정하려면 <xref:System.ServiceModel.Dispatcher.ClientRuntime> 클래스를 사용합니다.  
  
 특정 서비스 작업을 나타내는 <xref:System.ServiceModel.Dispatcher.ClientOperation> 개체를 찾으려면 <xref:System.ServiceModel.Dispatcher.ClientRuntime.Operations%2A> 속성을 사용합니다.다음 속성을 사용하면 사용자 지정 개체를 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 클라이언트 시스템에 삽입할 수 있습니다.  
  
-   작업에 대한 사용자 지정 <xref:System.ServiceModel.Dispatcher.IClientMessageFormatter> 구현을 삽입하거나 현재 포맷터를 수정하려면 <xref:System.ServiceModel.Dispatcher.ClientOperation.Formatter%2A> 속성을 사용합니다.  
  
-   사용자 지정 <xref:System.ServiceModel.Dispatcher.IParameterInspector> 구현을 삽입하거나 현재 구현을 수정하려면 <xref:System.ServiceModel.Dispatcher.ClientOperation.ParameterInspectors%2A> 속성을 사용합니다.  
  
 다음 속성을 사용하면 포맷터 및 사용자 지정 매개 변수 검사자와 상호 작용하여 시스템을 수정할 수 있습니다.  
  
-   아웃바운드 메시지에 대한 serialization을 제어하려면 <xref:System.ServiceModel.Dispatcher.ClientOperation.SerializeRequest%2A> 속성을 사용합니다.  
  
-   인바운드 메시지에 대한 deserialization을 제어하려면 <xref:System.ServiceModel.Dispatcher.ClientOperation.DeserializeReply%2A> 속성을 사용합니다.  
  
-   요청 메시지에 대한 WS\-Addressing 동작을 제어하려면 <xref:System.ServiceModel.Dispatcher.ClientOperation.Action%2A> 속성을 사용합니다.  
  
-   비동기 작업에 연결되는 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 클라이언트 메서드를 지정하려면 <xref:System.ServiceModel.Dispatcher.ClientOperation.BeginMethod%2A> 및 <xref:System.ServiceModel.Dispatcher.ClientOperation.EndMethod%2A>를 사용합니다.  
  
-   SOAP 오류에 세부 유형으로 표시될 수 있는 형식이 포함된 컬렉션을 가져오려면 <xref:System.ServiceModel.Dispatcher.ClientOperation.FaultContractInfos%2A> 속성을 사용합니다.  
  
-   작업이 호출될 때 세션이 초기화되는지 또는 삭제되는지 여부를 각각 제어하려면 <xref:System.ServiceModel.Dispatcher.ClientOperation.IsInitiating%2A> 및 <xref:System.ServiceModel.Dispatcher.ClientOperation.IsTerminating%2A> 속성을 사용합니다.  
  
-   작업이 단방향 작업인지 제어하려면 <xref:System.ServiceModel.Dispatcher.ClientOperation.IsOneWay%2A> 속성을 사용합니다.  
  
-   포함하는 <xref:System.ServiceModel.Dispatcher.ClientRuntime> 개체를 가져오려면 <xref:System.ServiceModel.Dispatcher.ClientOperation.Parent%2A> 속성을 사용합니다.  
  
-   작업 이름을 가져오려면 <xref:System.ServiceModel.Dispatcher.ClientOperation.Name%2A> 속성을 사용합니다.  
  
-   작업에 매핑되는 메서드를 제어하려면 <xref:System.ServiceModel.Dispatcher.ClientOperation.SyncMethod%2A> 속성을 사용합니다.  
  
 단 하나의 서비스 작업에서 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 클라이언트 실행을 확장하려면, <xref:System.ServiceModel.Dispatcher.ClientRuntime> 클래스에서 사용할 수 있는 속성을 검토하여 속성 수정이나 인터페이스 구현 및 이를 속성에 추가하는 방식으로 원하는 기능을 만들 수 있는지 확인합니다.빌드하려는 특정 확장을 선택했으면, 호출 시 <xref:System.ServiceModel.Dispatcher.ClientOperation> 클래스에 대한 액세스를 제공하는 클라이언트 동작을 구현하여 적합한<xref:System.ServiceModel.Dispatcher.ClientOperation> 속성에 확장을 삽입합니다.그러면 해당 동작에서 <xref:System.ServiceModel.Dispatcher.ClientRuntime> 속성을 사용자의 요구 사항에 맞게 수정할 수 있습니다.  
  
 일반적으로 작업 동작\(<xref:System.ServiceModel.Description.IOperationBehavior> 인터페이스를 구현하는 개체\) 구현으로도 충분하지만, 특정 작업에 대한 <xref:System.ServiceModel.Description.OperationDescription>을 찾아 여기에 동작을 연결하여 끝점 동작과 계약 동작을 사용하여 같은 결과를 얻을 수 있습니다.자세한 내용은 [동작을 사용하여 런타임 구성 및 확장](../../../../docs/framework/wcf/extending/configuring-and-extending-the-runtime-with-behaviors.md)를 참조하십시오.  
  
 구성에서 사용자 지정 동작을 사용하려면 사용자 지정 동작 구성 섹션 처리기를 사용하여 동작을 설치합니다.사용자 지정 특성을 만들어 동작을 설치할 수도 있습니다.  
  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 클라이언트에서의 가로채기 방법을 보여 주는 예제는 [방법: 매개 변수 검사 또는 수정](../../../../docs/framework/wcf/extending/how-to-inspect-or-modify-parameters.md)을 참조하십시오.  
  
## 참고 항목  
 <xref:System.ServiceModel.Dispatcher.ClientRuntime>   
 <xref:System.ServiceModel.Dispatcher.ClientOperation>   
 [방법: 클라이언트에서 메시지 검사 또는 수정](../../../../docs/framework/wcf/extending/how-to-inspect-or-modify-messages-on-the-client.md)   
 [방법: 매개 변수 검사 또는 수정](../../../../docs/framework/wcf/extending/how-to-inspect-or-modify-parameters.md)