---
title: + (추가)
ms.date: 03/30/2017
ms.assetid: 51769b02-a8f7-4177-9e99-bbd10e77092c
ms.openlocfilehash: a3c41ef8cf393a4d1b1deb362d6a3614558a34ba
ms.sourcegitcommit: ad99773e5e45068ce03b99518008397e1299e0d1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/23/2018
ms.locfileid: "46703793"
---
# <a name="-add"></a><span data-ttu-id="de9d1-102">+ (추가)</span><span class="sxs-lookup"><span data-stu-id="de9d1-102">+ (Add)</span></span>
<span data-ttu-id="de9d1-103">두 숫자를 더합니다.</span><span class="sxs-lookup"><span data-stu-id="de9d1-103">Adds two numbers.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="de9d1-104">구문</span><span class="sxs-lookup"><span data-stu-id="de9d1-104">Syntax</span></span>  
  
```  
expression + expression  
```  
  
## <a name="arguments"></a><span data-ttu-id="de9d1-105">인수</span><span class="sxs-lookup"><span data-stu-id="de9d1-105">Arguments</span></span>  
 `expression`  
 <span data-ttu-id="de9d1-106">숫자 데이터 형식의 유효한 식입니다.</span><span class="sxs-lookup"><span data-stu-id="de9d1-106">Any valid expression of any one of the numeric data types.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="de9d1-107">결과 형식</span><span class="sxs-lookup"><span data-stu-id="de9d1-107">Result Types</span></span>  
 <span data-ttu-id="de9d1-108">두 인수에 대해 암시적 형식 승격을 수행한 결과 데이터 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="de9d1-108">The data type that results from the implicit type promotion of the two arguments.</span></span> <span data-ttu-id="de9d1-109">암시적 형식 승격에 대 한 자세한 내용은 참조 하세요. [형식 시스템](../../../../../../docs/framework/data/adonet/ef/language-reference/type-system-entity-sql.md)입니다.</span><span class="sxs-lookup"><span data-stu-id="de9d1-109">For more information about implicit type promotion, see [Type System](../../../../../../docs/framework/data/adonet/ef/language-reference/type-system-entity-sql.md).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="de9d1-110">설명</span><span class="sxs-lookup"><span data-stu-id="de9d1-110">Remarks</span></span>  
 <span data-ttu-id="de9d1-111">EDM.String 형식의 경우 더하기는 연결입니다.</span><span class="sxs-lookup"><span data-stu-id="de9d1-111">For EDM.String types, addition is concatenation.</span></span>  
  
## <a name="example"></a><span data-ttu-id="de9d1-112">예제</span><span class="sxs-lookup"><span data-stu-id="de9d1-112">Example</span></span>  
 <span data-ttu-id="de9d1-113">다음 Entity SQL 쿼리에서는 + 산술 연산자를 사용하여 두 숫자를 더합니다.</span><span class="sxs-lookup"><span data-stu-id="de9d1-113">The following Entity SQL query uses the + arithmetic operator to add two numbers.</span></span> <span data-ttu-id="de9d1-114">쿼리는 AdventureWorks Sales 모델을 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="de9d1-114">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="de9d1-115">이 쿼리를 컴파일하고 실행하려면 다음 단계를 수행하세요.</span><span class="sxs-lookup"><span data-stu-id="de9d1-115">To compile and run this query, follow these steps:</span></span>  
  
1.  <span data-ttu-id="de9d1-116">[How to: Execute a Query that Returns StructuralType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md)의 절차를 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="de9d1-116">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2.  <span data-ttu-id="de9d1-117">다음 쿼리를 `ExecuteStructuralTypeQuery` 메서드에 인수로 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="de9d1-117">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#ADD](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#add)]  
  
## <a name="see-also"></a><span data-ttu-id="de9d1-118">참고 항목</span><span class="sxs-lookup"><span data-stu-id="de9d1-118">See Also</span></span>  
 [<span data-ttu-id="de9d1-119">엔터티 SQL 참조</span><span class="sxs-lookup"><span data-stu-id="de9d1-119">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)  
 [<span data-ttu-id="de9d1-120">개념적 모델 형식 (CSDL)</span><span class="sxs-lookup"><span data-stu-id="de9d1-120">Conceptual Model Types (CSDL)</span></span>](https://msdn.microsoft.com/library/987b995f-e429-4569-9559-b4146744def4)
