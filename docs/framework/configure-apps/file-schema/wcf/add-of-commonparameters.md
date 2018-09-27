---
title: '&lt;commonParameters&gt;의 &lt;add&gt;'
ms.date: 03/30/2017
ms.assetid: 3713bf25-20c8-455f-bb85-de46b6487932
ms.openlocfilehash: 93e82aa3bd44a747d1e85986c51c21522d709bd0
ms.sourcegitcommit: fb78d8abbdb87144a3872cf154930157090dd933
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/27/2018
ms.locfileid: "47402554"
---
# <a name="ltaddgt-of-ltcommonparametersgt"></a><span data-ttu-id="b2387-102">&lt;commonParameters&gt;의 &lt;add&gt;</span><span class="sxs-lookup"><span data-stu-id="b2387-102">&lt;add&gt; of &lt;commonParameters&gt;</span></span>
<span data-ttu-id="b2387-103">여러 서비스에서 전역적으로 사용되는 매개 변수의 이름-값 쌍을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="b2387-103">Specifies a name-value pair of parameters that are used globally across multiple services.</span></span> <span data-ttu-id="b2387-104">일반적으로 이 매개 변수에는 영속 서비스에서 공유할 수 있는 데이터베이스 연결 문자열이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="b2387-104">Typically this parameter includes the database connection string that might be shared by durable services.</span></span>  
  
 <span data-ttu-id="b2387-105">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="b2387-105">\<system.ServiceModel></span></span>  
<span data-ttu-id="b2387-106">\<동작 ></span><span class="sxs-lookup"><span data-stu-id="b2387-106">\<behaviors></span></span>  
<span data-ttu-id="b2387-107">\<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="b2387-107">\<serviceBehaviors></span></span>  
<span data-ttu-id="b2387-108">\<동작 ></span><span class="sxs-lookup"><span data-stu-id="b2387-108">\<behavior></span></span>  
<span data-ttu-id="b2387-109">\<workflowRuntime></span><span class="sxs-lookup"><span data-stu-id="b2387-109">\<workflowRuntime></span></span>  
<span data-ttu-id="b2387-110">\<commonParameters></span><span class="sxs-lookup"><span data-stu-id="b2387-110">\<commonParameters></span></span>  
<span data-ttu-id="b2387-111">\<add></span><span class="sxs-lookup"><span data-stu-id="b2387-111">\<add></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b2387-112">구문</span><span class="sxs-lookup"><span data-stu-id="b2387-112">Syntax</span></span>  
  
```xml  
<workflowRuntime>  
   <commonParameters>  
      <add name="String" value="String" />  
   </commonParameters>  
</workflowRuntime>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b2387-113">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="b2387-113">Attributes and Elements</span></span>  
 <span data-ttu-id="b2387-114">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="b2387-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b2387-115">특성</span><span class="sxs-lookup"><span data-stu-id="b2387-115">Attributes</span></span>  
  
|<span data-ttu-id="b2387-116">특성</span><span class="sxs-lookup"><span data-stu-id="b2387-116">Attribute</span></span>|<span data-ttu-id="b2387-117">설명</span><span class="sxs-lookup"><span data-stu-id="b2387-117">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="b2387-118">name</span><span class="sxs-lookup"><span data-stu-id="b2387-118">name</span></span>|<span data-ttu-id="b2387-119">서비스에 지정한 매개 변수 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="b2387-119">The name of the parameter specified for a service.</span></span>|  
|<span data-ttu-id="b2387-120">값</span><span class="sxs-lookup"><span data-stu-id="b2387-120">value</span></span>|<span data-ttu-id="b2387-121">서비스에 지정한 매개 변수 값입니다.</span><span class="sxs-lookup"><span data-stu-id="b2387-121">The value of the parameter specified for a service.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="b2387-122">자식 요소</span><span class="sxs-lookup"><span data-stu-id="b2387-122">Child Elements</span></span>  
 <span data-ttu-id="b2387-123">없음</span><span class="sxs-lookup"><span data-stu-id="b2387-123">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="b2387-124">부모 요소</span><span class="sxs-lookup"><span data-stu-id="b2387-124">Parent Elements</span></span>  
  
|<span data-ttu-id="b2387-125">요소</span><span class="sxs-lookup"><span data-stu-id="b2387-125">Element</span></span>|<span data-ttu-id="b2387-126">설명</span><span class="sxs-lookup"><span data-stu-id="b2387-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="b2387-127">\<commonParameters></span><span class="sxs-lookup"><span data-stu-id="b2387-127">\<commonParameters></span></span>](https://msdn.microsoft.com/library/d0e1e6fc-985a-4713-b7da-194e30dfab4c)|<span data-ttu-id="b2387-128">서비스에서 사용하는 일반 매개 변수 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="b2387-128">A collection of common parameters used by services.</span></span> <span data-ttu-id="b2387-129">일반적으로 이 컬렉션에는 영속 서비스에서 공유할 수 있는 데이터베이스 연결 문자열이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="b2387-129">This collection will typically include the database connection string that might be shared by durable services.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b2387-130">설명</span><span class="sxs-lookup"><span data-stu-id="b2387-130">Remarks</span></span>  
 <span data-ttu-id="b2387-131">`<commonParameters>` 요소는 여러 서비스에서 전역적으로 사용되는 모든 매개 변수를 정의합니다. 예를 들어 `ConnectionString`를 사용하는 경우 <xref:System.Workflow.Runtime.Hosting.SharedConnectionWorkflowCommitWorkBatchService>을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="b2387-131">The `<commonParameters>` element defines any parameters that are used globally across multiple services, for example `ConnectionString` when using the <xref:System.Workflow.Runtime.Hosting.SharedConnectionWorkflowCommitWorkBatchService>.</span></span>  
  
 <span data-ttu-id="b2387-132">작업 일괄 처리를 지속성 저장소에 커밋하는 서비스(예: <xref:System.Workflow.Runtime.Hosting.DefaultWorkflowCommitWorkBatchService> 및 <xref:System.Workflow.Runtime.Hosting.SqlWorkflowPersistenceService>)의 경우 다음 예제와 같이 `EnableRetries` 매개 변수를 사용하여 트랜잭션을 다시 시도하도록 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b2387-132">For services that commit work batches to persistence stores, such as <xref:System.Workflow.Runtime.Hosting.DefaultWorkflowCommitWorkBatchService> and <xref:System.Workflow.Runtime.Hosting.SqlWorkflowPersistenceService>, you can enable them to retry their transaction by using the `EnableRetries` parameter as shown in the following example:</span></span>  
  
```xml  
<WorkflowRuntime Name="SampleApplication" UnloadOnIdle="false">  
    <commonParameters>  
        <add name="ConnectionString" value="Initial Catalog=WorkflowStore;Data Source=localhost;Integrated Security=SSPI;" />  
        <add name="EnableRetries" value="True" />  
    </commonParameters>  
    <Services>  
        <add type="System.Workflow.Runtime.Hosting.SqlWorkflowPersistenceService, System.Workflow.Runtime, Version=3.0.00000.0, Culture=neutral, PublicKeyToken=31bf3856ad364e35" EnableRetries="False" />   
     </Services>  
</WorkflowRuntime>  
```  
  
 <span data-ttu-id="b2387-133">`EnableRetries` 매개 변수에서 전역 수준을 설정할 수 있습니다 (에 표시 된 대로 합니다 *CommonParameters* 섹션) 개인에 대 한 지 원하는 서비스 또는 `EnableRetries` (에서처럼는 *Services*섹션).</span><span class="sxs-lookup"><span data-stu-id="b2387-133">Notice that the `EnableRetries` parameter can be set at either a global level (as shown in the *CommonParameters* section) or for individual services that support `EnableRetries` (as shown in the *Services* section).</span></span>  
  
 <span data-ttu-id="b2387-134">동작을 제어 하려면 구성 파일을 사용 하는 방법은 <xref:System.Workflow.Runtime.WorkflowRuntime> 개체는 Windows Workflow Foundation 호스트 응용 프로그램의 참조 [워크플로 구성 파일](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms732240(v=vs.90))합니다.</span><span class="sxs-lookup"><span data-stu-id="b2387-134">For more information on using a configuration file to control the behavior of a <xref:System.Workflow.Runtime.WorkflowRuntime> object of a Windows Workflow Foundation host application, see [Workflow Configuration Files](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms732240(v=vs.90)).</span></span>  
  
## <a name="example"></a><span data-ttu-id="b2387-135">예제</span><span class="sxs-lookup"><span data-stu-id="b2387-135">Example</span></span>  
  
```xml  
<commonParameters>  
   <add name="ConnectionString" value="Initial Catalog=WorkflowStore;Data Source=localhost;Integrated Security=SSPI;"/>  
   <add name="EnableRetries" value="true"/>  
</commonParameters>  
```  
  
## <a name="see-also"></a><span data-ttu-id="b2387-136">참고 항목</span><span class="sxs-lookup"><span data-stu-id="b2387-136">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.WorkflowRuntimeElement>  
 <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement>  
 <xref:System.Workflow.Runtime.WorkflowRuntime>  
 <xref:System.Workflow.Runtime.Hosting.DefaultWorkflowCommitWorkBatchService>  
 <xref:System.Workflow.Runtime.Hosting.SqlWorkflowPersistenceService>  
 <span data-ttu-id="b2387-137">[워크플로 구성 파일](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms732240(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="b2387-137">[Workflow Configuration Files](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms732240(v=vs.90))</span></span>  
 [<span data-ttu-id="b2387-138">\<commonParameters></span><span class="sxs-lookup"><span data-stu-id="b2387-138">\<commonParameters></span></span>](https://msdn.microsoft.com/library/d0e1e6fc-985a-4713-b7da-194e30dfab4c)
