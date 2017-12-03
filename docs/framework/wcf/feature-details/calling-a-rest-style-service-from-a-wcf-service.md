---
title: "WCF 서비스에서 REST 스타일 서비스 호출"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 77df81d8-7f53-4daf-8d2d-bf7996e94d5a
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: efb04f36ad83755edd2e7d49c7cdec3cce77273b
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/02/2017
---
# <a name="calling-a-rest-style-service-from-a-wcf-service"></a><span data-ttu-id="5ff1d-102">WCF 서비스에서 REST 스타일 서비스 호출</span><span class="sxs-lookup"><span data-stu-id="5ff1d-102">Calling a REST-style service from a WCF service</span></span>
<span data-ttu-id="5ff1d-103">일반(SOAP 기반) WCF 서비스에서 REST 스타일의 서비스를 호출할 때 서비스 메서드의 작업 컨텍스트(들어오는 요청에 대한 정보 포함)가 나가는 요청에 사용되는 컨텍스트를 재정의합니다.</span><span class="sxs-lookup"><span data-stu-id="5ff1d-103">When calling a REST-style service from a regular (SOAP-based) WCF service, the operation context on the service method (which contains information about the incoming request) overrides the context which should be used by the outgoing request.</span></span> <span data-ttu-id="5ff1d-104">따라서 HTTP GET 요청이 HTTP POST 요청으로 변경됩니다.</span><span class="sxs-lookup"><span data-stu-id="5ff1d-104">This causes HTTP GET requests to change to HTTP POST requests.</span></span> <span data-ttu-id="5ff1d-105">WCF 서비스가 REST 스타일 서비스를 호출하는 데 올바른 컨텍스트를 사용하도록 적용하려면 새 <xref:System.ServiceModel.OperationContextScope>를 만들고 작업 컨텍스트 범위 내에서 REST 스타일 서비스를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="5ff1d-105">To force the WCF service to use the right context for calling the REST-style service, create a new <xref:System.ServiceModel.OperationContextScope> and call the REST-style service from inside the operation context scope.</span></span> <span data-ttu-id="5ff1d-106">이 항목에서는 이러한 기술을 설명하는 간단한 예제를 만드는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="5ff1d-106">This topic will describe how to create a simple sample that illustrates this technique.</span></span>  
  
## <a name="define-the-rest-style-service-contract"></a><span data-ttu-id="5ff1d-107">REST 스타일 서비스 계약 정의</span><span class="sxs-lookup"><span data-stu-id="5ff1d-107">Define the REST-style service contract</span></span>  
 <span data-ttu-id="5ff1d-108">간단한 REST 스타일 서비스 계약 정의:</span><span class="sxs-lookup"><span data-stu-id="5ff1d-108">Define a simple  REST-style service contract:</span></span>  
  
```csharp
[ServiceContract]
public interface IRestInterface  
{  
    [OperationContract, WebGet]
    int Add(int x, int y);
    
    [OperationContract, WebGet]
    string Echo(string input);
}
```
  
## <a name="implement-the-rest-style-service-contract"></a><span data-ttu-id="5ff1d-109">REST 스타일 서비스 계약 구현</span><span class="sxs-lookup"><span data-stu-id="5ff1d-109">Implement the REST-style service contract</span></span>  
 <span data-ttu-id="5ff1d-110">REST 스타일 서비스 계약 구현:</span><span class="sxs-lookup"><span data-stu-id="5ff1d-110">Implement the REST-style service contract:</span></span>  
  
```csharp
public class RestService : IRestInterface
{
    public int Add(int x, int y)
    {
        return x + y;
    }
    
    public string Echo(string input)
    {
        return input;
    }
}
```
  
## <a name="define-the-wcf-service-contract"></a><span data-ttu-id="5ff1d-111">WCF 서비스 계약 정의</span><span class="sxs-lookup"><span data-stu-id="5ff1d-111">Define the WCF service contract</span></span>  
 <span data-ttu-id="5ff1d-112">REST 스타일 서비스를 호출하는 데 사용되는 WCF 서비스 계약 정의:</span><span class="sxs-lookup"><span data-stu-id="5ff1d-112">Define a WCF service contract  that will be used to call the REST-style service:</span></span>  
  
```csharp
[ServiceContract]
public interface INormalInterface
{
    [OperationContract]
    int CallAdd(int x, int y);
    
    [OperationContract]
    string CallEcho(string input);
}
```  
  
## <a name="implement-the-wcf-service-contract"></a><span data-ttu-id="5ff1d-113">WCF 서비스 계약 구현</span><span class="sxs-lookup"><span data-stu-id="5ff1d-113">Implement the WCF service contract</span></span>  
 <span data-ttu-id="5ff1d-114">WCF 서비스 계약 구현:</span><span class="sxs-lookup"><span data-stu-id="5ff1d-114">Implement the WCF service contract:</span></span>  
  
```csharp
public class NormalService : INormalInterface  
{  
    static MyRestClient client = new MyRestClient(RestServiceBaseAddress);  
    public int CallAdd(int x, int y)  
    {  
        return client.Add(x, y);  
    }  
    
    public string CallEcho(string input)  
    {  
        return client.Echo(input);  
    }  
}  
```  
  
## <a name="create-the-client-proxy-for-the-rest-style-service"></a><span data-ttu-id="5ff1d-115">REST 스타일 서비스에 대한 클라이언트 프록시 만들기</span><span class="sxs-lookup"><span data-stu-id="5ff1d-115">Create the client proxy for the REST-style service</span></span>  
 <span data-ttu-id="5ff1d-116">사용 하 여 <!--zz<xref:System.ServiceModel.ClientBase%60>--> `System.ServiceModel.ClientBase` 클라이언트 프록시를 구현 합니다.</span><span class="sxs-lookup"><span data-stu-id="5ff1d-116">Using <!--zz<xref:System.ServiceModel.ClientBase%60>--> `System.ServiceModel.ClientBase` implement the client proxy.</span></span> <span data-ttu-id="5ff1d-117">호출되는 각 메서드에 대해 새로운 <xref:System.ServiceModel.OperationContextScope>가 생성되고 작업 호출에 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="5ff1d-117">For each method called, a new <xref:System.ServiceModel.OperationContextScope> is created and used to call the operation.</span></span>  
  
```csharp
public class MyRestClient : ClientBase<IRestInterface>, IRestInterface
{
    public MyRestClient(string address)
        : base(new WebHttpBinding(), new EndpointAddress(address))
    {
        this.Endpoint.Behaviors.Add(new WebHttpBehavior());
    }

    public int Add(int x, int y)
    {
        using (new OperationContextScope(this.InnerChannel))
        {
            return base.Channel.Add(x, y);
        }
    }

    public string Echo(string input)
    {
        using (new OperationContextScope(this.InnerChannel))
        {
            return base.Channel.Echo(input);
        }
    }
}
```  
  
## <a name="host-and-call-the-services"></a><span data-ttu-id="5ff1d-118">서비스 호스트 및 호출</span><span class="sxs-lookup"><span data-stu-id="5ff1d-118">Host and call the services</span></span>  
 <span data-ttu-id="5ff1d-119">필요한 끝점 및 동작을 추가하여 콘솔 응용 프로그램에서 두 서비스를 모두 호스트합니다.</span><span class="sxs-lookup"><span data-stu-id="5ff1d-119">Host both services in a console app, adding the needed endpoints and behaviors.</span></span> <span data-ttu-id="5ff1d-120">그런 후 일반 WCF 서비스를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="5ff1d-120">And then call the regular WCF service:</span></span>  
  
```csharp
public static void Main()
{
    ServiceHost restHost = new ServiceHost(typeof(RestService), new Uri(RestServiceBaseAddress));
    restHost.AddServiceEndpoint(typeof(IRestInterface), new WebHttpBinding(), "").Behaviors.Add(new WebHttpBehavior());
    restHost.Open();

    ServiceHost normalHost = new ServiceHost(typeof(NormalService), new Uri(NormalServiceBaseAddress));
    normalHost.AddServiceEndpoint(typeof(INormalInterface), new BasicHttpBinding(), "");
    normalHost.Open();

    Console.WriteLine("Hosts opened");

    ChannelFactory<INormalInterface> factory = new ChannelFactory<INormalInterface>(new BasicHttpBinding(), new EndpointAddress(NormalServiceBaseAddress));
    INormalInterface proxy = factory.CreateChannel();

    Console.WriteLine(proxy.CallAdd(123, 456));
    Console.WriteLine(proxy.CallEcho("Hello world"));
}
```  
  
## <a name="complete-code-listing"></a><span data-ttu-id="5ff1d-121">전체 코드 목록</span><span class="sxs-lookup"><span data-stu-id="5ff1d-121">Complete code listing</span></span>  
 <span data-ttu-id="5ff1d-122">다음은 이 항목에서 구현된 예제의 전체 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="5ff1d-122">The following is a complete listing of the sample implemented in this topic:</span></span>  
  
```csharp
public class CallingRESTSample  
{  
    static readonly string RestServiceBaseAddress = "http://" + Environment.MachineName + ":8008/Service";  
    static readonly string NormalServiceBaseAddress = "http://" + Environment.MachineName + ":8000/Service";  

    [ServiceContract]  
    public interface IRestInterface  
    {  
        [OperationContract, WebGet]  
        int Add(int x, int y);  
        [OperationContract, WebGet]  
        string Echo(string input);  
    }  

    [ServiceContract]  
    public interface INormalInterface  
    {  
        [OperationContract]  
        int CallAdd(int x, int y);  
        [OperationContract]  
        string CallEcho(string input);  
    }  

    public class RestService : IRestInterface  
    {  
        public int Add(int x, int y)  
        {  
            return x + y;  
        }  

        public string Echo(string input)  
        {  
            return input;  
        }  
    }  

    public class MyRestClient : ClientBase<IRestInterface>, IRestInterface  
    {  
        public MyRestClient(string address)  
            : base(new WebHttpBinding(), new EndpointAddress(address))  
        {  
            this.Endpoint.Behaviors.Add(new WebHttpBehavior());  
        }  

        public int Add(int x, int y)  
        {  
            using (new OperationContextScope(this.InnerChannel))  
            {  
                return base.Channel.Add(x, y);  
            }  
        }  

        public string Echo(string input)  
        {  
            using (new OperationContextScope(this.InnerChannel))  
            {  
                return base.Channel.Echo(input);  
            }  
        }  
    }  

    public class NormalService : INormalInterface  
    {  
        static MyRestClient client = new MyRestClient(RestServiceBaseAddress);  
        public int CallAdd(int x, int y)  
        {  
            return client.Add(x, y);  
        }  

        public string CallEcho(string input)  
        {  
            return client.Echo(input);  
        }  
    }
    
    public static void Main()  
    {  
        ServiceHost restHost = new ServiceHost(typeof(RestService), new Uri(RestServiceBaseAddress));  
        restHost.AddServiceEndpoint(typeof(IRestInterface), new WebHttpBinding(), "").Behaviors.Add(new WebHttpBehavior());  
        restHost.Open();  

        ServiceHost normalHost = new ServiceHost(typeof(NormalService), new Uri(NormalServiceBaseAddress));  
        normalHost.AddServiceEndpoint(typeof(INormalInterface), new BasicHttpBinding(), "");  
        normalHost.Open();  

        Console.WriteLine("Hosts opened");  

        ChannelFactory<INormalInterface> factory = new ChannelFactory<INormalInterface>(new BasicHttpBinding(), new EndpointAddress(NormalServiceBaseAddress));  
        INormalInterface proxy = factory.CreateChannel();  

        Console.WriteLine(proxy.CallAdd(123, 456));  
        Console.WriteLine(proxy.CallEcho("Hello world"));  
    }  
}
```
  
## <a name="see-also"></a><span data-ttu-id="5ff1d-123">참고 항목</span><span class="sxs-lookup"><span data-stu-id="5ff1d-123">See Also</span></span>  
 [<span data-ttu-id="5ff1d-124">방법: 기본 WCF 웹 HTTP 서비스 만들기</span><span class="sxs-lookup"><span data-stu-id="5ff1d-124">How to: Create a Basic WCF Web HTTP Service</span></span>](../../../../docs/framework/wcf/feature-details/how-to-create-a-basic-wcf-web-http-service.md)  
 [<span data-ttu-id="5ff1d-125">WCF 웹 HTTP 프로그래밍 개체 모델</span><span class="sxs-lookup"><span data-stu-id="5ff1d-125">WCF Web HTTP Programming Object Model</span></span>](../../../../docs/framework/wcf/feature-details/wcf-web-http-programming-object-model.md)
