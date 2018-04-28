---
title: ASP.NET AJAX용 WCF 서비스 만들기
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 04c0402c-e617-4ba5-aedf-d17692234776
caps.latest.revision: 18
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 64ab5c6bf4b555504562dbf68a60d032743df865
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/28/2018
---
# <a name="creating-wcf-services-for-aspnet-ajax"></a><span data-ttu-id="27cf3-102">ASP.NET AJAX용 WCF 서비스 만들기</span><span class="sxs-lookup"><span data-stu-id="27cf3-102">Creating WCF Services for ASP.NET AJAX</span></span>
<span data-ttu-id="27cf3-103">Microsoft ASP.NET AJAX를 사용하면 응답성이 높고 친숙한 사용자 인터페이스 요소를 통해 풍부한 사용자 경험을 제공하는 웹 페이지를 빠르게 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="27cf3-103">Microsoft ASP.NET AJAX enables you to quickly create Web pages that include a rich user experience with responsive and familiar user interface elements.</span></span> <span data-ttu-id="27cf3-104">ASP.NET AJAX는 크로스 브라우저 ECMAScript(JavaScript) 및 DHTML(동적 HTML) 기술을 통합하는 클라이언트 스크립트 라이브러리를 제공하며 ASP.NET 2.0 서버 기반 개발 플랫폼과 통합됩니다.</span><span class="sxs-lookup"><span data-stu-id="27cf3-104">ASP.NET AJAX provides client-script libraries that incorporate cross-browser ECMAScript (JavaScript) and dynamic HTML (DHTML) technologies, and it integrates them with the ASP.NET 2.0 server-based development platform.</span></span> <span data-ttu-id="27cf3-105">ASP.NET AJAX를 사용하여 사용자 환경 및 웹 응용 프로그램의 효율성을 개선할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="27cf3-105">By using ASP.NET AJAX, you can improve the user experience and the efficiency of your Web applications.</span></span>  
  
 <span data-ttu-id="27cf3-106">ASP.NET AJAX는 강력한 개발 프레임워크를 제공하기 위해 통합된 서버 구성 요소와 클라이언트 스크립트 라이브러리로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="27cf3-106">ASP.NET AJAX consists of client-script libraries and of server components that are integrated to provide a robust development framework.</span></span> <span data-ttu-id="27cf3-107">ASP.NET 페이지에서 서비스에 액세스하려는 경우 일단, 서비스 URL을 페이지의 ASP.NET 스크립트 관리자 컨트롤에 추가하면 일반 JavaScript 기능 호출과 똑같은 JavaScript 코드를 사용하여 서비스 작업을 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="27cf3-107">To access a service from an ASP.NET page: once the service URL is added to the ASP.NET Script Manager control on the page, service operations may be invoked using JavaScript code that looks exactly like a regular JavaScript function call.</span></span> <span data-ttu-id="27cf3-108">참조 [알아보려면 ASP.NET AJAX](http://go.microsoft.com/fwlink/?LinkId=186475) AJAX 프레임 워크 내에서 웹 서비스의 사용에 대 한 합니다.</span><span class="sxs-lookup"><span data-stu-id="27cf3-108">See [Learn ASP.NET AJAX](http://go.microsoft.com/fwlink/?LinkId=186475) about the use of Web services within the AJAX framework.</span></span>  
  
 <span data-ttu-id="27cf3-109">대부분의 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 서비스는 적합한 ASP.NET AJAX 끝점을 추가하여 ASP.NET AJAX와 호환되는 서비스로 노출될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="27cf3-109">Most [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] services may be exposed as a service compatible with ASP.NET AJAX by adding an appropriate ASP.NET AJAX endpoint.</span></span>  
  
 <span data-ttu-id="27cf3-110">Visual Studio를 사용 하는 경우에 사용할 수 있는 AJAX 사용 WCF 서비스에 대 한 미리 작성 된 서식 파일을 사용할 수 있습니다는 **새 항목 추가** ASP.NET 웹 사이트 또는 웹 응용 프로그램에서 작업할 때 대화 상자.</span><span class="sxs-lookup"><span data-stu-id="27cf3-110">If you are using Visual Studio, you may use a pre-built template for AJAX-enabled WCF services, available in the **Add New Item** dialog when working with ASP.NET Web Sites or Web Applications.</span></span>  
  
 <span data-ttu-id="27cf3-111">Visual Studio 템플릿을 사용하지 않는 경우 다음 두 가지 방법으로 ASP.NET AJAX 끝점을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="27cf3-111">If you are not using the Visual Studio templates, there are two ways to create an ASP.NET AJAX endpoint:</span></span>  
  
-   <span data-ttu-id="27cf3-112">구성을 사용하지 않고 동적 호스트 활성화를 사용하여 끝점을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="27cf3-112">Create the endpoint using dynamic host activation without using any configuration.</span></span> <span data-ttu-id="27cf3-113">이 방법은 WCF 구성 시스템에 익숙하지 않은 경우 사용할 수 있는 가장 기본적인 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="27cf3-113">This is the most basic approach if you are unfamiliar with the WCF configuration system.</span></span> <span data-ttu-id="27cf3-114">자세한 내용은 참조 [하는 방법: ASP.NET AJAX 끝점 하지 않고 사용 하 여 구성을 추가](../../../../docs/framework/wcf/feature-details/how-to-add-an-aspnet-ajax-endpoint-without-using-configuration.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="27cf3-114">For more information, see [How to: Add an ASP.NET AJAX Endpoint Without Using Configuration](../../../../docs/framework/wcf/feature-details/how-to-add-an-aspnet-ajax-endpoint-without-using-configuration.md).</span></span>  
  
-   <span data-ttu-id="27cf3-115">구성을 사용하여 AJAX 사용 끝점을 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 서비스에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="27cf3-115">Add an AJAX-enabled endpoint to a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] service using configuration.</span></span> <span data-ttu-id="27cf3-116">자세한 내용은 참조 [하는 방법: ASP.NET AJAX 끝점 추가를 사용 하 여 구성](../../../../docs/framework/wcf/feature-details/how-to-use-configuration-to-add-an-aspnet-ajax-endpoint.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="27cf3-116">For more information, see [How to: Use Configuration to Add an ASP.NET AJAX Endpoint](../../../../docs/framework/wcf/feature-details/how-to-use-configuration-to-add-an-aspnet-ajax-endpoint.md).</span></span>  
  
 <span data-ttu-id="27cf3-117">에 설명 된 웹 프로그래밍 모델은 [WCF 웹 HTTP 프로그래밍 모델 개요](../../../../docs/framework/wcf/feature-details/wcf-web-http-programming-model-overview.md) ASP.NET AJAX 서비스와 함께 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="27cf3-117">The Web Programming Model described in the [WCF Web HTTP Programming Model Overview](../../../../docs/framework/wcf/feature-details/wcf-web-http-programming-model-overview.md) may be used with ASP.NET AJAX services.</span></span> <span data-ttu-id="27cf3-118">구체적으로는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="27cf3-118">Specifically:</span></span>  
  
-   <span data-ttu-id="27cf3-119"><xref:System.ServiceModel.Web.WebGetAttribute> 및 <xref:System.ServiceModel.Web.WebInvokeAttribute> 특성을 사용하여 HTTP GET 및 HTTP POST 동사 중에서 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="27cf3-119">You can use the <xref:System.ServiceModel.Web.WebGetAttribute> and <xref:System.ServiceModel.Web.WebInvokeAttribute> attributes to select between HTTP GET and HTTP POST verbs.</span></span> <span data-ttu-id="27cf3-120">이 기능을 올바르게 사용하면 응용 프로그램의 성능이 크게 향상될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="27cf3-120">If used correctly, this may significantly improve your application’s performance.</span></span> <span data-ttu-id="27cf3-121">자세한 내용은 참조 [하는 방법: ASP.NET AJAX 끝점에 대 한 요청에서 HTTP POST 및 HTTP GET 간의 선택](../../../../docs/framework/wcf/feature-details/http-post-and-http-get-requests-for-aspnet-ajax-endpoints.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="27cf3-121">For more information, see [How to: Choose between HTTP POST and HTTP GET requests for ASP.NET AJAX Endpoints](../../../../docs/framework/wcf/feature-details/http-post-and-http-get-requests-for-aspnet-ajax-endpoints.md).</span></span>  
  
-   <span data-ttu-id="27cf3-122"><xref:System.ServiceModel.Web.WebGetAttribute.ResponseFormat%2A> 및 <xref:System.ServiceModel.Web.WebInvokeAttribute.ResponseFormat%2A> 속성을 사용하여 서비스에서 기본 JSON(JavaScript Object Notation) 대신 XML 데이터를 반환하도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="27cf3-122">You can use the <xref:System.ServiceModel.Web.WebGetAttribute.ResponseFormat%2A> and <xref:System.ServiceModel.Web.WebInvokeAttribute.ResponseFormat%2A> properties to cause your service to return XML data instead of the default JavaScript Object Notation (JSON).</span></span> <span data-ttu-id="27cf3-123">ASP.NET AJAX 프레임워크를 사용하여 이 작업을 수행하면 JavaScript 클라이언트가 XML DOM 개체를 받게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="27cf3-123">Doing this with the ASP.NET AJAX framework causes the JavaScript client to receive an XML DOM object.</span></span>  
  
    > [!WARNING]
    >  <span data-ttu-id="27cf3-124">이 작업을 수행하려면 콘텐츠 형식을 text/xml로 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="27cf3-124">Your operation must set the content type to text/xml for this to work.</span></span> <span data-ttu-id="27cf3-125">그렇지 않으면 JavaScript 클라이언트가 XML DOM 개체 대신 XML이 들어 있는 문자열을 받게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="27cf3-125">Otherwise, the JavaScript client will receive a string containing the XML instead of an XML DOM object.</span></span>  
  
     <span data-ttu-id="27cf3-126">다음은 콘텐츠 형식이 적절하게 설정된 XML 데이터를 반환하는 작업의 예제입니다.</span><span class="sxs-lookup"><span data-stu-id="27cf3-126">The following is an example of an operation that returns XML data with the content type set appropriately:</span></span>  
  
    ```  
    [OperationContract, WebGet(ResponseFormat=WebMessageFormat.Xml)]  
    public XElement GetData()  
    {  
    XElement x;  
    //Get some data here...  
  
    WebOperationContext.Current.OutgoingResponse.ContentType = "text/xml";      
    return x;  
    }  
    ```  
  
-   <span data-ttu-id="27cf3-127">ASP.NET AJAX와의 호환성이 필요한 경우에는 <xref:System.ServiceModel.Web.WebGetAttribute> 및 <xref:System.ServiceModel.Web.WebInvokeAttribute> 특성의 다른 속성을 변경할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="27cf3-127">No other properties on the <xref:System.ServiceModel.Web.WebGetAttribute> and <xref:System.ServiceModel.Web.WebInvokeAttribute> attributes can be changed if compatibility with ASP.NET AJAX is required.</span></span> <span data-ttu-id="27cf3-128">ASP.NET AJAX 호출 규칙을 위반하지 않는 한 웹 프로그래밍 모델의 다른 부분을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="27cf3-128">Other aspects of the Web Programming Model can be used as long as the ASP.NET AJAX calling conventions are not violated.</span></span>  
  
 <span data-ttu-id="27cf3-129">고급 시나리오를 사용하려면 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]의 AJAX 지원에 대한 추가 정보를 이해해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="27cf3-129">More advanced scenarios require some additional details of AJAX support in [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] be understood:</span></span>  
  
-   <span data-ttu-id="27cf3-130">AJAX 페이지 클라이언트 사이 데이터를 전송 하는 방법을 이해 하 고 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] JavaScript를 사용 하 여 서비스 및.NET Framework 형식이 JavaScript 형식에 매핑되는 방식에 대 한 세부 정보를 참조 하십시오. [JSON 및 기타 데이터 형식 전송에 대 한 지원을](../../../../docs/framework/wcf/feature-details/support-for-json-and-other-data-transfer-formats.md) .</span><span class="sxs-lookup"><span data-stu-id="27cf3-130">To understand how data is transferred between an AJAX page client and a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] service using JavaScript, and for details on how .NET Framework types map to JavaScript types, see [Support for JSON and Other Data Transfer Formats](../../../../docs/framework/wcf/feature-details/support-for-json-and-other-data-transfer-formats.md).</span></span>  
  
-   <span data-ttu-id="27cf3-131">URL 기반 인증 및 ASP.NET 세션 정보 액세스 등 ASP.NET 기능을 사용하려면 구성을 통해 ASP.NET 호환 모드를 활성화하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="27cf3-131">To take advantage of ASP.NET features, for example, URL-based authentication and accessing the ASP.NET session information, you may want to enable the ASP.NET Compatibility Mode through configuration.</span></span>  
  
 <span data-ttu-id="27cf3-132">ASP.NET AJAX 프레임워크가 없어도 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]의 AJAX 끝점을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="27cf3-132">AJAX endpoints in [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] may even be consumed without the ASP.NET AJAX framework.</span></span> <span data-ttu-id="27cf3-133">이렇게 하려면 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]에서 AJAX 지원 아키텍처를 이해해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="27cf3-133">Doing so requires an understanding of the support architecture of AJAX support in [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].</span></span> <span data-ttu-id="27cf3-134">이 아키텍처의 논의 알려면 [WCF 웹 HTTP 프로그래밍 개체 모델](../../../../docs/framework/wcf/feature-details/wcf-web-http-programming-object-model.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="27cf3-134">For a discussion of this architecture, see [WCF Web HTTP Programming Object Model](../../../../docs/framework/wcf/feature-details/wcf-web-http-programming-object-model.md).</span></span> <span data-ttu-id="27cf3-135">이 방법을 보여 주는 코드 샘플을 참조 하십시오.는 [JSON 및 XML을 포함 한 AJAX 서비스](../../../../docs/framework/wcf/samples/ajax-service-with-json-and-xml-sample.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="27cf3-135">For a code sample demonstrating this approach, see the [AJAX Service with JSON and XML](../../../../docs/framework/wcf/samples/ajax-service-with-json-and-xml-sample.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="27cf3-136">참고 항목</span><span class="sxs-lookup"><span data-stu-id="27cf3-136">See Also</span></span>  
 [<span data-ttu-id="27cf3-137">WCF 웹 HTTP 프로그래밍 모델</span><span class="sxs-lookup"><span data-stu-id="27cf3-137">WCF Web HTTP Programming Model</span></span>](../../../../docs/framework/wcf/feature-details/wcf-web-http-programming-model.md)  
 [<span data-ttu-id="27cf3-138">방법: 구성을 사용하지 않고 ASP.NET AJAX 끝점 추가</span><span class="sxs-lookup"><span data-stu-id="27cf3-138">How to: Add an ASP.NET AJAX Endpoint Without Using Configuration</span></span>](../../../../docs/framework/wcf/feature-details/how-to-add-an-aspnet-ajax-endpoint-without-using-configuration.md)  
 [<span data-ttu-id="27cf3-139">방법: 구성을 사용하여 ASP.NET AJAX 끝점 추가</span><span class="sxs-lookup"><span data-stu-id="27cf3-139">How to: Use Configuration to Add an ASP.NET AJAX Endpoint</span></span>](../../../../docs/framework/wcf/feature-details/how-to-use-configuration-to-add-an-aspnet-ajax-endpoint.md)  
 [<span data-ttu-id="27cf3-140">방법: ASP.NET AJAX 끝점에 대해 HTTP POST 및 HTTP GET 요청 중에서 선택</span><span class="sxs-lookup"><span data-stu-id="27cf3-140">How to: Choose between HTTP POST and HTTP GET requests for ASP.NET AJAX Endpoints</span></span>](../../../../docs/framework/wcf/feature-details/http-post-and-http-get-requests-for-aspnet-ajax-endpoints.md)
