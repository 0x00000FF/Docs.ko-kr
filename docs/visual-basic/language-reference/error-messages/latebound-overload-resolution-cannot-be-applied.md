---
title: 액세스 인스턴스가 인터페이스 형식이므로 런타임에 바인딩 오버로드 확인을 '<procedurename>'에 적용할 수 없습니다.
ms.date: 07/20/2015
f1_keywords:
- vbc30933
- bc30933
helpviewer_keywords:
- overload resolution [Visual Basic], with late-bound argument
- BC30933
ms.assetid: 8182eea0-dd34-4d6e-9ca0-41d8713e9dc4
ms.openlocfilehash: 7215be3f454f4a799124620fb5db520282988035
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/30/2019
ms.locfileid: "55272641"
---
# <a name="latebound-overload-resolution-cannot-be-applied-to-procedurename-because-the-accessing-instance-is-an-interface-type"></a><span data-ttu-id="132f8-102">런타임에 바인딩 오버 로드 확인에 적용할 수 없습니다 '\<procedurename >' 액세스 인스턴스가 인터페이스 형식 이므로</span><span class="sxs-lookup"><span data-stu-id="132f8-102">Latebound overload resolution cannot be applied to '\<procedurename>' because the accessing instance is an interface type</span></span>
<span data-ttu-id="132f8-103">컴파일러에서 오버 로드 된 속성 또는 프로시저에 대 한 참조를 확인 하려고 시도 하지만 인수 형식 이므로 참조 실패 `Object` 참조 하는 개체 인터페이스의 데이터 형식이 고 합니다.</span><span class="sxs-lookup"><span data-stu-id="132f8-103">The compiler is attempting to resolve a reference to an overloaded property or procedure, but the reference fails because an argument is of type `Object` and the referring object has the data type of an interface.</span></span> <span data-ttu-id="132f8-104">`Object` 인수를 사용 하면 런타임에 바인딩된으로 참조를 해결 하려면 컴파일러.</span><span class="sxs-lookup"><span data-stu-id="132f8-104">The `Object` argument forces the compiler to resolve the reference as late-bound.</span></span>  
  
 <span data-ttu-id="132f8-105">이러한 상황에서는 컴파일러 대신 기본 인터페이스를 통해 구현 클래스를 통해 오버 로드를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="132f8-105">In these circumstances, the compiler resolves the overload through the implementing class instead of through the underlying interface.</span></span> <span data-ttu-id="132f8-106">클래스 이름 바꾸기 오버 로드 된 버전 중 하나, 컴파일러가 이름과 다르기 때문에 오버 로드 되도록 해당 버전을 고려 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="132f8-106">If the class renames one of the overloaded versions, the compiler does not consider that version to be an overload because its name is different.</span></span> <span data-ttu-id="132f8-107">이 컴파일러에서 참조를 해결 하려면 올바른 선택 되었을 때 이름이 바뀐된 버전을 무시 합니다.</span><span class="sxs-lookup"><span data-stu-id="132f8-107">This in turn causes the compiler to ignore the renamed version when it might have been the correct choice to resolve the reference.</span></span>  
  
 <span data-ttu-id="132f8-108">**오류 ID:** BC30933</span><span class="sxs-lookup"><span data-stu-id="132f8-108">**Error ID:** BC30933</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="132f8-109">이 오류를 해결하려면</span><span class="sxs-lookup"><span data-stu-id="132f8-109">To correct this error</span></span>  
  
-   <span data-ttu-id="132f8-110">사용 하 여 `CType` 에 있는 인수를 캐스팅할 `Object` 호출 하려는 오버 로드의 서명에서 지정 된 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="132f8-110">Use `CType` to cast the argument from `Object` to the type specified by the signature of the overload you want to call.</span></span>  
  
     <span data-ttu-id="132f8-111">참고를 참조 하는 기본 인터페이스에 개체를 캐스팅 하는 데 도움이 되지는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="132f8-111">Note that it does not help to cast the referring object to the underlying interface.</span></span> <span data-ttu-id="132f8-112">이 오류를 방지 하려면 인수를 캐스팅 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="132f8-112">You must cast the argument to avoid this error.</span></span>  
  
## <a name="example"></a><span data-ttu-id="132f8-113">예제</span><span class="sxs-lookup"><span data-stu-id="132f8-113">Example</span></span>  
 <span data-ttu-id="132f8-114">다음 예제에서는 오버 로드에 대 한 호출 `Sub` 프로시저 컴파일 타임에이 오류가 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="132f8-114">The following example shows a call to an overloaded `Sub` procedure that causes this error at compile time.</span></span>  
  
```  
Module m1  
    Interface i1  
        Sub s1(ByVal p1 As Integer)  
        Sub s1(ByVal p1 As Double)  
    End Interface  
    Class c1  
        Implements i1  
        Public Overloads Sub s1(ByVal p1 As Integer) Implements i1.s1  
        End Sub  
        Public Overloads Sub s2(ByVal p1 As Double) Implements i1.s1  
        End Sub  
    End Class  
    Sub Main()  
        Dim refer As i1 = New c1  
        Dim o1 As Object = 3.1415  
        ' The following reference is INVALID and causes a compiler error.  
        refer.s1(o1)   
    End Sub  
End Module  
```  
  
 <span data-ttu-id="132f8-115">위의 예제에서는 컴파일러에 대 한 호출을 허용 하는 경우 `s1` 확인이 클래스를 통해 작성 된 대로 수행 `c1` 인터페이스 대신 `i1`합니다.</span><span class="sxs-lookup"><span data-stu-id="132f8-115">In the preceding example, if the compiler allowed the call to `s1` as written, the resolution would take place through the class `c1` instead of the interface `i1`.</span></span> <span data-ttu-id="132f8-116">컴파일러를 고려 하지 않습니다 의미 `s2` 해당 이름에서 다르기 때문 `c1`경우에 적합 한 것으로 정의 된 대로 `i1`입니다.</span><span class="sxs-lookup"><span data-stu-id="132f8-116">This would mean that the compiler would not consider `s2` because its name is different in `c1`, even though it is the correct choice as defined by `i1`.</span></span>  
  
 <span data-ttu-id="132f8-117">코드의 다음 줄 중 하나에 대 한 호출을 변경 하 여 오류를 해결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="132f8-117">You can correct the error by changing the call to either of the following lines of code:</span></span>  
  
```  
refer.s1(CType(o1, Integer))  
refer.s1(CType(o1, Double))  
```  
  
 <span data-ttu-id="132f8-118">코드의 이전 줄을 각각 명시적으로 캐스팅 합니다 `Object` 변수 `o1` 오버 로드에 대해 정의 된 매개 변수 형식 중 하나에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="132f8-118">Each of the preceding lines of code explicitly casts the `Object` variable `o1` to one of the parameter types defined for the overloads.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="132f8-119">참고자료</span><span class="sxs-lookup"><span data-stu-id="132f8-119">See also</span></span>
- [<span data-ttu-id="132f8-120">프로시저 오버로딩</span><span class="sxs-lookup"><span data-stu-id="132f8-120">Procedure Overloading</span></span>](../../../visual-basic/programming-guide/language-features/procedures/procedure-overloading.md)
- [<span data-ttu-id="132f8-121">오버로드 확인</span><span class="sxs-lookup"><span data-stu-id="132f8-121">Overload Resolution</span></span>](../../../visual-basic/programming-guide/language-features/procedures/overload-resolution.md)
- [<span data-ttu-id="132f8-122">CType 함수</span><span class="sxs-lookup"><span data-stu-id="132f8-122">CType Function</span></span>](../../../visual-basic/language-reference/functions/ctype-function.md)
