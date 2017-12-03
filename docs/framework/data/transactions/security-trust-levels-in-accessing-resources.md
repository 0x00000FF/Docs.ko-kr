---
title: "리소스 액세스의 보안 신뢰 수준"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: fb5be924-317d-4d69-b33a-3d18ecfb9d6e
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: d6fe8902021d6585434c2dcdfa42784d59818157
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/02/2017
---
# <a name="security-trust-levels-in-accessing-resources"></a>리소스 액세스의 보안 신뢰 수준
이 항목에서는 <xref:System.Transactions>에서 노출하는 리소스 형식에 따라 액세스가 제한되는 방법에 대해 설명합니다.  
  
 <xref:System.Transactions>에 대한 세 가지 기본 신뢰 수준이 있습니다. 신뢰 수준은 <xref:System.Transactions>에서 노출하는 리소스 형식과 이러한 리소스에 액세스하는 데 필요한 신뢰 수준을 기반으로 정의됩니다. <xref:System.Transactions>에서 액세스를 제공하는 리소스는 시스템 메모리, 공유 프로세스 범위 리소스 및 시스템 범위 리소스입니다. 수준은 다음과 같습니다.  
  
-   **AllowPartiallyTrustedCallers** (APTCA) 트랜잭션을 사용 하 여 단일 응용 프로그램 도메인 내에서 응용 프로그램에 대 한 합니다.  
  
-   **DistributedTransactionPermission** DTP 분산된 트랜잭션을 사용 하 여 응용 프로그램에 대 한 합니다.  
  
-   지속적인 리소스, 구성 관리 응용 프로그램 및 레거시 interop 응용 프로그램에 대한 완전 신뢰  
  
> [!NOTE]
>  가장된 컨텍스트를 사용하여 인리스트먼트 인터페이스를 호출하면 안 됩니다.  
  
## <a name="trust-levels"></a>신뢰 수준  
  
### <a name="aptca-partial-trust"></a>APTCA(부분 신뢰)  
 <xref:System.Transactions> 으로 표시 되어 있으므로 부분적으로 신뢰할 수 있는 코드에서 어셈블리를 호출할 수 있습니다는 **AllowPartiallyTrustedCallers** 특성 (APTCA). 이 특성을 기본적으로 암시적 제거 <xref:System.Security.Permissions.SecurityAction.LinkDemand> 에 대 한는 **FullTrust** 사용 권한 집합을 이외 각 형식의 공개적으로 액세스 가능한 각 메서드에 자동으로 배치 합니다. 그러나 일부 형식과 멤버에는 더 강력한 권한이 필요합니다.  
  
 APTCA 특성을 통해 응용 프로그램은 단일 응용 프로그램 도메인 내에서 부분 신뢰 트랜잭션을 사용할 수 있습니다. 이 경우 일시적인 인리스트먼트와 에스컬레이션되지 않는 트랜잭션을 오류 처리에 사용할 수 있습니다. 이러한 예로 트랜잭션된 해시 테이블과 이를 사용하는 응용 프로그램이 있습니다. 단일 트랜잭션으로 해시 테이블에 데이터를 추가하고 제거할 수 있습니다. 나중에 트랜잭션을 롤백하는 경우 해당 트랜잭션에서 수행된 해시 테이블의 모든 변경 내용을 취소할 수 있습니다.  
  
### <a name="distributedtransactionpermission-dtp"></a>DistributedTransactionPermission(DTP)  
 MSDTC에서 관리하도록 <xref:System.Transactions> 트랜잭션을 에스컬레이션하는 경우 <xref:System.Transactions>에서 분산 트랜잭션을 만들려면 <xref:System.Transactions.DistributedTransactionPermission>(DTP)이 필요합니다. 따라서 serialization 또는 지속적인 추가 인리스트먼트를 통해 트랜잭션이 에스컬레이션되게 하는 코드에 DTP를 부여해야 합니다. 원래 <xref:System.Transactions> 트랜잭션을 만든 코드에는 이 권한이 없어도 됩니다.  
  
### <a name="fulltrust-link-demands"></a>FullTrust 링크 요청  
 이 사용 권한 수준은 지속적인 리소스에 쓰는 응용 프로그램을 제한합니다. 실패 시 응용 프로그램이 복구될 수 있어야 하며 트랜잭션 관리자가 영구 데이터를 업데이트할 수 있도록 트랜잭션의 최종 결과를 확인해야 합니다. 이 응용 프로그램 종류를 지속적인 소스 관리자라고 합니다. 이 응용 프로그램 종류의 일반적인 예로 SQL이 있습니다.  
  
 복구를 사용하기 위해 이 응용 프로그램 종류에는 시스템 리소스를 영구적으로 사용하는 기능이 있습니다. 이는 트랜잭션에 참여하는 모든 지속적인 리소스 관리자에서 결과를 받은 것을 확인할 수 있을 때까지 복구할 수 있는 트랜잭션 관리자가 커밋된 트랜잭션을 저장해야 하기 때문입니다. 따라서 이 응용 프로그램 종류에는 완전 신뢰가 필요하며 해당 신뢰 수준이 부여되지 않은 경우 실행하면 안 됩니다.  
  
 지속적인 인리스트먼트 및 복구에 대 한 자세한 내용은 참조는 [트랜잭션에서 참가자 인 리스트 먼 트 리소스](../../../../docs/framework/data/transactions/enlisting-resources-as-participants-in-a-transaction.md) 및 [복구 수행](../../../../docs/framework/data/transactions/performing-recovery.md) 항목입니다.  
  
 COM+와의 레거시 interop 작업을 수행하는 응용 프로그램에도 완전 신뢰가 있어야 합니다.  
  
 다음은 형식의 목록 및 부분적으로에서 호출할 수 없는 멤버에 신뢰할 수 있는 코드와 데코레이팅되기 때문에 **FullTrust** 선언적 보안 특성:  
  
 `PermissionSetAttribute(SecurityAction.LinkDemand, Name := "FullTrust")`  
  
-   <xref:System.Transactions.Transaction.EnlistDurable%2A?displayProperty=nameWithType>  
  
-   <xref:System.Transactions.Transaction.EnlistPromotableSinglePhase%2A>  
  
-   <xref:System.Transactions.TransactionInterop>  
  
-   <xref:System.Transactions.TransactionManager.DistributedTransactionStarted>  
  
-   <xref:System.Transactions.HostCurrentTransactionCallback>  
  
-   <xref:System.Transactions.TransactionManager.Reenlist%2A>  
  
-   <xref:System.Transactions.TransactionManager.RecoveryComplete%2A>  
  
-   <xref:System.Transactions.TransactionScope.%23ctor%28System.Transactions.TransactionScopeOption%2CSystem.Transactions.TransactionOptions%2CSystem.Transactions.EnterpriseServicesInteropOption%29>  
  
 만 직접 실행 호출자가 보유 하는 데 필요한는 **FullTrust** 권한 위의 형식이 나 메서드를 사용 하도록 설정 합니다.
