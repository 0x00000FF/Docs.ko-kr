---
title: 사용자 지정 채널 디스패처
ms.date: 03/30/2017
ms.assetid: 813acf03-9661-4d57-a3c7-eeab497321c6
ms.openlocfilehash: 20574b4c849f312cb2cf55709d8d5e2a9b5dbca7
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/02/2018
ms.locfileid: "43462381"
---
# <a name="custom-channel-dispatcher"></a>사용자 지정 채널 디스패처
이 샘플에서는 <xref:System.ServiceModel.ServiceHostBase>를 직접 구현하여 사용자 지정 방식으로 채널 스택을 빌드하는 방법과 웹 호스트 환경에서 사용자 지정 채널 디스패처를 만드는 방법을 보여 줍니다. 채널 디스패처에서는 <xref:System.ServiceModel.Channels.IChannelListener>와 상호 작용하여 채널을 수락하고 채널 스택에서 메시지를 검색합니다. 또한 이 샘플에서는 <xref:System.ServiceModel.Activation.VirtualPathExtension>을 사용하여 웹 호스트 환경에서 채널 스택을 빌드하는 방법을 보여 주는 기본 샘플을 제공합니다.  
  
## <a name="custom-servicehostbase"></a>사용자 지정 ServiceHostBase  
 이 샘플에서는 기본 형식 구현 <xref:System.ServiceModel.ServiceHostBase> 대신 <xref:System.ServiceModel.ServiceHost> Windows Communication Foundation (WCF) 스택 구현을 채널 스택 맨 위에 있는 계층 처리 사용자 지정 메시지를 대체 하는 방법을 보여 줍니다. 가상 메서드 <xref:System.ServiceModel.ServiceHostBase.InitializeRuntime%2A>을 재정의하여 채널 수신기 및 채널 디스패처를 빌드합니다.  
  
 웹 호스팅 서비스를 구현하려면 전송 계층에서 호스팅 환경 설정, 즉 IIS(인터넷 정보 서비스)/WAS(Windows Process Activation Service) 설정을 기반으로 채널 수신기를 구성하는 방법을 알 수 있도록 <xref:System.ServiceModel.Activation.VirtualPathExtension> 컬렉션에서 서비스 확장 <xref:System.ServiceModel.ServiceHostBase.Extensions%2A>을 가져와 <xref:System.ServiceModel.Channels.BindingParameterCollection>에 추가합니다.  
  
## <a name="custom-channel-dispatcher"></a>사용자 지정 채널 디스패처  
 사용자 지정 채널 디스패처에서는 <xref:System.ServiceModel.Dispatcher.ChannelDispatcherBase> 형식을 확장합니다. 이 형식은 채널 계층 프로그래밍 논리를 구현합니다. 이 샘플에서는 요청-회신 메시지 교환 패턴에 <xref:System.ServiceModel.Channels.IReplyChannel>만 지원되지만 사용자 지정 채널 디스패처를 다른 채널 형식으로 손쉽게 확장할 수 있습니다.  
  
 디스패처에서는 먼저 채널 수신기를 연 다음 singleton 회신 채널을 수락합니다. 그런 다음 이 채널을 사용하여 무한 루프에 메시지(요청)를 보내기 시작합니다. 또한 각 요청에 대해 회신 메시지를 만들고 이를 다시 클라이언트에 보냅니다.  
  
## <a name="creating-a-response-message"></a>응답 메시지 만들기  
 메시지 처리는 `MyServiceManager` 형식에서 구현됩니다. `HandleRequest` 메서드에서는 메시지의 `Action` 헤더를 먼저 검사하여 요청이 지원되는지 여부를 확인합니다. SOAP 동작 미리 정의 된 "http://tempuri.org/HelloWorld/Hello" 메시지 필터링을 제공 하도록 정의 됩니다. 이것은 WCF 구현의 서비스 계약 개념과 비슷합니다 <xref:System.ServiceModel.ServiceHost>합니다.  
  
 올바른 SOAP 동작의 경우 샘플에서는 요청된 메시지 데이터를 검색하고 <xref:System.ServiceModel.ServiceHost>의 경우와 비슷하게 요청에 해당하는 응답을 생성합니다.  
  
 이 경우 브라우저에서 서비스를 찾아 올바르게 컴파일되었는지 확인할 수 있도록 사용자 지정 HTML 메시지를 반환하여 HTTP-GET 동사를 특별하게 처리했습니다. SOAP 동작이 일치하지 않는 경우에는 요청이 지원되지 않음을 나타내는 오류 메시지를 다시 보냅니다.  
  
 이 샘플의 클라이언트는 일반 WCF 클라이언트는 서비스에서 아무 것도 가정 하지 않습니다. 서비스는 일반 WCF에서 가져온 것에 맞게 특별히 고안 된 따라서<xref:System.ServiceModel.ServiceHost> 구현 합니다. 결과적으로 클라이언트에는 서비스 계약만 필요합니다.  
  
## <a name="using-the-sample"></a>샘플 사용  
 클라이언트 응용 프로그램을 직접 실행하면 다음과 같이 출력됩니다.  
  
```Output  
Client is talking to a request/reply WCF service.   
Type what you want to say to the server: Howdy  
Server replied: You said: Howdy. Message id: 1  
Server replied: You said: Howdy. Message id: 2  
Server replied: You said: Howdy. Message id: 3  
Server replied: You said: Howdy. Message id: 4  
Server replied: You said: Howdy. Message id: 5  
```  
  
 HTTP-GET 메시지가 서버에서 처리될 수 있도록 브라우저에서 서비스를 찾을 수도 있습니다. 이렇게 하면 제대로 구성된 HTML 텍스트를 다시 가져올 수 있습니다.  
  
> [!IMPORTANT]
>  컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다. 계속하기 전에 다음(기본) 디렉터리를 확인하세요.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  이 디렉터리가 없으면로 이동 [Windows Communication Foundation (WCF) 및.NET Framework 4 용 Windows WF (Workflow Foundation) 샘플](https://go.microsoft.com/fwlink/?LinkId=150780) 모든 Windows Communication Foundation (WCF)를 다운로드 하 고 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플. 이 샘플은 다음 디렉터리에 있습니다.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Extensibility\Channels\CustomChannelDispatcher`
