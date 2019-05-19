---
title: '연습: 내게 필요한 옵션이 지원되는 Windows 기반 애플리케이션 만들기'
ms.date: 03/30/2017
helpviewer_keywords:
- accessibility [Windows Forms], Windows applications
- Windows applications [Windows Forms], accessibility
- applications [Windows Forms], accessibility
ms.assetid: 654c7f2f-1586-480b-9f12-9d9b8f5cc32b
ms.openlocfilehash: 7dec86c724479fde78fcb2e2881dce40b1bf747a
ms.sourcegitcommit: c4e9d05644c9cb89de5ce6002723de107ea2e2c4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/19/2019
ms.locfileid: "65877110"
---
# <a name="walkthrough-creating-an-accessible-windows-based-application"></a><span data-ttu-id="7c537-102">연습: 내게 필요한 옵션이 지원되는 Windows 기반 애플리케이션 만들기</span><span class="sxs-lookup"><span data-stu-id="7c537-102">Walkthrough: Creating an Accessible Windows-based Application</span></span>

<span data-ttu-id="7c537-103">액세스할 수 있는 애플리케이션을 만드는 것은 비즈니스에 중요한 영향을 줍니다.</span><span class="sxs-lookup"><span data-stu-id="7c537-103">Creating an accessible application has important business implications.</span></span> <span data-ttu-id="7c537-104">많은 정부 기관에는 소프트웨어 구매와 관련된 접근성 규정이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7c537-104">Many governments have accessibility regulations for software purchase.</span></span> <span data-ttu-id="7c537-105">Certified for Windows 로고에는 접근성 요구 사항이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="7c537-105">The Certified for Windows logo includes accessibility requirements.</span></span> <span data-ttu-id="7c537-106">미국에만 3천만 명이 거주하는 것으로 추정되는 잠재 고객 중 많은 사람이 소프트웨어의 내게 필요한 옵션 기능에 따른 영향을 받습니다.</span><span class="sxs-lookup"><span data-stu-id="7c537-106">An estimated 30 million residents of the U.S. alone, many of them potential customers, are affected by the accessibility of software.</span></span>

<span data-ttu-id="7c537-107">이 연습에서는 Certified for Windows 로고를 위한 5가지 접근성 요구 사항을 다룹니다.</span><span class="sxs-lookup"><span data-stu-id="7c537-107">This walkthrough will address the five accessibility requirements for the Certified for Windows logo.</span></span> <span data-ttu-id="7c537-108">이러한 요구 사항에 따라 액세스할 수 있는 애플리케이션은 다음을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="7c537-108">According to these requirements, an accessible application will:</span></span>

- <span data-ttu-id="7c537-109">제어판 크기, 색, 글꼴 및 입력 설정을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="7c537-109">Support Control Panel size, color, font, and input settings.</span></span> <span data-ttu-id="7c537-110">사용자가 제어판 설정을 변경하면 메뉴 모음, 제목 표시줄, 테두리 및 상태 표시줄의 크기가 자동으로 모두 조정됩니다.</span><span class="sxs-lookup"><span data-stu-id="7c537-110">The menu bar, title bar, borders, and status bar will all resize themselves when the user changes the control panel settings.</span></span> <span data-ttu-id="7c537-111">이 애플리케이션에서 컨트롤 또는 코드를 추가로 변경할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="7c537-111">No additional changes to the controls or code are required in this application.</span></span>

- <span data-ttu-id="7c537-112">고대비 모드를 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="7c537-112">Support High Contrast mode.</span></span>

- <span data-ttu-id="7c537-113">모든 기능에 대한 문서화된 키보드 액세스를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="7c537-113">Provide documented keyboard access to all features.</span></span>

- <span data-ttu-id="7c537-114">키보드 포커스의 위치를 시각적으로 및 프로그래밍 방식으로 노출합니다.</span><span class="sxs-lookup"><span data-stu-id="7c537-114">Expose location of the keyboard focus visually and programmatically.</span></span>

- <span data-ttu-id="7c537-115">중요한 정보를 소리로만 전달하지 마세요.</span><span class="sxs-lookup"><span data-stu-id="7c537-115">Avoid conveying important information by sound alone.</span></span>

<span data-ttu-id="7c537-116">자세한 내용은 [내게 필요한 옵션을 제공하는 애플리케이션 설계를 위한 리소스](/visualstudio/ide/reference/resources-for-designing-accessible-applications)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="7c537-116">For more information, see [Resources for Designing Accessible Applications](/visualstudio/ide/reference/resources-for-designing-accessible-applications).</span></span>

<span data-ttu-id="7c537-117">다양한 자판 배열을 지원하는 방법에 대한 자세한 내용은 [지역화 대비 애플리케이션 개발을 위한 최선의 구현 방법](../../../standard/globalization-localization/best-practices-for-developing-world-ready-apps.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="7c537-117">For information on supporting varying keyboard layouts, see [Best Practices for Developing World-Ready Applications](../../../standard/globalization-localization/best-practices-for-developing-world-ready-apps.md).</span></span>

## <a name="creating-the-project"></a><span data-ttu-id="7c537-118">프로젝트 만들기</span><span class="sxs-lookup"><span data-stu-id="7c537-118">Creating the Project</span></span>

<span data-ttu-id="7c537-119">이 연습에서는 피자 주문을 받는 애플리케이션용 사용자 인터페이스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="7c537-119">This walkthrough creates the user interface for an application that takes pizza orders.</span></span> <span data-ttu-id="7c537-120">고객 이름을 나타내는 <xref:System.Windows.Forms.TextBox>, 피자 크기를 선택하기 위한 <xref:System.Windows.Forms.RadioButton> 그룹, 토핑을 선택하기 위한 <xref:System.Windows.Forms.CheckedListBox>, Order 및 Cancel 레이블이 붙은 단추 컨트롤 2개 및 Exit 명령이 포함된 메뉴로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="7c537-120">It consists of a <xref:System.Windows.Forms.TextBox> for the customer's name, a <xref:System.Windows.Forms.RadioButton> group to select the pizza size, a <xref:System.Windows.Forms.CheckedListBox> for selecting the toppings, two Button controls labeled Order and Cancel, and a Menu with an Exit command.</span></span>

<span data-ttu-id="7c537-121">사용자가 고객 이름, 피자 크기 및 원하는 토핑을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="7c537-121">The user enters the customer's name, the size of the pizza, and the toppings desired.</span></span> <span data-ttu-id="7c537-122">사용자가 Order 단추를 클릭하면 주문 요약과 비용이 메시지 상자에 표시되며 컨트롤이 선택 취소되고 다음 주문을 준비합니다.</span><span class="sxs-lookup"><span data-stu-id="7c537-122">When the user clicks the Order button, a summary of the order and its cost are displayed in a message box and the controls are cleared and ready for the next order.</span></span> <span data-ttu-id="7c537-123">사용자가 Cancel 단추를 클릭하면 컨트롤이 선택 취소되고 다음 주문을 준비합니다.</span><span class="sxs-lookup"><span data-stu-id="7c537-123">When the user clicks the Cancel button, the controls are cleared and ready for the next order.</span></span> <span data-ttu-id="7c537-124">사용자가 Exit 메뉴 항목을 클릭하면 프로그램이 닫힙니다.</span><span class="sxs-lookup"><span data-stu-id="7c537-124">When the user clicks the Exit menu item, the program closes.</span></span>

<span data-ttu-id="7c537-125">이 연습은 소매 주문 시스템의 코드가 아니라 사용자 인터페이스의 접근성을 강조합니다.</span><span class="sxs-lookup"><span data-stu-id="7c537-125">The emphasis of this walkthrough is not the code for a retail order system, but the accessibility of the user interface.</span></span> <span data-ttu-id="7c537-126">이 연습에서는 단추, 라디오 단추, 텍스트 상자 및 레이블을 포함하여 자주 사용하는 여러 컨트롤의 접근성 기능을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="7c537-126">The walkthrough demonstrates the accessibility features of several frequently used controls, including buttons, radio buttons, text boxes, and labels.</span></span>

#### <a name="to-begin-making-the-application"></a><span data-ttu-id="7c537-127">애플리케이션 만들기를 시작하려면</span><span class="sxs-lookup"><span data-stu-id="7c537-127">To begin making the application</span></span>

- <span data-ttu-id="7c537-128">Visual Basic 또는 시각적 개체에서 새 Windows 응용 프로그램 만들기 C#입니다.</span><span class="sxs-lookup"><span data-stu-id="7c537-128">Create a new Windows Application in Visual Basic or Visual C#.</span></span> <span data-ttu-id="7c537-129">프로젝트 이름을 **PizzaOrder**로 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="7c537-129">Name the project **PizzaOrder**.</span></span> <span data-ttu-id="7c537-130">자세한 내용은 [새 솔루션 및 프로젝트 만들기](/visualstudio/ide/creating-solutions-and-projects)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="7c537-130">(For details see [Creating New Solutions and Projects](/visualstudio/ide/creating-solutions-and-projects).)</span></span>

## <a name="adding-the-controls-to-the-form"></a><span data-ttu-id="7c537-131">폼에 컨트롤 추가</span><span class="sxs-lookup"><span data-stu-id="7c537-131">Adding the Controls to the Form</span></span>

<span data-ttu-id="7c537-132">폼에 컨트롤을 추가하는 경우 액세스할 수 있는 애플리케이션을 만들기 위한 다음 지침을 고려하세요.</span><span class="sxs-lookup"><span data-stu-id="7c537-132">When adding the controls to a form, keep in mind the following guidelines to make an accessible application:</span></span>

- <span data-ttu-id="7c537-133"><xref:System.Windows.Forms.Control.AccessibleDescription%2A> 및 <xref:System.Windows.Forms.Control.AccessibleName%2A> 속성을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="7c537-133">Set the <xref:System.Windows.Forms.Control.AccessibleDescription%2A> and <xref:System.Windows.Forms.Control.AccessibleName%2A> properties.</span></span> <span data-ttu-id="7c537-134">이 예제에서는 <xref:System.Windows.Forms.Control.AccessibleRole%2A>에 대한 기본 설정만으로도 충분합니다.</span><span class="sxs-lookup"><span data-stu-id="7c537-134">In this example, the Default setting for the <xref:System.Windows.Forms.Control.AccessibleRole%2A> is sufficient.</span></span> <span data-ttu-id="7c537-135">내게 필요한 옵션 속성에 대한 자세한 내용은 [Windows Form의 컨트롤에 내게 필요한 옵션 정보 제공](../controls/providing-accessibility-information-for-controls-on-a-windows-form.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="7c537-135">For more information on the accessibility properties, see [Providing Accessibility Information for Controls on a Windows Form](../controls/providing-accessibility-information-for-controls-on-a-windows-form.md).</span></span>

- <span data-ttu-id="7c537-136">글꼴 크기를 10포인트 이상으로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="7c537-136">Set the font size to 10 points or larger.</span></span>

  > [!NOTE]
  > <span data-ttu-id="7c537-137">시작할 때 폼의 글꼴 크기를 10으로 설정하면 이후에 폼에 추가된 모든 컨트롤도 글꼴 크기가 10입니다.</span><span class="sxs-lookup"><span data-stu-id="7c537-137">If you set the font size of the form to 10 when you start, then all controls subsequently added to the form will have a font size of 10.</span></span>

- <span data-ttu-id="7c537-138">TextBox 컨트롤을 설명하는 Label 컨트롤은 탭 순서에서 TextBox 컨트롤 바로 앞에 와야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7c537-138">Make sure any Label control that describes a TextBox control immediately precedes the TextBox control in the tab order.</span></span>

- <span data-ttu-id="7c537-139">사용자가 탐색할 수 있는 모든 컨트롤의 <xref:System.Windows.Forms.Control.Text%2A> 속성에 "&" 문자를 사용하여 액세스 키를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="7c537-139">Add an access key, using the "&" character, to the <xref:System.Windows.Forms.Control.Text%2A> property of any control the user may want to navigate to.</span></span>

- <span data-ttu-id="7c537-140">사용자가 탐색할 수 있는 컨트롤 앞에 오는 레이블의 <xref:System.Windows.Forms.Control.Text%2A> 속성에 "&" 문자를 사용하여 액세스 키를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="7c537-140">Add an access key, using the "&" character, to the <xref:System.Windows.Forms.Control.Text%2A> property of the label that precedes a control that the user may want to navigate to.</span></span> <span data-ttu-id="7c537-141">사용자가 액세스 키를 누를 때 포커스가 탭 순서의 다음 컨트롤로 설정되도록 레이블의 <xref:System.Windows.Forms.Label.UseMnemonic%2A> 속성을 `true`로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="7c537-141">Set the labels' <xref:System.Windows.Forms.Label.UseMnemonic%2A> property to `true`, so that the focus is set to the next control in the tab order when the user presses the access key.</span></span>

- <span data-ttu-id="7c537-142">모든 메뉴 항목에 액세스 키를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="7c537-142">Add access keys to all menu items.</span></span>

#### <a name="to-make-your-windows-application-accessible"></a><span data-ttu-id="7c537-143">Windows 애플리케이션을 액세스할 수 있게 하려면</span><span class="sxs-lookup"><span data-stu-id="7c537-143">To make your Windows Application accessible</span></span>

- <span data-ttu-id="7c537-144">폼에 컨트롤을 추가하고 아래에 설명된 대로 속성을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="7c537-144">Add the controls to the form and set the properties as described below.</span></span> <span data-ttu-id="7c537-145">폼에 컨트롤을 정렬하는 방법에 대한 모델은 표 끝에 있는 그림을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="7c537-145">See the picture at the end of the table for a model of how to arrange the controls on the form.</span></span>

   |<span data-ttu-id="7c537-146">개체</span><span class="sxs-lookup"><span data-stu-id="7c537-146">Object</span></span>|<span data-ttu-id="7c537-147">속성</span><span class="sxs-lookup"><span data-stu-id="7c537-147">Property</span></span>|<span data-ttu-id="7c537-148">값</span><span class="sxs-lookup"><span data-stu-id="7c537-148">Value</span></span>|
   |------------|--------------|-----------|
   |<span data-ttu-id="7c537-149">Form1</span><span class="sxs-lookup"><span data-stu-id="7c537-149">Form1</span></span>|<span data-ttu-id="7c537-150">AccessibleDescription</span><span class="sxs-lookup"><span data-stu-id="7c537-150">AccessibleDescription</span></span>|<span data-ttu-id="7c537-151">Order form</span><span class="sxs-lookup"><span data-stu-id="7c537-151">Order form</span></span>|
   ||<span data-ttu-id="7c537-152">AccessibleName</span><span class="sxs-lookup"><span data-stu-id="7c537-152">AccessibleName</span></span>|<span data-ttu-id="7c537-153">Order form</span><span class="sxs-lookup"><span data-stu-id="7c537-153">Order form</span></span>|
   ||<span data-ttu-id="7c537-154">글꼴 크기</span><span class="sxs-lookup"><span data-stu-id="7c537-154">Font Size</span></span>|<span data-ttu-id="7c537-155">10</span><span class="sxs-lookup"><span data-stu-id="7c537-155">10</span></span>|
   ||<span data-ttu-id="7c537-156">텍스트</span><span class="sxs-lookup"><span data-stu-id="7c537-156">Text</span></span>|<span data-ttu-id="7c537-157">Pizza Order Form</span><span class="sxs-lookup"><span data-stu-id="7c537-157">Pizza Order Form</span></span>|
   |<span data-ttu-id="7c537-158">PictureBox</span><span class="sxs-lookup"><span data-stu-id="7c537-158">PictureBox</span></span>|<span data-ttu-id="7c537-159">이름</span><span class="sxs-lookup"><span data-stu-id="7c537-159">Name</span></span>|<span data-ttu-id="7c537-160">로고</span><span class="sxs-lookup"><span data-stu-id="7c537-160">logo</span></span>|
   ||<span data-ttu-id="7c537-161">AccessibleDescription</span><span class="sxs-lookup"><span data-stu-id="7c537-161">AccessibleDescription</span></span>|<span data-ttu-id="7c537-162">A slice of pizza</span><span class="sxs-lookup"><span data-stu-id="7c537-162">A slice of pizza</span></span>|
   ||<span data-ttu-id="7c537-163">AccessibleName</span><span class="sxs-lookup"><span data-stu-id="7c537-163">AccessibleName</span></span>|<span data-ttu-id="7c537-164">Company logo</span><span class="sxs-lookup"><span data-stu-id="7c537-164">Company logo</span></span>|
   ||<span data-ttu-id="7c537-165">이미지</span><span class="sxs-lookup"><span data-stu-id="7c537-165">Image</span></span>|<span data-ttu-id="7c537-166">임의 아이콘 또는 비트맵</span><span class="sxs-lookup"><span data-stu-id="7c537-166">Any icon or bitmap</span></span>|
   |<span data-ttu-id="7c537-167">레이블</span><span class="sxs-lookup"><span data-stu-id="7c537-167">Label</span></span>|<span data-ttu-id="7c537-168">이름</span><span class="sxs-lookup"><span data-stu-id="7c537-168">Name</span></span>|<span data-ttu-id="7c537-169">companyLabel</span><span class="sxs-lookup"><span data-stu-id="7c537-169">companyLabel</span></span>|
   ||<span data-ttu-id="7c537-170">텍스트</span><span class="sxs-lookup"><span data-stu-id="7c537-170">Text</span></span>|<span data-ttu-id="7c537-171">Good Pizza</span><span class="sxs-lookup"><span data-stu-id="7c537-171">Good Pizza</span></span>|
   ||<span data-ttu-id="7c537-172">TabIndex</span><span class="sxs-lookup"><span data-stu-id="7c537-172">TabIndex</span></span>|<span data-ttu-id="7c537-173">1</span><span class="sxs-lookup"><span data-stu-id="7c537-173">1</span></span>|
   ||<span data-ttu-id="7c537-174">AccessibleDescription</span><span class="sxs-lookup"><span data-stu-id="7c537-174">AccessibleDescription</span></span>|<span data-ttu-id="7c537-175">Company name</span><span class="sxs-lookup"><span data-stu-id="7c537-175">Company name</span></span>|
   ||<span data-ttu-id="7c537-176">AccessibleName</span><span class="sxs-lookup"><span data-stu-id="7c537-176">AccessibleName</span></span>|<span data-ttu-id="7c537-177">Company name</span><span class="sxs-lookup"><span data-stu-id="7c537-177">Company name</span></span>|
   ||<span data-ttu-id="7c537-178">Backcolor</span><span class="sxs-lookup"><span data-stu-id="7c537-178">Backcolor</span></span>|<span data-ttu-id="7c537-179">파랑</span><span class="sxs-lookup"><span data-stu-id="7c537-179">Blue</span></span>|
   ||<span data-ttu-id="7c537-180">Forecolor</span><span class="sxs-lookup"><span data-stu-id="7c537-180">Forecolor</span></span>|<span data-ttu-id="7c537-181">노랑</span><span class="sxs-lookup"><span data-stu-id="7c537-181">Yellow</span></span>|
   ||<span data-ttu-id="7c537-182">글꼴 크기</span><span class="sxs-lookup"><span data-stu-id="7c537-182">Font size</span></span>|<span data-ttu-id="7c537-183">18</span><span class="sxs-lookup"><span data-stu-id="7c537-183">18</span></span>|
   |<span data-ttu-id="7c537-184">레이블</span><span class="sxs-lookup"><span data-stu-id="7c537-184">Label</span></span>|<span data-ttu-id="7c537-185">이름</span><span class="sxs-lookup"><span data-stu-id="7c537-185">Name</span></span>|<span data-ttu-id="7c537-186">customerLabel</span><span class="sxs-lookup"><span data-stu-id="7c537-186">customerLabel</span></span>|
   ||<span data-ttu-id="7c537-187">텍스트</span><span class="sxs-lookup"><span data-stu-id="7c537-187">Text</span></span>|<span data-ttu-id="7c537-188">이름(&N)</span><span class="sxs-lookup"><span data-stu-id="7c537-188">&Name</span></span>|
   ||<span data-ttu-id="7c537-189">TabIndex</span><span class="sxs-lookup"><span data-stu-id="7c537-189">TabIndex</span></span>|<span data-ttu-id="7c537-190">2</span><span class="sxs-lookup"><span data-stu-id="7c537-190">2</span></span>|
   ||<span data-ttu-id="7c537-191">AccessibleDescription</span><span class="sxs-lookup"><span data-stu-id="7c537-191">AccessibleDescription</span></span>|<span data-ttu-id="7c537-192">Customer name label</span><span class="sxs-lookup"><span data-stu-id="7c537-192">Customer name label</span></span>|
   ||<span data-ttu-id="7c537-193">AccessibleName</span><span class="sxs-lookup"><span data-stu-id="7c537-193">AccessibleName</span></span>|<span data-ttu-id="7c537-194">Customer name label</span><span class="sxs-lookup"><span data-stu-id="7c537-194">Customer name label</span></span>|
   ||<span data-ttu-id="7c537-195">UseMnemonic</span><span class="sxs-lookup"><span data-stu-id="7c537-195">UseMnemonic</span></span>|<span data-ttu-id="7c537-196">True</span><span class="sxs-lookup"><span data-stu-id="7c537-196">True</span></span>|
   |<span data-ttu-id="7c537-197">TextBox</span><span class="sxs-lookup"><span data-stu-id="7c537-197">TextBox</span></span>|<span data-ttu-id="7c537-198">이름</span><span class="sxs-lookup"><span data-stu-id="7c537-198">Name</span></span>|<span data-ttu-id="7c537-199">customerName</span><span class="sxs-lookup"><span data-stu-id="7c537-199">customerName</span></span>|
   ||<span data-ttu-id="7c537-200">텍스트</span><span class="sxs-lookup"><span data-stu-id="7c537-200">Text</span></span>|<span data-ttu-id="7c537-201">(없음)</span><span class="sxs-lookup"><span data-stu-id="7c537-201">(none)</span></span>|
   ||<span data-ttu-id="7c537-202">TabIndex</span><span class="sxs-lookup"><span data-stu-id="7c537-202">TabIndex</span></span>|<span data-ttu-id="7c537-203">3</span><span class="sxs-lookup"><span data-stu-id="7c537-203">3</span></span>|
   ||<span data-ttu-id="7c537-204">AccessibleDescription</span><span class="sxs-lookup"><span data-stu-id="7c537-204">AccessibleDescription</span></span>|<span data-ttu-id="7c537-205">Customer name</span><span class="sxs-lookup"><span data-stu-id="7c537-205">Customer name</span></span>|
   ||<span data-ttu-id="7c537-206">AccessibleName</span><span class="sxs-lookup"><span data-stu-id="7c537-206">AccessibleName</span></span>|<span data-ttu-id="7c537-207">Customer name</span><span class="sxs-lookup"><span data-stu-id="7c537-207">Customer name</span></span>|
   |<span data-ttu-id="7c537-208">GroupBox</span><span class="sxs-lookup"><span data-stu-id="7c537-208">GroupBox</span></span>|<span data-ttu-id="7c537-209">이름</span><span class="sxs-lookup"><span data-stu-id="7c537-209">Name</span></span>|<span data-ttu-id="7c537-210">sizeOptions</span><span class="sxs-lookup"><span data-stu-id="7c537-210">sizeOptions</span></span>|
   ||<span data-ttu-id="7c537-211">AccessibleDescription</span><span class="sxs-lookup"><span data-stu-id="7c537-211">AccessibleDescription</span></span>|<span data-ttu-id="7c537-212">Pizza size options</span><span class="sxs-lookup"><span data-stu-id="7c537-212">Pizza size options</span></span>|
   ||<span data-ttu-id="7c537-213">AccessibleName</span><span class="sxs-lookup"><span data-stu-id="7c537-213">AccessibleName</span></span>|<span data-ttu-id="7c537-214">Pizza size options</span><span class="sxs-lookup"><span data-stu-id="7c537-214">Pizza size options</span></span>|
   ||<span data-ttu-id="7c537-215">텍스트</span><span class="sxs-lookup"><span data-stu-id="7c537-215">Text</span></span>|<span data-ttu-id="7c537-216">Pizza size</span><span class="sxs-lookup"><span data-stu-id="7c537-216">Pizza size</span></span>|
   ||<span data-ttu-id="7c537-217">TabIndex</span><span class="sxs-lookup"><span data-stu-id="7c537-217">TabIndex</span></span>|<span data-ttu-id="7c537-218">4</span><span class="sxs-lookup"><span data-stu-id="7c537-218">4</span></span>|
   |<span data-ttu-id="7c537-219">RadioButton</span><span class="sxs-lookup"><span data-stu-id="7c537-219">RadioButton</span></span>|<span data-ttu-id="7c537-220">이름</span><span class="sxs-lookup"><span data-stu-id="7c537-220">Name</span></span>|<span data-ttu-id="7c537-221">smallPizza</span><span class="sxs-lookup"><span data-stu-id="7c537-221">smallPizza</span></span>|
   ||<span data-ttu-id="7c537-222">텍스트</span><span class="sxs-lookup"><span data-stu-id="7c537-222">Text</span></span>|<span data-ttu-id="7c537-223">&Small $6.00</span><span class="sxs-lookup"><span data-stu-id="7c537-223">&Small $6.00</span></span>|
   ||<span data-ttu-id="7c537-224">선택한 상태</span><span class="sxs-lookup"><span data-stu-id="7c537-224">Checked</span></span>|<span data-ttu-id="7c537-225">True</span><span class="sxs-lookup"><span data-stu-id="7c537-225">True</span></span>|
   ||<span data-ttu-id="7c537-226">TabIndex</span><span class="sxs-lookup"><span data-stu-id="7c537-226">TabIndex</span></span>|<span data-ttu-id="7c537-227">0</span><span class="sxs-lookup"><span data-stu-id="7c537-227">0</span></span>|
   ||<span data-ttu-id="7c537-228">AccessibleDescription</span><span class="sxs-lookup"><span data-stu-id="7c537-228">AccessibleDescription</span></span>|<span data-ttu-id="7c537-229">Small pizza</span><span class="sxs-lookup"><span data-stu-id="7c537-229">Small pizza</span></span>|
   ||<span data-ttu-id="7c537-230">AccessibleName</span><span class="sxs-lookup"><span data-stu-id="7c537-230">AccessibleName</span></span>|<span data-ttu-id="7c537-231">Small pizza</span><span class="sxs-lookup"><span data-stu-id="7c537-231">Small pizza</span></span>|
   |<span data-ttu-id="7c537-232">RadioButton</span><span class="sxs-lookup"><span data-stu-id="7c537-232">RadioButton</span></span>|<span data-ttu-id="7c537-233">이름</span><span class="sxs-lookup"><span data-stu-id="7c537-233">Name</span></span>|<span data-ttu-id="7c537-234">largePizza</span><span class="sxs-lookup"><span data-stu-id="7c537-234">largePizza</span></span>|
   ||<span data-ttu-id="7c537-235">텍스트</span><span class="sxs-lookup"><span data-stu-id="7c537-235">Text</span></span>|<span data-ttu-id="7c537-236">&Large $10.00</span><span class="sxs-lookup"><span data-stu-id="7c537-236">&Large $10.00</span></span>|
   ||<span data-ttu-id="7c537-237">TabIndex</span><span class="sxs-lookup"><span data-stu-id="7c537-237">TabIndex</span></span>|<span data-ttu-id="7c537-238">1</span><span class="sxs-lookup"><span data-stu-id="7c537-238">1</span></span>|
   ||<span data-ttu-id="7c537-239">AccessibleDescription</span><span class="sxs-lookup"><span data-stu-id="7c537-239">AccessibleDescription</span></span>|<span data-ttu-id="7c537-240">Large pizza</span><span class="sxs-lookup"><span data-stu-id="7c537-240">Large pizza</span></span>|
   ||<span data-ttu-id="7c537-241">AccessibleName</span><span class="sxs-lookup"><span data-stu-id="7c537-241">AccessibleName</span></span>|<span data-ttu-id="7c537-242">Large pizza</span><span class="sxs-lookup"><span data-stu-id="7c537-242">Large pizza</span></span>|
   |<span data-ttu-id="7c537-243">레이블</span><span class="sxs-lookup"><span data-stu-id="7c537-243">Label</span></span>|<span data-ttu-id="7c537-244">이름</span><span class="sxs-lookup"><span data-stu-id="7c537-244">Name</span></span>|<span data-ttu-id="7c537-245">toppingsLabel</span><span class="sxs-lookup"><span data-stu-id="7c537-245">toppingsLabel</span></span>|
   ||<span data-ttu-id="7c537-246">텍스트</span><span class="sxs-lookup"><span data-stu-id="7c537-246">Text</span></span>|<span data-ttu-id="7c537-247">&Toppings ($0.75 each)</span><span class="sxs-lookup"><span data-stu-id="7c537-247">&Toppings ($0.75 each)</span></span>|
   ||<span data-ttu-id="7c537-248">TabIndex</span><span class="sxs-lookup"><span data-stu-id="7c537-248">TabIndex</span></span>|<span data-ttu-id="7c537-249">5</span><span class="sxs-lookup"><span data-stu-id="7c537-249">5</span></span>|
   ||<span data-ttu-id="7c537-250">AccessibleDescription</span><span class="sxs-lookup"><span data-stu-id="7c537-250">AccessibleDescription</span></span>|<span data-ttu-id="7c537-251">Toppings label</span><span class="sxs-lookup"><span data-stu-id="7c537-251">Toppings label</span></span>|
   ||<span data-ttu-id="7c537-252">AccessibleName</span><span class="sxs-lookup"><span data-stu-id="7c537-252">AccessibleName</span></span>|<span data-ttu-id="7c537-253">Toppings label</span><span class="sxs-lookup"><span data-stu-id="7c537-253">Toppings label</span></span>|
   ||<span data-ttu-id="7c537-254">UseMnemonic</span><span class="sxs-lookup"><span data-stu-id="7c537-254">UseMnemonic</span></span>|<span data-ttu-id="7c537-255">True</span><span class="sxs-lookup"><span data-stu-id="7c537-255">True</span></span>|
   |<span data-ttu-id="7c537-256">CheckedListBox</span><span class="sxs-lookup"><span data-stu-id="7c537-256">CheckedListBox</span></span>|<span data-ttu-id="7c537-257">이름</span><span class="sxs-lookup"><span data-stu-id="7c537-257">Name</span></span>|<span data-ttu-id="7c537-258">toppings</span><span class="sxs-lookup"><span data-stu-id="7c537-258">toppings</span></span>|
   ||<span data-ttu-id="7c537-259">TabIndex</span><span class="sxs-lookup"><span data-stu-id="7c537-259">TabIndex</span></span>|<span data-ttu-id="7c537-260">6</span><span class="sxs-lookup"><span data-stu-id="7c537-260">6</span></span>|
   ||<span data-ttu-id="7c537-261">AccessibleDescription</span><span class="sxs-lookup"><span data-stu-id="7c537-261">AccessibleDescription</span></span>|<span data-ttu-id="7c537-262">Available toppings</span><span class="sxs-lookup"><span data-stu-id="7c537-262">Available toppings</span></span>|
   ||<span data-ttu-id="7c537-263">AccessibleName</span><span class="sxs-lookup"><span data-stu-id="7c537-263">AccessibleName</span></span>|<span data-ttu-id="7c537-264">Available toppings</span><span class="sxs-lookup"><span data-stu-id="7c537-264">Available toppings</span></span>|
   ||<span data-ttu-id="7c537-265">항목</span><span class="sxs-lookup"><span data-stu-id="7c537-265">Items</span></span>|<span data-ttu-id="7c537-266">Pepperoni, Sausage, Mushrooms</span><span class="sxs-lookup"><span data-stu-id="7c537-266">Pepperoni, Sausage, Mushrooms</span></span>|
   |<span data-ttu-id="7c537-267">단추</span><span class="sxs-lookup"><span data-stu-id="7c537-267">Button</span></span>|<span data-ttu-id="7c537-268">이름</span><span class="sxs-lookup"><span data-stu-id="7c537-268">Name</span></span>|<span data-ttu-id="7c537-269">순서</span><span class="sxs-lookup"><span data-stu-id="7c537-269">order</span></span>|
   ||<span data-ttu-id="7c537-270">텍스트</span><span class="sxs-lookup"><span data-stu-id="7c537-270">Text</span></span>|<span data-ttu-id="7c537-271">순서(&O)</span><span class="sxs-lookup"><span data-stu-id="7c537-271">&Order</span></span>|
   ||<span data-ttu-id="7c537-272">TabIndex</span><span class="sxs-lookup"><span data-stu-id="7c537-272">TabIndex</span></span>|<span data-ttu-id="7c537-273">7</span><span class="sxs-lookup"><span data-stu-id="7c537-273">7</span></span>|
   ||<span data-ttu-id="7c537-274">AccessibleDescription</span><span class="sxs-lookup"><span data-stu-id="7c537-274">AccessibleDescription</span></span>|<span data-ttu-id="7c537-275">Total the order</span><span class="sxs-lookup"><span data-stu-id="7c537-275">Total the order</span></span>|
   ||<span data-ttu-id="7c537-276">AccessibleName</span><span class="sxs-lookup"><span data-stu-id="7c537-276">AccessibleName</span></span>|<span data-ttu-id="7c537-277">Total order</span><span class="sxs-lookup"><span data-stu-id="7c537-277">Total order</span></span>|
   |<span data-ttu-id="7c537-278">단추</span><span class="sxs-lookup"><span data-stu-id="7c537-278">Button</span></span>|<span data-ttu-id="7c537-279">이름</span><span class="sxs-lookup"><span data-stu-id="7c537-279">Name</span></span>|<span data-ttu-id="7c537-280">cancel</span><span class="sxs-lookup"><span data-stu-id="7c537-280">cancel</span></span>|
   ||<span data-ttu-id="7c537-281">텍스트</span><span class="sxs-lookup"><span data-stu-id="7c537-281">Text</span></span>|<span data-ttu-id="7c537-282">취소(&C)</span><span class="sxs-lookup"><span data-stu-id="7c537-282">&Cancel</span></span>|
   ||<span data-ttu-id="7c537-283">TabIndex</span><span class="sxs-lookup"><span data-stu-id="7c537-283">TabIndex</span></span>|<span data-ttu-id="7c537-284">9</span><span class="sxs-lookup"><span data-stu-id="7c537-284">8</span></span>|
   ||<span data-ttu-id="7c537-285">AccessibleDescription</span><span class="sxs-lookup"><span data-stu-id="7c537-285">AccessibleDescription</span></span>|<span data-ttu-id="7c537-286">Cancel the order</span><span class="sxs-lookup"><span data-stu-id="7c537-286">Cancel the order</span></span>|
   ||<span data-ttu-id="7c537-287">AccessibleName</span><span class="sxs-lookup"><span data-stu-id="7c537-287">AccessibleName</span></span>|<span data-ttu-id="7c537-288">Cancel order</span><span class="sxs-lookup"><span data-stu-id="7c537-288">Cancel order</span></span>|
   |<span data-ttu-id="7c537-289">MainMenu</span><span class="sxs-lookup"><span data-stu-id="7c537-289">MainMenu</span></span>|<span data-ttu-id="7c537-290">이름</span><span class="sxs-lookup"><span data-stu-id="7c537-290">Name</span></span>|<span data-ttu-id="7c537-291">theMainMenu</span><span class="sxs-lookup"><span data-stu-id="7c537-291">theMainMenu</span></span>|
   |<span data-ttu-id="7c537-292">MenuItem</span><span class="sxs-lookup"><span data-stu-id="7c537-292">MenuItem</span></span>|<span data-ttu-id="7c537-293">이름</span><span class="sxs-lookup"><span data-stu-id="7c537-293">Name</span></span>|<span data-ttu-id="7c537-294">fileCommands</span><span class="sxs-lookup"><span data-stu-id="7c537-294">fileCommands</span></span>|
   ||<span data-ttu-id="7c537-295">텍스트</span><span class="sxs-lookup"><span data-stu-id="7c537-295">Text</span></span>|<span data-ttu-id="7c537-296">파일(&F)</span><span class="sxs-lookup"><span data-stu-id="7c537-296">&File</span></span>|
   |<span data-ttu-id="7c537-297">MenuItem</span><span class="sxs-lookup"><span data-stu-id="7c537-297">MenuItem</span></span>|<span data-ttu-id="7c537-298">이름</span><span class="sxs-lookup"><span data-stu-id="7c537-298">Name</span></span>|<span data-ttu-id="7c537-299">exitApp</span><span class="sxs-lookup"><span data-stu-id="7c537-299">exitApp</span></span>|
   ||<span data-ttu-id="7c537-300">텍스트</span><span class="sxs-lookup"><span data-stu-id="7c537-300">Text</span></span>|<span data-ttu-id="7c537-301">끝내기(&X)</span><span class="sxs-lookup"><span data-stu-id="7c537-301">E&xit</span></span>|

   <span data-ttu-id="7c537-302">폼은 다음 이미지와 같이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7c537-302">Your form will look something like the following image:</span></span>

   ![이름 텍스트 상자 및 크기와 토 핑 선택 하 여 피자 주문 양식입니다.](./media/walkthrough-creating-an-accessible-windows-based-application/visual-basic-pizza-order-form.gif)

## <a name="supporting-high-contrast-mode"></a><span data-ttu-id="7c537-304">고대비 모드 지원</span><span class="sxs-lookup"><span data-stu-id="7c537-304">Supporting High Contrast Mode</span></span>

<span data-ttu-id="7c537-305">고대비 모드는 시각 장애가 있는 사용자에게 도움이 되는 대비 색과 글꼴 크기를 사용하여 가독성을 향상시키는 Windows 시스템 설정입니다.</span><span class="sxs-lookup"><span data-stu-id="7c537-305">High Contrast mode is a Windows system setting that improves readability by using contrasting colors and font sizes that are beneficial for visually impaired users.</span></span> <span data-ttu-id="7c537-306"><xref:System.Windows.Forms.SystemInformation.HighContrast%2A> 속성 고대비 모드가 설정 되어 있는지 확인 하기 위해 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7c537-306">The <xref:System.Windows.Forms.SystemInformation.HighContrast%2A> property is provided to determine whether the High Contrast mode is set.</span></span>

<span data-ttu-id="7c537-307">SystemInformation.HighContrast가 `true`이면 애플리케이션에서 다음을 수행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7c537-307">If SystemInformation.HighContrast is `true`, the application should:</span></span>

- <span data-ttu-id="7c537-308">시스템 색 구성표를 사용하여 모든 사용자 인터페이스 요소 표시</span><span class="sxs-lookup"><span data-stu-id="7c537-308">Display all user interface elements using the system color scheme</span></span>

- <span data-ttu-id="7c537-309">색을 통해 전달되는 모든 정보를 시각 신호나 소리로 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="7c537-309">Convey by visual cues or sound any information that is conveyed through color.</span></span> <span data-ttu-id="7c537-310">예를 들어 빨강 글꼴을 사용하여 특정 목록 항목이 강조 표시된 경우 해당 글꼴에 굵게 표시를 추가하여 항목이 강조 표시되었다는 색이 아닌 신호를 사용자에게 제공할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7c537-310">For example, if particular list items are highlighted by using a red font, you could also add bold to the font, so that the user has a non-color cue that the items are highlighted.</span></span>

- <span data-ttu-id="7c537-311">텍스트 뒤에 있는 모든 이미지 또는 패턴 생략</span><span class="sxs-lookup"><span data-stu-id="7c537-311">Omit any images or patterns behind text</span></span>

<span data-ttu-id="7c537-312">응용 프로그램이 시작되고 시스템 이벤트 <xref:Microsoft.Win32.SystemEvents.UserPreferenceChanged>에 응답할 때 응용 프로그램에서 <xref:System.Windows.Forms.SystemInformation.HighContrast%2A>의 설정을 확인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7c537-312">The application should check the setting of <xref:System.Windows.Forms.SystemInformation.HighContrast%2A> when the application starts and respond to the system event <xref:Microsoft.Win32.SystemEvents.UserPreferenceChanged>.</span></span> <span data-ttu-id="7c537-313"><xref:System.Windows.Forms.SystemInformation.HighContrast%2A>의 값이 변경되면 <xref:Microsoft.Win32.SystemEvents.UserPreferenceChanged> 이벤트가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="7c537-313">The <xref:Microsoft.Win32.SystemEvents.UserPreferenceChanged> event is raised whenever the value of <xref:System.Windows.Forms.SystemInformation.HighContrast%2A> changes.</span></span>

<span data-ttu-id="7c537-314">이 애플리케이션에서 색 시스템 설정을 사용하지 않는 요소는 `lblCompanyName`뿐입니다.</span><span class="sxs-lookup"><span data-stu-id="7c537-314">In our application, the only element that is not using the system settings for color is `lblCompanyName`.</span></span> <span data-ttu-id="7c537-315"><xref:System.Drawing.SystemColors> 클래스 레이블의 색 설정을 사용자가 선택한 시스템 색을 변경 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7c537-315">The <xref:System.Drawing.SystemColors> class is used to change the color settings of the label to the user-selected system colors.</span></span>

#### <a name="to-enable-high-contrast-mode-in-an-effective-way"></a><span data-ttu-id="7c537-316">효과적인 방법으로 고대비 모드를 사용하도록 설정하려면</span><span class="sxs-lookup"><span data-stu-id="7c537-316">To enable High Contrast mode in an effective way</span></span>

1. <span data-ttu-id="7c537-317">레이블의 색을 시스템 색으로 설정하는 메서드를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="7c537-317">Create a method to set the colors of the label to the system colors.</span></span>

    ```vb
    ' Visual Basic
    Private Sub SetColorScheme()
       If SystemInformation.HighContrast Then
          companyLabel.BackColor = SystemColors.Window
          companyLabel.ForeColor = SystemColors.WindowText
       Else
          companyLabel.BackColor = Color.Blue
          companyLabel.ForeColor = Color.Yellow
       End If
    End Sub
    ```

    ```csharp
    // C#
    private void SetColorScheme()
    {
       if (SystemInformation.HighContrast)
       {
          companyLabel.BackColor = SystemColors.Window;
          companyLabel.ForeColor = SystemColors.WindowText;
       }
       else
       {
          companyLabel.BackColor = Color.Blue;
          companyLabel.ForeColor = Color.Yellow;
       }
    }
    ```

2. <span data-ttu-id="7c537-318">양식 생성자(Visual Basic의 `Public Sub New()`, Visual C#의 `public class Form1`)에서 `SetColorScheme` 프로시저를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="7c537-318">Call the `SetColorScheme` procedure in the form constructor (`Public Sub New()` in Visual Basic and `public class Form1` in Visual C#).</span></span> <span data-ttu-id="7c537-319">Visual Basic에서 생성자에 액세스하려면 **Windows Form 디자이너에서 생성한 코드** 레이블이 지정된 영역을 확장해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7c537-319">To access the constructor in Visual Basic, you will need to expand the region labeled **Windows Form Designer generated code**.</span></span>

    ```vb
    ' Visual Basic
    Public Sub New()
       MyBase.New()
       InitializeComponent()
       SetColorScheme()
    End Sub
    ```

    ```csharp
    // C#
    public Form1()
    {
       InitializeComponent();
       SetColorScheme();
    }
    ```

3. <span data-ttu-id="7c537-320">적절한 서명을 사용하여 <xref:Microsoft.Win32.SystemEvents.UserPreferenceChanged> 이벤트에 응답하는 이벤트 프로시저를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="7c537-320">Create an event procedure, with the appropriate signature, to respond to the <xref:Microsoft.Win32.SystemEvents.UserPreferenceChanged> event.</span></span>

    ```vb
    ' Visual Basic
    Protected Sub UserPreferenceChanged(ByVal sender As Object, _
    ByVal e As Microsoft.Win32.UserPreferenceChangedEventArgs)
       SetColorScheme()
    End Sub
    ```

    ```csharp
    // C#
    public void UserPreferenceChanged(object sender,
    Microsoft.Win32.UserPreferenceChangedEventArgs e)
    {
       SetColorScheme();
    }
    ```

4. <span data-ttu-id="7c537-321">양식 생성자에서 `InitializeComponents` 호출 뒤에 이벤트 프로시저를 시스템 이벤트에 연결하는 코드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="7c537-321">Add code to the form constructor, after the call to `InitializeComponents`, to hook up the event procedure to the system event.</span></span> <span data-ttu-id="7c537-322">이 메서드는 `SetColorScheme` 프로시저를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="7c537-322">This method calls the `SetColorScheme` procedure.</span></span>

    ```vb
    ' Visual Basic
    Public Sub New()
       MyBase.New()
       InitializeComponent()
       SetColorScheme()
       AddHandler Microsoft.Win32.SystemEvents.UserPreferenceChanged, _
          AddressOf Me.UserPreferenceChanged
    End Sub
    ```

    ```csharp
    // C#
    public Form1()
    {
       InitializeComponent();
       SetColorScheme();
       Microsoft.Win32.SystemEvents.UserPreferenceChanged
          += new Microsoft.Win32.UserPreferenceChangedEventHandler(
          this.UserPreferenceChanged);
    }
    ```

5. <span data-ttu-id="7c537-323">폼 <xref:System.Windows.Forms.Control.Dispose%2A> 메서드에서 기본 클래스의 <xref:System.Windows.Forms.Control.Dispose%2A> 메서드 호출 앞에 코드를 추가하여 응용 프로그램이 닫힐 때 이벤트를 해제합니다.</span><span class="sxs-lookup"><span data-stu-id="7c537-323">Add code to the form <xref:System.Windows.Forms.Control.Dispose%2A> method, before the call to the <xref:System.Windows.Forms.Control.Dispose%2A> method of the base class, to release the event when the application closes.</span></span> <span data-ttu-id="7c537-324">Visual Basic에서 <xref:System.Windows.Forms.Control.Dispose%2A> 메서드에 액세스하려면 Windows Form 디자이너에서 생성한 코드 레이블이 지정된 영역을 확장해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7c537-324">To access the <xref:System.Windows.Forms.Control.Dispose%2A> method in Visual Basic, you will need to expand the region labeled Windows Form Designer generated code.</span></span>

    > [!NOTE]
    > <span data-ttu-id="7c537-325">시스템 이벤트 코드는 주 애플리케이션과 별개인 스레드를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="7c537-325">The system event code runs a thread separate from the main application.</span></span> <span data-ttu-id="7c537-326">이벤트를 해제하지 않으면 이벤트에 연결하는 코드가 프로그램이 닫힌 후에도 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="7c537-326">If you do not release the event, the code that you hook up to the event will run even after the program is closed.</span></span>

    ```vb
    ' Visual Basic
    Protected Overloads Overrides Sub Dispose(ByVal disposing As Boolean)
       If disposing Then
          If Not (components Is Nothing) Then
             components.Dispose()
          End If
       End If
       RemoveHandler Microsoft.Win32.SystemEvents.UserPreferenceChanged, _
          AddressOf Me.UserPreferenceChanged
       MyBase.Dispose(disposing)
    End Sub
    ```

    ```csharp
    // C#
    protected override void Dispose( bool disposing )
    {
       if( disposing )
       {
          if (components != null)
          {
             components.Dispose();
          }
       }
       Microsoft.Win32.SystemEvents.UserPreferenceChanged
          -= new Microsoft.Win32.UserPreferenceChangedEventHandler(
          this.UserPreferenceChanged);
       base.Dispose( disposing );
    }
    ```

6. <span data-ttu-id="7c537-327">F5 키를 눌러 애플리케이션을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="7c537-327">Press F5 to run the application.</span></span>

## <a name="conveying-important-information-by-means-other-than-sound"></a><span data-ttu-id="7c537-328">소리가 아닌 다른 수단으로 중요한 정보 전달</span><span class="sxs-lookup"><span data-stu-id="7c537-328">Conveying Important Information by Means Other Than Sound</span></span>

<span data-ttu-id="7c537-329">이 애플리케이션에서는 정보가 소리로만 전달되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7c537-329">In this application, no information is conveyed by sound alone.</span></span> <span data-ttu-id="7c537-330">애플리케이션에서 소리를 사용하는 경우 다른 수단을 통해서도 정보를 제공해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7c537-330">If you use sound in your application, then you should supply the information by some other means as well.</span></span>

#### <a name="to-supply-information-by-some-other-means-than-sound"></a><span data-ttu-id="7c537-331">소리가 아닌 다른 수단으로 정보를 제공하려면</span><span class="sxs-lookup"><span data-stu-id="7c537-331">To supply information by some other means than sound</span></span>

1. <span data-ttu-id="7c537-332">Windows API 함수 FlashWindow를 사용하여 제목 표시줄을 깜박이게 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="7c537-332">Make the title bar flash by using the Windows API function FlashWindow.</span></span> <span data-ttu-id="7c537-333">Windows API 함수를 호출 하는 방법의 예제를 참조 하세요. [연습: Windows Api 호출](~/docs/visual-basic/programming-guide/com-interop/walkthrough-calling-windows-apis.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="7c537-333">For an example of how to call Windows API functions, see [Walkthrough: Calling Windows APIs](~/docs/visual-basic/programming-guide/com-interop/walkthrough-calling-windows-apis.md).</span></span>

    > [!NOTE]
    > <span data-ttu-id="7c537-334">사용자가 Windows 소리 탐지 서비스를 사용하도록 설정했을 수도 있습니다. 이 서비스는 컴퓨터의 기본 제공 스피커를 통해 시스템 소리가 재생될 때 창도 깜박이게 합니다.</span><span class="sxs-lookup"><span data-stu-id="7c537-334">The user may have the Windows SoundSentry service enabled, which will also cause the window to flash when the system sounds are played through the computer's built-in speaker.</span></span>

2. <span data-ttu-id="7c537-335">사용자가 응답할 수 있도록 비모달 창에 중요한 정보를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="7c537-335">Display the important information in a non-modal window so that the user may respond to it.</span></span>

3. <span data-ttu-id="7c537-336">키보드 포커스를 획득하는 메시지 상자를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="7c537-336">Display a message box that acquires the keyboard focus.</span></span> <span data-ttu-id="7c537-337">사용자가 입력 중일 때는 이 메서드를 사용하지 마세요.</span><span class="sxs-lookup"><span data-stu-id="7c537-337">Avoid this method when the user may be typing.</span></span>

4. <span data-ttu-id="7c537-338">작업 표시줄의 상태 알림 영역에 상태 표시기를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="7c537-338">Display a status indicator in the status notification area of the taskbar.</span></span> <span data-ttu-id="7c537-339">자세한 내용은 [Windows Forms NotifyIcon 구성 요소를 사용하여 작업 표시줄에 애플리케이션 아이콘 추가](../controls/app-icons-to-the-taskbar-with-wf-notifyicon.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="7c537-339">For details, see [Adding Application Icons to the TaskBar with the Windows Forms NotifyIcon Component](../controls/app-icons-to-the-taskbar-with-wf-notifyicon.md).</span></span>

## <a name="testing-the-application"></a><span data-ttu-id="7c537-340">애플리케이션 테스트</span><span class="sxs-lookup"><span data-stu-id="7c537-340">Testing the Application</span></span>

<span data-ttu-id="7c537-341">애플리케이션을 배포하기 전에 구현한 접근성 기능을 테스트해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7c537-341">Before deploying the application, you should test the accessibility features that you have implemented.</span></span>

#### <a name="to-test-accessibility-features"></a><span data-ttu-id="7c537-342">접근성 기능을 테스트하려면</span><span class="sxs-lookup"><span data-stu-id="7c537-342">To test accessibility features</span></span>

1. <span data-ttu-id="7c537-343">키보드 액세스를 테스트하려면 마우스를 분리하고 키보드만 사용하여 각 기능에 대한 사용자 인터페이스를 탐색합니다.</span><span class="sxs-lookup"><span data-stu-id="7c537-343">To test keyboard access, unplug the mouse and navigate the user interface for each feature using only the keyboard.</span></span> <span data-ttu-id="7c537-344">키보드만 사용하여 모든 작업을 수행할 수 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="7c537-344">Ensure that all tasks may be performed using the keyboard only.</span></span>

2. <span data-ttu-id="7c537-345">고대비 지원을 테스트하려면 제어판의 내게 필요한 옵션 아이콘을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="7c537-345">To test support of High Contrast, choose the Accessibility Options icon in Control Panel.</span></span> <span data-ttu-id="7c537-346">표시 탭을 클릭하고 고대비 사용 확인란을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="7c537-346">Click the Display tab and select the Use High Contrast check box.</span></span> <span data-ttu-id="7c537-347">모든 사용자 인터페이스 요소를 탐색하여 색 및 글꼴 변경 내용이 반영되었는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="7c537-347">Navigate through all user interface elements to ensure that the color and font changes are reflected.</span></span> <span data-ttu-id="7c537-348">또한 텍스트 뒤에 그려진 이미지 또는 패턴이 생략되었는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="7c537-348">Also, ensure that images or patterns drawn behind text are omitted.</span></span>

    > [!NOTE]
    > <span data-ttu-id="7c537-349">Windows NT 4에서는 제어판에 내게 필요한 옵션 아이콘이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="7c537-349">Windows NT 4 does not have an Accessibility Options icon in Control Panel.</span></span> <span data-ttu-id="7c537-350">따라서 SystemInformation.HighContrast 설정을 변경하는 이 절차는 Windows NT 4에서 작동하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7c537-350">Thus, this procedure for changing the SystemInformation.HighContrast setting does not work in Windows NT 4.</span></span>

3. <span data-ttu-id="7c537-351">다른 도구는 애플리케이션의 접근성 테스트에 바로 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7c537-351">Other tools are readily available for testing the accessibility of an application.</span></span>

4. <span data-ttu-id="7c537-352">키보드 포커스 노출을 테스트하려면 돋보기를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="7c537-352">To test exposing the keyboard focus, run Magnifier.</span></span> <span data-ttu-id="7c537-353">돋보기를 열려면 **시작** 메뉴를 클릭하고**프로그램**, **보조프로그램**, **내게 필요한 옵션**을 차례로 가리킨 다음 **돋보기**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="7c537-353">(To open it, click the **Start** menu, point to **Programs**, point to **Accessories**, point to **Accessibility**, and then click **Magnifier**).</span></span> <span data-ttu-id="7c537-354">키보드 탭 이동 및 마우스를 사용하여 사용자 인터페이스를 탐색합니다.</span><span class="sxs-lookup"><span data-stu-id="7c537-354">Navigate the user interface using both keyboard tabbing and the mouse.</span></span> <span data-ttu-id="7c537-355">**돋보기**에서 모든 탐색이 제대로 추적되는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="7c537-355">Ensure that all navigation is tracked properly in **Magnifier**.</span></span>

5. <span data-ttu-id="7c537-356">화면 요소 노출을 테스트하려면 조사를 실행하고 마우스와 Tab 키를 둘 다 사용하여 각 요소에 접근합니다.</span><span class="sxs-lookup"><span data-stu-id="7c537-356">To test exposing screen elements, run Inspect, and use both the mouse and the TAB key to reach each element.</span></span> <span data-ttu-id="7c537-357">조사 창의 이름, 상태, 역할, 위치 및 값 필드에 제공된 정보가 UI의 각 개체에 대해 사용자에게 의미 있는 정보인지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="7c537-357">Ensure that the information presented in the Name, State, Role, Location, and Value fields of the Inspect window is meaningful to the user for each object in the UI.</span></span>
