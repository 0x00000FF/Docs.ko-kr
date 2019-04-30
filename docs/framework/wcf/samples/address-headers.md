---
title: 주소 헤더
ms.date: 03/30/2017
ms.assetid: b0c94d4a-3bde-4b4d-bb6d-9f12bc3a6940
ms.openlocfilehash: 4ccb309178251b32068d6cdbb81874322f991bb9
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62002952"
---
# <a name="address-headers"></a><span data-ttu-id="9747f-102">주소 헤더</span><span class="sxs-lookup"><span data-stu-id="9747f-102">Address Headers</span></span>

<span data-ttu-id="9747f-103">Address Headers 샘플은 클라이언트 Windows Communication Foundation (WCF)를 사용 하 여 서비스에 대 한 참조 매개 변수를 전달 하는 방법 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="9747f-103">The Address Headers sample demonstrates how clients can pass reference parameters to a service using Windows Communication Foundation (WCF).</span></span>

> [!NOTE]
> <span data-ttu-id="9747f-104">이 샘플의 설치 절차 및 빌드 지침은 이 항목의 끝부분에 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9747f-104">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>

<span data-ttu-id="9747f-105">WS-Addressing 사양은 특성 웹 서비스 엔드포인트의 주소를 지정하는 방법으로 엔드포인트 참조의 개념을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="9747f-105">The WS-Addressing specification defines the notion of an endpoint reference as a way to address a particular Web service endpoint.</span></span> <span data-ttu-id="9747f-106">Wcf에서 끝점 참조를 사용 하 여 모델링 됩니다 합니다 `EndpointAddress` 클래스- `EndpointAddress` 의 주소 필드의 형식인는 `ServiceEndpoint` 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="9747f-106">In WCF, endpoint references are modeled using the `EndpointAddress` class - `EndpointAddress` is the type of the Address field of the `ServiceEndpoint` class.</span></span>

<span data-ttu-id="9747f-107">엔드포인트 참조 모델의 일부에서 각 참조는 추가 식별 정보를 추가하는 일부 참조 매개 변수를 전달할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9747f-107">Part of the endpoint reference model is that each reference can carry some reference parameters that add extra identifying information.</span></span> <span data-ttu-id="9747f-108">Wcf에서 이러한 참조 매개 변수는의 인스턴스로 모델링 됩니다 `AddressHeader` 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="9747f-108">In WCF, these reference parameters are modeled as instances of `AddressHeader` class.</span></span>

<span data-ttu-id="9747f-109">이 샘플에서 클라이언트는 클라이언트 엔드포인트의 `EndpointAddress`에 참조 매개 변수를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="9747f-109">In this sample, the client adds a reference parameter to the `EndpointAddress` of the client endpoint.</span></span> <span data-ttu-id="9747f-110">서비스는 이 참조 매개 변수를 찾아서 "Hello" 서비스 작업의 논리에 해당 값을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="9747f-110">The service looks for this reference parameter and uses its value in the logic of its "Hello" service operation.</span></span>

## <a name="client"></a><span data-ttu-id="9747f-111">클라이언트</span><span class="sxs-lookup"><span data-stu-id="9747f-111">Client</span></span>

<span data-ttu-id="9747f-112">클라이언트는 참조 매개 변수를 보내려면 `AddressHeader`의 `EndpointAddress`에 `ServiceEndpoint`를 추가해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9747f-112">For the client to send a reference parameter, it must add an `AddressHeader` to the `EndpointAddress` of the `ServiceEndpoint`.</span></span> <span data-ttu-id="9747f-113">`EndpointAddress` 클래스를 변경할 수 없으므로 엔드포인트 주소 수정은 `EndpointAddressBuilder` 클래스를 사용하여 수행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9747f-113">Because the `EndpointAddress` class is immutable, modification of an endpoint address must be done using the `EndpointAddressBuilder` class.</span></span> <span data-ttu-id="9747f-114">다음 코드에서는 해당 메시지의 일부로 참조 매개 변수를 보내도록 클라이언트를 초기화합니다.</span><span class="sxs-lookup"><span data-stu-id="9747f-114">The following code initializes the client to send a reference parameter as part of its message.</span></span>

```csharp
HelloClient client = new HelloClient();
EndpointAddressBuilder builder =
    new EndpointAddressBuilder(client.Endpoint.Address);
AddressHeader header =
    AddressHeader.CreateAddressHeader(IDName, IDNamespace, "John");
builder.Headers.Add(header);
client.Endpoint.Address = builder.ToEndpointAddress();
```

<span data-ttu-id="9747f-115">이 코드는 원래 `EndpointAddressBuilder`를 초기 값으로 사용하여 `EndpointAddress`를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="9747f-115">The code creates an `EndpointAddressBuilder` using the original `EndpointAddress` as an initial value.</span></span> <span data-ttu-id="9747f-116">그런 다음 새로 만든된 주소 헤더를 추가 에 대 한 호출 `CreateAddressHeader` 특정 이름, 네임 스페이스 및 값을 사용 하 여 헤더를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="9747f-116">It then adds a newly created address header; the call to `CreateAddressHeader` creates a header with a particular name, namespace, and value.</span></span> <span data-ttu-id="9747f-117">여기서 값은 "John"입니다.</span><span class="sxs-lookup"><span data-stu-id="9747f-117">Here the value is "John".</span></span> <span data-ttu-id="9747f-118">헤더가 작성기에 추가되고 나면 `ToEndpointAddress()` 메서드는 변경할 수 있는 작성기를 변경할 수 없는 엔드포인트 주소로 다시 변환하고 이 주소는 클라이언트 엔드포인트의 주소 필드에 할당됩니다.</span><span class="sxs-lookup"><span data-stu-id="9747f-118">Once the header is added to the builder, the `ToEndpointAddress()` method converts the (mutable) builder back into an (immutable) endpoint address, which is assigned back to the client endpoint's Address field.</span></span>

<span data-ttu-id="9747f-119">이제 클라이언트가 `Console.WriteLine(client.Hello());`를 호출하면 클라이언트의 결과 출력에 나온 것처럼 서비스는 이 주소 매개 변수의 값을 가져올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9747f-119">Now when the client calls `Console.WriteLine(client.Hello());`, the service is able to get the value of this address parameter, as seen in the resulting output of the client.</span></span>

`Hello, John`

## <a name="server"></a><span data-ttu-id="9747f-120">서버</span><span class="sxs-lookup"><span data-stu-id="9747f-120">Server</span></span>

<span data-ttu-id="9747f-121">서비스 작업 `Hello()`의 구현에서는 현재 `OperationContext`를 사용하여 들어오는 메시지에서 헤더 값을 검사합니다.</span><span class="sxs-lookup"><span data-stu-id="9747f-121">The implementation of the service operation `Hello()` uses the current `OperationContext` to inspect the values of the headers on the incoming message.</span></span>

```csharp
string id = null;
// look at headers on incoming message
for (int i = 0;
     i < OperationContext.Current.IncomingMessageHeaders.Count;
     ++i)
{
    MessageHeaderInfo h = OperationContext.Current.IncomingMessageHeaders[i];
    // for any reference parameters with the correct name & namespace
    if (h.IsReferenceParameter &&
        h.Name == IDName &&
        h.Namespace == IDNamespace)
    {
        // read the value of that header
        XmlReader xr = OperationContext.Current.IncomingMessageHeaders.GetReaderAtHeader(i);
        id = xr.ReadElementContentAsString();
    }
}
return "Hello, " + id;
```

<span data-ttu-id="9747f-122">이 코드는 들어오는 메시지의 모든 헤더를 반복하여 특정 이름을 가진 참조 매개 변수인 헤더를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="9747f-122">The code iterates over all the headers on the incoming message, looking for headers that are reference parameters with the particular name and.</span></span> <span data-ttu-id="9747f-123">매개 변수가 발견되면 매개 변수의 값을 읽고 "id" 변수에 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="9747f-123">When the parameter is found, it reads the value of the parameter and stores it in the "id" variable.</span></span>

#### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="9747f-124">샘플을 설치, 빌드 및 실행하려면</span><span class="sxs-lookup"><span data-stu-id="9747f-124">To set up, build, and run the sample</span></span>

1. <span data-ttu-id="9747f-125">수행 했는지 확인 합니다 [Windows Communication Foundation 샘플에 대 한 일회성 설치 절차](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="9747f-125">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>

2. <span data-ttu-id="9747f-126">C# 또는 Visual Basic .NET 버전의 솔루션을 빌드하려면 [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md)의 지침을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="9747f-126">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>

3. <span data-ttu-id="9747f-127">단일 또는 다중 컴퓨터 구성에서 샘플을 실행 하려면의 지침을 따릅니다 [Windows Communication Foundation 샘플 실행](../../../../docs/framework/wcf/samples/running-the-samples.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="9747f-127">To run the sample in a single- or cross-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="9747f-128">컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9747f-128">The samples may already be installed on your machine.</span></span> <span data-ttu-id="9747f-129">계속하기 전에 다음(기본) 디렉터리를 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="9747f-129">Check for the following (default) directory before continuing.</span></span>
>
> `<InstallDrive>:\WF_WCF_Samples`
>
> <span data-ttu-id="9747f-130">이 디렉터리가 없으면로 이동 [Windows Communication Foundation (WCF) 및.NET Framework 4 용 Windows WF (Workflow Foundation) 샘플](https://go.microsoft.com/fwlink/?LinkId=150780) 모든 Windows Communication Foundation (WCF)를 다운로드 하 고 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플.</span><span class="sxs-lookup"><span data-stu-id="9747f-130">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="9747f-131">이 샘플은 다음 디렉터리에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9747f-131">This sample is located in the following directory.</span></span>
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Client\AddressHeaders`
