---
title: '방법: 프로그래밍 방식으로 WCF 서비스 및 클라이언트에 검색 기능 추가'
ms.date: 03/30/2017
ms.assetid: 4f7ae7ab-6fc8-4769-9730-c14d43f7b9b1
ms.openlocfilehash: de227e8df895dd4c031aadce16102559c43e47ce
ms.sourcegitcommit: c7a7e1468bf0fa7f7065de951d60dfc8d5ba89f5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/14/2019
ms.locfileid: "65586616"
---
# <a name="how-to-programmatically-add-discoverability-to-a-wcf-service-and-client"></a><span data-ttu-id="fcf69-102">방법: 프로그래밍 방식으로 WCF 서비스 및 클라이언트에 검색 기능 추가</span><span class="sxs-lookup"><span data-stu-id="fcf69-102">How to: Programmatically Add Discoverability to a WCF Service and Client</span></span>
<span data-ttu-id="fcf69-103">이 항목에서는 Windows Communication Foundation (WCF) 서비스를 검색할 수 있도록 설정 하는 방법에 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="fcf69-103">This topic explains how to make a Windows Communication Foundation (WCF) service discoverable.</span></span> <span data-ttu-id="fcf69-104">기반이 되는 [Self-host](https://go.microsoft.com/fwlink/?LinkId=145523) 샘플입니다.</span><span class="sxs-lookup"><span data-stu-id="fcf69-104">It is based on the [Self-Host](https://go.microsoft.com/fwlink/?LinkId=145523) sample.</span></span>  
  
### <a name="to-configure-the-existing-self-host-service-sample-for-discovery"></a><span data-ttu-id="fcf69-105">기존 자체 호스팅 서비스 샘플을 검색용으로 구성하려면</span><span class="sxs-lookup"><span data-stu-id="fcf69-105">To configure the existing Self-Host service sample for Discovery</span></span>  
  
1. <span data-ttu-id="fcf69-106">Visual Studio 2012에서 자체 호스트 솔루션을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="fcf69-106">Open the Self-Host solution in Visual Studio 2012.</span></span> <span data-ttu-id="fcf69-107">샘플은 TechnologySamples\Basic\Service\Hosting\SelfHost 디렉터리에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fcf69-107">The sample is located in the TechnologySamples\Basic\Service\Hosting\SelfHost directory.</span></span>  
  
2. <span data-ttu-id="fcf69-108">서비스 프로젝트에 `System.ServiceModel.Discovery.dll`에 대한 참조를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="fcf69-108">Add a reference to `System.ServiceModel.Discovery.dll` to the service project.</span></span> <span data-ttu-id="fcf69-109">"System 라는 오류 메시지가 표시 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fcf69-109">You may see an error message saying "System.</span></span> <span data-ttu-id="fcf69-110">나타나면 또는 해당 종속성 중 하나... 프로젝트에서 지정한 것 보다 최신 버전의.NET Framework 필요 " 이 메시지를 표시 하는 경우 솔루션 탐색기에서 프로젝트를 마우스 오른쪽 단추로 클릭 하 고 선택 **속성**합니다.</span><span class="sxs-lookup"><span data-stu-id="fcf69-110">ServiceModel.Discovery.dll or one of its dependencies requires a later version of the .NET Framework than the one specified in the project …" If you see this message, right-click the project in the Solution Explorer and choose **Properties**.</span></span> <span data-ttu-id="fcf69-111">에 **프로젝트 속성** 창 있는지 확인 합니다 **대상 프레임 워크** 는 [!INCLUDE[netfx_current_long](../../../../includes/netfx-current-long-md.md)].</span><span class="sxs-lookup"><span data-stu-id="fcf69-111">In the **Project Properties** window, make sure that the **Target Framework** is [!INCLUDE[netfx_current_long](../../../../includes/netfx-current-long-md.md)].</span></span>  
  
3. <span data-ttu-id="fcf69-112">Service.cs 파일을 열고 다음 `using` 문을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="fcf69-112">Open the Service.cs file and add the following `using` statement.</span></span>  
  
    ```csharp  
    using System.ServiceModel.Discovery;  
    ```  
  
4. <span data-ttu-id="fcf69-113">`Main()` 메서드의 `using` 문 안에서 서비스 호스트에 <xref:System.ServiceModel.Discovery.ServiceDiscoveryBehavior> 인스턴스를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="fcf69-113">In the `Main()` method, inside the `using` statement, add a <xref:System.ServiceModel.Discovery.ServiceDiscoveryBehavior> instance to the service host.</span></span>  
  
    ```csharp  
    public static void Main()  
    {  
        // Create a ServiceHost for the CalculatorService type.  
        using (ServiceHost serviceHost = new ServiceHost(typeof(CalculatorService)))  
        {  
            // Add a ServiceDiscoveryBehavior  
            serviceHost.Description.Behaviors.Add(new ServiceDiscoveryBehavior());                  
  
            // ...  
        }  
    }  
    ```  
  
     <span data-ttu-id="fcf69-114"><xref:System.ServiceModel.Discovery.ServiceDiscoveryBehavior>는 자신이 적용되는 서비스가 검색 가능하게 되도록 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="fcf69-114">The <xref:System.ServiceModel.Discovery.ServiceDiscoveryBehavior> specifies that the service it is applied to is discoverable.</span></span>  
  
5. <span data-ttu-id="fcf69-115"><xref:System.ServiceModel.Discovery.UdpDiscoveryEndpoint>를 추가하는 코드 바로 뒤에 있는 서비스 호스트에 <xref:System.ServiceModel.Discovery.ServiceDiscoveryBehavior>를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="fcf69-115">Add a <xref:System.ServiceModel.Discovery.UdpDiscoveryEndpoint> to the service host right after the code that adds the <xref:System.ServiceModel.Discovery.ServiceDiscoveryBehavior>.</span></span>  
  
    ```csharp  
    // Add ServiceDiscoveryBehavior  
    serviceHost.Description.Behaviors.Add(new ServiceDiscoveryBehavior());  
  
    // Add a UdpDiscoveryEndpoint  
    serviceHost.AddServiceEndpoint(new UdpDiscoveryEndpoint());  
    ```  
  
     <span data-ttu-id="fcf69-116">이 코드는 검색 메시지를 표준 UDP 검색 엔드포인트에 보내도록 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="fcf69-116">This code specifies that discovery messages should be sent to the standard UDP discovery endpoint.</span></span>  
  
### <a name="to-create-a-client-application-that-uses-discovery-to-call-the-service"></a><span data-ttu-id="fcf69-117">검색을 사용하는 클라이언트 애플리케이션을 만들어 서비스를 호출하려면</span><span class="sxs-lookup"><span data-stu-id="fcf69-117">To create a client application that uses discovery to call the service</span></span>  
  
1. <span data-ttu-id="fcf69-118">`DiscoveryClientApp`라는 솔루션에 새 콘솔 애플리케이션을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="fcf69-118">Add a new console application to the solution called `DiscoveryClientApp`.</span></span>  
  
2. <span data-ttu-id="fcf69-119">`System.ServiceModel.dll` 및 `System.ServiceModel.Discovery.dll`에 대한 참조를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="fcf69-119">Add a reference to `System.ServiceModel.dll` and `System.ServiceModel.Discovery.dll`</span></span>  
  
3. <span data-ttu-id="fcf69-120">GeneratedClient.cs 및 App.config 파일을 기본 클라이언트 프로젝트에서 새 DiscoveryClientApp 프로젝트로 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="fcf69-120">Copy the GeneratedClient.cs and App.config files from the existing client project to the new DiscoveryClientApp project.</span></span> <span data-ttu-id="fcf69-121">이렇게 하려면 파일을 마우스 오른쪽 단추로 합니다 **솔루션 탐색기**를 선택 **복사**를 선택한 후는 **DiscoveryClientApp** 선택한프로젝트를마우스오른쪽단추로클릭**붙여넣기**합니다.</span><span class="sxs-lookup"><span data-stu-id="fcf69-121">To do this, right-click the files in the **Solution Explorer**, select **Copy**, and then select the **DiscoveryClientApp** project, right-click and select **Paste**.</span></span>  
  
4. <span data-ttu-id="fcf69-122">Program.cs를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="fcf69-122">Open Program.cs.</span></span>  
  
5. <span data-ttu-id="fcf69-123">다음 `using` 문을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="fcf69-123">Add the following `using` statements.</span></span>  
  
    ```csharp  
    using System.ServiceModel;  
    using System.ServiceModel.Discovery;  
    using Microsoft.ServiceModel.Samples;  
    ```  
  
6. <span data-ttu-id="fcf69-124">`FindCalculatorServiceAddress()`라는 정적 메서드를 `Program` 클래스에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="fcf69-124">Add a static method called `FindCalculatorServiceAddress()` to the `Program` class.</span></span>  
  
    ```csharp  
    static EndpointAddress FindCalculatorServiceAddress()  
    {  
    }  
    ```  
  
     <span data-ttu-id="fcf69-125">이 메서드는 검색을 사용하여 `CalculatorService` 서비스를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="fcf69-125">This method uses discovery to search for the `CalculatorService` service.</span></span>  
  
7. <span data-ttu-id="fcf69-126">`FindCalculatorServiceAddress` 메서드 안에서 생성자에 <xref:System.ServiceModel.Discovery.DiscoveryClient>를 전달하여 새 <xref:System.ServiceModel.Discovery.UdpDiscoveryEndpoint> 인스턴스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="fcf69-126">Inside the `FindCalculatorServiceAddress` method, create a new <xref:System.ServiceModel.Discovery.DiscoveryClient> instance, passing in a <xref:System.ServiceModel.Discovery.UdpDiscoveryEndpoint> to the constructor.</span></span>  
  
    ```csharp  
    static EndpointAddress FindCalculatorServiceAddress()  
    {  
        // Create DiscoveryClient  
        DiscoveryClient discoveryClient = new DiscoveryClient(new UdpDiscoveryEndpoint());  
    }  
    ```  
  
     <span data-ttu-id="fcf69-127">이렇게 하면 WCF는는 <xref:System.ServiceModel.Discovery.DiscoveryClient> 클래스 검색 메시지를 받고 보내는 데 표준 UDP 검색 끝점을 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fcf69-127">This tells WCF that the <xref:System.ServiceModel.Discovery.DiscoveryClient> class should use the standard UDP discovery endpoint to send and receive discovery messages.</span></span>  
  
8. <span data-ttu-id="fcf69-128">다음 줄에서 <xref:System.ServiceModel.Discovery.DiscoveryClient.Find%2A> 메서드를 호출하고 검색하려는 서비스 계약이 포함된 <xref:System.ServiceModel.Discovery.FindCriteria> 인스턴스를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="fcf69-128">On the next line, call the <xref:System.ServiceModel.Discovery.DiscoveryClient.Find%2A> method and specify a <xref:System.ServiceModel.Discovery.FindCriteria> instance that contains the service contract you want to search for.</span></span> <span data-ttu-id="fcf69-129">이 경우 `ICalculator`를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="fcf69-129">In this case, specify `ICalculator`.</span></span>  
  
    ```csharp  
    // Find ICalculatorService endpoints              
    FindResponse findResponse = discoveryClient.Find(new FindCriteria(typeof(ICalculator)));  
    ```  
  
9. <span data-ttu-id="fcf69-130"><xref:System.ServiceModel.Discovery.DiscoveryClient.Find%2A>를 호출한 후 일치하는 서비스가 하나 이상 있는지 확인하고 첫 번째 일치하는 서비스의 <xref:System.ServiceModel.EndpointAddress>를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="fcf69-130">After the call to <xref:System.ServiceModel.Discovery.DiscoveryClient.Find%2A>, check to see if there is at least one matching service and return the <xref:System.ServiceModel.EndpointAddress> of the first matching service.</span></span> <span data-ttu-id="fcf69-131">그렇지 않으면 `null`을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="fcf69-131">Otherwise return `null`.</span></span>  
  
    ```csharp  
    if (findResponse.Endpoints.Count > 0)  
    {  
        return findResponse.Endpoints[0].Address;  
    }  
    else  
    {  
        return null;  
    }  
    ```  
  
10. <span data-ttu-id="fcf69-132">`InvokeCalculatorService`라는 정적 메서드를 `Program` 클래스에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="fcf69-132">Add a static method named `InvokeCalculatorService` to the `Program` class.</span></span>  
  
    ```csharp  
    static void InvokeCalculatorService(EndpointAddress endpointAddress)  
    {  
    }  
    ```  
  
     <span data-ttu-id="fcf69-133">이 메서드는 `FindCalculatorServiceAddress`에서 반환되는 엔드포인트 주소를 사용하여 계산기 서비스를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="fcf69-133">This method uses the endpoint address returned from `FindCalculatorServiceAddress` to call the calculator service.</span></span>  
  
11. <span data-ttu-id="fcf69-134">`InvokeCalculatorService` 메서드 안에서 `CalculatorServiceClient` 클래스의 인스턴스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="fcf69-134">Inside the `InvokeCalculatorService` method, create an instance of the `CalculatorServiceClient` class.</span></span> <span data-ttu-id="fcf69-135">이 클래스는 정의한 합니다 [Self-host](https://go.microsoft.com/fwlink/?LinkId=145523) 샘플입니다.</span><span class="sxs-lookup"><span data-stu-id="fcf69-135">This class is defined by the [Self-Host](https://go.microsoft.com/fwlink/?LinkId=145523) sample.</span></span> <span data-ttu-id="fcf69-136">이 클래스는 Svcutil.exe를 사용하여 생성되었습니다.</span><span class="sxs-lookup"><span data-stu-id="fcf69-136">It was generated using Svcutil.exe.</span></span>  
  
    ```csharp  
    // Create a client  
    CalculatorClient client = new CalculatorClient();  
    ```  
  
12. <span data-ttu-id="fcf69-137">다음 줄에서 클라이언트의 엔드포인트 주소를 `FindCalculatorServiceAddress()`에서 반환되는 엔드포인트 주소로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="fcf69-137">On the next line, set the endpoint address of the client to the endpoint address returned from `FindCalculatorServiceAddress()`.</span></span>  
  
    ```csharp  
    // Connect to the discovered service endpoint  
    client.Endpoint.Address = endpointAddress;  
    ```  
  
13. <span data-ttu-id="fcf69-138">이전 단계의 코드 바로 뒤에서 계산기 서비스에 의해 노출되는 메서드를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="fcf69-138">Immediately after the code for the previous step, call the methods exposed by the calculator service.</span></span>  
  
    ```csharp  
    Console.WriteLine("Invoking CalculatorService at {0}", endpointAddress);  
  
    double value1 = 100.00D;  
    double value2 = 15.99D;  
  
    // Call the Add service operation.  
    double result = client.Add(value1, value2);  
    Console.WriteLine("Add({0},{1}) = {2}", value1, value2, result);  
  
    // Call the Subtract service operation.  
    result = client.Subtract(value1, value2);  
    Console.WriteLine("Subtract({0},{1}) = {2}", value1, value2, result);  
  
    // Call the Multiply service operation.  
    result = client.Multiply(value1, value2);  
    Console.WriteLine("Multiply({0},{1}) = {2}", value1, value2, result);  
  
    // Call the Divide service operation.  
    result = client.Divide(value1, value2);  
    Console.WriteLine("Divide({0},{1}) = {2}", value1, value2, result);  
    Console.WriteLine();  
  
    //Closing the client gracefully closes the connection and cleans up resources  
    client.Close();  
    ```  
  
14. <span data-ttu-id="fcf69-139">`Main()` 클래스의 `Program` 메서드에 `FindCalculatorServiceAddress`를 호출하는 코드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="fcf69-139">Add code to the `Main()` method in the `Program` class to call `FindCalculatorServiceAddress`.</span></span>  
  
    ```csharp  
    public static void Main()  
    {  
        EndpointAddress endpointAddress = FindCalculatorServiceAddress();  
    }  
    ```  
  
15. <span data-ttu-id="fcf69-140">다음 줄에서 `InvokeCalculatorService()`를 호출하고 `FindCalculatorServiceAddress()`에서 반환되는 엔드포인트 주소를 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="fcf69-140">On the next line, call the `InvokeCalculatorService()` and pass in the endpoint address returned from `FindCalculatorServiceAddress()`.</span></span>  
  
    ```csharp  
    if (endpointAddress != null)  
    {  
        InvokeCalculatorService(endpointAddress);  
    }  
  
    Console.WriteLine("Press <ENTER> to exit.");  
    Console.ReadLine();  
    ```  
  
### <a name="to-test-the-application"></a><span data-ttu-id="fcf69-141">애플리케이션을 테스트하려면</span><span class="sxs-lookup"><span data-stu-id="fcf69-141">To test the application</span></span>  
  
1. <span data-ttu-id="fcf69-142">권한이 높은 명령 프롬프트를 열고 Service.exe를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="fcf69-142">Open an elevated command prompt and run Service.exe.</span></span>  
  
2. <span data-ttu-id="fcf69-143">명령 프롬프트를 열고 Discoveryclientapp.exe를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="fcf69-143">Open a command prompt and run Discoveryclientapp.exe.</span></span>  
  
3. <span data-ttu-id="fcf69-144">service.exe의 출력이 다음과 같이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="fcf69-144">The output from service.exe should look like the following output.</span></span>  
  
    ```Output  
    Received Add(100,15.99)  
    Return: 115.99  
    Received Subtract(100,15.99)  
    Return: 84.01  
    Received Multiply(100,15.99)  
    Return: 1599  
    Received Divide(100,15.99)  
    Return: 6.25390869293308  
    ```  
  
4. <span data-ttu-id="fcf69-145">Discoveryclientapp.exe의 출력이 다음과 같이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="fcf69-145">The output from Discoveryclientapp.exe should look like the following output.</span></span>  
  
    ```Output  
    Invoking CalculatorService at http://localhost:8000/ServiceModelSamples/service  
    Add(100,15.99) = 115.99  
    Subtract(100,15.99) = 84.01  
    Multiply(100,15.99) = 1599  
    Divide(100,15.99) = 6.25390869293308  
  
    Press <ENTER> to exit.  
    ```  
  
## <a name="example"></a><span data-ttu-id="fcf69-146">예제</span><span class="sxs-lookup"><span data-stu-id="fcf69-146">Example</span></span>  
 <span data-ttu-id="fcf69-147">다음은 이 샘플의 코드 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="fcf69-147">The following is a listing of the code for this sample.</span></span> <span data-ttu-id="fcf69-148">이 코드는 기반으로 하므로 합니다 [Self-host](https://go.microsoft.com/fwlink/?LinkId=145523) 샘플에서 변경 된 파일만 나열 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fcf69-148">Because this code is based on the [Self-Host](https://go.microsoft.com/fwlink/?LinkId=145523) sample, only those files that are changed are listed.</span></span> <span data-ttu-id="fcf69-149">Self-host 샘플에 대 한 자세한 내용은 참조 하세요. [설치 지침](https://go.microsoft.com/fwlink/?LinkId=145522)합니다.</span><span class="sxs-lookup"><span data-stu-id="fcf69-149">For more information about the Self-Host sample, see [Setup Instructions](https://go.microsoft.com/fwlink/?LinkId=145522).</span></span>  
  
```csharp  
// Service.cs  
using System;  
using System.Configuration;  
using System.ServiceModel;  
using System.ServiceModel.Discovery;  
  
namespace Microsoft.ServiceModel.Samples  
{  
    // See SelfHost sample for service contract and implementation  
    // ...  
  
        // Host the service within this EXE console application.  
        public static void Main()  
        {  
            // Create a ServiceHost for the CalculatorService type.  
            using (ServiceHost serviceHost = new ServiceHost(typeof(CalculatorService)))  
            {  
                // Add the ServiceDiscoveryBehavior to make the service discoverable  
                serviceHost.Description.Behaviors.Add(new ServiceDiscoveryBehavior());  
                serviceHost.AddServiceEndpoint(new UdpDiscoveryEndpoint());  
  
                // Open the ServiceHost to create listeners and start listening for messages.  
                serviceHost.Open();  
  
                // The service can now be accessed.  
                Console.WriteLine("The service is ready.");  
                Console.WriteLine("Press <ENTER> to terminate service.");  
                Console.WriteLine();  
                Console.ReadLine();  
            }  
        }  
    }  
}  
```  
  
```csharp  
// Program.cs  
using System;  
using System.Collections.Generic;  
using System.Linq;  
using System.ServiceModel;  
using System.ServiceModel.Discovery;  
using Microsoft.ServiceModel.Samples;  
using System.Text;  
  
namespace DiscoveryClientApp  
{  
    class Program  
    {  
        static EndpointAddress FindCalculatorServiceAddress()  
        {  
            // Create DiscoveryClient  
            DiscoveryClient discoveryClient = new DiscoveryClient(new UdpDiscoveryEndpoint());  
  
            // Find ICalculatorService endpoints              
            FindResponse findResponse = discoveryClient.Find(new FindCriteria(typeof(ICalculator)));  
  
            if (findResponse.Endpoints.Count > 0)  
            {  
                return findResponse.Endpoints[0].Address;  
            }  
            else  
            {  
                return null;  
            }  
        }  
  
        static void InvokeCalculatorService(EndpointAddress endpointAddress)  
        {  
            // Create a client  
            CalculatorClient client = new CalculatorClient();  
  
            // Connect to the discovered service endpoint  
            client.Endpoint.Address = endpointAddress;  
  
            Console.WriteLine("Invoking CalculatorService at {0}", endpointAddress);  
  
            double value1 = 100.00D;  
            double value2 = 15.99D;  
  
            // Call the Add service operation.  
            double result = client.Add(value1, value2);  
            Console.WriteLine("Add({0},{1}) = {2}", value1, value2, result);  
  
            // Call the Subtract service operation.  
            result = client.Subtract(value1, value2);  
            Console.WriteLine("Subtract({0},{1}) = {2}", value1, value2, result);  
  
            // Call the Multiply service operation.  
            result = client.Multiply(value1, value2);  
            Console.WriteLine("Multiply({0},{1}) = {2}", value1, value2, result);  
  
            // Call the Divide service operation.  
            result = client.Divide(value1, value2);  
            Console.WriteLine("Divide({0},{1}) = {2}", value1, value2, result);  
            Console.WriteLine();  
  
            //Closing the client gracefully closes the connection and cleans up resources  
            client.Close();  
        }  
        static void Main(string[] args)  
        {  
            EndpointAddress endpointAddress = FindCalculatorServiceAddress();  
  
            if (endpointAddress != null)  
            {  
                InvokeCalculatorService(endpointAddress);  
            }  
  
            Console.WriteLine("Press <ENTER> to exit.");  
            Console.ReadLine();  
  
        }  
    }  
}  
```  

## <a name="see-also"></a><span data-ttu-id="fcf69-150">참고자료</span><span class="sxs-lookup"><span data-stu-id="fcf69-150">See also</span></span>

- [<span data-ttu-id="fcf69-151">WCF 검색 개요</span><span class="sxs-lookup"><span data-stu-id="fcf69-151">WCF Discovery Overview</span></span>](../../../../docs/framework/wcf/feature-details/wcf-discovery-overview.md)
- [<span data-ttu-id="fcf69-152">WCF 검색 개체 모델</span><span class="sxs-lookup"><span data-stu-id="fcf69-152">WCF Discovery Object Model</span></span>](../../../../docs/framework/wcf/feature-details/wcf-discovery-object-model.md)
