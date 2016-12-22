---
title: "nameof(C# 및 Visual Basic 참조) | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "CSharp"
ms.assetid: 33601bf3-cc2c-4496-846d-f9679bccf2a7
caps.latest.revision: 3
caps.handback.revision: 3
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# nameof(C# 및 Visual Basic 참조)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

변수, 형식 또는 멤버의 단순\(정규화되지 않은\) 문자열 이름을 가져오는 데 사용됩니다.  코드에서 오류를 보고하거나, MVC\(모델\-뷰\-컨트롤러\) 링크를 연결하거나, 속성 변경됨 이벤트를 발생시키는 경우 등에서 대체로 메서드의 문자열 이름을 캡처하려고 합니다.  `nameof`를 사용하면 정의 이름을 바꿀 때 코드 유효성을 유지하는 데 도움이 됩니다.  이전에는 문자열 리터럴을 사용하여 정의를 참조해야 했으며, 도구에서 해당 문자열 리터럴을 검사하는 방법을 알 수 없기 때문에 코드 요소의 이름을 바꿀 때는 불안정합니다.  
  
 `nameof` 식의 형식은 다음과 같습니다.  
  
```c#  
if (x == null) throw new ArgumentNullException(nameof(x));  
WriteLine(nameof(person.Address.ZipCode)); // prints "ZipCode”  
  
```  
  
## 주요 사용 사례  
 이러한 예제에서는 `nameof`의 주요 사용 사례를 보여 줍니다.  
  
 매개 변수 유효성 검사:  
 ```c#  
void f(string s) {  
    if (s == null) throw new ArgumentNullException(nameof(s));  
}  
  
```  
  
 MVC 작업 링크:  
 ```html  
<%= Html.ActionLink("Sign up",  
             @typeof(UserController),  
             @nameof(UserController.SignUp))  
%>  
  
```  
  
 INotifyPropertyChanged:  
 ```c#  
int p {  
    get { return this.p; }  
    set { this.p = value; PropertyChanged(this, new PropertyChangedEventArgs(nameof(this.p)); } // nameof(p) works too  
}  
  
```  
  
 XAML 종속성 속성:  
 ```c#  
public static DependencyProperty AgeProperty = DependencyProperty.Register(nameof(Age), typeof(int), typeof(C));  
  
```  
  
 로깅:  
 ```c#  
void f(int i) {  
    Log(nameof(f), "method entry");  
}  
  
```  
  
 특성:  
 ```c#  
[DebuggerDisplay("={" + nameof(GetString) + "()}")]  
class C {  
    string GetString() { }  
}  
```  
  
## 예  
 일부 C\# 예제:  
  
```c#  
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
nameof(f) -> “f”  
nameof(f<T>) -> syntax error  
nameof(f<>) -> syntax error  
nameof(Method2()) -> error “This expression does not have a name”  
  
```  
  
 위 샘플은 대부분 Visual Basic에 적용됩니다.  다음은 몇 가지 특정 Visual Basic 예제입니다.  
  
```vb  
NameOf(a!Foo) -> ' error  "This expression does not have a name"  
NameOf(dict("Foo")) -> ' error  "This expression does not have a name": default property access  
NameOf(dict.Item("Foo")) -> ' error  "This expression does not have a name"  
NameOf(arr(2)) -> ' error  "This expression does not have a name": array element index  
Dim x = Nothing   
NameOf(x.ToString(2)) -> ' error  "This expression does not have a name"  
Dim o = Nothing  
NameOf(o.Equals) -> ' result "Equals".  Warning: "Access of static member of instance; instance will not be evaluated"  
  
```  
  
## 설명  
 `nameof`에 대한 인수는 단순한 이름, 정규화된 이름, 멤버 액세스, 지정된 멤버를 사용한 기본 액세스 또는 지정된 멤버를 사용한 이 액세스여야 합니다.  인수 식은 코드 정의를 식별하지만 계산되지 않습니다.  
  
 인수는 구문상 식이어야 하므로 나열해도 유용하지 않은, 허용되지 않는 많은 항목이 있습니다.  오류를 생성하는 다음 항목은 주의해야 합니다. 미리 정의된 형식\(예: `int` 또는 `void`\), null 허용 형식\(`Point?`\), 배열 형식\(`Customer[,]`\), 포인터 형식\(`Buffer*`\), 정규화된 별칭\(`A::B`\), 바운딩되지 않은 제네릭 형식\(`Dictionary<,>`\), 전처리 기호\(`DEBUG`\) 및 레이블\(`loop:`\).  
  
 정규화된 이름을 가져와야 하는 경우 `nameof`와 함께 `typeof` 식을 사용할 수 있습니다.  
  
 예제에서 형식 이름을 사용하여 인스턴스 메서드 이름에 액세스할 수 있는 것을 확인할 수 있습니다.  계산된 식에서 필요한 것처럼 형식의 인스턴스를 포함할 필요가 없습니다.  형식 이름을 사용하면 매우 편리한 경우가 있으며, 이름만 참조하고 인스턴스 데이터를 사용하지 않는 경우 인스턴스 변수 또는 식을 고려할 필요가 없습니다.  
  
 클래스의 특성 식에서 클래스 멤버를 참조할 수 있습니다.  
  
 "`Method1 (str, str)`"과 같은 서명 정보를 가져올 수 있는 방법은 없습니다.  이 작업을 수행하는 한 가지 방법은 `Expression e = () => A.B.Method1("s1", "s2")` 식을 사용하고 결과 식 트리에서 MemberInfo를 끌어오는 것입니다.  
  
## 언어 사양  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec_md.md)]  
  
 자세한 내용은 [Visual Basic Language Reference](../../../visual-basic/language-reference/index.md)를 참조하세요.  
  
## 참고 항목  
 [C\# 참조](../../../csharp/language-reference/index.md)   
 [C\# 프로그래밍 가이드](../../../csharp/programming-guide/index.md)   
 [typeof](../../../csharp/language-reference/keywords/typeof.md)   
 [Visual Basic Language Reference](../../../visual-basic/language-reference/index.md)   
 [Visual Basic Programming Guide](../../../visual-basic/programming-guide/index.md)