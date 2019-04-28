---
title: '방법: XmlSerializer를 사용하여 WCF 클라이언트 애플리케이션의 시작 시간 향상'
ms.date: 03/30/2017
ms.assetid: 21093451-0bc3-4b1a-9a9d-05f7f71fa7d0
ms.openlocfilehash: b6f010cb5edc3111f05c78f5d27cf178bd501ef9
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61747630"
---
# <a name="how-to-improve-the-startup-time-of-wcf-client-applications-using-the-xmlserializer"></a><span data-ttu-id="e0adf-102">방법: XmlSerializer를 사용하여 WCF 클라이언트 애플리케이션의 시작 시간 향상</span><span class="sxs-lookup"><span data-stu-id="e0adf-102">How to: Improve the Startup Time of WCF Client Applications using the XmlSerializer</span></span>
<span data-ttu-id="e0adf-103"><xref:System.Xml.Serialization.XmlSerializer>를 사용하여 serialize할 수 있는 데이터 형식을 사용하는 서비스 및 클라이언트 응용 프로그램은 런타임에 해당 데이터 형식에 대한 serialization 코드를 생성하고 컴파일합니다. 이로 인해 시작 시 성능이 저하될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e0adf-103">Services and client applications that use data types that are serializable using the <xref:System.Xml.Serialization.XmlSerializer> generate and compile serialization code for those data types at runtime, which can result in slow start-up performance.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e0adf-104">미리 생성된 serialization 코드는 서비스가 아닌 클라이언트 응용 프로그램에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e0adf-104">Pre-generated serialization code can only be used in client applications and not in services.</span></span>  
  
 <span data-ttu-id="e0adf-105">합니다 [ServiceModel Metadata 유틸리티 도구 (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) 응용 프로그램에 대 한 컴파일된 어셈블리 로부터 필요한 serialization 코드를 생성 하 여 이러한 응용 프로그램의 시작 성능을 향상 시킬 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e0adf-105">The [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) can improve start-up performance for these applications by generating the necessary serialization code from the compiled assemblies for the application.</span></span> <span data-ttu-id="e0adf-106">Svcutil.exe는 <xref:System.Xml.Serialization.XmlSerializer>를 사용하여 serialize될 수 있는 컴파일된 응용 프로그램 어셈블리에서 서비스 계약에 사용하는 모든 데이터 형식에 대한 serialization 코드를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="e0adf-106">Svcutil.exe generates serialization code for all data types used in service contracts in the compiled application assembly that can be serialized using the <xref:System.Xml.Serialization.XmlSerializer>.</span></span> <span data-ttu-id="e0adf-107"><xref:System.Xml.Serialization.XmlSerializer>를 사용하는 서비스 및 작업 계약은 <xref:System.ServiceModel.XmlSerializerFormatAttribute>와 함께 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="e0adf-107">Service and operation contracts that use the <xref:System.Xml.Serialization.XmlSerializer> are marked with the <xref:System.ServiceModel.XmlSerializerFormatAttribute>.</span></span>  
  
### <a name="to-generate-xmlserializer-serialization-code"></a><span data-ttu-id="e0adf-108">XmlSerializer serialization 코드를 생성하려면</span><span class="sxs-lookup"><span data-stu-id="e0adf-108">To generate XmlSerializer serialization code</span></span>  
  
1. <span data-ttu-id="e0adf-109">서비스 또는 클라이언트 코드를 하나 이상의 어셈블리로 컴파일합니다.</span><span class="sxs-lookup"><span data-stu-id="e0adf-109">Compile your service or client code into one or more assemblies.</span></span>  
  
2. <span data-ttu-id="e0adf-110">SDK 명령 프롬프트를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="e0adf-110">Open an SDK command prompt.</span></span>  
  
3. <span data-ttu-id="e0adf-111">명령 프롬프트에서 다음 형식을 사용하여 Svcutil.exe 도구를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="e0adf-111">At the command prompt, launch the Svcutil.exe tool using the following format.</span></span>  
  
    ```  
    svcutil.exe /t:xmlSerializer  <assemblyPath>*  
    ```  
  
     <span data-ttu-id="e0adf-112">`assemblyPath` 인수는 서비스 계약 형식이 포함된 어셈블리의 경로를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="e0adf-112">The `assemblyPath` argument specifies the path to an assembly that contains service contract types.</span></span> <span data-ttu-id="e0adf-113">Svcutil.exe는 <xref:System.Xml.Serialization.XmlSerializer>를 사용하여 serialize될 수 있는 컴파일된 응용 프로그램 어셈블리에서 서비스 계약에 사용하는 모든 데이터 형식에 대한 serialization 코드를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="e0adf-113">Svcutil.exe generates serialization code for all data types used in service contracts in the compiled application assembly that can be serialized using the <xref:System.Xml.Serialization.XmlSerializer>.</span></span>  
  
     <span data-ttu-id="e0adf-114">Svcutil.exe는 C# serialization 코드만 생성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e0adf-114">Svcutil.exe can only generate C# serialization code.</span></span> <span data-ttu-id="e0adf-115">각 입력 어셈블리에 대해서 하나의 소스 코드 파일이 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="e0adf-115">One source code file is generated for each input assembly.</span></span> <span data-ttu-id="e0adf-116">사용할 수 없습니다는 **/language** 스위치 생성된 된 코드의 언어를 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="e0adf-116">You cannot use the **/language** switch to change the language of the generated code.</span></span>  
  
     <span data-ttu-id="e0adf-117">종속 어셈블리의 경로를 지정 하려면 사용 합니다 **/reference** 옵션입니다.</span><span class="sxs-lookup"><span data-stu-id="e0adf-117">To specify the path to dependent assemblies, use the **/reference** option.</span></span>  
  
4. <span data-ttu-id="e0adf-118">다음 옵션 중 하나를 사용하여 생성된 serialization 코드를 응용 프로그램에서 사용할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="e0adf-118">Make the generated serialization code available to your application by using one of the following options:</span></span>  
  
    1. <span data-ttu-id="e0adf-119">이름 사용 하 여 별도 어셈블리로 생성된 된 serialization 코드를 컴파일 [*원래 어셈블리*]. .Xmlserializers.dll (예: MyApp.XmlSerializers.dll)입니다.</span><span class="sxs-lookup"><span data-stu-id="e0adf-119">Compile the generated serialization code into a separate assembly with the name [*original assembly*].XmlSerializers.dll (for example, MyApp.XmlSerializers.dll).</span></span> <span data-ttu-id="e0adf-120">응용 프로그램에서 어셈블리를 로드할 수 있어야 하며, 해당 어셈블리는 원본 어셈블리와 동일한 키로 서명되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e0adf-120">Your application must be able to load the assembly, which must be signed with the same key as the original assembly.</span></span> <span data-ttu-id="e0adf-121">원본 어셈블리를 다시 컴파일하면 serialization 어셈블리도 다시 생성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e0adf-121">If you recompile the original assembly, you must regenerate the serialization assembly.</span></span>  
  
    2. <span data-ttu-id="e0adf-122">생성된 serialization 코드를 별도의 어셈블리로 컴파일하고 <xref:System.Xml.Serialization.XmlSerializerAssemblyAttribute>를 사용하는 서비스 계약에 <xref:System.ServiceModel.XmlSerializerFormatAttribute>를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="e0adf-122">Compile the generated serialization code into a separate assembly and use the <xref:System.Xml.Serialization.XmlSerializerAssemblyAttribute> on the service contract that uses the <xref:System.ServiceModel.XmlSerializerFormatAttribute>.</span></span> <span data-ttu-id="e0adf-123">컴파일된 serialization 어셈블리를 가리키기 위해 <xref:System.Xml.Serialization.XmlSerializerAssemblyAttribute.AssemblyName%2A> 또는 <xref:System.Xml.Serialization.XmlSerializerAssemblyAttribute.CodeBase%2A> 속성을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="e0adf-123">Set the <xref:System.Xml.Serialization.XmlSerializerAssemblyAttribute.AssemblyName%2A> or <xref:System.Xml.Serialization.XmlSerializerAssemblyAttribute.CodeBase%2A> properties to point to the compiled serialization assembly.</span></span>  
  
    3. <span data-ttu-id="e0adf-124">생성된 serialization 코드를 응용 프로그램 어셈블리로 컴파일하고 <xref:System.Xml.Serialization.XmlSerializerAssemblyAttribute>를 사용하는 서비스 계약에 <xref:System.ServiceModel.XmlSerializerFormatAttribute>를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="e0adf-124">Compile the generated serialization code into your application assembly and add the <xref:System.Xml.Serialization.XmlSerializerAssemblyAttribute> to the service contract that uses the <xref:System.ServiceModel.XmlSerializerFormatAttribute>.</span></span> <span data-ttu-id="e0adf-125"><xref:System.Xml.Serialization.XmlSerializerAssemblyAttribute.AssemblyName%2A> 또는 <xref:System.Xml.Serialization.XmlSerializerAssemblyAttribute.CodeBase%2A> 속성은 설정하지 마십시오.</span><span class="sxs-lookup"><span data-stu-id="e0adf-125">Do not set the <xref:System.Xml.Serialization.XmlSerializerAssemblyAttribute.AssemblyName%2A> or <xref:System.Xml.Serialization.XmlSerializerAssemblyAttribute.CodeBase%2A> properties.</span></span> <span data-ttu-id="e0adf-126">기본 serialization 어셈블리가 현재 어셈블리로 간주됩니다.</span><span class="sxs-lookup"><span data-stu-id="e0adf-126">The default serialization assembly is assumed to be the current assembly.</span></span>  
  
### <a name="to-generate-xmlserializer-serialization-code-in-visual-studio"></a><span data-ttu-id="e0adf-127">Visual Studio에서 XmlSerializer serialization 코드를 생성 하려면</span><span class="sxs-lookup"><span data-stu-id="e0adf-127">To generate XmlSerializer serialization code in Visual Studio</span></span>  
  
1. <span data-ttu-id="e0adf-128">WCF 서비스와 클라이언트 프로젝트 Visual Studio에서 만들기.</span><span class="sxs-lookup"><span data-stu-id="e0adf-128">Create the WCF service and client projects in Visual Studio.</span></span> <span data-ttu-id="e0adf-129">그런 다음 클라이언트 프로젝트에 대 한 서비스 참조를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="e0adf-129">Then, add a service reference to the client project.</span></span>  
  
2. <span data-ttu-id="e0adf-130">추가 <xref:System.ServiceModel.XmlSerializerFormatAttribute> 서비스 계약에 *reference.cs* 아래에 있는 클라이언트 앱 프로젝트에서 파일 **serviceReference** -> **reference.svcmap** .</span><span class="sxs-lookup"><span data-stu-id="e0adf-130">Add an <xref:System.ServiceModel.XmlSerializerFormatAttribute> to the service contract in the *reference.cs* file in the client app project under **serviceReference** -> **reference.svcmap**.</span></span> <span data-ttu-id="e0adf-131">에 모든 파일 표시 해야 **솔루션 탐색기** 이러한 파일을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e0adf-131">Note that you need to show all files in **Solution Explorer** to see these files.</span></span>  
  
3. <span data-ttu-id="e0adf-132">클라이언트 앱을 빌드하십시오.</span><span class="sxs-lookup"><span data-stu-id="e0adf-132">Build the client app.</span></span>  
  
4. <span data-ttu-id="e0adf-133">사용 된 [ServiceModel Metadata 유틸리티 도구 (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) 미리 생성 된 serializer를 만들려면 *.cs* 명령을 사용 하 여 파일:</span><span class="sxs-lookup"><span data-stu-id="e0adf-133">Use the [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) to create a pre-generated serializer *.cs* file by using the command:</span></span>  
  
    ```  
    svcutil.exe /t:xmlSerializer  <assemblyPath>*  
    ```  
  
     <span data-ttu-id="e0adf-134">AssemblyPath 인수에는 WCF 클라이언트 어셈블리의 경로를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="e0adf-134">The assemblyPath argument specifies the path to the WCF client assembly.</span></span>  
  
     <span data-ttu-id="e0adf-135">와 같은:</span><span class="sxs-lookup"><span data-stu-id="e0adf-135">Such as:</span></span>  
  
    ```  
    svcutil.exe /t:xmlSerializer wcfclient.exe  
    ```  
  
     <span data-ttu-id="e0adf-136">합니다 *WCFClient.XmlSerializers.dll.cs* 파일이 생성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e0adf-136">The *WCFClient.XmlSerializers.dll.cs* file will be generated.</span></span>  
  
5. <span data-ttu-id="e0adf-137">미리 생성 된 serialization 어셈블리를 컴파일하십시오.</span><span class="sxs-lookup"><span data-stu-id="e0adf-137">Compile the pre-generated serialization assembly.</span></span>  
  
     <span data-ttu-id="e0adf-138">이전 단계에서 예제에 따라 컴파일 명령은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="e0adf-138">Based on the example in the previous step, the compile command would be the following:</span></span>  
  
    ```  
    csc /r:wcfclient.exe /out:WCFClient.XmlSerializers.dll /t:library WCFClient.XmlSerializers.dll.cs  
    ```  
  
     <span data-ttu-id="e0adf-139">했는지 생성 된 *WCFClient.XmlSerializers.dll* 는 클라이언트 앱의 경우와 동일한 디렉터리에 *WCFClient.exe* 이 경우.</span><span class="sxs-lookup"><span data-stu-id="e0adf-139">Make sure the generated *WCFClient.XmlSerializers.dll* is in the same directory as the client app, which is *WCFClient.exe* in this case.</span></span>  
  
6. <span data-ttu-id="e0adf-140">클라이언트 앱을 정상적으로 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="e0adf-140">Run the client app as usual.</span></span> <span data-ttu-id="e0adf-141">미리 생성된 된 serialization 어셈블리 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e0adf-141">The pre-generated serialization assembly will be used.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e0adf-142">예제</span><span class="sxs-lookup"><span data-stu-id="e0adf-142">Example</span></span>  
 <span data-ttu-id="e0adf-143">다음 명령은 어셈블리의 모든 서비스 계약이 사용하는 `XmlSerializer` 형식에 대해 serialization 형식을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="e0adf-143">The following command generates serialization types for `XmlSerializer` types that any service contracts in the assembly use.</span></span>  
  
```  
svcutil /t:xmlserializer myContractLibrary.exe  
```  
  
## <a name="see-also"></a><span data-ttu-id="e0adf-144">참고자료</span><span class="sxs-lookup"><span data-stu-id="e0adf-144">See also</span></span>

- [<span data-ttu-id="e0adf-145">ServiceModel Metadata 유틸리티 도구(Svcutil.exe)</span><span class="sxs-lookup"><span data-stu-id="e0adf-145">ServiceModel Metadata Utility Tool (Svcutil.exe)</span></span>](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md)
