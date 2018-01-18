---
title: "연결 집합 End"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: fe4bf1d3-047a-4a37-98c5-a66e70811346
caps.latest.revision: "4"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: 85b4bd732d9de987676bae70f7749a1dd9dc76c5
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/17/2018
---
# <a name="association-set-end"></a><span data-ttu-id="93b5c-102">연결 집합 End</span><span class="sxs-lookup"><span data-stu-id="93b5c-102">association set end</span></span>
<span data-ttu-id="93b5c-103">*연결 집합 end* 식별 된 [엔터티 형식](../../../../docs/framework/data/adonet/entity-type.md) 및 [엔터티 집합](../../../../docs/framework/data/adonet/entity-set.md) 의 끝에는 [연결 집합](../../../../docs/framework/data/adonet/association-set.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="93b5c-103">An *association set end* identifies the [entity type](../../../../docs/framework/data/adonet/entity-type.md) and the [entity set](../../../../docs/framework/data/adonet/entity-set.md) at the end of an [association set](../../../../docs/framework/data/adonet/association-set.md).</span></span> <span data-ttu-id="93b5c-104">연결 집합 End는 연결 집합의 일부로 정의되고 연결 집합에는 정확히 두 개의 연결 집합 End가 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="93b5c-104">Association set ends are defined as part of an association set; an association set must have exactly two association set ends.</span></span>  
  
 <span data-ttu-id="93b5c-105">연결 집합 End 정의에는 다음 정보가 들어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="93b5c-105">An association set end definition contains the following information:</span></span>  
  
-   <span data-ttu-id="93b5c-106">연결 집합과 관련된 엔터티 형식 중 하나</span><span class="sxs-lookup"><span data-stu-id="93b5c-106">One of the entity types involved in the association set.</span></span> <span data-ttu-id="93b5c-107">(필수)</span><span class="sxs-lookup"><span data-stu-id="93b5c-107">(Required)</span></span>  
  
-   <span data-ttu-id="93b5c-108">연결 집합과 관련된 엔터티 형식에 대한 엔터티 집합</span><span class="sxs-lookup"><span data-stu-id="93b5c-108">The entity set for the entity type involved in the association set.</span></span> <span data-ttu-id="93b5c-109">(필수)</span><span class="sxs-lookup"><span data-stu-id="93b5c-109">(Required)</span></span>  
  
## <a name="example"></a><span data-ttu-id="93b5c-110">예제</span><span class="sxs-lookup"><span data-stu-id="93b5c-110">Example</span></span>  
 <span data-ttu-id="93b5c-111">다음 다이어그램에서는 두 연결 `WrittenBy` 및 `PublishedBy`의 개념적 모델을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="93b5c-111">The diagram below shows a conceptual model with two associations: `WrittenBy` and `PublishedBy`.</span></span>  
  
 <span data-ttu-id="93b5c-112">![예제 모델](../../../../docs/framework/data/adonet/media/examplemodel.gif "ExampleModel")</span><span class="sxs-lookup"><span data-stu-id="93b5c-112">![Example Model](../../../../docs/framework/data/adonet/media/examplemodel.gif "ExampleModel")</span></span>  
  
 <span data-ttu-id="93b5c-113">다음 다이어그램에서는 위에 나온 개념적 모델을 기반으로 하여 하나의 연결 집합(`PublishedBy`) 및 두 개의 엔터티 집합(`Books` 및 `Publishers`)을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="93b5c-113">The following diagram shows an association set (`PublishedBy`) and two entity sets (`Books` and `Publishers`) based on the conceptual model shown above.</span></span> <span data-ttu-id="93b5c-114">연결 집합 End는 `Books` 및 `Publishers` 엔터티 집합입니다.</span><span class="sxs-lookup"><span data-stu-id="93b5c-114">The association set ends are the `Books` and `Publishers` entity sets.</span></span> <span data-ttu-id="93b5c-115">bi는 `Books` 엔터티 집합의 인스턴스를 나타내며는 `Book` 런타임 시 엔터티 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="93b5c-115">Bi in the `Books` entity set represents an instance of the `Book` entity type at run time.</span></span> <span data-ttu-id="93b5c-116">마찬가지로, Pj 나타냅니다는 `Publisher` 인스턴스는 `Publishers` 엔터티 집합입니다.</span><span class="sxs-lookup"><span data-stu-id="93b5c-116">Similarly, Pj represents a `Publisher` instance in the `Publishers` entity set.</span></span> <span data-ttu-id="93b5c-117">BiPj의 인스턴스를 나타내며는 `PublishedBy` 에서 연결의 `PublishedBy` 연결 집합입니다.</span><span class="sxs-lookup"><span data-stu-id="93b5c-117">BiPj represents an instance of the `PublishedBy` association in the `PublishedBy` association set.</span></span>  
  
 <span data-ttu-id="93b5c-118">![예제 설정](../../../../docs/framework/data/adonet/media/setsexample.gif "SetsExample")</span><span class="sxs-lookup"><span data-stu-id="93b5c-118">![Sets Example](../../../../docs/framework/data/adonet/media/setsexample.gif "SetsExample")</span></span>  
  
 <span data-ttu-id="93b5c-119">[ADO.NET Entity Framework](../../../../docs/framework/data/adonet/ef/index.md) 개념 스키마 정의 언어 이라고 하는 DSL을 사용 하 여 ([CSDL](../../../../docs/framework/data/adonet/ef/language-reference/csdl-specification.md)) 개념적 모델을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="93b5c-119">The [ADO.NET Entity Framework](../../../../docs/framework/data/adonet/ef/index.md) uses a DSL called conceptual schema definition language ([CSDL](../../../../docs/framework/data/adonet/ef/language-reference/csdl-specification.md)) to define conceptual models.</span></span> <span data-ttu-id="93b5c-120">다음 CSDL에서는 위의 다이어그램에 있는 각 연결에 대한 하나의 연결 집합을 사용하여 엔터티 컨테이너를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="93b5c-120">The following CSDL defines an entity container with one association set for each association in the diagram above.</span></span> <span data-ttu-id="93b5c-121">연결 집합 End는 각 연결 집합 정의의 일부로 정의되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="93b5c-121">Note that association set ends are defined as part of each association set definition.</span></span>  
  
 [!code-xml[EDM_Example_Model#EntityContainerExample](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books.edmx#entitycontainerexample)]  
  
## <a name="see-also"></a><span data-ttu-id="93b5c-122">참고 항목</span><span class="sxs-lookup"><span data-stu-id="93b5c-122">See Also</span></span>  
 [<span data-ttu-id="93b5c-123">엔터티 데이터 모델의 주요 개념</span><span class="sxs-lookup"><span data-stu-id="93b5c-123">Entity Data Model Key Concepts</span></span>](../../../../docs/framework/data/adonet/entity-data-model-key-concepts.md)  
 [<span data-ttu-id="93b5c-124">엔터티 데이터 모델</span><span class="sxs-lookup"><span data-stu-id="93b5c-124">Entity Data Model</span></span>](../../../../docs/framework/data/adonet/entity-data-model.md)
