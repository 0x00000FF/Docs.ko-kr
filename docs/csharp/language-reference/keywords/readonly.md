---
title: "readonly(C# 참조)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- readonly_CSharpKeyword
- readonly
helpviewer_keywords:
- readonly keyword [C#]
ms.assetid: 2f8081f6-0de2-4903-898d-99696c48d2f4
caps.latest.revision: 
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: b499f9fc5121afe6c2e92bcf8c5d2ac593b4c06c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="readonly-c-reference"></a><span data-ttu-id="24717-102">readonly(C# 참조)</span><span class="sxs-lookup"><span data-stu-id="24717-102">readonly (C# Reference)</span></span>
<span data-ttu-id="24717-103">`readonly` 키워드는 필드에 사용할 수 있는 한정자입니다.</span><span class="sxs-lookup"><span data-stu-id="24717-103">The `readonly` keyword is a modifier that you can use on fields.</span></span> <span data-ttu-id="24717-104">필드 선언에 `readonly` 한정자가 포함되어 있는 경우 선언에 의해 추가된 필드에 대한 할당은 선언의 일부로서 또는 같은 클래스의 생성자에서만 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="24717-104">When a field declaration includes a `readonly` modifier, assignments to the fields introduced by the declaration can only occur as part of the declaration or in a constructor in the same class.</span></span>  
  
## <a name="example"></a><span data-ttu-id="24717-105">예제</span><span class="sxs-lookup"><span data-stu-id="24717-105">Example</span></span>  
 <span data-ttu-id="24717-106">이 예제에서는 클래스 생성자에서 값이 할당되지만, `year` 필드의 값을 `ChangeYear` 메서드에서 변경할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="24717-106">In this example, the value of the field `year` cannot be changed in the method `ChangeYear`, even though it is assigned a value in the class constructor:</span></span>  
  
 [!code-csharp[csrefKeywordsModifiers#14](../../../csharp/language-reference/keywords/codesnippet/CSharp/readonly_1.cs)]  
  
 <span data-ttu-id="24717-107">다음 컨텍스트에서만 `readonly` 필드에 값을 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="24717-107">You can assign a value to a `readonly` field only in the following contexts:</span></span>  
  
-   <span data-ttu-id="24717-108">변수가 선언에서 초기화될 때. 예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="24717-108">When the variable is initialized in the declaration, for example:</span></span>  
  
    ```  
    public readonly int y = 5;  
    ```  
  
-   <span data-ttu-id="24717-109">인스턴스 필드의 경우 필드 선언이 포함된 클래스의 인스턴스 생성자에서, 또는 정적 필드의 경우 필드 선언이 포함된 클래스의 정적 생성자에서.</span><span class="sxs-lookup"><span data-stu-id="24717-109">For an instance field, in the instance constructors of the class that contains the field declaration, or for a static field, in the static constructor of the class that contains the field declaration.</span></span> <span data-ttu-id="24717-110">`readonly` 필드를 [out](../../../csharp/language-reference/keywords/out.md) 또는 [ref](../../../csharp/language-reference/keywords/ref.md)로 전달하는 것이 유효한 컨텍스트는 이러한 경우뿐입니다.</span><span class="sxs-lookup"><span data-stu-id="24717-110">These are also the only contexts in which it is valid to pass a `readonly` field as an [out](../../../csharp/language-reference/keywords/out.md) or [ref](../../../csharp/language-reference/keywords/ref.md) parameter.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="24717-111">`readonly` 키워드와 [const](../../../csharp/language-reference/keywords/const.md) 키워드와 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="24717-111">The `readonly` keyword is different from the [const](../../../csharp/language-reference/keywords/const.md) keyword.</span></span> <span data-ttu-id="24717-112">`const` 필드는 필드 선언에서만 초기화될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="24717-112">A `const` field can only be initialized at the declaration of the field.</span></span> <span data-ttu-id="24717-113">`readonly` 필드는 선언이나 생성자에서 초기화될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="24717-113">A `readonly` field can be initialized either at the declaration or in a constructor.</span></span> <span data-ttu-id="24717-114">따라서 `readonly` 필드는 사용된 생성자에 따라 다른 값을 가질 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="24717-114">Therefore, `readonly` fields can have different values depending on the constructor used.</span></span> <span data-ttu-id="24717-115">또한 `const` 필드는 컴파일 시간 상수인 반면, `readonly` 필드는 다음 예제와 같이 런타임 상수에 사용될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="24717-115">Also, while a `const` field is a compile-time constant, the `readonly` field can be used for runtime constants as in the following example:</span></span>  
  
```  
public static readonly uint timeStamp = (uint)DateTime.Now.Ticks;  
```  
  
## <a name="example"></a><span data-ttu-id="24717-116">예제</span><span class="sxs-lookup"><span data-stu-id="24717-116">Example</span></span>  
 [!code-csharp[csrefKeywordsModifiers#15](../../../csharp/language-reference/keywords/codesnippet/CSharp/readonly_2.cs)]  
  
 <span data-ttu-id="24717-117">위의 예제에서 다음과 같은 문을 사용하는 경우</span><span class="sxs-lookup"><span data-stu-id="24717-117">In the preceding example, if you use a statement like this:</span></span>  
  
 `p2.y = 66;        // Error`  
  
 <span data-ttu-id="24717-118">컴파일러 오류 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="24717-118">you will get the compiler error message:</span></span>  
  
 `The left-hand side of an assignment must be an l-value`  
  
 <span data-ttu-id="24717-119">상수에 값을 할당하려고 할 때 표시되는 것과 같은 오류입니다.</span><span class="sxs-lookup"><span data-stu-id="24717-119">which is the same error you get when you attempt to assign a value to a constant.</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="24717-120">C# 언어 사양</span><span class="sxs-lookup"><span data-stu-id="24717-120">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="24717-121">참고 항목</span><span class="sxs-lookup"><span data-stu-id="24717-121">See Also</span></span>  
 [<span data-ttu-id="24717-122">C# 참조</span><span class="sxs-lookup"><span data-stu-id="24717-122">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="24717-123">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="24717-123">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="24717-124">C# 키워드</span><span class="sxs-lookup"><span data-stu-id="24717-124">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
 [<span data-ttu-id="24717-125">한정자</span><span class="sxs-lookup"><span data-stu-id="24717-125">Modifiers</span></span>](../../../csharp/language-reference/keywords/modifiers.md)  
 [<span data-ttu-id="24717-126">const</span><span class="sxs-lookup"><span data-stu-id="24717-126">const</span></span>](../../../csharp/language-reference/keywords/const.md)  
 [<span data-ttu-id="24717-127">필드</span><span class="sxs-lookup"><span data-stu-id="24717-127">Fields</span></span>](../../../csharp/programming-guide/classes-and-structs/fields.md)
