---
title: "매개 변수 전달(C# 프로그래밍 가이드)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- parameters [C#], passing
- passing parameters [C#]
- arguments [C#]
- methods [C#], passing parameters
- C# language, method parameters
ms.assetid: a5c3003f-7441-4710-b8b1-c79de77e0b77
caps.latest.revision: 17
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 4b8c0c7f7b8c3820edbafbe90fb961c12da8fc84
ms.contentlocale: ko-kr
ms.lasthandoff: 07/28/2017

---
# <a name="passing-parameters-c-programming-guide"></a><span data-ttu-id="ce978-102">매개 변수 전달(C# 프로그래밍 가이드)</span><span class="sxs-lookup"><span data-stu-id="ce978-102">Passing Parameters (C# Programming Guide)</span></span>
<span data-ttu-id="ce978-103">C#에서는 인수를 값 또는 참조로 매개 변수에 전달할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ce978-103">In C#, arguments can be passed to parameters either by value or by reference.</span></span> <span data-ttu-id="ce978-104">참조로 전달하면 함수 멤버, 메서드, 속성, 인덱서, 연산자 및 생성자가 매개 변수의 값을 변경하고 해당 변경 내용을 호출 환경에서 유지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ce978-104">Passing by reference enables function members, methods, properties, indexers, operators, and constructors to change the value of the parameters and have that change persist in the calling environment.</span></span> <span data-ttu-id="ce978-105">참조로 매개 변수를 전달하려면 `ref` 또는 `out` 키워드를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="ce978-105">To pass a parameter by reference, use the `ref` or `out` keyword.</span></span> <span data-ttu-id="ce978-106">간단히 설명하기 위해 이 항목의 예제에서는 `ref` 키워드만 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="ce978-106">For simplicity, only the `ref` keyword is used in the examples in this topic.</span></span> <span data-ttu-id="ce978-107">`ref` 및 `out` 간의 차이점에 대한 자세한 내용은 [ref](../../../csharp/language-reference/keywords/ref.md), [out](../../../csharp/language-reference/keywords/out.md) 및 [ref 및 out을 사용하여 배열 전달](../../../csharp/programming-guide/arrays/passing-arrays-using-ref-and-out.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ce978-107">For more information about the difference between `ref` and `out`, see [ref](../../../csharp/language-reference/keywords/ref.md), [out](../../../csharp/language-reference/keywords/out.md), and [Passing Arrays Using ref and out](../../../csharp/programming-guide/arrays/passing-arrays-using-ref-and-out.md).</span></span>  
  
 <span data-ttu-id="ce978-108">다음 예제에서는 값 및 참조 매개 변수 간의 차이점을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="ce978-108">The following example illustrates the difference between value and reference parameters.</span></span>  
  
 <span data-ttu-id="ce978-109">[!code-cs[csProgGuideParameters#10](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/passing-parameters_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="ce978-109">[!code-cs[csProgGuideParameters#10](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/passing-parameters_1.cs)]</span></span>  
  
 <span data-ttu-id="ce978-110">자세한 내용은 다음 항목을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ce978-110">For more information, see the following topics:</span></span>  
  
-   [<span data-ttu-id="ce978-111">값 형식 매개 변수 전달</span><span class="sxs-lookup"><span data-stu-id="ce978-111">Passing Value-Type Parameters</span></span>](../../../csharp/programming-guide/classes-and-structs/passing-value-type-parameters.md)  
  
-   [<span data-ttu-id="ce978-112">참조 형식 매개 변수 전달</span><span class="sxs-lookup"><span data-stu-id="ce978-112">Passing Reference-Type Parameters</span></span>](../../../csharp/programming-guide/classes-and-structs/passing-reference-type-parameters.md)  
  
## <a name="c-language-specification"></a><span data-ttu-id="ce978-113">C# 언어 사양</span><span class="sxs-lookup"><span data-stu-id="ce978-113">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="ce978-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ce978-114">See Also</span></span>  
 <span data-ttu-id="ce978-115">[C# 프로그래밍 가이드](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="ce978-115">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 [<span data-ttu-id="ce978-116">메서드</span><span class="sxs-lookup"><span data-stu-id="ce978-116">Methods</span></span>](../../../csharp/programming-guide/classes-and-structs/methods.md)

