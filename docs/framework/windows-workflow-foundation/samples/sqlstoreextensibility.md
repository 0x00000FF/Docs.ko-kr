---
title: SQLStoreExtensibility
ms.date: 03/30/2017
ms.assetid: 5da1b5a3-f144-41ba-b9c4-02818b28b15d
ms.openlocfilehash: f49d05244cf9f65a8e06f39c7e40391aaebd9f77
ms.sourcegitcommit: 5bbfe34a9a14e4ccb22367e57b57585c208cf757
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/17/2018
ms.locfileid: "45750247"
---
# <a name="sqlstoreextensibility"></a><span data-ttu-id="eb5e9-102">SQLStoreExtensibility</span><span class="sxs-lookup"><span data-stu-id="eb5e9-102">SQLStoreExtensibility</span></span>
<span data-ttu-id="eb5e9-103">이 샘플에서는 SQL 워크플로 인스턴스 저장소에서 승격된 속성을 사용하고 구성하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="eb5e9-103">This sample demonstrates the use and configuration of promoted properties in the SQL workflow instance store.</span></span> <span data-ttu-id="eb5e9-104">SQL 워크플로 인스턴스 저장소는 인스턴스 저장소의 SQL 기반 구현이며,</span><span class="sxs-lookup"><span data-stu-id="eb5e9-104">The SQL workflow instance store is a SQL-based implementation of an instance store.</span></span> <span data-ttu-id="eb5e9-105">이 저장소를 사용하면 인스턴스가 SQL Server 또는 SQL Server Express 데이터베이스 간에 인스턴스 상태를 저장하고 로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eb5e9-105">It allows an instance to save its state and load its state to and from a SQL Server or SQL Server Express database.</span></span> <span data-ttu-id="eb5e9-106">저장소 확장성 기능을 사용하면 사용자가 인스턴스 저장소에 저장되는 속성을 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eb5e9-106">The store extensibility feature allows the user to define properties that are stored in the instance store.</span></span> <span data-ttu-id="eb5e9-107">이러한 속성은 승격된 속성 뷰에 표시되며 사용자는 이 뷰에서 속성을 쿼리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eb5e9-107">These properties are displayed in a promoted properties view that allows the user to query for them.</span></span>  
  
 <span data-ttu-id="eb5e9-108">이 샘플은 계산 서비스를 구현하는 워크플로로 구성되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eb5e9-108">This sample consists of a workflow that implements a counting service.</span></span> <span data-ttu-id="eb5e9-109">서비스의 시작 메서드를 호출하면 서비스는 0부터 29까지 계산합니다.</span><span class="sxs-lookup"><span data-stu-id="eb5e9-109">Once the service's start method is invoked, the service counts from 0 to 29.</span></span> <span data-ttu-id="eb5e9-110">카운터는 2초 간격으로 증가하고,</span><span class="sxs-lookup"><span data-stu-id="eb5e9-110">The counter is incremented once every 2 seconds.</span></span> <span data-ttu-id="eb5e9-111">각 계산 후에 워크플로가 지속됩니다.</span><span class="sxs-lookup"><span data-stu-id="eb5e9-111">After each count, the workflow persists.</span></span> <span data-ttu-id="eb5e9-112">현재 카운터 값은 인스턴스 저장소에 승격된 속성으로 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="eb5e9-112">The current counter value is stored in the instance store as a promoted property.</span></span>  
  
 <span data-ttu-id="eb5e9-113">계산 워크플로는 워크플로 서비스 호스트에서 자체 호스트합니다.</span><span class="sxs-lookup"><span data-stu-id="eb5e9-113">The Counting Workflow is self-hosted by a Workflow Service Host.</span></span> <span data-ttu-id="eb5e9-114">프로그램의 `Main` 메서드는 다음 동작을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="eb5e9-114">The program's `Main` method performs the following actions:</span></span>  
  
-   <span data-ttu-id="eb5e9-115">계산 워크플로를 호스트하는 워크플로 서비스 호스트의 인스턴스를 만들고 계산 워크플로가 도달할 수 있는 끝점을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="eb5e9-115">Creates an instance of the Workflow Service Host that hosts the Counting Workflow and defines the endpoints under which the Counting Workflow can be reached.</span></span>  
  
-   <span data-ttu-id="eb5e9-116">SQL 워크플로 인스턴스 저장소를 구성하는 데 사용되는 SQL 워크플로 인스턴스 저장소 동작을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="eb5e9-116">Defines a SQL workflow instance store behavior, which is used to configure the SQL workflow instance store.</span></span> <span data-ttu-id="eb5e9-117">`CountStatus`를 승격된 속성으로 처리하도록 저장소에 지시합니다.</span><span class="sxs-lookup"><span data-stu-id="eb5e9-117">The store is instructed to treat `CountStatus` as a promoted property.</span></span>  
  
-   <span data-ttu-id="eb5e9-118">계산 워크플로의 시작 메서드를 호출하는 클라이언트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="eb5e9-118">Creates a client that calls the start method of the counting workflow.</span></span>  
  
 <span data-ttu-id="eb5e9-119">프로그램을 시작하면 카운터가 자동으로 계산을 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="eb5e9-119">Once the program is started, the counter automatically starts counting.</span></span> <span data-ttu-id="eb5e9-120">인스턴스를 로드하고 SQL 워크플로 인스턴스 저장소를 구성하는 데는 몇 초 정도 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eb5e9-120">Note that it might take a few seconds to load the instance and configure the SQL workflow instance store.</span></span>  
  
 <span data-ttu-id="eb5e9-121">카운터 값을 사용자 지정 속성으로 승격하려면 다음 단계를 수행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="eb5e9-121">To promote the counter value as a custom property, the following steps must be taken:</span></span>  
  
1.  <span data-ttu-id="eb5e9-122">클래스 `CounterStatus`는 작업이 상태 변수를 제공하는 데 사용하는 <xref:System.Activities.Persistence.PersistenceParticipant> 형식의 인스턴스 확장을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="eb5e9-122">The class `CounterStatus` defines an instance extension of type <xref:System.Activities.Persistence.PersistenceParticipant>, which is used by activities to supply the state variables.</span></span> <span data-ttu-id="eb5e9-123">`Count`는 쓰기 전용 값으로 정의됩니다.</span><span class="sxs-lookup"><span data-stu-id="eb5e9-123">`Count` is defined as a write-only value.</span></span> <span data-ttu-id="eb5e9-124">워크플로 인스턴스가 유지 지점에 도달할 경우 인스턴스 확장은 `Count` 속성을 지속성 데이터 컬렉션에 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="eb5e9-124">When a workflow instance comes to a persistence point, the instance extension saves the `Count` property into the persistence data collection.</span></span>  
  
2.  <span data-ttu-id="eb5e9-125">인스턴스 저장소를 만들 때 새 속성인 `CountStatus`는 `store.Promote()` 메서드를 통해 정의됩니다.</span><span class="sxs-lookup"><span data-stu-id="eb5e9-125">When creating the instance store, a new property, `CountStatus`, is defined through the `store.Promote()` method.</span></span>  
  
3.  <span data-ttu-id="eb5e9-126">워크플로의 `SaveCounter` 활동은 현재 카운터 값을 `Count` 상태 필드에 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="eb5e9-126">The workflow's `SaveCounter` activity assigns the current counter value to the `Count` status field.</span></span>  
  
### <a name="to-use-this-sample"></a><span data-ttu-id="eb5e9-127">이 샘플을 사용하려면</span><span class="sxs-lookup"><span data-stu-id="eb5e9-127">To use this sample</span></span>  
  
1.  <span data-ttu-id="eb5e9-128">인스턴스 저장소 데이터베이스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="eb5e9-128">Create the instance store database.</span></span>  
  
    1.  <span data-ttu-id="eb5e9-129">[!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] 명령 프롬프트를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="eb5e9-129">Open a [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] command prompt.</span></span>  
  
    2.  <span data-ttu-id="eb5e9-130">샘플 디렉터리(\WF\Basic\Persistence\SqlStoreExtensibility\CS)로 이동하고 [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] 명령 프롬프트에서 CreateInstanceStore.cmd를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="eb5e9-130">Navigate to the sample directory (\WF\Basic\Persistence\SqlStoreExtensibility\CS) and run CreateInstanceStore.cmd in the [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] command prompt.</span></span>  
  
        > [!WARNING]
        >  <span data-ttu-id="eb5e9-131">CreateInstanceStore.cmd 스크립트가 SQL Server 2008 Express의 기본 인스턴스에 데이터베이스를 만들려고 시도합니다.</span><span class="sxs-lookup"><span data-stu-id="eb5e9-131">The CreateInstanceStore.cmd script attempts to create the database on the default instance of SQL Server 2008 Express.</span></span> <span data-ttu-id="eb5e9-132">다른 인스턴스에 데이터베이스를 설치하려면 스크립트를 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="eb5e9-132">If you want to install the database on a different instance, modify the script to do so.</span></span>  
  
2.  <span data-ttu-id="eb5e9-133">[!INCLUDE[vs2010](../../../../includes/vs2010-md.md)]을 열고 SqlStoreExtensibility.sln 솔루션을 로드한 다음 Ctrl+Shift+B 키를 눌러 솔루션을 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="eb5e9-133">Open [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] and load the SqlStoreExtensibility.sln solution and build it by pressing CTRL+SHIFT+B.</span></span>  
  
    > [!WARNING]
    >  <span data-ttu-id="eb5e9-134">SQL Server의 기본 인스턴스가 아닌 인스턴스에 데이터베이스를 설치한 경우 솔루션을 빌드하기 전에 코드에서 연결 문자열을 업데이트합니다.</span><span class="sxs-lookup"><span data-stu-id="eb5e9-134">If you installed the database on a non-default instance of SQL Server, update the connection string in the code prior to building the solution.</span></span>  
  
3.  <span data-ttu-id="eb5e9-135">프로젝트의 bin 디렉터리 (\WF\Basic\Persistence\SqlStoreExtensibility\bin\Debug)로 이동 하 여 관리자 권한으로 샘플을 실행 [!INCLUDE[fileExplorer](../../../../includes/fileexplorer-md.md)]SqlStoreExtensibility.exe를 마우스 오른쪽 단추로 클릭 하 고 선택 **으로 실행 관리자**합니다.</span><span class="sxs-lookup"><span data-stu-id="eb5e9-135">Run the sample with administrator privileges by navigating to the project’s bin directory (\WF\Basic\Persistence\SqlStoreExtensibility\bin\Debug) in [!INCLUDE[fileExplorer](../../../../includes/fileexplorer-md.md)], right-clicking SqlStoreExtensibility.exe and selecting **Run as Administrator**.</span></span>  
  
### <a name="to-verify-the-sample-is-working-correctly"></a><span data-ttu-id="eb5e9-136">샘플이 올바르게 작동하고 있는지 확인하려면</span><span class="sxs-lookup"><span data-stu-id="eb5e9-136">To verify the sample is working correctly</span></span>  
  
1.  <span data-ttu-id="eb5e9-137">SQL Server Management Studio를 사용 하 여 인스턴스 테이블의 내용을 선택 하 여 보려는 **데이터베이스**, **InstanceStore**를 차례로  **System.ServiceModel.Activities.DurableInstancing.InstanceTable** 개체 탐색기에서 마우스 오른쪽 단추로 클릭 **System.ServiceModel.Activities.DurableInstancing.InstanceTable** 를선택합니다. **상위 1000 개의 행 선택**합니다.</span><span class="sxs-lookup"><span data-stu-id="eb5e9-137">Use SQL Server Management Studio to view the contents of the instance table by selecting **Databases**, **InstanceStore**, and then **System.ServiceModel.Activities.DurableInstancing.InstanceTable** in the Object Explorer, right-click **System.ServiceModel.Activities.DurableInstancing.InstanceTable** and select **Select Top 1000 Rows**.</span></span> <span data-ttu-id="eb5e9-138">SQL Server Management Studio에 대 한 자세한 내용은 참조 하세요. [SQL Server Management Studio 소개](https://go.microsoft.com/fwlink/?LinkId=165645)</span><span class="sxs-lookup"><span data-stu-id="eb5e9-138">For more information about SQL Server Management Studio, see [Introducing SQL Server Management Studio](https://go.microsoft.com/fwlink/?LinkId=165645)</span></span>  
  
2.  <span data-ttu-id="eb5e9-139">나열된 워크플로 인스턴스를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="eb5e9-139">Observe the workflow instances listed.</span></span>  
  
3.  <span data-ttu-id="eb5e9-140">[!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] 명령 프롬프트에서 샘플 디렉터리(\WF\Basic\Persistence\SqlStoreExtensibility)에 있는 QueryInstanceStore.cmd 스크립트를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="eb5e9-140">In a [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] command prompt, run the QueryInstanceStore.cmd script located in the sample directory (\WF\Basic\Persistence\SqlStoreExtensibility).</span></span>  
  
4.  <span data-ttu-id="eb5e9-141">아래 표시 된 카운터 값을 관찰 **CountStatus**합니다.</span><span class="sxs-lookup"><span data-stu-id="eb5e9-141">Observe the counter value displayed under **CountStatus**.</span></span>  
  
5.  <span data-ttu-id="eb5e9-142">스크립트를 몇 번 실행 참조 하는 **CountStats** 변경 값입니다.</span><span class="sxs-lookup"><span data-stu-id="eb5e9-142">Run the script a few times to see the **CountStats** value change.</span></span>  
  
6.  <span data-ttu-id="eb5e9-143">Enter 키를 눌러 워크플로 응용 프로그램을 종료합니다.</span><span class="sxs-lookup"><span data-stu-id="eb5e9-143">Press ENTER to terminate the workflow application.</span></span>  
  
### <a name="to-uninstall-the-sample"></a><span data-ttu-id="eb5e9-144">샘플을 제거하려면</span><span class="sxs-lookup"><span data-stu-id="eb5e9-144">To uninstall the sample</span></span>  
  
1.  <span data-ttu-id="eb5e9-145">샘플 디렉터리(\WF\Basic\Persistence\SqlStoreExtensibility)에 있는 RemoveInstanceStore.cmd 스크립트를 실행하여 인스턴스 저장소 데이터베이스를 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="eb5e9-145">Remove the instance store database by running the RemoveInstanceStore.cmd script located in the sample directory (\WF\Basic\Persistence\SqlStoreExtensibility).</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="eb5e9-146">컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eb5e9-146">The samples may already be installed on your machine.</span></span> <span data-ttu-id="eb5e9-147">계속하기 전에 다음(기본) 디렉터리를 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="eb5e9-147">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="eb5e9-148">이 디렉터리가 없으면로 이동 [Windows Communication Foundation (WCF) 및.NET Framework 4 용 Windows WF (Workflow Foundation) 샘플](https://go.microsoft.com/fwlink/?LinkId=150780) 모든 Windows Communication Foundation (WCF)를 다운로드 하 고 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플.</span><span class="sxs-lookup"><span data-stu-id="eb5e9-148">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="eb5e9-149">이 샘플은 다음 디렉터리에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eb5e9-149">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Persistence\SQLStoreExtensibility`  
  
## <a name="see-also"></a><span data-ttu-id="eb5e9-150">참고 항목</span><span class="sxs-lookup"><span data-stu-id="eb5e9-150">See Also</span></span>  
 [<span data-ttu-id="eb5e9-151">워크플로 유지</span><span class="sxs-lookup"><span data-stu-id="eb5e9-151">Workflow Persistence</span></span>](../../../../docs/framework/windows-workflow-foundation/workflow-persistence.md)  
 [<span data-ttu-id="eb5e9-152">워크플로 서비스</span><span class="sxs-lookup"><span data-stu-id="eb5e9-152">Workflow Services</span></span>](../../../../docs/framework/wcf/feature-details/workflow-services.md)  
 [<span data-ttu-id="eb5e9-153">AppFabric 호스팅 및 지 속성 샘플</span><span class="sxs-lookup"><span data-stu-id="eb5e9-153">AppFabric Hosting and Persistence Samples</span></span>](https://go.microsoft.com/fwlink/?LinkId=193961)
