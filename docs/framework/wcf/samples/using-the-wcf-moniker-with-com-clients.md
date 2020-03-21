---
title: Using the WCF Moniker with COM Clients
ms.date: 03/30/2017
ms.assetid: e2799bfe-88bd-49d7-9d6d-ac16a9b16b04
ms.openlocfilehash: d4d812c59a504f365eb3ad63ddd45ba5a66296e9
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79183230"
---
# <a name="using-the-wcf-moniker-with-com-clients"></a><span data-ttu-id="d1386-102">Using the WCF Moniker with COM Clients</span><span class="sxs-lookup"><span data-stu-id="d1386-102">Using the WCF Moniker with COM Clients</span></span>
<span data-ttu-id="d1386-103">이 샘플에서는 WCF(Windows 통신 재단) 서비스 모니커를 사용하여 웹 서비스를 Com 기반 개발 환경에 통합하는 방법을 보여 줍니다(예: Microsoft Office 응용 프로그램용 시각적 기본( Office VBA) 또는 Visual Basic 6.0.</span><span class="sxs-lookup"><span data-stu-id="d1386-103">This sample demonstrates how to use the Windows Communication Foundation (WCF) service moniker to integrate Web services into COM-based development environments, such as Microsoft Office Visual Basic for Applications (Office VBA) or Visual Basic 6.0.</span></span> <span data-ttu-id="d1386-104">이 샘플은 IIS(인터넷 정보 서비스)에서 호스트되는 Windows 스크립트 호스트 클라이언트(.vbs), 지원 클라이언트 라이브러리(.dll) 및 서비스 라이브러리(.dll)로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="d1386-104">This sample consists of a Windows Script Host client (.vbs), a supporting client library (.dll), and a service library (.dll) hosted by Internet Information Services (IIS).</span></span> <span data-ttu-id="d1386-105">서비스는 계산기 서비스이고 COM 클라이언트는 서비스에서 수학 작업인 Add, Subtract, Multiply 및 Divide를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="d1386-105">The service is a calculator service and the COM client calls math operations—Add, Subtract, Multiply, and Divide—on the service.</span></span> <span data-ttu-id="d1386-106">클라이언트 동작이 메시지 상자 창에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="d1386-106">Client activity is visible in the message box windows.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="d1386-107">이 샘플의 설치 절차 및 빌드 지침은 이 항목의 끝부분에 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d1386-107">The set-up procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="d1386-108">컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d1386-108">The samples may already be installed on your computer.</span></span> <span data-ttu-id="d1386-109">계속하기 전에 다음(기본) 디렉터리를 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="d1386-109">Check for the following (default) directory before continuing.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> <span data-ttu-id="d1386-110">이 디렉터리가 없는 경우 [.NET Framework 4에 대한 WCF(Windows 통신 재단) 및 WF(Windows 워크플로우 재단) 샘플로](https://www.microsoft.com/download/details.aspx?id=21459) 이동하여 모든 WCF(Windows 통신 재단) 및 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플을 다운로드합니다.</span><span class="sxs-lookup"><span data-stu-id="d1386-110">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="d1386-111">이 샘플은 다음 디렉터리에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d1386-111">This sample is located in the following directory.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Services\Interop\COM`  
  
 <span data-ttu-id="d1386-112">서비스는 다음 코드 예제와 같이 정의된 `ICalculator` 계약을 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="d1386-112">The service implements an `ICalculator` contract defined as shown in the following code example.</span></span>  
  
```csharp
[ServiceContract(Namespace="http://Microsoft.ServiceModel.Samples")]  
public interface ICalculator  
{  
    [OperationContract]  
    double Add(double n1, double n2);  
    [OperationContract]  
    double Subtract(double n1, double n2);  
    [OperationContract]  
    double Multiply(double n1, double n2);  
    [OperationContract]  
    double Divide(double n1, double n2);  
}  
```  
  
 <span data-ttu-id="d1386-113">이 샘플에서는 모니커 사용을 위한 세 가지 대체 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="d1386-113">The sample demonstrates the three alternative approaches for using the moniker:</span></span>  
  
- <span data-ttu-id="d1386-114">형식화된 계약 – 계약이 클라이언트 컴퓨터에 COM 노출 형식으로 등록됩니다.</span><span class="sxs-lookup"><span data-stu-id="d1386-114">Typed contract – The contract is registered as a COM visible type on the client computer.</span></span>  
  
- <span data-ttu-id="d1386-115">WSDL 계약 – 계약이 WSDL 문서 형식으로 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="d1386-115">WSDL contract – The contract is supplied in the form of a WSDL document.</span></span>  
  
- <span data-ttu-id="d1386-116">메타데이터 교환 계약 - 계약이 MEX(메타데이터 교환) 엔드포인트에서 런타임에 검색됩니다.</span><span class="sxs-lookup"><span data-stu-id="d1386-116">Metadata Exchange contract – The contract is retrieved at runtime from a Metadata Exchange (MEX) endpoint.</span></span>  
  
## <a name="typed-contract"></a><span data-ttu-id="d1386-117">형식화된 계약</span><span class="sxs-lookup"><span data-stu-id="d1386-117">Typed Contract</span></span>  
 <span data-ttu-id="d1386-118">형식화된 계약 사용과 함께 모니커를 사용하려면 서비스 계약에 대한 적절한 특성 사용 형식을 COM에 등록해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d1386-118">To use the moniker with a typed contract use, appropriately attributed types for the service contract must be registered with COM.</span></span> <span data-ttu-id="d1386-119">먼저 [ServiceModel 메타데이터 유틸리티 도구(Svcutil.exe)를](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md)사용하여 클라이언트를 생성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d1386-119">First, a client must be generated by using the [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md).</span></span> <span data-ttu-id="d1386-120">클라이언트 디렉터리의 명령 프롬프트에서 다음 명령을 실행하여 형식화된 프록시를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="d1386-120">Run the following command from a command prompt in the client directory to generate the typed proxy.</span></span>  
  
```console  
svcutil.exe /n:http://Microsoft.ServiceModel.Samples,Microsoft.ServiceModel.Samples http://localhost/servicemodelsamples/service.svc /out:generatedClient.cs  
```  
  
 <span data-ttu-id="d1386-121">이 클래스는 프로젝트에 포함되어야 하고 프로젝트는 컴파일 시에 서명된 COM 노출 어셈블리를 생성하도록 구성되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d1386-121">This class must be included in a project and the project should be configured to generate a COM-visible, signed assembly when compiled.</span></span> <span data-ttu-id="d1386-122">다음 특성이 AssemblyInfo.cs 파일에 포함되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d1386-122">The following attribute should be included in the AssemblyInfo.cs file.</span></span>  
  
```csharp
[assembly: ComVisible(true)]  
```  
  
 <span data-ttu-id="d1386-123">프로젝트를 빌드한 후 다음 예제와 같이 `regasm`을 사용하여 COM 노출 형식을 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="d1386-123">After building the project, register the COM-visible types by using `regasm` as shown in the following example.</span></span>  
  
```console  
regasm.exe /tlb:CalcProxy.tlb client.dll  
```  
  
 <span data-ttu-id="d1386-124">만들어진 어셈블리는 전역 어셈블리 캐시에 추가되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d1386-124">The assembly that is created should be added to the Global Assembly Cache.</span></span> <span data-ttu-id="d1386-125">반드시 필요한 것은 아니지만 이렇게 하면 어셈블리를 찾는 런타임 프로세스가 단순화됩니다.</span><span class="sxs-lookup"><span data-stu-id="d1386-125">Though not strictly required, this simplifies the process of the runtime locating the assembly.</span></span> <span data-ttu-id="d1386-126">다음 명령은 전역 어셈블리 캐시에 어셈블리를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="d1386-126">The following command adds the assembly to the Global Assembly Cache.</span></span>  
  
```console  
gacutil.exe /i client.dll  
```  
  
> [!NOTE]
> <span data-ttu-id="d1386-127">서비스 모니커에는 형식 등록만 필요하고 서비스와 통신하기 위해 프록시가 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d1386-127">The service moniker requires only the type registration and does not use the proxy to communicate with the service.</span></span>  
  
 <span data-ttu-id="d1386-128">ComCalcClient.vbs 클라이언트 애플리케이션은 `GetObject` 함수를 사용하여 서비스용 프록시를 생성하며 서비스에 대한 주소, 바인딩 및 계약을 지정하기 위해 서비스 모니커 구문이 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="d1386-128">ComCalcClient.vbs client application uses the `GetObject` function to construct a proxy for the service, using the service moniker syntax to specify the address, binding, and contract for the service.</span></span>  
  
```vbscript
Set typedServiceMoniker = GetObject(  
"service4:address=http://localhost/ServiceModelSamples/service.svc, binding=wsHttpBinding,
contractType={9213C6D2-5A6F-3D26-839B-3BA9B82228D3}")  
```  
  
 <span data-ttu-id="d1386-129">모니커에 사용되는 매개 변수는 다음을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="d1386-129">The parameters used by the moniker specify:</span></span>  
  
- <span data-ttu-id="d1386-130">서비스 엔드포인트의 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="d1386-130">The address of the service endpoint.</span></span>  
  
- <span data-ttu-id="d1386-131">해당 엔드포인트와 연결하기 위해 클라이언트가 사용해야 하는 바인딩.</span><span class="sxs-lookup"><span data-stu-id="d1386-131">The binding that the client should use to connect with that endpoint.</span></span> <span data-ttu-id="d1386-132">이 경우 클라이언트 구성 파일에 사용자 지정 바인딩이 정의될 수도 있지만 시스템 정의 wsHttpBinding이 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="d1386-132">In this case, the system-defined wsHttpBinding is used though custom bindings can be defined in client configuration files.</span></span> <span data-ttu-id="d1386-133">Windows 스크립트 호스트와 함께 사용하는 경우 사용자 지정 바인딩은 Cscript.exe와 동일한 디렉터리의 Cscript.exe.config 파일에 정의됩니다.</span><span class="sxs-lookup"><span data-stu-id="d1386-133">For use with the Windows Script Host, the custom binding is defined in a Cscript.exe.config file in the same directory as Cscript.exe.</span></span>  
  
- <span data-ttu-id="d1386-134">엔드포인트에서 지원되는 계약의 형식.</span><span class="sxs-lookup"><span data-stu-id="d1386-134">The type of the contract that is supported at the endpoint.</span></span> <span data-ttu-id="d1386-135">이는 위에서 생성 및 등록된 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="d1386-135">This is the type that was generated and registered above.</span></span> <span data-ttu-id="d1386-136">Visual Basic 스크립트에서 강력한 형식의 COM 환경이 제공되지 않으므로 계약에 대한 식별자를 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d1386-136">Because Visual Basic script does not provide a strongly-typed COM environment, an identifier for the contract must be specified.</span></span> <span data-ttu-id="d1386-137">이 GUID는 OLE/COM 개체 뷰어(OleView.exe)와 같은 COM 도구를 사용하여 볼 수 있는 CalcProxy.tlb에 있는 `interfaceID`입니다.</span><span class="sxs-lookup"><span data-stu-id="d1386-137">This GUID is the `interfaceID` from CalcProxy.tlb, which can be viewed by using COM tools such as the OLE/COM Object Viewer (OleView.exe).</span></span> <span data-ttu-id="d1386-138">Office VBA 또는 Visual Basic 6.0과 같은 강력한 형식의 환경인 경우 계약 매개 변수 대신에 형식 라이브러리에 명시적 참조를 추가한 다음 프록시 개체의 형식을 선언하는 방법을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d1386-138">For strongly-typed environments such as Office VBA or Visual Basic 6.0, adding an explicit reference to the type library and then declaring the type of the proxy object can be used in place of the contract parameter.</span></span> <span data-ttu-id="d1386-139">또한 이렇게 하면 클라이언트 애플리케이션 개발 도중에 IntelliSense 지원이 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="d1386-139">This also provides IntelliSense support during client application development.</span></span>  
  
 <span data-ttu-id="d1386-140">서비스 모니커를 사용하여 프록시 인스턴스를 생성한 후 클라이언트 애플리케이션은 프록시에서 메서드를 호출할 수 있습니다. 이렇게 하면 결과적으로 서비스 모니커 인프라에서 해당 서비스 작업을 호출하게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d1386-140">Having constructed the proxy instance with the service moniker, the client application can call methods on the proxy, which results in the service moniker infrastructure calling the corresponding service operations.</span></span>  
  
```vbscript  
' Call the service operations using the moniker object  
WScript.Echo "Typed service moniker: 100 + 15.99 = " & typedServiceMoniker.Add(100, 15.99)  
```  
  
 샘플을 실행할 경우 작업 응답이 Windows 스크립트 호스트 메시지 상자 창에 표시됩니다. 이는 입력된 모니커를 사용하여 COM 호출을 WCF 서비스와 통신하는 COM 클라이언트를 보여 줍니다. <span data-ttu-id="d1386-143">클라이언트 애플리케이션에서 COM이 사용되지만 서비스와의 통신은 웹 서비스 호출로만 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="d1386-143">Despite the use of COM in the client application, the communication with the service consists only of Web service calls.</span></span>  
  
## <a name="wsdl-contract"></a><span data-ttu-id="d1386-144">WSDL 계약</span><span class="sxs-lookup"><span data-stu-id="d1386-144">WSDL Contract</span></span>  
 <span data-ttu-id="d1386-145">WSDL 계약과 함께 모니커를 사용하려면 클라이언트 라이브러리 등록이 필요하지 않지만 브라우저를 사용하여 서비스의 WSDL 엔드포인트에 액세스하는 것처럼 out-of-band 메커니즘을 통해 서비스에 대한 WSDL 계약을 검색해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d1386-145">To use the moniker with a WSDL contract, no client library registration is required but the WSDL contract for the service must be retrieved through an out-of-band mechanism such as using a browser to access the WSDL endpoint for the service.</span></span> <span data-ttu-id="d1386-146">그런 다음 모니커는 실행 시에 해당 계약에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d1386-146">The moniker can then access that contract at execution time.</span></span>  
  
 <span data-ttu-id="d1386-147">ComCalcClient.vbs 클라이언트 애플리케이션은 `FileSystemObject`를 사용하여 로컬로 저장된 WSDL 파일에 액세스한 다음 `GetObject` 함수를 다시 사용하여 서비스에 대한 프록시를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="d1386-147">The ComCalcClient.vbs client application uses the `FileSystemObject` to access the locally saved WSDL file and then again uses the `GetObject` function to construct a proxy for the service.</span></span>  
  
```vbscript  
' Open the WSDL contract file and read it all into the wsdlContract string  
Const ForReading = 1  
Set objFSO = CreateObject("Scripting.FileSystemObject")  
Set objFile = objFSO.OpenTextFile("serviceWsdl.xml", ForReading)  
wsdlContract = objFile.ReadAll  
objFile.Close  
  
' Create a string for the service moniker including the content of the WSDL contract file  
wsdlMonikerString = "service4:address='http://localhost/ServiceModelSamples/service.svc'"  
wsdlMonikerString = wsdlMonikerString + ", binding=WSHttpBinding_ICalculator, bindingNamespace='http://Microsoft.ServiceModel.Samples'"  
wsdlMonikerString = wsdlMonikerString + ", wsdl='" & wsdlContract & "'"  
wsdlMonikerString = wsdlMonikerString + ", contract=ICalculator, contractNamespace='http://Microsoft.ServiceModel.Samples'"  
  
' Create the service moniker object  
Set wsdlServiceMoniker = GetObject(wsdlMonikerString)  
```  
  
 <span data-ttu-id="d1386-148">모니커에 사용되는 매개 변수는 다음을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="d1386-148">The parameters used by the moniker specify:</span></span>  
  
- <span data-ttu-id="d1386-149">서비스 엔드포인트의 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="d1386-149">The address of the service endpoint.</span></span>  
  
- <span data-ttu-id="d1386-150">해당 엔드포인트와 연결하기 위해 클라이언트가 사용해야 하는 바인딩 및 해당 바인딩이 정의되는 네임스페이스.</span><span class="sxs-lookup"><span data-stu-id="d1386-150">The binding that the client should use to connect with that endpoint and the namespace in which that binding is defined.</span></span> <span data-ttu-id="d1386-151">이 경우 `wsHttpBinding_ICalculator`가 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="d1386-151">In this case, the `wsHttpBinding_ICalculator` is used.</span></span>  
  
- <span data-ttu-id="d1386-152">계약을 정의하는 WSDL.</span><span class="sxs-lookup"><span data-stu-id="d1386-152">The WSDL that defines the contract.</span></span> <span data-ttu-id="d1386-153">이 경우 serviceWsdl.xml 파일에서 읽은 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="d1386-153">In this case this is the string that has been read from the serviceWsdl.xml file.</span></span>  
  
- <span data-ttu-id="d1386-154">계약의 이름 및 네임스페이스.</span><span class="sxs-lookup"><span data-stu-id="d1386-154">The name and namespace of the contract.</span></span> <span data-ttu-id="d1386-155">WSDL에 둘 이상의 계약이 포함될 수도 있으므로 이 식별 정보가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="d1386-155">This identification is required because the WSDL may contain more than one contract.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="d1386-156">기본적으로 WCF 서비스는 사용하는 각 네임스페이스에 대해 별도의 WSDL 파일을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="d1386-156">By default, WCF services generate separate WSDL files for each namespace that the use.</span></span> <span data-ttu-id="d1386-157">이러한 파일은 WSDL 가져오기 구문 사용과 연결됩니다.</span><span class="sxs-lookup"><span data-stu-id="d1386-157">These are linked with the use of the WSDL import construct.</span></span> <span data-ttu-id="d1386-158">모니커에 단일 WSDL 정의가 필요하므로 이 샘플에 표시된 것처럼 단일 네임스페이스가 서비스에 사용되거나 별개의 파일을 수동으로 병합해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d1386-158">Because the moniker expects a single WSDL definition, the service must either use a single namespace as demonstrated in this sample or the separate files must be manually merged.</span></span>  
  
 <span data-ttu-id="d1386-159">서비스 모니커를 사용하여 프록시 인스턴스를 생성한 후 클라이언트 애플리케이션은 프록시에서 메서드를 호출할 수 있습니다. 이렇게 하면 결과적으로 서비스 모니커 인프라에서 해당 서비스 작업을 호출하게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d1386-159">Having constructed the proxy instance with the service moniker, the client application can call methods on the proxy, which results in the service moniker infrastructure calling the corresponding service operations.</span></span>  
  
```vbscript  
' Call the service operations using the moniker object  
WScript.Echo "WSDL service moniker: 145 - 76.54 = " & wsdlServiceMoniker.Subtract(145, 76.54)  
```  
  
 샘플을 실행할 경우 작업 응답이 Windows 스크립트 호스트 메시지 상자 창에 표시됩니다. <span data-ttu-id="d1386-161">이는 WSDL 계약을 사용하여 모니커를 사용하여 COM 호출을 하는 COM 클라이언트가 WCF 서비스와 통신하는 것을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="d1386-161">This demonstrates a COM client making COM calls using the moniker with a WSDL contract to communicate with a WCF service.</span></span>  
  
## <a name="metadata-exchange-contract"></a><span data-ttu-id="d1386-162">메타데이터 교환 계약</span><span class="sxs-lookup"><span data-stu-id="d1386-162">Metadata Exchange Contract</span></span>  
 <span data-ttu-id="d1386-163">MEX 계약과 함께 모니커를 사용하려면 WSDL 계약과 마찬가지로 클라이언트 등록이 필요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d1386-163">To use the moniker with a MEX contract, as with the WSDL contract, no client registration is required.</span></span> <span data-ttu-id="d1386-164">서비스에 대한 계약은 메타데이터 교환의 내부 사용을 통해 실행 시에 검색됩니다.</span><span class="sxs-lookup"><span data-stu-id="d1386-164">The contract for the service is retrieved at execution time through the internal use of Metadata Exchange.</span></span>  
  
 <span data-ttu-id="d1386-165">ComCalcClient.vbs 클라이언트 애플리케이션은 `GetObject` 함수를 다시 사용하여 서비스에 대한 프록시를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="d1386-165">The ComCalcClient.vbs client application again uses the `GetObject` function to construct a proxy for the service.</span></span>  
  
```vbscript  
' Create a string for the service moniker specifying the address to retrieve the service metadata from  
mexMonikerString = "service4:mexAddress='http://localhost/servicemodelsamples/service.svc/mex'"  
mexMonikerString = mexMonikerString + ", address='http://localhost/ServiceModelSamples/service.svc'"  
mexMonikerString = mexMonikerString + ", binding=WSHttpBinding_ICalculator, bindingNamespace='http://Microsoft.ServiceModel.Samples'"  
mexMonikerString = mexMonikerString + ", contract=ICalculator, contractNamespace='http://Microsoft.ServiceModel.Samples'"  
  
' Create the service moniker object  
Set mexServiceMoniker = GetObject(mexMonikerString)  
```  
  
 <span data-ttu-id="d1386-166">모니커에 사용되는 매개 변수는 다음을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="d1386-166">The parameters used by the moniker specify:</span></span>  
  
- <span data-ttu-id="d1386-167">서비스 메타데이터 교환 엔드포인트의 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="d1386-167">The address of the service metadata exchange endpoint.</span></span>  
  
- <span data-ttu-id="d1386-168">서비스 엔드포인트의 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="d1386-168">The address of the service endpoint.</span></span>  
  
- <span data-ttu-id="d1386-169">해당 엔드포인트와 연결하기 위해 클라이언트가 사용해야 하는 바인딩 및 해당 바인딩이 정의되는 네임스페이스.</span><span class="sxs-lookup"><span data-stu-id="d1386-169">The binding that the client should use to connect with that endpoint and the namespace in which that binding is defined.</span></span> <span data-ttu-id="d1386-170">이 경우 `wsHttpBinding_ICalculator`가 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="d1386-170">In this case, the `wsHttpBinding_ICalculator` is used.</span></span>  
  
- <span data-ttu-id="d1386-171">계약의 이름 및 네임스페이스.</span><span class="sxs-lookup"><span data-stu-id="d1386-171">The name and namespace of the contract.</span></span> <span data-ttu-id="d1386-172">WSDL에 둘 이상의 계약이 포함될 수도 있으므로 이 식별 정보가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="d1386-172">This identification is required because the WSDL may contain more than one contract.</span></span>  
  
 <span data-ttu-id="d1386-173">서비스 모니커를 사용하여 프록시 인스턴스를 생성한 후 클라이언트 애플리케이션은 프록시에서 메서드를 호출할 수 있습니다. 이렇게 하면 결과적으로 서비스 모니커 인프라에서 해당 서비스 작업을 호출하게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d1386-173">Having constructed the proxy instance with the service moniker, the client application can call methods on the proxy, which results in the service moniker infrastructure calling the corresponding service operations.</span></span>  
  
```vbscript  
' Call the service operations using the moniker object  
WScript.Echo "MEX service moniker: 9 * 81.25 = " & mexServiceMoniker.Multiply(9, 81.25)  
```  
  
 샘플을 실행할 경우 작업 응답이 Windows 스크립트 호스트 메시지 상자 창에 표시됩니다. <span data-ttu-id="d1386-175">이는 MEX 계약을 사용하여 모니커를 사용하여 COM 을 호출하여 WCF 서비스와 통신하는 COM 클라이언트를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="d1386-175">This demonstrates a COM client making COM calls using the moniker with a MEX contract to communicate with a WCF service.</span></span>  
  
#### <a name="to-set-up-and-build-the-sample"></a><span data-ttu-id="d1386-176">샘플을 설치하고 빌드하려면</span><span class="sxs-lookup"><span data-stu-id="d1386-176">To set up and build the sample</span></span>  
  
1. <span data-ttu-id="d1386-177">Windows 통신 기초 [샘플에 대한 일회성 설치 절차를](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md)수행했어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d1386-177">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2. <span data-ttu-id="d1386-178">C# 또는 Visual Basic .NET 버전의 솔루션을 빌드하려면 [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md)의 지침을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="d1386-178">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
3. <span data-ttu-id="d1386-179">Visual Studio에 대한 개발자 명령 프롬프트에서 언어별 폴더 아래에 \client\bin 폴더를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="d1386-179">From a Developer Command Prompt for Visual Studio, open the \client\bin folder, under the language-specific folder.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="d1386-180">Windows Vista, Windows Server 2008, Windows 7 또는 Windows Server 2008 R2를 사용하는 경우 관리자 권한으로 명령 프롬프트를 실행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d1386-180">If you are using Windows Vista, Windows Server 2008, Windows 7, or Windows Server 2008 R2, make sure that you run the command prompt with administrator privileges.</span></span>  
  
4. <span data-ttu-id="d1386-181">dll을 tlb 파일로 내보내려면 입력합니다. `tlbexp.exe client.dll /out:CalcProxy.tlb`</span><span class="sxs-lookup"><span data-stu-id="d1386-181">Type in `tlbexp.exe client.dll /out:CalcProxy.tlb` to export the dll to a tlb file.</span></span> <span data-ttu-id="d1386-182">"형식 라이브러리 내보내기 경고"가 발생할 수 있지만 제네릭 형식이 필요하지 않으므로 문제가 되지는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d1386-182">A "Type library exporter warning" is expected but is not an issue because the generic type is not required.</span></span>  
  
5. <span data-ttu-id="d1386-183">`regasm.exe /tlb:CalcProxy.tlb client.dll` 입력하여 COM으로 형식을 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="d1386-183">Type in `regasm.exe /tlb:CalcProxy.tlb client.dll` to register the types with COM.</span></span> <span data-ttu-id="d1386-184">"형식 라이브러리 내보내기 경고"가 발생할 수 있지만 제네릭 형식이 필요하지 않으므로 문제가 되지는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d1386-184">A "Type library exporter warning" is expected but is not an issue because the generic type is not required.</span></span>  
  
6. <span data-ttu-id="d1386-185">입력을 `gacutil.exe /i client.dll` 입력하여 전역 어셈블리 캐시에 어셈블리를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="d1386-185">Type in `gacutil.exe /i client.dll` to add the assembly to the Global Assembly Cache.</span></span>  
  
#### <a name="to-run-the-sample-on-the-same-computer"></a><span data-ttu-id="d1386-186">단일 컴퓨터 구성에서 샘플을 실행하려면</span><span class="sxs-lookup"><span data-stu-id="d1386-186">To run the sample on the same computer</span></span>  
  
1. <span data-ttu-id="d1386-187">다음 주소를 입력하여 브라우저를 사용하여 서비스에 액세스할 수 `http://localhost/servicemodelsamples/service.svc`있는지 테스트합니다.</span><span class="sxs-lookup"><span data-stu-id="d1386-187">Test that you can access the service using a browser by typing in the following address: `http://localhost/servicemodelsamples/service.svc`.</span></span> <span data-ttu-id="d1386-188">확인 페이지가 응답으로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="d1386-188">A confirmation page should be displayed in response.</span></span>  
  
2. <span data-ttu-id="d1386-189">언어별 폴더의 \client에서 ComCalcClient.vbs를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="d1386-189">Run ComCalcClient.vbs from \client, from under the language-specific folder.</span></span> <span data-ttu-id="d1386-190">메시지 상자 창에 클라이언트 동작이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="d1386-190">Client activity is displayed in message box windows.</span></span>  
  
3. <span data-ttu-id="d1386-191">클라이언트와 서비스가 통신할 수 없는 경우 [WCF 샘플에 대한 문제 해결 팁을](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751511(v=vs.90))참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="d1386-191">If the client and service are not able to communicate, see [Troubleshooting Tips for WCF Samples](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751511(v=vs.90)).</span></span>  
  
#### <a name="to-run-the-sample-across-computers"></a><span data-ttu-id="d1386-192">다중 컴퓨터 구성에서 샘플을 실행하려면</span><span class="sxs-lookup"><span data-stu-id="d1386-192">To run the sample across computers</span></span>  
  
1. <span data-ttu-id="d1386-193">서비스 컴퓨터에서 ServiceModelSamples라는 가상 디렉터리를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="d1386-193">On the service computer, create a virtual directory named ServiceModelSamples.</span></span> <span data-ttu-id="d1386-194">샘플에 포함된 Setupvroot.bat 스크립트를 사용하여 디스크 디렉터리와 가상 디렉터리를 만들 수 있습니다</span><span class="sxs-lookup"><span data-stu-id="d1386-194">The Setupvroot.bat script included with the sample can be used to create the disk directory and virtual directory.</span></span>  
  
2. <span data-ttu-id="d1386-195">%SystemDrive%\Inetpub\wwwroot\servicemodelsamples에서 서비스 프로그램 파일을 서비스 컴퓨터의 ServiceModelSamples 가상 디렉터리로 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="d1386-195">Copy the service program files from %SystemDrive%\Inetpub\wwwroot\servicemodelsamples to the ServiceModelSamples virtual directory on the service computer.</span></span> <span data-ttu-id="d1386-196">\bin 디렉터리에 파일을 포함해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d1386-196">Be sure to include the files in the \bin directory.</span></span>  
  
3. <span data-ttu-id="d1386-197">언어별 폴더의 \client 폴더에서 클라이언트 컴퓨터로 클라이언트 스크립트 파일을 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="d1386-197">Copy the client script file from the \client folder, under the language-specific folder, to the client computer.</span></span>  
  
4. <span data-ttu-id="d1386-198">스크립트 파일에서 엔드포인트 정의의 주소 값을 서비스의 새 주소와 일치하도록 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="d1386-198">In the script file, change the address value of the endpoint definition to match the new address of your service.</span></span> <span data-ttu-id="d1386-199">주소에서 "localhost"에 대한 참조를 정규화된 도메인 이름으로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="d1386-199">Replace any references to "localhost" with a fully-qualified domain name in the address.</span></span>  
  
5. <span data-ttu-id="d1386-200">WSDL 파일을 클라이언트 컴퓨터로 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="d1386-200">Copy the WSDL file to the client computer.</span></span> <span data-ttu-id="d1386-201">WSDL 파일 serviceWsdl.xml에서 주소의 "localhost"에 대한 참조를 정규화된 도메인 이름으로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="d1386-201">In the WSDL file, serviceWsdl.xml, replace any references to "localhost" with a fully-qualified domain name in the address.</span></span>  
  
6. <span data-ttu-id="d1386-202">언어별 폴더의 \client\bin 폴더에서 클라이언트 컴퓨터의 디렉터리로 Client.dll 라이브러리를 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="d1386-202">Copy the Client.dll library from the \client\bin folder, under the language-specific folder, to a directory on the client computer.</span></span>  
  
7. <span data-ttu-id="d1386-203">명령 프롬프트에서 클라이언트 컴퓨터의 대상 디렉터리로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="d1386-203">From a command prompt, navigate to that destination directory on the client computer.</span></span> <span data-ttu-id="d1386-204">Windows Vista 또는 Windows Server 2008을 사용하는 경우 명령 프롬프트를 관리자로 실행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d1386-204">If using Windows Vista or Windows Server 2008, make sure to run the command prompt as Administrator.</span></span>  
  
8. <span data-ttu-id="d1386-205">dll을 tlb 파일로 내보내려면 입력합니다. `tlbexp.exe client.dll /out:CalcProxy.tlb`</span><span class="sxs-lookup"><span data-stu-id="d1386-205">Type in `tlbexp.exe client.dll /out:CalcProxy.tlb` to export the dll to a tlb file.</span></span> <span data-ttu-id="d1386-206">"형식 라이브러리 내보내기 경고"가 발생할 수 있지만 제네릭 형식이 필요하지 않으므로 문제가 되지는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d1386-206">A "Type library exporter warning" is expected but is not an issue because the generic type is not required.</span></span>  
  
9. <span data-ttu-id="d1386-207">`regasm.exe /tlb:CalcProxy.tlb client.dll` 입력하여 COM으로 형식을 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="d1386-207">Type in `regasm.exe /tlb:CalcProxy.tlb client.dll` to register the types with COM.</span></span> <span data-ttu-id="d1386-208">명령을 실행하기 전에 경로가 포함된 `regasm.exe` 폴더로 설정되어 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="d1386-208">Ensure that path has been set to the folder that contains `regasm.exe` before you run the command.</span></span>  
  
10. <span data-ttu-id="d1386-209">입력을 `gacutil.exe /i client.dll` 입력하여 전역 어셈블리 캐시에 어셈블리를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="d1386-209">Type in `gacutil.exe /i client.dll` to add the assembly to the Global Assembly Cache.</span></span> <span data-ttu-id="d1386-210">명령을 실행하기 전에 경로가 포함된 `gacutil.exe` 폴더로 설정되어 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="d1386-210">Ensure that path has been set to the folder that contains `gacutil.exe` before you run the command.</span></span>  
  
11. <span data-ttu-id="d1386-211">클라이언트 컴퓨터에서 브라우저를 사용하여 서비스에 액세스할 수 있는지 테스트합니다.</span><span class="sxs-lookup"><span data-stu-id="d1386-211">Test that you can access the service from the client computer using a browser.</span></span>  
  
12. <span data-ttu-id="d1386-212">클라이언트 컴퓨터에서 ComCalcClient.vbs를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="d1386-212">On the client computer, launch ComCalcClient.vbs.</span></span>  
  
#### <a name="to-clean-up-after-the-sample"></a><span data-ttu-id="d1386-213">샘플 실행 후 정리를 수행하려면</span><span class="sxs-lookup"><span data-stu-id="d1386-213">To clean up after the sample</span></span>  
  
- <span data-ttu-id="d1386-214">보안을 위해 샘플 사용이 끝나면 설정 단계에서 부여된 가상 디렉터리 정의와 사용 권한을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="d1386-214">For security purposes, remove the virtual directory definition and permissions granted in the setup steps when you are finished with the samples.</span></span>  
