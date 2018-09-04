---
title: ASP.NET에서 System.Transactions 사용
ms.date: 03/30/2017
ms.assetid: 1982c300-7ea6-4242-95ed-dc28ccfacac9
ms.openlocfilehash: 7b73ec970776f39a0c056e2a706d4818cda6cd72
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/04/2018
ms.locfileid: "43534545"
---
# <a name="using-systemtransactions-in-aspnet"></a><span data-ttu-id="83e0f-102">ASP.NET에서 System.Transactions 사용</span><span class="sxs-lookup"><span data-stu-id="83e0f-102">Using System.Transactions in ASP.NET</span></span>
<span data-ttu-id="83e0f-103">이 항목에서는 <xref:System.Transactions> 응용 프로그램 내부에서 [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] 를 성공적으로 사용하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="83e0f-103">This topic describes how you can successfully use <xref:System.Transactions> inside an [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] application.</span></span>  
  
## <a name="enable-distributedtransactionpermission-in-aspnet"></a><span data-ttu-id="83e0f-104">ASP.NET에서 DistributedTransactionPermission 사용</span><span class="sxs-lookup"><span data-stu-id="83e0f-104">Enable DistributedTransactionPermission in ASP.NET</span></span>  
 <span data-ttu-id="83e0f-105"><xref:System.Transactions> 는 부분적으로 신뢰할 수 있는 호출자를 지원하며 **AllowPartiallyTrustedCallers** 특성(APTCA)으로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="83e0f-105"><xref:System.Transactions> supports partially trusted callers and is marked with the **AllowPartiallyTrustedCallers** attribute (APTCA).</span></span> <span data-ttu-id="83e0f-106"><xref:System.Transactions> 에 대한 신뢰 수준은 <xref:System.Transactions> 가 노출하는 리소스 형식(예: 시스템 메모리, 공유 프로세스 범위 리소스, 시스템 범위 리소스 및 기타 리소스) 및 해당 리소스에 액세스하는 데 필요한 신뢰 수준을 기반으로 정의됩니다.</span><span class="sxs-lookup"><span data-stu-id="83e0f-106">The trust levels for <xref:System.Transactions> are defined based on the types of resources, (for example, system memory, shared process-wide resources, system-wide resources, and other resources), that <xref:System.Transactions> exposes and the level of trust that should be required to access those resources.</span></span> <span data-ttu-id="83e0f-107">부분 신뢰 환경에서 완전 신뢰가 아닌 어셈블리는 <xref:System.Transactions.DistributedTransactionPermission>이 부여되지 않은 경우 응용 프로그램 도메인 내에서만 트랜잭션을 사용할 수 있습니다(이 경우 보호되는 리소스는 시스템 메모리뿐임).</span><span class="sxs-lookup"><span data-stu-id="83e0f-107">In a partial-trust environment, a non-full trust assembly can only use transactions within the Application Domain (in this case, the only resource being protected is system memory), unless it is granted the <xref:System.Transactions.DistributedTransactionPermission>.</span></span>  
  
 <span data-ttu-id="83e0f-108">MSDTC(Microsoft Distributed Transaction Coordinator)에서 관리하도록 트랜잭션 관리를 에스컬레이션할 때마다<xref:System.Transactions.DistributedTransactionPermission> 이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="83e0f-108"><xref:System.Transactions.DistributedTransactionPermission> is demanded whenever transaction management is escalated to be managed by the Microsoft Distributed Transaction Coordinator (MSDTC).</span></span> <span data-ttu-id="83e0f-109">이 종류의 시나리오에서는 프로세스 범위 리소스, 특히 MSDTC 로그의 예약된 공간인 전역 리소스를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="83e0f-109">This kind of scenario utilizes process-wide resources and particularly a global resource, which is the reserved space in the MSDTC log.</span></span> <span data-ttu-id="83e0f-110">이러한 사용 예로 데이터베이스에 대한 웹 프런트 엔드 또는 제공하는 서비스의 일부로 데이터베이스를 사용하는 응용 프로그램이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="83e0f-110">An example of this usage is a Web front-end to a database or an application that uses a database as part of the services it provides.</span></span>  
  
 [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)]<span data-ttu-id="83e0f-111"> 에는 자체 신뢰 수준 집합이 있으며 정책 파일을 통해 특정 사용 권한 집합을 이러한 신뢰 수준과 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="83e0f-111"> has its own set of trust levels and associates a specific set of permissions with these trust levels through policy files.</span></span> <span data-ttu-id="83e0f-112">자세한 내용은 [ASP.NET 신뢰 수준과 정책 파일](https://msdn.microsoft.com/library/f897c794-10d3-414c-86b7-59b66564bbf1)합니다.</span><span class="sxs-lookup"><span data-stu-id="83e0f-112">For more information, see [ASP.NET Trust Levels and Policy Files](https://msdn.microsoft.com/library/f897c794-10d3-414c-86b7-59b66564bbf1).</span></span> <span data-ttu-id="83e0f-113">Windows SDK를 처음 설치할 때는 [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] 과 연결된 기본 <xref:System.Transactions.DistributedTransactionPermission>정책 파일이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="83e0f-113">When you initially install the Windows SDK, none of the default [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] policy files are associated with the <xref:System.Transactions.DistributedTransactionPermission>.</span></span> <span data-ttu-id="83e0f-114">따라서 MSDTC에서 관리하도록 [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] 응용 프로그램의 트랜잭션을 에스컬레이션하는 경우 <xref:System.Security.SecurityException> 을 요청할 때 <xref:System.Transactions.DistributedTransactionPermission>이 발생하며 에스컬레이션이 실패합니다.</span><span class="sxs-lookup"><span data-stu-id="83e0f-114">As such, when your transaction in an [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] application is escalated to be managed by the MSDTC, the escalation fails with a <xref:System.Security.SecurityException> upon demanding the <xref:System.Transactions.DistributedTransactionPermission>.</span></span> <span data-ttu-id="83e0f-115">[!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] 부분 신뢰 환경에서 트랜잭션 에스컬레이션을 사용하려면 <xref:System.Transactions.DistributedTransactionPermission> 과 동일한 기본 신뢰 수준에서 <xref:System.Data.SqlClient.SqlClientPermission>을 부여해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="83e0f-115">To enable transaction escalation in an [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] partial trust environment, you should grant the <xref:System.Transactions.DistributedTransactionPermission> in the same default trust levels as those of <xref:System.Data.SqlClient.SqlClientPermission>.</span></span> <span data-ttu-id="83e0f-116">이를 지원하도록 사용자 지정 신뢰 수준과 정책 파일을 구성하거나 **Web_hightrust.config** 및 **Web_mediumtrust.config**인 기본 정책 파일을 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="83e0f-116">You can either configure your own custom trust level and policy file to support this, or you can modify the default policy files, which are **Web_hightrust.config** and **Web_mediumtrust.config**.</span></span>  
  
 <span data-ttu-id="83e0f-117">정책 파일을 수정 하려면을 **SecurityClass** 요소에 대 한 **DistributedTransactionPermission** 하는 **SecurityClasses** 요소 아래에 있는  **PolicyLevel** 요소 및 해당 추가 **IPermission** 요소 아래에 있는 합니다 [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] **NamedPermissionSet** System.Transactions에 대 한 합니다.</span><span class="sxs-lookup"><span data-stu-id="83e0f-117">To modify the policy files, add a **SecurityClass** element for **DistributedTransactionPermission** to the **SecurityClasses** element under the **PolicyLevel** element and add a corresponding **IPermission** element under the [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] **NamedPermissionSet** for System.Transactions.</span></span> <span data-ttu-id="83e0f-118">다음 구성 파일에서 이 작업을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="83e0f-118">The following configuration file demonstrates this.</span></span>  
  
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
  
 <span data-ttu-id="83e0f-119">에 대 한 자세한 내용은 [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] 보안 정책 참조 [securityPolicy 요소 (ASP.NET 설정 스키마)](https://msdn.microsoft.com/library/469d8d22-d263-46bb-8400-40d8d027faba)합니다.</span><span class="sxs-lookup"><span data-stu-id="83e0f-119">For more information about [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] security policy, see [securityPolicy Element (ASP.NET Settings Schema)](https://msdn.microsoft.com/library/469d8d22-d263-46bb-8400-40d8d027faba).</span></span>  
  
## <a name="dynamic-compilation"></a><span data-ttu-id="83e0f-120">동적 컴파일</span><span class="sxs-lookup"><span data-stu-id="83e0f-120">Dynamic Compilation</span></span>  
 <span data-ttu-id="83e0f-121">액세스 시 동적으로 컴파일되는 <xref:System.Transactions> 응용 프로그램에서 [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] 를 가져오고 사용하려면 <xref:System.Transactions> 어셈블리에 대한 참조를 구성 파일에 넣어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="83e0f-121">If you want to import and use <xref:System.Transactions> in an [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] application that is dynamically compiled on access, you should place a reference to the <xref:System.Transactions> assembly in the configuration file.</span></span> <span data-ttu-id="83e0f-122">특히 기본 루트 **Web.config**/**compilation** / **assemblies** 섹션 아래에 참조를 추가해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="83e0f-122">Specifically, the reference should be added under the **compilation**/**assemblies** section of the default root **Web.config** configuration file, or a specific Web application's configuration file.</span></span> <span data-ttu-id="83e0f-123">다음은 이에 대한 예입니다.</span><span class="sxs-lookup"><span data-stu-id="83e0f-123">The following example demonstrates this.</span></span>  
  
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
  
 <span data-ttu-id="83e0f-124">자세한 내용은 [컴파일 (ASP.NET 설정 스키마)에 대 한 어셈블리에 대 한 add 요소](https://msdn.microsoft.com/library/602197e8-108d-4249-b752-ba2a318f75e4)합니다.</span><span class="sxs-lookup"><span data-stu-id="83e0f-124">For more information, see [add Element for assemblies for compilation (ASP.NET Settings Schema)](https://msdn.microsoft.com/library/602197e8-108d-4249-b752-ba2a318f75e4).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="83e0f-125">참고 항목</span><span class="sxs-lookup"><span data-stu-id="83e0f-125">See Also</span></span>  
 [<span data-ttu-id="83e0f-126">ASP.NET 신뢰 수준과 정책 파일</span><span class="sxs-lookup"><span data-stu-id="83e0f-126">ASP.NET Trust Levels and Policy Files</span></span>](https://msdn.microsoft.com/library/f897c794-10d3-414c-86b7-59b66564bbf1)  
 [<span data-ttu-id="83e0f-127">securityPolicy 요소 (ASP.NET 설정 스키마)</span><span class="sxs-lookup"><span data-stu-id="83e0f-127">securityPolicy Element (ASP.NET Settings Schema)</span></span>](https://msdn.microsoft.com/library/469d8d22-d263-46bb-8400-40d8d027faba)  
 [<span data-ttu-id="83e0f-128">트랜잭션 관리 에스컬레이션</span><span class="sxs-lookup"><span data-stu-id="83e0f-128">Transaction Management Escalation</span></span>](../../../../docs/framework/data/transactions/transaction-management-escalation.md)
