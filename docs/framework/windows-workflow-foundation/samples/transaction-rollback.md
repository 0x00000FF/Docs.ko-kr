---
title: "트랜잭션 롤백 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 7f377147-7529-4689-a588-608cee87fdf8
caps.latest.revision: 9
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 9
---
# 트랜잭션 롤백
이 샘플에서는 앰비언트 <xref:System.Activities.RuntimeTransactionHandle>에 액세스하여 앰비언트 트랜잭션을 가져와서 명시적으로 롤백하는 사용자 지정 <xref:System.Activities.NativeActivity>를 만드는 방법을 보여 줍니다.  
  
## 샘플 세부 정보  
 워크플로에서 트랜잭션은 가장 바깥쪽 <xref:System.Activities.Statements.TransactionScope> 또는 <xref:System.ServiceModel.Activities.TransactedReceiveScope>가 완료될 때 자동으로 완료됩니다.트랜잭션은 처리되지 않은 예외가 범위 경계에 전파될 때 암시적으로 롤백됩니다.그러나 예외를 throw할 필요 없이 트랜잭션을 명시적으로 롤백하는 것이 적합한 경우도 있습니다.이 경우에는 이 샘플의 활동과 같은 사용자 지정 롤백 활동을 사용하여 앰비언트 트랜잭션을 명시적으로 중단하고 선택적으로 예외 이유를 제공할 수 있습니다.  
  
 `RollbackActivity`는 <xref:System.Activities.NativeActivity>입니다. 앰비언트 <xref:System.Activities.RuntimeTransactionHandle>을 가져오려면 실행 속성에 대한 액세스 권한이 필요하기 때문입니다.`Execute` 메서드에서 <xref:System.Activities.RuntimeTransactionHandle>을 가져와서 `null`인지 여부를 확인합니다. Null은 활동이 앰비언트 런타임 트랜잭션 없이 사용되었음을 나타냅니다.그런 다음 트랜잭션을 가져와서 `null`이 있는지 여부를 다시 확인합니다.런타임 트랜잭션을 초기화하지 않고 앰비언트 <xref:System.Activities.RuntimeTransactionHandle>을 사용할 수 있습니다.마지막으로, <xref:System.Transactions.Transaction.Rollback%2A>을 호출하고 활동이 트랜잭션을 롤백했음을 나타내는 제네릭 예외 또는 사용자 제공 예외를 지정하여 트랜잭션을 중단합니다.  
  
 데모 워크플로는 `RollbackActivity` 실행 전이나 후에 본문에서 트랜잭션 상태를 출력하는 <xref:System.Activities.Statements.TransactionScope>로 구성되어 있습니다.트랜잭션이 롤백되었어도 <xref:System.Activities.Statements.TransactionScope>는 완료될 때까지 실행되며, 본문이 완료될 때까지 워크플로를 중단하지 않습니다.<xref:System.Activities.Statements.TransactionScope.AbortInstanceOnTransactionFailure%2A> 속성의 기본값은 `true`이므로 워크플로가 중단됩니다.  
  
#### 이 샘플을 사용하려면  
  
1.  [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)]에서 TransactionRollback.sln 솔루션을 로드합니다.  
  
2.  Ctrl\+Shift\+B를 눌러 솔루션을 빌드합니다.  
  
3.  Ctrl\+F5를 눌러 응용 프로그램을 실행합니다.  
  
> [!IMPORTANT]
>  컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다.계속하기 전에 다음\(기본\) 디렉터리를 확인하십시오.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  이 디렉터리가 없으면 [Windows Communication Foundation \(WCF\) and Windows Workflow Foundation \(WF\) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780)로 이동하여 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 및 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플을 모두 다운로드하십시오.이 샘플은 다음 디렉터리에 있습니다.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\Transactions\TransactionRollback`  
  
## 참고 항목  
 [트랜잭션](../../../../docs/framework/windows-workflow-foundation//workflow-transactions.md)