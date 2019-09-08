---
title: 연결 End 복합성
ms.date: 03/30/2017
ms.assetid: 340926ee-aefb-4bef-92cc-453e5251fd03
ms.openlocfilehash: cdcf69e7118620b2f8febd02d7695d429bf8cc2c
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/07/2019
ms.locfileid: "70786949"
---
# <a name="association-end-multiplicity"></a><span data-ttu-id="a47e2-102">연결 End 복합성</span><span class="sxs-lookup"><span data-stu-id="a47e2-102">association end multiplicity</span></span>
<span data-ttu-id="a47e2-103">*연결 end 복합성* 은 [연결](association-type.md)의 한 end에 있을 수 있는 [엔터티 형식](entity-type.md) 인스턴스 수를 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="a47e2-103">*Association end multiplicity* defines the number of [entity type](entity-type.md) instances that can be at one end of an [association](association-type.md).</span></span>  
  
 <span data-ttu-id="a47e2-104">연결 End 복합성은 다음 값 중 하나일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a47e2-104">An association end multiplicity can have one of the following values:</span></span>  
  
- <span data-ttu-id="a47e2-105">1 (1): 연결 end에 엔터티 형식 인스턴스가 정확히 한 개 있음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="a47e2-105">one (1): Indicates that exactly one entity type instance exists at the association end.</span></span>  
  
- <span data-ttu-id="a47e2-106">0 또는 1 (0 ..1): 연결 end에 엔터티 형식 인스턴스가 0 개 또는 한 개 존재 함을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="a47e2-106">zero or one (0..1): Indicates that zero or one entity type instances exist at the association end.</span></span>  
  
- <span data-ttu-id="a47e2-107">many (\*): 연결 end에 엔터티 형식 인스턴스가 0 개 이상 있음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="a47e2-107">many (\*): Indicates that zero, one, or more entity type instances exist at the association end.</span></span>  
  
 <span data-ttu-id="a47e2-108">연결은 대체로 연결 End 복합성 특성을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="a47e2-108">An association is often characterized by its association end multiplicities.</span></span> <span data-ttu-id="a47e2-109">예를 들어 연결의 끝에 복합성 one (1) 및 many (\*)가 있는 경우 연결을 일대다 연결 이라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="a47e2-109">For example, if the ends of an association have multiplicities one (1) and many (\*), the association is called a one-to-many association.</span></span> <span data-ttu-id="a47e2-110">다음 예에서 `PublishedBy` 연결은 일대다 연결입니다. 즉, 한 명의 발행자가 많은 책을 출판하고 책 하나는 한 명의 발행자에 의해 출판됩니다.</span><span class="sxs-lookup"><span data-stu-id="a47e2-110">In the example below, the `PublishedBy` association is a one-to-many association (a publisher publishes many books and a book is published by one publisher).</span></span> <span data-ttu-id="a47e2-111">`WrittenBy` 연결은 다대다 연결입니다. 한 권의 책에 저자가 여러 명일 수 있고 한 명의 저자가 여러 책을 쓸 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a47e2-111">The `WrittenBy` association is a many-to-many association (a book can have multiple authors and an author can write multiple books).</span></span>  
  
## <a name="example"></a><span data-ttu-id="a47e2-112">예제</span><span class="sxs-lookup"><span data-stu-id="a47e2-112">Example</span></span>  
 <span data-ttu-id="a47e2-113">다음 다이어그램에서는 두 연결 `PublishedBy` 및 `WrittenBy`의 개념적 모델을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="a47e2-113">The diagram below shows a conceptual model with two associations: `PublishedBy` and `WrittenBy`.</span></span> <span data-ttu-id="a47e2-114">`PublishedBy` 연결의 연결 End는 `Book` 및 `Publisher` 엔터티 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="a47e2-114">The association ends for the `PublishedBy` association are the `Book` and `Publisher` entity types.</span></span> <span data-ttu-id="a47e2-115">`Publisher` 끝의 복합성은 1이 고, `Book` 끝의 복합성은 다 수 (\*)입니다.</span><span class="sxs-lookup"><span data-stu-id="a47e2-115">The multiplicity of the `Publisher` end is one (1) and the multiplicity of the `Book` end is many (\*).</span></span>  
  
 ![세 개의 엔터티 형식이 있는 예제 모델](./media/association-end-multiplicity/example-model-three-entity-types.gif)  
  
 <span data-ttu-id="a47e2-117">ADO.NET Entity Framework에서는[CSDL](./ef/language-reference/csdl-specification.md)(개념 스키마 정의 언어) 이라는 DSL (도메인별 언어)을 사용 하 여 개념적 모델을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="a47e2-117">The ADO.NET Entity Framework uses a domain-specific language (DSL) called conceptual schema definition language ([CSDL](./ef/language-reference/csdl-specification.md)) to define conceptual models.</span></span> <span data-ttu-id="a47e2-118">다음 CSDL에서는 위의 다이어그램에 표시된 `PublishedBy` 연결을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="a47e2-118">The following CSDL defines the `PublishedBy` association shown in the diagram above:</span></span>  
  
 [!code-xml[EDM_Example_Model#AssociationExample](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books.edmx#associationexample)]  
  
## <a name="see-also"></a><span data-ttu-id="a47e2-119">참고자료</span><span class="sxs-lookup"><span data-stu-id="a47e2-119">See also</span></span>

- [<span data-ttu-id="a47e2-120">엔터티 데이터 모델의 주요 개념</span><span class="sxs-lookup"><span data-stu-id="a47e2-120">Entity Data Model Key Concepts</span></span>](entity-data-model-key-concepts.md)
- [<span data-ttu-id="a47e2-121">엔터티 데이터 모델</span><span class="sxs-lookup"><span data-stu-id="a47e2-121">Entity Data Model</span></span>](entity-data-model.md)
