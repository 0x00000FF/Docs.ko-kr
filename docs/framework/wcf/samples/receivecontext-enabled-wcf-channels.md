---
title: ReceiveContext 사용 WCF 채널
ms.date: 03/30/2017
ms.assetid: d990d119-7321-4b8c-852b-10256f59f9b0
ms.openlocfilehash: d7f80d0874606129876fbf7dfa30c0327680b922
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/01/2018
ms.locfileid: "43442748"
---
# <a name="receivecontext-enabled-wcf-channels"></a><span data-ttu-id="ff29c-102">ReceiveContext 사용 WCF 채널</span><span class="sxs-lookup"><span data-stu-id="ff29c-102">ReceiveContext-Enabled WCF Channels</span></span>
<span data-ttu-id="ff29c-103">이 샘플에서는 <xref:System.ServiceModel.Channels.ReceiveContext> 사용 WCF 채널의 유용성을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="ff29c-103">This sample demonstrates the usefulness of <xref:System.ServiceModel.Channels.ReceiveContext>-enabled WCF channels.</span></span> <span data-ttu-id="ff29c-104">이 샘플에서는 NetMSMQ 채널을 사용하여 두 수의 곱을 찾기 위한 서비스를 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="ff29c-104">The sample implements a service to find the product of two numbers using a NetMSMQ channel.</span></span>  
  
 <span data-ttu-id="ff29c-105"><xref:System.ServiceModel.Channels.ReceiveContext> 클래스를 사용하면 응용 프로그램에서는 메시지 내용을 검사한 후라도 메시지에 액세스할지 아니면 추가 처리를 위해 메시지를 큐에 둘지를 결정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ff29c-105">The <xref:System.ServiceModel.Channels.ReceiveContext> class enables an application to decide whether to access the message or leave it in the queue for further processing, even after the contents of the message have been inspected.</span></span> <span data-ttu-id="ff29c-106">이 샘플의 클라이언트는 트랜잭션 큐에 임의의 정수를 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="ff29c-106">In this sample, a client sends random integers to a transactional queue.</span></span> <span data-ttu-id="ff29c-107">`ProductCalculator` 서비스에서는 메시지를 받고 메시지 내용, 즉 정수를 검사하여 곱을 계산할 수 있는지 여부를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="ff29c-107">The `ProductCalculator` service receives the messages and inspects the message contents, which are integers, to determine whether the product can be computed.</span></span> <span data-ttu-id="ff29c-108">서비스 작업에서 곱을 계산하지 않는 경우에는 메시지가 큐에 다시 배치되므로 해당 큐에서 수신 대기하는 서비스가 이 메시지를 다시 받을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ff29c-108">If the service operation does not compute the product, the message is put back into the queue and can be received again by the service listening on the queue.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="ff29c-109">컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ff29c-109">The samples may already be installed on your computer.</span></span> <span data-ttu-id="ff29c-110">계속하기 전에 다음(기본) 디렉터리를 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="ff29c-110">Check for the following (default) directory before continuing:</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="ff29c-111">이 디렉터리가 없으면로 이동 [Windows Communication Foundation (WCF) 및.NET Framework 4 용 Windows WF (Workflow Foundation) 샘플](https://go.microsoft.com/fwlink/?LinkId=150780) 모든 Windows Communication Foundation (WCF)를 다운로드 하 고 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플.</span><span class="sxs-lookup"><span data-stu-id="ff29c-111">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="ff29c-112">이 샘플은 다음 디렉터리에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ff29c-112">This sample is located in the following directory:</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Binding\Net\MSMQ\ReceiveContextProductGenerator`  
  
#### <a name="to-use-this-sample"></a><span data-ttu-id="ff29c-113">이 샘플을 사용하려면</span><span class="sxs-lookup"><span data-stu-id="ff29c-113">To use this sample</span></span>  
  
1.  <span data-ttu-id="ff29c-114">MSMQ(Microsoft Message Queuing)가 설치되어 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="ff29c-114">Ensure that Microsoft Message Queuing (MSMQ) is installed.</span></span>  
  
    1.  <span data-ttu-id="ff29c-115">[!INCLUDE[lserver](../../../../includes/lserver-md.md)]에 MSMQ를 설치하려면</span><span class="sxs-lookup"><span data-stu-id="ff29c-115">To install MSMQ on [!INCLUDE[lserver](../../../../includes/lserver-md.md)]:</span></span>  
  
        1.  <span data-ttu-id="ff29c-116">**서버 관리자**, 클릭 **기능**합니다.</span><span class="sxs-lookup"><span data-stu-id="ff29c-116">In **Server Manager**, click **Features**.</span></span>  
  
        2.  <span data-ttu-id="ff29c-117">오른쪽 창의 **기능 요약**, 클릭 **추가 기능**합니다.</span><span class="sxs-lookup"><span data-stu-id="ff29c-117">In the right pane under **Features Summary**, click **Add Features**.</span></span>  
  
        3.  <span data-ttu-id="ff29c-118">결과 창에서 확장 **메시지 큐**합니다.</span><span class="sxs-lookup"><span data-stu-id="ff29c-118">In the resulting window, expand **Message Queuing**.</span></span>  
  
        4.  <span data-ttu-id="ff29c-119">확장 **큐 서비스 메시지**합니다.</span><span class="sxs-lookup"><span data-stu-id="ff29c-119">Expand **Message Queuing Services**.</span></span>  
  
        5.  <span data-ttu-id="ff29c-120">클릭 **디렉터리 서비스 통합** (컴퓨터에 대 한 도메인에 가입)를 클릭 하 고 **HTTP 지원을**합니다.</span><span class="sxs-lookup"><span data-stu-id="ff29c-120">Click **Directory Services Integration** (for computers joined to a domain), and then click **HTTP Support**.</span></span>  
  
        6.  <span data-ttu-id="ff29c-121">클릭 **다음**를 클릭 하 고 **설치**합니다.</span><span class="sxs-lookup"><span data-stu-id="ff29c-121">Click **Next**, and then click **Install**.</span></span>  
  
    2.  <span data-ttu-id="ff29c-122">[!INCLUDE[wv](../../../../includes/wv-md.md)]에 MSMQ를 설치하려면</span><span class="sxs-lookup"><span data-stu-id="ff29c-122">To install MSMQ on [!INCLUDE[wv](../../../../includes/wv-md.md)]:</span></span>  
  
        1.  <span data-ttu-id="ff29c-123">**제어판**을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="ff29c-123">Open **Control Panel**.</span></span>  
  
        2.  <span data-ttu-id="ff29c-124">클릭 **프로그램** 차례로 **프로그램 및 기능**, 클릭 **Windows 기능 사용 안 함 설정 및 해제**합니다.</span><span class="sxs-lookup"><span data-stu-id="ff29c-124">Click **Programs** and then, under **Programs and Features**, click **Turn Windows Features on and off**.</span></span>  
  
        3.  <span data-ttu-id="ff29c-125">확장 **Microsoft Message Queue (MSMQ) Server**, 확장 **Microsoft Message Queue (MSMQ) Server Core**를 선택한 다음 설치 하려면 다음 메시지 큐 기능 확인란:</span><span class="sxs-lookup"><span data-stu-id="ff29c-125">Expand **Microsoft Message Queue (MSMQ) Server**, expand **Microsoft Message Queue (MSMQ) Server Core**, and then select the check boxes for the following Message Queuing features to install:</span></span>  
  
            -   <span data-ttu-id="ff29c-126">메시지 큐 서버</span><span class="sxs-lookup"><span data-stu-id="ff29c-126">Message Queuing Server</span></span>  
  
            -   <span data-ttu-id="ff29c-127">MSMQ Active Directory 도메인 서비스 통합(도메인에 가입된 컴퓨터의 경우)</span><span class="sxs-lookup"><span data-stu-id="ff29c-127">MSMQ Active Directory Domain Services Integration (for computers joined to a domain)</span></span>  
  
            -   <span data-ttu-id="ff29c-128">MSMQ HTTP 지원</span><span class="sxs-lookup"><span data-stu-id="ff29c-128">MSMQ HTTP Support</span></span>  
  
        4.  <span data-ttu-id="ff29c-129">**확인**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="ff29c-129">Click **OK**.</span></span>  
  
        5.  <span data-ttu-id="ff29c-130">컴퓨터 다시 시작 하 라는 메시지가 나타나면 클릭 **확인** 설치를 완료 합니다.</span><span class="sxs-lookup"><span data-stu-id="ff29c-130">If you are prompted to restart the computer, click **OK** to complete the installation.</span></span>  
  
2.  <span data-ttu-id="ff29c-131">컴퓨터에 [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)]이 설치되어 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="ff29c-131">Ensure that [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] is installed on the computer.</span></span>  
  
3.  <span data-ttu-id="ff29c-132">[!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)]에서 ReceiveContextProductGenerator.sln 솔루션 파일을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="ff29c-132">Using [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)], open the ReceiveContextProductGenerator.sln solution file.</span></span>  
  
4.  <span data-ttu-id="ff29c-133">Ctrl+Shift+B를 눌러 솔루션을 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="ff29c-133">To build the solution, press CTRL+SHIFT+B.</span></span>  
  
5.  <span data-ttu-id="ff29c-134">Ctrl+F5를 눌러 솔루션을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="ff29c-134">To run the solution, press CTRL+F5.</span></span>
