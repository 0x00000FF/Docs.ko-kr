---
title: "nameof(C# 참조)"
ms.date: 2017-06-16
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- nameof_CSharpKeyword
- nameof
dev_langs:
- CSharp
ms.assetid: 33601bf3-cc2c-4496-846d-f9679bccf2a7
caps.latest.revision: 3
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
ms.openlocfilehash: db79af5f38439b881863cf3e03aa0e684ec5cd39
ms.contentlocale: ko-kr
ms.lasthandoff: 07/28/2017

---
# <a name="nameof-c-reference"></a><span data-ttu-id="f5108-102">nameof(C# 참조)</span><span class="sxs-lookup"><span data-stu-id="f5108-102">nameof (C# Reference)</span></span>

<span data-ttu-id="f5108-103">변수, 형식 또는 멤버의 단순(정규화되지 않은) 문자열 이름을 가져오는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="f5108-103">Used to obtain the simple (unqualified) string name of a variable, type, or member.</span></span>  

<span data-ttu-id="f5108-104">코드에서 오류를 보고하거나, MVC(모델-뷰-컨트롤러) 링크를 연결하거나, 속성 변경됨 이벤트를 발생시키는 경우 등에서 대체로 메서드의 문자열 이름을 캡처하려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="f5108-104">When reporting errors in code, hooking up model-view-controller (MVC) links, firing property changed events, etc., you often want to capture the string name of a method.</span></span>  <span data-ttu-id="f5108-105">`nameof`를 사용하면 정의 이름을 바꿀 때 코드 유효성을 유지하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f5108-105">Using `nameof` helps keep your code valid when renaming definitions.</span></span>  <span data-ttu-id="f5108-106">이전에는 문자열 리터럴을 사용하여 정의를 참조해야 했으며, 도구에서 해당 문자열 리터럴을 검사하는 방법을 알 수 없기 때문에 코드 요소의 이름을 바꿀 때는 불안정합니다.</span><span class="sxs-lookup"><span data-stu-id="f5108-106">Before, you had to use string literals to refer to definitions, which is brittle when renaming code elements because tools do not know to check these string literals.</span></span>  
  
 <span data-ttu-id="f5108-107">`nameof` 식의 형식은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="f5108-107">A `nameof` expression has this form:</span></span>  
  
```csharp  
if (x == null) throw new ArgumentNullException(nameof(x));  
WriteLine(nameof(person.Address.ZipCode)); // prints "ZipCode"  
```  
  
## <a name="key-use-cases"></a><span data-ttu-id="f5108-108">주요 사용 사례</span><span class="sxs-lookup"><span data-stu-id="f5108-108">Key Use Cases</span></span>  
 <span data-ttu-id="f5108-109">이러한 예제에서는 `nameof`의 주요 사용 사례를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="f5108-109">These examples show the key use cases for `nameof`.</span></span>  
  
 <span data-ttu-id="f5108-110">매개 변수 유효성 검사:</span><span class="sxs-lookup"><span data-stu-id="f5108-110">Validate parameters:</span></span>  
 ```csharp  
void f(string s) {  
    if (s == null) throw new ArgumentNullException(nameof(s));  
}  
```  
  
 <span data-ttu-id="f5108-111">MVC 작업 링크:</span><span class="sxs-lookup"><span data-stu-id="f5108-111">MVC Action links:</span></span>  
 ```html  
<%= Html.ActionLink("Sign up",  
             @typeof(UserController),  
             @nameof(UserController.SignUp))  
%>  
```  
  
 <span data-ttu-id="f5108-112">INotifyPropertyChanged:</span><span class="sxs-lookup"><span data-stu-id="f5108-112">INotifyPropertyChanged:</span></span>  
 ```csharp  
int p {  
    get { return this.p; }  
    set { this.p = value; PropertyChanged(this, new PropertyChangedEventArgs(nameof(this.p)); } // nameof(p) works too  
}  
```  
  
 <span data-ttu-id="f5108-113">XAML 종속성 속성:</span><span class="sxs-lookup"><span data-stu-id="f5108-113">XAML dependency property:</span></span>  
 ```csharp  
public static DependencyProperty AgeProperty = DependencyProperty.Register(nameof(Age), typeof(int), typeof(C));  
```  
  
 <span data-ttu-id="f5108-114">로깅:</span><span class="sxs-lookup"><span data-stu-id="f5108-114">Logging:</span></span>  
 ```csharp  
void f(int i) {  
    Log(nameof(f), "method entry");  
}  
```  
  
 <span data-ttu-id="f5108-115">특성:</span><span class="sxs-lookup"><span data-stu-id="f5108-115">Attributes:</span></span>  
 ```csharp  
[DebuggerDisplay("={" + nameof(GetString) + "()}")]  
class C {  
    string GetString() { }  
}  
```  
  
## <a name="examples"></a><span data-ttu-id="f5108-116">예</span><span class="sxs-lookup"><span data-stu-id="f5108-116">Examples</span></span>  
 <span data-ttu-id="f5108-117">일부 C# 예제:</span><span class="sxs-lookup"><span data-stu-id="f5108-117">Some C# examples:</span></span>  
  
```csharp  
using Stuff = Some.Cool.Functionality  
class C {  
    static int Method1 (string x, int y) {}  
    static int Method1 (string x, string y) {}  
    int Method2 (int z) {}  
    string f<T>() => nameof(T);  
}  
  
var c = new C()  
  
nameof(C) -> "C"  
nameof(C.Method1) -> "Method1"   
nameof(C.Method2) -> "Method2"  
nameof(c.Method1) -> "Method1"   
nameof(c.Method2) -> "Method2"  
nameof(z) -> "z" // inside of Method2 ok, inside Method1 is a compiler error  
nameof(Stuff) = "Stuff"  
nameof(T) -> "T" // works inside of method but not in attributes on the method  
nameof(f) -> "f"  
nameof(f<T>) -> syntax error  
nameof(f<>) -> syntax error  
nameof(Method2()) -> error "This expression does not have a name"  
```  
  
## <a name="remarks"></a><span data-ttu-id="f5108-118">설명</span><span class="sxs-lookup"><span data-stu-id="f5108-118">Remarks</span></span>  
 <span data-ttu-id="f5108-119">`nameof`에 대한 인수는 단순한 이름, 정규화된 이름, 멤버 액세스, 지정된 멤버를 사용한 기본 액세스 또는 지정된 멤버를 사용한 이 액세스여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f5108-119">The argument to `nameof` must be a simple name, qualified name, member access, base access with a specified member, or this access with a specified member.</span></span>  <span data-ttu-id="f5108-120">인수 식은 코드 정의를 식별하지만 계산되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f5108-120">The argument expression identifies a code definition, but it is never evaluated.</span></span>  
  
 <span data-ttu-id="f5108-121">인수는 구문상 식이어야 하므로 나열해도 유용하지 않은, 허용되지 않는 많은 항목이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f5108-121">Because the argument needs to be an expression syntactically, there are many things disallowed that are not useful to list.</span></span>  <span data-ttu-id="f5108-122">오류를 생성하는 다음 항목은 주의해야 합니다. 미리 정의된 형식(예: `int` 또는 `void`), null 허용 형식(`Point?`), 배열 형식(`Customer[,]`), 포인터 형식(`Buffer*`), 정규화된 별칭(`A::B`), 바운딩되지 않은 제네릭 형식(`Dictionary<,>`), 전처리 기호(`DEBUG`) 및 레이블(`loop:`).</span><span class="sxs-lookup"><span data-stu-id="f5108-122">The following are worth mentioning that produce errors: predefined types (for example, `int` or `void`), nullable types (`Point?`), array types (`Customer[,]`), pointer types (`Buffer*`), qualified alias (`A::B`), and unbound generic types (`Dictionary<,>`), preprocessing symbols (`DEBUG`), and labels (`loop:`).</span></span>  
  
 <span data-ttu-id="f5108-123">정규화된 이름을 가져와야 하는 경우 `nameof`와 함께 `typeof` 식을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f5108-123">If you need to get the fully-qualified name, you can use the `typeof` expression along with `nameof`.</span></span>  <span data-ttu-id="f5108-124">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="f5108-124">For example:</span></span>
```csharp  
class C {
    void f(int i) {  
        Log($"{typeof(C)}.{nameof(f)}", "method entry");  
    }
}
``` 

 <span data-ttu-id="f5108-125">안타깝게도 `typeof`는 `nameof`와 같은 상수 식이 아니므로 `nameof`와 동일한 모든 장소에서 `typeof`를 `nameof`와 함께 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f5108-125">Unfortunately `typeof` is not a constant expression like `nameof`, so `typeof` cannot be used in conjunction with `nameof` in all the same places as `nameof`.</span></span>  <span data-ttu-id="f5108-126">예를 들어 다음 코드는 CS0182 컴파일 오류를 발생시킵니다.</span><span class="sxs-lookup"><span data-stu-id="f5108-126">For example, the following would cause a CS0182 compile error:</span></span>
 ```csharp  
[DebuggerDisplay("={" + typeof(C) + nameof(GetString) + "()}")]  
class C {  
    string GetString() { }  
}  
```    
 <span data-ttu-id="f5108-127">예제에서 형식 이름을 사용하여 인스턴스 메서드 이름에 액세스할 수 있는 것을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f5108-127">In the examples you see that you can use a type name and access an instance method name.</span></span>  <span data-ttu-id="f5108-128">계산된 식에서 필요한 것처럼 형식의 인스턴스를 포함할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f5108-128">You do not need to have an instance of the type, as required in evaluated expressions.</span></span>  <span data-ttu-id="f5108-129">형식 이름을 사용하면 매우 편리한 경우가 있으며, 이름만 참조하고 인스턴스 데이터를 사용하지 않는 경우 인스턴스 변수 또는 식을 고려할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f5108-129">Using the type name can be very convenient in some situations, and since you are just referring to the name and not using instance data, you do not need to contrive an instance variable or expression.</span></span>  
  
 <span data-ttu-id="f5108-130">클래스의 특성 식에서 클래스 멤버를 참조할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f5108-130">You can reference the members of a class in attribute expressions on the class.</span></span>  
  
 <span data-ttu-id="f5108-131">"`Method1 (str, str)`"과 같은 서명 정보를 가져올 수 있는 방법은 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f5108-131">There is no way to get a signatures information such as "`Method1 (str, str)`".</span></span>  <span data-ttu-id="f5108-132">이 작업을 수행하는 한 가지 방법은 `Expression e = () => A.B.Method1("s1", "s2")` 식을 사용하고 결과 식 트리에서 MemberInfo를 끌어오는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="f5108-132">One way to do that is to use an Expression, `Expression e = () => A.B.Method1("s1", "s2")`, and pull the MemberInfo from the resulting expression tree.</span></span>  
  
## <a name="language-specifications"></a><span data-ttu-id="f5108-133">언어 사양</span><span class="sxs-lookup"><span data-stu-id="f5108-133">Language Specifications</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="f5108-134">참고 항목</span><span class="sxs-lookup"><span data-stu-id="f5108-134">See Also</span></span>  
 <span data-ttu-id="f5108-135">[C# 참조](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="f5108-135">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="f5108-136">[C# 프로그래밍 가이드](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="f5108-136">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 [<span data-ttu-id="f5108-137">typeof</span><span class="sxs-lookup"><span data-stu-id="f5108-137">typeof</span></span>](../../../csharp/language-reference/keywords/typeof.md)   
 

