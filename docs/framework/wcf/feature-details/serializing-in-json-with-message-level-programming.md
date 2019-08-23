---
title: 메시지 수준의 프로그래밍으로 JSON으로 serialize
ms.date: 03/30/2017
ms.assetid: 5f940ba2-57ee-4c49-a779-957c5e7e71fa
ms.openlocfilehash: 6e8bb43b7a7755c20699aa377c9d60b0f285493b
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2019
ms.locfileid: "69949195"
---
# <a name="serializing-in-json-with-message-level-programming"></a><span data-ttu-id="33e4c-102">메시지 수준의 프로그래밍으로 JSON으로 serialize</span><span class="sxs-lookup"><span data-stu-id="33e4c-102">Serializing in Json with Message Level Programming</span></span>
<span data-ttu-id="33e4c-103">WCF는 JSON 형식의 데이터 serialize를 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="33e4c-103">WCF supports serializing data in JSON format.</span></span> <span data-ttu-id="33e4c-104">이 항목에서는 <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer>를 사용하여 WCF가 형식을 serialize하도록 하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="33e4c-104">This topic describes how to tell WCF to serialize your types using the <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer>.</span></span>  
  
## <a name="typed-message-programming"></a><span data-ttu-id="33e4c-105">형식화된 메시지 프로그래밍</span><span class="sxs-lookup"><span data-stu-id="33e4c-105">Typed Message Programming</span></span>  
 <span data-ttu-id="33e4c-106">서비스 작업에 <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> 또는 <xref:System.ServiceModel.Web.WebGetAttribute>가 적용되면 <xref:System.ServiceModel.Web.WebInvokeAttribute>를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="33e4c-106">The <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> is used when the <xref:System.ServiceModel.Web.WebGetAttribute> or the <xref:System.ServiceModel.Web.WebInvokeAttribute> is applied to a service operation.</span></span> <span data-ttu-id="33e4c-107">두 특성을 사용하여 `RequestFormat` 및 `ResponseFormat`을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="33e4c-107">Both of these attributes allow you to specify the `RequestFormat` and `ResponseFormat`.</span></span> <span data-ttu-id="33e4c-108">요청 및 응답에 JSON을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="33e4c-108">To use JSON for requests and responses.</span></span> <span data-ttu-id="33e4c-109">둘 다를로 `WebMessageFormat.Json`설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="33e4c-109">set both of these to `WebMessageFormat.Json`.</span></span>  <span data-ttu-id="33e4c-110">JSON을 사용 하려면를 자동으로 <xref:System.ServiceModel.WebHttpBinding> <xref:System.ServiceModel.Description.WebHttpBehavior>구성 하는를 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="33e4c-110">In order to use JSON, you must use the <xref:System.ServiceModel.WebHttpBinding>, which automatically configures the <xref:System.ServiceModel.Description.WebHttpBehavior>.</span></span> <span data-ttu-id="33e4c-111">WCF 직렬화에 대 한 자세한 내용은 [serialization 및 Deserialization](../../../../docs/framework/wcf/feature-details/serialization-and-deserialization.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="33e4c-111">For more information about WCF serialization, see [Serialization and Deserialization](../../../../docs/framework/wcf/feature-details/serialization-and-deserialization.md).</span></span> <span data-ttu-id="33e4c-112">JSON 및 WCF에 대 한 자세한 내용은 [서비스 스테이션-wcf를 사용 하는 RESTful Services 소개](https://msdn.microsoft.com/magazine/dd315413.aspx)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="33e4c-112">For more information about JSON and WCF, see [Service Station - An Introduction To RESTful Services With WCF](https://msdn.microsoft.com/magazine/dd315413.aspx).</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="33e4c-113">JSON을 사용하려면 SOAP 통신을 지원하지 않는 <xref:System.ServiceModel.WebHttpBinding> 및 <xref:System.ServiceModel.Description.WebHttpBehavior>를 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="33e4c-113">Using JSON requires use of <xref:System.ServiceModel.WebHttpBinding> and <xref:System.ServiceModel.Description.WebHttpBehavior> which do not support SOAP communication.</span></span> <span data-ttu-id="33e4c-114">과 <xref:System.ServiceModel.WebHttpBinding> 통신 하는 서비스는 서비스 메타 데이터 노출을 지원 하지 않으므로 Visual Studio의 서비스 참조 추가 기능 또는 svcutil 명령줄 도구를 사용 하 여 클라이언트 쪽 프록시를 생성할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="33e4c-114">Services that communicate with the <xref:System.ServiceModel.WebHttpBinding> do not support exposing service metadata so you will not be able to use Visual Studio’s Add Service Reference functionality or the svcutil command-line tool to generate a client-side proxy.</span></span> <span data-ttu-id="33e4c-115">를 사용 <xref:System.ServiceModel.WebHttpBinding>하는 서비스를 프로그래밍 방식으로 호출 하는 방법에 대 한 자세한 내용은 [WCF에서 REST 서비스를 사용 하는 방법을](https://blogs.msdn.com/b/pedram/archive/2008/04/21/how-to-consume-rest-services-with-wcf.aspx)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="33e4c-115">For more information how you can programmatically call services that use <xref:System.ServiceModel.WebHttpBinding>, see [How to Consume REST Services with WCF](https://blogs.msdn.com/b/pedram/archive/2008/04/21/how-to-consume-rest-services-with-wcf.aspx).</span></span>  
  
## <a name="untyped-message-programming"></a><span data-ttu-id="33e4c-116">형식화되지 않은 메시지 프로그래밍</span><span class="sxs-lookup"><span data-stu-id="33e4c-116">Untyped Message Programming</span></span>  
 <span data-ttu-id="33e4c-117">형식화되지 않은 메시기 개체로 직접 작업할 때는 형식화되지 않은 메시지의 속성을 명시적으로 설정하여 JSON으로 serialize해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="33e4c-117">When working directly with untyped Message objects, you must explicitly set the properties on the untyped message to serialize it as JSON.</span></span> <span data-ttu-id="33e4c-118">다음 코드 조각에서는 이를 수행하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="33e4c-118">The following code snippet shows how to do this.</span></span>  
  
```  
 Message response = Message.CreateMessage(  
                  MessageVersion.None,    // No SOAP message version  
                             "*",                     // SOAP action, ignored since this is JSON  
                             "Response string: JSON format specified", // Message body  
                             new DataContractJsonSerializer(typeof(string))); // Specify DataContractJsonSerializer  
      response.Properties.Add( WebBodyFormatMessageProperty.Name,   
                    new WebBodyFormatMessageProperty(WebContentFormat.Json)); // Use JSON format  
```  
  
## <a name="see-also"></a><span data-ttu-id="33e4c-119">참고자료</span><span class="sxs-lookup"><span data-stu-id="33e4c-119">See also</span></span>

- [<span data-ttu-id="33e4c-120">AJAX 통합 및 JSON 지원</span><span class="sxs-lookup"><span data-stu-id="33e4c-120">AJAX Integration and JSON Support</span></span>](../../../../docs/framework/wcf/feature-details/ajax-integration-and-json-support.md)
- [<span data-ttu-id="33e4c-121">독립 실행형 JSON Serialization</span><span class="sxs-lookup"><span data-stu-id="33e4c-121">Stand-Alone JSON Serialization</span></span>](../../../../docs/framework/wcf/feature-details/stand-alone-json-serialization.md)
- [<span data-ttu-id="33e4c-122">JSON Serialization</span><span class="sxs-lookup"><span data-stu-id="33e4c-122">JSON Serialization</span></span>](../../../../docs/framework/wcf/samples/json-serialization.md)
