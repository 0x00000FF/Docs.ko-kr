---
title: 데이터 필터링(C#)
ms.date: 07/20/2015
ms.assetid: fbaece0d-0f23-47f7-89c5-f3ea8db692b6
ms.openlocfilehash: df2f9f1bab7767365be65dbb60fb4af324ae3dab
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/04/2018
ms.locfileid: "43503299"
---
# <a name="filtering-data-c"></a><span data-ttu-id="61d22-102">데이터 필터링(C#)</span><span class="sxs-lookup"><span data-stu-id="61d22-102">Filtering Data (C#)</span></span>
<span data-ttu-id="61d22-103">필터링은 지정된 조건을 충족하는 요소만 포함하도록 결과 집합을 제한하는 작업을 가리킵니다.</span><span class="sxs-lookup"><span data-stu-id="61d22-103">Filtering refers to the operation of restricting the result set to contain only those elements that satisfy a specified condition.</span></span> <span data-ttu-id="61d22-104">필터링은 선택이라고도 합니다.</span><span class="sxs-lookup"><span data-stu-id="61d22-104">It is also known as selection.</span></span>  
  
 <span data-ttu-id="61d22-105">다음 그림에서는 문자 시퀀스를 필터링한 결과를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="61d22-105">The following illustration shows the results of filtering a sequence of characters.</span></span> <span data-ttu-id="61d22-106">필터링 작업에 대한 조건자는 문자가 'A'가 되도록 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="61d22-106">The predicate for the filtering operation specifies that the character must be 'A'.</span></span>  
  
 <span data-ttu-id="61d22-107">![LINQ 필터링 작업](../../../../csharp/programming-guide/concepts/linq/media/linq_filter.png "LINQ_Filter")</span><span class="sxs-lookup"><span data-stu-id="61d22-107">![LINQ Filtering Operation](../../../../csharp/programming-guide/concepts/linq/media/linq_filter.png "LINQ_Filter")</span></span>  
  
 <span data-ttu-id="61d22-108">선택을 수행하는 표준 쿼리 연산자 메서드는 다음 섹션에 나열됩니다.</span><span class="sxs-lookup"><span data-stu-id="61d22-108">The standard query operator methods that perform selection are listed in the following section.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="61d22-109">메서드</span><span class="sxs-lookup"><span data-stu-id="61d22-109">Methods</span></span>  
  
|<span data-ttu-id="61d22-110">메서드 이름</span><span class="sxs-lookup"><span data-stu-id="61d22-110">Method Name</span></span>|<span data-ttu-id="61d22-111">설명</span><span class="sxs-lookup"><span data-stu-id="61d22-111">Description</span></span>|<span data-ttu-id="61d22-112">C# 쿼리 식 구문</span><span class="sxs-lookup"><span data-stu-id="61d22-112">C# Query Expression Syntax</span></span>|<span data-ttu-id="61d22-113">추가 정보</span><span class="sxs-lookup"><span data-stu-id="61d22-113">More Information</span></span>|  
|-----------------|-----------------|---------------------------------|----------------------|  
|<span data-ttu-id="61d22-114">OfType</span><span class="sxs-lookup"><span data-stu-id="61d22-114">OfType</span></span>|<span data-ttu-id="61d22-115">지정된 형식으로 캐스트할 수 있는지 여부에 따라 값을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="61d22-115">Selects values, depending on their ability to be cast to a specified type.</span></span>|<span data-ttu-id="61d22-116">해당 사항 없음.</span><span class="sxs-lookup"><span data-stu-id="61d22-116">Not applicable.</span></span>|<xref:System.Linq.Enumerable.OfType%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.OfType%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="61d22-117">Where</span><span class="sxs-lookup"><span data-stu-id="61d22-117">Where</span></span>|<span data-ttu-id="61d22-118">조건자 함수를 기반으로 하는 값을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="61d22-118">Selects values that are based on a predicate function.</span></span>|`where`|<xref:System.Linq.Enumerable.Where%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Where%2A?displayProperty=nameWithType>|  
  
## <a name="query-expression-syntax-example"></a><span data-ttu-id="61d22-119">쿼리 식 구문 예제</span><span class="sxs-lookup"><span data-stu-id="61d22-119">Query Expression Syntax Example</span></span>  
 <span data-ttu-id="61d22-120">다음 예제에서는 `where` 절을 사용하여 배열에서 특정 길이의 문자열을 필터링합니다.</span><span class="sxs-lookup"><span data-stu-id="61d22-120">The following example uses the `where` clause to filter from an array those strings that have a specific length.</span></span>  
  
```csharp  
string[] words = { "the", "quick", "brown", "fox", "jumps" };  
  
IEnumerable<string> query = from word in words  
                            where word.Length == 3  
                            select word;  
  
foreach (string str in query)  
    Console.WriteLine(str);  
  
/* This code produces the following output:  
  
    the  
    fox  
*/  
```  
  
## <a name="see-also"></a><span data-ttu-id="61d22-121">참고 항목</span><span class="sxs-lookup"><span data-stu-id="61d22-121">See Also</span></span>

- <xref:System.Linq>  
- [<span data-ttu-id="61d22-122">표준 쿼리 연산자 개요(C#)</span><span class="sxs-lookup"><span data-stu-id="61d22-122">Standard Query Operators Overview (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/standard-query-operators-overview.md)  
- [<span data-ttu-id="61d22-123">where 절</span><span class="sxs-lookup"><span data-stu-id="61d22-123">where clause</span></span>](../../../../csharp/language-reference/keywords/where-clause.md)  
- [<span data-ttu-id="61d22-124">방법: 런타임에 동적으로 조건자 필터 지정</span><span class="sxs-lookup"><span data-stu-id="61d22-124">How to: Dynamically Specify Predicate Filters at Runtime</span></span>](../../../../csharp/programming-guide/linq-query-expressions/how-to-dynamically-specify-predicate-filters-at-runtime.md)  
- [<span data-ttu-id="61d22-125">방법: 리플렉션을 사용하여 어셈블리의 메타데이터 쿼리(LINQ)(C#)</span><span class="sxs-lookup"><span data-stu-id="61d22-125">How to: Query An Assembly's Metadata with Reflection (LINQ) (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/how-to-query-an-assembly-s-metadata-with-reflection-linq.md)  
- [<span data-ttu-id="61d22-126">방법: 지정된 특성 또는 이름을 갖는 파일 쿼리(C#)</span><span class="sxs-lookup"><span data-stu-id="61d22-126">How to: Query for Files with a Specified Attribute or Name (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/how-to-query-for-files-with-a-specified-attribute-or-name.md)  
- [<span data-ttu-id="61d22-127">방법: 단어 또는 필드에 따라 텍스트 데이터 정렬 또는 필터링(LINQ)(C#)</span><span class="sxs-lookup"><span data-stu-id="61d22-127">How to: Sort or Filter Text Data by Any Word or Field (LINQ) (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/how-to-sort-or-filter-text-data-by-any-word-or-field-linq.md)
