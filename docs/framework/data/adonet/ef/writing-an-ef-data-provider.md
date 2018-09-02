---
title: Entity Framework 데이터 공급자 작성
ms.date: 03/30/2017
ms.assetid: 092e88c4-a301-453a-b5c3-5740c6575a9f
ms.openlocfilehash: 50c0555d84c5b5f180c8c49a8419e8a414a4befe
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/01/2018
ms.locfileid: "43401463"
---
# <a name="writing-an-entity-framework-data-provider"></a><span data-ttu-id="35c32-102">Entity Framework 데이터 공급자 작성</span><span class="sxs-lookup"><span data-stu-id="35c32-102">Writing an Entity Framework Data Provider</span></span>
<span data-ttu-id="35c32-103">이 섹션에서는 작성 하는 방법을 설명는 [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] 공급자를 SQL Server 이외의 데이터 소스를 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="35c32-103">This section discusses how to write an [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] provider to support a data source other than SQL Server.</span></span> <span data-ttu-id="35c32-104">[!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] SQL Server를 지 원하는 공급자를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="35c32-104">The [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] includes a provider that supports SQL Server.</span></span>  
  
## <a name="introducing-the-entity-framework-provider-model"></a><span data-ttu-id="35c32-105">Entity Framework 공급자 모델 소개</span><span class="sxs-lookup"><span data-stu-id="35c32-105">Introducing the Entity Framework Provider Model</span></span>  
 <span data-ttu-id="35c32-106">[!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)]는 데이터베이스와 독립적이므로 다양한 데이터 소스 집합에 연결하기 위해 ADO.NET 공급자 모델을 사용하여 공급자를 작성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="35c32-106">The [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] is database independent, and you can write a provider by using the ADO.NET Provider Model to connect to a diverse set of data sources.</span></span>  
  
 <span data-ttu-id="35c32-107">Entity Framework 데이터 공급자(ADO.NET 데이터 공급자 모델을 사용하여 작성됨)는 다음과 같은 기능을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="35c32-107">The Entity Framework data provider (built using the ADO.NET Data Provider model) performs the following functions:</span></span>  
  
-   <span data-ttu-id="35c32-108">EDM(엔터티 데이터 모델) 기본 형식을 공급자 형식에 매핑합니다.</span><span class="sxs-lookup"><span data-stu-id="35c32-108">Maps Entity Data Model (EDM) primitive types to provider types.</span></span>  
  
-   <span data-ttu-id="35c32-109">공급자별 함수를 노출합니다.</span><span class="sxs-lookup"><span data-stu-id="35c32-109">Exposes provider-specific functions.</span></span>  
  
-   <span data-ttu-id="35c32-110">[!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] 쿼리를 지원하기 위해 지정된 DbQueryCommandTree에 대한 공급자별 명령을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="35c32-110">Generates provider-specific commands for a given DbQueryCommandTree to support [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] queries.</span></span>  
  
-   <span data-ttu-id="35c32-111">[!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)]를 통한 업데이트를 지원하기 위해 지정된 DbModificationCommandTree에 대한 공급자별 업데이트 명령을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="35c32-111">Generates provider-specific update commands for a given DbModificationCommandTree to support updates through the [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)].</span></span>  
  
-   <span data-ttu-id="35c32-112">데이터베이스 기반의 모델 생성을 지원하기 위해 저장소 스키마 정의에 대한 매핑 파일을 노출합니다.</span><span class="sxs-lookup"><span data-stu-id="35c32-112">Exposes mapping files for the store schema definition, to support generation of a model based on a database.</span></span>  
  
-   <span data-ttu-id="35c32-113">개념적 모델을 통해 메타데이터(예: 테이블 및 뷰)를 노출합니다.</span><span class="sxs-lookup"><span data-stu-id="35c32-113">Exposes metadata (tables and views, for example) via a conceptual model.</span></span>  
  
 <span data-ttu-id="35c32-114">![b42a7a5c&#45;0ac0&#45;4911&#45;86be&#45;0460a78760ba](../../../../../docs/framework/data/adonet/ef/media/b42a7a5c-0ac0-4911-86be-0460a78760ba.gif "b42a7a5c-0ac0-4911-86be-0460a78760ba")</span><span class="sxs-lookup"><span data-stu-id="35c32-114">![b42a7a5c&#45;0ac0&#45;4911&#45;86be&#45;0460a78760ba](../../../../../docs/framework/data/adonet/ef/media/b42a7a5c-0ac0-4911-86be-0460a78760ba.gif "b42a7a5c-0ac0-4911-86be-0460a78760ba")</span></span>  
  
## <a name="sample"></a><span data-ttu-id="35c32-115">샘플</span><span class="sxs-lookup"><span data-stu-id="35c32-115">Sample</span></span>  
 <span data-ttu-id="35c32-116">참조를 [Entity Framework Sample Provider](https://go.microsoft.com/fwlink/?LinkId=180616) 의 예제는 [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] SQL Server 이외의 데이터 소스를 지 원하는 공급자입니다.</span><span class="sxs-lookup"><span data-stu-id="35c32-116">See the [Entity Framework Sample Provider](https://go.microsoft.com/fwlink/?LinkId=180616) for a sample of an [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] provider that supports a data source other than SQL Server.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="35c32-117">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="35c32-117">In This Section</span></span>  
 [<span data-ttu-id="35c32-118">SQL 생성</span><span class="sxs-lookup"><span data-stu-id="35c32-118">SQL Generation</span></span>](../../../../../docs/framework/data/adonet/ef/sql-generation.md)  
  
 [<span data-ttu-id="35c32-119">수정 SQL 생성</span><span class="sxs-lookup"><span data-stu-id="35c32-119">Modification SQL Generation</span></span>](../../../../../docs/framework/data/adonet/ef/modification-sql-generation.md)  
  
 [<span data-ttu-id="35c32-120">공급자 매니페스트 지정</span><span class="sxs-lookup"><span data-stu-id="35c32-120">Provider Manifest Specification</span></span>](../../../../../docs/framework/data/adonet/ef/provider-manifest-specification.md)  
  
## <a name="see-also"></a><span data-ttu-id="35c32-121">참고 항목</span><span class="sxs-lookup"><span data-stu-id="35c32-121">See Also</span></span>  
 [<span data-ttu-id="35c32-122">데이터 공급자 작업</span><span class="sxs-lookup"><span data-stu-id="35c32-122">Working with Data Providers</span></span>](../../../../../docs/framework/data/adonet/ef/working-with-data-providers.md)
