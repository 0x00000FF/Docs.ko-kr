---
title: "기본적인 XAML 전용 서비스"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c106feb0-0245-43b5-aefe-93ce0e4d38eb
caps.latest.revision: "6"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 3fbf8a719647199439e2333ba5e26cbe51be3add
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="basic-xaml-only-service"></a><span data-ttu-id="a9d5c-102">기본적인 XAML 전용 서비스</span><span class="sxs-lookup"><span data-stu-id="a9d5c-102">Basic XAML only Service</span></span>
<span data-ttu-id="a9d5c-103">이 샘플에서는 XAML로만 구성된 서비스를 만드는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="a9d5c-103">This sample demonstrates how to create a XAML only service.</span></span> <span data-ttu-id="a9d5c-104">이 시나리오는 자동차 관련 문제에 대한 진단 서비스입니다.</span><span class="sxs-lookup"><span data-stu-id="a9d5c-104">The scenario is a diagnostics service for car-related problems.</span></span> <span data-ttu-id="a9d5c-105">이 서비스는 문제를 진단하기 위해 고객에게 일련의 질문을 하는 워크플로로 구현됩니다.</span><span class="sxs-lookup"><span data-stu-id="a9d5c-105">The service is implemented as a workflow that asks the client a series of questions to diagnose the problem.</span></span> <span data-ttu-id="a9d5c-106">이 서비스로 진단할 수 있는 문제에는 두 가지 유형이 있습니다. 그 중 하나는 자동차의 시동이 걸리지 않는 문제이고, 다른 하나는 공조기가 작동하지 않는 문제입니다.</span><span class="sxs-lookup"><span data-stu-id="a9d5c-106">There are two types of issues the service can diagnose (car does not start or air conditioning not working).</span></span> <span data-ttu-id="a9d5c-107">이 워크플로에서는 디자이너의 요청/회신 템플릿을 사용하여 간단한 서비스 작업 세 가지를 노출합니다.</span><span class="sxs-lookup"><span data-stu-id="a9d5c-107">The workflow uses Request/Reply template from the designer to expose three simple service operations.</span></span> <span data-ttu-id="a9d5c-108">서비스는 IIS에 가상 디렉터리를 만들고 service1.xamlx와 Web.config 파일을 가상 디렉터리에 복사하여 IIS에서 호스트되며 컴파일된 코드는 필요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a9d5c-108">The service is hosted in IIS by creating a virtual directory in IIS and copying the service1.xamlx and Web.config files into the virtual directory, no compiled code is required.</span></span> <span data-ttu-id="a9d5c-109">기본적으로이 샘플에서는 자동으로 복사 필요한 파일을 WCF 및 WF 샘플에 대 한 설치 지침을 수행할 때 만든 가상 디렉터리에: [WindowsCommunicationFoundation샘플의일회설치절차](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md) Visual Studio 2010에서 기본적으로 제공 하는 경우.</span><span class="sxs-lookup"><span data-stu-id="a9d5c-109">By default this sample will automatically copy the needed files into the virtual directory created when you follow the setup instructions for the WCF and WF samples: [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md) when built in Visual Studio 2010.</span></span>  
  
#### <a name="to-use-this-sample"></a><span data-ttu-id="a9d5c-110">이 샘플을 사용하려면</span><span class="sxs-lookup"><span data-stu-id="a9d5c-110">To use this sample</span></span>  
  
1.  <span data-ttu-id="a9d5c-111">[!INCLUDE[vs2010](../../../../includes/vs2010-md.md)]에 프로젝트 솔루션을 로드하고 프로젝트를 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="a9d5c-111">Load the project solution in [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] and build the project.</span></span>  
  
2.  <span data-ttu-id="a9d5c-112">[solution base directory]\Client\bin\debug에 생성된 클라이언트 응용 프로그램을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="a9d5c-112">Run the Client application generated in [solution base directory]\Client\bin\debug.</span></span>  
  
3.  <span data-ttu-id="a9d5c-113">응용 프로그램에 옵션이 출력되면 옵션을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="a9d5c-113">The application prints out options, selects an option.</span></span> <span data-ttu-id="a9d5c-114">그런 다음 응용 프로그램에 몇 가지 질문이 표시되면 Y/N 키를 사용하여 예 또는 아니요로 답합니다.</span><span class="sxs-lookup"><span data-stu-id="a9d5c-114">The application then asks some questions, answer them yes or no (using Y/N keys).</span></span> <span data-ttu-id="a9d5c-115">서비스를 통해 문제 진단이 완료되면 진단 결과가 응용 프로그램에 출력됩니다.</span><span class="sxs-lookup"><span data-stu-id="a9d5c-115">When the service is done diagnosing the issues, the application prints out a diagnosis.</span></span>  
  
4.  <span data-ttu-id="a9d5c-116">응용 프로그램이 옵션 화면으로 되돌아갑니다.</span><span class="sxs-lookup"><span data-stu-id="a9d5c-116">The application goes back to the options.</span></span> <span data-ttu-id="a9d5c-117">여기에서 다른 문제를 진단하거나 응용 프로그램을 끝낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a9d5c-117">You can diagnose another problem or exit the application.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="a9d5c-118">컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a9d5c-118">The samples may already be installed on your machine.</span></span> <span data-ttu-id="a9d5c-119">계속하기 전에 다음(기본) 디렉터리를 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="a9d5c-119">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="a9d5c-120">이 디렉터리가 없으면 [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4(.NET Framework 4용 WCF(Windows Communication Foundation) 및 WF(Windows Workflow Foundation) 샘플)](http://go.microsoft.com/fwlink/?LinkId=150780) 로 이동하여 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 및 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플을 모두 다운로드하세요.</span><span class="sxs-lookup"><span data-stu-id="a9d5c-120">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="a9d5c-121">이 샘플은 다음 디렉터리에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a9d5c-121">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Services\XAMLService`  
  
## <a name="see-also"></a><span data-ttu-id="a9d5c-122">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a9d5c-122">See Also</span></span>
