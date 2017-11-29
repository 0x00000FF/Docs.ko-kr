---
title: "LINQ to Entities 쿼리에서 함수 호출"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 12a525a9-727c-4464-a0c7-71a0ef541792
caps.latest.revision: "3"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 6e50147d356ad9e389a87868205bb9b8b6b3e7b3
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="calling-functions-in-linq-to-entities-queries"></a><span data-ttu-id="e647a-102">LINQ to Entities 쿼리에서 함수 호출</span><span class="sxs-lookup"><span data-stu-id="e647a-102">Calling Functions in LINQ to Entities Queries</span></span>
<span data-ttu-id="e647a-103">이 단원의 항목에서는 LINQ to Entities 쿼리에서 함수를 호출하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="e647a-103">The topics in this section describe how to call functions in LINQ to Entities queries.</span></span>  
  
 <span data-ttu-id="e647a-104"><xref:System.Data.Objects.EntityFunctions> 및 <xref:System.Data.Objects.SqlClient.SqlFunctions> 클래스를 사용하여 Entity Framework의 일부인 정식 함수와 데이터베이스 함수에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e647a-104">The <xref:System.Data.Objects.EntityFunctions> and <xref:System.Data.Objects.SqlClient.SqlFunctions> classes provide access to canonical and database functions as part of the Entity Framework.</span></span> <span data-ttu-id="e647a-105">자세한 내용은 참조 [하는 방법: 정식 함수 호출](../../../../../../docs/framework/data/adonet/ef/language-reference/how-to-call-canonical-functions.md) 및 [하는 방법: 데이터베이스 함수 호출](../../../../../../docs/framework/data/adonet/ef/language-reference/how-to-call-database-functions.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="e647a-105">For more information, see [How to: Call Canonical Functions](../../../../../../docs/framework/data/adonet/ef/language-reference/how-to-call-canonical-functions.md) and [How to: Call Database Functions](../../../../../../docs/framework/data/adonet/ef/language-reference/how-to-call-database-functions.md).</span></span>  
  
 <span data-ttu-id="e647a-106">사용자 지정 함수를 호출하는 과정은 다음의 기본적인 세 단계로 이루어집니다.</span><span class="sxs-lookup"><span data-stu-id="e647a-106">The process for calling a custom function requires three basic steps:</span></span>  
  
1.  <span data-ttu-id="e647a-107">개념적 모델에서 함수를 정의하거나 저장소 모델에서 함수를 선언합니다.</span><span class="sxs-lookup"><span data-stu-id="e647a-107">Define a function in your conceptual model or declare a function in your storage model.</span></span>  
  
2.  <span data-ttu-id="e647a-108">응용 프로그램에 메서드를 추가하고 <xref:System.Data.Objects.DataClasses.EdmFunctionAttribute>를 사용하여 이 메서드를 모델의 함수에 매핑합니다.</span><span class="sxs-lookup"><span data-stu-id="e647a-108">Add a method to your application and map it to the function in the model with an <xref:System.Data.Objects.DataClasses.EdmFunctionAttribute>.</span></span>  
  
3.  <span data-ttu-id="e647a-109">LINQ to Entities 쿼리에서 함수를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="e647a-109">Call the function in a LINQ to Entities query.</span></span>  
  
 <span data-ttu-id="e647a-110">자세한 내용은 이 단원의 해당 항목을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="e647a-110">For more information, see the topics in this section.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="e647a-111">단원 내용</span><span class="sxs-lookup"><span data-stu-id="e647a-111">In This Section</span></span>  
 [<span data-ttu-id="e647a-112">방법: 정식 함수를 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="e647a-112">How to: Call Canonical Functions</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/how-to-call-canonical-functions.md)  
  
 [<span data-ttu-id="e647a-113">방법: 데이터베이스 함수 호출</span><span class="sxs-lookup"><span data-stu-id="e647a-113">How to: Call Database Functions</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/how-to-call-database-functions.md)  
  
 [<span data-ttu-id="e647a-114">방법: 사용자 지정 데이터베이스 함수 호출</span><span class="sxs-lookup"><span data-stu-id="e647a-114">How to: Call Custom Database Functions</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/how-to-call-custom-database-functions.md)  
  
 [<span data-ttu-id="e647a-115">방법: 쿼리에서 모델 정의 함수를 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="e647a-115">How to: Call Model-Defined Functions in Queries</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/how-to-call-model-defined-functions-in-queries.md)  
  
 [<span data-ttu-id="e647a-116">방법: 개체 메서드로 모델 정의 함수 호출</span><span class="sxs-lookup"><span data-stu-id="e647a-116">How to: Call Model-Defined Functions as Object Methods</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/how-to-call-model-defined-functions-as-object-methods.md)  
  
## <a name="see-also"></a><span data-ttu-id="e647a-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="e647a-117">See Also</span></span>  
 [<span data-ttu-id="e647a-118">LINQ to Entities에서 쿼리</span><span class="sxs-lookup"><span data-stu-id="e647a-118">Queries in LINQ to Entities</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/queries-in-linq-to-entities.md)  
 [<span data-ttu-id="e647a-119">정식 함수</span><span class="sxs-lookup"><span data-stu-id="e647a-119">Canonical Functions</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/canonical-functions.md)  
 [<span data-ttu-id="e647a-120">.edmx 파일 개요</span><span class="sxs-lookup"><span data-stu-id="e647a-120">.edmx File Overview</span></span>](http://msdn.microsoft.com/en-us/f4c8e7ce-1db6-417e-9759-15f8b55155d4)  
 [<span data-ttu-id="e647a-121">방법: 사용자 지정 함수를 개념적 모델의 정의</span><span class="sxs-lookup"><span data-stu-id="e647a-121">How to: Define Custom Functions in the Conceptual Model</span></span>](http://msdn.microsoft.com/en-us/0dad7b8b-58f6-4271-b238-f34810d68e5f)
