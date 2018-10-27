---
title: 참조 반환 값 (Visual Basic)
ms.date: 04/28/2017
helpviewer_keywords:
- variables [Visual Basic]
- ref return values [Visual Basic]
- ref returns [Visual Basic]
ms.assetid: 5ef0cc69-eb3a-4a67-92a2-78585f223cb5
ms.openlocfilehash: ba649c4beaf3ec70a8c118f823fe8f25651a05a7
ms.sourcegitcommit: 4621e67f69e7a9503ea93313ff60d69683207889
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2018
ms.locfileid: "49995141"
---
# <a name="support-for-reference-return-values-visual-basic"></a><span data-ttu-id="20237-102">참조 반환 값 (Visual Basic)에 대 한 지원</span><span class="sxs-lookup"><span data-stu-id="20237-102">Support for reference return values (Visual Basic)</span></span>

<span data-ttu-id="20237-103">부터 C# 7.0에는 C# 언어 지원 *반환 값을 참조*합니다.</span><span class="sxs-lookup"><span data-stu-id="20237-103">Starting with C# 7.0, the C# language supports *reference return values*.</span></span> <span data-ttu-id="20237-104">참조 반환 값을 이해 하는 한 가지 방법은 이들이 반대 메서드에 참조로 전달 되는 인수입니다.</span><span class="sxs-lookup"><span data-stu-id="20237-104">One way to understand reference return values is that they are the opposite of arguments that are passed by reference to a method.</span></span> <span data-ttu-id="20237-105">참조로 전달 되는 인수 수정 되 면 변경 내용이 호출자에 변수의 값에 반영 됩니다.</span><span class="sxs-lookup"><span data-stu-id="20237-105">When an argument passed by reference is modified, the changes are reflected in value of the variable on the caller.</span></span> <span data-ttu-id="20237-106">호출자에 게 참조 반환 값을 제공 하는 메서드를, 호출자가 참조 반환 값에 대 한 수정 호출된 된 메서드의 데이터에 반영 됩니다.</span><span class="sxs-lookup"><span data-stu-id="20237-106">When an method provides a reference return value to a caller, modifications made to the reference return value by the caller are reflected in the called method's data.</span></span>

<span data-ttu-id="20237-107">Visual Basic 참조를 사용 하 여 만든 메서드에 값 돌아가게 없지만 참조 반환 값을 사용할 수 있습니다 수는 허용 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="20237-107">Visual Basic does not allow you to author methods with reference return values, but it does allow you to consume reference return values.</span></span> <span data-ttu-id="20237-108">즉, 참조 반환 값을 사용 하 여 메서드를 호출 하 고 해당 반환 값을 수정할 수 있습니다 및 참조 반환 값을 변경 하는 호출된 된 메서드의 데이터에 반영 됩니다.</span><span class="sxs-lookup"><span data-stu-id="20237-108">In other words, you can call a method with a reference return value and modify that return value, and changes to the reference return value are reflected in the called method's data.</span></span>

## <a name="modifying-the-ref-return-value-directly"></a><span data-ttu-id="20237-109">참조 반환 값을 직접 수정</span><span class="sxs-lookup"><span data-stu-id="20237-109">Modifying the ref return value directly</span></span>

<span data-ttu-id="20237-110">항상 실패 하 고 없는 하는 방법에 대 한 `ByRef` 매개 변수를 직접 참조 반환 값을 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="20237-110">For methods that always succeed and have no `ByRef` parameters, you can modify the reference return value directly.</span></span> <span data-ttu-id="20237-111">참조 반환 값을 반환 하는 식에 새 값을 할당 하 여이 작업을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="20237-111">You do this by assigning the new value to the expressions that returns the reference return value.</span></span> 

<span data-ttu-id="20237-112">다음 C# 예제에서는 정의 `NumericValue.IncrementValue` 메서드 내부 값을 증가 시키고 참조로 반환 하는 값을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="20237-112">The following C# example defines a `NumericValue.IncrementValue` method that increments an internal value and returns it as a reference return value.</span></span> 

[!code-csharp[Ref-Return](../../../../../samples/snippets/visualbasic/programming-guide/language-features/procedures/ref-returns1.cs)]

<span data-ttu-id="20237-113">참조 값이 다음 Visual Basic 예제에서는 호출자가 수정 후 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="20237-113">The reference return value is then modified by the caller in the following Visual Basic example.</span></span> <span data-ttu-id="20237-114">한 줄으로 된 `NumericValue.IncrementValue` 메서드 호출 메서드에 값을 할당 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="20237-114">Note that the line with the `NumericValue.IncrementValue` method call does not assign a value to the method.</span></span> <span data-ttu-id="20237-115">대신, 메서드에 의해 반환 되는 참조 반환 값을 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="20237-115">Instead, it assigns a value to the reference return value returned by the method.</span></span>

[!code-vb[Ref-Return](../../../../../samples/snippets/visualbasic/programming-guide/language-features/procedures/use-ref-returns1.vb)]

## <a name="using-a-helper-method"></a><span data-ttu-id="20237-116">도우미 메서드를 사용 하 여</span><span class="sxs-lookup"><span data-stu-id="20237-116">Using a helper method</span></span>

<span data-ttu-id="20237-117">다른 경우에 메서드 호출의 참조 반환 값을 직접 수정 항상 바람직하지 않을 합니다.</span><span class="sxs-lookup"><span data-stu-id="20237-117">In other cases, modifying the reference return value of a method call directly may not always be desirable.</span></span> <span data-ttu-id="20237-118">예를 들어 문자열을 반환 하는 검색 메서드를 찾을 수 없습니다 항상 일치 하는 합니다.</span><span class="sxs-lookup"><span data-stu-id="20237-118">For example, a search method that returns a string may not always find a match.</span></span> <span data-ttu-id="20237-119">이 경우 검색에 성공 하는 경우에 참조 반환 값을 수정 하려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="20237-119">In that case, you want to modify the reference return value only if the search is successful.</span></span>

<span data-ttu-id="20237-120">다음 C# 예제에서는이 시나리오를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="20237-120">The following C# example illustrates this scenario.</span></span> <span data-ttu-id="20237-121">정의 `Sentence` 로 작성 된 클래스 C# 포함을 `FindNext` 메서드는 지정된 된 부분 문자열을 사용 하 여 시작 하는 문장 내에서 다음 단어를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="20237-121">It defines a `Sentence` class written in C# includes a `FindNext` method that finds the next word in a sentence that begins with a specified substring.</span></span> <span data-ttu-id="20237-122">문자열은 참조 반환 값으로 반환되며, 메서드에 참조로 전달된 `Boolean` 변수는 검색에 성공했는지 여부를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="20237-122">The string is returned as a reference return value, and a `Boolean` variable passed by reference to the method indicates whether the search was successful.</span></span> <span data-ttu-id="20237-123">참조 반환 값이 나타냅니다는 호출자가 읽을 수 없습니다만 반환 되는 값입니다. 자신이 수정할 수 있으며 해당 수정에서 내부적으로 포함 된 데이터에 반영 됩니다는 `Sentence` 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="20237-123">The reference return value indicates that the caller can not only read the returned value; he or she can also modify it, and that modification is reflected in the data contained internally in the `Sentence` class.</span></span>

[!code-csharp[Ref-Return](../../../../../samples/snippets/visualbasic/getting-started/ref-returns.cs)]

<span data-ttu-id="20237-124">참조를 직접 수정 반환 값이 경우은 하지 않습니다, 신뢰할 수 있는 일치 항목을 찾을 문장의 첫 번째 단어를 반환 하는 메서드 호출이 실패할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="20237-124">Directly modifying the reference return value in this case is not reliable, since the method call may fail to find a match and return the first word in the sentence.</span></span> <span data-ttu-id="20237-125">이 경우 호출자가 문장의 첫 번째 단어를 실수로 수정 합니다.</span><span class="sxs-lookup"><span data-stu-id="20237-125">In that case, the caller will inadvertently modify the first word of the sentence.</span></span> <span data-ttu-id="20237-126">이 반환 하는 호출자에 의해 차단 될 수 있습니다는 `null` (또는 `Nothing` Visual basic에서).</span><span class="sxs-lookup"><span data-stu-id="20237-126">This could be prevented by the caller returning a `null` (or `Nothing` in Visual Basic).</span></span> <span data-ttu-id="20237-127">이 경우 값이 문자열을 수정 하려고 하지만 `Nothing` throw를 <xref:System.NullReferenceException>입니다.</span><span class="sxs-lookup"><span data-stu-id="20237-127">But in that case, attempting to modify a string whose value is `Nothing` throws a <xref:System.NullReferenceException>.</span></span> <span data-ttu-id="20237-128">반환 하는 호출자에 의해 차단 될 수 있습니다 하는 경우 <xref:System.String.Empty?displayProperty=nameWithType>를 호출자에 게 값인 문자열 변수 정의 필요 하지만 <xref:System.String.Empty?displayProperty=nameWithType>합니다.</span><span class="sxs-lookup"><span data-stu-id="20237-128">If could also be prevented by the caller returning <xref:System.String.Empty?displayProperty=nameWithType>, but this requires that the caller define a string variable whose value is <xref:System.String.Empty?displayProperty=nameWithType>.</span></span> <span data-ttu-id="20237-129">수정 된 문자열에서 저장 된 문장에 대 한 단어 아무런 관계가 있으므로 자체 수정 없는 용도로 호출자에 게 해당 문자열을 수정할 수, 하는 동안 사용 되는 `Sentence` 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="20237-129">While the caller can modify that string, the modification itself serves no purpose, since the modified string has no relationship to the words in the sentence stored by the `Sentence` class.</span></span>

<span data-ttu-id="20237-130">이 시나리오를 처리 하는 가장 좋은 방법은 도우미 메서드에 대 한 참조에서 참조 반환 값을 전달 하는 경우</span><span class="sxs-lookup"><span data-stu-id="20237-130">The best way to handle this scenario is to pass the reference return value by reference to a helper method.</span></span> <span data-ttu-id="20237-131">도우미 메서드는 다음 논리를 확인 하는지 여부를 메서드 호출에 성공한 경우 수정 하려면 참조 반환 값을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="20237-131">The helper method then contains the logic to determine whether the method call succeeded and, if it did, to modify the reference return value.</span></span> <span data-ttu-id="20237-132">다음 예제에서는 가능한 구현을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="20237-132">The following example provides a possible implementation.</span></span>

[!code-vb[Ref-Return](../../../../../samples/snippets/visualbasic/getting-started/ref-return-helper.vb#1)]

## <a name="see-also"></a><span data-ttu-id="20237-133">참고자료</span><span class="sxs-lookup"><span data-stu-id="20237-133">See also</span></span>

<span data-ttu-id="20237-134">[값 및 참조로 인수 전달](passing-arguments-by-value-and-by-reference.md) </span><span class="sxs-lookup"><span data-stu-id="20237-134">[Passing arguments by value and by reference](passing-arguments-by-value-and-by-reference.md) </span></span>  
[<span data-ttu-id="20237-135">Visual Basic의 프로시저</span><span class="sxs-lookup"><span data-stu-id="20237-135">Procedures in Visual Basic</span></span>](index.md)   


