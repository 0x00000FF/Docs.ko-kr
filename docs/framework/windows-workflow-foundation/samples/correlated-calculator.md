---
title: 상호 관련된 계산기
ms.date: 03/30/2017
ms.assetid: c365166e-6552-49a4-bf17-9f4e597d4d41
ms.openlocfilehash: 71cfdd0906ef20ec36b76ef5e508a4551b9fe3fe
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/04/2018
ms.locfileid: "43517315"
---
# <a name="correlated-calculator"></a><span data-ttu-id="8064a-102">상호 관련된 계산기</span><span class="sxs-lookup"><span data-stu-id="8064a-102">Correlated Calculator</span></span>
<span data-ttu-id="8064a-103">이 샘플에서는 디자이너에서 메시지의 매개 변수를 기준으로 내용 기반 상관 관계에 <xref:System.ServiceModel.Activities.Receive> 및 <xref:System.ServiceModel.Activities.SendReply> 메시징 활동을 사용하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="8064a-103">This sample demonstrates how to use the messaging activities (<xref:System.ServiceModel.Activities.Receive> and <xref:System.ServiceModel.Activities.SendReply>) in the designer with content-based correlation based on a parameter in the message.</span></span> <span data-ttu-id="8064a-104">이 시나리오에서는 계산이 작업이 병렬 호송됩니다.</span><span class="sxs-lookup"><span data-stu-id="8064a-104">In this scenario, the operations of the calculator are in a parallel convoy.</span></span> <span data-ttu-id="8064a-105">인스턴스 및 `CalculatorId` 기반의 상관 관계는 둘 다 워크플로에 첫 메시지를 보낼 때 만들어지며, `CalculatorId`가 동일한 후속 메시지는 Reset 작업을 호출할 때까지 해당 인스턴스에 디스패치됩니다.</span><span class="sxs-lookup"><span data-stu-id="8064a-105">Both an instance and a correlation (based on `CalculatorId`) are created when the first message is sent to the workflow, and subsequent messages with the same `CalculatorId` are dispatched to that instance until the Reset operation is called.</span></span> <span data-ttu-id="8064a-106">클라이언트는 서비스와 통신하기 위해 코드 기반 클라이언트 프록시를 사용하는 WPF 응용 프로그램으로 구현됩니다.</span><span class="sxs-lookup"><span data-stu-id="8064a-106">The client is implemented as a WPF application that uses a code-based client proxy to communicate with the service.</span></span>  
  
#### <a name="to-use-this-sample"></a><span data-ttu-id="8064a-107">이 샘플을 사용하려면</span><span class="sxs-lookup"><span data-stu-id="8064a-107">To use this sample</span></span>  
  
1.  <span data-ttu-id="8064a-108">높은 권한으로 [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)]을 시작하고 For.sln 솔루션 파일을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="8064a-108">Start [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] in elevated permissions, open the For.sln solution file.</span></span>  
  
    1.  <span data-ttu-id="8064a-109">[!INCLUDE[vs2010](../../../../includes/vs2010-md.md)]이 들어 있는 폴더로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="8064a-109">Navigate to the folder that contains [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span></span>  
  
    2.  <span data-ttu-id="8064a-110">Devenv.exe를 마우스 오른쪽 단추로 클릭 **관리자 권한으로 실행**합니다.</span><span class="sxs-lookup"><span data-stu-id="8064a-110">Right-click Devenv.exe and select **Run as administrator**.</span></span>  
  
2.  <span data-ttu-id="8064a-111">[!INCLUDE[vs2010](../../../../includes/vs2010-md.md)]에서 CorrelatedCalculator.sln 솔루션 파일을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="8064a-111">Using [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)], open the CorrelatedCalculator.sln solution file.</span></span>  
  
3.  <span data-ttu-id="8064a-112">Ctrl+Shift+B를 눌러 솔루션을 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="8064a-112">To build the solution, press CTRL+SHIFT+B.</span></span>  
  
4.  <span data-ttu-id="8064a-113">서비스 프로젝트를 실행하려면 Ctrl+F5를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="8064a-113">To run the service project, press CTRL+F5.</span></span>  
  
5.  <span data-ttu-id="8064a-114">서버가 메시지를 수신할 준비가 되어 있으면 솔루션 탐색기에서 클라이언트 프로젝트를 마우스 오른쪽 단추로 클릭하고 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="8064a-114">Once the service is ready and listening for messages, in Solution Explorer, right-click the Client project and run it.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="8064a-115">컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8064a-115">The samples may already be installed on your machine.</span></span> <span data-ttu-id="8064a-116">계속하기 전에 다음(기본) 디렉터리를 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="8064a-116">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="8064a-117">이 디렉터리가 없으면로 이동 [Windows Communication Foundation (WCF) 및.NET Framework 4 용 Windows WF (Workflow Foundation) 샘플](https://go.microsoft.com/fwlink/?LinkId=150780) 모든 Windows Communication Foundation (WCF)를 다운로드 하 고 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플.</span><span class="sxs-lookup"><span data-stu-id="8064a-117">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="8064a-118">이 샘플은 다음 디렉터리에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8064a-118">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\Services\CorellatedCalculator`