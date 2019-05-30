---
title: WorkflowIdentity 및 버전 관리 사용
ms.date: 03/30/2017
ms.assetid: b8451735-8046-478f-912b-40870a6c0c3a
ms.openlocfilehash: acf2b2c9502487c8bc8960f2a5625db94c31945f
ms.sourcegitcommit: 4735bb7741555bcb870d7b42964d3774f4897a6e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/30/2019
ms.locfileid: "66380125"
---
# <a name="using-workflowidentity-and-versioning"></a><span data-ttu-id="dbd98-102">WorkflowIdentity 및 버전 관리 사용</span><span class="sxs-lookup"><span data-stu-id="dbd98-102">Using WorkflowIdentity and Versioning</span></span>
<span data-ttu-id="dbd98-103"><xref:System.Activities.WorkflowIdentity>는 워크플로 응용 프로그램 개발자에게 이름 및 <xref:System.Version>을 워크플로 정의에 연결하는 방법을 제공하며, 이러한 정보는 지속형 워크플로 인스턴스와 연결됩니다.</span><span class="sxs-lookup"><span data-stu-id="dbd98-103"><xref:System.Activities.WorkflowIdentity> provides a way for workflow application developers to associate a name and a <xref:System.Version> with a workflow definition, and for this information to be associated with a persisted workflow instance.</span></span> <span data-ttu-id="dbd98-104">이 ID 정보는 워크플로 응용 프로그램 개발자가 여러 버전의 워크플로 정의를 side-by-side로 실행하는 경우와 같은 시나리오를 가능하도록 하는 데 사용될 수 있으며 동적 업데이트와 같은 다른 기능의 토대를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="dbd98-104">This identity information can be used by workflow application developers to enable scenarios such as side-by-side execution of multiple versions of a workflow definition, and provides the cornerstone for other functionality such as dynamic update.</span></span> <span data-ttu-id="dbd98-105">이 항목에서는 <xref:System.Activities.WorkflowIdentity> 호스팅과 함께 <xref:System.Activities.WorkflowApplication>를 사용하는 방법을 간단하게 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="dbd98-105">This topic provides as overview of using <xref:System.Activities.WorkflowIdentity> with <xref:System.Activities.WorkflowApplication> hosting.</span></span> <span data-ttu-id="dbd98-106">워크플로 서비스에서 워크플로 정의의 side-by-side-실행 정보를 참조 하세요 [WorkflowServiceHost에서 Side-by-side 버전 관리](../wcf/feature-details/side-by-side-versioning-in-workflowservicehost.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="dbd98-106">For information on side-by-side execution of workflow definitions in a workflow service, see [Side by Side Versioning in WorkflowServiceHost](../wcf/feature-details/side-by-side-versioning-in-workflowservicehost.md).</span></span> <span data-ttu-id="dbd98-107">동적 업데이트에 대 한 자세한 내용은 [동적 업데이트](dynamic-update.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="dbd98-107">For information on dynamic update, see [Dynamic Update](dynamic-update.md).</span></span>  
  
## <a name="in-this-topic"></a><span data-ttu-id="dbd98-108">항목 내용</span><span class="sxs-lookup"><span data-stu-id="dbd98-108">In this topic</span></span>  
  
- [<span data-ttu-id="dbd98-109">WorkflowIdentity 사용</span><span class="sxs-lookup"><span data-stu-id="dbd98-109">Using WorkflowIdentity</span></span>](using-workflowidentity-and-versioning.md#UsingWorkflowIdentity)  
  
    - [<span data-ttu-id="dbd98-110">WorkflowIdentity를 사용한 side-by-side-실행</span><span class="sxs-lookup"><span data-stu-id="dbd98-110">Side-by-side Execution using WorkflowIdentity</span></span>](using-workflowidentity-and-versioning.md#SxS)  
  
- [<span data-ttu-id="dbd98-111">워크플로 버전 관리를 지원 하기 위해.NET Framework 4 지 속성 데이터베이스 업그레이드</span><span class="sxs-lookup"><span data-stu-id="dbd98-111">Upgrading .NET Framework 4 Persistence Databases to Support Workflow Versioning</span></span>](using-workflowidentity-and-versioning.md#UpdatingWF4PersistenceDatabases)  
  
    - [<span data-ttu-id="dbd98-112">데이터베이스 스키마를 업그레이드 하려면</span><span class="sxs-lookup"><span data-stu-id="dbd98-112">To upgrade the database schema</span></span>](using-workflowidentity-and-versioning.md#ToUpgrade)  
  
## <a name="UsingWorkflowIdentity"></a> <span data-ttu-id="dbd98-113">WorkflowIdentity 사용</span><span class="sxs-lookup"><span data-stu-id="dbd98-113">Using WorkflowIdentity</span></span>  
 <span data-ttu-id="dbd98-114"><xref:System.Activities.WorkflowIdentity>를 사용하려면 인스턴스를 만들어 구성한 다음 <xref:System.Activities.WorkflowApplication> 인스턴스에 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="dbd98-114">To use <xref:System.Activities.WorkflowIdentity>, create an instance, configure it, and associate it with a <xref:System.Activities.WorkflowApplication> instance.</span></span> <span data-ttu-id="dbd98-115"><xref:System.Activities.WorkflowIdentity> 인스턴스에는 세 가지 식별 정보가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="dbd98-115">A <xref:System.Activities.WorkflowIdentity> instance contains three identifying pieces of information.</span></span> <span data-ttu-id="dbd98-116">필수 요소인 <xref:System.Activities.WorkflowIdentity.Name%2A> 및 <xref:System.Activities.WorkflowIdentity.Version%2A>에는 이름과 <xref:System.Version>이 포함되며, 선택적인 <xref:System.Activities.WorkflowIdentity.Package%2A>는 어셈블리 이름 등의 정보나 원하는 다른 정보를 포함하는 추가 문자열을 지정하는 데 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dbd98-116"><xref:System.Activities.WorkflowIdentity.Name%2A> and <xref:System.Activities.WorkflowIdentity.Version%2A> contain a name and a <xref:System.Version> and are required, and <xref:System.Activities.WorkflowIdentity.Package%2A> is optional and can be used to specify an additional string containing information such as assembly name or other desired information.</span></span> <span data-ttu-id="dbd98-117">세 개의 속성 중 하나라도 다른 <xref:System.Activities.WorkflowIdentity>와 다르면 <xref:System.Activities.WorkflowIdentity>가 고유한 것으로 간주됩니다.</span><span class="sxs-lookup"><span data-stu-id="dbd98-117">A <xref:System.Activities.WorkflowIdentity> is unique if any of its three properties are different from another <xref:System.Activities.WorkflowIdentity>.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="dbd98-118"><xref:System.Activities.WorkflowIdentity>에는 어떠한 PII(개인적으로 식별할 수 있는 정보)도 포함해서는 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="dbd98-118">A <xref:System.Activities.WorkflowIdentity> should not contain any personally identifiable information (PII).</span></span> <span data-ttu-id="dbd98-119">인스턴스를 만드는 데 사용되는 <xref:System.Activities.WorkflowIdentity>에 대한 정보는 활동 수명 주기의 여러 시점에 런타임에 의해 구성된 추적 서비스로 내보내집니다.</span><span class="sxs-lookup"><span data-stu-id="dbd98-119">Information about the <xref:System.Activities.WorkflowIdentity> used to create an instance is emitted to any configured tracking services at several different points of the activity life-cycle by the runtime.</span></span> <span data-ttu-id="dbd98-120">WF 추적 기능에는 중요한 사용자 데이터인 PII를 숨기는 메커니즘이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="dbd98-120">WF Tracking does not have any mechanism to hide PII (sensitive user data).</span></span> <span data-ttu-id="dbd98-121">따라서 <xref:System.Activities.WorkflowIdentity> 인스턴스는 런타임에 의해 추적 레코드에 내보내져 추적 레코드를 볼 수 있는 권한이 있는 사람에게 표시될 수 있기 때문에 이 인스턴스에 PII 데이터가 포함되어서는 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="dbd98-121">Therefore, a <xref:System.Activities.WorkflowIdentity> instance should not contain any PII data as it will be emitted by the runtime in tracking records and may be visible to anyone with access to view the tracking records.</span></span>  
  
 <span data-ttu-id="dbd98-122">다음 예제에서는 <xref:System.Activities.WorkflowIdentity>를 만든 후 `MortgageWorkflow` 워크플로 정의를 사용하여 만든 워크플로 인스턴스에 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="dbd98-122">In the following example, a <xref:System.Activities.WorkflowIdentity> is created and associated with an instance of a workflow created using a `MortgageWorkflow` workflow definition.</span></span>  
  
```csharp  
WorkflowIdentity identityV1 = new WorkflowIdentity  
{  
    Name = "MortgageWorkflow v1",  
    Version = new Version(1, 0, 0, 0)  
};  
  
WorkflowApplication wfApp = new WorkflowApplication(new MortgageWorkflow(), identity);  
  
// Configure the WorkflowApplication with persistence and desired workflow event handlers.  
ConfigureWorkflowApplication(wfApp);  
  
// Run the workflow.  
wfApp.Run();  
```  
  
 <span data-ttu-id="dbd98-123">워크플로를 다시 로드하고 다시 시작할 때는 지속형 워크플로 인스턴스의 <xref:System.Activities.WorkflowIdentity>와 일치하도록 구성된 <xref:System.Activities.WorkflowIdentity>를 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="dbd98-123">When reloading and resuming a workflow, a <xref:System.Activities.WorkflowIdentity> that is configured to match the <xref:System.Activities.WorkflowIdentity> of the persisted workflow instance must be used.</span></span>  
  
```csharp  
WorkflowApplication wfApp = new WorkflowApplication(new MortgageWorkflow(), identityV1);  
  
// Configure the WorkflowApplication with persistence and desired workflow event handlers.  
ConfigureWorkflowApplication(wfApp);  
  
// Load the workflow.  
wfApp.Load(instanceId);  
  
// Resume the workflow...  
```  
  
 <span data-ttu-id="dbd98-124">워크플로 인스턴스를 다시 로드할 때 사용된 <xref:System.Activities.WorkflowIdentity>가 유지된 <xref:System.Activities.WorkflowIdentity>와 일치하지 않으면 <xref:System.Activities.VersionMismatchException>이 throw됩니다.</span><span class="sxs-lookup"><span data-stu-id="dbd98-124">If the <xref:System.Activities.WorkflowIdentity> used when reloading the workflow instance does not match the persisted <xref:System.Activities.WorkflowIdentity>, a <xref:System.Activities.VersionMismatchException> is thrown.</span></span> <span data-ttu-id="dbd98-125">다음 예제에서는 이전 예제에서 유지된 `MortgageWorkflow` 인스턴스에 대해 로드를 시도합니다.</span><span class="sxs-lookup"><span data-stu-id="dbd98-125">In the following example a load attempt is made on the `MortgageWorkflow` instance that was persisted in the previous example.</span></span> <span data-ttu-id="dbd98-126">이 로드를 시도하는 데는 지속형 인스턴스와 일치하지 않는 융자 워크플로의 새로운 버전에 맞게 구성된 <xref:System.Activities.WorkflowIdentity>가 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="dbd98-126">This load attempt is made using a <xref:System.Activities.WorkflowIdentity> configured for a newer version of the mortgage workflow that does not match the persisted instance.</span></span>  
  
```csharp  
WorkflowApplication wfApp = new WorkflowApplication(new MortgageWorkflow_v2(), identityV2);  
  
// Configure the WorkflowApplication with persistence and desired workflow event handlers.  
ConfigureWorkflowApplication(wfApp);  
  
// Attempt to load the workflow instance.  
wfApp.Load(instanceId);  
  
// Resume the workflow...  
```  
  
 <span data-ttu-id="dbd98-127">앞의 코드가 실행되면 다음 <xref:System.Activities.VersionMismatchException>이 throw됩니다.</span><span class="sxs-lookup"><span data-stu-id="dbd98-127">When the previous code is executed, the following <xref:System.Activities.VersionMismatchException> is thrown.</span></span>  
  
 <span data-ttu-id="dbd98-128">**WorkflowIdentity ('MortgageWorkflow v1; 버전 1.0.0.0' =) 로드 된 인스턴스의 WorkflowIdentity을 일치 하지 않습니다 ('MortgageWorkflow v2; 버전 2.0.0.0 ') 제공된 된 워크플로 정의입니다. 인스턴스가 다른 정의 사용 하 여 로드 하거나 동적 업데이트를 사용 하 여 업데이트 합니다.**</span><span class="sxs-lookup"><span data-stu-id="dbd98-128">**The WorkflowIdentity ('MortgageWorkflow v1; Version=1.0.0.0') of the loaded instance does not match the WorkflowIdentity ('MortgageWorkflow v2; Version=2.0.0.0') of the provided workflow definition. The instance can be loaded using a different definition, or updated using Dynamic Update.**</span></span>  
### <a name="SxS"></a> <span data-ttu-id="dbd98-129">WorkflowIdentity를 사용한 side-by-side-실행</span><span class="sxs-lookup"><span data-stu-id="dbd98-129">Side-by-side Execution using WorkflowIdentity</span></span>  
 <span data-ttu-id="dbd98-130"><xref:System.Activities.WorkflowIdentity>를 사용하면 여러 버전의 워크플로를 손쉽게 side-by-side로 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dbd98-130"><xref:System.Activities.WorkflowIdentity> can be used to facilitate the execution of multiple versions of a workflow side-by-side.</span></span> <span data-ttu-id="dbd98-131">한 가지 일반적인 시나리오는 장기 실행 워크플로에 대한 비즈니스 요구 사항을 변경하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="dbd98-131">One common scenario is changing business requirements on a long-running workflow.</span></span> <span data-ttu-id="dbd98-132">업데이트된 버전이 배포될 때 여러 워크플로 인스턴스가 실행 중일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dbd98-132">Many instances of a workflow could be running when an updated version is deployed.</span></span> <span data-ttu-id="dbd98-133">새 인스턴스를 시작할 때 업데이트된 워크플로 정의를 사용하도록 호스트 응용 프로그램을 구성할 수 있으며, 호스트 응용 프로그램에서는 인스턴스를 다시 시작할 때 올바른 워크플로 정의를 제공해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="dbd98-133">The host application can be configured to use the updated workflow definition when starting new instances, and it is the responsibility of the host application to provide the correct workflow definition when resuming instances.</span></span> <span data-ttu-id="dbd98-134"><xref:System.Activities.WorkflowIdentity>를 사용하면 워크플로 인스턴스를 다시 시작할 때 일치하는 워크플로 정의를 식별하고 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dbd98-134"><xref:System.Activities.WorkflowIdentity> can be used to identify and supply the matching workflow definition when resuming workflow instances.</span></span>  
  
 <span data-ttu-id="dbd98-135">지속형 워크플로 인스턴스의 <xref:System.Activities.WorkflowIdentity>를 검색하려면 <xref:System.Activities.WorkflowApplication.GetInstance%2A> 메서드를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="dbd98-135">To retrieve the <xref:System.Activities.WorkflowIdentity> of a persisted workflow instance, the <xref:System.Activities.WorkflowApplication.GetInstance%2A> method is used.</span></span> <span data-ttu-id="dbd98-136"><xref:System.Activities.WorkflowApplication.GetInstance%2A> 메서드는 지속형 워크플로 인스턴스의 <xref:System.Activities.WorkflowApplication.Id%2A>와 지속형 인스턴스가 포함된 <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore>를 매개 변수로 받아 <xref:System.Activities.WorkflowApplicationInstance>를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="dbd98-136">The <xref:System.Activities.WorkflowApplication.GetInstance%2A> method takes the <xref:System.Activities.WorkflowApplication.Id%2A> of the persisted workflow instance and the <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore> that contains the persisted instance and returns a <xref:System.Activities.WorkflowApplicationInstance>.</span></span> <span data-ttu-id="dbd98-137"><xref:System.Activities.WorkflowApplicationInstance>에는 지속형 워크플로 인스턴스에 연결된 <xref:System.Activities.WorkflowIdentity>를 포함하여 지속형 워크플로 인스턴스에 대한 정보가 들어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dbd98-137">A <xref:System.Activities.WorkflowApplicationInstance> contains information about a persisted workflow instance, including its associated <xref:System.Activities.WorkflowIdentity>.</span></span> <span data-ttu-id="dbd98-138">이 연결된 <xref:System.Activities.WorkflowIdentity>는 호스트에서 워크플로 인스턴스를 로드하고 다시 시작할 때 올바른 워크플로 정의를 제공하는 데 사용될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dbd98-138">This associated <xref:System.Activities.WorkflowIdentity> can be used by the host to supply the correct workflow definition when loading and resuming the workflow instance.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="dbd98-139"><xref:System.Activities.WorkflowIdentity>는 null일 수 있으며, 이 값은 호스트에서 적절한 워크플로 정의에 <xref:System.Activities.WorkflowIdentity>가 연결되지 않은 상태에서 유지된 인스턴스를 매핑하는 데 사용될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dbd98-139">A null <xref:System.Activities.WorkflowIdentity> is valid, and can be used by the host to map instances that were persisted with no associated <xref:System.Activities.WorkflowIdentity> to the proper workflow definition.</span></span> <span data-ttu-id="dbd98-140">이는 워크플로 응용 프로그램이 원래 워크플로 버전 관리를 사용하여 작성되지 않은 경우나 응용 프로그램이 [!INCLUDE[netfx40_short](../../../includes/netfx40-short-md.md)]에서 업그레이드된 경우에 해당될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dbd98-140">This scenario can occur when a workflow application was not initially written with workflow versioning, or when an application is upgraded from [!INCLUDE[netfx40_short](../../../includes/netfx40-short-md.md)].</span></span> <span data-ttu-id="dbd98-141">자세한 내용은 [.NET Framework 4 지 속성 데이터베이스 업그레이드 워크플로 버전 관리 지원](using-workflowidentity-and-versioning.md#UpdatingWF4PersistenceDatabases)합니다.</span><span class="sxs-lookup"><span data-stu-id="dbd98-141">For more information, see [Upgrading .NET Framework 4 Persistence Databases to Support Workflow Versioning](using-workflowidentity-and-versioning.md#UpdatingWF4PersistenceDatabases).</span></span>  
  
 <span data-ttu-id="dbd98-142">다음 예제에서는 `Dictionary<WorkflowIdentity, Activity>` 연결할 때 사용 됩니다 <xref:System.Activities.WorkflowIdentity> 가 일치 하는 워크플로 정 및 워크플로 사용 하 여 인스턴스를 사용 하 여 시작 합니다 `MortgageWorkflow` 연결 된 워크플로 정의 `identityV1` <xref:System.Activities.WorkflowIdentity>.</span><span class="sxs-lookup"><span data-stu-id="dbd98-142">In the following example a `Dictionary<WorkflowIdentity, Activity>` is used to associate <xref:System.Activities.WorkflowIdentity> instances with their matching workflow definitions, and a workflow is started using the `MortgageWorkflow` workflow definition, which is associated with the `identityV1` <xref:System.Activities.WorkflowIdentity>.</span></span>  
  
```csharp  
WorkflowIdentity identityV1 = new WorkflowIdentity  
{  
    Name = "MortgageWorkflow v1",  
    Version = new Version(1, 0, 0, 0)  
};  
  
WorkflowIdentity identityV2 = new WorkflowIdentity  
{  
    Name = "MortgageWorkflow v2",  
    Version = new Version(2, 0, 0, 0)  
};  
  
Dictionary<WorkflowIdentity, Activity> WorkflowVersionMap = new Dictionary<WorkflowIdentity, Activity>();  
WorkflowVersionMap.Add(identityV1, new MortgageWorkflow());  
WorkflowVersionMap.Add(identityV2, new MortgageWorkflow_v2());  
  
WorkflowApplication wfApp = new WorkflowApplication(new MortgageWorkflow(), identityV1);  
  
// Configure the WorkflowApplication with persistence and desired workflow event handlers.  
ConfigureWorkflowApplication(wfApp);  
  
// Run the workflow.  
wfApp.Run();  
```  
  
 <span data-ttu-id="dbd98-143">다음 예제에서는 <xref:System.Activities.WorkflowApplication.GetInstance%2A>를 호출하여 이전 예제의 지속형 워크플로 인스턴스에 대한 정보를 검색하고, 유지된 <xref:System.Activities.WorkflowIdentity> 정보를 사용하여 일치하는 워크플로 정의를 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="dbd98-143">In the following example, information about the persisted workflow instance from the previous example is retrieved by calling <xref:System.Activities.WorkflowApplication.GetInstance%2A>, and the persisted <xref:System.Activities.WorkflowIdentity> information is used to retrieve the matching workflow definition.</span></span> <span data-ttu-id="dbd98-144">이 정보는 <xref:System.Activities.WorkflowApplication>을 구성하는 데 사용되며, 그런 다음 워크플로가 로드됩니다.</span><span class="sxs-lookup"><span data-stu-id="dbd98-144">This information is used to configure the <xref:System.Activities.WorkflowApplication>, and then the workflow is loaded.</span></span> <span data-ttu-id="dbd98-145"><xref:System.Activities.WorkflowApplication.Load%2A>를 사용하는 <xref:System.Activities.WorkflowApplicationInstance> 오버로드가 사용되므로 <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore>에서 구성된 <xref:System.Activities.WorkflowApplicationInstance>가 <xref:System.Activities.WorkflowApplication>에서 사용되며, 따라서 <xref:System.Activities.WorkflowApplication.InstanceStore%2A> 속성을 구성할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="dbd98-145">Note that because the <xref:System.Activities.WorkflowApplication.Load%2A> overload that takes the <xref:System.Activities.WorkflowApplicationInstance> is used, the <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore> that was configured on the <xref:System.Activities.WorkflowApplicationInstance> is used by the <xref:System.Activities.WorkflowApplication> and therefore its <xref:System.Activities.WorkflowApplication.InstanceStore%2A> property does not need to be configured.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="dbd98-146"><xref:System.Activities.WorkflowApplication.InstanceStore%2A> 속성을 설정할 경우에는 <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore>에 사용된 <xref:System.Activities.WorkflowApplicationInstance> 인스턴스와 동일하게 설정해야 하며, 그렇지 않으면 <xref:System.ArgumentException>이라는 메시지와 함께 `The instance is configured with a different InstanceStore than this WorkflowApplication.`이 throw됩니다.</span><span class="sxs-lookup"><span data-stu-id="dbd98-146">If the <xref:System.Activities.WorkflowApplication.InstanceStore%2A> property is set, it must be set with the same <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore> instance used by the <xref:System.Activities.WorkflowApplicationInstance> or else an <xref:System.ArgumentException> will be thrown with the following message: `The instance is configured with a different InstanceStore than this WorkflowApplication.`.</span></span>  
  
```csharp  
// Get the WorkflowApplicationInstance of the desired workflow from the specified  
// SqlWorkflowInstanceStore.  
WorkflowApplicationInstance instance = WorkflowApplication.GetInstance(instanceId, store);  
  
// Use the persisted WorkflowIdentity to retrieve the correct workflow  
// definition from the dictionary.  
Activity definition = WorkflowVersionMap[instance.DefinitionIdentity];  
  
WorkflowApplication wfApp = new WorkflowApplication(definition, instance.DefinitionIdentity);  
  
// Configure the WorkflowApplication with persistence and desired workflow event handlers.  
ConfigureWorkflowApplication(wfApp);  
  
// Load the persisted workflow instance.  
wfApp.Load(instance);  
  
// Resume the workflow...  
```  
  
## <a name="UpdatingWF4PersistenceDatabases"></a> <span data-ttu-id="dbd98-147">워크플로 버전 관리를 지원 하기 위해.NET Framework 4 지 속성 데이터베이스 업그레이드</span><span class="sxs-lookup"><span data-stu-id="dbd98-147">Upgrading .NET Framework 4 Persistence Databases to Support Workflow Versioning</span></span>  
 <span data-ttu-id="dbd98-148">[!INCLUDE[netfx40_short](../../../includes/netfx40-short-md.md)] 데이터베이스 스크립트를 사용하여 만들어진 지속성 데이터베이스를 업그레이드하기 위해 SqlWorkflowInstanceStoreSchemaUpgrade.sql 데이터베이스 스크립트가 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="dbd98-148">A SqlWorkflowInstanceStoreSchemaUpgrade.sql database script is provided to upgrade persistence databases created using the [!INCLUDE[netfx40_short](../../../includes/netfx40-short-md.md)] database scripts.</span></span> <span data-ttu-id="dbd98-149">이 스크립트는.NET Framework 4.5에서 도입 된 새 버전 관리 기능을 지원 하도록 데이터베이스를 업데이트 합니다.</span><span class="sxs-lookup"><span data-stu-id="dbd98-149">This script updates the databases to support the new versioning capabilities introduced in .NET Framework 4.5.</span></span> <span data-ttu-id="dbd98-150">데이터베이스의 지속형 워크플로 인스턴스는 기본 버전 관리 값이 제공 받으며, side-by-side 실행 및 동적 업데이트에 참여할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dbd98-150">Any persisted workflow instances in the databases are given default versioning values, and can then participate in side-by-side execution and dynamic update.</span></span>  
  
 <span data-ttu-id="dbd98-151">.NET Framework 4.5 워크플로 응용 프로그램 업그레이드 되지 않았습니다. 제공된 된 스크립트를 사용 하 여 지 속성 데이터베이스에서 새 버전 관리 기능을 사용 하는 지 속성 작업을 시도 하는 경우는 <xref:System.Runtime.DurableInstancing.InstancePersistenceCommandException> 유사한 메시지를 사용 하 여 throw 되는 다음 메시지입니다.</span><span class="sxs-lookup"><span data-stu-id="dbd98-151">If a .NET Framework 4.5 workflow application attempts any persistence operations that use the new versioning features on a persistence database which has not been upgraded using the provided script, an <xref:System.Runtime.DurableInstancing.InstancePersistenceCommandException> is thrown with a message similar to the following message.</span></span>  
  
 <span data-ttu-id="dbd98-152">**SqlWorkflowInstanceStore의 데이터베이스 버전이 '4.0.0.0'입니다. InstancePersistenceCommand 'System.Activities.DurableInstancing.CreateWorkflowOwnerWithIdentityCommand'을(를) 이 데이터베이스 버전에 대해 실행할 수 없습니다.  '4.5.0.0' 데이터베이스를 업그레이드 하세요.**</span><span class="sxs-lookup"><span data-stu-id="dbd98-152">**The SqlWorkflowInstanceStore has a database version of '4.0.0.0'. InstancePersistenceCommand 'System.Activities.DurableInstancing.CreateWorkflowOwnerWithIdentityCommand' cannot be run against this database version.  Please upgrade the database to '4.5.0.0'.**</span></span>  
### <a name="ToUpgrade"></a> <span data-ttu-id="dbd98-153">데이터베이스 스키마를 업그레이드 하려면</span><span class="sxs-lookup"><span data-stu-id="dbd98-153">To upgrade the database schema</span></span>  
  
1. <span data-ttu-id="dbd98-154">SQL Server Management Studio를 열고 예를 들어 지 속성 데이터베이스 서버에 연결 **. \SQLEXPRESS**합니다.</span><span class="sxs-lookup"><span data-stu-id="dbd98-154">Open SQL Server Management Studio and connect to the persistence database server, for example **.\SQLEXPRESS**.</span></span>  
  
2. <span data-ttu-id="dbd98-155">선택 **엽니다**를 **파일** 에서 합니다 **파일** 메뉴.</span><span class="sxs-lookup"><span data-stu-id="dbd98-155">Choose **Open**, **File** from the **File** menu.</span></span> <span data-ttu-id="dbd98-156">`C:\Windows\Microsoft.NET\Framework\4.0.30319\sql\en` 폴더로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="dbd98-156">Browse to the following folder: `C:\Windows\Microsoft.NET\Framework\4.0.30319\sql\en`</span></span>  
  
3. <span data-ttu-id="dbd98-157">선택 **SqlWorkflowInstanceStoreSchemaUpgrade.sql** 누릅니다 **오픈**합니다.</span><span class="sxs-lookup"><span data-stu-id="dbd98-157">Select **SqlWorkflowInstanceStoreSchemaUpgrade.sql** and click **Open**.</span></span>  
  
4. <span data-ttu-id="dbd98-158">지 속성 데이터베이스의 이름을 선택 합니다 **사용 가능한 데이터베이스** 드롭 다운 합니다.</span><span class="sxs-lookup"><span data-stu-id="dbd98-158">Select the name of the persistence database in the **Available Databases** drop-down.</span></span>  
  
5. <span data-ttu-id="dbd98-159">선택할 **Execute** 에서 합니다 **쿼리** 메뉴.</span><span class="sxs-lookup"><span data-stu-id="dbd98-159">Choose **Execute** from the **Query** menu.</span></span>  
  
 <span data-ttu-id="dbd98-160">쿼리가 완료되면 데이터베이스 스키마가 업그레이드되고 지속형 워크플로 인스턴스에 할당된 기본 워크플로 ID를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dbd98-160">When the query completes, the database schema is upgraded, and if desired, you can view the default workflow identity that was assigned to the persisted workflow instances.</span></span> <span data-ttu-id="dbd98-161">지 속성 데이터베이스를 확장 합니다 **데이터베이스** 노드의 **개체 탐색기**를 펼친 다음를 **뷰** 노드.</span><span class="sxs-lookup"><span data-stu-id="dbd98-161">Expand your persistence database in the **Databases** node of the **Object Explorer**, and then expand the **Views** node.</span></span> <span data-ttu-id="dbd98-162">마우스 오른쪽 단추로 클릭 **System.Activities.DurableInstancing.Instances** 선택한 **상위 1000 개의 행 선택**합니다.</span><span class="sxs-lookup"><span data-stu-id="dbd98-162">Right-click **System.Activities.DurableInstancing.Instances** and choose **Select Top 1000 Rows**.</span></span> <span data-ttu-id="dbd98-163">열의 끝으로 스크롤하여 뷰에 추가 하는 6 개의 추가 열은: **IdentityName**, **IdentityPackage**를 **빌드**를 **주요**를 **부**, 및 **수정**.</span><span class="sxs-lookup"><span data-stu-id="dbd98-163">Scroll to end of the columns and note that there are six additional columns added to the view: **IdentityName**, **IdentityPackage**, **Build**, **Major**, **Minor**, and **Revision**.</span></span> <span data-ttu-id="dbd98-164">지속형된 워크플로의의 값이 포함 됩니다 **NULL** 이러한 필드에 대 한 null 워크플로 id를 나타내는입니다.</span><span class="sxs-lookup"><span data-stu-id="dbd98-164">Any persisted workflows will have a value of **NULL** for these fields, representing a null workflow identity.</span></span>
