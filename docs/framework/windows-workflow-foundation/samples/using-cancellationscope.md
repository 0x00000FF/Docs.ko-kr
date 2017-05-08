---
title: "CancellationScope 사용 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 39c5c338-b316-43d6-b7fe-a543281dd1ec
caps.latest.revision: 10
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 10
---
# CancellationScope 사용
이 샘플에서는 <xref:System.Activities.Statements.CancellationScope> 활동을 사용하여 응용 프로그램에서 작업을 취소하는 방법을 보여 줍니다.  
  
 많은 중간 계층 구성 요소 및 서비스는 잘 알려진 트랜잭션 프로그래밍 구문을 사용하여 취소를 처리하지만  트랜잭션에서 수행할 수 없는 작업을 취소해야 하는 경우도 많습니다.  취소해야 하는 작업을 먼저 추적해야 하기 때문에 취소를 사용하는 것이 트랜잭션을 사용하는 것보다 어렵습니다.  [!INCLUDE[netfx_current_short](../../../../includes/netfx-current-short-md.md)]는 <xref:System.Activities.Statements.CancellationScope> 활동을 제공하여 이 기능을 수행합니다.  
  
 취소는 활동 내에서 또는 활동의 부모에서 트리거할 수 있습니다.  자식 활동은 <xref:System.Activities.Statements.Sequence>, <xref:System.Activities.Statements.Parallel>, <xref:System.Activities.Statements.Flowchart> 또는 사용자 지정 복합 활동과 같은 부모 활동에 의해 예약됩니다.  이유에 관계없이 부모 활동은 자식 활동을 취소할 수 있습니다.  예를 들어 세 개의 자식 분기가 있는 <xref:System.Activities.Statements.Parallel> 활동은 분기를 완료하고 <xref:System.Activities.Statements.Parallel.CompletionCondition%2A>식이 `true`로 평가될 때마다 나머지 자식 분기를 취소합니다.  <xref:System.Activities.WorkflowApplication.Cancel%2A>을 호출하여 호스트 응용 프로그램에서 워크플로를 외부적으로 취소할 수도 있습니다.  
  
 <xref:System.Activities.Statements.CancellationScope> 활동을 사용하려면 취소해야 하는 작업을 <xref:System.Activities.Statements.CancellationScope.Body%2A> 속성에 넣고 취소 후에 수행되는 작업을 <xref:System.Activities.Statements.CancellationScope.CancellationHandler%2A> 속성에 넣습니다.  
  
 이 샘플에서는 활동 자체 내에서 활동을 취소하는 방법을 보여 줍니다.  
  
 이 샘플에서 <xref:System.Activities.Statements.CancellationScope> 활동을 보여 주기 위해 사용하는 시니리오에서는 고객이 최대한 빨리 마이애미행 비행기표를 구입하려고 합니다.  거래를 원하는 두 개의 여행사가 있으며,  샘플에서는 <xref:System.Activities.Statements.CancellationScope> 활동 내에서 두 개의 <xref:System.Activities.Statements.Parallel>를 사용하여 이 비즈니스 논리를 모델링합니다.  <xref:System.Activities.Statements.Parallel.CompletionCondition%2A> 활동의 <xref:System.Activities.Statements.Parallel>은 `true`로 설정됩니다. <xref:System.Activities.Statements.Parallel.CompletionCondition%2A>은 분기 중 하나가 완료된 후 확인되므로 첫 번째 분기가 완료된 후 나머지 분기가 취소됩니다.  클라이언트 응용 프로그램은 두 여행사에 비행기표 구입을 문의한 후 둘 중 한 여행사에서 비행기표를 구입했음을 확인하면 다른 여행사에서의 주문을 취소합니다.  
  
## 이 샘플을 사용하려면  
  
1.  [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)]을 사용하여 CancelationScopeXAML.sln 솔루션 파일을 엽니다.  
  
2.  Ctrl\+Shift\+B를 눌러 솔루션을 빌드합니다.  
  
3.  Ctrl\+F5를 눌러 솔루션을 실행합니다.  
  
> [!IMPORTANT]
>  컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다.  계속하기 전에 다음\(기본\) 디렉터리를 확인하세요.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  이 디렉터리가 없으면 [.NET Framework 4용 WCF\(Windows Communication Foundation\) 및 Windows WF\(Workflow Foundation\) 샘플](http://go.microsoft.com/fwlink/?LinkId=150780)\(영문\)로 이동하여 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 및 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플을 모두 다운로드하세요.  이 샘플은 다음 디렉터리에 있습니다.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Built-InActivities\CancellationScope`  
  
## 참고 항목