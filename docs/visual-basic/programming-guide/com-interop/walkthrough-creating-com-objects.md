---
title: '연습: Visual Basic을 사용 하 여 COM 개체 만들기'
ms.date: 07/20/2015
helpviewer_keywords:
- COM interop [Visual Basic], creating COM objects
- COM objects, creating
- COM interop [Visual Basic], walkthroughs
- object creation [Visual Basic], COM objects
- COM objects, walkthroughs
ms.assetid: 7b07a463-bc72-4392-9ba0-9dfcb697a44f
ms.openlocfilehash: 6b079db3ccc07494bdfdf7dba49c27fe14dca4e5
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/28/2019
ms.locfileid: "56973940"
---
# <a name="walkthrough-creating-com-objects-with-visual-basic"></a><span data-ttu-id="e3fba-102">연습: Visual Basic을 사용 하 여 COM 개체 만들기</span><span class="sxs-lookup"><span data-stu-id="e3fba-102">Walkthrough: Creating COM Objects with Visual Basic</span></span>
<span data-ttu-id="e3fba-103">새 응용 프로그램 또는 구성 요소를 만들 때.NET Framework 어셈블리를 만드는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="e3fba-103">When creating new applications or components, it is best to create .NET Framework assemblies.</span></span> <span data-ttu-id="e3fba-104">그러나 Visual Basic도 쉽게 COM에.NET Framework 구성 요소 노출</span><span class="sxs-lookup"><span data-stu-id="e3fba-104">However, Visual Basic also makes it easy to expose a .NET Framework component to COM.</span></span> <span data-ttu-id="e3fba-105">이 옵션을 사용 하면 COM 구성 요소를 필요로 하는 이전 응용 프로그램 도구 모음에 대 한 새 구성 요소를 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e3fba-105">This enables you to provide new components for earlier application suites that require COM components.</span></span> <span data-ttu-id="e3fba-106">이 연습에는 Visual Basic 노출을 사용 하는 방법을 보여 줍니다. [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] COM 개체를 사용 하 여 및 COM 클래스 템플릿을 사용 하지 않고 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="e3fba-106">This walkthrough demonstrates how to use Visual Basic to expose [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] objects as COM objects, both with and without the COM class template.</span></span>  
  
 <span data-ttu-id="e3fba-107">COM 클래스 템플릿을 사용 하 여 COM 개체를 노출 하는 가장 쉬운 방법은 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e3fba-107">The easiest way to expose COM objects is by using the COM class template.</span></span> <span data-ttu-id="e3fba-108">COM 클래스 템플릿을 새 클래스를 만들고 COM 개체로 클래스 및 상호 운용성 계층을 생성 하 고 운영 체제를 사용 하 여 등록 하려면 프로젝트를 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="e3fba-108">The COM class template creates a new class, and then configures your project to generate the class and interoperability layer as a COM object and register it with the operating system.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e3fba-109">Visual Basic에서 사용 하 여 비관리 코드를 COM 개체로 만든 클래스를 노출할 수도 있습니다, 있지만 실제 COM 개체 아니며 Visual Basic에서 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e3fba-109">Although you can also expose a class created in Visual Basic as a COM object for unmanaged code to use, it is not a true COM object and cannot be used by Visual Basic.</span></span> <span data-ttu-id="e3fba-110">자세한 내용은 [.NET Framework 응용 프로그램의 COM 상호 운용성](../../../visual-basic/programming-guide/com-interop/com-interoperability-in-net-framework-applications.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="e3fba-110">For more information, see [COM Interoperability in .NET Framework Applications](../../../visual-basic/programming-guide/com-interop/com-interoperability-in-net-framework-applications.md).</span></span>  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
### <a name="to-create-a-com-object-by-using-the-com-class-template"></a><span data-ttu-id="e3fba-111">COM 클래스 템플릿을 사용 하 여 COM 개체를 만들려면</span><span class="sxs-lookup"><span data-stu-id="e3fba-111">To create a COM object by using the COM class template</span></span>  
  
1.  <span data-ttu-id="e3fba-112">새 Windows 응용 프로그램 프로젝트를 엽니다는 **파일** 를 클릭 하 여 메뉴 **새 프로젝트**합니다.</span><span class="sxs-lookup"><span data-stu-id="e3fba-112">Open a new Windows Application project from the **File** menu by clicking **New Project**.</span></span>  
  
2.  <span data-ttu-id="e3fba-113">에 **새 프로젝트** 대화 상자의 합니다 **프로젝트 형식** 필드에 Windows가 선택 되었는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="e3fba-113">In the **New Project** dialog box under the **Project Types** field, check that Windows is selected.</span></span> <span data-ttu-id="e3fba-114">선택 **클래스 라이브러리** 에서 합니다 **템플릿** 목록을 연 다음 클릭 **확인**합니다.</span><span class="sxs-lookup"><span data-stu-id="e3fba-114">Select **Class Library** from the **Templates** list, and then click **OK**.</span></span> <span data-ttu-id="e3fba-115">새 프로젝트가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e3fba-115">The new project is displayed.</span></span>  
  
3.  <span data-ttu-id="e3fba-116">선택 **새 항목 추가** 에서 합니다 **프로젝트** 메뉴.</span><span class="sxs-lookup"><span data-stu-id="e3fba-116">Select **Add New Item** from the **Project** menu.</span></span> <span data-ttu-id="e3fba-117">**새 항목 추가** 대화 상자가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="e3fba-117">The **Add New Item** dialog box is displayed.</span></span>  
  
4.  <span data-ttu-id="e3fba-118">선택 **COM 클래스** 에서 합니다 **템플릿** 목록을 연 다음 클릭 **추가**합니다.</span><span class="sxs-lookup"><span data-stu-id="e3fba-118">Select **COM Class** from the **Templates** list, and then click **Add**.</span></span> <span data-ttu-id="e3fba-119">Visual Basic 새 클래스를 추가 하 고 COM interop에 대 한 새 프로젝트를 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="e3fba-119">Visual Basic adds a new class and configures the new project for COM interop.</span></span>  
  
5.  <span data-ttu-id="e3fba-120">COM 클래스 속성, 메서드 및 이벤트와 같은 코드를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="e3fba-120">Add code such as properties, methods, and events to the COM class.</span></span>  
  
6.  <span data-ttu-id="e3fba-121">선택 **빌드 ClassLibrary1** 에서 합니다 **빌드** 메뉴.</span><span class="sxs-lookup"><span data-stu-id="e3fba-121">Select **Build ClassLibrary1** from the **Build** menu.</span></span> <span data-ttu-id="e3fba-122">Visual Basic 어셈블리를 빌드하고 운영 체제를 사용 하 여 COM 개체를 등록 합니다.</span><span class="sxs-lookup"><span data-stu-id="e3fba-122">Visual Basic builds the assembly and registers the COM object with the operating system.</span></span>  
  
## <a name="creating-com-objects-without-the-com-class-template"></a><span data-ttu-id="e3fba-123">COM 클래스 템플릿 사용 하지 않고 COM 개체 만들기</span><span class="sxs-lookup"><span data-stu-id="e3fba-123">Creating COM Objects without the COM Class Template</span></span>  
 <span data-ttu-id="e3fba-124">또한 COM 클래스 템플릿을 사용 하는 대신 수동으로 COM 클래스를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e3fba-124">You can also create a COM class manually instead of using the COM class template.</span></span> <span data-ttu-id="e3fba-125">이 절차는 명령줄에서 작업할 때 또는 COM 개체를 정의 하는 방법을 더 제어 하려는 경우 유용 합니다.</span><span class="sxs-lookup"><span data-stu-id="e3fba-125">This procedure is helpful when you are working from the command line or when you want more control over how COM objects are defined.</span></span>  
  
#### <a name="to-set-up-your-project-to-generate-a-com-object"></a><span data-ttu-id="e3fba-126">COM 개체를 생성 하도록 프로젝트를 설정 하려면</span><span class="sxs-lookup"><span data-stu-id="e3fba-126">To set up your project to generate a COM object</span></span>  
  
1.  <span data-ttu-id="e3fba-127">새 Windows 응용 프로그램 프로젝트를 엽니다는 **파일** 를 클릭 하 여 메뉴 **NewProject**합니다.</span><span class="sxs-lookup"><span data-stu-id="e3fba-127">Open a new Windows Application project from the **File** menu by clicking **NewProject**.</span></span>  
  
2.  <span data-ttu-id="e3fba-128">에 **새 프로젝트** 대화 상자의 합니다 **프로젝트 형식** 필드에 Windows가 선택 되었는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="e3fba-128">In the **New Project** dialog box under the **Project Types** field, check that Windows is selected.</span></span> <span data-ttu-id="e3fba-129">선택 **클래스 라이브러리** 에서 합니다 **템플릿** 목록을 연 다음 클릭 **확인**합니다.</span><span class="sxs-lookup"><span data-stu-id="e3fba-129">Select **Class Library** from the **Templates** list, and then click **OK**.</span></span> <span data-ttu-id="e3fba-130">새 프로젝트가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e3fba-130">The new project is displayed.</span></span>  
  
3.  <span data-ttu-id="e3fba-131">**솔루션 탐색기**에서 프로젝트를 오른쪽 마우스 단추로 클릭하고 **속성**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="e3fba-131">In **Solution Explorer**, right-click your project, and then click **Properties**.</span></span> <span data-ttu-id="e3fba-132">합니다 **프로젝트 디자이너** 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e3fba-132">The **Project Designer** is displayed.</span></span>  
  
4.  <span data-ttu-id="e3fba-133">**컴파일** 탭을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="e3fba-133">Click the **Compile** tab.</span></span>  
  
5.  <span data-ttu-id="e3fba-134">선택 된 **COM Interop 등록** 확인란 합니다.</span><span class="sxs-lookup"><span data-stu-id="e3fba-134">Select the **Register for COM Interop** check box.</span></span>  
  
#### <a name="to-set-up-the-code-in-your-class-to-create-a-com-object"></a><span data-ttu-id="e3fba-135">COM 개체를 만드는 클래스의 코드를 설정 하려면</span><span class="sxs-lookup"><span data-stu-id="e3fba-135">To set up the code in your class to create a COM object</span></span>  
  
1.  <span data-ttu-id="e3fba-136">**솔루션 탐색기**를 두 번 클릭 **Class1.vb** 해당 코드를 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="e3fba-136">In **Solution Explorer**, double-click **Class1.vb** to display its code.</span></span>  
  
2.  <span data-ttu-id="e3fba-137">클래스 이름을 `ComClass1`로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="e3fba-137">Rename the class to `ComClass1`.</span></span>  
  
3.  <span data-ttu-id="e3fba-138">다음 상수를 추가 `ComClass1`합니다.</span><span class="sxs-lookup"><span data-stu-id="e3fba-138">Add the following constants to `ComClass1`.</span></span> <span data-ttu-id="e3fba-139">전역적으로 고유 식별자 (GUID) 상수 COM 개체가 있어야 하는 저장 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e3fba-139">They will store the Globally Unique Identifier (GUID) constants that the COM objects are required to have.</span></span>  
  
     [!code-vb[VbVbalrInterop#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrInterop/VB/Class1.vb#2)]  
  
4.  <span data-ttu-id="e3fba-140">**도구** 메뉴에서 **GUID 만들기**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="e3fba-140">On the **Tools** menu, click **Create Guid**.</span></span> <span data-ttu-id="e3fba-141">**GUID 만들기** 대화 상자에서 **레지스트리 형식**과 **복사**를 차례로 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="e3fba-141">In the **Create GUID** dialog box, click **Registry Format** and then click **Copy**.</span></span> <span data-ttu-id="e3fba-142">**끝내기**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="e3fba-142">Click **Exit**.</span></span>  
  
5.  <span data-ttu-id="e3fba-143">빈 문자열을 대체 합니다 `ClassId` GUID를 사용 하 여 제거 하는 선행 및 후행 중괄호입니다.</span><span class="sxs-lookup"><span data-stu-id="e3fba-143">Replace the empty string for the `ClassId` with the GUID, removing the leading and trailing braces.</span></span> <span data-ttu-id="e3fba-144">예를 들어 GUID는 Guidgen을 제공한 경우 `"{2C8B0AEE-02C9-486e-B809-C780A11530FE}"` 다음 코드는 다음과 같이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e3fba-144">For example, if the GUID provided by Guidgen is `"{2C8B0AEE-02C9-486e-B809-C780A11530FE}"` then your code should appear as follows.</span></span>  
  
     [!code-vb[VbVbalrInterop#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrInterop/VB/Class1.vb#3)]  
  
6.  <span data-ttu-id="e3fba-145">에 대 한 이전 단계를 반복 합니다 `InterfaceId` 및 `EventsId` 다음 예제와 같이 상수입니다.</span><span class="sxs-lookup"><span data-stu-id="e3fba-145">Repeat the previous steps for the `InterfaceId` and `EventsId` constants, as in the following example.</span></span>  
  
     [!code-vb[VbVbalrInterop#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrInterop/VB/Class1.vb#4)]  
  
    > [!NOTE]
    >  <span data-ttu-id="e3fba-146">Guid는 새롭고 고유한; 되는지 확인 그렇지 않으면 COM 구성 요소는 다른 COM 구성 요소와 충돌할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e3fba-146">Make sure that the GUIDs are new and unique; otherwise, your COM component could conflict with other COM components.</span></span>  
  
7.  <span data-ttu-id="e3fba-147">추가 합니다 `ComClass` 특성을 `ComClass1`, 다음 예제와 같이 클래스 ID, 인터페이스 ID 및 이벤트 ID에 대 한 Guid를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="e3fba-147">Add the `ComClass` attribute to `ComClass1`, specifying the GUIDs for the Class ID, Interface ID, and Events ID as in the following example:</span></span>  
  
     [!code-vb[VbVbalrInterop#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrInterop/VB/Class1.vb#5)]  
  
8.  <span data-ttu-id="e3fba-148">COM 클래스에 매개 변수가 없는 있어야 `Public Sub New()` 생성자 또는 클래스는 제대로 등록 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e3fba-148">COM classes must have a parameterless `Public Sub New()` constructor, or the class will not register correctly.</span></span> <span data-ttu-id="e3fba-149">클래스에는 매개 변수가 없는 생성자를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="e3fba-149">Add a parameterless constructor to the class:</span></span>  
  
     [!code-vb[VbVbalrInterop#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrInterop/VB/Class1.vb#6)]  
  
9. <span data-ttu-id="e3fba-150">속성, 메서드 및 이벤트 클래스를 추가, 사용 하 여 종료를 `End Class` 문입니다.</span><span class="sxs-lookup"><span data-stu-id="e3fba-150">Add properties, methods, and events to the class, ending it with an `End Class` statement.</span></span> <span data-ttu-id="e3fba-151">선택 **솔루션 빌드** 에서 합니다 **빌드** 메뉴.</span><span class="sxs-lookup"><span data-stu-id="e3fba-151">Select **Build Solution** from the **Build** menu.</span></span> <span data-ttu-id="e3fba-152">Visual Basic 어셈블리를 빌드하고 운영 체제를 사용 하 여 COM 개체를 등록 합니다.</span><span class="sxs-lookup"><span data-stu-id="e3fba-152">Visual Basic builds the assembly and registers the COM object with the operating system.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="e3fba-153">True 이면 COM 개체 하지 않기 때문에 다른 Visual Basic 응용 프로그램에서 Visual Basic을 사용 하 여 생성 하는 COM 개체를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e3fba-153">The COM objects you generate with Visual Basic cannot be used by other Visual Basic applications because they are not true COM objects.</span></span> <span data-ttu-id="e3fba-154">이러한 COM 개체에 대 한 참조를 추가 하려는 시도 오류가 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="e3fba-154">Attempts to add references to such COM objects will raise an error.</span></span> <span data-ttu-id="e3fba-155">자세한 내용은 참조 하세요 [.NET Framework 응용 프로그램의 COM 상호 운용성](../../../visual-basic/programming-guide/com-interop/com-interoperability-in-net-framework-applications.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="e3fba-155">For details, see [COM Interoperability in .NET Framework Applications](../../../visual-basic/programming-guide/com-interop/com-interoperability-in-net-framework-applications.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e3fba-156">참고자료</span><span class="sxs-lookup"><span data-stu-id="e3fba-156">See also</span></span>
- <xref:Microsoft.VisualBasic.ComClassAttribute>
- [<span data-ttu-id="e3fba-157">COM Interop</span><span class="sxs-lookup"><span data-stu-id="e3fba-157">COM Interop</span></span>](../../../visual-basic/programming-guide/com-interop/index.md)
- [<span data-ttu-id="e3fba-158">연습: COM 개체를 사용한 상속 구현</span><span class="sxs-lookup"><span data-stu-id="e3fba-158">Walkthrough: Implementing Inheritance with COM Objects</span></span>](../../../visual-basic/programming-guide/com-interop/walkthrough-implementing-inheritance-with-com-objects.md)
- [<span data-ttu-id="e3fba-159">#Region 지시문</span><span class="sxs-lookup"><span data-stu-id="e3fba-159">#Region Directive</span></span>](../../../visual-basic/language-reference/directives/region-directive.md)
- [<span data-ttu-id="e3fba-160">.NET Framework 응용 프로그램의 COM 상호 운용성</span><span class="sxs-lookup"><span data-stu-id="e3fba-160">COM Interoperability in .NET Framework Applications</span></span>](../../../visual-basic/programming-guide/com-interop/com-interoperability-in-net-framework-applications.md)
- [<span data-ttu-id="e3fba-161">상호 운용성 문제 해결</span><span class="sxs-lookup"><span data-stu-id="e3fba-161">Troubleshooting Interoperability</span></span>](../../../visual-basic/programming-guide/com-interop/troubleshooting-interoperability.md)
