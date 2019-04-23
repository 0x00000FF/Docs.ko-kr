---
title: 외래 키 속성
ms.date: 03/30/2017
ms.assetid: 23cb6729-544d-4f67-9ee7-44e8a6545587
ms.openlocfilehash: 74117b30ca54f7c57bd970003fc6f5dcc54d553f
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59218019"
---
# <a name="foreign-key-property"></a><span data-ttu-id="6977b-102">외래 키 속성</span><span class="sxs-lookup"><span data-stu-id="6977b-102">foreign key property</span></span>
<span data-ttu-id="6977b-103">A *외래 키 속성* 엔터티 데이터 모델 (EDM)의 기본 형식인 [속성](../../../../docs/framework/data/adonet/property.md) (또는 기본 형식 속성 집합)에 [엔터티 형식](../../../../docs/framework/data/adonet/entity-type.md) 를포함하는[엔터티 키](../../../../docs/framework/data/adonet/entity-key.md) 다른 엔터티 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="6977b-103">A *foreign key property* in the Entity Data Model (EDM) is a primitive type [property](../../../../docs/framework/data/adonet/property.md) (or a set of primitive type properties) on an [entity type](../../../../docs/framework/data/adonet/entity-type.md) that contains the [entity key](../../../../docs/framework/data/adonet/entity-key.md) of another entity type.</span></span>  
  
 <span data-ttu-id="6977b-104">외래 키 속성은 관계형 데이터베이스의 외래 키 열과 유사합니다.</span><span class="sxs-lookup"><span data-stu-id="6977b-104">A foreign key property is analogous to a foreign key column in a relational database.</span></span> <span data-ttu-id="6977b-105">테이블의 행 간의 관계를 만들려면 관계형 데이터베이스의 외래 키 열을 사용 된 동일한 방식으로 개념적 모델에서 외래 키 속성을 설정 하 되 [연결](../../../../docs/framework/data/adonet/association-type.md) 엔터티 형식 간의 합니다.</span><span class="sxs-lookup"><span data-stu-id="6977b-105">In the same way that foreign key columns are used in a relational database to create relationships between rows in tables, foreign key properties in a conceptual model are used to establish [associations](../../../../docs/framework/data/adonet/association-type.md) between entity types.</span></span> <span data-ttu-id="6977b-106">A [참조 무결성 제약 조건](../../../../docs/framework/data/adonet/referential-integrity-constraint.md) 형식 중 하나에 외래 키 속성이 경우 두 엔터티 형식 간의 연결을 정의 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6977b-106">A [referential integrity constraint](../../../../docs/framework/data/adonet/referential-integrity-constraint.md) is used to define an association between two entity types when one of the types has a foreign key property.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6977b-107">예제</span><span class="sxs-lookup"><span data-stu-id="6977b-107">Example</span></span>  
 <span data-ttu-id="6977b-108">다음 다이어그램에서는 세 가지 엔터티 형식 `Book`, `Publisher` 및 `Author`가 포함된 개념적 모델을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="6977b-108">The diagram below shows a conceptual model with three entity types: `Book`, `Publisher`, and `Author`.</span></span> <span data-ttu-id="6977b-109">`Book` 엔터티 형식에는 `PublisherId` 연결에 참조 무결성 제약 조건을 정의할 때 `Publisher` 엔터티 형식의 엔터티 키를 참조하는 `PublishedBy` 속성이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6977b-109">The `Book` entity type has a property, `PublisherId`, that references the entity key of the `Publisher` entity type when you define a referential integrity constraint on the `PublishedBy` association.</span></span>  
  
 <span data-ttu-id="6977b-110">![RefConstraintModel](./media/foreign-key-property/reference-constraint-model.gif "참조 제약 조건이 모델의 예")</span><span class="sxs-lookup"><span data-stu-id="6977b-110">![RefConstraintModel](./media/foreign-key-property/reference-constraint-model.gif "Example of a referential constraint model")</span></span>  
  
 <span data-ttu-id="6977b-111">합니다 [ADO.NET Entity Framework](../../../../docs/framework/data/adonet/ef/index.md) 개념 스키마 정의 언어를 호출 하는 도메인 특정 언어 (DSL)를 사용 하 여 ([CSDL](../../../../docs/framework/data/adonet/ef/language-reference/csdl-specification.md)) 개념적 모델을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="6977b-111">The [ADO.NET Entity Framework](../../../../docs/framework/data/adonet/ef/index.md) uses a domain-specific language (DSL) called conceptual schema definition language ([CSDL](../../../../docs/framework/data/adonet/ef/language-reference/csdl-specification.md)) to define conceptual models.</span></span> <span data-ttu-id="6977b-112">다음 CSDL에서는 외래 키 속성 `PublisherId`를 사용하여 위의 개념적 모델에 표시된 `PublishedBy` 연결에 참조 무결성 제약 조건을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="6977b-112">The following CSDL uses the foreign key property `PublisherId` to define a referential integrity constraint on the `PublishedBy` association shown in the conceptual model shown above.</span></span>  
  
 [!code-xml[EDM_Example_Model#RefConstraint](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books4.edmx#refconstraint)]  
  
## <a name="see-also"></a><span data-ttu-id="6977b-113">참고자료</span><span class="sxs-lookup"><span data-stu-id="6977b-113">See also</span></span>

- [<span data-ttu-id="6977b-114">엔터티 데이터 모델의 주요 개념</span><span class="sxs-lookup"><span data-stu-id="6977b-114">Entity Data Model Key Concepts</span></span>](../../../../docs/framework/data/adonet/entity-data-model-key-concepts.md)
- [<span data-ttu-id="6977b-115">엔터티 데이터 모델</span><span class="sxs-lookup"><span data-stu-id="6977b-115">Entity Data Model</span></span>](../../../../docs/framework/data/adonet/entity-data-model.md)
