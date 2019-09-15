---
title: '연습: WPF에서 Windows Forms 복합 컨트롤 호스팅'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- hosting Windows Forms control in WPF [WPF]
- composite controls [WPF], hosting in WPF
ms.assetid: 96fcd78d-1c77-4206-8928-3a0579476ef4
ms.openlocfilehash: e4c1de17b131ee68c6e6fce0035b703eb5b489a0
ms.sourcegitcommit: 005980b14629dfc193ff6cdc040800bc75e0a5a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/14/2019
ms.locfileid: "70991879"
---
# <a name="walkthrough-hosting-a-windows-forms-composite-control-in-wpf"></a><span data-ttu-id="0b920-102">연습: WPF에서 Windows Forms 복합 컨트롤 호스팅</span><span class="sxs-lookup"><span data-stu-id="0b920-102">Walkthrough: Hosting a Windows Forms Composite Control in WPF</span></span>
[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]<span data-ttu-id="0b920-103">에서는 응용 프로그램을 만들기 위한 다양한 환경을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="0b920-103">provides a rich environment for creating applications.</span></span> <span data-ttu-id="0b920-104">그러나 코드에 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 상당한 투자가 있으면 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 응용 프로그램에서 해당 코드를 처음부터 다시 작성 하는 것 보다는 해당 코드를 다시 사용 하는 것이 더 효과적일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0b920-104">However, when you have a substantial investment in [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] code, it can be more effective to reuse at least some of that code in your [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] application rather than to rewrite it from scratch.</span></span> <span data-ttu-id="0b920-105">가장 일반적인 시나리오는 기존 Windows Forms 컨트롤이 있는 경우입니다.</span><span class="sxs-lookup"><span data-stu-id="0b920-105">The most common scenario is when you have existing Windows Forms controls.</span></span> <span data-ttu-id="0b920-106">경우에 따라 이러한 컨트롤에 대한 소스 코드에 액세스하지 못할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0b920-106">In some cases, you might not even have access to the source code for these controls.</span></span> [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]<span data-ttu-id="0b920-107">[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 응용 프로그램에서 이러한 컨트롤을 호스팅하기 위한 간단한 절차를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="0b920-107">provides a straightforward procedure for hosting such controls in a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] application.</span></span> <span data-ttu-id="0b920-108">예를 들어, 특수화 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Forms.DataGridView> 된 컨트롤을 호스트 하는 동안 대부분의 프로그래밍에를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0b920-108">For example, you can use [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] for most of your programming while hosting your specialized <xref:System.Windows.Forms.DataGridView> controls.</span></span>  
  
 <span data-ttu-id="0b920-109">이 연습에서는 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 응용 프로그램에서 데이터 입력을 수행 하기 위해 Windows Forms 복합 컨트롤을 호스트 하는 응용 프로그램을 단계별로 안내 합니다.</span><span class="sxs-lookup"><span data-stu-id="0b920-109">This walkthrough steps you through an application that hosts a Windows Forms composite control to perform data entry in a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] application.</span></span> <span data-ttu-id="0b920-110">복합 컨트롤은 DLL로 패키지됩니다.</span><span class="sxs-lookup"><span data-stu-id="0b920-110">The composite control is packaged in a DLL.</span></span> <span data-ttu-id="0b920-111">이 일반적인 절차는 더 복잡한 애플리케이션 및 컨트롤로 확장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0b920-111">This general procedure can be extended to more complex applications and controls.</span></span> <span data-ttu-id="0b920-112">이 연습은 [연습의 모양과 기능과 거의 동일 하 게 디자인 되었습니다. Windows Forms](walkthrough-hosting-a-wpf-composite-control-in-windows-forms.md)에서 WPF 복합 컨트롤 호스팅</span><span class="sxs-lookup"><span data-stu-id="0b920-112">This walkthrough is designed to be nearly identical in appearance and functionality to [Walkthrough: Hosting a WPF Composite Control in Windows Forms](walkthrough-hosting-a-wpf-composite-control-in-windows-forms.md).</span></span> <span data-ttu-id="0b920-113">주요 차이점은 호스팅 시나리오가 반대라는 점입니다.</span><span class="sxs-lookup"><span data-stu-id="0b920-113">The primary difference is that the hosting scenario is reversed.</span></span>  
  
 <span data-ttu-id="0b920-114">이 연습은 두 개의 섹션으로 구분됩니다.</span><span class="sxs-lookup"><span data-stu-id="0b920-114">The walkthrough is divided into two sections.</span></span> <span data-ttu-id="0b920-115">첫 번째 섹션에서는 Windows Forms 복합 컨트롤의 구현을 간략하게 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="0b920-115">The first section briefly describes the implementation of the Windows Forms composite control.</span></span> <span data-ttu-id="0b920-116">두 번째 섹션에서는 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 응용 프로그램에서 복합 컨트롤을 호스트 하 고, 컨트롤에서 이벤트를 수신 하 고, 컨트롤의 일부 속성에 액세스 하는 방법에 대해 자세히 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="0b920-116">The second section discusses in detail how to host the composite control in a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] application, receive events from the control, and access some of the control's properties.</span></span>  
  
 <span data-ttu-id="0b920-117">이 연습에서 설명하는 작업은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="0b920-117">Tasks illustrated in this walkthrough include:</span></span>  
  
- <span data-ttu-id="0b920-118">Windows Forms 복합 컨트롤 구현</span><span class="sxs-lookup"><span data-stu-id="0b920-118">Implementing the Windows Forms composite control.</span></span>  
  
- <span data-ttu-id="0b920-119">WPF 호스트 애플리케이션 구현</span><span class="sxs-lookup"><span data-stu-id="0b920-119">Implementing the WPF host application.</span></span>  
  
 <span data-ttu-id="0b920-120">이 연습에서 설명 하는 작업의 전체 코드 목록은 [WPF에서 Windows Forms 복합 컨트롤 호스팅 샘플](https://go.microsoft.com/fwlink/?LinkID=159999)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="0b920-120">For a complete code listing of the tasks illustrated in this walkthrough, see [Hosting a Windows Forms Composite Control in WPF Sample](https://go.microsoft.com/fwlink/?LinkID=159999).</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="0b920-121">전제 조건</span><span class="sxs-lookup"><span data-stu-id="0b920-121">Prerequisites</span></span>  

<span data-ttu-id="0b920-122">이 연습을 완료하려면 Visual Studio가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="0b920-122">You need Visual Studio to complete this walkthrough.</span></span>
  
## <a name="implementing-the-windows-forms-composite-control"></a><span data-ttu-id="0b920-123">Windows Forms 복합 컨트롤 구현</span><span class="sxs-lookup"><span data-stu-id="0b920-123">Implementing the Windows Forms Composite Control</span></span>  
 <span data-ttu-id="0b920-124">이 예제에서 사용 되는 Windows Forms 복합 컨트롤은 간단한 데이터 입력 폼입니다.</span><span class="sxs-lookup"><span data-stu-id="0b920-124">The Windows Forms composite control used in this example is a simple data-entry form.</span></span> <span data-ttu-id="0b920-125">이 폼에서는 사용자의 이름 및 주소를 사용한 다음 사용자 지정 이벤트를 사용하여 해당 정보를 호스트에 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="0b920-125">This form takes the user's name and address and then uses a custom event to return that information to the host.</span></span> <span data-ttu-id="0b920-126">다음 그림에서는 렌더링된 컨트롤을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="0b920-126">The following illustration shows the rendered control.</span></span>  

 <span data-ttu-id="0b920-127">다음 이미지는 Windows Forms 복합 컨트롤을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="0b920-127">The following image shows a Windows Forms composite control:</span></span>  

 ![간단한 Windows Forms 컨트롤을 보여 주는 스크린샷](./media/walkthrough-hosting-a-windows-forms-composite-control-in-wpf/windows-forms-control.gif)  
  
### <a name="creating-the-project"></a><span data-ttu-id="0b920-129">프로젝트 만들기</span><span class="sxs-lookup"><span data-stu-id="0b920-129">Creating the Project</span></span>  
 <span data-ttu-id="0b920-130">프로젝트를 시작하려면</span><span class="sxs-lookup"><span data-stu-id="0b920-130">To start the project:</span></span>  
  
1. <span data-ttu-id="0b920-131">를 [!INCLUDE[TLA#tla_visualstu](../../../../includes/tlasharptla-visualstu-md.md)]시작 하 고 **새 프로젝트** 대화 상자를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="0b920-131">Launch [!INCLUDE[TLA#tla_visualstu](../../../../includes/tlasharptla-visualstu-md.md)], and open the **New Project** dialog box.</span></span>  
  
2. <span data-ttu-id="0b920-132">창 범주에서 **Windows Forms 컨트롤 라이브러리** 템플릿을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="0b920-132">In the Window category, select the **Windows Forms Control Library** template.</span></span>  
  
3. <span data-ttu-id="0b920-133">새 프로젝트의 이름을 `MyControls`로 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="0b920-133">Name the new project `MyControls`.</span></span>  
  
4. <span data-ttu-id="0b920-134">위치에 대해와 같이 편리 하 게 `WpfHostingWindowsFormsControl`명명 된 최상위 폴더를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="0b920-134">For the location, specify a conveniently named top-level folder, such as `WpfHostingWindowsFormsControl`.</span></span> <span data-ttu-id="0b920-135">나중에 이 폴더에 호스트 애플리케이션을 넣습니다.</span><span class="sxs-lookup"><span data-stu-id="0b920-135">Later, you will put the host application in this folder.</span></span>  
  
5. <span data-ttu-id="0b920-136">**확인**을 클릭해 프로젝트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="0b920-136">Click **OK** to create the project.</span></span> <span data-ttu-id="0b920-137">기본 프로젝트에는 라는 `UserControl1`단일 컨트롤이 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0b920-137">The default project contains a single control named `UserControl1`.</span></span>  
  
6. <span data-ttu-id="0b920-138">솔루션 탐색기에서로 `MyControl1`이름을 `UserControl1` 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="0b920-138">In Solution Explorer, rename `UserControl1` to `MyControl1`.</span></span>  
  
 <span data-ttu-id="0b920-139">프로젝트에는 다음과 같은 시스템 DLL에 대한 참조가 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0b920-139">Your project should have references to the following system DLLs.</span></span> <span data-ttu-id="0b920-140">이러한 DLL이 기본적으로 포함되지 않은 경우 프로젝트에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="0b920-140">If any of these DLLs are not included by default, add them to the project.</span></span>  
  
- <span data-ttu-id="0b920-141">시스템</span><span class="sxs-lookup"><span data-stu-id="0b920-141">System</span></span>  
  
- <span data-ttu-id="0b920-142">System.Data</span><span class="sxs-lookup"><span data-stu-id="0b920-142">System.Data</span></span>  
  
- <span data-ttu-id="0b920-143">System.Drawing</span><span class="sxs-lookup"><span data-stu-id="0b920-143">System.Drawing</span></span>  
  
- <span data-ttu-id="0b920-144">System.Windows.Forms</span><span class="sxs-lookup"><span data-stu-id="0b920-144">System.Windows.Forms</span></span>  
  
- <span data-ttu-id="0b920-145">System.Xml</span><span class="sxs-lookup"><span data-stu-id="0b920-145">System.Xml</span></span>  
  
### <a name="adding-controls-to-the-form"></a><span data-ttu-id="0b920-146">폼에 컨트롤 추가</span><span class="sxs-lookup"><span data-stu-id="0b920-146">Adding Controls to the Form</span></span>  
 <span data-ttu-id="0b920-147">폼에 컨트롤을 추가하려면</span><span class="sxs-lookup"><span data-stu-id="0b920-147">To add controls to the form:</span></span>  
  
- <span data-ttu-id="0b920-148">디자이너 `MyControl1` 에서를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="0b920-148">Open `MyControl1` in the designer.</span></span>  
  
 <span data-ttu-id="0b920-149">앞의 <xref:System.Windows.Forms.Label> 그림과 같이 폼에 <xref:System.Windows.Forms.TextBox> 5 개의 컨트롤과 해당 컨트롤을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="0b920-149">Add five <xref:System.Windows.Forms.Label> controls and their corresponding <xref:System.Windows.Forms.TextBox> controls, sized and arranged as they are in the preceding illustration, on the form.</span></span> <span data-ttu-id="0b920-150">이 예제에서 컨트롤의 <xref:System.Windows.Forms.TextBox> 이름은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="0b920-150">In the example, the <xref:System.Windows.Forms.TextBox> controls are named:</span></span>  
  
- `txtName`  
  
- `txtAddress`  
  
- `txtCity`  
  
- `txtState`  
  
- `txtZip`  
  
 <span data-ttu-id="0b920-151">확인 및 <xref:System.Windows.Forms.Button> **취소**라는 두 개의 컨트롤 **을** 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="0b920-151">Add two <xref:System.Windows.Forms.Button> controls labeled **OK** and **Cancel**.</span></span> <span data-ttu-id="0b920-152">이 예제에서 단추 이름은 `btnOK` 각각 및 `btnCancel`입니다.</span><span class="sxs-lookup"><span data-stu-id="0b920-152">In the example, the button names are `btnOK` and `btnCancel`, respectively.</span></span>  
  
### <a name="implementing-the-supporting-code"></a><span data-ttu-id="0b920-153">지원 코드 구현</span><span class="sxs-lookup"><span data-stu-id="0b920-153">Implementing the Supporting Code</span></span>  
 <span data-ttu-id="0b920-154">코드 보기에서 폼을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="0b920-154">Open the form in code view.</span></span> <span data-ttu-id="0b920-155">컨트롤은 사용자 지정 `OnButtonClick` 이벤트를 발생 시켜 해당 호스트에 수집 된 데이터를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="0b920-155">The control returns the collected data to its host by raising the custom `OnButtonClick` event.</span></span> <span data-ttu-id="0b920-156">데이터는 이벤트 인수 개체에 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0b920-156">The data is contained in the event argument object.</span></span> <span data-ttu-id="0b920-157">다음 코드에서는 이벤트 및 대리자 선언을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="0b920-157">The following code shows the event and delegate declaration.</span></span>  
  
 <span data-ttu-id="0b920-158">`MyControl1` 클래스에 다음 코드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="0b920-158">Add the following code to the `MyControl1` class.</span></span>  
  
 [!code-csharp[WpfHostingWindowsFormsControl#2](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/CSharp/MyControls/MyControl1.cs#2)]
 [!code-vb[WpfHostingWindowsFormsControl#2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/VisualBasic/MyControls/MyControl1.vb#2)]

 <span data-ttu-id="0b920-159">클래스 `MyControlEventArgs` 에는 호스트에 반환 되는 정보가 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0b920-159">The `MyControlEventArgs` class contains the information to be returned to the host.</span></span>

 <span data-ttu-id="0b920-160">다음 클래스를 폼에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="0b920-160">Add the following class to the form.</span></span>

 [!code-csharp[WpfHostingWindowsFormsControl#3](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/CSharp/MyControls/MyControl1.cs#3)]
 [!code-vb[WpfHostingWindowsFormsControl#3](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/VisualBasic/MyControls/MyControl1.vb#3)]

 <span data-ttu-id="0b920-161">사용자가 **확인** 또는 **취소** <xref:System.Windows.Forms.Control.Click> 단추를 클릭 하면 이벤트 처리기가 데이터를 포함 `MyControlEventArgs` 하는 개체를 만들고 이벤트를 `OnButtonClick` 발생 시킵니다.</span><span class="sxs-lookup"><span data-stu-id="0b920-161">When the user clicks the **OK** or **Cancel** button, the <xref:System.Windows.Forms.Control.Click> event handlers create a `MyControlEventArgs` object that contains the data and raises the `OnButtonClick` event.</span></span> <span data-ttu-id="0b920-162">두 처리기의 유일한 차이점은 이벤트 인수의 `IsOK` 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="0b920-162">The only difference between the two handlers is the event argument's `IsOK` property.</span></span> <span data-ttu-id="0b920-163">이 속성을 통해 호스트는 클릭한 단추를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0b920-163">This property enables the host to determine which button was clicked.</span></span> <span data-ttu-id="0b920-164">`true` **확인** 단추 와`false` **취소** 단추의 경우로 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0b920-164">It is set to `true` for the **OK** button, and `false` for the **Cancel** button.</span></span> <span data-ttu-id="0b920-165">다음 코드에서는 두 개의 단추 처리기를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="0b920-165">The following code shows the two button handlers.</span></span>

 <span data-ttu-id="0b920-166">`MyControl1` 클래스에 다음 코드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="0b920-166">Add the following code to the `MyControl1` class.</span></span>

 [!code-csharp[WpfHostingWindowsFormsControl#4](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/CSharp/MyControls/MyControl1.cs#4)]
 [!code-vb[WpfHostingWindowsFormsControl#4](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/VisualBasic/MyControls/MyControl1.vb#4)]

### <a name="giving-the-assembly-a-strong-name-and-building-the-assembly"></a><span data-ttu-id="0b920-167">어셈블리에 강력한 이름을 지정하고 어셈블리 빌드</span><span class="sxs-lookup"><span data-stu-id="0b920-167">Giving the Assembly a Strong Name and Building the Assembly</span></span>
 <span data-ttu-id="0b920-168">[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 응용 프로그램에서이 어셈블리를 참조 하려면 강력한 이름을 포함 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0b920-168">For this assembly to be referenced by a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] application, it must have a strong name.</span></span> <span data-ttu-id="0b920-169">강력한 이름을 만들려면 Sn.exe를 사용 하 여 키 파일을 만들고 프로젝트에 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="0b920-169">To create a strong name, create a key file with Sn.exe and add it to your project.</span></span>

1. <span data-ttu-id="0b920-170">[!INCLUDE[TLA2#tla_visualstu](../../../../includes/tla2sharptla-visualstu-md.md)] 명령 프롬프트를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="0b920-170">Open a [!INCLUDE[TLA2#tla_visualstu](../../../../includes/tla2sharptla-visualstu-md.md)] command prompt.</span></span> <span data-ttu-id="0b920-171">이렇게 하려면 **시작** 메뉴를 클릭 한 다음 **모든 프로그램/Microsoft Visual Studio 2010/Visual Studio Tools/Visual Studio 명령 프롬프트**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="0b920-171">To do so, click the **Start** menu, and then select **All Programs/Microsoft Visual Studio 2010/Visual Studio Tools/Visual Studio Command Prompt**.</span></span> <span data-ttu-id="0b920-172">그러면 사용자 지정된 환경 변수가 있는 콘솔 창이 시작됩니다.</span><span class="sxs-lookup"><span data-stu-id="0b920-172">This launches a console window with customized environment variables.</span></span>

2. <span data-ttu-id="0b920-173">명령 프롬프트에서 `cd` 명령을 사용 하 여 프로젝트 폴더로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="0b920-173">At the command prompt, use the `cd` command to go to your project folder.</span></span>

3. <span data-ttu-id="0b920-174">다음 명령을 실행하여 MyControls.snk라는 키 파일을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="0b920-174">Generate a key file named MyControls.snk by running the following command.</span></span>

    ```console
    Sn.exe -k MyControls.snk
    ```

4. <span data-ttu-id="0b920-175">프로젝트에 키 파일을 포함 하려면 솔루션 탐색기에서 프로젝트 이름을 마우스 오른쪽 단추로 클릭 한 다음 **속성**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="0b920-175">To include the key file in your project, right-click the project name in Solution Explorer and then click **Properties**.</span></span> <span data-ttu-id="0b920-176">프로젝트 디자이너에서 **서명** 탭을 클릭 하 고 **어셈블리 서명** 확인란을 선택한 다음 키 파일을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="0b920-176">In the Project Designer, click the **Signing** tab, select the **Sign the assembly** check box and then browse to your key file.</span></span>

5. <span data-ttu-id="0b920-177">솔루션을 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="0b920-177">Build the solution.</span></span> <span data-ttu-id="0b920-178">빌드하면 MyControls.dll이라는 DLL이 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="0b920-178">The build will produce a DLL named MyControls.dll.</span></span>

## <a name="implementing-the-wpf-host-application"></a><span data-ttu-id="0b920-179">WPF 호스트 애플리케이션 구현</span><span class="sxs-lookup"><span data-stu-id="0b920-179">Implementing the WPF Host Application</span></span>
 <span data-ttu-id="0b920-180">호스트 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 응용 프로그램은 <xref:System.Windows.Forms.Integration.WindowsFormsHost> 컨트롤을 사용 하 `MyControl1`여를 호스팅합니다.</span><span class="sxs-lookup"><span data-stu-id="0b920-180">The [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] host application uses the <xref:System.Windows.Forms.Integration.WindowsFormsHost> control to host `MyControl1`.</span></span> <span data-ttu-id="0b920-181">응용 프로그램은 `OnButtonClick` 이벤트를 처리 하 여 컨트롤에서 데이터를 수신 합니다.</span><span class="sxs-lookup"><span data-stu-id="0b920-181">The application handles the `OnButtonClick` event to receive the data from the control.</span></span> <span data-ttu-id="0b920-182">또한 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 응용 프로그램에서 컨트롤의 일부 속성을 변경할 수 있는 옵션 단추 모음이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0b920-182">It also has a collection of option buttons that enable you to change some of the control's properties from the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] application.</span></span> <span data-ttu-id="0b920-183">다음 그림에서는 완료된 애플리케이션을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="0b920-183">The following illustration shows the finished application.</span></span>

<span data-ttu-id="0b920-184">다음 이미지는 WPF 응용 프로그램에 포함 된 컨트롤을 포함 하 여 전체 응용 프로그램을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="0b920-184">The following image shows the complete application, including the control embedded in the WPF application:</span></span>

 ![WPF 페이지에 포함 된 컨트롤을 보여 주는 스크린샷](./media/walkthrough-hosting-a-windows-forms-composite-control-in-wpf/windows-presentation-foundation-page-control.gif)

### <a name="creating-the-project"></a><span data-ttu-id="0b920-186">프로젝트 만들기</span><span class="sxs-lookup"><span data-stu-id="0b920-186">Creating the Project</span></span>
 <span data-ttu-id="0b920-187">프로젝트를 시작하려면</span><span class="sxs-lookup"><span data-stu-id="0b920-187">To start the project:</span></span>

1. <span data-ttu-id="0b920-188">를 [!INCLUDE[TLA2#tla_visualstu](../../../../includes/tla2sharptla-visualstu-md.md)]열고 **새 프로젝트**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="0b920-188">Open [!INCLUDE[TLA2#tla_visualstu](../../../../includes/tla2sharptla-visualstu-md.md)], and select **New Project**.</span></span>

2. <span data-ttu-id="0b920-189">창 범주에서 **WPF 응용 프로그램** 템플릿을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="0b920-189">In the Window category, select the **WPF Application** template.</span></span>

3. <span data-ttu-id="0b920-190">새 프로젝트의 이름을 `WpfHost`로 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="0b920-190">Name the new project `WpfHost`.</span></span>

4. <span data-ttu-id="0b920-191">위치에는 MyControls 프로젝트를 포함하는 동일한 최상위 폴더를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="0b920-191">For the location, specify the same top-level folder that contains the MyControls project.</span></span>

5. <span data-ttu-id="0b920-192">**확인**을 클릭해 프로젝트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="0b920-192">Click **OK** to create the project.</span></span>

 <span data-ttu-id="0b920-193">또한 및 기타 어셈블리를 포함 `MyControl1` 하는 DLL에 대 한 참조를 추가 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0b920-193">You also need to add references to the DLL that contains `MyControl1` and other assemblies.</span></span>

1. <span data-ttu-id="0b920-194">솔루션 탐색기에서 프로젝트 이름을 마우스 오른쪽 단추로 클릭 하 고 **참조 추가**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="0b920-194">Right-click the project name in Solution Explorer and select **Add Reference**.</span></span>

2. <span data-ttu-id="0b920-195">**찾아보기** 탭을 클릭 하 고 MyControls이 포함 된 폴더를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="0b920-195">Click the **Browse** tab, and browse to the folder that contains MyControls.dll.</span></span> <span data-ttu-id="0b920-196">이 연습에서 이 폴더는 MyControls\bin\Debug입니다.</span><span class="sxs-lookup"><span data-stu-id="0b920-196">For this walkthrough, this folder is MyControls\bin\Debug.</span></span>

3. <span data-ttu-id="0b920-197">MyControls를 선택 하 고 **확인**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="0b920-197">Select MyControls.dll, and then click **OK**.</span></span>

4. <span data-ttu-id="0b920-198">Windows양식 통합 어셈블리에 참조를 추가 합니다 .이 어셈블리에는 Windows Integration .dll 이라는 이름이 지정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0b920-198">Add a reference to the WindowsFormsIntegration assembly, which is named WindowsFormsIntegration.dll.</span></span>

### <a name="implementing-the-basic-layout"></a><span data-ttu-id="0b920-199">기본 레이아웃 구현</span><span class="sxs-lookup"><span data-stu-id="0b920-199">Implementing the Basic Layout</span></span>
 <span data-ttu-id="0b920-200">호스트 [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] 응용 프로그램의는 mainwindow.xaml에서 구현 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0b920-200">The [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] of the host application is implemented in MainWindow.xaml.</span></span> <span data-ttu-id="0b920-201">이 파일에 [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] 는 레이아웃을 정의 하 고 Windows Forms 컨트롤을 호스트 하는 태그가 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0b920-201">This file contains [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] markup that defines the layout, and hosts the Windows Forms control.</span></span> <span data-ttu-id="0b920-202">애플리케이션은 세 가지 영역으로 구분됩니다.</span><span class="sxs-lookup"><span data-stu-id="0b920-202">The application is divided into three regions:</span></span>

- <span data-ttu-id="0b920-203">**컨트롤 속성** 패널-호스트 된 컨트롤의 다양 한 속성을 수정 하는 데 사용할 수 있는 옵션 단추 모음이 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0b920-203">The **Control Properties** panel, which contains a collection of option buttons that you can use to modify various properties of the hosted control.</span></span>

- <span data-ttu-id="0b920-204">호스팅된 컨트롤에서 반환 된 데이터를 표시 하 <xref:System.Windows.Controls.TextBlock> 는 여러 요소가 포함 된 **제어판의 데이터** 입니다.</span><span class="sxs-lookup"><span data-stu-id="0b920-204">The **Data from Control** panel, which contains several <xref:System.Windows.Controls.TextBlock> elements that display the data returned from the hosted control.</span></span>

- <span data-ttu-id="0b920-205">호스트된 컨트롤 자체.</span><span class="sxs-lookup"><span data-stu-id="0b920-205">The hosted control itself.</span></span>

 <span data-ttu-id="0b920-206">기본 레이아웃은 다음과 같은 XAML로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="0b920-206">The basic layout is shown in the following XAML.</span></span> <span data-ttu-id="0b920-207">호스트 `MyControl1` 하는 데 필요한 태그는이 예제에서 생략 되었지만 나중에 설명 하겠습니다.</span><span class="sxs-lookup"><span data-stu-id="0b920-207">The markup that is needed to host `MyControl1` is omitted from this example, but will be discussed later.</span></span>

 <span data-ttu-id="0b920-208">MainWindow.xaml의 XAML을 다음 코드로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="0b920-208">Replace the XAML in MainWindow.xaml with the following.</span></span> <span data-ttu-id="0b920-209">Visual Basic를 사용 하는 경우 클래스를로 `x:Class="MainWindow"`변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="0b920-209">If you are using Visual Basic, change the class to `x:Class="MainWindow"`.</span></span>

 [!code-xaml[WpfHostingWindowsFormsControl#100](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/CSharp/WpfHost/Page1.xaml#100)]

 <span data-ttu-id="0b920-210">첫 번째 <xref:System.Windows.Controls.StackPanel> 요소에는 호스트 된 <xref:System.Windows.Controls.RadioButton> 컨트롤의 다양 한 기본 속성을 수정할 수 있도록 하는 여러 컨트롤 집합이 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0b920-210">The first <xref:System.Windows.Controls.StackPanel> element contains several sets of <xref:System.Windows.Controls.RadioButton> controls that enable you to modify various default properties of the hosted control.</span></span> <span data-ttu-id="0b920-211">그런 다음 <xref:System.Windows.Forms.Integration.WindowsFormsHost> 를 호스팅하 `MyControl1`는 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="0b920-211">That is followed by a <xref:System.Windows.Forms.Integration.WindowsFormsHost> element, which hosts `MyControl1`.</span></span> <span data-ttu-id="0b920-212">Final <xref:System.Windows.Controls.StackPanel> 요소에는 호스팅된 <xref:System.Windows.Controls.TextBlock> 컨트롤에서 반환 하는 데이터를 표시 하는 여러 요소가 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0b920-212">The final <xref:System.Windows.Controls.StackPanel> element contains several <xref:System.Windows.Controls.TextBlock> elements that display the data that is returned by the hosted control.</span></span> <span data-ttu-id="0b920-213">요소와 <xref:System.Windows.Controls.DockPanel.Dock%2A> 및 <xref:System.Windows.FrameworkElement.Height%2A> 특성 설정의 순서는 호스트 된 컨트롤을 간격이 나 왜곡 없이 창에 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="0b920-213">The ordering of the elements and the <xref:System.Windows.Controls.DockPanel.Dock%2A> and <xref:System.Windows.FrameworkElement.Height%2A> attribute settings embed the hosted control into the window with no gaps or distortion.</span></span>

#### <a name="hosting-the-control"></a><span data-ttu-id="0b920-214">컨트롤 호스팅</span><span class="sxs-lookup"><span data-stu-id="0b920-214">Hosting the Control</span></span>
 <span data-ttu-id="0b920-215">이전 XAML의 편집 된 다음 버전은를 호스트 `MyControl1`하는 데 필요한 요소를 중점적으로 다룹니다.</span><span class="sxs-lookup"><span data-stu-id="0b920-215">The following edited version of the previous XAML focuses on the elements that are needed to host `MyControl1`.</span></span>

 [!code-xaml[WpfHostingWindowsFormsControl#101](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/CSharp/WpfHost/Page1.xaml#101)]
[!code-xaml[WpfHostingWindowsFormsControl#102](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/CSharp/WpfHost/Page1.xaml#102)]

 <span data-ttu-id="0b920-216">네임 `xmlns` 스페이스 매핑 특성은 호스팅된 컨트롤을 포함 `MyControls` 하는 네임 스페이스에 대 한 참조를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="0b920-216">The `xmlns` namespace mapping attribute creates a reference to the `MyControls` namespace that contains the hosted control.</span></span> <span data-ttu-id="0b920-217">이 매핑을 사용 하면를 `MyControl1` [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 로 `<mcl:MyControl1>`나타낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0b920-217">This mapping enables you to represent `MyControl1` in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] as `<mcl:MyControl1>`.</span></span>

 <span data-ttu-id="0b920-218">XAML의 두 요소가 호스팅을 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="0b920-218">Two elements in the XAML handle the hosting:</span></span>

- <span data-ttu-id="0b920-219">`WindowsFormsHost`응용[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 프로그램 <xref:System.Windows.Forms.Integration.WindowsFormsHost> 에서 Windows Forms 컨트롤을 호스트 하는 데 사용할 수 있는 요소를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="0b920-219">`WindowsFormsHost` represents the <xref:System.Windows.Forms.Integration.WindowsFormsHost> element that enables you to host a Windows Forms control in a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] application.</span></span>

- <span data-ttu-id="0b920-220">`mcl:MyControl1`가 나타내는 `MyControl1`는 <xref:System.Windows.Forms.Integration.WindowsFormsHost> 요소의 자식 컬렉션에 추가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0b920-220">`mcl:MyControl1`, which represents `MyControl1`, is added to the <xref:System.Windows.Forms.Integration.WindowsFormsHost> element's child collection.</span></span> <span data-ttu-id="0b920-221">결과적으로이 Windows Forms 컨트롤은 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 창의 일부로 렌더링 되며 응용 프로그램에서 컨트롤과 통신할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0b920-221">As a result, this Windows Forms control is rendered as part of the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] window, and you can communicate with the control from the application.</span></span>

### <a name="implementing-the-code-behind-file"></a><span data-ttu-id="0b920-222">코드 숨김 파일 구현</span><span class="sxs-lookup"><span data-stu-id="0b920-222">Implementing the Code-Behind File</span></span>
 <span data-ttu-id="0b920-223">코드 숨김이 파일 mainwindow.xaml 또는 MainWindow.xaml.cs에는 이전 섹션에서 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] 설명한의 기능을 구현 하는 절차 코드가 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0b920-223">The code-behind file, MainWindow.xaml.vb or MainWindow.xaml.cs, contains the procedural code that implements the functionality of the [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] discussed in the preceding section.</span></span> <span data-ttu-id="0b920-224">기본 작업은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="0b920-224">The primary tasks are:</span></span>

- <span data-ttu-id="0b920-225">이벤트 처리기를의 `MyControl1` `OnButtonClick` 이벤트에 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="0b920-225">Attaching an event handler to `MyControl1`'s `OnButtonClick` event.</span></span>

- <span data-ttu-id="0b920-226">옵션 단추의 컬렉션을 `MyControl1`설정 하는 방법에 따라의 다양 한 속성을 수정 합니다.</span><span class="sxs-lookup"><span data-stu-id="0b920-226">Modifying various properties of `MyControl1`, based on how the collection of option buttons are set.</span></span>

- <span data-ttu-id="0b920-227">컨트롤에서 수집한 데이터 표시.</span><span class="sxs-lookup"><span data-stu-id="0b920-227">Displaying the data collected by the control.</span></span>

#### <a name="initializing-the-application"></a><span data-ttu-id="0b920-228">애플리케이션 초기화</span><span class="sxs-lookup"><span data-stu-id="0b920-228">Initializing the Application</span></span>
 <span data-ttu-id="0b920-229">초기화 코드는 창의 <xref:System.Windows.FrameworkElement.Loaded> 이벤트에 대 한 이벤트 처리기에 포함 되 고 컨트롤의 `OnButtonClick` 이벤트에 이벤트 처리기를 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="0b920-229">The initialization code is contained in an event handler for the window's <xref:System.Windows.FrameworkElement.Loaded> event and attaches an event handler to the control's `OnButtonClick` event.</span></span>

 <span data-ttu-id="0b920-230">Mainwindow.xaml 또는 MainWindow.xaml.cs에서 다음 코드를 `MainWindow` 클래스에 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="0b920-230">In MainWindow.xaml.vb or MainWindow.xaml.cs, add the following code to the `MainWindow` class.</span></span>

 [!code-csharp[WpfHostingWindowsFormsControl#11](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/CSharp/WpfHost/Page1.xaml.cs#11)]
 [!code-vb[WpfHostingWindowsFormsControl#11](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/VisualBasic/WpfHost/Page1.xaml.vb#11)]

 <span data-ttu-id="0b920-231">앞에서 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 설명한가 <xref:System.Windows.Forms.Integration.WindowsFormsHost> 요소의 `MyControl1` `MyControl1` 자식요소<xref:System.Windows.Forms.Integration.WindowsFormsHost.Child%2A> 컬렉션에 추가 되었기 때문에에 대 한 참조를 가져오기 위해 요소의를캐스팅할수있습니다.<xref:System.Windows.Forms.Integration.WindowsFormsHost></span><span class="sxs-lookup"><span data-stu-id="0b920-231">Because the [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] discussed previously added `MyControl1` to the <xref:System.Windows.Forms.Integration.WindowsFormsHost> element's child element collection, you can cast the <xref:System.Windows.Forms.Integration.WindowsFormsHost> element's <xref:System.Windows.Forms.Integration.WindowsFormsHost.Child%2A> to get the reference to `MyControl1`.</span></span> <span data-ttu-id="0b920-232">그런 다음 해당 참조를 사용 하 여에 `OnButtonClick`이벤트 처리기를 연결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0b920-232">You can then use that reference to attach an event handler to `OnButtonClick`.</span></span>

 <span data-ttu-id="0b920-233">컨트롤 자체에 대 한 참조를 제공 하는 것 <xref:System.Windows.Forms.Integration.WindowsFormsHost> 외에도는 응용 프로그램에서 조작할 수 있는 다양 한 컨트롤 속성을 노출 합니다.</span><span class="sxs-lookup"><span data-stu-id="0b920-233">In addition to providing a reference to the control itself, <xref:System.Windows.Forms.Integration.WindowsFormsHost> exposes a number of the control's properties, which you can manipulate from the application.</span></span> <span data-ttu-id="0b920-234">초기화 코드는 나중에 애플리케이션에서 사용할 수 있도록 private 전역 변수에 해당 값을 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="0b920-234">The initialization code assigns those values to private global variables for later use in the application.</span></span>

 <span data-ttu-id="0b920-235">`MyControls` DLL의 형식에 쉽게 액세스할 수 있도록 파일의 맨 위에 다음 `Imports` 또는 `using` 문을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="0b920-235">So that you can easily access the types in the `MyControls` DLL, add the following `Imports` or `using` statement to the top of the file.</span></span>

```vb
Imports MyControls
```

```csharp
using MyControls;
```

#### <a name="handling-the-onbuttonclick-event"></a><span data-ttu-id="0b920-236">OnButtonClick 이벤트 처리</span><span class="sxs-lookup"><span data-stu-id="0b920-236">Handling the OnButtonClick Event</span></span>
 <span data-ttu-id="0b920-237">`MyControl1`사용자가 `OnButtonClick` 컨트롤의 단추 중 하나를 클릭 하면 이벤트를 발생 시킵니다.</span><span class="sxs-lookup"><span data-stu-id="0b920-237">`MyControl1` raises the `OnButtonClick` event when the user clicks either of the control's buttons.</span></span>

 <span data-ttu-id="0b920-238">`MainWindow` 클래스에 다음 코드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="0b920-238">Add the following code to the `MainWindow` class.</span></span>

 [!code-csharp[WpfHostingWindowsFormsControl#12](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/CSharp/WpfHost/Page1.xaml.cs#12)]
 [!code-vb[WpfHostingWindowsFormsControl#12](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/VisualBasic/WpfHost/Page1.xaml.vb#12)]

 <span data-ttu-id="0b920-239">텍스트 상자의 데이터는 `MyControlEventArgs` 개체에 압축 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0b920-239">The data in the text boxes is packed into the `MyControlEventArgs` object.</span></span> <span data-ttu-id="0b920-240">사용자가 **확인** 단추를 클릭 하면 이벤트 처리기가 데이터를 추출 하 여 아래 `MyControl1`패널에 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="0b920-240">If the user clicks the **OK** button, the event handler extracts the data and displays it in the panel below `MyControl1`.</span></span>

#### <a name="modifying-the-controls-properties"></a><span data-ttu-id="0b920-241">컨트롤의 속성 수정</span><span class="sxs-lookup"><span data-stu-id="0b920-241">Modifying the Control’s Properties</span></span>
 <span data-ttu-id="0b920-242">요소 <xref:System.Windows.Forms.Integration.WindowsFormsHost> 는 호스트 된 컨트롤의 몇 가지 기본 속성을 노출 합니다.</span><span class="sxs-lookup"><span data-stu-id="0b920-242">The <xref:System.Windows.Forms.Integration.WindowsFormsHost> element exposes several of the hosted control's default properties.</span></span> <span data-ttu-id="0b920-243">결과적으로 애플리케이션의 스타일과 더 가깝게 일치하도록 컨트롤의 모양을 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0b920-243">As a result, you can change the appearance of the control to match the style of your application more closely.</span></span> <span data-ttu-id="0b920-244">왼쪽 패널의 옵션 단추 집합을 사용하여 사용자는 여러 가지 색 및 글꼴 속성을 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0b920-244">The sets of option buttons in the left panel enable the user to modify several color and font properties.</span></span> <span data-ttu-id="0b920-245">각 단추 집합에는 <xref:System.Windows.Controls.Primitives.ButtonBase.Click> 이벤트에 대 한 처리기가 있으며 사용자의 옵션 단추 선택 항목을 검색 하 고 컨트롤의 해당 속성을 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="0b920-245">Each set of buttons has a handler for the <xref:System.Windows.Controls.Primitives.ButtonBase.Click> event, which detects the user's option button selections and changes the corresponding property on the control.</span></span>

 <span data-ttu-id="0b920-246">`MainWindow` 클래스에 다음 코드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="0b920-246">Add the following code to the `MainWindow` class.</span></span>

 [!code-csharp[WpfHostingWindowsFormsControl#13](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/CSharp/WpfHost/Page1.xaml.cs#13)]
 [!code-vb[WpfHostingWindowsFormsControl#13](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/VisualBasic/WpfHost/Page1.xaml.vb#13)]  
  
 <span data-ttu-id="0b920-247">애플리케이션을 빌드 및 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="0b920-247">Build and run the application.</span></span> <span data-ttu-id="0b920-248">Windows Forms 복합 컨트롤에 일부 텍스트를 추가한 다음 **확인**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="0b920-248">Add some text in the Windows Forms composite control and then click **OK**.</span></span> <span data-ttu-id="0b920-249">텍스트가 레이블에 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="0b920-249">The text appears in the labels.</span></span> <span data-ttu-id="0b920-250">컨트롤에 대한 효과를 확인하려면 다른 라디오 단추를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="0b920-250">Click the different radio buttons to see the effect on the control.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0b920-251">참고자료</span><span class="sxs-lookup"><span data-stu-id="0b920-251">See also</span></span>

- <xref:System.Windows.Forms.Integration.ElementHost>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [<span data-ttu-id="0b920-252">Visual Studio에서 XAML 디자인</span><span class="sxs-lookup"><span data-stu-id="0b920-252">Design XAML in Visual Studio</span></span>](/visualstudio/designers/designing-xaml-in-visual-studio)
- [<span data-ttu-id="0b920-253">연습: WPF에서 Windows Forms 컨트롤 호스팅</span><span class="sxs-lookup"><span data-stu-id="0b920-253">Walkthrough: Hosting a Windows Forms Control in WPF</span></span>](walkthrough-hosting-a-windows-forms-control-in-wpf.md)
- [<span data-ttu-id="0b920-254">연습: Windows Forms에서 WPF 복합 컨트롤 호스팅</span><span class="sxs-lookup"><span data-stu-id="0b920-254">Walkthrough: Hosting a WPF Composite Control in Windows Forms</span></span>](walkthrough-hosting-a-wpf-composite-control-in-windows-forms.md)
