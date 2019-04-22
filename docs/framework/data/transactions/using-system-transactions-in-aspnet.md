---
title: ASP.NET에서 System.Transactions 사용
ms.date: 03/30/2017
ms.assetid: 1982c300-7ea6-4242-95ed-dc28ccfacac9
ms.openlocfilehash: df9a9f1878b2268d1d6bc3d9b05d0ad8d7bcc3f0
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59134593"
---
# <a name="using-systemtransactions-in-aspnet"></a>ASP.NET에서 System.Transactions 사용
이 항목에서는 <xref:System.Transactions> 애플리케이션 내부에서 [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] 를 성공적으로 사용하는 방법에 대해 설명합니다.  
  
## <a name="enable-distributedtransactionpermission-in-aspnet"></a>ASP.NET에서 DistributedTransactionPermission 사용  
 <xref:System.Transactions> 는 부분적으로 신뢰할 수 있는 호출자를 지원하며 **AllowPartiallyTrustedCallers** 특성(APTCA)으로 표시됩니다. <xref:System.Transactions> 에 대한 신뢰 수준은 <xref:System.Transactions> 가 노출하는 리소스 형식(예: 시스템 메모리, 공유 프로세스 범위 리소스, 시스템 범위 리소스 및 기타 리소스) 및 해당 리소스에 액세스하는 데 필요한 신뢰 수준을 기반으로 정의됩니다. 부분 신뢰 환경에서 완전 신뢰가 아닌 어셈블리는 <xref:System.Transactions.DistributedTransactionPermission>이 부여되지 않은 경우 애플리케이션 도메인 내에서만 트랜잭션을 사용할 수 있습니다(이 경우 보호되는 리소스는 시스템 메모리뿐임).  
  
 MSDTC(Microsoft Distributed Transaction Coordinator)에서 관리하도록 트랜잭션 관리를 에스컬레이션할 때마다<xref:System.Transactions.DistributedTransactionPermission> 이 필요합니다. 이 종류의 시나리오에서는 프로세스 범위 리소스, 특히 MSDTC 로그의 예약된 공간인 전역 리소스를 사용합니다. 이러한 사용 예로 데이터베이스에 대한 웹 프런트 엔드 또는 제공하는 서비스의 일부로 데이터베이스를 사용하는 애플리케이션이 있습니다.  
  
 [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] 에는 자체 신뢰 수준 집합이 있으며 정책 파일을 통해 특정 사용 권한 집합을 이러한 신뢰 수준과 연결합니다. 자세한 내용은 [ASP.NET 신뢰 수준과 정책 파일](https://docs.microsoft.com/previous-versions/aspnet/wyts434y(v=vs.100))합니다. Windows SDK를 처음 설치할 때는 [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] 과 연결된 기본 <xref:System.Transactions.DistributedTransactionPermission>정책 파일이 없습니다. 따라서 MSDTC에서 관리하도록 [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] 애플리케이션의 트랜잭션을 에스컬레이션하는 경우 <xref:System.Security.SecurityException> 을 요청할 때 <xref:System.Transactions.DistributedTransactionPermission>이 발생하며 에스컬레이션이 실패합니다. [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] 부분 신뢰 환경에서 트랜잭션 에스컬레이션을 사용하려면 <xref:System.Transactions.DistributedTransactionPermission> 과 동일한 기본 신뢰 수준에서 <xref:System.Data.SqlClient.SqlClientPermission>을 부여해야 합니다. 이를 지원하도록 사용자 지정 신뢰 수준과 정책 파일을 구성하거나 **Web_hightrust.config** 및 **Web_mediumtrust.config**인 기본 정책 파일을 수정할 수 있습니다.  
  
 정책 파일을 수정 하려면을 **SecurityClass** 요소에 대 한 **DistributedTransactionPermission** 하는 **SecurityClasses** 요소 아래에 있는  **PolicyLevel** 요소 및 해당 추가 **IPermission** 요소 아래에 있는 합니다 [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] **NamedPermissionSet** System.Transactions에 대 한 합니다. 다음 구성 파일에서 이 작업을 보여 줍니다.  
  
```xml  
<SecurityClasses>  
   <SecurityClass Name="DistributedTransactionPermission" Description="System.Transactions.DistributedTransactionPermission, System.Transactions, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089"/>  
...  
</SecurityClasses>  
  
<PermissionSet  
  class="NamedPermissionSet"  
  version="1"  
  Name="ASP.Net">  
     <IPermission  
        class="System.Transactions.DistributedTransactionPermission, System.Transactions, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089"  
        version="1"  
        Unrestricted="true"  
     />  
...  
</PermissionSet>  
```  
  
 에 대 한 자세한 내용은 [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] 보안 정책 참조 [securityPolicy 요소 (ASP.NET 설정 스키마)](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/zhs35b56(v=vs.100))합니다.  
  
## <a name="dynamic-compilation"></a>동적 컴파일  
 액세스 시 동적으로 컴파일되는 <xref:System.Transactions> 애플리케이션에서 [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] 를 가져오고 사용하려면 <xref:System.Transactions> 어셈블리에 대한 참조를 구성 파일에 넣어야 합니다. 특히 기본 루트 **Web.config**/**compilation** / **assemblies** 섹션 아래에 참조를 추가해야 합니다. 다음은 이에 대한 예입니다.  
  
```xml  
<configuration>  
   <system.web>  
      <compilation>  
         <assemblies>  
      <add assembly="System.Transactions, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" />  
         </assemblies>  
      </compilation>  
   </system.web>  
</configuration>  
```  
  
 자세한 내용은 [컴파일 (ASP.NET 설정 스키마)에 대 한 어셈블리에 대 한 add 요소](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/37e2zyhb(v=vs.100))합니다.  
  
## <a name="see-also"></a>참고자료

- [ASP.NET 신뢰 수준과 정책 파일](https://docs.microsoft.com/previous-versions/aspnet/wyts434y(v=vs.100))
- [securityPolicy 요소 (ASP.NET 설정 스키마)](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/zhs35b56(v=vs.100))
- [트랜잭션 관리 에스컬레이션](../../../../docs/framework/data/transactions/transaction-management-escalation.md)
