---
title: "연습-형식 공급자 (F #)를 사용 하 여 웹 서비스에 액세스"
description: "WSDL 서비스에 액세스 하려면 F # 3.0에서 사용할 수 있는 WSDL 웹 서비스 설명 언어 () 형식 공급자를 사용 하는 방법에 알아봅니다."
keywords: "visual f#, f#, 함수형 프로그래밍"
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: 63374fa9-8fb8-43ac-bcb9-ef2290d9f851
ms.openlocfilehash: 2929198172a4e9f908daa64af19208e07859263f
ms.sourcegitcommit: 655fd4f78741967f80c409cef98347fdcf77857d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/28/2018
---
# <a name="walkthrough-accessing-a-web-service-by-using-type-providers"></a><span data-ttu-id="2760d-104">연습: 형식 공급자를 사용하여 웹 서비스에 액세스</span><span class="sxs-lookup"><span data-stu-id="2760d-104">Walkthrough: Accessing a Web Service by Using Type Providers</span></span>

> [!NOTE]
<span data-ttu-id="2760d-105">이 가이드는 F # 3.0 용으로 작성 된 하 고 업데이트 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2760d-105">This guide was written for F# 3.0 and will be updated.</span></span>  <span data-ttu-id="2760d-106">최신 크로스 플랫폼 형식 공급자에 대해서는 [FSharp.Data](https://fsharp.github.io/FSharp.Data/)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="2760d-106">See [FSharp.Data](https://fsharp.github.io/FSharp.Data/) for up-to-date, cross-platform type providers.</span></span>

> [!NOTE]
<span data-ttu-id="2760d-107">API 참조 링크 MSDN을 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="2760d-107">The API reference links will take you to MSDN.</span></span>  <span data-ttu-id="2760d-108">docs.microsoft.com API 참조가 완전하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2760d-108">The docs.microsoft.com API reference is not complete.</span></span>

<span data-ttu-id="2760d-109">이 연습에서는 F # 3.0 WSDL 서비스에 액세스할 수 있는 WSDL 웹 서비스 설명 언어 () 형식 공급자를 사용 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="2760d-109">This walkthrough shows you how to use the Web Services Description Language (WSDL) type provider that is available in F# 3.0 to access a WSDL service.</span></span> <span data-ttu-id="2760d-110">다른.NET 언어에서 호출 svcutil.exe를 통해 웹 서비스에 액세스 하는 코드를 생성의 웹 참조를 추가 하 여 예를 들어 C# 프로젝트 또는 svcutil.exe를 대신 호출 하도록 Visual Studio 가져오려면.</span><span class="sxs-lookup"><span data-stu-id="2760d-110">In other .NET languages, you generate the code to access the web service by calling svcutil.exe, or by adding a web reference in, for example, a C# project to get Visual Studio to call svcutil.exe for you.</span></span> <span data-ttu-id="2760d-111">F #에서 WsdlService 형식을 만드는 코드를 작성 하므로 빨리 있습니다 WSDL 형식 공급자를 사용 하 여 추가 옵션을 사용할 형식을 생성 되어 사용할 수 있게 합니다.</span><span class="sxs-lookup"><span data-stu-id="2760d-111">In F#, you have the additional option of using the WSDL type provider, so as soon as you write the code that creates the WsdlService type, the types are generated and become available.</span></span> <span data-ttu-id="2760d-112">이 프로세스는 서비스를 사용할 수 있는 코드를 작성 하는 경우에 의존 합니다.</span><span class="sxs-lookup"><span data-stu-id="2760d-112">This process relies on the service being available when you are writing the code.</span></span>

<span data-ttu-id="2760d-113">이 연습에서는 다음 작업을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="2760d-113">This walkthrough illustrates the following tasks.</span></span> <span data-ttu-id="2760d-114">이 연습을 완료 하려면이 순서 대로 해당를 완료 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2760d-114">You must complete them in this order for the walkthrough to succeed:</span></span>


- <span data-ttu-id="2760d-115">프로젝트 만들기</span><span class="sxs-lookup"><span data-stu-id="2760d-115">Creating the project</span></span>
<br />

- <span data-ttu-id="2760d-116">형식 공급자 구성</span><span class="sxs-lookup"><span data-stu-id="2760d-116">Configuring the type provider</span></span>
<br />

- <span data-ttu-id="2760d-117">웹 서비스를 호출 하 고 결과 처리</span><span class="sxs-lookup"><span data-stu-id="2760d-117">Calling the web service, and processing the results</span></span>
<br />


## <a name="creating-the-project"></a><span data-ttu-id="2760d-118">프로젝트 만들기</span><span class="sxs-lookup"><span data-stu-id="2760d-118">Creating the project</span></span>
<span data-ttu-id="2760d-119">단계에서 프로젝트를 만들고 WSDL 형식 공급자를 사용 하려면 적절 한 참조를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="2760d-119">In the step, you create a project and add the appropriate references to use a WSDL type provider.</span></span>


#### <a name="to-create-and-set-up-an-f-project"></a><span data-ttu-id="2760d-120">F# 프로젝트를 만들고 설정하려면</span><span class="sxs-lookup"><span data-stu-id="2760d-120">To create and set up an F# project</span></span>

1. <span data-ttu-id="2760d-121">새 F # 콘솔 응용 프로그램 프로젝트를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="2760d-121">Open a new F# Console Application project.</span></span>
<br />

2. <span data-ttu-id="2760d-122">**솔루션 탐색기**, 프로젝트의에 대 한 바로 가기 메뉴를 열고 **참조** 노드를 선택한 후 **참조 추가**합니다.</span><span class="sxs-lookup"><span data-stu-id="2760d-122">In **Solution Explorer**, open the shortcut menu for the project's **Reference** node, and then choose **Add Reference**.</span></span>
<br />

3. <span data-ttu-id="2760d-123">에 **어셈블리** 영역에서 선택 **프레임 워크**, 한 다음 사용할 수 있는 어셈블리의 목록에서 선택 **System.Runtime.Serialization** 및  **System.ServiceModel**합니다.</span><span class="sxs-lookup"><span data-stu-id="2760d-123">In the **Assemblies** area, choose **Framework**, and then, in the list of available assemblies, choose **System.Runtime.Serialization** and **System.ServiceModel**.</span></span>
<br />

4. <span data-ttu-id="2760d-124">에 **어셈블리** 영역에서 선택 **확장**합니다.</span><span class="sxs-lookup"><span data-stu-id="2760d-124">In the **Assemblies** area, choose **Extensions**.</span></span>
<br />

5. <span data-ttu-id="2760d-125">사용할 수 있는 어셈블리의 목록에서 선택 **FSharp.Data.TypeProviders**를 선택한 후는 **확인** 이러한 어셈블리에 대 한 참조를 추가 하는 단추입니다.</span><span class="sxs-lookup"><span data-stu-id="2760d-125">In the list of available assemblies, choose **FSharp.Data.TypeProviders**, and then choose the **OK** button to add references to these assemblies.</span></span>
<br />

## <a name="configuring-the-type-provider"></a><span data-ttu-id="2760d-126">형식 공급자 구성</span><span class="sxs-lookup"><span data-stu-id="2760d-126">Configuring the type provider</span></span>
<span data-ttu-id="2760d-127">이 단계에서는 WSDL 형식 공급자를 사용 하 여 TerraServer 웹 서비스에 대 한 형식을 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="2760d-127">In this step, you use the WSDL type provider to generate types for the TerraServer web service.</span></span>


#### <a name="to-configure-the-type-provider-and-generate-types"></a><span data-ttu-id="2760d-128">형식 공급자를 구성하고 형식을 생성하려면</span><span class="sxs-lookup"><span data-stu-id="2760d-128">To configure the type provider and generate types</span></span>

1. <span data-ttu-id="2760d-129">형식 공급자 네임 스페이스를 여는 코드를 다음 줄을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="2760d-129">Add the following line of code to open the type provider namespace.</span></span>
<br />

```fsharp
open System
open System.ServiceModel
open Microsoft.FSharp.Linq
open Microsoft.FSharp.Data.TypeProviders
```

2. <span data-ttu-id="2760d-130">웹 서비스와 형식 공급자를 호출 하는 코드의 다음 줄을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="2760d-130">Add the following line of code to invoke the type provider with a web service.</span></span> <span data-ttu-id="2760d-131">이 예제에서는 TerraServer 웹 서비스를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="2760d-131">In this example, use the TerraServer web service.</span></span>
<br />

```fsharp
type TerraService = WsdlService<" HYPERLINK "https://terraserver-usa.com/TerraService2.asmx?WSDL" https://msrmaps.com/TerraService2.asmx?WSDL">
```

  <span data-ttu-id="2760d-132">빨간색 물결 서비스 URI의 철자가 잘못 된 경우 또는 서비스 자체 작동이 중지 되었거나 작동 하지 않을 경우이 코드 줄 아래에 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="2760d-132">A red squiggle appears under this line of code if the service URI is misspelled or if the service itself is down or isn’t performing.</span></span> <span data-ttu-id="2760d-133">코드를 가리키는 경우 오류 메시지가 문제를 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="2760d-133">If you point to the code, an error message describes the problem.</span></span> <span data-ttu-id="2760d-134">동일한 정보를 찾을 수 있습니다는 **오류 목록** 창 또는 **출력 창** 구성한 후에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2760d-134">You can find the same information in the **Error List** window or in the **Output Window** after you build.</span></span>
<br />  <span data-ttu-id="2760d-135">프로젝트에 대 한 app.config 파일을 사용 하 여 또는 공급자 형식 선언에 정적 형식 매개 변수를 사용 하 여 WSDL 연결에 대 한 구성 설정을 지정 하는 방법은 두 가지가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2760d-135">There are two ways to specify configuration settings for a WSDL connection, by using the app.config file for the project, or by using the static type parameters in the type provider declaration.</span></span> <span data-ttu-id="2760d-136">Svcutil.exe를 사용 하 여 적절 한 구성 파일 요소를 생성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2760d-136">You can use svcutil.exe to generate appropriate configuration file elements.</span></span> <span data-ttu-id="2760d-137">Svcutil.exe를 사용 하 여 웹 서비스에 대 한 구성 정보를 생성 하는 방법에 대 한 자세한 내용은 참조 [ServiceModel Metadata 유틸리티 도구 &#40; Svcutil.exe &#41; ](https://msdn.microsoft.com/library/aa347733.aspx).</span><span class="sxs-lookup"><span data-stu-id="2760d-137">For more information about using svcutil.exe to generate configuration information for a web service, see [ServiceModel Metadata Utility Tool &#40;Svcutil.exe&#41;](https://msdn.microsoft.com/library/aa347733.aspx).</span></span> <span data-ttu-id="2760d-138">에 대 한 전체 설명은 WSDL 형식 공급자에 대 한 정적 형식 매개 변수를 참조 하세요. [WsdlService 형식 공급자](https://msdn.microsoft.com/visualfsharpdocs/conceptual/wsdlservice-type-provider-%5bfsharp%5d)합니다.</span><span class="sxs-lookup"><span data-stu-id="2760d-138">For a full description of the static type parameters for the WSDL type provider, see [WsdlService Type Provider](https://msdn.microsoft.com/visualfsharpdocs/conceptual/wsdlservice-type-provider-%5bfsharp%5d).</span></span>
<br />

## <a name="calling-the-web-service-and-processing-the-results"></a><span data-ttu-id="2760d-139">웹 서비스를 호출 하 고 결과 처리</span><span class="sxs-lookup"><span data-stu-id="2760d-139">Calling the web service, and processing the results</span></span>
<span data-ttu-id="2760d-140">각 웹 서비스에 고유한 집합이 해당 메서드 호출에 대 한 매개 변수로 사용 되는 형식.</span><span class="sxs-lookup"><span data-stu-id="2760d-140">Each web service has its own set of types that are used as parameters for its method calls.</span></span> <span data-ttu-id="2760d-141">이러한 매개 변수를 준비 합니다.이 단계에서는 웹 메서드를 호출 하 고 반환 되는 정보를 처리 합니다.</span><span class="sxs-lookup"><span data-stu-id="2760d-141">In this step, you prepare these parameters, call a web method, and process the information that it returns.</span></span>


#### <a name="to-call-the-web-service-and-process-the-results"></a><span data-ttu-id="2760d-142">웹 서비스를 호출 하 고 결과 처리 하려면</span><span class="sxs-lookup"><span data-stu-id="2760d-142">To call the web service, and process the results</span></span>

1. <span data-ttu-id="2760d-143">웹 서비스의 시간이 초과 될 수 있습니다 또는 작동 하지 않으므로 예외를 처리 하는 블록에 웹 서비스 호출을 포함 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2760d-143">The web service might time out or stop functioning, so you should include the web service call in an exception handling block.</span></span> <span data-ttu-id="2760d-144">웹 서비스에서 데이터를 가져올 다음 코드를 작성 합니다.</span><span class="sxs-lookup"><span data-stu-id="2760d-144">Write the following code to try to get data from the web service.</span></span>
<br />

```fsharp
try
  let terraClient = TerraService.GetTerraServiceSoap ()
  let myPlace = new TerraService.ServiceTypes.msrmaps.com.Place(City = "Redmond", State = "Washington", Country = "United States")
  let myLocation = terraClient.ConvertPlaceToLonLatPt(myPlace)
  printfn "Redmond Latitude: %f Longitude: %f" (myLocation.Lat) (myLocation.Lon)
with
| :? ServerTooBusyException as exn ->
  let innerMessage =
    match (exn.InnerException) with
    | null -> ""
    | innerExn -> innerExn.Message
  printfn "An exception occurred:\n %s\n %s" exn.Message innerMessage
| exn -> printfn "An exception occurred: %s" exn.Message
```

<span data-ttu-id="2760d-145">와 같은 웹 서비스에 필요한 데이터 종류를 만들 **위치** 및 **위치**는 WsdlService 아래 중첩된 형식 유형으로, **TerraService**합니다.</span><span class="sxs-lookup"><span data-stu-id="2760d-145">Notice that you create the data types that are needed for the web service, such as **Place** and **Location**, as nested types under the WsdlService type **TerraService**.</span></span>
<br />


## <a name="see-also"></a><span data-ttu-id="2760d-146">참고 항목</span><span class="sxs-lookup"><span data-stu-id="2760d-146">See Also</span></span>
[<span data-ttu-id="2760d-147">WsdlService 형식 공급자</span><span class="sxs-lookup"><span data-stu-id="2760d-147">WsdlService Type Provider</span></span>](https://msdn.microsoft.com/visualfsharpdocs/conceptual/wsdlservice-type-provider-%5bfsharp%5d)

[<span data-ttu-id="2760d-148">형식 공급자</span><span class="sxs-lookup"><span data-stu-id="2760d-148">Type Providers</span></span>](index.md)
