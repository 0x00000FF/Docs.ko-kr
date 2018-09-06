---
title: POCO 지원
ms.date: 03/30/2017
ms.assetid: 3846ca73-2819-4ca2-8367-dc739dde5a5b
ms.openlocfilehash: beba1469d5d9575a5b2ef76a4db3747dfcc35d0c
ms.sourcegitcommit: 3c1c3ba79895335ff3737934e39372555ca7d6d0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/06/2018
ms.locfileid: "43857604"
---
# <a name="poco-support"></a><span data-ttu-id="7aa5b-102">POCO 지원</span><span class="sxs-lookup"><span data-stu-id="7aa5b-102">POCO Support</span></span>
<span data-ttu-id="7aa5b-103">이 샘플에서는 표시되지 않은 형식, 즉 serialization 특성이 적용되지 않은 형식을 소개합니다. 이러한 형식을 POCO(Plain Old CLR Object) 형식이라고도 합니다.</span><span class="sxs-lookup"><span data-stu-id="7aa5b-103">This sample demonstrates the serialization support for unmarked types; that is, types to which serialization attributes have not been applied, sometimes referred to as Plain Old CLR Object (POCO) types.</span></span> <span data-ttu-id="7aa5b-104"><xref:System.Runtime.Serialization.DataContractSerializer>는 기본 생성자를 가진 표시되지 않은 모든 public 형식에 대한 데이터 계약을 유추합니다.</span><span class="sxs-lookup"><span data-stu-id="7aa5b-104">The <xref:System.Runtime.Serialization.DataContractSerializer> infers a data contract for all public unmarked types that have a default constructor.</span></span> <span data-ttu-id="7aa5b-105">데이터 계약을 사용하면 서비스와 구조적 데이터를 주고 받을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7aa5b-105">Data contracts allow you to pass structured data to and from services.</span></span> <span data-ttu-id="7aa5b-106">표시 되지 않은 형식에 대 한 자세한 내용은 참조 하세요. [Serializable Types](../../../../docs/framework/wcf/feature-details/serializable-types.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="7aa5b-106">For more information about unmarked types, see [Serializable Types](../../../../docs/framework/wcf/feature-details/serializable-types.md).</span></span>  
  
 <span data-ttu-id="7aa5b-107">이 샘플은 기반 합니다 [Getting Started](../../../../docs/framework/wcf/samples/getting-started-sample.md), 하지만 기본 숫자 형식 대신에 복소수를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="7aa5b-107">This sample is based on the [Getting Started](../../../../docs/framework/wcf/samples/getting-started-sample.md), but uses complex numbers instead of primitive numeric types.</span></span> <span data-ttu-id="7aa5b-108">비슷합니다 이기도 합니다 [Basic Data Contract](../../../../docs/framework/wcf/samples/basic-data-contract.md) 샘플링 하는 점을 제외 하면를 <xref:System.Runtime.Serialization.DataContractAttribute> 및 <xref:System.Runtime.Serialization.DataMemberAttribute> 특성은 사용 되지.</span><span class="sxs-lookup"><span data-stu-id="7aa5b-108">It is also similar to the [Basic Data Contract](../../../../docs/framework/wcf/samples/basic-data-contract.md) sample, except that the <xref:System.Runtime.Serialization.DataContractAttribute> and <xref:System.Runtime.Serialization.DataMemberAttribute> attributes are not used.</span></span>  
  
 <span data-ttu-id="7aa5b-109">서비스는 IIS(인터넷 정보 서비스)를 통해 호스팅되고 클라이언트는 콘솔 응용 프로그램(.exe)입니다.</span><span class="sxs-lookup"><span data-stu-id="7aa5b-109">The service is hosted by Internet Information Services (IIS) and the client is a console application (.exe).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="7aa5b-110">이 샘플의 설치 절차 및 빌드 지침은 이 항목의 끝부분에 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7aa5b-110">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
 <span data-ttu-id="7aa5b-111">`ComplexNumber` 클래스는 `ServiceContract`에서 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="7aa5b-111">The `ComplexNumber` class is used in the `ServiceContract`.</span></span> <span data-ttu-id="7aa5b-112">다음 샘플 코드에 나온 것처럼 `ComplexNumber` 형식에는 <xref:System.Runtime.Serialization.DataContractAttribute> 및 <xref:System.Runtime.Serialization.DataMemberAttribute> 특성이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="7aa5b-112">The `ComplexNumber` type does not have the <xref:System.Runtime.Serialization.DataContractAttribute> and <xref:System.Runtime.Serialization.DataMemberAttribute> attributes, as shown in the following sample code.</span></span> <span data-ttu-id="7aa5b-113">기본적으로 모든 public 속성과 필드가 serialize됩니다.</span><span class="sxs-lookup"><span data-stu-id="7aa5b-113">By default, all public properties and fields are serialized.</span></span>  
  
```  
public class ComplexNumber  
{  
    public double Real;  
    public double Imaginary;  
    public ComplexNumber()  
    {  
        Real = double.MinValue;  
        Imaginary = double.MinValue;  
    }  
    public ComplexNumber(double real, double imaginary)  
    {  
        this.Real = real;  
        this.Imaginary = imaginary;  
    }  
}  
```  
  
### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="7aa5b-114">샘플을 설치, 빌드 및 실행하려면</span><span class="sxs-lookup"><span data-stu-id="7aa5b-114">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="7aa5b-115">수행 했는지 확인 합니다 [Windows Communication Foundation 샘플에 대 한 일회성 설치 절차](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="7aa5b-115">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2.  <span data-ttu-id="7aa5b-116">C# 또는 Visual Basic .NET 버전의 솔루션을 빌드하려면 [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md)의 지침을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="7aa5b-116">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
3.  <span data-ttu-id="7aa5b-117">단일 또는 다중 컴퓨터 구성에서 샘플을 실행 하려면의 지침을 따릅니다 [Windows Communication Foundation 샘플 실행](../../../../docs/framework/wcf/samples/running-the-samples.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="7aa5b-117">To run the sample in a single- or cross-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="7aa5b-118">컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7aa5b-118">The samples may already be installed on your machine.</span></span> <span data-ttu-id="7aa5b-119">계속하기 전에 다음(기본) 디렉터리를 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="7aa5b-119">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="7aa5b-120">이 디렉터리가 없으면로 이동 [Windows Communication Foundation (WCF) 및.NET Framework 4 용 Windows WF (Workflow Foundation) 샘플](https://go.microsoft.com/fwlink/?LinkId=150780) 모든 Windows Communication Foundation (WCF)를 다운로드 하 고 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플.</span><span class="sxs-lookup"><span data-stu-id="7aa5b-120">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="7aa5b-121">이 샘플은 다음 디렉터리에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7aa5b-121">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Contract\Data\POCO`  
  
## <a name="see-also"></a><span data-ttu-id="7aa5b-122">참고 항목</span><span class="sxs-lookup"><span data-stu-id="7aa5b-122">See Also</span></span>  
 <xref:System.Runtime.Serialization.IgnoreDataMemberAttribute>  
 [<span data-ttu-id="7aa5b-123">직렬화 가능 형식</span><span class="sxs-lookup"><span data-stu-id="7aa5b-123">Serializable Types</span></span>](../../../../docs/framework/wcf/feature-details/serializable-types.md)
