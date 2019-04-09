---
title: 엔터티 집합
ms.date: 03/30/2017
ms.assetid: 59ec6ab0-88e5-4d25-b112-7a4eccbe61f0
ms.openlocfilehash: 7fcaa2cb9bac02271940a712d4d044df25d7d4cf
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59126622"
---
# <a name="entity-set"></a><span data-ttu-id="d56f2-102">엔터티 집합</span><span class="sxs-lookup"><span data-stu-id="d56f2-102">entity set</span></span>
<span data-ttu-id="d56f2-103">*엔터티 집합* 는 대 한 논리적 컨테이너의 인스턴스를 [엔터티 형식](../../../../docs/framework/data/adonet/entity-type.md) 및 해당 엔터티 형식에서 파생 된 유형의 인스턴스.</span><span class="sxs-lookup"><span data-stu-id="d56f2-103">An *entity set* is a logical container for instances of an [entity type](../../../../docs/framework/data/adonet/entity-type.md) and instances of any type derived from that entity type.</span></span> <span data-ttu-id="d56f2-104">(파생된 형식에 대 한 정보를 참조 하세요. [엔터티 데이터 모델: 상속](../../../../docs/framework/data/adonet/entity-data-model-inheritance.md).) 엔터티 형식과 엔터티 집합 간의 관계를 행과 관계형 데이터베이스에서 테이블 간의 관계와 비슷합니다. 행과 같이 데이터 구조를 설명 하는 엔터티 형식 및 테이블과 같이 엔터티 집합을 지정한 구조체의 인스턴스를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="d56f2-104">(For information about derived types, see [Entity Data Model: Inheritance](../../../../docs/framework/data/adonet/entity-data-model-inheritance.md).) The relationship between an entity type and an entity set is analogous to the relationship between a row and a table in a relational database: Like a row, an entity type describes data structure, and, like a table, an entity set contains instances of a given structure.</span></span> <span data-ttu-id="d56f2-105">엔터티 집합은 데이터 모델링 구문이 아니며 데이터 구조를 설명하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d56f2-105">An entity set is not a data modeling construct; it does not describe the structure of data.</span></span> <span data-ttu-id="d56f2-106">대신 엔터티 집합은 엔터티 형식 인스턴스를 그룹화하여 데이터 저장소에 매핑할 수 있도록 호스팅 또는 저장소 환경(예: 공용 언어 런타임 또는 SQL Server 데이터베이스)에 대한 구문을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="d56f2-106">Instead, an entity set provides a construct for a hosting or storage environment (such as the common language runtime or a SQL Server database) to group entity type instances so that they can be mapped to a data store.</span></span>  
  
 <span data-ttu-id="d56f2-107">엔터티 집합 내에 정의 되어는 [엔터티 컨테이너](../../../../docs/framework/data/adonet/entity-container.md), 엔터티 집합의 논리적 그룹인 및 [연결 집합](../../../../docs/framework/data/adonet/association-set.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="d56f2-107">An entity set is defined within an [entity container](../../../../docs/framework/data/adonet/entity-container.md), which is a logical grouping of entity sets and [association sets](../../../../docs/framework/data/adonet/association-set.md).</span></span>  
  
 <span data-ttu-id="d56f2-108">엔터티 형식 인스턴스가 엔터티 집합에 있으려면 다음 조건을 충족해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d56f2-108">For an entity type instance to exist in an entity set, the following must be true:</span></span>  
  
-   <span data-ttu-id="d56f2-109">인스턴스 형식이 엔터티 집합의 기반이 되는 엔터티 형식과 같거나 인스턴스 형식이 엔터티 형식의 하위 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="d56f2-109">The type of the instance is either the same as the entity type on which the entity set is based, or the type of the instance is a subtype of the entity type.</span></span>  
  
-   <span data-ttu-id="d56f2-110">합니다 [엔터티 키](../../../../docs/framework/data/adonet/entity-key.md) 인스턴스는 엔터티 집합 내에서 고유 합니다.</span><span class="sxs-lookup"><span data-stu-id="d56f2-110">The [entity key](../../../../docs/framework/data/adonet/entity-key.md) for the instance is unique within the entity set.</span></span>  
  
-   <span data-ttu-id="d56f2-111">인스턴스가 다른 엔터티 집합에 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d56f2-111">The instance does not exist in any other entity set.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="d56f2-112">같은 엔터티 형식을 사용하여 여러 엔터티 집합을 정의할 수 있지만 지정된 엔터티 형식의 인스턴스는 하나의 엔터티 집합에만 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d56f2-112">Multiple entity sets can be defined using the same entity type, but an instance of a given entity type can only exist in one entity set.</span></span>  
  
 <span data-ttu-id="d56f2-113">개념적 모델의 각 엔터티 형식에 대해 엔터티 집합을 정의할 필요는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d56f2-113">You do not have to define an entity set for each entity type in a conceptual model.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d56f2-114">예제</span><span class="sxs-lookup"><span data-stu-id="d56f2-114">Example</span></span>  
 <span data-ttu-id="d56f2-115">다음 다이어그램에서는 세 가지 엔터티 형식 `Book`, `Publisher` 및 `Author`가 포함된 개념적 모델을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="d56f2-115">The diagram below shows a conceptual model with three entity types: `Book`, `Publisher`, and `Author`.</span></span>  
  
 ![세 가지 엔터티 형식을 사용 하 여 예제 모델](./media/entity-set/example-model-three-entity-types.gif)  
  
 <span data-ttu-id="d56f2-117">다음 다이어그램에서는 위에 표시된 개념적 모델을 기반으로 하여 엔터티 집합 두 개(`Books` 및 `Publishers`)와 연결 집합(`PublishedBy`)을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="d56f2-117">The following diagram shows two entity sets (`Books` and `Publishers`) and an association set (`PublishedBy`) based on the conceptual model shown above.</span></span> <span data-ttu-id="d56f2-118">bi 합니다 `Books` 엔터티 집합의 인스턴스를 나타냅니다는 `Book` 런타임에 엔터티 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="d56f2-118">Bi in the `Books` entity set represents an instance of the `Book` entity type at run time.</span></span> <span data-ttu-id="d56f2-119">Pj 나타내는 마찬가지로 `Publisher` 의 인스턴스는 `Publishers` 엔터티 집합입니다.</span><span class="sxs-lookup"><span data-stu-id="d56f2-119">Similarly, Pj represent a `Publisher` instance in the `Publishers` entity set.</span></span> <span data-ttu-id="d56f2-120">BiPj의 인스턴스를 나타냅니다 합니다 `PublishedBy` 의 연결을 `PublishedBy` 연결 집합입니다.</span><span class="sxs-lookup"><span data-stu-id="d56f2-120">BiPj represents an instance of the `PublishedBy` association in the `PublishedBy` association set.</span></span>  
  
 ![집합 예제를 보여 주는 스크린샷.](./media/entity-set/sets-example-association.gif)  
  
 <span data-ttu-id="d56f2-122">합니다 [ADO.NET Entity Framework](../../../../docs/framework/data/adonet/ef/index.md) 개념 스키마 정의 언어를 호출 하는 도메인 특정 언어 (DSL)를 사용 하 여 ([CSDL](../../../../docs/framework/data/adonet/ef/language-reference/csdl-specification.md)) 개념적 모델을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="d56f2-122">The [ADO.NET Entity Framework](../../../../docs/framework/data/adonet/ef/index.md) uses a domain-specific language (DSL) called conceptual schema definition language ([CSDL](../../../../docs/framework/data/adonet/ef/language-reference/csdl-specification.md)) to define conceptual models.</span></span> <span data-ttu-id="d56f2-123">다음 CSDL에서는 위에 표시된 개념적 모델의 각 엔터티 형식에 대해 하나의 엔터티 집합이 있는 엔터티 컨테이너를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="d56f2-123">The following CSDL defines an entity container with one entity set for each entity type in the conceptual model shown above.</span></span> <span data-ttu-id="d56f2-124">각 엔터티 집합의 이름과 엔터티 형식은 XML 특성을 사용하여 정의됩니다.</span><span class="sxs-lookup"><span data-stu-id="d56f2-124">Note that the name and entity type for each entity set are defined using XML attributes.</span></span>  
  
 [!code-xml[EDM_Example_Model#EntityContainerExample](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books.edmx#entitycontainerexample)]  
  
 <span data-ttu-id="d56f2-125">형식당 여러 엔터티 집합(MEST)을 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d56f2-125">It is possible to define multiple entity sets per type (MEST).</span></span> <span data-ttu-id="d56f2-126">다음 CSDL에서는 `Book` 엔터티 형식에 대한 두 개의 엔터티 집합이 있는 엔터티 컨테이너를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="d56f2-126">The following CSDL defines an entity container with two entity sets for the `Book` entity type:</span></span>  
  
 [!code-xml[EDM_Example_Model#MESTExample](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books2.edmx#mestexample)]  
  
## <a name="see-also"></a><span data-ttu-id="d56f2-127">참고자료</span><span class="sxs-lookup"><span data-stu-id="d56f2-127">See also</span></span>

- [<span data-ttu-id="d56f2-128">엔터티 데이터 모델의 주요 개념</span><span class="sxs-lookup"><span data-stu-id="d56f2-128">Entity Data Model Key Concepts</span></span>](../../../../docs/framework/data/adonet/entity-data-model-key-concepts.md)
- [<span data-ttu-id="d56f2-129">엔터티 데이터 모델</span><span class="sxs-lookup"><span data-stu-id="d56f2-129">Entity Data Model</span></span>](../../../../docs/framework/data/adonet/entity-data-model.md)
