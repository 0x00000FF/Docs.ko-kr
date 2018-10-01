---
title: 순수 함수 변환 소개(C#)
ms.date: 07/20/2015
ms.assetid: 8495c9d9-2d02-4aa0-8a10-9e8794b985fe
ms.openlocfilehash: f04189c5ae6fc8f6c827f983357ab0126b2c086d
ms.sourcegitcommit: fb78d8abbdb87144a3872cf154930157090dd933
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/27/2018
ms.locfileid: "47193855"
---
# <a name="introduction-to-pure-functional-transformations-c"></a><span data-ttu-id="d9d7f-102">순수 함수 변환 소개(C#)</span><span class="sxs-lookup"><span data-stu-id="d9d7f-102">Introduction to Pure Functional Transformations (C#)</span></span>
<span data-ttu-id="d9d7f-103">이 단원에서는 기본 개념과 지원하는 언어 구문을 비롯하여 함수 변환에 대해 소개합니다.</span><span class="sxs-lookup"><span data-stu-id="d9d7f-103">This section introduces functional transformations, including the underlying concepts and supporting language constructs.</span></span> <span data-ttu-id="d9d7f-104">프로그래밍에 대한 개체 지향 및 함수 변환 방법을 대조하고 함수 변환 방법으로 전환하는 방법에 대한 조언을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="d9d7f-104">It contrasts the object-oriented and functional transformation approaches to programming, including advice on how to transition to the latter.</span></span> <span data-ttu-id="d9d7f-105">많은 프로그래밍 시나리오에서 함수 변환을 사용할 수 있지만 여기에서는 XML 변환이 구체적인 예제로 사용되었습니다.</span><span class="sxs-lookup"><span data-stu-id="d9d7f-105">Although functional transformations can be used in many programming scenarios, XML transformation is used here as a concrete example.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="d9d7f-106">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="d9d7f-106">In This Section</span></span>  
  
|<span data-ttu-id="d9d7f-107">항목</span><span class="sxs-lookup"><span data-stu-id="d9d7f-107">Topic</span></span>|<span data-ttu-id="d9d7f-108">설명</span><span class="sxs-lookup"><span data-stu-id="d9d7f-108">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="d9d7f-109">개념과 용어(함수 변환)(C#)</span><span class="sxs-lookup"><span data-stu-id="d9d7f-109">Concepts and Terminology (Functional Transformation) (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/concepts-and-terminology-functional-transformation.md)|<span data-ttu-id="d9d7f-110">순수 함수 변환의 개념과 용어에 대해 소개합니다.</span><span class="sxs-lookup"><span data-stu-id="d9d7f-110">Introduces the concepts and terminology of pure functional transformations.</span></span>|  
|[<span data-ttu-id="d9d7f-111">함수형 프로그래밍과 명령형 프로그래밍 비교(C#)</span><span class="sxs-lookup"><span data-stu-id="d9d7f-111">Functional Programming vs. Imperative Programming (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/functional-programming-vs-imperative-programming.md)|<span data-ttu-id="d9d7f-112">함수형 프로그래밍을 더욱 일반적인 명령형(절차적) 프로그래밍과 비교하고 대조합니다.</span><span class="sxs-lookup"><span data-stu-id="d9d7f-112">Compares and contrasts functional programming to more traditional imperative (procedural) programming.</span></span>|  
|[<span data-ttu-id="d9d7f-113">순수 함수로 리팩터링(C#)</span><span class="sxs-lookup"><span data-stu-id="d9d7f-113">Refactoring Into Pure Functions (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/refactoring-into-pure-functions.md)|<span data-ttu-id="d9d7f-114">순수 함수에 대해 소개하고 순수 함수와 비순수 함수의 예제를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="d9d7f-114">Introduces pure functions, and shows examples of and pure and impure functions.</span></span>|  
|[<span data-ttu-id="d9d7f-115">함수 변환의 적용 가능 범위(C#)</span><span class="sxs-lookup"><span data-stu-id="d9d7f-115">Applicability of Functional Transformation (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/applicability-of-functional-transformation.md)|<span data-ttu-id="d9d7f-116">함수 변환의 일반적인 시나리오에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="d9d7f-116">Describes typical scenarios for functional transformations.</span></span>|  
|[<span data-ttu-id="d9d7f-117">XML의 함수 변환(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d9d7f-117">Functional Transformation of XML (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/functional-transformation-of-xml.md)|<span data-ttu-id="d9d7f-118">XML 트리 변환 측면에서 함수 변환에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="d9d7f-118">Describes functional transformations in the context of transforming XML trees.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="d9d7f-119">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d9d7f-119">See Also</span></span>

- [<span data-ttu-id="d9d7f-120">XML의 순수 함수 변환(C#)</span><span class="sxs-lookup"><span data-stu-id="d9d7f-120">Pure Functional Transformations of XML (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/pure-functional-transformations-of-xml.md)
