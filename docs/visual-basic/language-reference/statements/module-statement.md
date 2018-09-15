---
title: Module 문 (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- Module
- vb.Module
helpviewer_keywords:
- modules, classes
- modules
- Module statement [Visual Basic]
- modules, declaring
- standard modules
- classes [Visual Basic], vs. modules
- declarations [Visual Basic], modules
ms.assetid: a1243afc-14a5-45df-95d5-51118aeac362
ms.openlocfilehash: 5628224a08fe5f12cf2a81b179c4998001174354
ms.sourcegitcommit: 6eac9a01ff5d70c6d18460324c016a3612c5e268
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/15/2018
ms.locfileid: "45653254"
---
# <a name="module-statement"></a><span data-ttu-id="c727a-102">Module 문</span><span class="sxs-lookup"><span data-stu-id="c727a-102">Module Statement</span></span>
<span data-ttu-id="c727a-103">모듈의 이름을 선언 하 고 변수, 속성, 이벤트 및 모듈을 구성 하는 프로시저의 정의 소개 합니다.</span><span class="sxs-lookup"><span data-stu-id="c727a-103">Declares the name of a module and introduces the definition of the variables, properties, events, and procedures that the module comprises.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c727a-104">구문</span><span class="sxs-lookup"><span data-stu-id="c727a-104">Syntax</span></span>  
  
```vb 
[ <attributelist> ] [ accessmodifier ]  Module name  
    [ statements ]  
End Module  
```  
  
## <a name="parts"></a><span data-ttu-id="c727a-105">요소</span><span class="sxs-lookup"><span data-stu-id="c727a-105">Parts</span></span>  
 `attributelist`  
 <span data-ttu-id="c727a-106">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="c727a-106">Optional.</span></span> <span data-ttu-id="c727a-107">참조 [특성 목록](../../../visual-basic/language-reference/statements/attribute-list.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="c727a-107">See [Attribute List](../../../visual-basic/language-reference/statements/attribute-list.md).</span></span>  
  
 `accessmodifier`  
 <span data-ttu-id="c727a-108">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="c727a-108">Optional.</span></span> <span data-ttu-id="c727a-109">다음 중 하나일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c727a-109">Can be one of the following:</span></span>  
  
-   [<span data-ttu-id="c727a-110">공용</span><span class="sxs-lookup"><span data-stu-id="c727a-110">Public</span></span>](../../../visual-basic/language-reference/modifiers/public.md)  
  
-   [<span data-ttu-id="c727a-111">Friend</span><span class="sxs-lookup"><span data-stu-id="c727a-111">Friend</span></span>](../../../visual-basic/language-reference/modifiers/friend.md)  
  
 <span data-ttu-id="c727a-112">참조 [액세스 수준을 Visual Basic의](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="c727a-112">See [Access levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span></span>  
  
 `name`  
 <span data-ttu-id="c727a-113">필수.</span><span class="sxs-lookup"><span data-stu-id="c727a-113">Required.</span></span> <span data-ttu-id="c727a-114">이 모듈의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="c727a-114">Name of this module.</span></span> <span data-ttu-id="c727a-115">참조 [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="c727a-115">See [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).</span></span>  
  
 `statements`  
 <span data-ttu-id="c727a-116">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="c727a-116">Optional.</span></span> <span data-ttu-id="c727a-117">변수, 속성, 이벤트, 프로시저 및이 모듈의 중첩 된 형식을 정의 하는 문입니다.</span><span class="sxs-lookup"><span data-stu-id="c727a-117">Statements which define the variables, properties, events, procedures, and nested types of this module.</span></span>  
  
 `End Module`  
 <span data-ttu-id="c727a-118">종료는 `Module` 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="c727a-118">Terminates the `Module` definition.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c727a-119">설명</span><span class="sxs-lookup"><span data-stu-id="c727a-119">Remarks</span></span>  
 <span data-ttu-id="c727a-120">`Module` 문은 해당 네임 스페이스에서 사용 가능한 참조 형식을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="c727a-120">A `Module` statement defines a reference type available throughout its namespace.</span></span> <span data-ttu-id="c727a-121">*모듈* (라고도 *표준 모듈*) 유사 하지만 몇 가지 중요 한 차이가 클래스.</span><span class="sxs-lookup"><span data-stu-id="c727a-121">A *module* (sometimes called a *standard module*)is similar to a class but with some important distinctions.</span></span> <span data-ttu-id="c727a-122">모든 모듈 인스턴스가 하나만 있고 생성 또는 변수에 할당할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c727a-122">Every module has exactly one instance and does not need to be created or assigned to a variable.</span></span> <span data-ttu-id="c727a-123">모듈 상속을 지원 하지 않거나 인터페이스를 구현 합니다.</span><span class="sxs-lookup"><span data-stu-id="c727a-123">Modules do not support inheritance or implement interfaces.</span></span> <span data-ttu-id="c727a-124">모듈이 *형식* 클래스 또는 구조체는 점에서-모듈의 데이터 형식이 프로그래밍 요소를 선언할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c727a-124">Notice that a module is not a *type* in the sense that a class or structure is — you cannot declare a programming element to have the data type of a module.</span></span>  
  
 <span data-ttu-id="c727a-125">사용할 수 있습니다 `Module` 네임 스페이스 수준 에서만.</span><span class="sxs-lookup"><span data-stu-id="c727a-125">You can use `Module` only at namespace level.</span></span> <span data-ttu-id="c727a-126">즉, 합니다 *선언 컨텍스트* 모듈을 소스 파일이 나 네임 스페이스에 있어야 하 고 클래스, 구조체, 모듈, 인터페이스, 프로시저 또는 블록 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c727a-126">This means the *declaration context* for a module must be a source file or namespace, and cannot be a class, structure, module, interface, procedure, or block.</span></span> <span data-ttu-id="c727a-127">모든 형식 또는 다른 모듈에서 모듈을 중첩할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c727a-127">You cannot nest a module within another module, or within any type.</span></span> <span data-ttu-id="c727a-128">자세한 내용은 [선언 컨텍스트 및 기본 액세스 수준](../../../visual-basic/language-reference/statements/declaration-contexts-and-default-access-levels.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c727a-128">For more information, see [Declaration Contexts and Default Access Levels](../../../visual-basic/language-reference/statements/declaration-contexts-and-default-access-levels.md).</span></span>  
  
 <span data-ttu-id="c727a-129">모듈에 프로그램 수명과 동일 합니다.</span><span class="sxs-lookup"><span data-stu-id="c727a-129">A module has the same lifetime as your program.</span></span> <span data-ttu-id="c727a-130">멤버는 모든 `Shared`와 같은 프로그램의 수명 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c727a-130">Because its members are all `Shared`, they also have lifetimes equal to that of the program.</span></span>  
  
 <span data-ttu-id="c727a-131">모듈은 기본적으로 [Friend](../../../visual-basic/language-reference/modifiers/friend.md) 액세스 합니다.</span><span class="sxs-lookup"><span data-stu-id="c727a-131">Modules default to [Friend](../../../visual-basic/language-reference/modifiers/friend.md) access.</span></span> <span data-ttu-id="c727a-132">액세스 한정자를 사용 하 여 해당 액세스 수준을 조정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c727a-132">You can adjust their access levels with the access modifiers.</span></span> <span data-ttu-id="c727a-133">자세한 내용은 [액세스 수준을 Visual Basic의](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="c727a-133">For more information, see [Access levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span></span>  
  
 <span data-ttu-id="c727a-134">모듈의 모든 멤버는 암시적 `Shared`합니다.</span><span class="sxs-lookup"><span data-stu-id="c727a-134">All members of a module are implicitly `Shared`.</span></span>  
  
## <a name="classes-and-modules"></a><span data-ttu-id="c727a-135">클래스와 모듈</span><span class="sxs-lookup"><span data-stu-id="c727a-135">Classes and Modules</span></span>  
 <span data-ttu-id="c727a-136">이러한 요소는 비슷한 점이 많이 몇 가지 중요 한 차이점도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c727a-136">These elements have many similarities, but there are some important differences as well.</span></span>  
  
-   <span data-ttu-id="c727a-137">**용어입니다.**</span><span class="sxs-lookup"><span data-stu-id="c727a-137">**Terminology.**</span></span> <span data-ttu-id="c727a-138">이전 버전의 Visual Basic 등 두 유형의 모듈로 인식: *클래스 모듈* (.cls 파일) 및 *표준 모듈* (.bas 파일).</span><span class="sxs-lookup"><span data-stu-id="c727a-138">Previous versions of Visual Basic recognize two types of modules: *class modules* (.cls files) and *standard modules* (.bas files).</span></span> <span data-ttu-id="c727a-139">현재 버전에서는 이러한 *클래스* 하 고 *모듈*, 각각.</span><span class="sxs-lookup"><span data-stu-id="c727a-139">The current version calls these *classes* and *modules*, respectively.</span></span>  
  
-   <span data-ttu-id="c727a-140">**공유 멤버입니다.**</span><span class="sxs-lookup"><span data-stu-id="c727a-140">**Shared Members.**</span></span> <span data-ttu-id="c727a-141">공유 클래스의 멤버 인지 또는 인스턴스 멤버를 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c727a-141">You can control whether a member of a class is a shared or instance member.</span></span>  
  
-   <span data-ttu-id="c727a-142">**개체 방향입니다.**</span><span class="sxs-lookup"><span data-stu-id="c727a-142">**Object Orientation.**</span></span> <span data-ttu-id="c727a-143">클래스는 개체 지향 되지만 모듈이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c727a-143">Classes are object-oriented, but modules are not.</span></span> <span data-ttu-id="c727a-144">따라서 클래스는 개체로 인스턴스화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c727a-144">So only classes can be instantiated as objects.</span></span> <span data-ttu-id="c727a-145">자세한 내용은 [개체 및 클래스](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="c727a-145">For more information, see [Objects and Classes](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md).</span></span>  
  
## <a name="rules"></a><span data-ttu-id="c727a-146">규칙</span><span class="sxs-lookup"><span data-stu-id="c727a-146">Rules</span></span>  
  
-   <span data-ttu-id="c727a-147">**한정자입니다.**</span><span class="sxs-lookup"><span data-stu-id="c727a-147">**Modifiers.**</span></span> <span data-ttu-id="c727a-148">모든 모듈 멤버는 암시적 [공유](../../../visual-basic/language-reference/modifiers/shared.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="c727a-148">All module members are implicitly [Shared](../../../visual-basic/language-reference/modifiers/shared.md).</span></span> <span data-ttu-id="c727a-149">사용할 수 없습니다는 `Shared` 키워드가 모든 멤버의 공유 상태를 변경할 수 없습니다는 멤버를 선언 하는 경우.</span><span class="sxs-lookup"><span data-stu-id="c727a-149">You cannot use the `Shared` keyword when declaring a member, and you cannot alter the shared status of any member.</span></span>  
  
-   <span data-ttu-id="c727a-150">**상속.**</span><span class="sxs-lookup"><span data-stu-id="c727a-150">**Inheritance.**</span></span> <span data-ttu-id="c727a-151">이외의 다른 모든 형식에서 상속할 수 없습니다. 모듈 <xref:System.Object>, 모든 모듈에서 상속 합니다.</span><span class="sxs-lookup"><span data-stu-id="c727a-151">A module cannot inherit from any type other than <xref:System.Object>, from which all modules inherit.</span></span> <span data-ttu-id="c727a-152">특히 하나의 모듈에서 다른 상속할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c727a-152">In particular, one module cannot inherit from another.</span></span>  
  
     <span data-ttu-id="c727a-153">사용할 수 없습니다는 [Inherits Statement](../../../visual-basic/language-reference/statements/inherits-statement.md) 지정 하는 데도 모듈 정의 <xref:System.Object>합니다.</span><span class="sxs-lookup"><span data-stu-id="c727a-153">You cannot use the [Inherits Statement](../../../visual-basic/language-reference/statements/inherits-statement.md) in a module definition, even to specify <xref:System.Object>.</span></span>  
  
-   <span data-ttu-id="c727a-154">**기본 속성입니다.**</span><span class="sxs-lookup"><span data-stu-id="c727a-154">**Default Property.**</span></span> <span data-ttu-id="c727a-155">모듈의 기본 속성을 정의할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c727a-155">You cannot define any default properties in a module.</span></span> <span data-ttu-id="c727a-156">자세한 내용은 [기본](../../../visual-basic/language-reference/modifiers/default.md)입니다.</span><span class="sxs-lookup"><span data-stu-id="c727a-156">For more information, see [Default](../../../visual-basic/language-reference/modifiers/default.md).</span></span>  
  
## <a name="behavior"></a><span data-ttu-id="c727a-157">동작</span><span class="sxs-lookup"><span data-stu-id="c727a-157">Behavior</span></span>  
  
-   <span data-ttu-id="c727a-158">**액세스 수준입니다.**</span><span class="sxs-lookup"><span data-stu-id="c727a-158">**Access Level.**</span></span> <span data-ttu-id="c727a-159">모듈 내에서 자신의 액세스 수준 가진 각 멤버를 선언할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c727a-159">Within a module, you can declare each member with its own access level.</span></span> <span data-ttu-id="c727a-160">모듈 멤버를 기본값으로 [공개](../../../visual-basic/language-reference/modifiers/public.md) 변수와 상수를 제외 하 고는 기본적으로 액세스 [개인](../../../visual-basic/language-reference/modifiers/private.md) 액세스 합니다.</span><span class="sxs-lookup"><span data-stu-id="c727a-160">Module members default to [Public](../../../visual-basic/language-reference/modifiers/public.md) access, except variables and constants, which default to [Private](../../../visual-basic/language-reference/modifiers/private.md) access.</span></span> <span data-ttu-id="c727a-161">모듈에 보다 제한적인 해당 멤버 중 하나를 지정 된 모듈 액세스 수준을 우선적으로 적용 합니다.</span><span class="sxs-lookup"><span data-stu-id="c727a-161">When a module has more restricted access than one of its members, the specified module access level takes precedence.</span></span>  
  
-   <span data-ttu-id="c727a-162">**범위입니다.**</span><span class="sxs-lookup"><span data-stu-id="c727a-162">**Scope.**</span></span> <span data-ttu-id="c727a-163">모듈은 해당 네임 스페이스 범위에서.</span><span class="sxs-lookup"><span data-stu-id="c727a-163">A module is in scope throughout its namespace.</span></span>  
  
     <span data-ttu-id="c727a-164">모든 모듈 멤버의 범위는 전체 모듈입니다.</span><span class="sxs-lookup"><span data-stu-id="c727a-164">The scope of every module member is the entire module.</span></span> <span data-ttu-id="c727a-165">표시 되는 모든 멤버가 *형식 승격*, 모듈을 포함 하는 네임 스페이스를 승격할 해당 범위에 이르게 합니다.</span><span class="sxs-lookup"><span data-stu-id="c727a-165">Notice that all members undergo *type promotion*, which causes their scope to be promoted to the namespace containing the module.</span></span> <span data-ttu-id="c727a-166">자세한 내용은 [형식 승격](../../../visual-basic/programming-guide/language-features/declared-elements/type-promotion.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="c727a-166">For more information, see [Type Promotion](../../../visual-basic/programming-guide/language-features/declared-elements/type-promotion.md).</span></span>  
  
-   <span data-ttu-id="c727a-167">**정규화 합니다.**</span><span class="sxs-lookup"><span data-stu-id="c727a-167">**Qualification.**</span></span> <span data-ttu-id="c727a-168">프로젝트에서 여러 모듈을 할 수 있습니다 하 고 둘 이상의 모듈에서 동일한 이름 가진 멤버를 선언할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c727a-168">You can have multiple modules in a project, and you can declare members with the same name in two or more modules.</span></span> <span data-ttu-id="c727a-169">그러나 모듈 외부에서 참조 되는 경우 적절 한 모듈 이름으로 이러한 멤버에 대 한 모든 참조를 정규화 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c727a-169">However, you must qualify any reference to such a member with the appropriate module name if the reference is from outside that module.</span></span> <span data-ttu-id="c727a-170">자세한 내용은 [References to Declared Elements](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="c727a-170">For more information, see [References to Declared Elements](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="c727a-171">예제</span><span class="sxs-lookup"><span data-stu-id="c727a-171">Example</span></span>  
 [!code-vb[VbVbalrStatements#69](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/module-statement_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="c727a-172">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c727a-172">See Also</span></span>  
 [<span data-ttu-id="c727a-173">Class 문</span><span class="sxs-lookup"><span data-stu-id="c727a-173">Class Statement</span></span>](../../../visual-basic/language-reference/statements/class-statement.md)  
 [<span data-ttu-id="c727a-174">Namespace 문</span><span class="sxs-lookup"><span data-stu-id="c727a-174">Namespace Statement</span></span>](../../../visual-basic/language-reference/statements/namespace-statement.md)  
 [<span data-ttu-id="c727a-175">Structure 문</span><span class="sxs-lookup"><span data-stu-id="c727a-175">Structure Statement</span></span>](../../../visual-basic/language-reference/statements/structure-statement.md)  
 [<span data-ttu-id="c727a-176">Interface 문</span><span class="sxs-lookup"><span data-stu-id="c727a-176">Interface Statement</span></span>](../../../visual-basic/language-reference/statements/interface-statement.md)  
 [<span data-ttu-id="c727a-177">Property 문</span><span class="sxs-lookup"><span data-stu-id="c727a-177">Property Statement</span></span>](../../../visual-basic/language-reference/statements/property-statement.md)  
 [<span data-ttu-id="c727a-178">형식 승격</span><span class="sxs-lookup"><span data-stu-id="c727a-178">Type Promotion</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/type-promotion.md)
