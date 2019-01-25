---
title: 변수 형식이 &#39; &lt;variablename&gt; &#39; 는 바깥쪽 범위의 필드에 바인딩되어 있으므로 유추 되지 것입니다
ms.date: 07/20/2015
f1_keywords:
- vbc42110
- bc42110
helpviewer_keywords:
- BC42110
ms.assetid: ef4442eb-08d1-434f-a03b-4aa2ed4e4414
ms.openlocfilehash: 6adcc1c2a449c9192e488a5d714e1c3271568be0
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54672385"
---
# <a name="the-type-for-variable-39ltvariablenamegt39-will-not-be-inferred-because-it-is-bound-to-a-field-in-an-enclosing-scope"></a><span data-ttu-id="0207c-102">변수 형식이 &#39; &lt;variablename&gt; &#39; 는 바깥쪽 범위의 필드에 바인딩되어 있으므로 유추 되지 것입니다</span><span class="sxs-lookup"><span data-stu-id="0207c-102">The type for variable &#39;&lt;variablename&gt;&#39; will not be inferred because it is bound to a field in an enclosing scope</span></span>
<span data-ttu-id="0207c-103">변수 형식이 '\<variablename >'는 바깥쪽 범위의 필드에 바인딩되어 있으므로 유추 되지 것입니다.</span><span class="sxs-lookup"><span data-stu-id="0207c-103">The type for variable '\<variablename>' will not be inferred because it is bound to a field in an enclosing scope.</span></span> <span data-ttu-id="0207c-104">이름을 변경 하거나 '\<variablename >', 또는 정규화 된 이름 (예: 'Me.variablename' 또는 'MyBase.variablename')를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="0207c-104">Either change the name of '\<variablename>', or use the fully qualified name (for example, 'Me.variablename' or 'MyBase.variablename').</span></span>  
  
 <span data-ttu-id="0207c-105">코드에서 루프 제어 변수를 클래스 또는 다른 바깥쪽 범위의 필드와 동일한 이름이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0207c-105">A loop control variable in your code has the same name as a field of the class or other enclosing scope.</span></span> <span data-ttu-id="0207c-106">제어 변수 없이 사용 되기 때문에 `As` 절 바깥쪽 범위의 필드에 바인딩되어 및 컴파일러에 대 한 새 변수를 만들 하지 않거나 해당 형식을 유추 합니다.</span><span class="sxs-lookup"><span data-stu-id="0207c-106">Because the control variable is used without an `As` clause, it is bound to the field in the enclosing scope, and the compiler does not create a new variable for it or infer its type.</span></span>  
  
 <span data-ttu-id="0207c-107">다음 예에서 `Index`, 제어 변수는 `For` 문이 바인딩되는 `Index` 필드에 `Customer` 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="0207c-107">In the following example, `Index`, the control variable in the `For` statement, is bound to the `Index` field in the `Customer` class.</span></span> <span data-ttu-id="0207c-108">컴파일러 제어 변수의 새 변수를 만들지 않습니다 `Index` 또는 해당 형식을 유추 합니다.</span><span class="sxs-lookup"><span data-stu-id="0207c-108">The compiler does not create a new variable for the control variable `Index` or infer its type.</span></span>  
  
```  
Class Customer  
  
    ' The class has a field named Index.  
    Private Index As Integer  
  
    Sub Main()  
  
    ' The following line will raise this warning.  
        For Index = 1 To 10  
            ' ...  
        Next  
  
    End Sub  
End Class  
```  
  
 <span data-ttu-id="0207c-109">이 메시지는 기본적으로 경고입니다.</span><span class="sxs-lookup"><span data-stu-id="0207c-109">By default, this message is a warning.</span></span> <span data-ttu-id="0207c-110">경고를 숨기거나 오류로 처리하는 방법에 대한 자세한 내용은 [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="0207c-110">For information about how to hide warnings or how to treat warnings as errors, see [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span></span>  
  
 <span data-ttu-id="0207c-111">**오류 ID:** BC42110</span><span class="sxs-lookup"><span data-stu-id="0207c-111">**Error ID:** BC42110</span></span>  
  
### <a name="to-address-this-warning"></a><span data-ttu-id="0207c-112">이 경고를 해결하려면</span><span class="sxs-lookup"><span data-stu-id="0207c-112">To address this warning</span></span>  
  
-   <span data-ttu-id="0207c-113">클래스의 필드 이름을 수도 없는 식별자에 해당 이름을 변경 하 여 루프 제어 변수의 로컬을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="0207c-113">Make the loop control variable local by changing its name to an identifier that is not also the name of a field of the class.</span></span>  
  
    ```  
    For I = 1 To 10  
    ```  
  
-   <span data-ttu-id="0207c-114">바인딩되도록 합니다 루프 제어 변수의 클래스 필드를 접두사로 사용 하 여 `Me.` 변수 이름에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0207c-114">Clarify that the loop control variable binds to the class field by prefixing `Me.` to the variable name.</span></span>  
  
    ```  
    For Me.Index = 1 To 10  
    ```  
  
-   <span data-ttu-id="0207c-115">지역 형식 유추에 의존 하는 대신 사용 하 여는 `As` 루프 제어 변수의 형식을 지정 하는 절.</span><span class="sxs-lookup"><span data-stu-id="0207c-115">Instead of relying on local type inference, use an `As` clause to specify a type for the loop control variable.</span></span>  
  
    ```  
    For Index As Integer = 1 To 10  
    ```  
  
## <a name="example"></a><span data-ttu-id="0207c-116">예제</span><span class="sxs-lookup"><span data-stu-id="0207c-116">Example</span></span>  
 <span data-ttu-id="0207c-117">다음 코드 위치에 있는 첫 번째 수정 앞의 예제를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="0207c-117">The following code shows the earlier example with the first correction in place.</span></span>  
  
```  
Class Customer  
  
    ' The class has a field named Index.  
    Private Index As Integer  
  
    Sub Main()  
  
        For I = 1 To 10  
            ' ...  
        Next  
  
    End Sub  
End Class  
```  
  
## <a name="see-also"></a><span data-ttu-id="0207c-118">참고자료</span><span class="sxs-lookup"><span data-stu-id="0207c-118">See also</span></span>
- [<span data-ttu-id="0207c-119">Option Infer 문</span><span class="sxs-lookup"><span data-stu-id="0207c-119">Option Infer Statement</span></span>](../../../visual-basic/language-reference/statements/option-infer-statement.md)
- [<span data-ttu-id="0207c-120">For Each...Next 문</span><span class="sxs-lookup"><span data-stu-id="0207c-120">For Each...Next Statement</span></span>](../../../visual-basic/language-reference/statements/for-each-next-statement.md)
- [<span data-ttu-id="0207c-121">For...Next 문</span><span class="sxs-lookup"><span data-stu-id="0207c-121">For...Next Statement</span></span>](../../../visual-basic/language-reference/statements/for-next-statement.md)
- [<span data-ttu-id="0207c-122">방법: 개체의 현재 인스턴스 참조</span><span class="sxs-lookup"><span data-stu-id="0207c-122">How to: Refer to the Current Instance of an Object</span></span>](../../../visual-basic/programming-guide/language-features/variables/how-to-refer-to-the-current-instance-of-an-object.md)
- [<span data-ttu-id="0207c-123">지역 형식 유추</span><span class="sxs-lookup"><span data-stu-id="0207c-123">Local Type Inference</span></span>](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)
- [<span data-ttu-id="0207c-124">Me, My, MyBase 및 MyClass</span><span class="sxs-lookup"><span data-stu-id="0207c-124">Me, My, MyBase, and MyClass</span></span>](../../../visual-basic/programming-guide/program-structure/me-my-mybase-and-myclass.md)
