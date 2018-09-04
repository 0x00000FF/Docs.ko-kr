---
title: + (문자열 연결) (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 580130fa-6c7c-4f76-a47d-d22c27ccadf6
ms.openlocfilehash: 8a1785d590c5f7fcc443856180d516bb40cfc28e
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/04/2018
ms.locfileid: "43500882"
---
# <a name="-string-concatenation-entity-sql"></a><span data-ttu-id="17afe-102">+ (문자열 연결)(Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="17afe-102">+ (String Concatenation) (Entity SQL)</span></span>
<span data-ttu-id="17afe-103">두 문자열을 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="17afe-103">Concatenates two strings.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="17afe-104">구문</span><span class="sxs-lookup"><span data-stu-id="17afe-104">Syntax</span></span>  
  
```  
expression + expression  
```  
  
## <a name="arguments"></a><span data-ttu-id="17afe-105">인수</span><span class="sxs-lookup"><span data-stu-id="17afe-105">Arguments</span></span>  
 `expression`  
 <span data-ttu-id="17afe-106">EDM.String 데이터 형식의 유효한 식입니다.</span><span class="sxs-lookup"><span data-stu-id="17afe-106">Any valid expression of the EDM.String data types.</span></span> <span data-ttu-id="17afe-107">두 식의 데이터 형식이 같거나 한 식이 다른 식의 데이터 형식으로 암시적으로 변환될 수 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="17afe-107">Both expressions must be of the same data type, or one expression must be able to be implicitly converted to the data type of the other expression.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="17afe-108">결과 형식</span><span class="sxs-lookup"><span data-stu-id="17afe-108">Result Types</span></span>  
 <span data-ttu-id="17afe-109">두 인수에 대해 암시적 형식 승격을 수행한 결과 데이터 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="17afe-109">The data type that results from the implicit type promotion of the two arguments.</span></span> <span data-ttu-id="17afe-110">암시적 형식 승격에 대 한 자세한 내용은 참조 하세요. [형식 시스템](../../../../../../docs/framework/data/adonet/ef/language-reference/type-system-entity-sql.md)입니다.</span><span class="sxs-lookup"><span data-stu-id="17afe-110">For more information about implicit type promotion, see [Type System](../../../../../../docs/framework/data/adonet/ef/language-reference/type-system-entity-sql.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="17afe-111">예제</span><span class="sxs-lookup"><span data-stu-id="17afe-111">Example</span></span>  
 <span data-ttu-id="17afe-112">다음 Entity SQL 쿼리에서는 + 연산자를 사용하여 두 문자열을 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="17afe-112">The following Entity SQL query uses the + operator to concatenates two strings.</span></span> <span data-ttu-id="17afe-113">쿼리는 AdventureWorks Sales 모델을 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="17afe-113">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="17afe-114">이 쿼리를 컴파일하고 실행하려면 다음 단계를 수행하세요.</span><span class="sxs-lookup"><span data-stu-id="17afe-114">To compile and run this query, follow these steps:</span></span>  
  
1.  <span data-ttu-id="17afe-115">절차를 따릅니다 [방법: PrimitiveType 결과 반환 하는 쿼리 실행](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-primitivetype-results.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="17afe-115">Follow the procedure in [How to: Execute a Query that Returns PrimitiveType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-primitivetype-results.md).</span></span>  
  
2.  <span data-ttu-id="17afe-116">다음 쿼리를 `ExecutePrimitiveTypeQuery` 메서드에 인수로 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="17afe-116">Pass the following query as an argument to the `ExecutePrimitiveTypeQuery` method:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#CONCAT](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#concat)]  
  
## <a name="see-also"></a><span data-ttu-id="17afe-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="17afe-117">See Also</span></span>  
 [<span data-ttu-id="17afe-118">엔터티 SQL 참조</span><span class="sxs-lookup"><span data-stu-id="17afe-118">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)  
 [<span data-ttu-id="17afe-119">개념적 모델 형식 (CSDL)</span><span class="sxs-lookup"><span data-stu-id="17afe-119">Conceptual Model Types (CSDL)</span></span>](https://msdn.microsoft.com/library/987b995f-e429-4569-9559-b4146744def4)
