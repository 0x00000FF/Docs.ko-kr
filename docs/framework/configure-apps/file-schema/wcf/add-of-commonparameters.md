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
# <a name="ltaddgt-of-ltcommonparametersgt"></a>&lt;commonParameters&gt;의 &lt;add&gt;
여러 서비스에서 전역적으로 사용되는 매개 변수의 이름-값 쌍을 지정합니다. 일반적으로 이 매개 변수에는 영속 서비스에서 공유할 수 있는 데이터베이스 연결 문자열이 포함됩니다.  
  
 \<system.ServiceModel>  
\<동작 >  
\<serviceBehaviors>  
\<동작 >  
\<workflowRuntime>  
\<commonParameters>  
\<add>  
  
## <a name="syntax"></a>구문  
  
```xml  
<workflowRuntime>  
   <commonParameters>  
      <add name="String" value="String" />  
   </commonParameters>  
</workflowRuntime>  
```  
  
## <a name="attributes-and-elements"></a>특성 및 요소  
 다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### <a name="attributes"></a>특성  
  
|특성|설명|  
|---------------|-----------------|  
|name|서비스에 지정한 매개 변수 이름입니다.|  
|값|서비스에 지정한 매개 변수 값입니다.|  
  
### <a name="child-elements"></a>자식 요소  
 없음  
  
### <a name="parent-elements"></a>부모 요소  
  
|요소|설명|  
|-------------|-----------------|  
|[\<commonParameters>](https://msdn.microsoft.com/library/d0e1e6fc-985a-4713-b7da-194e30dfab4c)|서비스에서 사용하는 일반 매개 변수 컬렉션입니다. 일반적으로 이 컬렉션에는 영속 서비스에서 공유할 수 있는 데이터베이스 연결 문자열이 포함됩니다.|  
  
## <a name="remarks"></a>설명  
 `<commonParameters>` 요소는 여러 서비스에서 전역적으로 사용되는 모든 매개 변수를 정의합니다. 예를 들어 `ConnectionString`를 사용하는 경우 <xref:System.Workflow.Runtime.Hosting.SharedConnectionWorkflowCommitWorkBatchService>을 정의합니다.  
  
 작업 일괄 처리를 지속성 저장소에 커밋하는 서비스(예: <xref:System.Workflow.Runtime.Hosting.DefaultWorkflowCommitWorkBatchService> 및 <xref:System.Workflow.Runtime.Hosting.SqlWorkflowPersistenceService>)의 경우 다음 예제와 같이 `EnableRetries` 매개 변수를 사용하여 트랜잭션을 다시 시도하도록 할 수 있습니다.  
  
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
  
 `EnableRetries` 매개 변수에서 전역 수준을 설정할 수 있습니다 (에 표시 된 대로 합니다 *CommonParameters* 섹션) 개인에 대 한 지 원하는 서비스 또는 `EnableRetries` (에서처럼는 *Services*섹션).  
  
 동작을 제어 하려면 구성 파일을 사용 하는 방법은 <xref:System.Workflow.Runtime.WorkflowRuntime> 개체는 Windows Workflow Foundation 호스트 응용 프로그램의 참조 [워크플로 구성 파일](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms732240(v=vs.90))합니다.  
  
## <a name="example"></a>예제  
  
```xml  
<commonParameters>  
   <add name="ConnectionString" value="Initial Catalog=WorkflowStore;Data Source=localhost;Integrated Security=SSPI;"/>  
   <add name="EnableRetries" value="true"/>  
</commonParameters>  
```  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.ServiceModel.Configuration.WorkflowRuntimeElement>  
 <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement>  
 <xref:System.Workflow.Runtime.WorkflowRuntime>  
 <xref:System.Workflow.Runtime.Hosting.DefaultWorkflowCommitWorkBatchService>  
 <xref:System.Workflow.Runtime.Hosting.SqlWorkflowPersistenceService>  
 [워크플로 구성 파일](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms732240(v=vs.90))  
 [\<commonParameters>](https://msdn.microsoft.com/library/d0e1e6fc-985a-4713-b7da-194e30dfab4c)
