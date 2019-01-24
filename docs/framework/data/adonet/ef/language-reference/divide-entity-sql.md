---
title: '- (나누기) (Entity SQL)'
ms.date: 03/30/2017
ms.assetid: ef48c368-f3ed-4275-8ada-4e9649781262
ms.openlocfilehash: 42fc5e2a9f9f159a8a60973dbed6540b3188fba6
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54745236"
---
# <a name="-divide-entity-sql"></a><span data-ttu-id="59654-102">/ (나누기) (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="59654-102">/ (Divide) (Entity SQL)</span></span>
<span data-ttu-id="59654-103">한 숫자를 다른 숫자로 나눕니다.</span><span class="sxs-lookup"><span data-stu-id="59654-103">Divides one number by another.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="59654-104">구문</span><span class="sxs-lookup"><span data-stu-id="59654-104">Syntax</span></span>  
  
```  
dividend / divisor  
```  
  
## <a name="arguments"></a><span data-ttu-id="59654-105">인수</span><span class="sxs-lookup"><span data-stu-id="59654-105">Arguments</span></span>  
 `dividend`  
 <span data-ttu-id="59654-106">나눌 숫자 식입니다.</span><span class="sxs-lookup"><span data-stu-id="59654-106">The numeric expression to divide.</span></span> <span data-ttu-id="59654-107">`dividend` 는 숫자 데이터 형식의 유효한 식입니다.</span><span class="sxs-lookup"><span data-stu-id="59654-107">`dividend` is any valid expression of any one of the numeric data types.</span></span>  
  
 `divisor`  
 <span data-ttu-id="59654-108">피제수를 나눌 숫자 식입니다.</span><span class="sxs-lookup"><span data-stu-id="59654-108">The numeric expression to divide the dividend by.</span></span> <span data-ttu-id="59654-109">`divisor` 는 숫자 데이터 형식의 유효한 식입니다.</span><span class="sxs-lookup"><span data-stu-id="59654-109">`divisor` is any valid expression of any one of the numeric data types.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="59654-110">결과 형식</span><span class="sxs-lookup"><span data-stu-id="59654-110">Result Types</span></span>  
 <span data-ttu-id="59654-111">두 인수에 대해 암시적 형식 승격을 수행한 결과 데이터 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="59654-111">The data type that results from the implicit type promotion of the two arguments.</span></span> <span data-ttu-id="59654-112">암시적 형식 승격에 대 한 자세한 내용은 참조 하세요. [형식 시스템](../../../../../../docs/framework/data/adonet/ef/language-reference/type-system-entity-sql.md)입니다.</span><span class="sxs-lookup"><span data-stu-id="59654-112">For more information about implicit type promotion, see [Type System](../../../../../../docs/framework/data/adonet/ef/language-reference/type-system-entity-sql.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="59654-113">예제</span><span class="sxs-lookup"><span data-stu-id="59654-113">Example</span></span>  
 <span data-ttu-id="59654-114">다음 Entity SQL 쿼리에서 / 산술 연산자를 다른 숫자로 나눕니다.</span><span class="sxs-lookup"><span data-stu-id="59654-114">The following Entity SQL query uses the / arithmetic operator to divide one number by another.</span></span> <span data-ttu-id="59654-115">쿼리는 AdventureWorks Sales 모델을 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="59654-115">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="59654-116">이 쿼리를 컴파일하고 실행하려면 다음 단계를 수행하세요.</span><span class="sxs-lookup"><span data-stu-id="59654-116">To compile and run this query, follow these steps:</span></span>  
  
1.  <span data-ttu-id="59654-117">절차에 따라 [방법: StructuralType 결과 반환 하는 쿼리 실행](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="59654-117">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2.  <span data-ttu-id="59654-118">다음 쿼리를 `ExecuteStructuralTypeQuery` 메서드에 인수로 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="59654-118">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#DIVIDE](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#divide)]  
  
## <a name="see-also"></a><span data-ttu-id="59654-119">참고자료</span><span class="sxs-lookup"><span data-stu-id="59654-119">See also</span></span>
- [<span data-ttu-id="59654-120">엔터티 SQL 참조</span><span class="sxs-lookup"><span data-stu-id="59654-120">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
