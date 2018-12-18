---
title: 속성 및 인덱서 비교 - C# 프로그래밍 가이드
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- properties [C#], vs. indexers
- indexers [C#], vs. properties
ms.assetid: 3358a89f-44a0-4a4d-bf8c-07237a90af39
ms.openlocfilehash: 053eb7ee0fe9333f049e5b4f8a8e709e42aa2119
ms.sourcegitcommit: bdd930b5df20a45c29483d905526a2a3e4d17c5b
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/11/2018
ms.locfileid: "53234463"
---
# <a name="comparison-between-properties-and-indexers-c-programming-guide"></a><span data-ttu-id="1228a-102">속성 및 인덱서 비교(C# 프로그래밍 가이드)</span><span class="sxs-lookup"><span data-stu-id="1228a-102">Comparison Between Properties and Indexers (C# Programming Guide)</span></span>
<span data-ttu-id="1228a-103">인덱서는 속성과 비슷합니다.</span><span class="sxs-lookup"><span data-stu-id="1228a-103">Indexers are like properties.</span></span> <span data-ttu-id="1228a-104">다음 표에 나와 있는 차이점을 제외하면 속성 접근자에 대해 정의된 모든 규칙이 인덱서 접근자에도 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="1228a-104">Except for the differences shown in the following table, all the rules that are defined for property accessors apply to indexer accessors also.</span></span>  
  
|<span data-ttu-id="1228a-105">속성</span><span class="sxs-lookup"><span data-stu-id="1228a-105">Property</span></span>|<span data-ttu-id="1228a-106">인덱서</span><span class="sxs-lookup"><span data-stu-id="1228a-106">Indexer</span></span>|  
|--------------|-------------|  
|<span data-ttu-id="1228a-107">공용 데이터 멤버인 것처럼 메서드를 호출할 수 있게 합니다.</span><span class="sxs-lookup"><span data-stu-id="1228a-107">Allows methods to be called as if they were public data members.</span></span>|<span data-ttu-id="1228a-108">개체 자체에 배열 표기법을 사용하여 개체의 내부 컬렉션 요소에 액세스할 수 있게 합니다.</span><span class="sxs-lookup"><span data-stu-id="1228a-108">Allows elements of an internal collection of an object to be accessed by using array notation on the object itself.</span></span>|  
|<span data-ttu-id="1228a-109">단순한 이름을 통해 액세스합니다.</span><span class="sxs-lookup"><span data-stu-id="1228a-109">Accessed through a simple name.</span></span>|<span data-ttu-id="1228a-110">인덱스를 통해 액세스합니다.</span><span class="sxs-lookup"><span data-stu-id="1228a-110">Accessed through an index.</span></span>|  
|<span data-ttu-id="1228a-111">정적 또는 인스턴스 멤버일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1228a-111">Can be a static or an instance member.</span></span>|<span data-ttu-id="1228a-112">인스턴스 멤버여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1228a-112">Must be an instance member.</span></span>|  
|<span data-ttu-id="1228a-113">속성의 [get](../../../csharp/language-reference/keywords/get.md) 접근자에는 매개 변수가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="1228a-113">A [get](../../../csharp/language-reference/keywords/get.md) accessor of a property has no parameters.</span></span>|<span data-ttu-id="1228a-114">인덱서의 `get` 접근자에는 인덱서와 동일한 형식 매개 변수 목록이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1228a-114">A `get` accessor of an indexer has the same formal parameter list as the indexer.</span></span>|  
|<span data-ttu-id="1228a-115">속성의 [set](../../../csharp/language-reference/keywords/set.md) 접근자에는 암시적 `value` 매개 변수가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1228a-115">A [set](../../../csharp/language-reference/keywords/set.md) accessor of a property contains the implicit `value` parameter.</span></span>|<span data-ttu-id="1228a-116">인덱서의 `set` 접근자에는 인덱서와 동일한 형식 매개 변수 목록이 있으며 [value](../../../csharp/language-reference/keywords/value.md) 매개 변수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1228a-116">A `set` accessor of an indexer has the same formal parameter list as the indexer, and also to the [value](../../../csharp/language-reference/keywords/value.md) parameter.</span></span>|  
|<span data-ttu-id="1228a-117">[자동으로 구현된 속성](../../../csharp/programming-guide/classes-and-structs/auto-implemented-properties.md)을 사용하여 약식 구문을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="1228a-117">Supports shortened syntax with [Auto-Implemented Properties](../../../csharp/programming-guide/classes-and-structs/auto-implemented-properties.md).</span></span>|<span data-ttu-id="1228a-118">약식 구문을 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1228a-118">Does not support shortened syntax.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="1228a-119">참고 항목</span><span class="sxs-lookup"><span data-stu-id="1228a-119">See Also</span></span>

- [<span data-ttu-id="1228a-120">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="1228a-120">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="1228a-121">인덱서</span><span class="sxs-lookup"><span data-stu-id="1228a-121">Indexers</span></span>](../../../csharp/programming-guide/indexers/index.md)  
- [<span data-ttu-id="1228a-122">속성</span><span class="sxs-lookup"><span data-stu-id="1228a-122">Properties</span></span>](../../../csharp/programming-guide/classes-and-structs/properties.md)
