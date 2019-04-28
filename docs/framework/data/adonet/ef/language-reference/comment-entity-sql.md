---
title: -- (주석)(Entity SQL)
ms.date: 03/30/2017
ms.assetid: 5d9de735-2099-47f1-b7e7-60856f494924
ms.openlocfilehash: c10b17931c6024e2a9e947083747435d8aa54fa2
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61605999"
---
# <a name="---comment-entity-sql"></a><span data-ttu-id="3b46c-102">-- (주석)(Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="3b46c-102">-- (Comment) (Entity SQL)</span></span>
[!INCLUDE[esql](../../../../../../includes/esql-md.md)] <span data-ttu-id="3b46c-103">쿼리에는 주석이 포함될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3b46c-103">queries can contain comments.</span></span> <span data-ttu-id="3b46c-104">주석 줄은 대시 두 개(`--`)로 시작됩니다.</span><span class="sxs-lookup"><span data-stu-id="3b46c-104">Two dashes (`--`) start a comment line.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3b46c-105">구문</span><span class="sxs-lookup"><span data-stu-id="3b46c-105">Syntax</span></span>  
  
```  
-- text_of_comment  
```  
  
## <a name="arguments"></a><span data-ttu-id="3b46c-106">인수</span><span class="sxs-lookup"><span data-stu-id="3b46c-106">Arguments</span></span>  
 `text_of_comment`  
 <span data-ttu-id="3b46c-107">주석의 텍스트를 포함하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="3b46c-107">Is the character string that contains the text of the comment.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3b46c-108">예제</span><span class="sxs-lookup"><span data-stu-id="3b46c-108">Example</span></span>  
 <span data-ttu-id="3b46c-109">다음 Entity SQL 쿼리에서는 주석을 사용하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="3b46c-109">The following Entity SQL query demonstrates how to use comments.</span></span> <span data-ttu-id="3b46c-110">쿼리는 AdventureWorks Sales 모델을 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="3b46c-110">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="3b46c-111">이 쿼리를 컴파일하고 실행하려면 다음 단계를 수행하세요.</span><span class="sxs-lookup"><span data-stu-id="3b46c-111">To compile and run this query, follow these steps:</span></span>  
  
1. <span data-ttu-id="3b46c-112">절차에 따라 [방법: StructuralType 결과 반환 하는 쿼리 실행](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="3b46c-112">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2. <span data-ttu-id="3b46c-113">다음 쿼리를 `ExecuteStructuralTypeQuery` 메서드에 인수로 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="3b46c-113">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#COMMENT](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#comment)]  
  
## <a name="see-also"></a><span data-ttu-id="3b46c-114">참고자료</span><span class="sxs-lookup"><span data-stu-id="3b46c-114">See also</span></span>

- [<span data-ttu-id="3b46c-115">Entity SQL 개요</span><span class="sxs-lookup"><span data-stu-id="3b46c-115">Entity SQL Overview</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-overview.md)
- [<span data-ttu-id="3b46c-116">엔터티 SQL 참조</span><span class="sxs-lookup"><span data-stu-id="3b46c-116">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
