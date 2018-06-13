---
title: 클라이언트 아키텍처
ms.date: 03/30/2017
ms.assetid: 02624403-0d77-41cb-9a86-ab55e98c7966
ms.openlocfilehash: 4ced24f370e2ab54528c6adb2b3617d3d849e745
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33494093"
---
# <a name="client-architecture"></a>클라이언트 아키텍처
응용 프로그램 Windows Communication Foundation (WCF) 클라이언트 개체를 사용 하 여 서비스 작업을 호출 합니다. 이 항목에서는 WCF 클라이언트 개체, WCF 클라이언트 채널 및 상호 관계 기본 채널 아키텍처를 설명 합니다. WCF 클라이언트 개체의 기본적인 개요를 참조 하십시오. [WCF 클라이언트 개요](../../../../docs/framework/wcf/wcf-client-overview.md)합니다. 채널 계층에 대 한 자세한 내용은 참조 [채널 계층 확장](../../../../docs/framework/wcf/extending/extending-the-channel-layer.md)합니다.  
  
## <a name="overview"></a>개요  
 서비스 모델 런타임에서 다음으로 구성 된 WCF 클라이언트를 만듭니다.  
  
-   서비스 계약에 대해 자동으로 생성되는 클라이언트 구현이 포함됩니다. 이를 통해 응용 프로그램 코드의 호출이 보내는 메시지로 변환되고 응답 메시지는 응용 프로그램에서 검색할 수 있는 출력 매개 변수 및 반환 값으로 변환됩니다.  
  
-   제어 인터페이스(<xref:System.ServiceModel.IClientChannel?displayProperty=nameWithType>)의 구현이 포함됩니다. 이를 통해 여러 인터페이스를 함께 그룹화하고 제어 기능, 특히 클라이언트 세션을 닫고 채널을 삭제하는 기능에 대한 액세스를 제공합니다.  
  
-   사용한 바인딩을 통해 지정된 구성 설정을 기반으로 빌드된 클라이언트 채널이 포함됩니다.  
  
 응용 프로그램을 통해 필요에 따라 이러한 클라이언트를 만들 수는 <xref:System.ServiceModel.ChannelFactory?displayProperty=nameWithType> 또는의 인스턴스를 만들어 한 <xref:System.ServiceModel.ClientBase%601> 파생 클래스에서 생성 되는 [ServiceModel Metadata 유틸리티 도구 (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md)합니다. 이미 빌드된 이러한 클라이언트 클래스는 캡슐화되어 <xref:System.ServiceModel.ChannelFactory>에 의해 동적으로 생성되는 클라이언트 채널 구현에 위임됩니다. 따라서 클라이언트 채널 및 클라이언트 채널을 생성하는 채널 팩터리에 대해 중점적으로 알아 봅니다.  
  
## <a name="client-objects-and-client-channels"></a>클라이언트 개체 및 클라이언트 채널  
 WCF 클라이언트의 기본 인터페이스는 <xref:System.ServiceModel.IClientChannel?displayProperty=nameWithType> 핵심 클라이언트 기능 뿐만 아니라의 기본적인 통신 개체 기능을 노출 하는 인터페이스 <xref:System.ServiceModel.ICommunicationObject?displayProperty=nameWithType>의 컨텍스트 기능 <xref:System.ServiceModel.IContextChannel?displayProperty=nameWithType>, 및의 확장 가능한 동작 <xref:System.ServiceModel.IExtensibleObject%601?displayProperty=nameWithType>.  
  
 그러나 <xref:System.ServiceModel.IClientChannel> 인터페이스는 서비스 계약 자체를 정의하지 않습니다. 서비스 계약 인터페이스에서 선언 하는 것 (일반적으로 같은 도구를 사용 하 여 서비스 메타 데이터에서 생성 된 [ServiceModel Metadata 유틸리티 도구 (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md)). WCF 클라이언트 형식은 둘 다 확장 <xref:System.ServiceModel.IClientChannel> 와 대상 서비스 계약 인터페이스와 직접 작업을 호출 응용 프로그램에 클라이언트 측 런타임 기능에 액세스할 수 있습니다. WCF를 제공 하는 WCF 클라이언트 만들기<xref:System.ServiceModel.ChannelFactory?displayProperty=nameWithType> 런타임 생성 하는 데 필요한 정보로 연결 하 고 구성 된 서비스 끝점과 상호 작용 수 있는 개체입니다.  
  
 앞서 언급 했 듯이 WCF 클라이언트 유형에 사용 하기 전에 구성 되어야 합니다. 가장 간단한 WCF 클라이언트 형식에서 파생 된 개체는 <xref:System.ServiceModel.ClientBase%601> (또는 <xref:System.ServiceModel.DuplexClientBase%601> 서비스 계약이 이중 계약인 경우). 개체를 프로그래밍 방식으로 구성한 경우에는 생성자를 사용하여, 서비스 작업 호출을 위해 직접 개체를 호출한 경우에는 구성 파일을 사용하여 이러한 형식을 만들 수 있습니다. 기본적인 개요에 대 한 <xref:System.ServiceModel.ClientBase%601> 개체 참조 [WCF 클라이언트 개요](../../../../docs/framework/wcf/wcf-client-overview.md)합니다.  
  
 두 번째 형식은 <xref:System.ServiceModel.ChannelFactory%601.CreateChannel%2A> 메서드에 대한 호출을 통해 런타임에 생성됩니다. 일반적으로 관련 통신 고유 정보에 대 한 엄격한 제어 된 응용 프로그램 이라는이 클라이언트 형식을 사용 하 여 한 *클라이언트 채널 개체*기본 클라이언트 런타임 및 채널 보다 더 직접적인 상호 작용을 수 있기 때문 시스템입니다.  
  
## <a name="channel-factories"></a>채널 팩터리  
 클라이언트 호출을 지원하는 기본 런타임을 만드는 클래스는 <xref:System.ServiceModel.ChannelFactory%601?displayProperty=nameWithType> 클래스입니다. WCF 클라이언트 개체와 WCF 클라이언트 채널 개체를 사용 하는 <xref:System.ServiceModel.ChannelFactory%601> 개체 인스턴스를 만듭니다;는 <xref:System.ServiceModel.ClientBase%601> 파생된 클라이언트 개체가 채널 팩터리 처리를 캡슐화 하지만 다양 한 시나리오에 대 한 것이 이상적 사용 하는 직접 채널 팩터리입니다. 여기에 해당하는 일반적인 시나리오는 기존 팩터리에서 새 클라이언트 채널을 반복적으로 만들려는 경우입니다. 클라이언트 개체를 사용 하는 경우에서 얻을 수 있습니다 기본 채널 팩터리는 WCF 클라이언트 개체를 호출 하 여는 <xref:System.ServiceModel.ClientBase%601.ChannelFactory%2A?displayProperty=nameWithType> 속성입니다.  
  
 채널 팩터리가 <xref:System.ServiceModel.ChannelFactory%601.CreateChannel%2A?displayProperty=nameWithType>을 호출하기 전에, 채널 팩터리에 제공된 구성에 대해 클라이언트 채널의 새 인스턴스를 만든다는 점이 중요합니다. 호출한 후 <xref:System.ServiceModel.ChannelFactory%601.CreateChannel%2A> (또는 <xref:System.ServiceModel.ClientBase%601.Open%2A?displayProperty=nameWithType>, <xref:System.ServiceModel.ClientBase%601.CreateChannel%2A?displayProperty=nameWithType>, 또는 WCF 클라이언트 개체에 대해 작업), 채널 팩터리를 수정 하 고 단지 대상 끝점 주소를 변경 하려는 경우에 예상 채널을 다른 서비스 인스턴스로 가져올 수 없습니다. 다른 구성을 사용하는 클라이언트 채널이나 클라이언트 개체를 만들려면 새로운 채널 팩터리를 먼저 만들어야 합니다.  
  
 WCF 클라이언트 개체와 WCF 클라이언트 채널을 사용 하 여 다양 한 문제에 대 한 자세한 내용은 참조 [WCF 클라이언트를 사용 하 여 액세스 서비스](../../../../docs/framework/wcf/feature-details/accessing-services-using-a-client.md)합니다.  
  
 만들고 사용할 WCF 클라이언트 채널 개체의 다음 두 섹션에 설명합니다.  
  
#### <a name="creating-a-new-wcf-client-channel-object"></a>새 WCF 클라이언트 채널 개체 만들기  
 클라이언트 채널 사용을 설명하기 위해 다음 서비스 계약이 생성되어 있는 것으로 가정합니다.  
  
 [!code-csharp[C_GeneratedCodeFiles#12](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_generatedcodefiles/cs/proxycode.cs#12)]  
  
 `ISampleService` 서비스에 연결하려면 생성된 계약 인터페이스를 채널 팩터리(<xref:System.ServiceModel.ChannelFactory%601>)와 함께 직접 사용합니다. 특정 계약을 위한 채널 팩터리를 만들고 구성하면, <xref:System.ServiceModel.ChannelFactory%601.CreateChannel%2A> 서비스와 통신하는 데 사용할 수 있는 클라이언트 채널 개체를 반환하는 `ISampleService` 메서드를 호출할 수 있습니다.  
  
 <xref:System.ServiceModel.ChannelFactory%601> 클래스를 서비스 계약 인터페이스와 함께 사용하면 채널을 명시적으로 열고, 닫고, 중단할 수 있도록 <xref:System.ServiceModel.IClientChannel> 인터페이스로 캐스팅해야 합니다. 더 편리하게 작업할 수 있도록 Svcutil.exe 도구에서는 서비스 계약 인터페이스와 <xref:System.ServiceModel.IClientChannel> 을 모두 구현하는 도우미 인터페이스도 생성되므로 캐스팅하지 않고도 클라이언트 채널 인프라와 상호 작용할 수 있습니다. 다음 코드에서는 이전의 서비스 계약을 구현하는 도우미 클라이언트 채널에 대한 정의를 보여 줍니다.  
  
 [!code-csharp[C_GeneratedCodeFiles#13](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_generatedcodefiles/cs/proxycode.cs#13)]  
  
#### <a name="creating-a-new-wcf-client-channel-object"></a>새 WCF 클라이언트 채널 개체 만들기  
 `ISampleService` 서비스에 연결하기 위해 클라이언트 채널을 사용하려면 생성된 계약 인터페이스(또는 도우미 버전)를 채널 팩터리와 함께 직접 사용하여 계약 인터페이스의 형식을 형식 매개 변수로 전달합니다. 특정 계약을 위한 채널 팩터리를 만들고 구성하면, <xref:System.ServiceModel.ChannelFactory%601.CreateChannel%2A?displayProperty=nameWithType> 서비스와 통신하는 데 사용할 수 있는 클라이언트 채널 개체를 반환하는 `ISampleService` 메서드를 호출할 수 있습니다.  
  
 생성된 클라이언트 채널 개체는 <xref:System.ServiceModel.IClientChannel> 및 계약 인터페이스를 구현합니다. 따라서 이를 직접 사용하여 해당 계약을 지원하는 서비스와 상호 작용하는 작업을 호출할 수 있습니다.  
  
 클라이언트 개체와 클라이언트 채널 개체에 대한 사용 상의 차이점은 단지 개발자의 사용 편이성과 제어에 대한 점입니다. 클래스 및 개체 사용에 익숙한 대부분의 개발자는 WCF 클라이언트 채널 대신 WCF 클라이언트 개체를 사용 하도록 기본적으로 사용 합니다.  
  
 예를 들어 참조 [하는 방법: ChannelFactory를 사용 하 여](../../../../docs/framework/wcf/feature-details/how-to-use-the-channelfactory.md)합니다.
