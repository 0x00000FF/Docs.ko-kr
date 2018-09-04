---
title: 숫자 및 비교 연산자
ms.date: 03/30/2017
ms.assetid: 25b4a26a-06f2-4f80-87a9-76705ed46197
ms.openlocfilehash: a7a455730860e2b11a5ceff5a70934502b312e19
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/04/2018
ms.locfileid: "43515068"
---
# <a name="numeric-and-comparison-operators"></a><span data-ttu-id="66bfa-102">숫자 및 비교 연산자</span><span class="sxs-lookup"><span data-stu-id="66bfa-102">Numeric and Comparison Operators</span></span>
<span data-ttu-id="66bfa-103">산술 및 비교 연산자는 CLR(공용 언어 런타임) 예외에서 다음과 같이 예상대로 동작합니다.</span><span class="sxs-lookup"><span data-stu-id="66bfa-103">Arithmetic and comparison operators work as expected in the common language runtime (CLR) except as follows:</span></span>  
  
-   <span data-ttu-id="66bfa-104">SQL에서는 부동 소수점 숫자에 대해 모듈 연산자를 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="66bfa-104">SQL does not support the modulus operator on floating-point numbers.</span></span>  
  
-   <span data-ttu-id="66bfa-105">SQL에서는 unchecked 산술 연산을 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="66bfa-105">SQL does not support unchecked arithmetic.</span></span>  
  
-   <span data-ttu-id="66bfa-106">증가 및 감소 연산자를 SQL에서 복제할 수 없는 식에 사용하면 예기치 않은 결과가 발생할 수 있기 때문에 두 연산자는 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="66bfa-106">Increment and decrement operators cause side-effects when you use them in expressions that cannot be replicated in SQL and are, therefore, not supported.</span></span>  
  
## <a name="supported-operators"></a><span data-ttu-id="66bfa-107">지원되는 연산자</span><span class="sxs-lookup"><span data-stu-id="66bfa-107">Supported Operators</span></span>  
 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]<span data-ttu-id="66bfa-108">에서는 다음 연산자를 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="66bfa-108"> supports the following operators.</span></span>  
  
-   <span data-ttu-id="66bfa-109">기본 산술 연산자:</span><span class="sxs-lookup"><span data-stu-id="66bfa-109">Basic arithmetic operators:</span></span>  
  
    -   `+`  
  
    -   <span data-ttu-id="66bfa-110">`-`(빼기)</span><span class="sxs-lookup"><span data-stu-id="66bfa-110">`-` (subtraction)</span></span>  
  
    -   `*`  
  
    -   `/`  
  
    -   <span data-ttu-id="66bfa-111">`\`(Visual Basic 정수 나누기)</span><span class="sxs-lookup"><span data-stu-id="66bfa-111">Visual Basic integer division (`\`)</span></span>  
  
    -   <span data-ttu-id="66bfa-112">`%`(Visual Basic `Mod`)</span><span class="sxs-lookup"><span data-stu-id="66bfa-112">`%` (Visual Basic `Mod`)</span></span>  
  
    -   `<<`  
  
    -   `>>`  
  
    -   <span data-ttu-id="66bfa-113">`-`(단항 부정 연산자)</span><span class="sxs-lookup"><span data-stu-id="66bfa-113">`-` (unary negation)</span></span>  
  
-   <span data-ttu-id="66bfa-114">기본 비교 연산자:</span><span class="sxs-lookup"><span data-stu-id="66bfa-114">Basic comparison operators:</span></span>  
  
    -   <span data-ttu-id="66bfa-115">Visual Basic `=` 및 C# `==`</span><span class="sxs-lookup"><span data-stu-id="66bfa-115">Visual Basic `=` and C# `==`</span></span>  
  
    -   <span data-ttu-id="66bfa-116">Visual Basic `<>` 및 C# `!=`</span><span class="sxs-lookup"><span data-stu-id="66bfa-116">Visual Basic `<>` and C# `!=`</span></span>  
  
    -   <span data-ttu-id="66bfa-117">Visual Basic `Is/IsNot`</span><span class="sxs-lookup"><span data-stu-id="66bfa-117">Visual Basic `Is/IsNot`</span></span>  
  
    -   `<`  
  
    -   `<=`  
  
    -   `>`  
  
    -   `>=`  
  
## <a name="see-also"></a><span data-ttu-id="66bfa-118">참고 항목</span><span class="sxs-lookup"><span data-stu-id="66bfa-118">See Also</span></span>  
 [<span data-ttu-id="66bfa-119">데이터 형식 및 함수</span><span class="sxs-lookup"><span data-stu-id="66bfa-119">Data Types and Functions</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/data-types-and-functions.md)  
 [<span data-ttu-id="66bfa-120">C# 연산자</span><span class="sxs-lookup"><span data-stu-id="66bfa-120">C# Operators</span></span>](https://msdn.microsoft.com/library/0301e31f-22ad-49af-ac3c-d5eae7f0ac43)  
 [<span data-ttu-id="66bfa-121">연산자</span><span class="sxs-lookup"><span data-stu-id="66bfa-121">Operators</span></span>](../../../../../visual-basic/language-reference/operators/index.md)
