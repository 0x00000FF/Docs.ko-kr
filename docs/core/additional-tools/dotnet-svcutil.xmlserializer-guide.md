---
title: .NET Core에서 dotnet-svcutil.xmlserializer 사용
description: '`dotnet-svcutil.xmlserializer` NuGet 패키지를 사용하여 .NET Core 프로젝트용 serialization 어셈블리를 미리 생성하는 방법을 알아봅니다.'
author: huanwu
ms.date: 11/27/2018
ms.openlocfilehash: a98f8d30f2e37b722a3bf1f93be8fe9df540a468
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/10/2019
ms.locfileid: "70848972"
---
# <a name="using-dotnet-svcutilxmlserializer-on-net-core"></a><span data-ttu-id="2202a-103">.NET Core에서 dotnet-svcutil.xmlserializer 사용</span><span class="sxs-lookup"><span data-stu-id="2202a-103">Using dotnet-svcutil.xmlserializer on .NET Core</span></span>

<span data-ttu-id="2202a-104">`dotnet-svcutil.xmlserializer` NuGet 패키지는 .NET Core 프로젝트용 serialization 어셈블리를 미리 생성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2202a-104">The `dotnet-svcutil.xmlserializer` NuGet package can pre-generate a serialization assembly for .NET Core projects.</span></span> <span data-ttu-id="2202a-105">WCF 서비스 계약에서 사용되고 XmlSerializer를 통해 직렬화할 수 있는 클라이언트 애플리케이션의 형식에 대해 C# serialization 코드를 미리 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="2202a-105">It pre-generates C# serialization code for the types in the client application that are used by the WCF Service Contract and that can be serialized by the XmlSerializer.</span></span> <span data-ttu-id="2202a-106">이렇게 하면 해당 형식의 개체를 직렬화 또는 deserialize할 때 XML serialization의 시작 성능이 향상됩니다.</span><span class="sxs-lookup"><span data-stu-id="2202a-106">This improves the startup performance of XML serialization when serializing or deserializing objects of those types.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="2202a-107">전제 조건</span><span class="sxs-lookup"><span data-stu-id="2202a-107">Prerequisites</span></span>

* <span data-ttu-id="2202a-108">[.NET Core 2.1 SDK](https://dotnet.microsoft.com/download) 이상</span><span class="sxs-lookup"><span data-stu-id="2202a-108">[.NET Core 2.1 SDK](https://dotnet.microsoft.com/download) or later</span></span>
* <span data-ttu-id="2202a-109">선호하는 코드 편집기</span><span class="sxs-lookup"><span data-stu-id="2202a-109">Your favorite code editor</span></span>

<span data-ttu-id="2202a-110">`dotnet --info` 명령을 사용하여 이미 설치한 .NET Core SDK 및 런타임 버전을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2202a-110">You can use the command `dotnet --info` to check which versions of .NET Core SDK and runtime you already have installed.</span></span>

## <a name="getting-started"></a><span data-ttu-id="2202a-111">시작</span><span class="sxs-lookup"><span data-stu-id="2202a-111">Getting started</span></span>

<span data-ttu-id="2202a-112">.NET Core 콘솔 애플리케이션에서 `dotnet-svcutil.xmlserializer`를 사용하려면</span><span class="sxs-lookup"><span data-stu-id="2202a-112">To use `dotnet-svcutil.xmlserializer` in a .NET Core console application:</span></span>

1. <span data-ttu-id="2202a-113">.NET Framework에서 기본 템플릿 ‘WCF 서비스 애플리케이션’을 사용하여 ‘MyWCFService’라는 WCF 서비스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="2202a-113">Create a WCF Service named 'MyWCFService' using the default template 'WCF Service Application' in .NET Framework.</span></span> <span data-ttu-id="2202a-114">다음과 같이 서비스 메서드에 `[XmlSerializerFormat]` 특성을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="2202a-114">Add `[XmlSerializerFormat]` attribute on the service method like the following:</span></span>

   ```csharp
    [ServiceContract]
    public interface IService1
    {
        [XmlSerializerFormat]
        [OperationContract(Action = "http://tempuri.org/IService1/GetData", ReplyAction = "http://tempuri.org/IService1/GetDataResponse")]
        string GetData(int value);
    }
    ```

2. <span data-ttu-id="2202a-115">.NET Core 2.1 이상 버전을 대상으로 하는 WCF 클라이언트 애플리케이션으로 .NET Core 콘솔 애플리케이션을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="2202a-115">Create a .NET Core console application as WCF client application that targets at .NET Core 2.1 or later versions.</span></span> <span data-ttu-id="2202a-116">예를 들어, 다음 명령으로 'MyWCFClient'라는 앱을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="2202a-116">For example, create an app named 'MyWCFClient' with the following command:</span></span>

    ```console
    dotnet new console --name MyWCFClient
    ```

    <span data-ttu-id="2202a-117">프로젝트가 .NET Core 2.1 이상을 대상으로 하고 있는지 확인하려면 프로젝트 파일에서 `TargetFramework` XML 요소를 검사합니다.</span><span class="sxs-lookup"><span data-stu-id="2202a-117">To ensure your project is targeting .NET Core 2.1 or later, inspect the `TargetFramework` XML element in your project file:</span></span>

    ```xml
    <TargetFramework>netcoreapp2.1</TargetFramework>
    ```

3. <span data-ttu-id="2202a-118">다음 명령을 실행하여 `System.ServiceModel.Http`에 패키지 참조를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="2202a-118">Add a package reference to `System.ServiceModel.Http` by running the following command:</span></span>

    ```console
    dotnet add package System.ServiceModel.Http
    ```

4. <span data-ttu-id="2202a-119">WCF 클라이언트 코드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="2202a-119">Add the WCF Client code:</span></span>

    ```csharp
    using System.ServiceModel;

        class Program
        {
            static void Main(string[] args)
            {
                var myBinding = new BasicHttpBinding();
                var myEndpoint = new EndpointAddress("http://localhost:2561/Service1.svc"); //Fill your service url here
                var myChannelFactory = new ChannelFactory<IService1>(myBinding, myEndpoint);
                IService1 client = myChannelFactory.CreateChannel();
                string s = client.GetData(1);
                ((ICommunicationObject)client).Close();
            }
        }

    [ServiceContract]
    public interface IService1
    {
        [XmlSerializerFormat]
        [OperationContract(Action = "http://tempuri.org/IService1/GetData", ReplyAction = "http://tempuri.org/IService1/GetDataResponse")]
        string GetData(int value);
    }
    ```

5. <span data-ttu-id="2202a-120">다음 명령을 실행하여 `dotnet-svcutil.xmlserializer` 패키지에 참조를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="2202a-120">Add a reference to the `dotnet-svcutil.xmlserializer` package by running the following command:</span></span>
  
    ```console
    dotnet add package dotnet-svcutil.xmlserializer
    ```

    <span data-ttu-id="2202a-121">명령을 실행하면 다음과 비슷한 항목이 프로젝트 파일에 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="2202a-121">Running the command should add an entry to your project file similar to this:</span></span>
  
    ```xml
    <ItemGroup>
      <DotNetCliToolReference Include="dotnet-svcutil.xmlserializer" Version="1.0.0" />
    </ItemGroup>
    ```

6. <span data-ttu-id="2202a-122">`dotnet build`를 실행하여 애플리케이션을 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="2202a-122">Build the application by running `dotnet build`.</span></span> <span data-ttu-id="2202a-123">모든 항목이 성공하면 *MyWCFClient.XmlSerializers.dll*이라는 어셈블리가 출력 폴더에 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="2202a-123">If everything succeeds, an assembly named *MyWCFClient.XmlSerializers.dll* is generated in the output folder.</span></span> <span data-ttu-id="2202a-124">도구가 어셈블리 생성에 실패할 경우 빌드 출력에 경고가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="2202a-124">If the tool failed to generate the assembly, you'll see warnings in the build output.</span></span>

7. <span data-ttu-id="2202a-125">예를 들어 브라우저에서 `http://localhost:2561/Service1.svc`를 실행하여 WCF 서비스를 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="2202a-125">Start the WCF service by, for example, running `http://localhost:2561/Service1.svc` in the browser.</span></span> <span data-ttu-id="2202a-126">그런 다음, 클라이언트 애플리케이션을 시작하면 미리 생성된 직렬 변환기가 런타임 시 자동으로 로드되어 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="2202a-126">Then start the client application, and it will automatically load and use the pre-generated serializers at runtime.</span></span>
