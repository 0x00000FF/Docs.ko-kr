---
title: REF(Entity SQL)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c5f4cb35-69e9-44cc-b63b-ee38922bbda1
caps.latest.revision: "3"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: 1836b91876ac3c993f07902a644c130dda76f158
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="ref-entity-sql"></a><span data-ttu-id="da238-102">REF(Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="da238-102">REF (Entity SQL)</span></span>
<span data-ttu-id="da238-103">엔터티 인스턴스에 대한 참조를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="da238-103">Returns a reference to an entity instance.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="da238-104">구문</span><span class="sxs-lookup"><span data-stu-id="da238-104">Syntax</span></span>  
  
```  
REF( expression )   
```  
  
## <a name="arguments"></a><span data-ttu-id="da238-105">인수</span><span class="sxs-lookup"><span data-stu-id="da238-105">Arguments</span></span>  
 `expression`  
 <span data-ttu-id="da238-106">엔터티 형식의 인스턴스를 생성하는 모든 유효한 식입니다.</span><span class="sxs-lookup"><span data-stu-id="da238-106">Any valid expression that yields an instance of an entity type.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="da238-107">반환 값</span><span class="sxs-lookup"><span data-stu-id="da238-107">Return Value</span></span>  
 <span data-ttu-id="da238-108">지정한 엔터티 인스턴스에 대한 참조입니다.</span><span class="sxs-lookup"><span data-stu-id="da238-108">A reference to the specified entity instance.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="da238-109">설명</span><span class="sxs-lookup"><span data-stu-id="da238-109">Remarks</span></span>  
 <span data-ttu-id="da238-110">엔터티 참조는 엔터티 키와 엔터티 집합 이름으로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="da238-110">An entity reference consists of the entity key and an entity set name.</span></span> <span data-ttu-id="da238-111">여러 엔터티 집합이 같은 엔터티 형식을 기반으로 할 수 있으므로 특정 엔터티 키가 여러 엔터티 집합에 나타날 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="da238-111">Because different entity sets can be based on the same entity type, a particular entity key can appear in multiple entity sets.</span></span> <span data-ttu-id="da238-112">하지만 엔터티 참조는 항상 고유합니다.</span><span class="sxs-lookup"><span data-stu-id="da238-112">However, an entity reference is always unique.</span></span> <span data-ttu-id="da238-113">입력 식이 보관된 엔터티를 나타내는 경우 이 엔터티에 대한 참조가 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="da238-113">If the input expression represents a persisted entity, a reference to this entity will be returned.</span></span> <span data-ttu-id="da238-114">입력 식이 보관된 엔터티가 아닌 경우 Null 참조가 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="da238-114">If the input expression is not a persisted entity, a null reference will be returned.</span></span>  
  
 <span data-ttu-id="da238-115">속성 추출 연산자(.)를 사용하여 엔터티의 속성에 액세스하면 해당 참조가 자동으로 역참조됩니다.</span><span class="sxs-lookup"><span data-stu-id="da238-115">If the property extraction operator (.) is used to access a property of an entity, the reference is automatically dereferenced.</span></span>  
  
## <a name="example"></a><span data-ttu-id="da238-116">예</span><span class="sxs-lookup"><span data-stu-id="da238-116">Example</span></span>  
 <span data-ttu-id="da238-117">다음 Entity SQL 쿼리는 REF 연산자를 사용하여 입력 엔터티 인수에 대한 참조를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="da238-117">The following Entity SQL query uses the REF operator to return the reference for an input entity argument.</span></span> <span data-ttu-id="da238-118">속성 추출 연산자(.)를 사용하여 Product 엔터티의 속성에 액세스하고 있으므로 같은 쿼리에서 참조를 역참조합니다.</span><span class="sxs-lookup"><span data-stu-id="da238-118">The same query dereferences the reference because we are using a property extraction operation (.) to access a property of the Product entity.</span></span> <span data-ttu-id="da238-119">쿼리는 AdventureWorks Sales 모델을 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="da238-119">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="da238-120">이 쿼리를 컴파일하고 실행하려면 다음 단계를 수행하세요.</span><span class="sxs-lookup"><span data-stu-id="da238-120">To compile and run this query, follow these steps:</span></span>  
  
1.  <span data-ttu-id="da238-121">절차에 따라 [하는 방법: PrimitiveType 결과 반환 하는 쿼리 실행](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-primitivetype-results.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="da238-121">Follow the procedure in [How to: Execute a Query that Returns PrimitiveType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-primitivetype-results.md).</span></span>  
  
2.  <span data-ttu-id="da238-122">다음 쿼리를 `ExecutePrimitiveTypeQuery` 메서드에 인수로 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="da238-122">Pass the following query as an argument to the `ExecutePrimitiveTypeQuery` method:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#REF](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#ref)]  
  
## <a name="see-also"></a><span data-ttu-id="da238-123">참고 항목</span><span class="sxs-lookup"><span data-stu-id="da238-123">See Also</span></span>  
 [<span data-ttu-id="da238-124">DEREF</span><span class="sxs-lookup"><span data-stu-id="da238-124">DEREF</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/deref-entity-sql.md)  
 [<span data-ttu-id="da238-125">CREATEREF</span><span class="sxs-lookup"><span data-stu-id="da238-125">CREATEREF</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/createref-entity-sql.md)  
 [<span data-ttu-id="da238-126">KEY</span><span class="sxs-lookup"><span data-stu-id="da238-126">KEY</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/key-entity-sql.md)  
 [<span data-ttu-id="da238-127">엔터티 SQL 참조</span><span class="sxs-lookup"><span data-stu-id="da238-127">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)  
 [<span data-ttu-id="da238-128">형식 정의</span><span class="sxs-lookup"><span data-stu-id="da238-128">Type Definitions</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/type-definitions-entity-sql.md)
