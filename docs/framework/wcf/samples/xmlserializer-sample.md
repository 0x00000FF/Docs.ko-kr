---
title: "XMLSerializer 샘플"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 7d134453-9a35-4202-ba77-9ca3a65babc3
caps.latest.revision: "23"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 1e18459d985447359d6314b68e48ce1ad4b0b9d2
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/02/2017
---
# <a name="xmlserializer-sample"></a><span data-ttu-id="0cb9f-102">XMLSerializer 샘플</span><span class="sxs-lookup"><span data-stu-id="0cb9f-102">XMLSerializer Sample</span></span>
<span data-ttu-id="0cb9f-103">이 샘플에서는 <xref:System.Xml.Serialization.XmlSerializer>와 호환되는 형식을 serialize 및 deserialize하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="0cb9f-103">This sample demonstrates how to serialize and deserialize types that are compatible with the <xref:System.Xml.Serialization.XmlSerializer>.</span></span> <span data-ttu-id="0cb9f-104">기본 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 포맷터는 <xref:System.Runtime.Serialization.DataContractSerializer> 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="0cb9f-104">The default [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] formatter is the <xref:System.Runtime.Serialization.DataContractSerializer> class.</span></span> <span data-ttu-id="0cb9f-105"><xref:System.Xml.Serialization.XmlSerializer> 클래스를 사용할 수 없는 경우 <xref:System.Runtime.Serialization.DataContractSerializer> 클래스를 사용하여 형식을 serialize 및 deserialize할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0cb9f-105">The <xref:System.Xml.Serialization.XmlSerializer> class can be used to serialize and deserialize types when the <xref:System.Runtime.Serialization.DataContractSerializer> class cannot be used.</span></span> <span data-ttu-id="0cb9f-106">이는 XML에 대한 정밀한 제어가 필요한 경우(예: 데이터의 일부가 XML 요소가 아닌 XML 특성이어야 하는 경우)에 자주 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="0cb9f-106">This is often the case when precise control over the XML is required - for example, if a piece of data must be an XML attribute and not an XML element.</span></span> <span data-ttu-id="0cb9f-107">또한 <xref:System.Xml.Serialization.XmlSerializer>가 아닌 서비스를 위해 클라이언트를 만들 때 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]가 자동으로 선택되는 경우가 많습니다.</span><span class="sxs-lookup"><span data-stu-id="0cb9f-107">Also, the <xref:System.Xml.Serialization.XmlSerializer> often gets automatically selected when creating clients for non-[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] services.</span></span>  
  
 <span data-ttu-id="0cb9f-108">이 샘플에서 클라이언트는 콘솔 응용 프로그램(.exe)이고 서비스는 IIS(인터넷 정보 서비스)를 통해 호스트됩니다.</span><span class="sxs-lookup"><span data-stu-id="0cb9f-108">In this sample, the client is a console application (.exe) and the service is hosted by Internet Information Services (IIS).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="0cb9f-109">이 샘플의 설치 절차 및 빌드 지침은 이 항목의 끝부분에 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0cb9f-109">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
 <span data-ttu-id="0cb9f-110">다음 샘플 코드에서 보여 주는 것처럼 <xref:System.ServiceModel.ServiceContractAttribute> 및 <xref:System.ServiceModel.XmlSerializerFormatAttribute>가 인터페이스에 적용되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0cb9f-110">The <xref:System.ServiceModel.ServiceContractAttribute> and <xref:System.ServiceModel.XmlSerializerFormatAttribute> must be applied to the interface as shown in the following sample code.</span></span>  
  
```  
[ServiceContract(Namespace="http://Microsoft.ServiceModel.Samples"), XmlSerializerFormat]  
public interface IXmlSerializerCalculator  
{  
    [OperationContract]  
    ComplexNumber Add(ComplexNumber n1, ComplexNumber n2);  
    [OperationContract]  
    ComplexNumber Subtract(ComplexNumber n1, ComplexNumber n2);  
    [OperationContract]  
    ComplexNumber Multiply(ComplexNumber n1, ComplexNumber n2);  
    [OperationContract]  
    ComplexNumber Divide(ComplexNumber n1, ComplexNumber n2);  
}  
```  
  
 <span data-ttu-id="0cb9f-111">`ComplexNumber` 클래스의 public 멤버는 <xref:System.Xml.Serialization.XmlSerializer>에 의해 XML 특성으로 serialize됩니다.</span><span class="sxs-lookup"><span data-stu-id="0cb9f-111">The public members of `ComplexNumber` class are serialized by <xref:System.Xml.Serialization.XmlSerializer> as XML attributes.</span></span> <span data-ttu-id="0cb9f-112">이러한 종류의 XML 인스턴스를 만들 때는 <xref:System.Runtime.Serialization.DataContractSerializer>를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="0cb9f-112">The <xref:System.Runtime.Serialization.DataContractSerializer> cannot be used to create this kind of XML instance.</span></span>  
  
```  
public class ComplexNumber  
{  
    private double real;  
    private double imaginary;  
  
    [XmlAttribute]  
    public double Real  
    {  
        get { return real; }  
        set { real = value; }  
    }  
  
    [XmlAttribute]  
    public double Imaginary  
    {  
        get { return imaginary; }  
        set { imaginary = value; }  
    }  
  
    public ComplexNumber(double real, double imaginary)  
    {  
        this.Real = real;  
        this.Imaginary = imaginary;  
    }  
    public ComplexNumber()  
    {  
        this.Real = 0;  
        this.Imaginary = 0;  
    }  
  
}  
```  
  
 <span data-ttu-id="0cb9f-113">서비스 구현은 적절한 결과를 계산하여 반환합니다. 즉, `ComplexNumber` 형식의 값을 수락하고 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="0cb9f-113">The service implementation calculates and returns the appropriate result—accepting and returning values of the `ComplexNumber` type.</span></span>  
  
```  
public class XmlSerializerCalculatorService : IXmlSerializerCalculator  
{  
    public ComplexNumber Add(ComplexNumber n1, ComplexNumber n2)  
    {  
        return new ComplexNumber(n1.Real + n2.Real, n1.Imaginary +  
                                                      n2.Imaginary);  
    }  
    …  
}  
```  
  
 <span data-ttu-id="0cb9f-114">클라이언트 구현에서도 복소수가 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="0cb9f-114">The client implementation also uses complex numbers.</span></span> <span data-ttu-id="0cb9f-115">서비스 계약 및 데이터 형식을 둘 다에 의해 생성 된 generatedClient.cs 소스 파일에 정의 되어는 [ServiceModel Metadata 유틸리티 도구 (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) 서비스 메타 데이터에서 합니다.</span><span class="sxs-lookup"><span data-stu-id="0cb9f-115">Both the service contract and the data types are defined in the generatedClient.cs source file, which was generated by the [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) from service metadata.</span></span> <span data-ttu-id="0cb9f-116">Svcutil.exe는 계약이 <xref:System.Runtime.Serialization.DataContractSerializer>에 의해 serialize될 수 없는 경우를 감지할 수 있으며, 이 경우 `XmlSerializable` 형식 내보내기로 되돌아갑니다.</span><span class="sxs-lookup"><span data-stu-id="0cb9f-116">Svcutil.exe can detect when a contract is not serializable by the <xref:System.Runtime.Serialization.DataContractSerializer> and reverts to emitting `XmlSerializable` types in this case.</span></span> <span data-ttu-id="0cb9f-117">강제로 <xref:System.Xml.Serialization.XmlSerializer>를 사용하려는 경우 /serializer:XmlSerializer(XmlSerializer 사용) 명령 옵션을 Svcutil.exe 도구에 전달할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0cb9f-117">If you want to force the use of the <xref:System.Xml.Serialization.XmlSerializer>, you can pass the /serializer:XmlSerializer (use XmlSerializer) command option to the Svcutil.exe tool.</span></span>  
  
```  
// Create a client.  
XmlSerializerCalculatorClient client = new  
                         XmlSerializerCalculatorClient();  
  
// Call the Add service operation.  
ComplexNumber value1 = new ComplexNumber();  
value1.Real = 1;  
value1.Imaginary = 2;  
ComplexNumber value2 = new ComplexNumber();  
value2.Real = 3;  
value2.Imaginary = 4;  
ComplexNumber result = client.Add(value1, value2);  
Console.WriteLine("Add({0} + {1}i, {2} + {3}i) = {4} + {5}i",  
    value1.Real, value1.Imaginary, value2.Real, value2.Imaginary,   
    result.Real, result.Imaginary);  
    …  
}  
```  
  
 <span data-ttu-id="0cb9f-118">샘플을 실행하면 작업 요청 및 응답이 클라이언트 콘솔 창에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="0cb9f-118">When you run the sample, the operation requests and responses are displayed in the client console window.</span></span> <span data-ttu-id="0cb9f-119">클라이언트를 종료하려면 클라이언트 창에서 Enter 키를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="0cb9f-119">Press ENTER in the client window to shut down the client.</span></span>  
  
```  
Add(1 + 2i, 3 + 4i) = 4 + 6i  
Subtract(1 + 2i, 3 + 4i) = -2 + -2i  
Multiply(2 + 3i, 4 + 7i) = -13 + 26i  
Divide(3 + 7i, 5 + -2i) = 0.0344827586206897 + 1.41379310344828i  
  
Press <ENTER> to terminate client.  
```  
  
### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="0cb9f-120">샘플을 설치, 빌드 및 실행하려면</span><span class="sxs-lookup"><span data-stu-id="0cb9f-120">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="0cb9f-121">수행 했는지 확인 하십시오.는 [Windows Communication Foundation 샘플의 일회 설치 절차](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="0cb9f-121">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2.  <span data-ttu-id="0cb9f-122">C# 또는 Visual Basic .NET 버전의 솔루션을 빌드하려면 [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md)의 지침을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="0cb9f-122">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
3.  <span data-ttu-id="0cb9f-123">지침에 따라 단일 또는 다중 컴퓨터 구성에서 샘플을 실행 하려면 [Windows Communication Foundation 샘플 실행](../../../../docs/framework/wcf/samples/running-the-samples.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="0cb9f-123">To run the sample in a single- or cross-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="0cb9f-124">컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0cb9f-124">The samples may already be installed on your machine.</span></span> <span data-ttu-id="0cb9f-125">계속하기 전에 다음(기본) 디렉터리를 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="0cb9f-125">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="0cb9f-126">이 디렉터리가 없으면 [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4(.NET Framework 4용 WCF(Windows Communication Foundation) 및 WF(Windows Workflow Foundation) 샘플)](http://go.microsoft.com/fwlink/?LinkId=150780) 로 이동하여 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 및 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플을 모두 다운로드하세요.</span><span class="sxs-lookup"><span data-stu-id="0cb9f-126">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="0cb9f-127">이 샘플은 다음 디렉터리에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0cb9f-127">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Client\Interop\XmlSerializer`  
  
## <a name="see-also"></a><span data-ttu-id="0cb9f-128">참고 항목</span><span class="sxs-lookup"><span data-stu-id="0cb9f-128">See Also</span></span>
