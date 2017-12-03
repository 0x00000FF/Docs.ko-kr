---
title: "사용자 지정 채널 디스패처"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 813acf03-9661-4d57-a3c7-eeab497321c6
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 81512576e1d26b63cf65b3a0c9992c2d273d2779
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/02/2017
---
# <a name="custom-channel-dispatcher"></a><span data-ttu-id="24bd5-102">사용자 지정 채널 디스패처</span><span class="sxs-lookup"><span data-stu-id="24bd5-102">Custom Channel Dispatcher</span></span>
<span data-ttu-id="24bd5-103">이 샘플에서는 <xref:System.ServiceModel.ServiceHostBase>를 직접 구현하여 사용자 지정 방식으로 채널 스택을 빌드하는 방법과 웹 호스트 환경에서 사용자 지정 채널 디스패처를 만드는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="24bd5-103">This sample demonstrates how to build the channel stack in a custom way by implementing <xref:System.ServiceModel.ServiceHostBase> directly and how to create a custom channel dispatcher in Web host environment.</span></span> <span data-ttu-id="24bd5-104">채널 디스패처에서는 <xref:System.ServiceModel.Channels.IChannelListener>와 상호 작용하여 채널을 수락하고 채널 스택에서 메시지를 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="24bd5-104">The channel dispatcher interacts with <xref:System.ServiceModel.Channels.IChannelListener> to accept channels and retrieves messages from the channel stack.</span></span> <span data-ttu-id="24bd5-105">또한 이 샘플에서는 <xref:System.ServiceModel.Activation.VirtualPathExtension>을 사용하여 웹 호스트 환경에서 채널 스택을 빌드하는 방법을 보여 주는 기본 샘플을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="24bd5-105">This sample also provides a basic sample to show how to build a channel stack in a Web host environment by using <xref:System.ServiceModel.Activation.VirtualPathExtension>.</span></span>  
  
## <a name="custom-servicehostbase"></a><span data-ttu-id="24bd5-106">사용자 지정 ServiceHostBase</span><span class="sxs-lookup"><span data-stu-id="24bd5-106">Custom ServiceHostBase</span></span>  
 <span data-ttu-id="24bd5-107">이 샘플에서는 <xref:System.ServiceModel.ServiceHostBase> 대신 기본 형식 <xref:System.ServiceModel.ServiceHost>를 구현하여 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 스택 구현을 채널 스택 맨 위의 사용자 지정 메시지 처리 계층으로 대체하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="24bd5-107">This sample implements the base type <xref:System.ServiceModel.ServiceHostBase> instead of <xref:System.ServiceModel.ServiceHost> to demonstrate how to replace the [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] stack implementation with a custom message handling layer on top of the channel stack.</span></span> <span data-ttu-id="24bd5-108">가상 메서드 <xref:System.ServiceModel.ServiceHostBase.InitializeRuntime%2A>을 재정의하여 채널 수신기 및 채널 디스패처를 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="24bd5-108">You override the virtual method <xref:System.ServiceModel.ServiceHostBase.InitializeRuntime%2A> to build channel listeners and the channel dispatcher.</span></span>  
  
 <span data-ttu-id="24bd5-109">웹 호스팅 서비스를 구현하려면 전송 계층에서 호스팅 환경 설정, 즉 IIS(인터넷 정보 서비스)/WAS(Windows Process Activation Service) 설정을 기반으로 채널 수신기를 구성하는 방법을 알 수 있도록 <xref:System.ServiceModel.Activation.VirtualPathExtension> 컬렉션에서 서비스 확장 <xref:System.ServiceModel.ServiceHostBase.Extensions%2A>을 가져와 <xref:System.ServiceModel.Channels.BindingParameterCollection>에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="24bd5-109">To implement a Web-hosted service, get the service extension <xref:System.ServiceModel.Activation.VirtualPathExtension> from the <xref:System.ServiceModel.ServiceHostBase.Extensions%2A> collection and add it to the <xref:System.ServiceModel.Channels.BindingParameterCollection> so that the transport layer knows how to configure the channel listener based on the hosting environment settings, that is, the Internet Information Services (IIS)/Windows Process Activation Service (WAS) settings.</span></span>  
  
## <a name="custom-channel-dispatcher"></a><span data-ttu-id="24bd5-110">사용자 지정 채널 디스패처</span><span class="sxs-lookup"><span data-stu-id="24bd5-110">Custom Channel Dispatcher</span></span>  
 <span data-ttu-id="24bd5-111">사용자 지정 채널 디스패처에서는 <xref:System.ServiceModel.Dispatcher.ChannelDispatcherBase> 형식을 확장합니다.</span><span class="sxs-lookup"><span data-stu-id="24bd5-111">The custom channel dispatcher extends the type <xref:System.ServiceModel.Dispatcher.ChannelDispatcherBase>.</span></span> <span data-ttu-id="24bd5-112">이 형식은 채널 계층 프로그래밍 논리를 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="24bd5-112">This type implements the channel-layer programming logic.</span></span> <span data-ttu-id="24bd5-113">이 샘플에서는 요청-회신 메시지 교환 패턴에 <xref:System.ServiceModel.Channels.IReplyChannel>만 지원되지만 사용자 지정 채널 디스패처를 다른 채널 형식으로 손쉽게 확장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="24bd5-113">In this sample, only <xref:System.ServiceModel.Channels.IReplyChannel> is supported for request-reply message exchange pattern, but the custom channel dispatcher can be easily extended to other channel types.</span></span>  
  
 <span data-ttu-id="24bd5-114">디스패처에서는 먼저 채널 수신기를 연 다음 singleton 회신 채널을 수락합니다.</span><span class="sxs-lookup"><span data-stu-id="24bd5-114">The dispatcher first opens the channel listener and then accepts the singleton reply channel.</span></span> <span data-ttu-id="24bd5-115">그런 다음 이 채널을 사용하여 무한 루프에 메시지(요청)를 보내기 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="24bd5-115">With the channel, it starts to send messages (requests) in an infinite loop.</span></span> <span data-ttu-id="24bd5-116">또한 각 요청에 대해 회신 메시지를 만들고 이를 다시 클라이언트에 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="24bd5-116">For each request, it creates a reply message and sends it back to the client.</span></span>  
  
## <a name="creating-a-response-message"></a><span data-ttu-id="24bd5-117">응답 메시지 만들기</span><span class="sxs-lookup"><span data-stu-id="24bd5-117">Creating a Response Message</span></span>  
 <span data-ttu-id="24bd5-118">메시지 처리는 `MyServiceManager` 형식에서 구현됩니다.</span><span class="sxs-lookup"><span data-stu-id="24bd5-118">The message processing is implemented in the type `MyServiceManager`.</span></span> <span data-ttu-id="24bd5-119">`HandleRequest` 메서드에서는 메시지의 `Action` 헤더를 먼저 검사하여 요청이 지원되는지 여부를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="24bd5-119">In the `HandleRequest` method, the `Action` header of the message is first checked to see whether the request is supported.</span></span> <span data-ttu-id="24bd5-120">미리 정의된 SOAP 동작 "http://tempuri.org/HelloWorld/Hello"는 메시지 필터링을 제공하도록 정의되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="24bd5-120">A predefined SOAP action "http://tempuri.org/HelloWorld/Hello" is defined to provide message filtering.</span></span> <span data-ttu-id="24bd5-121">이는 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]에서 구현하는 <xref:System.ServiceModel.ServiceHost>의 서비스 계약 개념과 비슷합니다.</span><span class="sxs-lookup"><span data-stu-id="24bd5-121">This is similar to the service contract concept in the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] implementation of <xref:System.ServiceModel.ServiceHost>.</span></span>  
  
 <span data-ttu-id="24bd5-122">올바른 SOAP 동작의 경우 샘플에서는 요청된 메시지 데이터를 검색하고 <xref:System.ServiceModel.ServiceHost>의 경우와 비슷하게 요청에 해당하는 응답을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="24bd5-122">For the correct SOAP action case, the sample retrieves the requested message data and generates a corresponding response to the request similar to what is seen in the <xref:System.ServiceModel.ServiceHost> case.</span></span>  
  
 <span data-ttu-id="24bd5-123">이 경우 브라우저에서 서비스를 찾아 올바르게 컴파일되었는지 확인할 수 있도록 사용자 지정 HTML 메시지를 반환하여 HTTP-GET 동사를 특별하게 처리했습니다.</span><span class="sxs-lookup"><span data-stu-id="24bd5-123">You specially handled the HTTP-GET verb by returning a custom HTML message, in this, case so that you can browse the service from a browser to see that it is compiled correctly.</span></span> <span data-ttu-id="24bd5-124">SOAP 동작이 일치하지 않는 경우에는 요청이 지원되지 않음을 나타내는 오류 메시지를 다시 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="24bd5-124">If the SOAP action does not match, send a fault message back to indicate that the request is not supported.</span></span>  
  
 <span data-ttu-id="24bd5-125">이 샘플의 클라이언트는 서비스에서 아무 것도 가정하지 않는 일반적인 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 클라이언트입니다.</span><span class="sxs-lookup"><span data-stu-id="24bd5-125">The client of this sample is a normal [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] client that does not assume anything from the service.</span></span> <span data-ttu-id="24bd5-126">따라서 서비스는 일반적인 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<xref:System.ServiceModel.ServiceHost> 구현에서 가져온 것과 일치하도록 특별하게 디자인되었습니다.</span><span class="sxs-lookup"><span data-stu-id="24bd5-126">So, the service is specially designed to match what you get from a normal [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<xref:System.ServiceModel.ServiceHost> implementation.</span></span> <span data-ttu-id="24bd5-127">결과적으로 클라이언트에는 서비스 계약만 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="24bd5-127">As a result, only a service contract is required on the client.</span></span>  
  
## <a name="using-the-sample"></a><span data-ttu-id="24bd5-128">샘플 사용</span><span class="sxs-lookup"><span data-stu-id="24bd5-128">Using the sample</span></span>  
 <span data-ttu-id="24bd5-129">클라이언트 응용 프로그램을 직접 실행하면 다음과 같이 출력됩니다.</span><span class="sxs-lookup"><span data-stu-id="24bd5-129">Running the client application directly produces the following output.</span></span>  
  
```Output  
Client is talking to a request/reply WCF service.   
Type what you want to say to the server: Howdy  
Server replied: You said: Howdy. Message id: 1  
Server replied: You said: Howdy. Message id: 2  
Server replied: You said: Howdy. Message id: 3  
Server replied: You said: Howdy. Message id: 4  
Server replied: You said: Howdy. Message id: 5  
```  
  
 <span data-ttu-id="24bd5-130">HTTP-GET 메시지가 서버에서 처리될 수 있도록 브라우저에서 서비스를 찾을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="24bd5-130">You can also browse the service from a browser so that an HTTP-GET message gets processed on the server.</span></span> <span data-ttu-id="24bd5-131">이렇게 하면 제대로 구성된 HTML 텍스트를 다시 가져올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="24bd5-131">This gets you well-formatted HTML text back.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="24bd5-132">컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="24bd5-132">The samples may already be installed on your machine.</span></span> <span data-ttu-id="24bd5-133">계속하기 전에 다음(기본) 디렉터리를 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="24bd5-133">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="24bd5-134">이 디렉터리가 없으면 [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4(.NET Framework 4용 WCF(Windows Communication Foundation) 및 WF(Windows Workflow Foundation) 샘플)](http://go.microsoft.com/fwlink/?LinkId=150780) 로 이동하여 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 및 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플을 모두 다운로드하세요.</span><span class="sxs-lookup"><span data-stu-id="24bd5-134">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="24bd5-135">이 샘플은 다음 디렉터리에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="24bd5-135">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Extensibility\Channels\CustomChannelDispatcher`
