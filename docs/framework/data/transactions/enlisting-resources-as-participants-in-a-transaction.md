---
title: "리소스를 트랜잭션에 참가 요소로 등록  | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 786a12c2-d530-49f4-9c59-5c973e15a11d
caps.latest.revision: 3
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 3
---
# 리소스를 트랜잭션에 참가 요소로 등록 
트랜잭션에 참여하는 각 리소스는 RM\(리소스 관리자\)에 의해 관리되고, RM의 작업은 TM\(트랜잭션 관리자\)에 의해 조정됩니다.코디네이션은 트랜잭션 관리자를 통해 트랜잭션에 참여한 구독자에게 제공되는 알림을 통해 수행됩니다.  
  
 이 항목에서는 하나의 리소스\(또는 여러 리소스\)가 트랜잭션에 참여할 수 있는 방법과 여러 인리스트먼트 유형에 대해 설명합니다.[단일 단계 및 다단계 트랜잭션 커밋 ](../../../../docs/framework/data/transactions/committing-a-transaction-in-single-phase-and-multi-phase.md) 항목에서는 참여하는 리소스에서 트랜잭션 커밋을 조정하는 방법에 대해 설명합니다.  
  
## 트랜잭션에 리소스 참여  
 리소스가 트랜잭션에 참가하려면 트랜잭션에 참여해야 합니다.<xref:System.Transactions.Transaction> 클래스는 이 기능을 제공하며 이름이 **Enlist**로 시작되는 메서드 집합을 정의합니다.각 **Enlist** 메서드는 리소스 관리자가 가질 수 있는 다른 인리스트먼트 형식에 해당합니다.특히 일시적인 리소스에는 <xref:System.Transactions.Transaction.EnlistVolatile%2A> 메서드를 사용하고 지속적인 리소스에는 <xref:System.Transactions.Transaction.EnlistDurable%2A> 메서드를 사용합니다.리소스 관리자의 지속성\(또는 일시성\)은 리소스 관리자가 오류 복구를 지원하는지 여부를 나타냅니다.오류 복구를 지원하는 경우 리소스 관리자는 Phase1\(준비\) 중에 지속적인 저장소에 데이터를 저장하여 리소스 관리자가 작동하지 않으면 복구 시 트랜잭션에 다시 참여하고 TM에서 받은 알림을 기반으로 적절한 작업을 수행할 수 있도록 합니다.일반적으로 일시적인 리소스 관리자는 메모리 내 데이터 구조\(예: 트랜잭션된 메모리 내 해시 테이블\) 같은 일시적인 리소스를 관리하고 지속적인 리소스 관리자는 보다 지속적인 백업 저장소\(예: 백업 저장소가 디스크인 데이터베이스\)가 있는 리소스를 관리합니다.  
  
 단순성을 위해 리소스의 지속성 지원을 기반으로 <xref:System.Transactions.Transaction.EnlistDurable%2A> 또는 <xref:System.Transactions.Transaction.EnlistVolatile%2A> 메서드를 사용할지 결정한 후 리소스 관리자에 대한 <xref:System.Transactions.IEnlistmentNotification> 인터페이스를 구현하여 2PC\(2단계 커밋\)에 참가할 리소스를 참여시켜야 합니다.2PC에 대한 자세한 내용은 [단일 단계 및 다단계 트랜잭션 커밋 ](../../../../docs/framework/data/transactions/committing-a-transaction-in-single-phase-and-multi-phase.md)을 참조하십시오.  
  
 단일 참가자가 <xref:System.Transactions.Transaction.EnlistDurable%2A> 및 <xref:System.Transactions.Transaction.EnlistVolatile%2A>을 여러 번 호출하여 이러한 프로토콜에 두 개 이상 참여할 수 있습니다.  
  
### 지속적인 인리스트먼트  
 <xref:System.Transactions.Transaction.EnlistDurable%2A> 메서드는 지속적인 리소스로 트랜잭션에 참가할 리소스 관리자를 참여시키는 데 사용됩니다.지속적인 리소스 관리자가 트랜잭션 중에 중단될 경우 <xref:System.Transactions.TransactionManager.Reenlist%2A> 메서드를 사용하여 참가자로 활동했으며 2단계를 완료하지 않은 모든 트랜잭션에 다시 참여하여 온라인 상태가 되면 복구를 수행할 수 있으며, 복구 처리가 완료되면 <xref:System.Transactions.TransactionManager.RecoveryComplete%2A>를 호출할 수 있습니다.복구에 대한 자세한 내용은 [복구 수행 ](../../../../docs/framework/data/transactions/performing-recovery.md)을 참조하십시오.  
  
 <xref:System.Transactions.Transaction.EnlistDurable%2A> 메서드는 모두 <xref:System.Guid> 개체를 첫 번째 매개 변수로 사용합니다.<xref:System.Guid>는 트랜잭션 관리자가 지속적인 인리스트먼트를 특정 리소스 관리자와 연결하는 데 사용됩니다.따라서 리소스 관리자는 일관되게 동일한 <xref:System.Guid>를 사용하여 다시 시작할 때 여러 리소스 관리자에서 자신을 식별해야 합니다. 그렇지 않으면 복구가 실패할 수 있습니다.  
  
 <xref:System.Transactions.Transaction.EnlistDurable%2A> 메서드의 두 번째 매개 변수는 리소스 관리자가 트랜잭션 알림을 받기 위해 구현하는 개체에 대한 참조입니다.사용하는 오버로드는 리소스 관리자가 SPC\(단일 단계 커밋\) 최적화를 지원하는지 여부를 트랜잭션 관리자에게 알립니다.대체로 2PC\(2단계 커밋\)에 참여할 <xref:System.Transactions.IEnlistmentNotification> 인터페이스를 구현합니다.그러나 커밋 프로세스를 최적화하려면 SPC에 대한 <xref:System.Transactions.ISinglePhaseNotification> 인터페이스 구현을 고려할 수 있습니다.SPC에 대한 자세한 내용은 [단일 단계 및 다단계 트랜잭션 커밋 ](../../../../docs/framework/data/transactions/committing-a-transaction-in-single-phase-and-multi-phase.md) 및 [단일 단계 커밋 및 승격 가능한 단일 단계 알림을 사용한 최적화 ](../../../../docs/framework/data/transactions/optimization-spc-and-promotable-spn.md)를 참조하십시오.  
  
 세 번째 매개 변수는 <xref:System.Transactions.EnlistmentOptions> 열거로, 해당 값은 <xref:System.Transactions.EnlistmentOptions> 또는 <xref:System.Transactions.EnlistmentOptions>일 수 있습니다.값이 <xref:System.Transactions.EnlistmentOptions>로 설정된 경우 인리스트먼트는 트랜잭션 관리자로부터 준비 알림을 받을 때 추가 리소스 관리자를 참여시킬 수 있습니다.그러나 이러한 유형의 인리스트먼트는 단일 단계 커밋 최적화에 사용할 수 없습니다.  
  
### 일시적인 인리스트먼트  
 캐시 등의 일시적인 리소스를 관리하는 참가자는 <xref:System.Transactions.Transaction.EnlistVolatile%2A> 메서드를 사용하여 참여해야 합니다.이러한 개체는 트랜잭션의 결과를 가져올 수 없거나 시스템 오류 후에 참여하는 트랜잭션의 상태를 복구할 수 없습니다.  
  
 앞에서 설명한 것처럼 리소스 관리자는 일시적인 메모리 내 리소스를 관리하는 경우에 일시적인 인리스트먼트를 만듭니다.<xref:System.Transactions.Transaction.EnlistVolatile%2A>을 사용하면 트랜잭션의 불필요한 에스컬레이션을 강제하지 않는다는 장점이 있습니다.트랜잭션 에스컬레이션에 대한 자세한 내용은 [트랜잭션 관리 에스컬레이션 ](../../../../docs/framework/data/transactions/transaction-management-escalation.md) 항목을 참조하십시오.일시적인 인리스트먼트는 트랜잭션 관리자의 인리스트먼트 처리 방법과 트랜잭션 관리자가 예상하는 리소스 관리자의 작업에서 모두 차이가 있음을 의미합니다.이는 일시적인 리소스 관리자가 복구를 수행하지 않기 때문입니다.<xref:System.Transactions.Transaction.EnlistVolatile%2A> 메서드는 <xref:System.Guid> 매개 변수를 사용하지 않습니다. 이는 일시적인 리소스 관리자가 복구를 수행하지 않으며 <xref:System.Guid>가 필요한 <xref:System.Transactions.TransactionManager.Reenlist%2A> 메서드를 호출하지 않기 때문입니다.  
  
 지속적인 인리스트먼트와 마찬가지로 인리스트먼트에 사용하는 오버로드 메서드는 리소스 관리자가 단일 단계 커밋 최적화를 지원하는지 여부를 트랜잭션 관리자에게 나타냅니다.일시적인 리소스 관리자는 복구를 수행할 수 없으므로 준비 단계 중에 일시적인 인리스트먼트에 대한 복구 정보는 작성되지 않습니다.따라서 <xref:System.Transactions.PreparingEnlistment.RecoveryInformation%2A> 메서드를 호출하면 <xref:System.InvalidOperationException>이 발생합니다.  
  
 다음 예제에서는 <xref:System.Transactions.Transaction.EnlistVolatile%2A> 메서드를 사용하여 트랜잭션의 참가자로 이러한 개체를 참여시키는 방법을 보여 줍니다.  
  
 [!code-csharp[Tx_Enlist#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/tx_enlist/cs/enlist.cs#1)]
 [!code-vb[Tx_Enlist#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/tx_enlist/vb/enlist.vb#1)]  
  
### 성능 최적화  
 <xref:System.Transactions.Transaction> 클래스는 PSPE\(승격 가능한 단일 단계 인리스트먼트\)를 참여시키는 <xref:System.Transactions.Transaction.EnlistPromotableSinglePhase%2A> 메서드도 제공합니다.이 메서드를 사용하면 지속적인 RM\(리소스 관리자\)이 트랜잭션을 호스팅하고 "소유"할 수 있으며, 필요한 경우 MSDTC에서 관리하도록 나중에 해당 트랜잭션을 에스컬레이션할 수 있습니다.이에 대한 자세한 내용은 [단일 단계 커밋 및 승격 가능한 단일 단계 알림을 사용한 최적화 ](../../../../docs/framework/data/transactions/optimization-spc-and-promotable-spn.md)를 참조하십시오.  
  
## 참고 항목  
 [단일 단계 커밋 및 승격 가능한 단일 단계 알림을 사용한 최적화 ](../../../../docs/framework/data/transactions/optimization-spc-and-promotable-spn.md)   
 [단일 단계 및 다단계 트랜잭션 커밋 ](../../../../docs/framework/data/transactions/committing-a-transaction-in-single-phase-and-multi-phase.md)