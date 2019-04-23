---
title: 바인딩에 시간 제한 값 구성
ms.date: 03/30/2017
ms.assetid: b5c825a2-b48f-444a-8659-61751ff11d34
ms.openlocfilehash: f323dfff338f8a3ba24caab6df3b3916d3ae0d13
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59773248"
---
# <a name="configuring-timeout-values-on-a-binding"></a><span data-ttu-id="cd588-102">바인딩에 시간 제한 값 구성</span><span class="sxs-lookup"><span data-stu-id="cd588-102">Configuring Timeout Values on a Binding</span></span>
<span data-ttu-id="cd588-103">WCF 바인딩에서 사용할 수 있는 시간 제한 설정은 여러 가지가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cd588-103">There are a number of timeout settings available in WCF bindings.</span></span> <span data-ttu-id="cd588-104">이러한 시간 제한 설정을 정확하게 설정하면 서비스 성능이 향상될 뿐만 아니라 서비스의 유용성과 보안에도 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="cd588-104">Setting these timeout settings correctly can improve not only your service’s performance but also play a role in the usability and security of your service.</span></span> <span data-ttu-id="cd588-105">WCF 바인딩에서 사용할 수 있는 시간 제한은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="cd588-105">The following timeouts are available on WCF bindings:</span></span>  
  
1. <span data-ttu-id="cd588-106">OpenTimeout</span><span class="sxs-lookup"><span data-stu-id="cd588-106">OpenTimeout</span></span>  
  
2. <span data-ttu-id="cd588-107">CloseTimeout</span><span class="sxs-lookup"><span data-stu-id="cd588-107">CloseTimeout</span></span>  
  
3. <span data-ttu-id="cd588-108">SendTimeout</span><span class="sxs-lookup"><span data-stu-id="cd588-108">SendTimeout</span></span>  
  
4. <span data-ttu-id="cd588-109">ReceiveTimeout</span><span class="sxs-lookup"><span data-stu-id="cd588-109">ReceiveTimeout</span></span>  
  
## <a name="wcf-binding-timeouts"></a><span data-ttu-id="cd588-110">WCF 바인딩 시간 제한</span><span class="sxs-lookup"><span data-stu-id="cd588-110">WCF Binding Timeouts</span></span>  
 <span data-ttu-id="cd588-111">이 항목에서 설명하는 각 설정은 바인딩 자체에서 코드 또는 구성으로 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="cd588-111">Each of the settings discussed in this topic are made on the binding itself, either in code or configuration.</span></span> <span data-ttu-id="cd588-112">다음 코드에서는 자체 호스트된 서비스의 컨텍스트에서 WCF 바인딩에 시간 제한을 프로그래밍 방식으로 설정하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="cd588-112">The following code shows how to programmatically set timeouts on a WCF binding in the context of a self-hosted service.</span></span>  
  
```csharp  
public static void Main()
{
    Uri baseAddress = new Uri("http://localhost/MyServer/MyService");
    
    try
    {
        ServiceHost serviceHost = new ServiceHost(typeof(CalculatorService));
        
        WSHttpBinding binding = new WSHttpBinding();
        binding.OpenTimeout = new TimeSpan(0, 10, 0);
        binding.CloseTimeout = new TimeSpan(0, 10, 0);
        binding.SendTimeout = new TimeSpan(0, 10, 0);
        binding.ReceiveTimeout = new TimeSpan(0, 10, 0);
        
        serviceHost.AddServiceEndpoint("ICalculator", binding, baseAddress);
        serviceHost.Open();
        
        // The service can now be accessed.
        Console.WriteLine("The service is ready.");
        Console.WriteLine("Press <ENTER> to terminate service.");
        Console.WriteLine();
        Console.ReadLine();
    }
    catch (CommunicationException ex)
    {
        // Handle exception ...
    }
}
```  
  
 <span data-ttu-id="cd588-113">다음 예제에서는 구성 파일에서 바인딩에 시간 제한을 구성하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="cd588-113">The following example shows how to configure timeouts on a binding in a configuration file.</span></span>  
  
```xml  
<configuration>
  <system.serviceModel>
    <bindings>
      <wsHttpBinding>
        <binding openTimeout="00:10:00" 
                 closeTimeout="00:10:00" 
                 sendTimeout="00:10:00" 
                 receiveTimeout="00:10:00">
        </binding>
      </wsHttpBinding>
    </bindings>
  </system.serviceModel>
</configuration>
```  
  
 <span data-ttu-id="cd588-114">이러한 설정에 대한 자세한 내용은 <xref:System.ServiceModel.Channels.Binding> 클래스 문서를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="cd588-114">More information about these settings can be found in the documentation for the <xref:System.ServiceModel.Channels.Binding> class.</span></span>  
  
### <a name="client-side-timeouts"></a><span data-ttu-id="cd588-115">클라이언트 측 시간 제한</span><span class="sxs-lookup"><span data-stu-id="cd588-115">Client-side Timeouts</span></span>  
 <span data-ttu-id="cd588-116">클라이언트 측:</span><span class="sxs-lookup"><span data-stu-id="cd588-116">On the client side:</span></span>  
  
1. <span data-ttu-id="cd588-117">SendTimeout - 요청/회신 서비스 작업의 회신 메시지 수신을 포함하여 메시지 보내기의 전체 과정을 제어하는 OperationTimeout을 초기화하는 데 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="cd588-117">SendTimeout – used to initialize the OperationTimeout, which governs the whole process of sending a message, including receiving a reply message for a request/reply service operation.</span></span> <span data-ttu-id="cd588-118">이 시간 제한은 콜백 계약 메서드에서 회신 메시지를 보낼 때도 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="cd588-118">This timeout also applies when sending reply messages from a callback contract method.</span></span>  
  
2. <span data-ttu-id="cd588-119">OpenTimeout – 명시적 시간 제한 값을 지정 하는 경우 채널을 열 때 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="cd588-119">OpenTimeout – used when opening channels when no explicit timeout value is specified.</span></span>  
  
3. <span data-ttu-id="cd588-120">CloseTimeout – 명시적 시간 제한 값을 지정 하는 경우 채널을 닫을 때 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="cd588-120">CloseTimeout – used when closing channels when no explicit timeout value is specified.</span></span>  
  
4. <span data-ttu-id="cd588-121">ReceiveTimeout – 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="cd588-121">ReceiveTimeout – is not used.</span></span>  
  
### <a name="service-side-timeouts"></a><span data-ttu-id="cd588-122">서비스 쪽 제한 시간</span><span class="sxs-lookup"><span data-stu-id="cd588-122">Service-side Timeouts</span></span>  
 <span data-ttu-id="cd588-123">서비스 측:</span><span class="sxs-lookup"><span data-stu-id="cd588-123">On the service side:</span></span>  
  
1. <span data-ttu-id="cd588-124">SendTimeout, OpenTimeout, CloseTimeout는 클라이언트에서와 동일 합니다.</span><span class="sxs-lookup"><span data-stu-id="cd588-124">SendTimeout, OpenTimeout, CloseTimeout are the same as on the client.</span></span>  
  
2. <span data-ttu-id="cd588-125">ReceiveTimeout – 서비스 프레임워크 레이어에서 제한 시간 만료 전에 세션이 유휴 상태일 수 있는 시간을 제어하는 세션 유휴 시간 제한을 초기화하는 데 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="cd588-125">ReceiveTimeout – used by the Service Framework Layer to initialize the session-idle timeout which controls how long a session can be idle before timing out.</span></span>
