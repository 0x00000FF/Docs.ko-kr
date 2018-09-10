---
title: by 상황별 키워드(C# 참조)
ms.date: 07/20/2015
f1_keywords:
- by
- by_CSharpKeyword
helpviewer_keywords:
- by keyword [C#]
ms.assetid: efe6f0e3-be40-4df2-a144-c7db968ae052
ms.openlocfilehash: b2d9b08378dd0edf37c07663b3fe37a09f8acf47
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/04/2018
ms.locfileid: "43524504"
---
# <a name="by-c-reference"></a><span data-ttu-id="c3d9b-102">by(C# 참조)</span><span class="sxs-lookup"><span data-stu-id="c3d9b-102">by (C# Reference)</span></span>

<span data-ttu-id="c3d9b-103">`by` 상황별 키워드는 쿼리 식의 `group` 절에서 사용되어 반환된 항목의 그룹화 방법을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="c3d9b-103">The `by` contextual keyword is used in the `group` clause in a query expression to specify how the returned items should be grouped.</span></span> <span data-ttu-id="c3d9b-104">자세한 내용은 [group 절](../../../csharp/language-reference/keywords/group-clause.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c3d9b-104">For more information, see [group clause](../../../csharp/language-reference/keywords/group-clause.md).</span></span>

## <a name="example"></a><span data-ttu-id="c3d9b-105">예</span><span class="sxs-lookup"><span data-stu-id="c3d9b-105">Example</span></span>

<span data-ttu-id="c3d9b-106">다음 예제에서는 `group` 절에 `by` 상황별 키워드를 사용하여 각 학생의 성에서 첫 번째 문자에 따라 학생들을 그룹화하도록 지정하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="c3d9b-106">The following example shows the use of the `by` contextual keyword in a `group` clause to specify that the students should be grouped according to the first letter of the last name of each student.</span></span>

[!code-csharp[csrefKeywordsContextual#10](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsContextual/CS/csrefKeywordsContextual.cs#10)]

## <a name="see-also"></a><span data-ttu-id="c3d9b-107">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c3d9b-107">See also</span></span>

- [<span data-ttu-id="c3d9b-108">LINQ 쿼리 식</span><span class="sxs-lookup"><span data-stu-id="c3d9b-108">LINQ Query Expressions</span></span>](../../../csharp/programming-guide/linq-query-expressions/index.md)
