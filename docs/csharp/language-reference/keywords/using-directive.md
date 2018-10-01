---
title: using 지시문(C# 참조)
ms.date: 07/20/2015
helpviewer_keywords:
- using directive [C#]
ms.assetid: b42b8e61-5e7e-439c-bb71-370094b44ae8
ms.openlocfilehash: 1ed7ac49cde6792cddff898e8b9930a83598e02c
ms.sourcegitcommit: fb78d8abbdb87144a3872cf154930157090dd933
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/01/2018
ms.locfileid: "47231546"
---
# <a name="using-directive-c-reference"></a><span data-ttu-id="84a6c-102">using 지시문(C# 참조)</span><span class="sxs-lookup"><span data-stu-id="84a6c-102">using Directive (C# Reference)</span></span>
<span data-ttu-id="84a6c-103">`using` 지시문에는 다음 세 가지 용도가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="84a6c-103">The `using` directive has three uses:</span></span>  
  
-   <span data-ttu-id="84a6c-104">네임스페이스에서 형식 사용을 한정할 필요가 없도록 해당 네임스페이스에서 형식 사용을 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="84a6c-104">To allow the use of types in a namespace so that you do not have to qualify the use of a type in that namespace:</span></span>  
  
    ```csharp  
    using System.Text;  
    ```  
  
-   <span data-ttu-id="84a6c-105">형식 이름을 사용하여 액세스를 한정할 필요 없이 형식의 정적 멤버 및 중첩 형식에 액세스하도록 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="84a6c-105">To allow you to access static members and nested types of a type without having to qualify the access with the type name.</span></span> 
  
    ```csharp  
    using static System.Math;  
    ```  
     
    <span data-ttu-id="84a6c-106">자세한 내용은 [using 정적 지시문](using-static.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="84a6c-106">For more information, see the [using static directive](using-static.md).</span></span>

-   <span data-ttu-id="84a6c-107">네임스페이스 또는 형식에 대한 별칭을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="84a6c-107">To create an alias for a namespace or a type.</span></span> <span data-ttu-id="84a6c-108">이를 *using 별칭 지시문*이라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="84a6c-108">This is called a *using alias directive*.</span></span>  
  
    ```csharp  
    using Project = PC.MyCompany.Project;  
    ```  
  
 <span data-ttu-id="84a6c-109">`using` 키워드는 파일 및 글꼴과 같은 <xref:System.IDisposable> 개체가 제대로 처리될 수 있게 도와주는 *using 문*을 만드는 데도 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="84a6c-109">The `using` keyword is also used to create *using statements*, which help ensure that <xref:System.IDisposable> objects such as files and fonts are handled correctly.</span></span> <span data-ttu-id="84a6c-110">자세한 내용은 [using 문](../../../csharp/language-reference/keywords/using-statement.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="84a6c-110">See [using Statement](../../../csharp/language-reference/keywords/using-statement.md) for more information.</span></span>  
  
## <a name="using-static-type"></a><span data-ttu-id="84a6c-111">정적 형식 사용</span><span class="sxs-lookup"><span data-stu-id="84a6c-111">Using Static Type</span></span>  
 <span data-ttu-id="84a6c-112">형식 이름을 사용하여 액세스를 한정할 필요 없이 형식의 정적 멤버에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="84a6c-112">You can access static members of a type without having to qualify the access with the type name:</span></span>  
  
```csharp  
using static System.Console;   
using static System.Math;  
class Program   
{   
    static void Main()   
    {   
        WriteLine(Sqrt(3*3 + 4*4));   
    }   
}  
```  
  
## <a name="remarks"></a><span data-ttu-id="84a6c-113">설명</span><span class="sxs-lookup"><span data-stu-id="84a6c-113">Remarks</span></span>  
 <span data-ttu-id="84a6c-114">`using` 지시문의 범위는 지시문이 나타내는 파일로 제한됩니다.</span><span class="sxs-lookup"><span data-stu-id="84a6c-114">The scope of a `using` directive is limited to the file in which it appears.</span></span>
 
 <span data-ttu-id="84a6c-115">`using` 지시문이 나타날 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="84a6c-115">The `using` directive can appear:</span></span>
- <span data-ttu-id="84a6c-116">모든 네임스페이스 또는 형식 정의 전에 소스 파일을 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="84a6c-116">At the beginning of a source code file, before any namespace or type definitions.</span></span>
- <span data-ttu-id="84a6c-117">모든 네임스페이스에 있지만 이 네임스페이스에 선언된 네임스페이스 또는 형식 앞에 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="84a6c-117">In any namespace, but before any namespace or types declared in this namespace.</span></span>

<span data-ttu-id="84a6c-118">이렇게 하지 않으면 컴파일러 오류 [CS1529](../../misc/cs1529.md)가 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="84a6c-118">Otherwise, compiler error [CS1529](../../misc/cs1529.md) is generated.</span></span>
  
 <span data-ttu-id="84a6c-119">`using` 별칭 지시문을 만들면 네임스페이스 또는 형식에 대한 식별자를 더 쉽게 한정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="84a6c-119">Create a `using` alias directive to make it easier to qualify an identifier to a namespace or type.</span></span> <span data-ttu-id="84a6c-120">모든 `using` 지시문에서 앞에 오는 `using` 지시문에 관계없이 정규화된 네임스페이스 또는 형식을 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="84a6c-120">In any `using` directive, the fully-qualified namespace or type must be used regardless of the `using` directives that come before it.</span></span> <span data-ttu-id="84a6c-121">`using` 별칭은 `using` 지시문 선언에 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="84a6c-121">No `using` alias can be used in the declaration of a `using` directive.</span></span> <span data-ttu-id="84a6c-122">예를 들어, 다음은 컴파일러 오류를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="84a6c-122">For example, the following generates a compiler error:</span></span>
 ```csharp
 using s = System.Text;
 using s.RegularExpressions; 
 ```
  
 <span data-ttu-id="84a6c-123">`using` 지시문을 만들어서 네임스페이스를 지정할 필요 없이 네임스페이스에서 이 형식을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="84a6c-123">Create a `using` directive to use the types in a namespace without having to specify the namespace.</span></span> <span data-ttu-id="84a6c-124">`using` 지시문은 지정한 네임스페이스에 중첩된 모든 네임스페이스에 대한 액세스 권한을 제공하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="84a6c-124">A `using` directive does not give you access to any namespaces that are nested in the namespace you specify.</span></span>  
  
 <span data-ttu-id="84a6c-125">네임스페이스는 두 가지 범주인 사용자 정의 및 시스템 정의로 구분됩니다.</span><span class="sxs-lookup"><span data-stu-id="84a6c-125">Namespaces come in two categories: user-defined and system-defined.</span></span> <span data-ttu-id="84a6c-126">사용자 정의 네임스페이스는 코드에서 정의된 네임스페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="84a6c-126">User-defined namespaces are namespaces defined in your code.</span></span> <span data-ttu-id="84a6c-127">시스템 정의 네임스페이스 목록은 [.NET API 브라우저](https://docs.microsoft.com/en-us/dotnet/api/)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="84a6c-127">For a list of the system-defined namespaces, see [.NET API Browser](https://docs.microsoft.com/en-us/dotnet/api/).</span></span>  
  
 <span data-ttu-id="84a6c-128">다른 어셈블리의 메서드를 참조하는 예제는 [명령줄을 사용하여 어셈블리 만들기 및 사용](../../programming-guide/concepts/assemblies-gac/how-to-create-and-use-assemblies-using-the-command-line.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="84a6c-128">For examples on referencing methods in other assemblies, see [Create and Use Assemblies Using the Command Line](../../programming-guide/concepts/assemblies-gac/how-to-create-and-use-assemblies-using-the-command-line.md).</span></span>  
  
## <a name="example-1"></a><span data-ttu-id="84a6c-129">예제 1</span><span class="sxs-lookup"><span data-stu-id="84a6c-129">Example 1</span></span>  
  
 <span data-ttu-id="84a6c-130">다음 예제에서는 `using` 네임스페이스에 대한 별칭을 정의 및 사용하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="84a6c-130">The following example shows how to define and use a `using` alias for a namespace:</span></span>  
  
 [!code-csharp[csrefKeywordsNamespace#8](../../../csharp/language-reference/keywords/codesnippet/CSharp/using-directive_1.cs)]  
  
 <span data-ttu-id="84a6c-131">using alias 지시문의 오른쪽에는 공개 제네릭 형식이 포함될 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="84a6c-131">A using alias directive cannot have an open generic type on the right hand side.</span></span> <span data-ttu-id="84a6c-132">예를 들어 List\<T>에 대해서는 using 별칭을 만들 수 없지만 List\<int>에 대해서는 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="84a6c-132">For example, you cannot create a using alias for a List\<T>, but you can create one for a List\<int>.</span></span>  
  
## <a name="example-2"></a><span data-ttu-id="84a6c-133">예제 2</span><span class="sxs-lookup"><span data-stu-id="84a6c-133">Example 2</span></span>  
  
 <span data-ttu-id="84a6c-134">다음 예제에서는 클래스에 대한 `using` 지시문 및 `using` 별칭을 정의하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="84a6c-134">The following example shows how to define a `using` directive and a `using` alias for a class:</span></span>  
  
 [!code-csharp[csrefKeywordsNamespace#9](../../../csharp/language-reference/keywords/codesnippet/CSharp/using-directive_2.cs)]  
  
## <a name="c-language-specification"></a><span data-ttu-id="84a6c-135">C# 언어 사양</span><span class="sxs-lookup"><span data-stu-id="84a6c-135">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="84a6c-136">참고 항목</span><span class="sxs-lookup"><span data-stu-id="84a6c-136">See Also</span></span>

- [<span data-ttu-id="84a6c-137">C# 참조</span><span class="sxs-lookup"><span data-stu-id="84a6c-137">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
- [<span data-ttu-id="84a6c-138">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="84a6c-138">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="84a6c-139">네임스페이스 사용</span><span class="sxs-lookup"><span data-stu-id="84a6c-139">Using Namespaces</span></span>](../../../csharp/programming-guide/namespaces/using-namespaces.md)  
- [<span data-ttu-id="84a6c-140">C# 키워드</span><span class="sxs-lookup"><span data-stu-id="84a6c-140">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
- [<span data-ttu-id="84a6c-141">네임스페이스 키워드</span><span class="sxs-lookup"><span data-stu-id="84a6c-141">Namespace Keywords</span></span>](../../../csharp/language-reference/keywords/namespace-keywords.md)  
- [<span data-ttu-id="84a6c-142">네임스페이스</span><span class="sxs-lookup"><span data-stu-id="84a6c-142">Namespaces</span></span>](../../../csharp/programming-guide/namespaces/index.md)  
- [<span data-ttu-id="84a6c-143">using 문</span><span class="sxs-lookup"><span data-stu-id="84a6c-143">using Statement</span></span>](../../../csharp/language-reference/keywords/using-statement.md)
