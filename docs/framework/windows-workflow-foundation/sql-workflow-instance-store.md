---
title: SQL 워크플로 인스턴스 저장소
ms.date: 03/30/2017
ms.assetid: 8cd2f8a5-4bf8-46ea-8909-c7fdb314fabc
ms.openlocfilehash: 926b50ee00743f6a84f48c6ccae976daf49b3d9a
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/09/2019
ms.locfileid: "57715674"
---
# <a name="sql-workflow-instance-store"></a><span data-ttu-id="aa3fa-102">SQL 워크플로 인스턴스 저장소</span><span class="sxs-lookup"><span data-stu-id="aa3fa-102">SQL Workflow Instance Store</span></span>
<span data-ttu-id="aa3fa-103">
  [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)]는 워크플로가 SQL Server 2005 또는 SQL Server 2008 데이터베이스에서 워크플로 인스턴스에 대한 상태 정보를 유지할 수 있는 SQL 워크플로 인스턴스 저장소와 함께 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="aa3fa-103">The [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)] ships with the SQL Workflow Instance Store, which allows workflows to persist state information about workflow instances in a SQL Server 2005 or SQL Server 2008 database.</span></span> <span data-ttu-id="aa3fa-104">이 기능은 주로 지속성 프레임워크의 추상 <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore> 클래스에서 파생되는 <xref:System.Runtime.DurableInstancing.InstanceStore> 클래스의 형태로 구현됩니다.</span><span class="sxs-lookup"><span data-stu-id="aa3fa-104">This feature is primarily implemented in the form of the <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore> class, which derives from the abstract <xref:System.Runtime.DurableInstancing.InstanceStore> class of the persistence framework.</span></span> <span data-ttu-id="aa3fa-105">SQL 워크플로 인스턴스 저장소 기능은 호스트가 지속성 명령을 저장소에 보내는 데 사용하는 지속성 API의 구체적인 구현인 SQL 지속성 공급자를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="aa3fa-105">The SQL Workflow Instance Store feature constitutes a SQL persistence provider, which is a concrete implementation of the persistence API that a host uses to send persistence commands to the store.</span></span>  
  
 <span data-ttu-id="aa3fa-106">SQL 워크플로 인스턴스 저장소는 <xref:System.Activities.WorkflowApplication> 또는 <xref:System.ServiceModel.WorkflowServiceHost>를 사용하는 자체 호스팅 워크플로 또는 워크플로 서비스뿐 아니라 <xref:System.ServiceModel.WorkflowServiceHost>를 사용하여 WAS에서 호스트되는 서비스도 모두 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="aa3fa-106">The SQL Workflow Instance Store supports both self-hosted workflows or workflow services that use <xref:System.Activities.WorkflowApplication> or <xref:System.ServiceModel.WorkflowServiceHost> as well as services hosted in WAS using <xref:System.ServiceModel.WorkflowServiceHost>.</span></span> <span data-ttu-id="aa3fa-107">기능에 의해 노출되는 개체 모델을 사용하여 자체 호스팅 서비스에 대한 SQL 워크플로 인스턴스 저장소 기능을 프로그래밍 방식으로 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aa3fa-107">You can configure the SQL Workflow Instance Store feature for self-hosted services programmatically by using the object model exposed by the feature.</span></span> <span data-ttu-id="aa3fa-108">개체 모델 및 XML 구성 파일을 사용하고 프로그래밍 방식으로 <xref:System.ServiceModel.WorkflowServiceHost>에 의해 호스트되는 서비스에 대해 이 기능을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aa3fa-108">You can configure this feature for services hosted by <xref:System.ServiceModel.WorkflowServiceHost> both programmatically by using the object model and also by using an XML configuration file.</span></span>  
  
 <span data-ttu-id="aa3fa-109">SQL 워크플로 인스턴스 저장소 기능 (**SqlWorkflowInstanceStore** 클래스)를 구현 하지 않습니다 <xref:System.ServiceModel.Persistence.PersistenceProviderFactory> 및 장기 실행 워크플로가 아닌 WCF 서비스에 대 한 지 속성 지원을 제공 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="aa3fa-109">The SQL Workflow Instance Store feature (**SqlWorkflowInstanceStore** class) does not implement <xref:System.ServiceModel.Persistence.PersistenceProviderFactory> and hence does not offer persistence support for durable non-workflow WCF services.</span></span> <span data-ttu-id="aa3fa-110">이 기능은 <xref:System.Workflow.Runtime.Hosting.WorkflowPersistenceService>도 구현하지 않으므로 3.x 워크플로에 대한 지속성 지원을 제공하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="aa3fa-110">It also does not implement <xref:System.Workflow.Runtime.Hosting.WorkflowPersistenceService> and hence does not offer persistence support for 3.x workflows.</span></span> <span data-ttu-id="aa3fa-111">이 기능은 WF 4.0 이상 워크플로 및 워크플로 서비스에 대해서만 지속성을 지원하며,</span><span class="sxs-lookup"><span data-stu-id="aa3fa-111">The feature supports persistence for only WF 4.0 (and later) workflows and workflow services.</span></span> <span data-ttu-id="aa3fa-112">SQL Server 2005 및 SQL Server 2008 이외의 다른 데이터베이스를 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="aa3fa-112">The feature also does not support any databases other than SQL Server 2005 and SQL Server 2008.</span></span>  
  
 <span data-ttu-id="aa3fa-113">이 단원의 항목에서는 SQL 워크플로 인스턴스 저장소의 속성과 기능을 설명하고 저장소 구성에 대한 세부 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="aa3fa-113">The topics in this section describe properties and features of the SQL Workflow Instance Store and provide you with details on configuring the store.</span></span>  
  
 <span data-ttu-id="aa3fa-114">Windows Server AppFabric은 고유의 인스턴스 저장소 및 도구를 제공하여 구성 및 인스턴스 저장소의 사용을 단순화합니다.</span><span class="sxs-lookup"><span data-stu-id="aa3fa-114">Windows Server App Fabric provides its own instance store and tooling to simplify the configuration and use of the instance store.</span></span> <span data-ttu-id="aa3fa-115">자세한 내용은 [Windows Server App Fabric 인스턴스 스토어](https://go.microsoft.com/fwlink/?LinkId=201201)합니다.</span><span class="sxs-lookup"><span data-stu-id="aa3fa-115">For more information, see [Windows Server App Fabric Instance Store](https://go.microsoft.com/fwlink/?LinkId=201201).</span></span> <span data-ttu-id="aa3fa-116">App Fabric SQL Server 지 속성 데이터베이스 참조에 대 한 자세한 내용은 [App Fabric SQL Server 지 속성 데이터베이스](https://go.microsoft.com/fwlink/?LinkId=201202)</span><span class="sxs-lookup"><span data-stu-id="aa3fa-116">For more information about the App Fabric SQL Server Persistence Database see [App Fabric SQL Server Persistence Database](https://go.microsoft.com/fwlink/?LinkId=201202)</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="aa3fa-117">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="aa3fa-117">In This Section</span></span>  
  
-   [<span data-ttu-id="aa3fa-118">SQL 워크플로 인스턴스 저장소의 속성</span><span class="sxs-lookup"><span data-stu-id="aa3fa-118">Properties of SQL Workflow Instance Store</span></span>](properties-of-sql-workflow-instance-store.md)  
  
-   [<span data-ttu-id="aa3fa-119">방법: 워크플로 및 워크플로 서비스에 대 한 SQL 지 속성 사용</span><span class="sxs-lookup"><span data-stu-id="aa3fa-119">How to: Enable SQL Persistence for Workflows and Workflow Services</span></span>](how-to-enable-sql-persistence-for-workflows-and-workflow-services.md)  
  
-   [<span data-ttu-id="aa3fa-120">인스턴스 활성화</span><span class="sxs-lookup"><span data-stu-id="aa3fa-120">Instance Activation</span></span>](instance-activation.md)  
  
-   [<span data-ttu-id="aa3fa-121">쿼리 지원</span><span class="sxs-lookup"><span data-stu-id="aa3fa-121">Support for Queries</span></span>](support-for-queries.md)  
  
-   [<span data-ttu-id="aa3fa-122">저장소 확장성</span><span class="sxs-lookup"><span data-stu-id="aa3fa-122">Store Extensibility</span></span>](store-extensibility.md)  
  
-   [<span data-ttu-id="aa3fa-123">보안</span><span class="sxs-lookup"><span data-stu-id="aa3fa-123">Security</span></span>](security.md)  
  
-   [<span data-ttu-id="aa3fa-124">SQL Server 지속성 데이터베이스</span><span class="sxs-lookup"><span data-stu-id="aa3fa-124">SQL Server Persistence Database</span></span>](sql-server-persistence-database.md)  
  
## <a name="see-also"></a><span data-ttu-id="aa3fa-125">참고자료</span><span class="sxs-lookup"><span data-stu-id="aa3fa-125">See also</span></span>
- [<span data-ttu-id="aa3fa-126">지 속성 샘플</span><span class="sxs-lookup"><span data-stu-id="aa3fa-126">Persistence Samples</span></span>](https://go.microsoft.com/fwlink/?LinkID=177735)
