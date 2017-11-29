---
title: "기본 제공 구성"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 34e85c9b-088d-4347-816c-0f77cb73ef2f
caps.latest.revision: "15"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 7dc11c19025393ffb1ce8e10cbfa637f38a867fd
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="built-in-configuration"></a><span data-ttu-id="0f930-102">기본 제공 구성</span><span class="sxs-lookup"><span data-stu-id="0f930-102">Built-in Configuration</span></span>
<span data-ttu-id="0f930-103">이 샘플에서는 SQL 워크플로 인스턴스 저장소를 사용하고 구성하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="0f930-103">This sample demonstrates the use and configuration of the SQL workflow instance store.</span></span> <span data-ttu-id="0f930-104">SQL 워크플로 인스턴스 저장소는 인스턴스 저장소의 SQL 기반 구현이며,</span><span class="sxs-lookup"><span data-stu-id="0f930-104">The SQL workflow instance store is a SQL-based implementation of an instance store.</span></span> <span data-ttu-id="0f930-105">이 저장소를 사용하면 인스턴스가 SQL Server 또는 SQL Server Express 데이터베이스 간에 인스턴스 상태를 저장하고 로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0f930-105">It allows an instance to save and load its state to and from a SQL Server or SQL Server Express database.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="0f930-106">컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0f930-106">The samples may already be installed on your computer.</span></span> <span data-ttu-id="0f930-107">계속하기 전에 다음(기본) 디렉터리를 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="0f930-107">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="0f930-108">이 디렉터리가 없으면 다운로드 페이지로 이동하여 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 및 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플을 모두 다운로드하세요.</span><span class="sxs-lookup"><span data-stu-id="0f930-108">If this directory does not exist, go to (download page) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="0f930-109">이 샘플은 다음 디렉터리에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0f930-109">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Persistence\BuiltInConfiguration`  
  
## <a name="sample-details"></a><span data-ttu-id="0f930-110">샘플 세부 정보</span><span class="sxs-lookup"><span data-stu-id="0f930-110">Sample Details</span></span>  
 <span data-ttu-id="0f930-111">이 샘플은 계산 서비스를 구현하는 워크플로로 구성되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0f930-111">This sample consists of a workflow that implements a counting service.</span></span> <span data-ttu-id="0f930-112">서비스의 시작 메서드를 호출하면 서비스는 0부터 59까지 계산합니다.</span><span class="sxs-lookup"><span data-stu-id="0f930-112">Once the service's start method is invoked, the service counts from 0 to 59.</span></span> <span data-ttu-id="0f930-113">카운터는 2초 간격으로 증가하고,</span><span class="sxs-lookup"><span data-stu-id="0f930-113">The counter is incremented once every 2 seconds.</span></span> <span data-ttu-id="0f930-114">각 계산 후에 워크플로가 지속됩니다.</span><span class="sxs-lookup"><span data-stu-id="0f930-114">After each count, the workflow persists.</span></span>  
  
 <span data-ttu-id="0f930-115">계산 워크플로는 워크플로 서비스 호스트에서 자체 호스트합니다.</span><span class="sxs-lookup"><span data-stu-id="0f930-115">The counting workflow is self-hosted by a workflow service host.</span></span> <span data-ttu-id="0f930-116">프로그램의 `Main` 메서드는 계산 워크플로를 호스트하는 워크플로 서비스 호스트의 인스턴스를 만들고,</span><span class="sxs-lookup"><span data-stu-id="0f930-116">The program's `Main` method creates an instance of the workflow service host that hosts the counting workflow.</span></span> <span data-ttu-id="0f930-117">계산 워크플로가 도달할 수 있는 끝점을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="0f930-117">It defines the endpoints under which the counting workflow can be reached.</span></span> <span data-ttu-id="0f930-118">그런 다음 SQL 워크플로 인스턴스 저장소를 구성하는 데 사용되는 SQL 워크플로 인스턴스 저장소 동작을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="0f930-118">After that, it defines a SQL workflow instance store behavior, which is used to configure the SQL workflow instance store.</span></span> <span data-ttu-id="0f930-119">그런 다음 프로그램은 계산 워크플로의 시작 메서드를 호출하는 클라이언트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="0f930-119">Next, the program creates a client that calls the start method of the counting workflow.</span></span>  
  
 <span data-ttu-id="0f930-120">프로그램을 시작하면 카운터가 자동으로 계산을 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="0f930-120">Once the program is started, the counter automatically starts counting.</span></span> <span data-ttu-id="0f930-121">인스턴스를 로드하고 SQL 워크플로 인스턴스 저장소를 구성하는 데는 몇 초 정도 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0f930-121">Note that it might take a few seconds to load the instance and configure the SQL workflow instance store.</span></span> [!INCLUDE[crabout](../../../../includes/crabout-md.md)]<span data-ttu-id="0f930-122">워크플로 인스턴스 저장소에서 참조 [SQL 워크플로 인스턴스 저장소](../../../../docs/framework/windows-workflow-foundation/sql-workflow-instance-store.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="0f930-122"> the workflow instance store, see [SQL Workflow Instance Store](../../../../docs/framework/windows-workflow-foundation/sql-workflow-instance-store.md).</span></span>  
  
 <span data-ttu-id="0f930-123">이 샘플은 두 부분으로 구성되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0f930-123">The sample consists of two parts:</span></span>  
  
1.  <span data-ttu-id="0f930-124">InstanceStore1에서는 C# 코드를 사용하여 <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore>를 구성하는 방법을 보여 줍니다(Program.cs 참조).</span><span class="sxs-lookup"><span data-stu-id="0f930-124">InstanceStore1 shows how <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore> is configured using C# code (see Program.cs).</span></span>  
  
2.  <span data-ttu-id="0f930-125">InstanceStore2에서는 XML을 사용하여 <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore>를 구성하는 방법을 보여 줍니다(App.config 참조).</span><span class="sxs-lookup"><span data-stu-id="0f930-125">InstanceStore2 shows how <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore> is configured using XML (see App.config).</span></span>  
  
 <span data-ttu-id="0f930-126">다음 설정은 SQL 워크플로 인스턴스 저장소 동작을 구성하는 데 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0f930-126">The following settings are available to configure the SQL Workflow Instance Store behavior:</span></span>  
  
-   <span data-ttu-id="0f930-127">`HostLockRenewalPeriod`을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="0f930-127">Set the `HostLockRenewalPeriod`.</span></span> <span data-ttu-id="0f930-128">이 시간에 따라 호스트가 실행하는 인스턴스의 소유권 잠금을 갱신하는 간격이 정의됩니다.</span><span class="sxs-lookup"><span data-stu-id="0f930-128">This time defines the interval with which the host renews the ownership lock of the instances it runs.</span></span> <span data-ttu-id="0f930-129">잠금 정보는 인스턴스 저장소에 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="0f930-129">The lock information is stored in the Instance Store.</span></span> <span data-ttu-id="0f930-130">`HostLockRenewalPeriod`에 정의된 간격이 두 번 경과할 때까지 소유권을 갱신하지 않으면 인스턴스는 중단된 것으로 간주됩니다.</span><span class="sxs-lookup"><span data-stu-id="0f930-130">If the ownership is not renewed for two of the intervals defined in `HostLockRenewalPeriod`, the instance is considered abandoned.</span></span> <span data-ttu-id="0f930-131">다른 <xref:System.ServiceModel.Activities.WorkflowServiceHost>가 같은 컴퓨터나 다른 컴퓨터의 동일한 인스턴스 저장소에 연결되어 있는 상태에서 같은 워크플로를 실행 중이면 해당 인스턴스가 복구됩니다.</span><span class="sxs-lookup"><span data-stu-id="0f930-131">If another <xref:System.ServiceModel.Activities.WorkflowServiceHost> is running the same workflow and connected to the same instance store (either on the same computer or a different computer), it recovers that instance.</span></span> <span data-ttu-id="0f930-132">인스턴스 복구에 대해서는 이 샘플에서 다루지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0f930-132">(Instance Recovery is out of scope for this sample.)</span></span>  
  
-   <span data-ttu-id="0f930-133">`RunnableInstancesDetectionPeriod`을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="0f930-133">Set the `RunnableInstancesDetectionPeriod`.</span></span> <span data-ttu-id="0f930-134">이 기간에 따라 호스트가 실행 가능하게 된 인스턴스를 폴링하는 간격이 정의됩니다.</span><span class="sxs-lookup"><span data-stu-id="0f930-134">This period defines the interval in which the host polls for instances that have become runnable.</span></span> <span data-ttu-id="0f930-135">인스턴스는 다음 이벤트 중 하나가 발생하는 경우 실행 가능하게 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0f930-135">Instances may become runnable if any of the following events occur:</span></span>  
  
    -   <span data-ttu-id="0f930-136">지속적인 타이머(<xref:System.Activities.Statements.Delay>)가 만료되는 경우</span><span class="sxs-lookup"><span data-stu-id="0f930-136">A Durable Timer (<xref:System.Activities.Statements.Delay>) expires.</span></span>  
  
    -   <span data-ttu-id="0f930-137">컴퓨터 고장 등의 이유로 다른 호스트에 `HostLockRenewal` 하트비트가 누락되고 인스턴스가 복구되는 경우</span><span class="sxs-lookup"><span data-stu-id="0f930-137">Another host misses its `HostLockRenewal` heartbeat (for example, due to a computer crash) and the instance is recovered.</span></span>  
  
-   <span data-ttu-id="0f930-138">`InstanceCompletionAction`을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="0f930-138">Set the `InstanceCompletionAction`.</span></span> <span data-ttu-id="0f930-139">이 속성을 `DeleteNothing`으로 설정하면 완료된 인스턴스가 인스턴스 저장소에서 유지되고, `DeleteAll`로 설정하면 인스턴스가 완료될 때 저장소에서 삭제됩니다.</span><span class="sxs-lookup"><span data-stu-id="0f930-139">This property, if set to `DeleteNothing`, keeps completed instances in the Instance Store; if set to `DeleteAll`, instances are deleted from the store upon completion.</span></span> <span data-ttu-id="0f930-140">다음 사항에 유의하십시오.</span><span class="sxs-lookup"><span data-stu-id="0f930-140">Note that</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="0f930-141">계산이 완료되기 전에 Enter 키를 눌러 호스트를 종료하면 워크플로 인스턴스가 완료되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0f930-141">Terminating the host by pressing ENTER before the counting has completed does not complete the workflow instance.</span></span>  
  
-   <span data-ttu-id="0f930-142">`InstanceLockedExceptionAction`을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="0f930-142">Set the `InstanceLockedExceptionAction`.</span></span> <span data-ttu-id="0f930-143">이 설정에 따라 호스트가 다른 호스트에서 잠근 인스턴스를 로드하려는 경우 수행해야 하는 작업이 정의됩니다.</span><span class="sxs-lookup"><span data-stu-id="0f930-143">This setting defines what a host should do if it wants to load an instance that is locked by another host.</span></span> <span data-ttu-id="0f930-144">다음과 같은 옵션이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0f930-144">The following options exist:</span></span>  
  
    -   <span data-ttu-id="0f930-145">`NoRetry`로 설정하는 경우: 로드하려고 다시 시도하지 않고 호스트에 `InstanceLockedException`을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="0f930-145">If set to `NoRetry`: Do not retry the load and return an `InstanceLockedException` to the host.</span></span>  
  
    -   <span data-ttu-id="0f930-146">`BasicRetry`로 설정하는 경우: 계속해서 인스턴스를 로드하려고 시도합니다.</span><span class="sxs-lookup"><span data-stu-id="0f930-146">If set to `BasicRetry`: Keep retrying to load the instance.</span></span> <span data-ttu-id="0f930-147">단순한 선형 알고리즘에 따라 다시 시도가 예약됩니다. 예를 들면 5초 간격으로 다시 시도합니다.</span><span class="sxs-lookup"><span data-stu-id="0f930-147">The retries are scheduled according to a simple linear algorithm (for example, retry every 5 seconds).</span></span>  
  
    -   <span data-ttu-id="0f930-148">`AggressiveRetry`로 설정하는 경우: 계속해서 인스턴스를 로드하려고 시도합니다.</span><span class="sxs-lookup"><span data-stu-id="0f930-148">If set to `AggressiveRetry`: Keep retrying to load the instance.</span></span> <span data-ttu-id="0f930-149">적극적인 지수 백오프 알고리즘에 따라 다시 시도가 예약됩니다.</span><span class="sxs-lookup"><span data-stu-id="0f930-149">The retries are scheduled according to an aggressive exponential back-off algorithm.</span></span>  
  
-   <span data-ttu-id="0f930-150">인코딩 옵션을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="0f930-150">Set the Encoding option.</span></span> <span data-ttu-id="0f930-151">이 설정에 따라 인스턴스 상태가 SQL 워크플로 인스턴스 저장소에 저장되는 방식이 정의됩니다.</span><span class="sxs-lookup"><span data-stu-id="0f930-151">This setting defines how the instance state is stored in the SQL Workflow Instance Store.</span></span> <span data-ttu-id="0f930-152">다음과 같은 옵션이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0f930-152">The following options exist:</span></span>  
  
    -   <span data-ttu-id="0f930-153">인스턴스 상태가 GZip 압축 알고리즘을 사용하여 압축됩니다.</span><span class="sxs-lookup"><span data-stu-id="0f930-153">The instance state is compressed using the GZip compression algorithm.</span></span>  
  
    -   <span data-ttu-id="0f930-154">인스턴스 상태가 압축되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0f930-154">The instance state is not compressed.</span></span>  
  
#### <a name="to-use-this-sample"></a><span data-ttu-id="0f930-155">이 샘플을 사용하려면</span><span class="sxs-lookup"><span data-stu-id="0f930-155">To use this sample</span></span>  
  
1.  <span data-ttu-id="0f930-156">관리자 권한(있는 경우)으로 [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] 명령 프롬프트를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="0f930-156">Open a [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] command prompt as an Administrator if permissions are available.</span></span>  
  
2.  <span data-ttu-id="0f930-157">샘플 디렉터리(\WF\Basic\Persistence\BuiltInConfiguration\CS)로 이동하고 CreateInstanceStore.cmd를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="0f930-157">Navigate to the sample directory (\WF\Basic\Persistence\BuiltInConfiguration\CS) and run CreateInstanceStore.cmd.</span></span>  
  
3.  <span data-ttu-id="0f930-158">관리자 권한이 없는 경우 SQL Server 로그인을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="0f930-158">If Administrator privileges are not available, Create SQL Server login.</span></span> <span data-ttu-id="0f930-159">로 이동 `Security`, **로그인**합니다.</span><span class="sxs-lookup"><span data-stu-id="0f930-159">Go to `Security`, **Logins**.</span></span> <span data-ttu-id="0f930-160">마우스 오른쪽 단추로 클릭 **로그인** 새 로그인을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="0f930-160">Right-click **Logins** and create a new login.</span></span>  
  
4.  <span data-ttu-id="0f930-161">SQL 역할에 ACL 사용자를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="0f930-161">Add your ACL user to SQL role.</span></span> <span data-ttu-id="0f930-162">열기 **데이터베이스**, **InstanceStore**, **보안**합니다.</span><span class="sxs-lookup"><span data-stu-id="0f930-162">Open **Databases**, **InstanceStore**, **Security**.</span></span> <span data-ttu-id="0f930-163">마우스 오른쪽 단추로 클릭 **사용자** 선택 **새 사용자**합니다.</span><span class="sxs-lookup"><span data-stu-id="0f930-163">Right-click **Users** and select **New users**.</span></span> <span data-ttu-id="0f930-164">설정의 **로그인 이름** 이전 단계에서 만든 사용자에 게 합니다.</span><span class="sxs-lookup"><span data-stu-id="0f930-164">Set the **Login name** to the user created in the previous step.</span></span> <span data-ttu-id="0f930-165">데이터베이스 역할 멤버 자격 사용자를 추가 **System.Activities.DurableInstancing.InstanceStoreUsers** (및 기타).</span><span class="sxs-lookup"><span data-stu-id="0f930-165">Add the user to the Database role membership **System.Activities.DurableInstancing.InstanceStoreUsers** (and others).</span></span> <span data-ttu-id="0f930-166">사용자가 이미 있을 수도 있습니다(예: 사용자 dbo).</span><span class="sxs-lookup"><span data-stu-id="0f930-166">Note that the user might exist already (for example, user dbo).</span></span>  
  
5.  <span data-ttu-id="0f930-167">[!INCLUDE[vs2010](../../../../includes/vs2010-md.md)]에서 InstanceStore.sln 파일을 열고 Ctrl 키를 눌러 솔루션을 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="0f930-167">Open the InstanceStore.sln file in [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] and build the solution by pressing CTRL+SHIFT+B.</span></span>  
  
6.  <span data-ttu-id="0f930-168">[!INCLUDE[fileExplorer](../../../../includes/fileexplorer-md.md)], 샘플의 적절 한 bin\debug 디렉터리 (\WF\Basic\Persistence\BuiltInConfiguration\cs\InstanceStore(1 or 2)\bin\debug)로 이동, InstanceStore.exe를 마우스 오른쪽 단추로 클릭 하 고 선택 **관리자권한으로실행**.</span><span class="sxs-lookup"><span data-stu-id="0f930-168">In [!INCLUDE[fileExplorer](../../../../includes/fileexplorer-md.md)], navigate to the sample’s appropriate bin\debug directory (\WF\Basic\Persistence\BuiltInConfiguration\cs\InstanceStore(1 or 2)\bin\debug), right click InstanceStore.exe and select **Run as administrator**.</span></span> <span data-ttu-id="0f930-169">이 샘플은 채널 수신기를 열기 때문에 관리자 권한으로 실행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0f930-169">This sample must be run with administrative privileges because it opens a channel listener.</span></span>  
  
7.  <span data-ttu-id="0f930-170">SQL Server Express 로컬 설치 이외의 데이터베이스에 인스턴스 저장소를 만든 경우에는 샘플에서 데이터베이스 연결 문자열(InstanceStore1 프로젝트의 Program.cs에 있는 `const string ConnectionString` 및 InstanceStore2 프로젝트의 App.config에 있는 `connectionString` 특성)을 업데이트한 다음 샘플을 다시 컴파일해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0f930-170">If you created the instance store in a database other than a local installation of SQL Server Express you must update the database connection string (`const string ConnectionString` in Program.cs of the InstanceStore1 project, and the `connectionString` attribute in App.config of the InstanceStore2 project) in the sample and recompile the sample.</span></span>  
  
#### <a name="to-verify-the-sample-is-running-correctly"></a><span data-ttu-id="0f930-171">샘플이 올바르게 실행되고 있는지 확인하려면</span><span class="sxs-lookup"><span data-stu-id="0f930-171">To verify the sample is running correctly</span></span>  
  
1.  <span data-ttu-id="0f930-172">샘플이 실행되고 있는 동안 SQL Server Management Studio를 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="0f930-172">While the sample is running, start SQL Server Management Studio.</span></span>  
  
2.  <span data-ttu-id="0f930-173">에 **개체 탐색기**선택, **데이터베이스**, **InstanceStore**, **테이블**, 차례로  **System.Activities.DurableInstancing.InstanceTable**합니다.</span><span class="sxs-lookup"><span data-stu-id="0f930-173">In the **Object Explorer**, select **Databases**, **InstanceStore**, **Tables**, and then **System.Activities.DurableInstancing.InstanceTable**.</span></span>  
  
3.  <span data-ttu-id="0f930-174">마우스 오른쪽 단추로 클릭 **인스턴스 테이블** 선택 **상위 1000 개 행 선택**합니다.</span><span class="sxs-lookup"><span data-stu-id="0f930-174">Right click **InstanceTable** and select **Select Top 1000 Rows**.</span></span>  
  
4.  <span data-ttu-id="0f930-175">새 항목이 있는지와 없는지 확인는 **잠금 만료** 5 초 간격으로 변경 (작업 표시줄의 클릭 **Execute** 단추를 쿼리를 새로 고칠).</span><span class="sxs-lookup"><span data-stu-id="0f930-175">Observe that there is a new entry and that the **Lock Expiration** changes every 5 seconds, (click the taskbar’s **Execute** button to refresh the query).</span></span> <span data-ttu-id="0f930-176">이 설정의 결과 **호스트 잠금 갱신 기간** 5입니다.</span><span class="sxs-lookup"><span data-stu-id="0f930-176">This is a consequence of setting the **Host Lock Renewal Period** to 5.</span></span>  
  
5.  <span data-ttu-id="0f930-177">계산이 완료된 후 인스턴스 테이블의 항목이 제거되었는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="0f930-177">Observe after the counting completes, that the entry in the instance table is removed.</span></span> <span data-ttu-id="0f930-178">이 설정의 **인스턴스 완료 동작** 를 **DeleteAll**합니다.</span><span class="sxs-lookup"><span data-stu-id="0f930-178">This is a consequence of setting **Instance Completion Action** to **DeleteAll**.</span></span>  
  
6.  <span data-ttu-id="0f930-179">Enter 키를 눌러 워크플로 호스트 응용 프로그램을 종료 하는 **LockOwnersTable** 삭제 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0f930-179">Press ENTER to terminate the workflow host application and observe that the **LockOwnersTable** is deleted.</span></span>  
  
#### <a name="to-uninstall-the-sample"></a><span data-ttu-id="0f930-180">샘플을 제거하려면</span><span class="sxs-lookup"><span data-stu-id="0f930-180">To uninstall the sample</span></span>  
  
1.  <span data-ttu-id="0f930-181">샘플 디렉터리(\WF\Basic\Persistence\BuiltInConfiguration)에서 RemoveInstanceStore.cmd를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="0f930-181">Run RemoveInstanceStore.cmd in the sample directory (\WF\Basic\Persistence\BuiltInConfiguration).</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="0f930-182">컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0f930-182">The samples may already be installed on your computer.</span></span> <span data-ttu-id="0f930-183">계속하기 전에 다음(기본) 디렉터리를 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="0f930-183">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="0f930-184">이 디렉터리가 없으면 [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4(.NET Framework 4용 WCF(Windows Communication Foundation) 및 WF(Windows Workflow Foundation) 샘플)](http://go.microsoft.com/fwlink/?LinkId=150780) 로 이동하여 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 및 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플을 모두 다운로드하세요.</span><span class="sxs-lookup"><span data-stu-id="0f930-184">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="0f930-185">이 샘플은 다음 디렉터리에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0f930-185">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Persistence\BuiltInConfiguration`  
  
## <a name="see-also"></a><span data-ttu-id="0f930-186">참고 항목</span><span class="sxs-lookup"><span data-stu-id="0f930-186">See Also</span></span>  
 [<span data-ttu-id="0f930-187">AppFabric 호스팅 및 지 속성 샘플</span><span class="sxs-lookup"><span data-stu-id="0f930-187">AppFabric Hosting and Persistence Samples</span></span>](http://go.microsoft.com/fwlink/?LinkId=193961)
