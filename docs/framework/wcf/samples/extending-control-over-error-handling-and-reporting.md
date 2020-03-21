---
title: 오류 처리 및 오류 보고에 대한 확장 제어
ms.date: 03/30/2017
ms.assetid: 45f996a7-fa00-45cb-9d6f-b368f5778aaa
ms.openlocfilehash: 68f3381e8db9d7c0222720dda335b47e30f57ac7
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79183676"
---
# <a name="extending-control-over-error-handling-and-reporting"></a><span data-ttu-id="ad8ac-102">오류 처리 및 오류 보고에 대한 확장 제어</span><span class="sxs-lookup"><span data-stu-id="ad8ac-102">Extending Control Over Error Handling and Reporting</span></span>
<span data-ttu-id="ad8ac-103">이 샘플에서는 <xref:System.ServiceModel.Dispatcher.IErrorHandler> 인터페이스를 사용하여 WCF(Windows 통신 Foundation) 서비스에서 오류 처리 및 오류 보고에 대한 제어를 확장하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="ad8ac-103">This sample demonstrates how to extend control over error handling and error reporting in a Windows Communication Foundation (WCF) service using the <xref:System.ServiceModel.Dispatcher.IErrorHandler> interface.</span></span> <span data-ttu-id="ad8ac-104">샘플은 오류를 처리하기 위해 서비스에 추가된 몇 가지 추가 코드로 [시작하기를](../../../../docs/framework/wcf/samples/getting-started-sample.md) 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="ad8ac-104">The sample is based on the [Getting Started](../../../../docs/framework/wcf/samples/getting-started-sample.md) with some additional code added to the service to handle errors.</span></span> <span data-ttu-id="ad8ac-105">클라이언트에서는 몇 가지 오류 조건을 발생시키고</span><span class="sxs-lookup"><span data-stu-id="ad8ac-105">The client forces several error conditions.</span></span> <span data-ttu-id="ad8ac-106">서비스에서는 해당 오류를 가로채서 파일에 기록합니다.</span><span class="sxs-lookup"><span data-stu-id="ad8ac-106">The service intercepts the errors and logs them in a file.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="ad8ac-107">이 샘플의 설치 절차 및 빌드 지침은 이 항목의 끝부분에 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ad8ac-107">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
 <span data-ttu-id="ad8ac-108">서비스에서는 <xref:System.ServiceModel.Dispatcher.IErrorHandler> 인터페이스를 사용하여 오류를 가로채고, 처리를 수행하고, 오류를 보고하는 방법에 영향을 줄 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ad8ac-108">Services can intercept errors, perform processing, and affect how errors are reported using the <xref:System.ServiceModel.Dispatcher.IErrorHandler> interface.</span></span> <span data-ttu-id="ad8ac-109">인터페이스에는 구현할 수 있는 두 개의 메서드 <xref:System.ServiceModel.Dispatcher.IErrorHandler.ProvideFault%28System.Exception%2CSystem.ServiceModel.Channels.MessageVersion%2CSystem.ServiceModel.Channels.Message%40%29> 및 <xref:System.ServiceModel.Dispatcher.IErrorHandler.HandleError%2A>가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ad8ac-109">The interface has two methods that can be implemented: <xref:System.ServiceModel.Dispatcher.IErrorHandler.ProvideFault%28System.Exception%2CSystem.ServiceModel.Channels.MessageVersion%2CSystem.ServiceModel.Channels.Message%40%29> and <xref:System.ServiceModel.Dispatcher.IErrorHandler.HandleError%2A>.</span></span> <span data-ttu-id="ad8ac-110"><xref:System.ServiceModel.Dispatcher.IErrorHandler.ProvideFault%28System.Exception%2CSystem.ServiceModel.Channels.MessageVersion%2CSystem.ServiceModel.Channels.Message%40%29> 메서드를 사용하면 예외에 대한 응답으로 생성되는 오류 메시지를 추가, 수정 또는 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ad8ac-110">The <xref:System.ServiceModel.Dispatcher.IErrorHandler.ProvideFault%28System.Exception%2CSystem.ServiceModel.Channels.MessageVersion%2CSystem.ServiceModel.Channels.Message%40%29> method allows you to add, modify, or suppress a fault message that is generated in response to an exception.</span></span> <span data-ttu-id="ad8ac-111"><xref:System.ServiceModel.Dispatcher.IErrorHandler.HandleError%2A> 메서드를 사용하면 오류가 발생한 경우 오류 처리를 허용하고 추가 오류 처리를 실행할 수 있는지 여부를 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ad8ac-111">The <xref:System.ServiceModel.Dispatcher.IErrorHandler.HandleError%2A> method allows error processing to take place in the event of an error and controls whether additional error handling can run.</span></span>  
  
 <span data-ttu-id="ad8ac-112">이 샘플에서 `CalculatorErrorHandler` 형식은 <xref:System.ServiceModel.Dispatcher.IErrorHandler> 인터페이스를 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="ad8ac-112">In this sample, the `CalculatorErrorHandler` type implements the <xref:System.ServiceModel.Dispatcher.IErrorHandler> interface.</span></span> <span data-ttu-id="ad8ac-113">먼저</span><span class="sxs-lookup"><span data-stu-id="ad8ac-113">In the</span></span>  
  
 <span data-ttu-id="ad8ac-114"><xref:System.ServiceModel.Dispatcher.IErrorHandler.HandleError%2A> 메서드에서 `CalculatorErrorHandler`는 c:\logs에 있는 Error.txt 텍스트 파일에 오류 로그를 기록합니다.</span><span class="sxs-lookup"><span data-stu-id="ad8ac-114"><xref:System.ServiceModel.Dispatcher.IErrorHandler.HandleError%2A> method, the `CalculatorErrorHandler` writes a log of the error to an Error.txt text file in c:\logs.</span></span> <span data-ttu-id="ad8ac-115">샘플에서는 오류를 기록한 후 제거하지 않으므로 해당 오류를 클라이언트에 다시 보고할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ad8ac-115">Note that the sample logs the fault and does not suppress it, allowing it to be reported back to the client.</span></span>  
  
```csharp
public class CalculatorErrorHandler : IErrorHandler
{
    // Provide a fault. The Message fault parameter can be replaced, or set to
    // null to suppress reporting a fault.

    public void ProvideFault(Exception error, MessageVersion version, ref Message fault)
    {
    }

    // HandleError. Log an error, then allow the error to be handled as usual.
    // Return true if the error is considered as already handled

    public bool HandleError(Exception error)
    {
        using (TextWriter tw = File.AppendText(@"c:\logs\error.txt"))
        {
            if (error != null)
            {
                tw.WriteLine("Exception: " + error.GetType().Name + " - " + error.Message);
            }
            tw.Close();
        }
        return true;
    }
}  
```  
  
 <span data-ttu-id="ad8ac-116">`ErrorBehaviorAttribute`는 서비스에 오류 처리기를 등록하는 데 사용되는 메커니즘입니다.</span><span class="sxs-lookup"><span data-stu-id="ad8ac-116">The `ErrorBehaviorAttribute` exists as a mechanism to register an error handler with a service.</span></span> <span data-ttu-id="ad8ac-117">이 특성에서는 단일 형식 매개 변수를 받습니다.</span><span class="sxs-lookup"><span data-stu-id="ad8ac-117">This attribute takes a single type parameter.</span></span> <span data-ttu-id="ad8ac-118">그 형식은 <xref:System.ServiceModel.Dispatcher.IErrorHandler> 인터페이스를 구현해야 하며 비어 있는 public 생성자가 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ad8ac-118">That type should implement the <xref:System.ServiceModel.Dispatcher.IErrorHandler> interface and should have a public, empty constructor.</span></span> <span data-ttu-id="ad8ac-119">그러면 이 특성에서 해당 오류 처리기 형식의 인스턴스를 만들어 서비스에 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="ad8ac-119">The attribute then instantiates an instance of that error handler type and installs it into the service.</span></span> <span data-ttu-id="ad8ac-120">이 작업을 수행하려면 <xref:System.ServiceModel.Description.IServiceBehavior> 인터페이스를 구현한 다음 <xref:System.ServiceModel.Description.IServiceBehavior.ApplyDispatchBehavior%2A> 메서드를 사용하여 오류 처리기의 인스턴스를 서비스에 추가하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ad8ac-120">It does this by implementing the <xref:System.ServiceModel.Description.IServiceBehavior> interface and then using the <xref:System.ServiceModel.Description.IServiceBehavior.ApplyDispatchBehavior%2A> method to add instances of the error handler to the service.</span></span>  
  
```csharp
// This attribute can be used to install a custom error handler for a service.  
public class ErrorBehaviorAttribute : Attribute, IServiceBehavior  
{  
    Type errorHandlerType;  
  
    public ErrorBehaviorAttribute(Type errorHandlerType)  
    {  
        this.errorHandlerType = errorHandlerType;  
    }  
  
    void IServiceBehavior.Validate(ServiceDescription description, ServiceHostBase serviceHostBase)  
    {  
    }  
  
    void IServiceBehavior.AddBindingParameters(ServiceDescription description, ServiceHostBase serviceHostBase, System.Collections.ObjectModel.Collection<ServiceEndpoint> endpoints, BindingParameterCollection parameters)  
    {  
    }  
  
    void IServiceBehavior.ApplyDispatchBehavior(ServiceDescription description, ServiceHostBase serviceHostBase)  
    {  
        IErrorHandler errorHandler;  
  
        try  
        {  
            errorHandler = (IErrorHandler)Activator.CreateInstance(errorHandlerType);  
        }  
        catch (MissingMethodException e)  
        {  
            throw new ArgumentException("The errorHandlerType specified in the ErrorBehaviorAttribute constructor must have a public empty constructor.", e);  
        }  
        catch (InvalidCastException e)  
        {  
            throw new ArgumentException("The errorHandlerType specified in the ErrorBehaviorAttribute constructor must implement System.ServiceModel.Dispatcher.IErrorHandler.", e);  
        }  
  
        foreach (ChannelDispatcherBase channelDispatcherBase in serviceHostBase.ChannelDispatchers)  
        {  
            ChannelDispatcher channelDispatcher = channelDispatcherBase as ChannelDispatcher;  
            channelDispatcher.ErrorHandlers.Add(errorHandler);  
        }
    }  
}  
```  
  
 <span data-ttu-id="ad8ac-121">샘플에서는 계산기 서비스를 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="ad8ac-121">The sample implements a calculator service.</span></span> <span data-ttu-id="ad8ac-122">클라이언트에서는 잘못된 값이 있는 매개 변수를 공급하여 고의로 서비스에 두 개의 오류를 일으킵니다.</span><span class="sxs-lookup"><span data-stu-id="ad8ac-122">The client deliberately causes two errors to occur on the service by providing parameters with illegal values.</span></span> <span data-ttu-id="ad8ac-123">`CalculatorErrorHandler`에서는 <xref:System.ServiceModel.Dispatcher.IErrorHandler> 인터페이스를 사용하여 로컬 파일에 오류를 기록한 다음 클라이언트에 다시 보고될 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="ad8ac-123">The `CalculatorErrorHandler` uses the <xref:System.ServiceModel.Dispatcher.IErrorHandler> interface to log the errors to a local file and then allows them to be reported back to the client.</span></span> <span data-ttu-id="ad8ac-124">클라이언트에서는 0으로 나누기와 argument-out-of-range 조건을 발생시킵니다.</span><span class="sxs-lookup"><span data-stu-id="ad8ac-124">The client forces a divide by zero and an argument-out-of-range condition.</span></span>  
  
```csharp
try
{  
    Console.WriteLine("Forcing an error in Divide");  
    // Call the Divide service operation - trigger a divide by 0 error.  
    value1 = 22;  
    value2 = 0;  
    result = proxy.Divide(value1, value2);  
    Console.WriteLine("Divide({0},{1}) = {2}", value1, value2, result);  
}  
catch (FaultException e)  
{  
    Console.WriteLine("FaultException: " + e.GetType().Name + " - " + e.Message);  
}  
catch (Exception e)  
{  
    Console.WriteLine("Exception: " + e.GetType().Name + " - " + e.Message);  
}  
```  
  
 <span data-ttu-id="ad8ac-125">샘플을 실행하면 작업 요청 및 응답이 클라이언트 콘솔 창에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="ad8ac-125">When you run the sample, the operation requests and responses are displayed in the client console window.</span></span> <span data-ttu-id="ad8ac-126">0으로 나누기와 argument-out-of-range 조건이 오류로 보고되는 것을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ad8ac-126">You see the division by zero and the argument-out-of-range conditions being reported as faults.</span></span> <span data-ttu-id="ad8ac-127">클라이언트를 종료하려면 클라이언트 창에서 Enter 키를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="ad8ac-127">Press ENTER in the client window to shut down the client.</span></span>  
  
```console  
Add(15,3) = 18  
Subtract(145,76) = 69  
Multiply(9,81) = 729  
Forcing an error in Divide  
FaultException: FaultException - Invalid Argument: The second argument must not be zero.  
Forcing an error in Factorial  
FaultException: FaultException - Invalid Argument: The argument must be greater than zero.  
  
Press <ENTER> to terminate client.  
```  
  
 <span data-ttu-id="ad8ac-128">c:\logs\errors.txt 파일에는 서비스에서 오류에 대해 기록한 정보가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ad8ac-128">The file c:\logs\errors.txt contains the information logged about the errors by the service.</span></span> <span data-ttu-id="ad8ac-129">서비스가 디렉터리에 쓸 수 있도록 하려면 서비스가 실행 중인 프로세스(일반적으로 ASP.NET 또는 네트워크 서비스)에 디렉터리에 쓸 수 있는 권한이 있는지 확인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ad8ac-129">Note that for the service to write to the directory you must make sure that the process under which the service is running (typically ASP.NET or Network Service) has permission to write to the directory.</span></span>  
  
```txt
Fault: Reason = Invalid Argument: The second argument must not be zero.  
Fault: Reason = Invalid Argument: The argument must be greater than zero.  
```  
  
### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="ad8ac-130">샘플을 설치, 빌드 및 실행하려면</span><span class="sxs-lookup"><span data-stu-id="ad8ac-130">To set up, build, and run the sample</span></span>  
  
1. <span data-ttu-id="ad8ac-131">Windows 통신 기초 [샘플에 대한 일회성 설치 절차를](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md)수행했어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ad8ac-131">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2. <span data-ttu-id="ad8ac-132">솔루션을 빌드하려면 Windows 통신 [기초 샘플 빌드의 지침을 따르십시오.](../../../../docs/framework/wcf/samples/building-the-samples.md)</span><span class="sxs-lookup"><span data-stu-id="ad8ac-132">To build the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
3. <span data-ttu-id="ad8ac-133">error.txt 파일을 보관할 c:\logs 디렉터리를 만들었는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="ad8ac-133">Ensure you have created the c:\logs directory for the error.txt file.</span></span> <span data-ttu-id="ad8ac-134">또는 `CalculatorErrorHandler.HandleError`에 사용된 파일 이름을 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="ad8ac-134">Or modify the file name used in `CalculatorErrorHandler.HandleError`.</span></span>  
  
4. <span data-ttu-id="ad8ac-135">단일 또는 교차 컴퓨터 구성에서 샘플을 실행하려면 Windows [통신 기반 샘플 실행의 지침을 따르십시오.](../../../../docs/framework/wcf/samples/running-the-samples.md)</span><span class="sxs-lookup"><span data-stu-id="ad8ac-135">To run the sample in a single- or cross-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="ad8ac-136">컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ad8ac-136">The samples may already be installed on your machine.</span></span> <span data-ttu-id="ad8ac-137">계속하기 전에 다음(기본) 디렉터리를 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="ad8ac-137">Check for the following (default) directory before continuing.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> <span data-ttu-id="ad8ac-138">이 디렉터리가 없는 경우 [.NET Framework 4에 대한 WCF(Windows 통신 재단) 및 WF(Windows 워크플로우 재단) 샘플로](https://www.microsoft.com/download/details.aspx?id=21459) 이동하여 모든 WCF(Windows 통신 재단) 및 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플을 다운로드합니다.</span><span class="sxs-lookup"><span data-stu-id="ad8ac-138">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="ad8ac-139">이 샘플은 다음 디렉터리에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ad8ac-139">This sample is located in the following directory.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Extensibility\ErrorHandling`  
