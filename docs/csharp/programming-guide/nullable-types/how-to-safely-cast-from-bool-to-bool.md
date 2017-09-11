---
title: "방법: bool?에서 bool로 안전하게 캐스팅(C# 프로그래밍 가이드)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- casting [C#], nullable types
- nullable types [C#], casting bool? to bool
ms.assetid: e06e4274-a443-422d-8ef1-9dbf9df55237
caps.latest.revision: 9
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
ms.openlocfilehash: c8a3dc3280b7dca802b327d9454c7f0ba9ed44be
ms.contentlocale: ko-kr
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-safely-cast-from-bool-to-bool-c-programming-guide"></a><span data-ttu-id="a8572-102">방법: bool?에서 bool로 안전하게 캐스팅(C# 프로그래밍 가이드)</span><span class="sxs-lookup"><span data-stu-id="a8572-102">How to: Safely Cast from bool? to bool (C# Programming Guide)</span></span>
<span data-ttu-id="a8572-103">`bool?` nullable 형식은 세 가지 값 `true`, `false` 및 `null`을 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a8572-103">The `bool?` nullable type can contain three different values: `true`, `false`, and `null`.</span></span> <span data-ttu-id="a8572-104">따라서 `bool?` 형식은 `if`, `for` 또는 `while`과 같은 조건에 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a8572-104">Therefore, the `bool?` type cannot be used in conditionals such as with `if`, `for`, or `while`.</span></span> <span data-ttu-id="a8572-105">예를 들어 다음 코드는 컴파일러 오류를 발생시킵니다.</span><span class="sxs-lookup"><span data-stu-id="a8572-105">For example, the following code causes a compiler error.</span></span>  
  
```  
bool? b = null;  
if (b) // Error CS0266.  
{  
}  
```  
  
 <span data-ttu-id="a8572-106">조건부의 컨텍스트에서 `null`이 의미하는 내용이 명확하지 않으므로 이는 허용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a8572-106">This is not allowed because it is unclear what `null` means in the context of a conditional.</span></span> <span data-ttu-id="a8572-107">조건문에 `bool?`를 사용하려면 먼저 해당 <xref:System.Nullable%601.HasValue%2A> 속성을 점검하여 해당 값이 `null`이 아닌지 확인한 다음, `bool`로 캐스팅합니다.</span><span class="sxs-lookup"><span data-stu-id="a8572-107">To use a `bool?` in a conditional statement, first check its <xref:System.Nullable%601.HasValue%2A> property to ensure that its value is not `null`, and then cast it to `bool`.</span></span> <span data-ttu-id="a8572-108">자세한 내용은 [bool](../../../csharp/language-reference/keywords/bool.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="a8572-108">For more information, see [bool](../../../csharp/language-reference/keywords/bool.md).</span></span> <span data-ttu-id="a8572-109">값이 `null`인 `bool?`에 대해 캐스팅을 수행하면 조건 테스트에서 <xref:System.InvalidOperationException>이 throw됩니다.</span><span class="sxs-lookup"><span data-stu-id="a8572-109">If you perform the cast on a `bool?` with a value of `null`, a <xref:System.InvalidOperationException> will be thrown in the conditional test.</span></span> <span data-ttu-id="a8572-110">다음 예제에서는 `bool?`에서 `bool`로 안전하게 캐스팅하는 한 가지 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="a8572-110">The following example shows one way to safely cast from `bool?` to `bool`:</span></span>  
  
## <a name="example"></a><span data-ttu-id="a8572-111">예제</span><span class="sxs-lookup"><span data-stu-id="a8572-111">Example</span></span>  
  
```csharp  
bool? test = null;  
// Other code that may or may not  
// give a value to test.  
if(!test.HasValue) //check for a value  
{  
    // Assume that IsInitialized  
    // returns either true or false.  
    test = IsInitialized();  
}  
if((bool)test) //now this cast is safe  
{  
   // Do something.  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="a8572-112">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a8572-112">See Also</span></span>  
 <span data-ttu-id="a8572-113">[C# 프로그래밍 가이드](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="a8572-113">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="a8572-114">[리터럴 키워드](../../../csharp/language-reference/keywords/literal-keywords.md) </span><span class="sxs-lookup"><span data-stu-id="a8572-114">[Literal Keywords](../../../csharp/language-reference/keywords/literal-keywords.md) </span></span>  
 <span data-ttu-id="a8572-115">[Nullable 형식](../../../csharp/programming-guide/nullable-types/index.md) </span><span class="sxs-lookup"><span data-stu-id="a8572-115">[Nullable Types](../../../csharp/programming-guide/nullable-types/index.md) </span></span>  
 [<span data-ttu-id="a8572-116">?? 연산자</span><span class="sxs-lookup"><span data-stu-id="a8572-116">?? Operator</span></span>](../../../csharp/language-reference/operators/null-conditional-operator.md)

