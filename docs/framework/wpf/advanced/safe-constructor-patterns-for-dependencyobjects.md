---
title: DependencyObject의 안전한 생성자 패턴
ms.date: 03/30/2017
helpviewer_keywords:
- constructor patterns for dependency objects [WPF]
- dependency objects [WPF], constructor patterns
- FXCop tool [WPF]
ms.assetid: f704b81c-449a-47a4-ace1-9332e3cc6d60
ms.openlocfilehash: 66e380a9428395c772d0dcfe45a995374774aec6
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2019
ms.locfileid: "74283822"
---
# <a name="safe-constructor-patterns-for-dependencyobjects"></a><span data-ttu-id="3d76c-102">DependencyObject의 안전한 생성자 패턴</span><span class="sxs-lookup"><span data-stu-id="3d76c-102">Safe Constructor Patterns for DependencyObjects</span></span>
<span data-ttu-id="3d76c-103">일반적으로 클래스 생성자는 가상 메서드나 대리자와 같은 콜백을 호출하면 안 됩니다. 이는 생성자는 파생 클래스에 대한 생성자의 기본 초기화로 호출될 수 있기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="3d76c-103">Generally, class constructors should not call callbacks such as virtual methods or delegates, because constructors can be called as base initialization of constructors for a derived class.</span></span> <span data-ttu-id="3d76c-104">특정 개체의 불완전한 초기화 상태에서 가상 항목이 입력될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3d76c-104">Entering the virtual might be done at an incomplete initialization state of any given object.</span></span> <span data-ttu-id="3d76c-105">하지만 속성 시스템 자체는 내부적으로 콜백을 종속성 속성 시스템의 일부로 호출하고 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="3d76c-105">However, the property system itself calls and exposes callbacks internally, as part of the dependency property system.</span></span> <span data-ttu-id="3d76c-106"><xref:System.Windows.DependencyObject.SetValue%2A> 호출을 사용 하 여 종속성 속성 값을 설정 하는 작업은 잠재적으로 결정의 어딘가에 콜백을 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3d76c-106">As simple an operation as setting a dependency property value with <xref:System.Windows.DependencyObject.SetValue%2A> call potentially includes a callback somewhere in the determination.</span></span> <span data-ttu-id="3d76c-107">이런 이유로 생성자 본문에서 종속성 속성 값을 설정할 때 주의해야 합니다. 형식이 기본 클래스로 사용될 경우 문제가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3d76c-107">For this reason, you should be careful when setting dependency property values within the body of a constructor, which can become problematic if your type is used as a base class.</span></span> <span data-ttu-id="3d76c-108">종속성 속성 상태와 관련 된 특정 문제를 방지 하는 <xref:System.Windows.DependencyObject> 생성자와 여기에 설명 된 고유 콜백을 구현 하기 위한 특정 패턴이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3d76c-108">There is a particular pattern for implementing <xref:System.Windows.DependencyObject> constructors that avoids specific problems with dependency property states and the inherent callbacks, which is documented here.</span></span>  

<a name="Property_System_Virtual_Methods"></a>   
## <a name="property-system-virtual-methods"></a><span data-ttu-id="3d76c-109">속성 시스템 가상 메서드</span><span class="sxs-lookup"><span data-stu-id="3d76c-109">Property System Virtual Methods</span></span>  
 <span data-ttu-id="3d76c-110"><xref:System.Windows.ValidateValueCallback>, <xref:System.Windows.PropertyChangedCallback>, <xref:System.Windows.CoerceValueCallback>, <xref:System.Windows.DependencyObject.OnPropertyChanged%2A>종속성 속성 값을 설정 하는 <xref:System.Windows.DependencyObject.SetValue%2A> 호출을 계산 하는 동안 다음과 같은 가상 메서드 또는 콜백이 호출 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3d76c-110">The following virtual methods or callbacks are potentially called during the computations of the <xref:System.Windows.DependencyObject.SetValue%2A> call that sets a dependency property value: <xref:System.Windows.ValidateValueCallback>, <xref:System.Windows.PropertyChangedCallback>, <xref:System.Windows.CoerceValueCallback>, <xref:System.Windows.DependencyObject.OnPropertyChanged%2A>.</span></span> <span data-ttu-id="3d76c-111">이러한 각 가상 메서드 또는 콜백은 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] 속성 시스템 및 종속성 속성의 다양성을 확장하기 위한 특정 목적으로 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="3d76c-111">Each of these virtual methods or callbacks serves a particular purpose in expanding the versatility of the [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] property system and dependency properties.</span></span> <span data-ttu-id="3d76c-112">이러한 가상 항목을 사용하여 속성 값 확인을 사용자 지정하는 방법에 대한 자세한 내용은 [종속성 속성 콜백 및 유효성 검사](dependency-property-callbacks-and-validation.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="3d76c-112">For more information on how to use these virtuals to customize property value determination, see [Dependency Property Callbacks and Validation](dependency-property-callbacks-and-validation.md).</span></span>  
  
### <a name="fxcop-rule-enforcement-vs-property-system-virtuals"></a><span data-ttu-id="3d76c-113">FXCop 규칙 적용 및 속성 시스템 가상 컴퓨터</span><span class="sxs-lookup"><span data-stu-id="3d76c-113">FXCop Rule Enforcement vs. Property System Virtuals</span></span>  
 <span data-ttu-id="3d76c-114">Microsoft 도구 FXCop를 빌드 프로세스에 사용하고 기본 생성자를 호출하는 특정 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 프레임워크 클래스에서 파생시키거나 파생 클래스에서 자체 종속성 속성을 구현할 경우 특정 FXCop 규칙 위반이 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3d76c-114">If you use the Microsoft tool FXCop as part of your build process, and you either derive from certain [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] framework classes calling the base constructor, or implement your own dependency properties on derived classes, you might encounter a particular FXCop rule violation.</span></span> <span data-ttu-id="3d76c-115">이 위반에 대한 이름 문자열은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="3d76c-115">The name string for this violation is:</span></span>  
  
 `DoNotCallOverridableMethodsInConstructors`  
  
 <span data-ttu-id="3d76c-116">이 규칙은 FXCop에 대해 설정된 기본 공용 규칙의 일부입니다.</span><span class="sxs-lookup"><span data-stu-id="3d76c-116">This is a rule that is part of the default public rule set for FXCop.</span></span> <span data-ttu-id="3d76c-117">이 규칙은 최종적으로 종속성 속성 시스템 가상 메서드를 호출하는 종속성 속성 시스템을 통한 추적을 보고할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3d76c-117">What this rule might be reporting is a trace through the dependency property system that eventually calls a dependency property system virtual method.</span></span> <span data-ttu-id="3d76c-118">이 규칙 위반은 이 항목에 설명된 권장 생성자 패턴을 따른 후에도 계속 표시될 수 있으므로 FXCop 규칙 집합 구성에서 해당 규칙을 사용하지 않도록 설정하거나 억제해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3d76c-118">This rule violation might continue to appear even after following the recommended constructor patterns documented in this topic, so you might need to disable or suppress that rule in your FXCop rule set configuration.</span></span>  
  
### <a name="most-issues-come-from-deriving-classes-not-using-existing-classes"></a><span data-ttu-id="3d76c-119">대부분 문제는 기존 클래스를 사용하지 않고 클래스를 파생시킬 경우 발생함</span><span class="sxs-lookup"><span data-stu-id="3d76c-119">Most Issues Come From Deriving Classes, Not Using Existing Classes</span></span>  
 <span data-ttu-id="3d76c-120">이 규칙을 통해 보고된 문제는 생성 시퀀스에서 가상 메서드를 사용하여 구현하는 클래스가 파생될 때 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="3d76c-120">The issues reported by this rule occur when a class that you implement with virtual methods in its construction sequence is then derived from.</span></span> <span data-ttu-id="3d76c-121">클래스를 봉인할 경우 또는 클래스가 파생되지 않는지 알거나 파생되지 않도록 하는 경우에는 여기에 설명된 고려 사항과 FXCop 규칙을 유발한 문제가 적용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3d76c-121">If you seal your class, or otherwise know or enforce that your class will not be derived from, the considerations explained here and the issues that motivated the FXCop rule do not apply to you.</span></span> <span data-ttu-id="3d76c-122">하지만 기본 클래스로 사용되도록 클래스를 작성할 경우(예: 템플릿 또는 확장 가능한 컨트롤 라이브러리 집합을 만들 경우) 여기서 권장된 생성자에 대한 패턴을 따라야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3d76c-122">However, if you are authoring classes in such a way that they are intended to be used as base classes, for instance if you are creating templates, or an expandable control library set, you should follow the patterns recommended here for constructors.</span></span>  
  
### <a name="default-constructors-must-initialize-all-values-requested-by-callbacks"></a><span data-ttu-id="3d76c-123">기본 생성자는 콜백을 통해 요청된 모든 값을 초기화해야 함</span><span class="sxs-lookup"><span data-stu-id="3d76c-123">Default Constructors Must Initialize All Values Requested By Callbacks</span></span>  
 <span data-ttu-id="3d76c-124">클래스에서 사용 하는 인스턴스 멤버 (속성 시스템 가상 섹션의 목록에서 콜백)는 이러한 값 중 일부가 "실제" 값으로 채워지는 경우에도 매개 변수가 없는 생성자에서 초기화 되어야 합니다. 매개 변수가 없는 생성자의 매개 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="3d76c-124">Any instance members that are used by your class overrides or callbacks (the callbacks from the list in the Property System Virtuals section) must be initialized in your class parameterless constructor, even if some of those values are filled by "real" values through parameters of the nonparameterless constructors.</span></span>  
  
 <span data-ttu-id="3d76c-125">다음 예제 코드(및 이후 예제)는 이 규칙을 위반하고 문제를 설명하는 의사 C# 예제입니다.</span><span class="sxs-lookup"><span data-stu-id="3d76c-125">The following example code (and subsequent examples) is a pseudo-C# example that violates this rule and explains the problem:</span></span>  
  
```csharp  
public class MyClass : DependencyObject  
{  
    public MyClass() {}  
    public MyClass(object toSetWobble)  
        : this()  
    {  
        Wobble = toSetWobble; //this is backed by a DependencyProperty  
        _myList = new ArrayList();    // this line should be in the default ctor  
    }  
    public static readonly DependencyProperty WobbleProperty =   
        DependencyProperty.Register("Wobble", typeof(object), typeof(MyClass));  
    public object Wobble  
    {  
        get { return GetValue(WobbleProperty); }  
        set { SetValue(WobbleProperty, value); }  
    }  
    protected override void OnPropertyChanged(DependencyPropertyChangedEventArgs e)  
    {  
        int count = _myList.Count;    // null-reference exception  
    }  
    private ArrayList _myList;  
}  
```  
  
 <span data-ttu-id="3d76c-126">응용 프로그램 코드는 `new MyClass(objectvalue)`를 호출할 때 매개 변수가 없는 생성자와 기본 클래스 생성자를 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="3d76c-126">When application code calls `new MyClass(objectvalue)`, this calls the parameterless constructor and base class constructors.</span></span> <span data-ttu-id="3d76c-127">그런 다음 소유 하는 `MyClass` <xref:System.Windows.DependencyObject>에서 가상 메서드 `OnPropertyChanged`를 호출 하 `Property1 = object1`를 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="3d76c-127">Then it sets `Property1 = object1`, which calls the virtual method `OnPropertyChanged` on the owning `MyClass` <xref:System.Windows.DependencyObject>.</span></span>  <span data-ttu-id="3d76c-128">재정의는 아직 초기화되지 않은 `_myList`를 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="3d76c-128">The override refers to `_myList`, which has not been initialized yet.</span></span>  
  
 <span data-ttu-id="3d76c-129">이러한 문제를 피하는 한 가지 방법은 콜백이 기타 종속성 속성만 사용하고 각 종속성 속성에 설정된 기본값을 등록된 메타데이터로 포함하는지 확인하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="3d76c-129">One way to avoid these issues is to make sure that callbacks use only other dependency properties, and that each such dependency property has an established default value as part of its registered metadata.</span></span>  
  
<a name="Safe_Constructor_Patterns"></a>   
## <a name="safe-constructor-patterns"></a><span data-ttu-id="3d76c-130">안전한 생성자 패턴</span><span class="sxs-lookup"><span data-stu-id="3d76c-130">Safe Constructor Patterns</span></span>  
 <span data-ttu-id="3d76c-131">클래스가 기본 클래스로 사용될 경우 불완전한 초기화의 위험을 피하려면 다음 패턴을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="3d76c-131">To avoid the risks of incomplete initialization if your class is used as a base class, follow these patterns:</span></span>  
  
#### <a name="parameterless-constructors-calling-base-initialization"></a><span data-ttu-id="3d76c-132">기본 초기화를 호출 하는 매개 변수가 없는 생성자</span><span class="sxs-lookup"><span data-stu-id="3d76c-132">Parameterless constructors calling base initialization</span></span>  
 <span data-ttu-id="3d76c-133">기본 기본값을 호출하는 다음 생성자를 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="3d76c-133">Implement these constructors calling the base default:</span></span>  
  
```csharp  
public MyClass : SomeBaseClass {  
    public MyClass() : base() {  
        // ALL class initialization, including initial defaults for   
        // possible values that other ctors specify or that callbacks need.  
    }  
}  
```  
  
#### <a name="non-default-convenience-constructors-not-matching-any-base-signatures"></a><span data-ttu-id="3d76c-134">기본 시그니처와 일치하지 않는 기본값이 아닌(편의) 생성자</span><span class="sxs-lookup"><span data-stu-id="3d76c-134">Non-default (convenience) constructors, not matching any base signatures</span></span>  
 <span data-ttu-id="3d76c-135">이러한 생성자가 매개 변수를 사용 하 여 초기화에서 종속성 속성을 설정 하는 경우 먼저 초기화에 대 한 매개 변수가 없는 클래스 생성자를 호출한 다음 매개 변수를 사용 하 여 종속성 속성을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="3d76c-135">If these constructors use the parameters to set dependency properties in the initialization, first call your own class parameterless constructor for initialization, and then use the parameters to set dependency properties.</span></span> <span data-ttu-id="3d76c-136">이러한 속성은 클래스에서 정의된 종속성 속성이거나 기본 클래스에서 상속된 종속성 속성일 수 있지만 두 경우 중 하나에는 다음 패턴을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="3d76c-136">These could either be dependency properties defined by your class, or dependency properties inherited from base classes, but in either case use the following pattern:</span></span>  
  
```csharp  
public MyClass : SomeBaseClass {  
    public MyClass(object toSetProperty1) : this() {  
        // Class initialization NOT done by default.  
        // Then, set properties to values as passed in ctor parameters.  
        Property1 = toSetProperty1;  
    }  
}  
```  
  
#### <a name="non-default-convenience-constructors-which-do-match-base-signatures"></a><span data-ttu-id="3d76c-137">기본 시그니처와 일치하는 기본값이 아닌(편의) 생성자</span><span class="sxs-lookup"><span data-stu-id="3d76c-137">Non-default (convenience) constructors, which do match base signatures</span></span>  
 <span data-ttu-id="3d76c-138">동일한 매개 변수화를 사용 하 여 기본 생성자를 호출 하는 대신, 고유한 클래스의 매개 변수 없는 생성자를 다시 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="3d76c-138">Instead of calling the base constructor with the same parameterization, again call your own class' parameterless constructor.</span></span> <span data-ttu-id="3d76c-139">기본 이니셜라이저를 호출하지 마세요. 대신에 `this()`를 호출해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3d76c-139">Do not call the base initializer; instead you should call `this()`.</span></span> <span data-ttu-id="3d76c-140">그 다음에 전달된 매개 변수를 관련 속성을 설정하기 위한 값으로 사용하여 원래 생성자 동작을 재현합니다.</span><span class="sxs-lookup"><span data-stu-id="3d76c-140">Then reproduce the original constructor behavior by using the passed parameters as values for setting the relevant properties.</span></span> <span data-ttu-id="3d76c-141">특정 매개 변수가 설정해야 하는 속성을 결정하는 과정의 지침으로 원래 기본 생성자 문서를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="3d76c-141">Use the original base constructor documentation for guidance in determining the properties that the particular parameters are intended to set:</span></span>  
  
```csharp  
public MyClass : SomeBaseClass {  
    public MyClass(object toSetProperty1) : this() {  
        // Class initialization NOT done by default.  
        // Then, set properties to values as passed in ctor parameters.  
        Property1 = toSetProperty1;  
    }  
}  
```  
  
#### <a name="must-match-all-signatures"></a><span data-ttu-id="3d76c-142">모든 시그니처와 일치해야 함</span><span class="sxs-lookup"><span data-stu-id="3d76c-142">Must match all signatures</span></span>  
 <span data-ttu-id="3d76c-143">기본 형식에 여러 개의 시그니처가 있는 경우에는 추가로 설정 하기 전에 매개 변수 없는 생성자 클래스를 호출 하는 것이 좋습니다. 정보의.</span><span class="sxs-lookup"><span data-stu-id="3d76c-143">For cases where the base type has multiple signatures, you must deliberately match all possible signatures with a constructor implementation of your own that uses the recommended pattern of calling the class parameterless constructor before setting further properties.</span></span>  
  
#### <a name="setting-dependency-properties-with-setvalue"></a><span data-ttu-id="3d76c-144">SetValue를 사용하여 종속성 속성 설정</span><span class="sxs-lookup"><span data-stu-id="3d76c-144">Setting dependency properties with SetValue</span></span>  
 <span data-ttu-id="3d76c-145">이러한 동일한 패턴은 속성 설정 편의를 위한 래퍼가 없는 속성을 설정 하 고 <xref:System.Windows.DependencyObject.SetValue%2A>를 사용 하 여 값을 설정 하는 경우에 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3d76c-145">These same patterns apply if you are setting a property that does not have a wrapper for property setting convenience, and set values with <xref:System.Windows.DependencyObject.SetValue%2A>.</span></span> <span data-ttu-id="3d76c-146">생성자 매개 변수를 통과 하는 <xref:System.Windows.DependencyObject.SetValue%2A>에 대 한 호출은 초기화를 위해 클래스의 매개 변수가 없는 생성자도 호출 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3d76c-146">Your calls to <xref:System.Windows.DependencyObject.SetValue%2A> that pass through constructor parameters should also call the class' parameterless constructor for initialization.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3d76c-147">참고 항목</span><span class="sxs-lookup"><span data-stu-id="3d76c-147">See also</span></span>

- [<span data-ttu-id="3d76c-148">사용자 지정 종속성 속성</span><span class="sxs-lookup"><span data-stu-id="3d76c-148">Custom Dependency Properties</span></span>](custom-dependency-properties.md)
- [<span data-ttu-id="3d76c-149">종속성 속성 개요</span><span class="sxs-lookup"><span data-stu-id="3d76c-149">Dependency Properties Overview</span></span>](dependency-properties-overview.md)
- [<span data-ttu-id="3d76c-150">종속성 속성 보안</span><span class="sxs-lookup"><span data-stu-id="3d76c-150">Dependency Property Security</span></span>](dependency-property-security.md)
