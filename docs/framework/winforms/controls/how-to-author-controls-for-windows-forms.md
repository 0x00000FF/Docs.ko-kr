---
title: '방법: Windows Forms 컨트롤 작성'
ms.date: 03/30/2017
helpviewer_keywords:
- controls [Windows Forms], creating
- UserControl class [Windows Forms], Windows Forms
- custom controls [Windows Forms], creating
ms.assetid: 7570e982-545b-4c3a-a7c7-55581d313400
ms.openlocfilehash: 0804b9824b84a32bdd79c763031a3de4ffa54099
ms.sourcegitcommit: cf9515122fce716bcfb6618ba366e39b5a2eb81e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/15/2019
ms.locfileid: "69039884"
---
# <a name="how-to-author-controls-for-windows-forms"></a><span data-ttu-id="b119f-102">방법: Windows Forms 컨트롤 작성</span><span class="sxs-lookup"><span data-stu-id="b119f-102">How to: Author Controls for Windows Forms</span></span>

<span data-ttu-id="b119f-103">컨트롤은 사용자와 프로그램 간의 그래픽 링크를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="b119f-103">A control represents a graphical link between the user and the program.</span></span> <span data-ttu-id="b119f-104">컨트롤은 데이터를 제공하거나 처리하고, 사용자 입력을 허용하고, 사용자 및 애플리케이션을 연결하는 다른 함수의 구성원을 합니다.</span><span class="sxs-lookup"><span data-stu-id="b119f-104">A control can provide or process data, accept user input, respond to events, or perform any number of other functions that connect the user and the application.</span></span> <span data-ttu-id="b119f-105">컨트롤이 기본적으로 그래픽 인터페이스를 사용하는 구성 요소이기 때문에 사용자 상호 작용을 제공할 뿐만 아니라 구성 요소가 수행하는 모든 함수를 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b119f-105">Because a control is essentially a component with a graphical interface, it can serve any function that a component does, as well as provide user interaction.</span></span> <span data-ttu-id="b119f-106">컨트롤은 특정 목적을 수행하기 위해 만들어지며 컨트롤 작성은 다른 프로그래밍 작업입니다.</span><span class="sxs-lookup"><span data-stu-id="b119f-106">Controls are created to serve specific purposes, and authoring controls is just another programming task.</span></span> <span data-ttu-id="b119f-107">이 점을 염두하면서 다음 단계는 컨트롤 작성 프로세스의 개요를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="b119f-107">With that in mind, the following steps represent an overview of the control authoring process.</span></span> <span data-ttu-id="b119f-108">링크는 각 단계에 대한 추가 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="b119f-108">Links provide additional information on the individual steps.</span></span>

> [!NOTE]
> <span data-ttu-id="b119f-109">Web Forms에서 사용할 사용자 지정 컨트롤을 작성하려는 경우 [사용자 지정 ASP.NET 서버 컨트롤 개발](https://docs.microsoft.com/previous-versions/aspnet/zt27tfhy(v=vs.100))을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b119f-109">If you want to author a custom control to use on Web Forms, see [Developing Custom ASP.NET Server Controls](https://docs.microsoft.com/previous-versions/aspnet/zt27tfhy(v=vs.100)).</span></span>

## <a name="to-author-a-control"></a><span data-ttu-id="b119f-110">컨트롤을 작성하려면</span><span class="sxs-lookup"><span data-stu-id="b119f-110">To author a control</span></span>

1. <span data-ttu-id="b119f-111">컨트롤이 수행하려는 항목 또는 애플리케이션에서 컨트롤이 맡은 역할을 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="b119f-111">Determine what you want your control to accomplish, or what part it will play in your application.</span></span> <span data-ttu-id="b119f-112">고려해야 하는 요인은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="b119f-112">Factors to consider are:</span></span>

    - <span data-ttu-id="b119f-113">어떤 종류의 그래픽 인터페이스가 필요한가요?</span><span class="sxs-lookup"><span data-stu-id="b119f-113">What kind of graphical interface do you need?</span></span>

    - <span data-ttu-id="b119f-114">이 컨트롤이 다룰 특정 사용자 인터페이스는 무엇인가요?</span><span class="sxs-lookup"><span data-stu-id="b119f-114">What specific user interactions will this control handle?</span></span>

    - <span data-ttu-id="b119f-115">기존 컨트롤에서 필요한 기능을 제공하나요?</span><span class="sxs-lookup"><span data-stu-id="b119f-115">Is the functionality you need provided by any existing controls?</span></span>

    - <span data-ttu-id="b119f-116">여러 Windows Forms 컨트롤을 결합하여 필요한 기능을 얻을 수 있나요?</span><span class="sxs-lookup"><span data-stu-id="b119f-116">Can you get the functionality you need by combining several Windows Forms controls?</span></span>

2. <span data-ttu-id="b119f-117">컨트롤에 대한 개체 모델이 필요한 경우 개체 모델 전체에 기능을 분산할 방법을 결정하고 컨트롤과 하위 개체 간의 기능을 분리합니다.</span><span class="sxs-lookup"><span data-stu-id="b119f-117">If you need an object model for your control, determine how functionality will be distributed throughout the object model, and divide up functionality between the control and any subobjects.</span></span> <span data-ttu-id="b119f-118">개체 모델은 복잡한 컨트롤 계획하거나 여러 기능을 통합하려는 경우에 유용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b119f-118">An object model may be useful if you are planning a complex control, or want to incorporate several functionalities.</span></span>

3. <span data-ttu-id="b119f-119">필요한 컨트롤의 형식을 확인합니다(예: 사용자 정의 컨트롤, 사용자 지정 컨트롤, 상속된 Windows Forms 컨트롤).</span><span class="sxs-lookup"><span data-stu-id="b119f-119">Determine the type of control (for example, user control, custom control, inherited Windows Forms control) you need.</span></span> <span data-ttu-id="b119f-120">자세한 내용은 [컨트롤 형식 권장 사항](control-type-recommendations.md) 및 [사용자 지정 컨트롤의 종류](varieties-of-custom-controls.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b119f-120">For details, see [Control Type Recommendations](control-type-recommendations.md) and [Varieties of Custom Controls](varieties-of-custom-controls.md).</span></span>

4. <span data-ttu-id="b119f-121">기능을 컨트롤의 속성, 메서드 및 이벤트 및 해당 하위 개체 또는 보조 구조로 나타내고 적절한 액세스 수준(예: 공용, 보호 등)을 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="b119f-121">Express functionality as properties, methods, and events of the control and its subobjects or subsidiary structures, and assign appropriate access levels (for example, public, protected, and so on).</span></span>

5. <span data-ttu-id="b119f-122">컨트롤에 사용자 지정 그리기가 필요한 경우 코드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="b119f-122">If you need custom painting for your control, add code for it.</span></span> <span data-ttu-id="b119f-123">자세한 내용은 [사용자 지정 컨트롤 그리기 및 렌더링](custom-control-painting-and-rendering.md)을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="b119f-123">For details, see [Custom Control Painting and Rendering](custom-control-painting-and-rendering.md).</span></span>

6. <span data-ttu-id="b119f-124">컨트롤이에서 <xref:System.Windows.Forms.UserControl>상속 하는 경우 컨트롤 프로젝트를 빌드하고 **UserControl 테스트 컨테이너**에서 실행 하 여 런타임 동작을 테스트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b119f-124">If your control inherits from <xref:System.Windows.Forms.UserControl>, you can test its runtime behavior by building the control project and running it in the **UserControl Test Container**.</span></span> <span data-ttu-id="b119f-125">자세한 내용은 [방법: UserControl](how-to-test-the-run-time-behavior-of-a-usercontrol.md)의 런타임 동작을 테스트 합니다.</span><span class="sxs-lookup"><span data-stu-id="b119f-125">For more information, see [How to: Test the Run-Time Behavior of a UserControl](how-to-test-the-run-time-behavior-of-a-usercontrol.md).</span></span>

7. <span data-ttu-id="b119f-126">또한 Windows 애플리케이션과 같이 새 프로젝트를 만들고 컨테이너에 배치하여 컨트롤을 테스트하고 디버그할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b119f-126">You can also test and debug your control by creating a new project, such as a Windows Application, and placing it into a container.</span></span> <span data-ttu-id="b119f-127">이 프로세스는 [연습의 일부로 보여 줍니다. Visual Basic](walkthrough-authoring-a-composite-control-with-visual-basic.md)를 사용 하 여 복합 컨트롤 작성</span><span class="sxs-lookup"><span data-stu-id="b119f-127">This process is demonstrated as part of [Walkthrough: Authoring a Composite Control with Visual Basic](walkthrough-authoring-a-composite-control-with-visual-basic.md).</span></span>

8. <span data-ttu-id="b119f-128">각 기능을 추가하면 기능을 테스트 프로젝트에 추가하여 새 기능을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="b119f-128">As you add each feature, add features to your test project to exercise the new functionality.</span></span>

9. <span data-ttu-id="b119f-129">반복하여 디자인을 구체화합니다.</span><span class="sxs-lookup"><span data-stu-id="b119f-129">Repeat, refining the design.</span></span>

10. <span data-ttu-id="b119f-130">컨트롤을 패키지하고 배포합니다.</span><span class="sxs-lookup"><span data-stu-id="b119f-130">Package and deploy your control.</span></span> <span data-ttu-id="b119f-131">자세한 내용은 [Visual Studio에서 배포 살펴보기](/visualstudio/deployment/deploying-applications-services-and-components)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="b119f-131">For details, see [First look at deployment in Visual Studio](/visualstudio/deployment/deploying-applications-services-and-components).</span></span>

## <a name="see-also"></a><span data-ttu-id="b119f-132">참고자료</span><span class="sxs-lookup"><span data-stu-id="b119f-132">See also</span></span>

- [<span data-ttu-id="b119f-133">연습: Visual Basic를 사용 하 여 복합 컨트롤 작성</span><span class="sxs-lookup"><span data-stu-id="b119f-133">Walkthrough: Authoring a Composite Control with Visual Basic</span></span>](walkthrough-authoring-a-composite-control-with-visual-basic.md)
- [<span data-ttu-id="b119f-134">연습: Visual Basic를 사용 하 여 Windows Forms 컨트롤에서 상속</span><span class="sxs-lookup"><span data-stu-id="b119f-134">Walkthrough: Inheriting from a Windows Forms Control with Visual Basic</span></span>](walkthrough-inheriting-from-a-windows-forms-control-with-visual-basic.md)
- [<span data-ttu-id="b119f-135">방법: UserControl 클래스에서 상속</span><span class="sxs-lookup"><span data-stu-id="b119f-135">How to: Inherit from the UserControl Class</span></span>](how-to-inherit-from-the-usercontrol-class.md)
- [<span data-ttu-id="b119f-136">방법: Control 클래스에서 상속</span><span class="sxs-lookup"><span data-stu-id="b119f-136">How to: Inherit from the Control Class</span></span>](how-to-inherit-from-the-control-class.md)
- [<span data-ttu-id="b119f-137">방법: 기존 Windows Forms 컨트롤에서 상속</span><span class="sxs-lookup"><span data-stu-id="b119f-137">How to: Inherit from Existing Windows Forms Controls</span></span>](how-to-inherit-from-existing-windows-forms-controls.md)
- [<span data-ttu-id="b119f-138">방법: UserControl의 런타임 동작 테스트</span><span class="sxs-lookup"><span data-stu-id="b119f-138">How to: Test the Run-Time Behavior of a UserControl</span></span>](how-to-test-the-run-time-behavior-of-a-usercontrol.md)
- [<span data-ttu-id="b119f-139">사용자 지정 컨트롤의 종류</span><span class="sxs-lookup"><span data-stu-id="b119f-139">Varieties of Custom Controls</span></span>](varieties-of-custom-controls.md)
