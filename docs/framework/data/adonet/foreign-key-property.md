---
title: 외래 키 속성
ms.date: 03/30/2017
ms.assetid: 23cb6729-544d-4f67-9ee7-44e8a6545587
ms.openlocfilehash: e2f41c2db9aea26c7954a99ebf3f40b03e8df735
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/07/2019
ms.locfileid: "70795032"
---
# <a name="foreign-key-property"></a><span data-ttu-id="dc80d-102">외래 키 속성</span><span class="sxs-lookup"><span data-stu-id="dc80d-102">foreign key property</span></span>
<span data-ttu-id="dc80d-103">EDM (엔터티 데이터 모델)의 *외래 키 속성* 은 다른 엔터티 형식의 [엔터티 키](entity-key.md) 를 포함 하는 [엔터티 형식](entity-type.md) 에 대 한 기본 형식 [속성](property.md) (또는 기본 형식 속성 집합)입니다.</span><span class="sxs-lookup"><span data-stu-id="dc80d-103">A *foreign key property* in the Entity Data Model (EDM) is a primitive type [property](property.md) (or a set of primitive type properties) on an [entity type](entity-type.md) that contains the [entity key](entity-key.md) of another entity type.</span></span>  
  
 <span data-ttu-id="dc80d-104">외래 키 속성은 관계형 데이터베이스의 외래 키 열과 유사합니다.</span><span class="sxs-lookup"><span data-stu-id="dc80d-104">A foreign key property is analogous to a foreign key column in a relational database.</span></span> <span data-ttu-id="dc80d-105">관계형 데이터베이스에서 외래 키 열을 사용 하 여 테이블의 행 간 관계를 만드는 것과 마찬가지로 개념적 모델의 외래 키 속성은 엔터티 형식 간의 [연결](association-type.md) 을 설정 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="dc80d-105">In the same way that foreign key columns are used in a relational database to create relationships between rows in tables, foreign key properties in a conceptual model are used to establish [associations](association-type.md) between entity types.</span></span> <span data-ttu-id="dc80d-106">[참조 무결성 제약 조건은](referential-integrity-constraint.md) 형식 중 하나에 외래 키 속성이 있는 경우 두 엔터티 형식 간의 연결을 정의 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="dc80d-106">A [referential integrity constraint](referential-integrity-constraint.md) is used to define an association between two entity types when one of the types has a foreign key property.</span></span>  
  
## <a name="example"></a><span data-ttu-id="dc80d-107">예제</span><span class="sxs-lookup"><span data-stu-id="dc80d-107">Example</span></span>  
 <span data-ttu-id="dc80d-108">다음 다이어그램에서는 세 가지 엔터티 형식 `Book`, `Publisher` 및 `Author`가 포함된 개념적 모델을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="dc80d-108">The diagram below shows a conceptual model with three entity types: `Book`, `Publisher`, and `Author`.</span></span> <span data-ttu-id="dc80d-109">`Book` 엔터티 형식에는 `PublisherId` 연결에 참조 무결성 제약 조건을 정의할 때 `Publisher` 엔터티 형식의 엔터티 키를 참조하는 `PublishedBy` 속성이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dc80d-109">The `Book` entity type has a property, `PublisherId`, that references the entity key of the `Publisher` entity type when you define a referential integrity constraint on the `PublishedBy` association.</span></span>  
  
 <span data-ttu-id="dc80d-110">![RefConstraintModel](./media/foreign-key-property/reference-constraint-model.gif "참조 제약 조건 모델 예")</span><span class="sxs-lookup"><span data-stu-id="dc80d-110">![RefConstraintModel](./media/foreign-key-property/reference-constraint-model.gif "Example of a referential constraint model")</span></span>  
  
 <span data-ttu-id="dc80d-111">[ADO.NET Entity Framework](./ef/index.md) 에서는[CSDL](./ef/language-reference/csdl-specification.md)(개념 스키마 정의 언어) 이라는 DSL (도메인별 언어)을 사용 하 여 개념적 모델을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="dc80d-111">The [ADO.NET Entity Framework](./ef/index.md) uses a domain-specific language (DSL) called conceptual schema definition language ([CSDL](./ef/language-reference/csdl-specification.md)) to define conceptual models.</span></span> <span data-ttu-id="dc80d-112">다음 CSDL에서는 외래 키 속성 `PublisherId`를 사용하여 위의 개념적 모델에 표시된 `PublishedBy` 연결에 참조 무결성 제약 조건을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="dc80d-112">The following CSDL uses the foreign key property `PublisherId` to define a referential integrity constraint on the `PublishedBy` association shown in the conceptual model shown above.</span></span>  
  
 [!code-xml[EDM_Example_Model#RefConstraint](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books4.edmx#refconstraint)]  
  
## <a name="see-also"></a><span data-ttu-id="dc80d-113">참고자료</span><span class="sxs-lookup"><span data-stu-id="dc80d-113">See also</span></span>

- [<span data-ttu-id="dc80d-114">엔터티 데이터 모델의 주요 개념</span><span class="sxs-lookup"><span data-stu-id="dc80d-114">Entity Data Model Key Concepts</span></span>](entity-data-model-key-concepts.md)
- [<span data-ttu-id="dc80d-115">엔터티 데이터 모델</span><span class="sxs-lookup"><span data-stu-id="dc80d-115">Entity Data Model</span></span>](entity-data-model.md)
