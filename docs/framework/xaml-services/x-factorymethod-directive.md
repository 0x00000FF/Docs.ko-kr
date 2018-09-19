---
title: x:FactoryMethod 지시문
ms.date: 03/30/2017
helpviewer_keywords:
- XAML. x:FactoryMethod directive [XAML Services]
- FactoryMethod directive in XAML [XAML Services]
- x:FactoryMethod directive [XAML Services]
ms.assetid: 829bcbdf-5318-4afb-9a03-c310e0d2f23d
ms.openlocfilehash: 436caa9b93467dcf2a0763bcc0962a2beb722315
ms.sourcegitcommit: 5bbfe34a9a14e4ccb22367e57b57585c208cf757
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/17/2018
ms.locfileid: "45972022"
---
# <a name="xfactorymethod-directive"></a><span data-ttu-id="8ce9c-102">x:FactoryMethod 지시문</span><span class="sxs-lookup"><span data-stu-id="8ce9c-102">x:FactoryMethod Directive</span></span>
<span data-ttu-id="8ce9c-103">XAML 프로세서는 지원 형식 해결 한 후 개체를 초기화 하는 데 사용 해야 하는 생성자 이외의 메서드를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="8ce9c-103">Specifies a method other than a constructor that a XAML processor should use to initialize an object after resolving its backing type.</span></span>  
  
## <a name="xaml-attribute-usage-no-xarguments"></a><span data-ttu-id="8ce9c-104">X: 인수 없이 XAML 특성 사용</span><span class="sxs-lookup"><span data-stu-id="8ce9c-104">XAML Attribute Usage, no x:Arguments</span></span>  
  
```  
<object x:FactoryMethod="methodname"...>  
  ...  
</object>  
```  
  
## <a name="xaml-attribute-usage-xarguments-as-elements"></a><span data-ttu-id="8ce9c-105">X:arguments 요소도 XAML 특성 사용</span><span class="sxs-lookup"><span data-stu-id="8ce9c-105">XAML Attribute Usage, x:Arguments as Element(s)</span></span>  
  
```  
<object x:FactoryMethod="methodname"...>  
  <x:Arguments>  
    oneOrMoreObjectElements  
  </x:Arguments>  
</object>  
```  
  
## <a name="xaml-values"></a><span data-ttu-id="8ce9c-106">XAML 값</span><span class="sxs-lookup"><span data-stu-id="8ce9c-106">XAML Values</span></span>  
  
|||  
|-|-|  
|`methodname`|<span data-ttu-id="8ce9c-107">XAML 프로세서 호출로 지정 된 인스턴스를 초기화 하는 메서드의 문자열 메서드 이름을 `object`입니다.</span><span class="sxs-lookup"><span data-stu-id="8ce9c-107">The string method name of a method that XAML processors call to initialize the instance specified as `object`.</span></span> <span data-ttu-id="8ce9c-108">설명 부분을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="8ce9c-108">See Remarks.</span></span>|  
|`oneOrMoreObjectElements`|<span data-ttu-id="8ce9c-109">팩터리 메서드 매개 변수를 지정 하는 개체에 대 한 하나 이상의 개체 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="8ce9c-109">One or more object elements for objects that specify factory method parameters.</span></span> <span data-ttu-id="8ce9c-110">순서가 중요 하지 않습니다. 팩터리 메서드에 인수를 전달 하는 순서를 의미 합니다.</span><span class="sxs-lookup"><span data-stu-id="8ce9c-110">Order is significant; it signifies the order in which arguments should be passed to the factory method.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8ce9c-111">설명</span><span class="sxs-lookup"><span data-stu-id="8ce9c-111">Remarks</span></span>  
 <span data-ttu-id="8ce9c-112">경우 `methodname` 인스턴스 메서드는 정규화 할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="8ce9c-112">If `methodname` is an instance method, it cannot be qualified.</span></span>  
  
 <span data-ttu-id="8ce9c-113">팩터리 메서드를 사용 하 여 정적 메서드 지원 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8ce9c-113">Static methods as factory methods are supported.</span></span> <span data-ttu-id="8ce9c-114">하는 경우 `methodname` 는 정적 메서드입니다 `methodname` 으로 제공 되는 *typeName*. *methodName* 조합, 여기서 *typeName* 정적 팩터리 메서드를 정의 하는 클래스의 이름을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="8ce9c-114">If `methodname` is a static method, `methodname` is provided as a *typeName*.*methodName* combination, where *typeName* names the class that defines the static factory method.</span></span> <span data-ttu-id="8ce9c-115">*typeName* 맵핑된 xmlns에서 형식을 참조 하는 경우 접두사 정규화 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8ce9c-115">*typeName* can be prefix-qualified if referring to a type in a mapped xmlns.</span></span> <span data-ttu-id="8ce9c-116">*typeName* 보다 다양 한 형식일 수 있습니다 `typeof(object)`합니다.</span><span class="sxs-lookup"><span data-stu-id="8ce9c-116">*typeName* can be a different type than `typeof(object)`.</span></span>  
  
 <span data-ttu-id="8ce9c-117">팩터리 메서드는 관련 개체 요소를 지 원하는 형식의 선언된 된 공용 메서드가 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8ce9c-117">The factory method must be a declared public method of the type that backs the relevant object element.</span></span>  
  
 <span data-ttu-id="8ce9c-118">팩터리 메서드는 관련 개체에 할당 될 수 있는 인스턴스를 반환 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8ce9c-118">The factory method must return an instance that is assignable to the relevant object.</span></span> <span data-ttu-id="8ce9c-119">팩터리 메서드가 null을 반환 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8ce9c-119">Factory methods should never return null.</span></span>  
  
 <span data-ttu-id="8ce9c-120">`x:Arguments` 팩터리 메서드 서명에 대 한 가장 일치 하는 원칙에서 작동합니다.</span><span class="sxs-lookup"><span data-stu-id="8ce9c-120">`x:Arguments` operates on a principle of best match for signatures of factory methods.</span></span> <span data-ttu-id="8ce9c-121">일치 하는 매개 변수 개수를 먼저 평가합니다.</span><span class="sxs-lookup"><span data-stu-id="8ce9c-121">Matching evaluates the parameter count first.</span></span> <span data-ttu-id="8ce9c-122">매개 변수 개수에 대 한 둘 이상의 가능한 일치 하는 경우 평가 되 고 가장 일치 하는 다음 매개 변수 유형이입니다.</span><span class="sxs-lookup"><span data-stu-id="8ce9c-122">If there is more than one possible match for a parameter count, parameter type is then evaluated and best match is determined.</span></span> <span data-ttu-id="8ce9c-123">이 평가 단계 후 모호성 지속 되 면 XAML 프로세서 동작은 정의 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8ce9c-123">If there is still ambiguity after this phase of evaluation, XAML processor behavior is undefined.</span></span>  
  
 <span data-ttu-id="8ce9c-124">`x:FactoryMethod` 요소 사용 아니므로 일반적으로, 속성 요소 사용 지시문 태그가 포함 된 개체 요소 형식을 참조 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8ce9c-124">The `x:FactoryMethod` element usage is not property element usage in the typical sense, because the directive markup does not reference the containing object element's type.</span></span> <span data-ttu-id="8ce9c-125">예상 하지만 요소는 특성 사용 보다 일반적이 지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8ce9c-125">It is expected that element usage is less common than attribute usage.</span></span> <span data-ttu-id="8ce9c-126">`x:Arguments` (특성 또는 요소 사용)와 함께 사용할 수 있습니다 `x:FactoryMethod` 요소를 사용 하지만이 표시 되지 않으면 특별히 사용 섹션입니다.</span><span class="sxs-lookup"><span data-stu-id="8ce9c-126">`x:Arguments` (either attribute or element usage) can be used along with `x:FactoryMethod` element usage, but this is not specifically shown in the Usage sections.</span></span>  
  
 <span data-ttu-id="8ce9c-127">`x:FactoryMethod` 요소는 다른 모든 속성 요소의 앞에 야, 대로 나와야 모든 `x:Arguments` 도 요소로 제공 되며 모든 콘텐츠/내부 텍스트/초기화 텍스트 앞에 야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8ce9c-127">`x:FactoryMethod` as an element must precede any other property elements, must precede any `x:Arguments` also provided as elements, and must precede any content/inner text/initialization text.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8ce9c-128">참고 항목</span><span class="sxs-lookup"><span data-stu-id="8ce9c-128">See Also</span></span>  
 [<span data-ttu-id="8ce9c-129">x:Arguments 지시문</span><span class="sxs-lookup"><span data-stu-id="8ce9c-129">x:Arguments Directive</span></span>](../../../docs/framework/xaml-services/x-arguments-directive.md)
