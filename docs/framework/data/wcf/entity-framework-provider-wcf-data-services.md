---
title: "Entity Framework 공급자(WCF Data Services)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework-oob
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- WCF Data Services, providers
ms.assetid: 650b5eb6-c71d-4dc1-8b64-b6beaf752114
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: bc27663904371991855b2fe7d96b4a15827d1180
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="entity-framework-provider-wcf-data-services"></a><span data-ttu-id="87a28-102">Entity Framework 공급자(WCF Data Services)</span><span class="sxs-lookup"><span data-stu-id="87a28-102">Entity Framework Provider (WCF Data Services)</span></span>
<span data-ttu-id="87a28-103">[!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)]와 마찬가지로 ADO.NET Entity Framework는 엔터티-관계 모델의 한 형식인 엔터티 데이터 모델을 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="87a28-103">Like [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)], the ADO.NET Entity Framework is based on the Entity Data Model, which is a type of entity-relationship model.</span></span> <span data-ttu-id="87a28-104">Entity Framework 변환 이라고 부르는 엔터티 데이터 모델의 구현에 대 한 작업의 *개념적 모델*, 데이터 원본에 대 한 동등한 작업으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="87a28-104">The Entity Framework translates operations against its implementation of the Entity Data Model, which is called the *conceptual model*, into equivalent operations against a data source.</span></span> <span data-ttu-id="87a28-105">따라서 Entity Framework는 관계형 데이터를 기반으로 하는 데이터 서비스에 적합한 공급자이며, Entity Framework를 지원하는 데이터 공급자가 있는 모든 데이터베이스를 [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)]와 함께 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="87a28-105">This makes the Entity Framework an ideal provider for data services that are based on relational data, and any database that has a data provider that supports the Entity Framework can be used with [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)].</span></span> <span data-ttu-id="87a28-106">목록이 현재 Entity Framework를 지원 되는 데이터 원본에 대 한 참조 [Entity Framework 용 타사 공급자](http://go.microsoft.com/fwlink/?LinkId=143699)합니다.</span><span class="sxs-lookup"><span data-stu-id="87a28-106">For a list of the data sources that currently support the Entity Framework, see [Third-Party Providers for the Entity Framework](http://go.microsoft.com/fwlink/?LinkId=143699).</span></span>  
  
 <span data-ttu-id="87a28-107">개념적 모델에서 엔터티 컨테이너는 서비스 루트입니다.</span><span class="sxs-lookup"><span data-stu-id="87a28-107">In a conceptual model, the entity container is the root of the service.</span></span> <span data-ttu-id="87a28-108">먼저 Entity Framework에서 개념적 모델을 정의해야 데이터 서비스가 데이터를 노출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="87a28-108">You must define a conceptual model in the Entity Framework before the data can be exposed by a data service.</span></span> <span data-ttu-id="87a28-109">자세한 내용은 참조 [하는 방법: ADO.NET Entity Framework 데이터 소스를 사용 하 여 데이터 서비스 만들기](../../../../docs/framework/data/wcf/create-a-data-service-using-an-adonet-ef-data-wcf.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="87a28-109">For more information, see [How to: Create a Data Service Using an ADO.NET Entity Framework Data Source](../../../../docs/framework/data/wcf/create-a-data-service-using-an-adonet-ef-data-wcf.md).</span></span>  
  
 [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)]<span data-ttu-id="87a28-110">엔터티의 동시성 토큰을 정의할 수 있도록 하 여 낙관적 동시성 모델을 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="87a28-110"> supports the optimistic concurrency model by enabling you to define a concurrency token for an entity.</span></span> <span data-ttu-id="87a28-111">엔터티의 속성을 하나 이상 포함하는 이 동시성 토큰은 요청되거나 업데이트 또는 삭제되고 있는 데이터가 변경되었는지 여부를 데이터 서비스에서 확인하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="87a28-111">This concurrency token, which includes one or more properties of the entity, is used by the data service to determine whether a change has occurred in the data that is being requested, updated, or deleted.</span></span> <span data-ttu-id="87a28-112">요청의 eTag에서 가져온 토큰 값이 엔터티의 현재 값과 다르면 데이터 서비스에서 예외가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="87a28-112">When token values obtained from the eTag in the request differ from the current values of the entity, an exception is raised by the data service.</span></span> <span data-ttu-id="87a28-113">속성이 동시성 토큰의 일부임을 나타내려면 `ConcurrencyMode="Fixed"` 공급자가 정의하는 데이터 모델에서 [!INCLUDE[adonet_ef](../../../../includes/adonet-ef-md.md)] 특성을 적용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="87a28-113">To indicate that a property is part of the concurrency token, you must apply the attribute `ConcurrencyMode="Fixed"` in the data model defined by the [!INCLUDE[adonet_ef](../../../../includes/adonet-ef-md.md)] provider.</span></span> <span data-ttu-id="87a28-114">동시성 토큰에는 키 속성이나 탐색 속성이 포함될 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="87a28-114">The concurrency token cannot include a key property or a navigation property.</span></span> <span data-ttu-id="87a28-115">자세한 내용은 참조 [데이터 서비스 업데이트](../../../../docs/framework/data/wcf/updating-the-data-service-wcf-data-services.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="87a28-115">For more information, see [Updating the Data Service](../../../../docs/framework/data/wcf/updating-the-data-service-wcf-data-services.md).</span></span>  
  
 <span data-ttu-id="87a28-116">Entity Framework에 대 한 자세한 참조 [Entity Framework 개요](../../../../docs/framework/data/adonet/ef/overview.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="87a28-116">To learn more about the Entity Framework, see [Entity Framework Overview](../../../../docs/framework/data/adonet/ef/overview.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="87a28-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="87a28-117">See Also</span></span>  
 [<span data-ttu-id="87a28-118">Data Services 공급자</span><span class="sxs-lookup"><span data-stu-id="87a28-118">Data Services Providers</span></span>](../../../../docs/framework/data/wcf/data-services-providers-wcf-data-services.md)  
 [<span data-ttu-id="87a28-119">리플렉션 공급자</span><span class="sxs-lookup"><span data-stu-id="87a28-119">Reflection Provider</span></span>](../../../../docs/framework/data/wcf/reflection-provider-wcf-data-services.md)  
 [<span data-ttu-id="87a28-120">엔터티 데이터 모델</span><span class="sxs-lookup"><span data-stu-id="87a28-120">Entity Data Model</span></span>](../../../../docs/framework/data/adonet/entity-data-model.md)
