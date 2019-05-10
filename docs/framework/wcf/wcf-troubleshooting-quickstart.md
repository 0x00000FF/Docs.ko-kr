---
title: WCF 문제 해결 퀵 스타트
ms.date: 03/30/2017
helpviewer_keywords:
- WCF [WCF], troubleshooting
- Windows Communication Foundation [WCF], troubleshooting
ms.assetid: a9ea7a53-f31a-46eb-806e-898e465a4992
ms.openlocfilehash: 6d631d51cc4f40b5be91b6579039a8b8dffa3dee
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/28/2019
ms.locfileid: "64613208"
---
# <a name="wcf-troubleshooting-quickstart"></a><span data-ttu-id="d7e8e-102">WCF 문제 해결 퀵 스타트</span><span class="sxs-lookup"><span data-stu-id="d7e8e-102">WCF Troubleshooting Quickstart</span></span>
<span data-ttu-id="d7e8e-103">이 항목에서는 WCF 클라이언트 및 서비스를 개발하는 동안 발생하는 몇 가지 알려진 문제점을 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="d7e8e-103">This topic lists a number of known issues customers have run into while developing WCF clients and services.</span></span> <span data-ttu-id="d7e8e-104">발생하는 문제가 이 목록에 없는 경우 서비스에 대한 추적을 구성하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="d7e8e-104">If the issue you are running into is not in this list, we recommend you configure tracing for your service.</span></span> <span data-ttu-id="d7e8e-105">추적을 구성하면 추적 파일 뷰어로 보고 서비스 내에서 발생하는 예외에 대한 자세한 정보를 얻을 수 있는 추적 파일이 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="d7e8e-105">This will generate a trace file that you can view with the trace file viewer and get detailed information about exceptions that may be occurring within the service.</span></span> <span data-ttu-id="d7e8e-106">추적 구성에 대 한 자세한 내용은 다음을 참조 하세요. [추적 구성](../../../docs/framework/wcf/diagnostics/tracing/configuring-tracing.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="d7e8e-106">For more information on configuring tracing, see: [Configuring Tracing](../../../docs/framework/wcf/diagnostics/tracing/configuring-tracing.md).</span></span> <span data-ttu-id="d7e8e-107">추적 파일 뷰어에 대 한 자세한 내용은 다음을 참조 하세요. [서비스 추적 뷰어 도구 (SvcTraceViewer.exe)](../../../docs/framework/wcf/service-trace-viewer-tool-svctraceviewer-exe.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="d7e8e-107">For more information on the trace file viewer, see: [Service Trace Viewer Tool (SvcTraceViewer.exe)](../../../docs/framework/wcf/service-trace-viewer-tool-svctraceviewer-exe.md).</span></span>  
  
1. [<span data-ttu-id="d7e8e-108">Windows 7 및 IIS를 설치한 후 WCF 서비스를 탐색 하려고 하는 경우는 다음과 같은 오류 메시지가: HTTP 오류 404.3 – 찾을 수 없음</span><span class="sxs-lookup"><span data-stu-id="d7e8e-108">After installing Windows 7 and IIS, when I attempt to browse to a WCF service I get the following error message: HTTP Error 404.3 – Not Found</span></span>](../../../docs/framework/wcf/wcf-troubleshooting-quickstart.md#bkmk_0)  
  
     <span data-ttu-id="d7e8e-109">HTTP 오류 404.3 – 찾을 수 없음. 확장명 구성으로 인해 요청한 페이지를 제공할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d7e8e-109">HTTP Error 404.3 – Not FoundThe page you are requesting cannot be served because of the extension configuration.</span></span> <span data-ttu-id="d7e8e-110">페이지가 스크립트인 경우 처리기를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="d7e8e-110">If the page is a script, add a handler.</span></span> <span data-ttu-id="d7e8e-111">파일을 다운로드해야 하는 경우 MIME 맵을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="d7e8e-111">If the file should be downloaded, add a MIME map.</span></span> <span data-ttu-id="d7e8e-112">자세한 오류 정보 모듈은 StaticFileModule입니다.</span><span class="sxs-lookup"><span data-stu-id="d7e8e-112">Detailed Error InformationModule StaticFileModule.</span></span>  
  
2. [<span data-ttu-id="d7e8e-113">첫 번째 요청 이후 클라이언트가 잠시 유휴 상태일 때 가끔씩 두 번째 요청에서 MessageSecurityException이 발생합니다. 이유가 무엇입니까?</span><span class="sxs-lookup"><span data-stu-id="d7e8e-113">Sometimes I receive a MessageSecurityException on the second request if my client is idle for a while after the first request. What is happening?</span></span>](../../../docs/framework/wcf/wcf-troubleshooting-quickstart.md#BKMK_q1)  
  
3. [<span data-ttu-id="d7e8e-114">서비스와 상호 작용하는 클라이언트의 수가 약 10개를 넘으면 서비스가 새 클라이언트를 거부하기 시작합니다. 이유가 무엇입니까?</span><span class="sxs-lookup"><span data-stu-id="d7e8e-114">My service starts to reject new clients after about 10 clients are interacting with it. What is happening?</span></span>](../../../docs/framework/wcf/wcf-troubleshooting-quickstart.md#BKMK_q2)  
  
4. [<span data-ttu-id="d7e8e-115">WCF 응용 프로그램의 구성 파일이 아닌 다른 위치에서 서비스 구성을 로드할 수 있습니까?</span><span class="sxs-lookup"><span data-stu-id="d7e8e-115">Can I load my service configuration from somewhere other than the WCF application’s configuration file?</span></span>](../../../docs/framework/wcf/wcf-troubleshooting-quickstart.md#BKMK_q3)  
  
5. [<span data-ttu-id="d7e8e-116">서비스와 클라이언트는 문제없이 작동하는데 클라이언트가 다른 컴퓨터에 있으면 둘 다 제대로 작동하지 않습니다. 이유가 무엇입니까?</span><span class="sxs-lookup"><span data-stu-id="d7e8e-116">My service and client work great, but I can’t get them to work when the client is on another computer? What’s happening?</span></span>](../../../docs/framework/wcf/wcf-troubleshooting-quickstart.md#BKMK_q4)  
  
6. [<span data-ttu-id="d7e8e-117">FaultException을 발생 하면\<예외 > 예외 형식이 인 경우 항상 받습니다 일반 FaultException 형식을 클라이언트에서 제네릭 형식이 아닌 합니다. 이유가 무엇입니까?</span><span class="sxs-lookup"><span data-stu-id="d7e8e-117">When I throw a FaultException\<Exception> where the type is an exception, I always receive a general FaultException type on the client and not the generic type. What’s happening?</span></span>](../../../docs/framework/wcf/wcf-troubleshooting-quickstart.md#BKMK_q5)  
  
7. [<span data-ttu-id="d7e8e-118">회신에 데이터가 포함되지 않은 경우 단방향 및 요청-회신 작업이 거의 같은 속도로 반환되는 것 같습니다. 이유가 무엇입니까?</span><span class="sxs-lookup"><span data-stu-id="d7e8e-118">It seems like one-way and request-reply operations return at roughly the same speed when the reply contains no data. What's happening?</span></span>](../../../docs/framework/wcf/wcf-troubleshooting-quickstart.md#BKMK_q6)  
  
8. [<span data-ttu-id="d7e8e-119">서비스에 X.509 인증서를 사용하고 있으며 System.Security.Cryptography.CryptographicException이 발생합니다. 이유가 무엇입니까?</span><span class="sxs-lookup"><span data-stu-id="d7e8e-119">I’m using an X.509 certificate with my service and I get a System.Security.Cryptography.CryptographicException. What’s happening?</span></span>](../../../docs/framework/wcf/wcf-troubleshooting-quickstart.md#BKMK_q77)  
  
9. [<span data-ttu-id="d7e8e-120">작업의 첫 번째 매개 변수를 대문자에서 소문자로 변경한 다음에 클라이언트에서 예외가 throw됩니다. 이유가 무엇입니까?</span><span class="sxs-lookup"><span data-stu-id="d7e8e-120">I changed the first parameter of an operation from uppercase to lowercase; now my client throws an exception. What's happening?</span></span>](../../../docs/framework/wcf/wcf-troubleshooting-quickstart.md#BKMK_q88)  
  
10. [<span data-ttu-id="d7e8e-121">추적 도구 중 하나를 사용하는 동안 EndpointNotFoundException이 발생합니다. 이유가 무엇입니까?</span><span class="sxs-lookup"><span data-stu-id="d7e8e-121">I’m using one of my tracing tools and I get an EndpointNotFoundException. What’s happening?</span></span>](../../../docs/framework/wcf/wcf-troubleshooting-quickstart.md#BKMK_q99)  
  
11. [<span data-ttu-id="d7e8e-122">WCF SOAP 응용 프로그램에서 WCF 웹 HTTP 응용 프로그램을 호출할 때 서비스에 다음 오류를 반환 합니다. 405 메서드가 허용 되지 않습니다</span><span class="sxs-lookup"><span data-stu-id="d7e8e-122">When calling a WCF Web HTTP application from a WCF SOAP application the service returns the following error: 405 Method Not Allowed</span></span>](../../../docs/framework/wcf/wcf-troubleshooting-quickstart.md#BK_MK99)  
  
 [<span data-ttu-id="d7e8e-123">기본 주소란 무엇입니까? 엔드포인트 주소와는 어떤 관계가 있습니까?</span><span class="sxs-lookup"><span data-stu-id="d7e8e-123">What is the base address? How does it relate to an endpoint address?</span></span>](../../../docs/framework/wcf/wcf-troubleshooting-quickstart.md#BKMK_q10)  
  
<a name="bkmk_0"></a>   
## <a name="after-installing-windows-7-and-iis-when-i-attempt-to-browse-to-a-wcf-service-i-get-the-following-error-message-http-error-4043--not-found"></a><span data-ttu-id="d7e8e-124">Windows 7 및 IIS를 설치한 후 WCF 서비스를 탐색 하려고 하는 경우는 다음과 같은 오류 메시지가: HTTP 오류 404.3 – 찾을 수 없음</span><span class="sxs-lookup"><span data-stu-id="d7e8e-124">After installing Windows 7 and IIS, when I attempt to browse to a WCF service I get the following error message: HTTP Error 404.3 – Not Found</span></span>  
 <span data-ttu-id="d7e8e-125">전체 오류 메시지는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="d7e8e-125">The full error message is:</span></span>  
  
 <span data-ttu-id="d7e8e-126">HTTP 오류 404.3 – 찾을 수 없음. 확장명 구성으로 인해 요청한 페이지를 제공할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d7e8e-126">HTTP Error 404.3 – Not FoundThe page you are requesting cannot be served because of the extension configuration.</span></span> <span data-ttu-id="d7e8e-127">페이지가 스크립트인 경우 처리기를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="d7e8e-127">If the page is a script, add a handler.</span></span> <span data-ttu-id="d7e8e-128">파일을 다운로드해야 하는 경우 MIME 맵을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="d7e8e-128">If the file should be downloaded, add a MIME map.</span></span> <span data-ttu-id="d7e8e-129">자세한 오류 정보 모듈은 StaticFileModule입니다.</span><span class="sxs-lookup"><span data-stu-id="d7e8e-129">Detailed Error InformationModule StaticFileModule.</span></span>  
  
 <span data-ttu-id="d7e8e-130">이 오류 메시지는 "Windows Communication Foundation HTTP 활성화" 제어판에서 명시적으로 설정 하지 않은 경우에 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="d7e8e-130">This error message occurs when "Windows Communication Foundation HTTP Activation" is not explicitly set in the Control Panel.</span></span> <span data-ttu-id="d7e8e-131">이를 설정하려면 제어판으로 이동하고 창 왼쪽 아래 모서리에서 프로그램을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="d7e8e-131">To set this go to the Control Panel, click Programs in the lower left hand corner of the window.</span></span> <span data-ttu-id="d7e8e-132">Windows 기능 사용/사용 안 함을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="d7e8e-132">Click Turn Windows features on or off.</span></span> <span data-ttu-id="d7e8e-133">Microsoft .NET Framework 3.5.1을 확장하고 Windows Communication Foundation HTTP 활성화를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="d7e8e-133">Expand Microsoft .NET Framework 3.5.1 and select Windows Communication Foundation HTTP Activation.</span></span>  
  
<a name="BKMK_q1"></a>   
## <a name="sometimes-i-receive-a-messagesecurityexception-on-the-second-request-if-my-client-is-idle-for-a-while-after-the-first-request-what-is-happening"></a><span data-ttu-id="d7e8e-134">첫 번째 요청 이후 클라이언트가 잠시 유휴 상태일 때 가끔씩 두 번째 요청에서 MessageSecurityException이 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="d7e8e-134">Sometimes I receive a MessageSecurityException on the second request if my client is idle for a while after the first request.</span></span> <span data-ttu-id="d7e8e-135">이유가 무엇입니까?</span><span class="sxs-lookup"><span data-stu-id="d7e8e-135">What is happening?</span></span>  
 <span data-ttu-id="d7e8e-136">두 번째 요청은 주로 두 가지 이유로 실패할 수 있습니다. (1) 세션 시간이 초과 되었습니다 또는 서비스를 호스팅하는 웹 서버 (2)는 재활용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d7e8e-136">The second request can fail primarily for two reasons: (1) the session has timed out or (2) the Web server that is hosting the service is recycled.</span></span> <span data-ttu-id="d7e8e-137">첫 번째 경우 세션은 서비스가 시간 제한을 초과할 때까지 유효합니다. 서비스는 서비스의 바인딩(<xref:System.ServiceModel.Channels.Binding.ReceiveTimeout%2A>)에 지정된 시간 내에 클라이언트가 보낸 요청을 받지 못하면 보안 세션을 종료합니다.</span><span class="sxs-lookup"><span data-stu-id="d7e8e-137">In the first case, the session is valid until the service times out. When the service does not receive a request from the client within the period of time specified in the service's binding (<xref:System.ServiceModel.Channels.Binding.ReceiveTimeout%2A>), the service terminates the security session.</span></span> <span data-ttu-id="d7e8e-138">이후로 클라이언트 메시지가 전송되면 <xref:System.ServiceModel.Security.MessageSecurityException>이 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="d7e8e-138">Subsequent client messages result in the <xref:System.ServiceModel.Security.MessageSecurityException>.</span></span> <span data-ttu-id="d7e8e-139">클라이언트는 이후로 메시지를 보내거나 상태 저장 보안 컨텍스트 토큰을 사용하려면 서비스와의 보안 세션을 다시 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d7e8e-139">The client must re-establish a secure session with the service to send future messages or use a stateful security context token.</span></span> <span data-ttu-id="d7e8e-140">상태 저장 보안 컨텍스트 토큰을 사용하여 웹 서버가 재생되는 동안 보안 세션이 유지되도록 할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d7e8e-140">Stateful security context tokens also allow a secure session to survive a Web server being recycled.</span></span> <span data-ttu-id="d7e8e-141">보안 세션에서 상태 저장 보안 컨텍스트 토큰을 사용 하는 방법에 대 한 자세한 내용은 참조 하세요. [방법: 보안 컨텍스트를 만들 보안 세션에 대 한 토큰](../../../docs/framework/wcf/feature-details/how-to-create-a-security-context-token-for-a-secure-session.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="d7e8e-141">For more information about using stateful secure context tokens in a secure session, see [How to: Create a Security Context Token for a Secure Session](../../../docs/framework/wcf/feature-details/how-to-create-a-security-context-token-for-a-secure-session.md).</span></span> <span data-ttu-id="d7e8e-142">또는 보안 세션을 사용하지 않도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d7e8e-142">Alternatively, you can disable secure sessions.</span></span> <span data-ttu-id="d7e8e-143">사용 하는 경우는 [ \<wsHttpBinding >](../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md) 바인딩을 설정할 수 있습니다 합니다 `establishSecurityContext` 속성을 `false` 보안 세션을 사용 하지 않도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="d7e8e-143">When you use the [\<wsHttpBinding>](../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md) binding, you can set the `establishSecurityContext` property to `false` to disable secure sessions.</span></span> <span data-ttu-id="d7e8e-144">다른 바인딩의 보안 세션을 사용하지 않도록 설정하려면 사용자 지정 바인딩을 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d7e8e-144">To disable secure sessions for other bindings, you must create a custom binding.</span></span> <span data-ttu-id="d7e8e-145">사용자 지정 바인딩을 만드는 방법에 대 한 자세한 내용은 참조 하세요. [방법: SecurityBindingElement를 사용 하 여 사용자 지정 바인딩을 만들려면](../../../docs/framework/wcf/feature-details/how-to-create-a-custom-binding-using-the-securitybindingelement.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="d7e8e-145">For details about creating a custom binding, see [How to: Create a Custom Binding Using the SecurityBindingElement](../../../docs/framework/wcf/feature-details/how-to-create-a-custom-binding-using-the-securitybindingelement.md).</span></span> <span data-ttu-id="d7e8e-146">이러한 옵션을 적용하기 전에 먼저 애플리케이션의 보안 요구 사항을 이해해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d7e8e-146">Before you apply any of these options, you must understand your application's security requirements.</span></span>  
  
<a name="BKMK_q2"></a>   
## <a name="my-service-starts-to-reject-new-clients-after-about-10-clients-are-interacting-with-it-what-is-happening"></a><span data-ttu-id="d7e8e-147">서비스와 상호 작용하는 클라이언트의 수가 약 10개를 넘으면 서비스가 새 클라이언트를 거부하기 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="d7e8e-147">My service starts to reject new clients after about 10 clients are interacting with it.</span></span> <span data-ttu-id="d7e8e-148">이유가 무엇입니까?</span><span class="sxs-lookup"><span data-stu-id="d7e8e-148">What is happening?</span></span>  
 <span data-ttu-id="d7e8e-149">기본적으로 서비스는 10개의 동시 세션만 지원할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d7e8e-149">By default, services can have only 10 concurrent sessions.</span></span> <span data-ttu-id="d7e8e-150">따라서 서비스 바인딩에서 세션을 사용하는 경우 서비스는 이 숫자에 도달할 때까지 새 클라이언트 연결을 수락하고, 그 후에는 현재 세션 중 하나가 끝날 때까지 새 클라이언트 연결을 거부합니다.</span><span class="sxs-lookup"><span data-stu-id="d7e8e-150">Therefore, if the service bindings use sessions, the service accepts new client connections until it reaches that number, after which it refuses new client connections until one of the current sessions ends.</span></span> <span data-ttu-id="d7e8e-151">여러 가지 방법을 통해 더 많은 클라이언트를 지원할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d7e8e-151">You can support more clients in a number of ways.</span></span> <span data-ttu-id="d7e8e-152">먼저, 서비스에 세션이 필요하지 않은 경우 세션 바인딩을 사용하지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d7e8e-152">If your service does not require sessions, do not use a sessionful binding.</span></span> <span data-ttu-id="d7e8e-153">(자세한 내용은 [를 사용 하 여 세션](../../../docs/framework/wcf/using-sessions.md).) 또 다른 방법으로, <xref:System.ServiceModel.Description.ServiceThrottlingBehavior.MaxConcurrentSessions%2A> 속성의 값을 사용자의 환경에 적절하게 변경하여 세션 제한을 높일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d7e8e-153">(For more information, see [Using Sessions](../../../docs/framework/wcf/using-sessions.md).) Another option is to increase the session limit by changing the value of the <xref:System.ServiceModel.Description.ServiceThrottlingBehavior.MaxConcurrentSessions%2A> property to the number appropriate to your circumstance.</span></span>  
  
<a name="BKMK_q3"></a>   
## <a name="can-i-load-my-service-configuration-from-somewhere-other-than-the-wcf-applications-configuration-file"></a><span data-ttu-id="d7e8e-154">WCF 애플리케이션의 구성 파일이 아닌 다른 위치에서 서비스 구성을 로드할 수 있습니까?</span><span class="sxs-lookup"><span data-stu-id="d7e8e-154">Can I load my service configuration from somewhere other than the WCF application’s configuration file?</span></span>  
 <span data-ttu-id="d7e8e-155">예. 그러나 <xref:System.ServiceModel.ServiceHost> 메서드를 재정의하는 사용자 지정 <xref:System.ServiceModel.ServiceHostBase.ApplyConfiguration%2A> 클래스를 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d7e8e-155">Yes, however, you have to create a custom <xref:System.ServiceModel.ServiceHost> class that overrides the <xref:System.ServiceModel.ServiceHostBase.ApplyConfiguration%2A> method.</span></span> <span data-ttu-id="d7e8e-156">이 메서드 내에서 기본을 호출하여 구성을 먼저 로드할 수 있으며(표준 구성 정보도 함께 로드하려는 경우), 또한 구성 로딩 시스템을 완전히 바꿀 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d7e8e-156">Inside that method, you can call the base to load configuration first (if you want to load the standard configuration information as well) but you can also entirely replace the configuration loading system.</span></span> <span data-ttu-id="d7e8e-157">애플리케이션 구성 파일과 다른 구성 파일에서 구성을 로드하려는 경우에는 구성 파일을 직접 구문 분석하고 구성을 로드해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d7e8e-157">Note that if you want to load configuration from a configuration file that is different from the application configuration file, you must parse the configuration file yourself and load the configuration.</span></span>  
  
 <span data-ttu-id="d7e8e-158">다음 코드 예제는 <xref:System.ServiceModel.ServiceHostBase.ApplyConfiguration%2A> 메서드를 재정의하고 엔드포인트를 직접 구성하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="d7e8e-158">The following code example shows how to override the <xref:System.ServiceModel.ServiceHostBase.ApplyConfiguration%2A> method and directly configure an endpoint.</span></span>  
  
```csharp
public class MyServiceHost : ServiceHost  
{  
    public MyServiceHost(Type serviceType, params Uri[] baseAddresses)    
      : base(serviceType, baseAddresses)  
    {
        Console.WriteLine("MyServiceHost Constructor");
    }  
  
    protected override void ApplyConfiguration()  
    {  
        string straddress = GetAddress();  
        Uri address = new Uri(straddress);  
        Binding binding = GetBinding();  
        base.AddServiceEndpoint(typeof(IData), binding, address);  
    }  
  
    string GetAddress()  
    {
        return "http://MyMachine:7777/MyEndpointAddress/";
    }  
  
    Binding GetBinding()  
    {  
        WSHttpBinding binding = new WSHttpBinding();  
        binding.Security.Mode = SecurityMode.None;  
        return binding;  
    }  
}  
```  
  
<a name="BKMK_q4"></a>   
## <a name="my-service-and-client-work-great-but-i-cant-get-them-to-work-when-the-client-is-on-another-computer-whats-happening"></a><span data-ttu-id="d7e8e-159">서비스와 클라이언트는 문제없이 작동하는데 클라이언트가 다른 컴퓨터에 있으면 둘 다 제대로 작동하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d7e8e-159">My service and client work great, but I can’t get them to work when the client is on another computer?</span></span> <span data-ttu-id="d7e8e-160">이유가 무엇입니까?</span><span class="sxs-lookup"><span data-stu-id="d7e8e-160">What’s happening?</span></span>  
 <span data-ttu-id="d7e8e-161">예외에 따라 여러 가지 문제가 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d7e8e-161">Depending upon the exception, there may be several issues:</span></span>  
  
- <span data-ttu-id="d7e8e-162">클라이언트 엔드포인트 주소를 "localhost" 대신 호스트 이름으로 변경해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d7e8e-162">You might need to change the client endpoint addresses to the host name and not "localhost".</span></span>  
  
- <span data-ttu-id="d7e8e-163">애플리케이션에 연결되는 포트를 열어야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d7e8e-163">You might need to open the port to the application.</span></span> <span data-ttu-id="d7e8e-164">자세한 내용은 SDK 샘플에서 [Firewall Instructions](../../../docs/framework/wcf/samples/firewall-instructions.md) 을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="d7e8e-164">For details, see [Firewall Instructions](../../../docs/framework/wcf/samples/firewall-instructions.md) from the SDK samples.</span></span>  
  
- <span data-ttu-id="d7e8e-165">다른 가능한 문제에 대 한 샘플 항목을 참조 하세요 [Windows Communication Foundation 샘플 실행](./samples/running-the-samples.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="d7e8e-165">For other possible issues, see the samples topic [Running the Windows Communication Foundation Samples](./samples/running-the-samples.md).</span></span>  
  
- <span data-ttu-id="d7e8e-166">클라이언트가 Windows 자격 증명을 사용하고 예외가 <xref:System.ServiceModel.Security.SecurityNegotiationException>인 경우 다음과 같이 Kerberos를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="d7e8e-166">If your client is using Windows credentials and the exception is a <xref:System.ServiceModel.Security.SecurityNegotiationException>, configure Kerberos as follows.</span></span>  
  
    1. <span data-ttu-id="d7e8e-167">클라이언트 App.config 파일의 엔드포인트 요소에 ID 자격 증명을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="d7e8e-167">Add the identity credentials to the endpoint element in the client’s App.config file:</span></span>  
  
        ```xml
        <endpoint   
          address="http://MyServer:8000/MyService/"   
          binding="wsHttpBinding"   
          bindingConfiguration="WSHttpBinding_IServiceExample"   
          contract="IServiceExample"   
          behaviorConfiguration="ClientCredBehavior"   
          name="WSHttpBinding_IServiceExample">  
          <identity>  
            <userPrincipalName value="name@corp.contoso.com"/>  
          </identity>  
        </endpoint>  
        ```  
  
    2. <span data-ttu-id="d7e8e-168">System 또는 NetworkService 계정으로 자체 호스팅 서비스를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="d7e8e-168">Run the self-hosted service under the System or NetworkService account.</span></span> <span data-ttu-id="d7e8e-169">다음 명령을 실행하여 System 계정으로 명령 창을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d7e8e-169">You can run this command to create a command window under the System account:</span></span>  
  
        ```console
        at 12:36 /interactive "cmd.exe"  
        ```  
  
    3. <span data-ttu-id="d7e8e-170">기본적으로 SPN(서비스 사용자 이름) 계정을 사용하는 IIS(인터넷 정보 서비스)에서 서비스를 호스팅합니다.</span><span class="sxs-lookup"><span data-stu-id="d7e8e-170">Host the service under Internet Information Services (IIS), which, by default, uses the service principal name (SPN) account.</span></span>  
  
    4. <span data-ttu-id="d7e8e-171">SetSPN을 사용하여 도메인에 새 SPN을 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="d7e8e-171">Register a new SPN with the domain using SetSPN.</span></span> <span data-ttu-id="d7e8e-172">이 작업을 수행하려면 도메인 관리자여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d7e8e-172">Note that you will need to be a domain administrator in order to do this.</span></span>  
  
 <span data-ttu-id="d7e8e-173">Kerberos 프로토콜에 대 한 자세한 내용은 참조 하세요. [Security Concepts Used in WCF](../../../docs/framework/wcf/feature-details/security-concepts-used-in-wcf.md) 및:</span><span class="sxs-lookup"><span data-stu-id="d7e8e-173">For more information about the Kerberos protocol, see [Security Concepts Used in WCF](../../../docs/framework/wcf/feature-details/security-concepts-used-in-wcf.md) and:</span></span>  
  
- [<span data-ttu-id="d7e8e-174">Windows 인증 오류 디버깅</span><span class="sxs-lookup"><span data-stu-id="d7e8e-174">Debugging Windows Authentication Errors</span></span>](../../../docs/framework/wcf/feature-details/debugging-windows-authentication-errors.md)  
  
- [<span data-ttu-id="d7e8e-175">Http.sys를 사용하여 Kerberos 서비스 보안 주체 이름 등록(영문 페이지일 수 있음)</span><span class="sxs-lookup"><span data-stu-id="d7e8e-175">Registering Kerberos Service Principal Names by Using Http.sys</span></span>](https://go.microsoft.com/fwlink/?LinkId=86943)  
  
- [<span data-ttu-id="d7e8e-176">Kerberos 설명(영문 페이지일 수 있음)</span><span class="sxs-lookup"><span data-stu-id="d7e8e-176">Kerberos Explained</span></span>](https://go.microsoft.com/fwlink/?LinkId=86946)  
  
<a name="BKMK_q5"></a>   
## <a name="when-i-throw-a-faultexceptionexception-where-the-type-is-an-exception-i-always-receive-a-general-faultexception-type-on-the-client-and-not-the-generic-type-whats-happening"></a><span data-ttu-id="d7e8e-177">FaultException을 발생 하면\<예외 > 예외 형식이 인 경우 항상 받습니다 일반 FaultException 형식을 클라이언트에서 제네릭 형식이 아닌 합니다.</span><span class="sxs-lookup"><span data-stu-id="d7e8e-177">When I throw a FaultException\<Exception> where the type is an exception, I always receive a general FaultException type on the client and not the generic type.</span></span> <span data-ttu-id="d7e8e-178">이유가 무엇입니까?</span><span class="sxs-lookup"><span data-stu-id="d7e8e-178">What’s happening?</span></span>  
 <span data-ttu-id="d7e8e-179">사용자 지정 오류 데이터 형식을 만들고 이 형식을 오류 계약에서 세부 형식으로 선언하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="d7e8e-179">It is highly recommended that you create your own custom error data type and declare that as the detail type in your fault contract.</span></span> <span data-ttu-id="d7e8e-180">시스템 제공 예외 형식을 사용하는 이유는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="d7e8e-180">The reason is that using system-provided exception types:</span></span>  
  
- <span data-ttu-id="d7e8e-181">서비스 지향 애플리케이션의 가장 큰 장점 중 하나를 제거하는 형식 종속성을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="d7e8e-181">Creates a type dependency that removes one of the biggest strengths of service-oriented applications.</span></span>  
  
- <span data-ttu-id="d7e8e-182">표준 방법으로 serialize하는 예외에 의존할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d7e8e-182">Cannot depend upon exceptions serializing in a standard way.</span></span> <span data-ttu-id="d7e8e-183"><xref:System.Security.SecurityException>과 같이 전혀 serialize할 수 없는 것도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d7e8e-183">Some—like <xref:System.Security.SecurityException>—may not be serializable at all.</span></span>  
  
- <span data-ttu-id="d7e8e-184">내부 구현 세부 정보를 클라이언트에 노출합니다.</span><span class="sxs-lookup"><span data-stu-id="d7e8e-184">Exposes internal implementation details to clients.</span></span> <span data-ttu-id="d7e8e-185">자세한 내용은 [지정 및 계약 및 서비스에서 오류 처리](../../../docs/framework/wcf/specifying-and-handling-faults-in-contracts-and-services.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="d7e8e-185">For more information, see [Specifying and Handling Faults in Contracts and Services](../../../docs/framework/wcf/specifying-and-handling-faults-in-contracts-and-services.md).</span></span>  
  
 <span data-ttu-id="d7e8e-186">그러나 애플리케이션을 디버깅하는 경우에는 <xref:System.ServiceModel.Description.ServiceDebugBehavior> 클래스를 사용하여 예외 정보를 serialize하고 클라이언트에 반환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d7e8e-186">If you are debugging an application, however, you can serialize exception information and return it to the client by using the <xref:System.ServiceModel.Description.ServiceDebugBehavior> class.</span></span>  
  
<a name="BKMK_q6"></a>   
## <a name="it-seems-like-one-way-and-request-reply-operations-return-at-roughly-the-same-speed-when-the-reply-contains-no-data-whats-happening"></a><span data-ttu-id="d7e8e-187">회신에 데이터가 포함되지 않은 경우 단방향 및 요청-회신 작업이 거의 같은 속도로 반환되는 것 같습니다.</span><span class="sxs-lookup"><span data-stu-id="d7e8e-187">It seems like one-way and request-reply operations return at roughly the same speed when the reply contains no data.</span></span> <span data-ttu-id="d7e8e-188">이유가 무엇입니까?</span><span class="sxs-lookup"><span data-stu-id="d7e8e-188">What's happening?</span></span>  
 <span data-ttu-id="d7e8e-189">작업을 단방향 작업으로 지정한다는 것은 작업 계약이 입력 메시지를 받은 다음 출력 메시지를 반환하지 않는다는 것을 의미할 뿐입니다.</span><span class="sxs-lookup"><span data-stu-id="d7e8e-189">Specifying that an operation is one way means only that the operation contract accepts an input message and does not return an output message.</span></span> <span data-ttu-id="d7e8e-190">Wcf에서 모든 클라이언트 호출은 아웃 바운드 데이터 전송에 쓰여졌는지 또는 예외가 발생 하는 경우를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="d7e8e-190">In WCF, all client invocations return when the outbound data has been written to the wire or an exception is thrown.</span></span> <span data-ttu-id="d7e8e-191">단방향 작업도 이와 동일한 방식으로 작동하며, 서비스를 찾을 수 없는 경우 throw되거나 서비스가 네트워크로부터 데이터를 받을 준비가 되지 않은 경우 블로킹될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d7e8e-191">One-way operations work the same way, and they can throw if the service cannot be located or block if the service is not prepared to accept the data from the network.</span></span> <span data-ttu-id="d7e8e-192">일반적으로 wcf에서는이 인해 단방향 호출이 요청-회신 보다 더 빨리 클라이언트에 게 반환 합니다. 하지만는 네트워크를 통해 아웃 바운드 데이터를 보내는 속도가 느려지는 상황이 요청-회신 작업 뿐 아니라 단방향 작업의 속도도 느려집니다.</span><span class="sxs-lookup"><span data-stu-id="d7e8e-192">Typically in WCF, this results in one-way calls returning to the client more quickly than request-reply; but any condition that slows the sending of the outbound data over the network slows one-way operations as well as request-reply operations.</span></span> <span data-ttu-id="d7e8e-193">자세한 내용은 [단방향 서비스](../../../docs/framework/wcf/feature-details/one-way-services.md) 하 고 [WCF 클라이언트를 사용 하 여 액세스 서비스](../../../docs/framework/wcf/feature-details/accessing-services-using-a-client.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="d7e8e-193">For more information, see [One-Way Services](../../../docs/framework/wcf/feature-details/one-way-services.md) and [Accessing Services Using a WCF Client](../../../docs/framework/wcf/feature-details/accessing-services-using-a-client.md).</span></span>  
  
<a name="BKMK_q77"></a>   
## <a name="im-using-an-x509-certificate-with-my-service-and-i-get-a-systemsecuritycryptographycryptographicexception-whats-happening"></a><span data-ttu-id="d7e8e-194">서비스에 X.509 인증서를 사용하고 있으며 System.Security.Cryptography.CryptographicException이 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="d7e8e-194">I’m using an X.509 certificate with my service and I get a System.Security.Cryptography.CryptographicException.</span></span> <span data-ttu-id="d7e8e-195">이유가 무엇입니까?</span><span class="sxs-lookup"><span data-stu-id="d7e8e-195">What’s happening?</span></span>  
 <span data-ttu-id="d7e8e-196">이 예외는 보통 IIS 작업자 프로세스를 실행하는 데 사용되는 사용자 계정을 변경한 후에 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="d7e8e-196">This commonly occurs after changing the user account under which the IIS worker process runs.</span></span> <span data-ttu-id="d7e8e-197">예를 들어, [!INCLUDE[wxp](../../../includes/wxp-md.md)]에서 Aspnet_wp.exe를 실행하는 데 사용되는 기본 사용자 계정을 ASPNET에서 사용자 지정 사용자 계정으로 변경하면 이 오류가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d7e8e-197">For example, in [!INCLUDE[wxp](../../../includes/wxp-md.md)], if you change the default user account that the Aspnet_wp.exe runs under from ASPNET to a custom user account, you may see this error.</span></span> <span data-ttu-id="d7e8e-198">개인 키를 사용하는 경우 이 키를 사용하는 프로세스에는 키가 저장된 파일에 액세스할 수 있는 권한이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d7e8e-198">If using a private key, the process that uses it will need to have permissions to access the file storing that key.</span></span>  
  
 <span data-ttu-id="d7e8e-199">이 경우에는 개인 키가 포함된 파일에 대한 프로세스 계정에 읽기 권한을 부여해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d7e8e-199">If this is the case, you must give read access privileges to the process's account for the file containing the private key.</span></span> <span data-ttu-id="d7e8e-200">예를 들어, IIS 작업자 프로세스가 밥 계정에서 실행되는 경우 밥에게 개인 키가 포함된 파일에 대한 읽기 권한을 부여해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d7e8e-200">For example, if the IIS worker process is running under the Bob account, then you will need to give Bob read access to the file containing the private key.</span></span>  
  
 <span data-ttu-id="d7e8e-201">특정 X.509 인증서의 개인 키를 포함 하는 파일에 올바른 사용자 계정 액세스를 부여 하는 방법에 대 한 자세한 내용은 참조 하세요. [방법: X.509 인증서를 WCF에 액세스할 수 있도록](../../../docs/framework/wcf/feature-details/how-to-make-x-509-certificates-accessible-to-wcf.md)입니다.</span><span class="sxs-lookup"><span data-stu-id="d7e8e-201">For more information about how to give the correct user account access to the file that contains the private key for a specific X.509 certificate, see [How to: Make X.509 Certificates Accessible to WCF](../../../docs/framework/wcf/feature-details/how-to-make-x-509-certificates-accessible-to-wcf.md).</span></span>  
  
<a name="BKMK_q88"></a>   
## <a name="i-changed-the-first-parameter-of-an-operation-from-uppercase-to-lowercase-now-my-client-throws-an-exception-whats-happening"></a><span data-ttu-id="d7e8e-202">작업의 첫 번째 매개 변수를 대문자에서 소문자로 변경한 다음에 클라이언트에서 예외가 throw됩니다.</span><span class="sxs-lookup"><span data-stu-id="d7e8e-202">I changed the first parameter of an operation from uppercase to lowercase; now my client throws an exception.</span></span> <span data-ttu-id="d7e8e-203">이유가 무엇입니까?</span><span class="sxs-lookup"><span data-stu-id="d7e8e-203">What's happening?</span></span>  
 <span data-ttu-id="d7e8e-204">작업 서명에 포함된 매개 변수 이름의 값은 계약의 일부이며 대/소문자를 구분합니다.</span><span class="sxs-lookup"><span data-stu-id="d7e8e-204">The value of the parameter names in the operation signature are part of the contract and are case-sensitive.</span></span> <span data-ttu-id="d7e8e-205">로컬 매개 변수 이름과 클라이언트 애플리케이션의 작업을 설명하는 메타데이터를 구분해야 하는 경우에는 <xref:System.ServiceModel.MessageParameterAttribute?displayProperty=nameWithType> 특성을 사용하십시오.</span><span class="sxs-lookup"><span data-stu-id="d7e8e-205">Use the <xref:System.ServiceModel.MessageParameterAttribute?displayProperty=nameWithType> attribute when you need to distinguish between the local parameter name and the metadata that describes the operation for client applications.</span></span>  
  
<a name="BKMK_q99"></a>   
## <a name="im-using-one-of-my-tracing-tools-and-i-get-an-endpointnotfoundexception-whats-happening"></a><span data-ttu-id="d7e8e-206">추적 도구 중 하나를 사용하는 동안 EndpointNotFoundException이 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="d7e8e-206">I’m using one of my tracing tools and I get an EndpointNotFoundException.</span></span> <span data-ttu-id="d7e8e-207">이유가 무엇입니까?</span><span class="sxs-lookup"><span data-stu-id="d7e8e-207">What’s happening?</span></span>  
 <span data-ttu-id="d7e8e-208">시스템 제공 WCF 추적 메커니즘이 아닌 추적 도구를 사용 하 고 수신 하는 경우는 <xref:System.ServiceModel.EndpointNotFoundException> 나타내는 주소 필터 불일치를 했습니다.을 사용 해야는 <xref:System.ServiceModel.Description.ClientViaBehavior> 메시지 추적 유틸리티를 클래스 및 유틸리티 서비스 주소에 해당 메시지를 리디렉션할 경우</span><span class="sxs-lookup"><span data-stu-id="d7e8e-208">If you are using a tracing tool that is not the system-provided WCF tracing mechanism and you receive an <xref:System.ServiceModel.EndpointNotFoundException> that indicates that there was an address filter mismatch, you need to use the <xref:System.ServiceModel.Description.ClientViaBehavior> class to direct the messages to the tracing utility and have the utility redirect those messages to the service address.</span></span> <span data-ttu-id="d7e8e-209"><xref:System.ServiceModel.Description.ClientViaBehavior> 클래스는 `Via` 주소 지정 헤더를 변경하여 `To` 주소 지정 헤더로 표시되는 최종 수신자와 별도로 다음 네트워크 주소를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="d7e8e-209">The <xref:System.ServiceModel.Description.ClientViaBehavior> class alters the `Via` addressing header to specify the next network address separately from the ultimate receiver, indicated by the `To` addressing header.</span></span> <span data-ttu-id="d7e8e-210">그러나 이 경우 `To` 값을 설정하는 데 사용되는 엔드포인트 주소를 변경해서는 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d7e8e-210">When doing this, however, do not change the endpoint address, which is used to establish the `To` value.</span></span>  
  
 <span data-ttu-id="d7e8e-211">다음 코드 예제는 클라이언트 구성 파일의 예를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="d7e8e-211">The following code example shows an example client configuration file.</span></span>  
  
```xml
<endpoint   
  address="http://localhost:8000/MyServer/"  
  binding="wsHttpBinding"  
  bindingConfiguration="WSHttpBinding_IMyContract"  
  behaviorConfiguration="MyClient"   
  contract="IMyContract"   
  name="WSHttpBinding_IMyContract">  
</endpoint>  
<behaviors>  
  <endpointBehaviors>  
    <behavior name="MyClient">  
      <clientVia viaUri="http://localhost:8001/MyServer/"/>  
    </behavior>  
  </endpointBehaviors>  
</behaviors>  
```  
  
<a name="BKMK_q10"></a>   
## <a name="what-is-the-base-address-how-does-it-relate-to-an-endpoint-address"></a><span data-ttu-id="d7e8e-212">기본 주소란 무엇입니까?</span><span class="sxs-lookup"><span data-stu-id="d7e8e-212">What is the base address?</span></span> <span data-ttu-id="d7e8e-213">끝점 주소와는 어떤 관계가 있습니까?</span><span class="sxs-lookup"><span data-stu-id="d7e8e-213">How does it relate to an endpoint address?</span></span>  
 <span data-ttu-id="d7e8e-214">기본 주소는 <xref:System.ServiceModel.ServiceHost> 클래스의 루트 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="d7e8e-214">A base address is the root address for a <xref:System.ServiceModel.ServiceHost> class.</span></span> <span data-ttu-id="d7e8e-215">기본적으로 서비스 구성에 <xref:System.ServiceModel.Description.ServiceMetadataBehavior> 클래스를 추가하면 호스트가 게시하는 모든 엔드포인트에 대한 WSDL(웹 서비스 기술 언어)이 HTTP 기본 주소, 메타데이터 동작에 제공된 관련 주소 및 "?wsdl"에서 검색됩니다.</span><span class="sxs-lookup"><span data-stu-id="d7e8e-215">By default, if you add a <xref:System.ServiceModel.Description.ServiceMetadataBehavior> class into your service configuration, the Web Services Description Language (WSDL) for all endpoints the host publishes are retrieved from the HTTP base address, plus any relative address provided to the metadata behavior, plus "?wsdl".</span></span> <span data-ttu-id="d7e8e-216">[!INCLUDE[vstecasp](../../../includes/vstecasp-md.md)] 및 IIS에 대해 잘 알고 있는 경우 기본 주소는 가상 디렉터리와 같은 것으로 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d7e8e-216">If you are familiar with [!INCLUDE[vstecasp](../../../includes/vstecasp-md.md)] and IIS, the base address is equivalent to the virtual directory.</span></span>  
  
## <a name="sharing-a-port-between-a-service-endpoint-and-a-mex-endpoint-using-the-nettcpbinding"></a><span data-ttu-id="d7e8e-217">NetTcpBinding을 사용하여 서비스 엔드포인트와 MEX 엔드포인트 간에 포트 공유</span><span class="sxs-lookup"><span data-stu-id="d7e8e-217">Sharing a port between a service endpoint and a mex endpoint using the NetTcpBinding</span></span>  
 <span data-ttu-id="d7e8e-218">서비스의 기본 주소를 net.tcp://MyServer:8080/MyService로 지정하고 다음 엔드포인트를 추가하는 경우:</span><span class="sxs-lookup"><span data-stu-id="d7e8e-218">If you specify the base address for a service as net.tcp://MyServer:8080/MyService and add the following endpoints:</span></span>  
  
```xml  
<services>  
  <service name="Microsoft.Samples.NetTcp.CalculatorService">  
    <endpoint address="calcsvc" binding ="netTcpBinding" contract="Microsoft.Samples.NetTcp.ICalculator"/>  
    <endpoint address="mex" binding="mexTcpBinding" contract="IMetadataExchange" />  
  </service>  
</services>  
```  
  
 <span data-ttu-id="d7e8e-219">다음 구성 코드 조각에 나와 있는 것처럼 NetTcpBinding 설정 중 하나를 수정하는 경우:</span><span class="sxs-lookup"><span data-stu-id="d7e8e-219">And if you modify one of the NetTcpBinding settings as shown in the following configuration snippet:</span></span>  
  
```xml  
<bindings>  
  <netTcpBinding>  
    <binding closeTimeout="00:01:00" openTimeout="00:01:00" receiveTimeout="00:10:00" sendTimeout="00:01:00" transactionFlow="false" transferMode="Buffered" transactionProtocol="OleTransactions" hostNameComparisonMode="StrongWildcard" listenBacklog="10" maxBufferPoolSize="524288" maxBufferSize="65536" maxConnections="11" maxReceivedMessageSize="65536">  
      <readerQuotas maxDepth="32" maxStringContentLength="8192" maxArrayLength="16384" maxBytesPerRead="4096" maxNameTableCharCount="16384"/>  
      <reliableSession ordered="true" inactivityTimeout="00:10:00" enabled="false"/>  
      <security mode="Transport">  
        <transport clientCredentialType="Windows" protectionLevel="EncryptAndSign"/>  
      </security>  
    </binding>  
  </netTcpBinding>  
</bindings>  
```  
  
 <span data-ttu-id="d7e8e-220">다음과 같은 오류가 표시 됩니다. 처리되지 않은 예외: System.ServiceModel.AddressAlreadyInUseException: 이미 수신기 IP 끝점 0.0.0.0:9000 다음 구성 코드 조각에 나와 있는 것 처럼 MEX 끝점에 대 한 다른 포트를 사용 하 여 정규화 된 URL을 지정 하 여이 오류를 해결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d7e8e-220">You will see an error like the following: Unhandled Exception: System.ServiceModel.AddressAlreadyInUseException: There is already a listener on IP endpoint 0.0.0.0:9000 You can work around this error by specifying a fully qualified URL with a different port for the MEX endpoint as shown in the following configuration snippet:</span></span>  
  
```xml
<services>  
  <service name="Microsoft.Samples.NetTcp.CalculatorService">  
    <endpoint address="calcsvc" binding ="netTcpBinding" contract="Microsoft.Samples.NetTcp.ICalculator"/>  
    <endpoint address="net.tcp://localhost:9001/servicemodelsamples/mex" binding="mexTcpBinding" contract="IMetadataExchange" />  
  </service>  
</services>  
```  
  
<a name="BK_MK99"></a>   
## <a name="when-calling-a-wcf-web-http-application-from-a-wcf-soap-application-the-service-returns-the-following-error-405-method-not-allowed"></a><span data-ttu-id="d7e8e-221">WCF SOAP 응용 프로그램에서 WCF 웹 HTTP 응용 프로그램을 호출할 때 서비스에 다음 오류를 반환 합니다. 405 메서드가 허용 되지 않습니다</span><span class="sxs-lookup"><span data-stu-id="d7e8e-221">When calling a WCF Web HTTP application from a WCF SOAP application the service returns the following error: 405 Method Not Allowed</span></span>  
 <span data-ttu-id="d7e8e-222">WCF 웹 HTTP 응용 프로그램을 호출 (사용 하는 서비스를 <xref:System.ServiceModel.WebHttpBinding> 및 <xref:System.ServiceModel.Description.WebHttpBehavior>) 서비스는 WCF에서 다음 예외를 생성할 수 있습니다. `Unhandled Exception: System.ServiceModel.FaultException`1[System.ServiceModel.ExceptionDetail]: 원격 서버에 예기치 않은 응답을 반환 합니다. (405) 메서드가 없습니다 허용 합니다.' 나가는 WCF 덮어쓰기 때문에이 예외가 발생 <xref:System.ServiceModel.OperationContext> 들어오는 사용 하 여 <xref:System.ServiceModel.OperationContext>입니다.</span><span class="sxs-lookup"><span data-stu-id="d7e8e-222">Calling a WCF Web HTTP application (a service that uses the <xref:System.ServiceModel.WebHttpBinding> and <xref:System.ServiceModel.Description.WebHttpBehavior>) from a WCF service may generate the following exception: `Unhandled Exception: System.ServiceModel.FaultException`1[System.ServiceModel.ExceptionDetail]: The remote server returned an unexpected response: (405) Method Not Allowed.\` This exception occurs because WCF overwrites the outgoing <xref:System.ServiceModel.OperationContext> with the incoming <xref:System.ServiceModel.OperationContext>.</span></span> <span data-ttu-id="d7e8e-223">이 문제를 해결하려면 WCF 웹 HTTP 서비스 작업 안에 <xref:System.ServiceModel.OperationContextScope> 을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="d7e8e-223">To solve this problem create an <xref:System.ServiceModel.OperationContextScope> within the WCF Web HTTP service operation.</span></span> <span data-ttu-id="d7e8e-224">예를 들어:</span><span class="sxs-lookup"><span data-stu-id="d7e8e-224">For example:</span></span>  
  
```csharp
public string Echo(string input)  
{  
    using (new OperationContextScope(this.InnerChannel))  
    {  
        return base.Channel.Echo(input);  
    }  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="d7e8e-225">참고자료</span><span class="sxs-lookup"><span data-stu-id="d7e8e-225">See also</span></span>

- [<span data-ttu-id="d7e8e-226">Windows 인증 오류 디버깅</span><span class="sxs-lookup"><span data-stu-id="d7e8e-226">Debugging Windows Authentication Errors</span></span>](../../../docs/framework/wcf/feature-details/debugging-windows-authentication-errors.md)
