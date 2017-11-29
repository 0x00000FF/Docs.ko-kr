---
title: "트랜잭션 범위 무시"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 49fb6dd4-30d4-4067-925c-c5de44c8c740
caps.latest.revision: "8"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: e95262fc1aee6efb6fe63f06530b70c7c16f64b3
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="suppress-transaction-scope"></a><span data-ttu-id="ee2f0-102">트랜잭션 범위 무시</span><span class="sxs-lookup"><span data-stu-id="ee2f0-102">Suppress Transaction Scope</span></span>
<span data-ttu-id="ee2f0-103">이 샘플에서는 앰비언트 런타임 트랜잭션이 있는 경우 이 트랜잭션을 표시하지 않도록 사용자 지정 `SuppressTransactionScope` 활동을 작성하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="ee2f0-103">The sample demonstrates how to author a custom `SuppressTransactionScope` activity to suppress the ambient run-time transaction, if present.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="ee2f0-104">컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ee2f0-104">The samples may already be installed on your machine.</span></span> <span data-ttu-id="ee2f0-105">계속하기 전에 다음(기본) 디렉터리를 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="ee2f0-105">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="ee2f0-106">이 디렉터리가 없으면 [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4(.NET Framework 4용 WCF(Windows Communication Foundation) 및 WF(Windows Workflow Foundation) 샘플)](http://go.microsoft.com/fwlink/?LinkId=150780) 로 이동하여 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 및 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플을 모두 다운로드하세요.</span><span class="sxs-lookup"><span data-stu-id="ee2f0-106">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="ee2f0-107">이 샘플은 다음 디렉터리에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ee2f0-107">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\Transactions\SuppressTransactionScope`  
  
## <a name="sample-details"></a><span data-ttu-id="ee2f0-108">샘플 세부 정보</span><span class="sxs-lookup"><span data-stu-id="ee2f0-108">Sample Details</span></span>  
 <span data-ttu-id="ee2f0-109">사용자 지정 활동은 트랜잭션 흐름이 특정 시나리오에 대해 문제가 있는 경우 트랜잭션을 다른 서비스로 이동하지 못하도록 하는 데 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="ee2f0-109">The custom activity is useful to prevent a transaction from being flowed out to another service if transaction flow is undesirable for the particular scenario.</span></span> <span data-ttu-id="ee2f0-110">워크플로 런타임에는 <xref:System.Activities.NativeActivity> 클래스에 앰비언트 트랜잭션을 표시하지 못하게 하기 위한 기본 제공 지원이 있지만 이 지원을 사용하려면 이 샘플에 있는 것과 같은 사용자 지정 <xref:System.Activities.NativeActivity>를 작성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ee2f0-110">The workflow runtime has built-in support for suppressing the ambient transaction in the <xref:System.Activities.NativeActivity> class, but to use this support it is necessary to author a custom <xref:System.Activities.NativeActivity> such as the one in this sample.</span></span>  
  
 <span data-ttu-id="ee2f0-111">시나리오는 세 부분으로 구성되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ee2f0-111">The scenario consists of three parts.</span></span> <span data-ttu-id="ee2f0-112">먼저 <xref:System.Activities.Statements.TransactionScope>가 앰비언트 트랜잭션이 되는 런타임 트랜잭션을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="ee2f0-112">First, a <xref:System.Activities.Statements.TransactionScope> creates a run-time transaction that becomes ambient.</span></span> <span data-ttu-id="ee2f0-113">이 트랜잭션은 트랜잭션의 로컬 및 분산 식별자를 출력하는 사용자 지정 활동에 의해 확인됩니다.</span><span class="sxs-lookup"><span data-stu-id="ee2f0-113">This is verified by a custom activity that prints the local and distributed identifiers of the transaction.</span></span> <span data-ttu-id="ee2f0-114">그런 다음 두 번째 부분을 시작하기 전에 이 트랜잭션이 원격 서비스로 이동됩니다.</span><span class="sxs-lookup"><span data-stu-id="ee2f0-114">The transaction is then flowed to a remote service before beginning the second part.</span></span> <span data-ttu-id="ee2f0-115">두 번째 부분이 진행되는 동안 워크플로는 `SuppressTransactionScope`를 시작하고 트랜잭션 식별자를 출력하고 트랜잭션을 이동하는 프로세스를 다시 반복합니다.</span><span class="sxs-lookup"><span data-stu-id="ee2f0-115">During the second part, the workflow enters a `SuppressTransactionScope` and again repeats the process of printing the transaction identifiers and flowing the transaction.</span></span> <span data-ttu-id="ee2f0-116">그러나 사용자 지정 활동은 앰비언트 트랜잭션을 찾지 않고 서비스로 이동된 메시지에는 트랜잭션이 포함되어 있지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ee2f0-116">However, the custom activity does not find an ambient transaction and the message flowed to the service does not contain the transaction.</span></span> <span data-ttu-id="ee2f0-117">결과적으로 서비스는 트랜잭션을 만들며, 이는 클라이언트와 서비스에서 출력된 분산 ID가 일치하지 않음을 의미합니다.</span><span class="sxs-lookup"><span data-stu-id="ee2f0-117">As a result, the service creates a transaction, which means the distributed ID printed on the client and service do not match.</span></span> <span data-ttu-id="ee2f0-118">마지막 부분은 `SuppressTransactionScope`가 종료된 후 발생하며, 다른 메시지에서 첫 번째 메시지의 식별자와 일치하는 분산 식별자를 가진 서비스로 확인될 때 런타임 트랜잭션이 다시 앰비언트 트랜잭션이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ee2f0-118">The final part occurs after the `SuppressTransactionScope` exits and the run-time transaction again becomes ambient as verified by another message to the service with a distributed identifier that matches the identifier of the first message.</span></span>  
  
 <span data-ttu-id="ee2f0-119">활동이 자식 활동을 예약하고 실행 속성을 추가해야 하기 때문에 활동 자체는 <xref:System.Activities.NativeActivity>에서 파생됩니다.</span><span class="sxs-lookup"><span data-stu-id="ee2f0-119">The activity itself derives from <xref:System.Activities.NativeActivity> because it must schedule a child activity and add an execution property.</span></span> <span data-ttu-id="ee2f0-120">`SuppressTransactionScope`에는 핸들이 초기화되어야 하기 때문에 <xref:System.Activities.Variable> 형식의 인스턴스 필드 대신 사용되어야 하는 <xref:System.Activities.RuntimeTransactionHandle> 형식의 <xref:System.Activities.RuntimeTransactionHandle>이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ee2f0-120">The `SuppressTransactionScope` has a <xref:System.Activities.Variable> of type <xref:System.Activities.RuntimeTransactionHandle>, which must be used rather than an instance field of type <xref:System.Activities.RuntimeTransactionHandle> because the handle must be initialized.</span></span> <span data-ttu-id="ee2f0-121">`Variable<RuntimeTransactionHandle>`은 내부적으로만 사용되므로 활동 메타데이터에 구현 변수로 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="ee2f0-121">The `Variable<RuntimeTransactionHandle>` is added to the activity’s metadata as an implementation variable because it is only used internally.</span></span>  
  
 <span data-ttu-id="ee2f0-122">활동을 실행하면 활동은 먼저 본문이 지정되었는지 여부를 확인하고 지정되었으면 `SuppressTransaction`에서 <xref:System.Activities.RuntimeTransactionHandle> 속성을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="ee2f0-122">When the activity is executed it first checks to see whether a body was specified and if so, sets the `SuppressTransaction` property on the <xref:System.Activities.RuntimeTransactionHandle>.</span></span> <span data-ttu-id="ee2f0-123">설정한 속성은 실행 속성에 추가되고 앰비언트 속성이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ee2f0-123">Once the property is set, it is added to the execution properties and becomes ambient.</span></span> <span data-ttu-id="ee2f0-124">즉, `SuppressTransactionScope`의 자식인 모든 활동이 속성을 볼 수 있으므로 런타임 트랜잭션을 표시하지 않도록 적용하고 중첩된 <xref:System.Activities.Statements.TransactionScope>에서 예외를 throw하도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="ee2f0-124">This means that any activity that is a child of the `SuppressTransactionScope` is able to see the property and therefore enforces the suppression of the run-time transaction and causes a nested <xref:System.Activities.Statements.TransactionScope> to throw an exception.</span></span> <span data-ttu-id="ee2f0-125">핸들을 실행 속성에 추가하면 본문이 실행되도록 예약됩니다.</span><span class="sxs-lookup"><span data-stu-id="ee2f0-125">Once the handle is added to the execution properties the body is scheduled to run.</span></span>  
  
#### <a name="to-use-this-sample"></a><span data-ttu-id="ee2f0-126">이 샘플을 사용하려면</span><span class="sxs-lookup"><span data-stu-id="ee2f0-126">To use this sample</span></span>  
  
1.  <span data-ttu-id="ee2f0-127">[!INCLUDE[vs2010](../../../../includes/vs2010-md.md)]에서 SuppressTransactionScope.sln 솔루션을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="ee2f0-127">Open the SuppressTransactionScope.sln solution in [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span></span>  
  
2.  <span data-ttu-id="ee2f0-128">솔루션을 빌드하려면 CTRL + SHIFT + B 키를 누르거나 선택 **솔루션 빌드** 에서 **빌드** 메뉴.</span><span class="sxs-lookup"><span data-stu-id="ee2f0-128">To build the solution, press CTRL+SHIFT+B or select **Build Solution** from the **Build** menu.</span></span>  
  
3.  <span data-ttu-id="ee2f0-129">빌드가 성공한 후 솔루션을 마우스 오른쪽 단추로 클릭 하 고 선택 **시작 프로젝트 설정**합니다.</span><span class="sxs-lookup"><span data-stu-id="ee2f0-129">Once the build has succeeded, right-click the solution and select **Set Startup Projects**.</span></span> <span data-ttu-id="ee2f0-130">이 대화 상자에서 선택 **여러 개의 시작 프로젝트** 하 고 두 프로젝트에 대 한 작업 확인 **시작**합니다.</span><span class="sxs-lookup"><span data-stu-id="ee2f0-130">From the dialog, select **Multiple Startup Projects** and ensure the action for both projects is **Start**.</span></span>  
  
4.  <span data-ttu-id="ee2f0-131">F5 키를 누르거나 선택 **디버깅 시작** 에서 **디버그** 메뉴.</span><span class="sxs-lookup"><span data-stu-id="ee2f0-131">Press F5 or select **Start Debugging** from the **Debug** menu.</span></span> <span data-ttu-id="ee2f0-132">또는 CTRL + f 5를 눌러 수도 있고 선택할 **디버깅 하지 않고 시작** 에서 **디버그** 메뉴 디버깅 없이 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="ee2f0-132">Alternatively, you can press CTRL+F5 or select **Start Without Debugging** from the **Debug** menu to run without debugging.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="ee2f0-133">클라이언트를 시작하기 전에 서버를 실행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ee2f0-133">The server must be running prior to starting the client.</span></span> <span data-ttu-id="ee2f0-134">서비스를 호스트하는 콘솔 창의 출력을 통해 서비스가 시작되었음을 알 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ee2f0-134">The output from the console window that hosts the service indicates when it has started.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="ee2f0-135">컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ee2f0-135">The samples may already be installed on your machine.</span></span> <span data-ttu-id="ee2f0-136">계속하기 전에 다음(기본) 디렉터리를 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="ee2f0-136">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="ee2f0-137">이 디렉터리가 없으면 [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4(.NET Framework 4용 WCF(Windows Communication Foundation) 및 WF(Windows Workflow Foundation) 샘플)](http://go.microsoft.com/fwlink/?LinkId=150780) 로 이동하여 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 및 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플을 모두 다운로드하세요.</span><span class="sxs-lookup"><span data-stu-id="ee2f0-137">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="ee2f0-138">이 샘플은 다음 디렉터리에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ee2f0-138">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\Transactions\SuppressTransactionScope`  
  
## <a name="see-also"></a><span data-ttu-id="ee2f0-139">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ee2f0-139">See Also</span></span>
