---
title: '연습: 사용자 정의 컨트롤에서 끌어서 놓기 사용'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- walkthrough [WPF], drag-and-drop
- drag-and-drop [WPF], walkthrough
ms.assetid: cc844419-1a77-4906-95d9-060d79107fc7
ms.openlocfilehash: e151eb7f428fecb330970210fd7addb1603a211f
ms.sourcegitcommit: 5bbfe34a9a14e4ccb22367e57b57585c208cf757
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/18/2018
ms.locfileid: "45988714"
---
# <a name="walkthrough-enabling-drag-and-drop-on-a-user-control"></a><span data-ttu-id="a23ff-102">연습: 사용자 정의 컨트롤에서 끌어서 놓기 사용</span><span class="sxs-lookup"><span data-stu-id="a23ff-102">Walkthrough: Enabling Drag and Drop on a User Control</span></span>
<span data-ttu-id="a23ff-103">이 연습에서는 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]에서 끌어서 놓기 데이터 전송에 참가할 수 있는 사용자 지정 사용자 정의 컨트롤을 만드는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="a23ff-103">This walkthrough demonstrates how to create a custom user control that can participate in drag-and-drop data transfer in [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)].</span></span>  
  
 <span data-ttu-id="a23ff-104">이 연습에서는 사용자 지정 WPF 만들어집니다 <xref:System.Windows.Controls.UserControl> 원 모양을 나타내는입니다.</span><span class="sxs-lookup"><span data-stu-id="a23ff-104">In this walkthrough, you will create a custom WPF <xref:System.Windows.Controls.UserControl> that represents a circle shape.</span></span> <span data-ttu-id="a23ff-105">컨트롤에서 끌어서 놓기를 통해 데이터 전송을 활성화하는 기능을 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="a23ff-105">You will implement functionality on the control to enable data transfer through drag-and-drop.</span></span> <span data-ttu-id="a23ff-106">예를 들어 한 원 컨트롤에서 다른 원 컨트롤로 끌면 채우기 색 데이터가 소스 원에서 대상 원으로 복사됩니다.</span><span class="sxs-lookup"><span data-stu-id="a23ff-106">For example, if you drag from one Circle control to another, the Fill color data is copied from the source Circle to the target.</span></span> <span data-ttu-id="a23ff-107">원 컨트롤로 끌면를 <xref:System.Windows.Controls.TextBox>, 채우기 색의 문자열 표현에 복사 됩니다는 <xref:System.Windows.Controls.TextBox>합니다.</span><span class="sxs-lookup"><span data-stu-id="a23ff-107">If you drag from a Circle control to a <xref:System.Windows.Controls.TextBox>, the string representation of the Fill color is copied to the <xref:System.Windows.Controls.TextBox>.</span></span> <span data-ttu-id="a23ff-108">두 개의 패널 컨트롤을 포함 하는 작은 응용 프로그램을 만듭니다 및 <xref:System.Windows.Controls.TextBox> 끌어서 놓기 기능을 테스트 합니다.</span><span class="sxs-lookup"><span data-stu-id="a23ff-108">You will also create a small application that contains two panel controls and a <xref:System.Windows.Controls.TextBox> to test the drag-and-drop functionality.</span></span> <span data-ttu-id="a23ff-109">패널이 끌어 놓은 원 데이터를 처리하여 한 패널의 자식 컬렉션에서 다른 패널로 원을 이동하거나 복사할 수 있도록 하는 코드를 작성합니다.</span><span class="sxs-lookup"><span data-stu-id="a23ff-109">You will write code that enables the panels to process dropped Circle data, which will enable you to move or copy Circles from the Children collection of one panel to the other.</span></span>  
  
 <span data-ttu-id="a23ff-110">이 연습에서는 다음 작업을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="a23ff-110">This walkthrough illustrates the following tasks:</span></span>  
  
-   <span data-ttu-id="a23ff-111">사용자 지정 사용자 정의 컨트롤 만들기</span><span class="sxs-lookup"><span data-stu-id="a23ff-111">Create a custom user control.</span></span>  
  
-   <span data-ttu-id="a23ff-112">사용자 정의 컨트롤을 끌기 소스로 사용할 수 있도록 설정</span><span class="sxs-lookup"><span data-stu-id="a23ff-112">Enable the user control to be a drag source.</span></span>  
  
-   <span data-ttu-id="a23ff-113">사용자 정의 컨트롤을 놓기 대상으로 사용할 수 있도록 설정</span><span class="sxs-lookup"><span data-stu-id="a23ff-113">Enable the user control to be a drop target.</span></span>  
  
-   <span data-ttu-id="a23ff-114">패널이 사용자 정의 컨트롤에서 놓은 데이터를 받을 수 있도록 설정</span><span class="sxs-lookup"><span data-stu-id="a23ff-114">Enable a panel to receive data dropped from the user control.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="a23ff-115">전제 조건</span><span class="sxs-lookup"><span data-stu-id="a23ff-115">Prerequisites</span></span>  
 <span data-ttu-id="a23ff-116">이 연습을 완료하려면 다음 구성 요소가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="a23ff-116">You need the following components to complete this walkthrough:</span></span>  
  
-   <span data-ttu-id="a23ff-117">Visual Studio 2010</span><span class="sxs-lookup"><span data-stu-id="a23ff-117">Visual Studio 2010</span></span>  
  
## <a name="creating-the-application-project"></a><span data-ttu-id="a23ff-118">응용 프로그램 프로젝트 만들기</span><span class="sxs-lookup"><span data-stu-id="a23ff-118">Creating the Application Project</span></span>  
 <span data-ttu-id="a23ff-119">이 섹션에서는 두 개의 패널을 사용 하 여 기본 페이지를 포함 하는 응용 프로그램 인프라를 만들게 됩니다 및 <xref:System.Windows.Controls.TextBox>합니다.</span><span class="sxs-lookup"><span data-stu-id="a23ff-119">In this section, you will create the application infrastructure, which includes a main page with two panels and a <xref:System.Windows.Controls.TextBox>.</span></span>  
  
### <a name="to-create-the-project"></a><span data-ttu-id="a23ff-120">프로젝트를 만들려면</span><span class="sxs-lookup"><span data-stu-id="a23ff-120">To create the project</span></span>  
  
1.  <span data-ttu-id="a23ff-121">Visual Basic 또는 Visual C#에서 `DragDropExample`이라는 새 WPF 응용 프로그램 프로젝트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="a23ff-121">Create a new WPF Application project in Visual Basic or Visual C# named `DragDropExample`.</span></span> <span data-ttu-id="a23ff-122">자세한 내용은 [방법: 새 WPF 응용 프로그램 프로젝트 만들기](https://msdn.microsoft.com/library/1f6aea7a-33e1-4d3f-8555-1daa42e95d82)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="a23ff-122">For more information, see [How to: Create a New WPF Application Project](https://msdn.microsoft.com/library/1f6aea7a-33e1-4d3f-8555-1daa42e95d82).</span></span>  
  
2.  <span data-ttu-id="a23ff-123">MainWindow.xaml을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="a23ff-123">Open MainWindow.xaml.</span></span>  
  
3.  <span data-ttu-id="a23ff-124">태그와 닫는 사이 다음 태그를 추가 <xref:System.Windows.Controls.Grid> 태그입니다.</span><span class="sxs-lookup"><span data-stu-id="a23ff-124">Add the following markup between the opening and closing <xref:System.Windows.Controls.Grid> tags.</span></span>  
  
     <span data-ttu-id="a23ff-125">이 태그는 테스트 응용 프로그램에 대한 사용자 인터페이스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="a23ff-125">This markup creates the user interface for the test application.</span></span>  
  
     [!code-xaml[DragDropWalkthrough#PanelsStep1XAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/SnippetWindow.xaml#panelsstep1xaml)]  
  
## <a name="adding-a-new-user-control-to-the-project"></a><span data-ttu-id="a23ff-126">프로젝트에 새 사용자 정의 컨트롤 추가</span><span class="sxs-lookup"><span data-stu-id="a23ff-126">Adding a New User Control to the Project</span></span>  
 <span data-ttu-id="a23ff-127">이 섹션에서는 프로젝트에 새 사용자 정의 컨트롤을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="a23ff-127">In this section, you will add a new user control to the project.</span></span>  
  
### <a name="to-add-a-new-user-control"></a><span data-ttu-id="a23ff-128">새 사용자 정의 컨트롤을 추가하려면</span><span class="sxs-lookup"><span data-stu-id="a23ff-128">To add a new user control</span></span>  
  
1.  <span data-ttu-id="a23ff-129">[프로젝트] 메뉴에서 **사용자 정의 컨트롤 추가**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="a23ff-129">On the Project menu, select **Add User Control**.</span></span>  
  
2.  <span data-ttu-id="a23ff-130">[새 항목 추가] 대화 상자에서 이름을 `Circle.xaml`로 변경하고 **추가**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="a23ff-130">In the Add New Item dialog box, change the name to `Circle.xaml`, and click **Add**.</span></span>  
  
     <span data-ttu-id="a23ff-131">Circle.xaml과 해당 코드 숨김이 프로젝트에 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="a23ff-131">Circle.xaml and its code-behind is added to the project.</span></span>  
  
3.  <span data-ttu-id="a23ff-132">Circle.xaml을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="a23ff-132">Open Circle.xaml.</span></span>  
  
     <span data-ttu-id="a23ff-133">이 파일에는 사용자 정의 컨트롤의 사용자 인터페이스 요소가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="a23ff-133">This file will contain the user interface elements of the user control.</span></span>  
  
4.  <span data-ttu-id="a23ff-134">루트에 다음 태그를 추가 <xref:System.Windows.Controls.Grid> 파란색 원을 UI로 된 간단한 사용자 컨트롤을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="a23ff-134">Add the following markup to the root <xref:System.Windows.Controls.Grid> to create a simple user control that has a blue circle as its UI.</span></span>  
  
     [!code-xaml[DragDropWalkthrough#EllipseXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/Circle.xaml#ellipsexaml)]  
  
5.  <span data-ttu-id="a23ff-135">Circle.xaml.cs 또는 Circle.xaml.vb를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="a23ff-135">Open Circle.xaml.cs or Circle.xaml.vb.</span></span>  
  
6.  <span data-ttu-id="a23ff-136">C#에서는 기본 생성자 뒤에 다음 코드를 추가하여 복사 생성자를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="a23ff-136">In C#, add the following code after the default constructor to create a copy constructor.</span></span> <span data-ttu-id="a23ff-137">Visual Basic에서는 다음 코드를 추가하여 기본 생성자와 복사 생성자를 모두 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="a23ff-137">In Visual Basic, add the following code to create both a default constructor and a copy constructor.</span></span>  
  
     <span data-ttu-id="a23ff-138">사용자 정의 컨트롤을 복사할 수 있도록 하려면 코드 숨김 파일에서 복사 생성자 메서드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="a23ff-138">In order to allow the user control to be copied, you add a copy constructor method in the code-behind file.</span></span> <span data-ttu-id="a23ff-139">간단한 원 사용자 정의 컨트롤에서 사용자 정의 컨트롤의 채우기와 크기만 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="a23ff-139">In the simplified Circle user control, you will only copy the Fill and the size of the of the user control.</span></span>  
  
     [!code-csharp[DragDropWalkthrough#CopyCtor](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/Circle.xaml.cs#copyctor)]
     [!code-vb[DragDropWalkthrough#CopyCtor](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DragDropWalkthrough/VB/Circle.xaml.vb#copyctor)]  
  
### <a name="to-add-the-user-control-to-the-main-window"></a><span data-ttu-id="a23ff-140">주 창에 사용자 정의 컨트롤을 추가하려면</span><span class="sxs-lookup"><span data-stu-id="a23ff-140">To add the user control to the main window</span></span>  
  
1.  <span data-ttu-id="a23ff-141">MainWindow.xaml을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="a23ff-141">Open MainWindow.xaml.</span></span>  
  
2.  <span data-ttu-id="a23ff-142">다음 XAML을 여는 추가 <xref:System.Windows.Window> 현재 응용 프로그램에 대 한 XML 네임 스페이스 참조를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="a23ff-142">Add the following XAML to the opening <xref:System.Windows.Window> tag to create an XML namespace reference to the current application.</span></span>  
  
    ```  
    xmlns:local="clr-namespace:DragDropExample"  
    ```  
  
3.  <span data-ttu-id="a23ff-143">첫 번째에서 <xref:System.Windows.Controls.StackPanel>, 첫 번째 패널에서 원 사용자 정의 컨트롤의 두 인스턴스를 만들려면 다음 XAML을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="a23ff-143">In the first <xref:System.Windows.Controls.StackPanel>, add the following XAML to create two instances of the Circle user control in the first panel.</span></span>  
  
     [!code-xaml[DragDropWalkthrough#CirclesXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/SnippetWindow.xaml#circlesxaml)]  
  
     <span data-ttu-id="a23ff-144">패널에 대한 전체 XAML은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="a23ff-144">The full XAML for the panel looks like the following.</span></span>  
  
     [!code-xaml[DragDropWalkthrough#PanelsStep2XAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/SnippetWindow.xaml#panelsstep2xaml)]  
  
## <a name="implementing-drag-source-events-in-the-user-control"></a><span data-ttu-id="a23ff-145">사용자 정의 컨트롤에서 끌기 소스 이벤트 구현</span><span class="sxs-lookup"><span data-stu-id="a23ff-145">Implementing Drag Source Events in the User Control</span></span>  
 <span data-ttu-id="a23ff-146">이 섹션에서는 재정의 <xref:System.Windows.UIElement.OnMouseMove%2A> 메서드 및 끌어서 놓기 작업을 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="a23ff-146">In this section, you will override the <xref:System.Windows.UIElement.OnMouseMove%2A> method and initiate the drag-and-drop operation.</span></span>  
  
 <span data-ttu-id="a23ff-147">끌기가 시작 되 면 (마우스 단추를 누르면 및 마우스 이동)에 전송할 데이터 패키지는 <xref:System.Windows.DataObject>합니다.</span><span class="sxs-lookup"><span data-stu-id="a23ff-147">If a drag is started (a mouse button is pressed and the mouse is moved), you will package the data to be transferred into a <xref:System.Windows.DataObject>.</span></span> <span data-ttu-id="a23ff-148">이 경우 원 컨트롤은 채우기 색의 문자열 표현, 높이의 double 표현과 자신의 복사본이라는 세 개의 데이터 항목을 패키지합니다.</span><span class="sxs-lookup"><span data-stu-id="a23ff-148">In this case, the Circle control will package three data items; a string representation of its Fill color, a double representation of its height, and a copy of itself.</span></span>  
  
### <a name="to-initiate-a-drag-and-drop-operation"></a><span data-ttu-id="a23ff-149">끌어서 놓기 작업을 시작하려면</span><span class="sxs-lookup"><span data-stu-id="a23ff-149">To initiate a drag-and-drop operation</span></span>  
  
1.  <span data-ttu-id="a23ff-150">Circle.xaml.cs 또는 Circle.xaml.vb를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="a23ff-150">Open Circle.xaml.cs or Circle.xaml.vb.</span></span>  
  
2.  <span data-ttu-id="a23ff-151">다음을 추가 합니다 <xref:System.Windows.UIElement.OnMouseMove%2A> 클래스에 대 한 처리를 제공 하는 재정의 <xref:System.Windows.UIElement.MouseMove> 이벤트입니다.</span><span class="sxs-lookup"><span data-stu-id="a23ff-151">Add the following <xref:System.Windows.UIElement.OnMouseMove%2A> override to provide class handling for the <xref:System.Windows.UIElement.MouseMove> event.</span></span>  
  
     [!code-csharp[DragDropWalkthrough#OnMouseMove](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/Circle.xaml.cs#onmousemove)]
     [!code-vb[DragDropWalkthrough#OnMouseMove](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DragDropWalkthrough/VB/Circle.xaml.vb#onmousemove)]  
  
     <span data-ttu-id="a23ff-152">이 <xref:System.Windows.UIElement.OnMouseMove%2A> 재정의 다음 작업을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="a23ff-152">This <xref:System.Windows.UIElement.OnMouseMove%2A> override performs the following tasks:</span></span>  
  
    -   <span data-ttu-id="a23ff-153">마우스를 이동하는 동안 마우스 왼쪽 단추를 눌렀는지 여부를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="a23ff-153">Checks whether the left mouse button is pressed while the mouse is moving.</span></span>  
  
    -   <span data-ttu-id="a23ff-154">원 데이터를 패키지는 <xref:System.Windows.DataObject>합니다.</span><span class="sxs-lookup"><span data-stu-id="a23ff-154">Packages the Circle data into a <xref:System.Windows.DataObject>.</span></span> <span data-ttu-id="a23ff-155">이 경우 원 컨트롤은 채우기 색의 문자열 표현, 높이의 double 표현과 자신의 복사본이라는 세 개의 데이터 항목을 패키지합니다.</span><span class="sxs-lookup"><span data-stu-id="a23ff-155">In this case, the Circle control packages three data items; a string representation of its Fill color, a double representation of its height, and a copy of itself.</span></span>  
  
    -   <span data-ttu-id="a23ff-156">정적 호출 <xref:System.Windows.DragDrop.DoDragDrop%2A?displayProperty=nameWithType> 끌어서 놓기 작업을 시작 하는 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="a23ff-156">Calls the static <xref:System.Windows.DragDrop.DoDragDrop%2A?displayProperty=nameWithType> method to initiate the drag-and-drop operation.</span></span> <span data-ttu-id="a23ff-157">다음 세 가지 매개 변수를 전달 합니다 <xref:System.Windows.DragDrop.DoDragDrop%2A> 메서드:</span><span class="sxs-lookup"><span data-stu-id="a23ff-157">You pass the following three parameters to the <xref:System.Windows.DragDrop.DoDragDrop%2A> method:</span></span>  
  
        -   <span data-ttu-id="a23ff-158">`dragSource` – 이 컨트롤에 대한 참조입니다.</span><span class="sxs-lookup"><span data-stu-id="a23ff-158">`dragSource` – A reference to this control.</span></span>  
  
        -   <span data-ttu-id="a23ff-159">`data` – <xref:System.Windows.DataObject> 이전 코드에서 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="a23ff-159">`data` – The <xref:System.Windows.DataObject> created in the previous code.</span></span>  
  
        -   <span data-ttu-id="a23ff-160">`allowedEffects` -허용 된 끌어서 놓기 작업으로, <xref:System.Windows.DragDropEffects.Copy> 또는 <xref:System.Windows.DragDropEffects.Move>합니다.</span><span class="sxs-lookup"><span data-stu-id="a23ff-160">`allowedEffects` – The allowed drag-and-drop operations, which are <xref:System.Windows.DragDropEffects.Copy> or <xref:System.Windows.DragDropEffects.Move>.</span></span>  
  
3.  <span data-ttu-id="a23ff-161">F5 키를 눌러 응용 프로그램을 빌드하고 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="a23ff-161">Press F5 to build and run the application.</span></span>  
  
4.  <span data-ttu-id="a23ff-162">원 컨트롤 중 하나를 클릭 하 고 패널, 다른 원 위로 끌어 및 <xref:System.Windows.Controls.TextBox>합니다.</span><span class="sxs-lookup"><span data-stu-id="a23ff-162">Click one of the Circle controls and drag it over the panels, the other Circle, and the <xref:System.Windows.Controls.TextBox>.</span></span> <span data-ttu-id="a23ff-163">위로 끌 때는 <xref:System.Windows.Controls.TextBox>, 이동을 나타내도록 커서가 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="a23ff-163">When dragging over the <xref:System.Windows.Controls.TextBox>, the cursor changes to indicate a move.</span></span>  
  
5.  <span data-ttu-id="a23ff-164">원 위로 끌어 하는 동안는 <xref:System.Windows.Controls.TextBox>, CTRL 키를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="a23ff-164">While dragging a Circle over the <xref:System.Windows.Controls.TextBox>, press the CTRL key.</span></span> <span data-ttu-id="a23ff-165">복사를 나타내기 위해 커서가 어떻게 변경되는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="a23ff-165">Notice how the cursor changes to indicate a copy.</span></span>  
  
6.  <span data-ttu-id="a23ff-166">끌어서 놓기에 원은 <xref:System.Windows.Controls.TextBox>합니다.</span><span class="sxs-lookup"><span data-stu-id="a23ff-166">Drag and drop a Circle onto the <xref:System.Windows.Controls.TextBox>.</span></span> <span data-ttu-id="a23ff-167">원 채우기 색의 문자열 표현에 추가 되는 <xref:System.Windows.Controls.TextBox>합니다.</span><span class="sxs-lookup"><span data-stu-id="a23ff-167">The string representation of the Circle’s fill color is appended to the <xref:System.Windows.Controls.TextBox>.</span></span>  
  
     <span data-ttu-id="a23ff-168">![원 채우기 색의 문자열 표현](../../../../docs/framework/wpf/advanced/media/dragdrop-colorstring.png "DragDrop_ColorString")</span><span class="sxs-lookup"><span data-stu-id="a23ff-168">![String representation of Circle's fill color](../../../../docs/framework/wpf/advanced/media/dragdrop-colorstring.png "DragDrop_ColorString")</span></span>  
  
 <span data-ttu-id="a23ff-169">기본적으로 커서는 끌어서 놓기 작업 중 데이터 놓기의 결과를 나타내도록 변경됩니다.</span><span class="sxs-lookup"><span data-stu-id="a23ff-169">By default, the cursor will change during a drag-and-drop operation to indicate what effect dropping the data will have.</span></span> <span data-ttu-id="a23ff-170">처리 하 여 사용자에 게 제공 되는 피드백을 사용자 지정할 수는 <xref:System.Windows.UIElement.GiveFeedback> 이벤트 및 다른 커서를 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="a23ff-170">You can customize the feedback given to the user by handling the <xref:System.Windows.UIElement.GiveFeedback> event and setting a different cursor.</span></span>  
  
### <a name="to-give-feedback-to-the-user"></a><span data-ttu-id="a23ff-171">사용자에게 피드백을 제공하려면</span><span class="sxs-lookup"><span data-stu-id="a23ff-171">To give feedback to the user</span></span>  
  
1.  <span data-ttu-id="a23ff-172">Circle.xaml.cs 또는 Circle.xaml.vb를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="a23ff-172">Open Circle.xaml.cs or Circle.xaml.vb.</span></span>  
  
2.  <span data-ttu-id="a23ff-173">다음을 추가 합니다 <xref:System.Windows.UIElement.OnGiveFeedback%2A> 클래스에 대 한 처리를 제공 하는 재정의 <xref:System.Windows.UIElement.GiveFeedback> 이벤트입니다.</span><span class="sxs-lookup"><span data-stu-id="a23ff-173">Add the following <xref:System.Windows.UIElement.OnGiveFeedback%2A> override to provide class handling for the <xref:System.Windows.UIElement.GiveFeedback> event.</span></span>  
  
     [!code-csharp[DragDropWalkthrough#OnGiveFeedback](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/Circle.xaml.cs#ongivefeedback)]
     [!code-vb[DragDropWalkthrough#OnGiveFeedback](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DragDropWalkthrough/VB/Circle.xaml.vb#ongivefeedback)]  
  
     <span data-ttu-id="a23ff-174">이 <xref:System.Windows.UIElement.OnGiveFeedback%2A> 재정의 다음 작업을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="a23ff-174">This <xref:System.Windows.UIElement.OnGiveFeedback%2A> override performs the following tasks:</span></span>  
  
    -   <span data-ttu-id="a23ff-175">확인 합니다 <xref:System.Windows.GiveFeedbackEventArgs.Effects%2A> 놓기 대상에서 설정 된 값 <xref:System.Windows.UIElement.DragOver> 이벤트 처리기입니다.</span><span class="sxs-lookup"><span data-stu-id="a23ff-175">Checks the <xref:System.Windows.GiveFeedbackEventArgs.Effects%2A> values that are set in the drop target's <xref:System.Windows.UIElement.DragOver> event handler.</span></span>  
  
    -   <span data-ttu-id="a23ff-176">설정에 따라 사용자 지정 커서를 <xref:System.Windows.GiveFeedbackEventArgs.Effects%2A> 값입니다.</span><span class="sxs-lookup"><span data-stu-id="a23ff-176">Sets a custom cursor based on the <xref:System.Windows.GiveFeedbackEventArgs.Effects%2A> value.</span></span> <span data-ttu-id="a23ff-177">커서는 데이터 놓기의 결과에 대한 시각적 피드백을 사용자에게 제공하기 위한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="a23ff-177">The cursor is intended to give visual feedback to the user about what effect dropping the data will have.</span></span>  
  
3.  <span data-ttu-id="a23ff-178">F5 키를 눌러 응용 프로그램을 빌드하고 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="a23ff-178">Press F5 to build and run the application.</span></span>  
  
4.  <span data-ttu-id="a23ff-179">패널, 다른 원 제어할 원 중 하나는 끌어서 및 <xref:System.Windows.Controls.TextBox>합니다.</span><span class="sxs-lookup"><span data-stu-id="a23ff-179">Drag one of the Circle controls over the panels, the other Circle, and the <xref:System.Windows.Controls.TextBox>.</span></span> <span data-ttu-id="a23ff-180">커서는에 지정 된 사용자 지정 커서 이제는 <xref:System.Windows.UIElement.OnGiveFeedback%2A> 재정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="a23ff-180">Notice that the cursors are now the custom cursors that you specified in the <xref:System.Windows.UIElement.OnGiveFeedback%2A> override.</span></span>  
  
     <span data-ttu-id="a23ff-181">![사용자 지정 커서로 끌어서 놓기](../../../../docs/framework/wpf/advanced/media/dragdrop-customcursor.png "DragDrop_CustomCursor")</span><span class="sxs-lookup"><span data-stu-id="a23ff-181">![Drag and drop with custom cursors](../../../../docs/framework/wpf/advanced/media/dragdrop-customcursor.png "DragDrop_CustomCursor")</span></span>  
  
5.  <span data-ttu-id="a23ff-182">텍스트 선택 `green` 에서 <xref:System.Windows.Controls.TextBox>합니다.</span><span class="sxs-lookup"><span data-stu-id="a23ff-182">Select the text `green` from the <xref:System.Windows.Controls.TextBox>.</span></span>  
  
6.  <span data-ttu-id="a23ff-183">`green` 텍스트를 원 컨트롤로 끕니다.</span><span class="sxs-lookup"><span data-stu-id="a23ff-183">Drag the `green` text to a Circle control.</span></span> <span data-ttu-id="a23ff-184">기본 커서가 끌어서 놓기 작업의 결과를 나타내도록 표시되는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="a23ff-184">Notice that the default cursors are shown to indicate the effects of the drag-and-drop operation.</span></span> <span data-ttu-id="a23ff-185">피드백 커서는 항상 끌기 소스에 의해 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="a23ff-185">The feedback cursor is always set by the drag source.</span></span>  
  
## <a name="implementing-drop-target-events-in-the-user-control"></a><span data-ttu-id="a23ff-186">사용자 정의 컨트롤에서 놓기 대상 이벤트 구현</span><span class="sxs-lookup"><span data-stu-id="a23ff-186">Implementing Drop Target Events in the User Control</span></span>  
 <span data-ttu-id="a23ff-187">이 섹션에서는 사용자 정의 컨트롤이 놓기 대상이 되도록 지정하고, 사용자 정의 컨트롤을 놓기 대상으로 사용할 수 있도록 설정하는 메서드를 재정의하며, 대상에 끌어 놓은 데이터를 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="a23ff-187">In this section, you will specify that the user control is a drop target, override the methods that enable the user control to be a drop target, and process the data that is dropped on it.</span></span>  
  
### <a name="to-enable-the-user-control-to-be-a-drop-target"></a><span data-ttu-id="a23ff-188">사용자 정의 컨트롤을 놓기 대상으로 사용할 수 있도록 설정하려면</span><span class="sxs-lookup"><span data-stu-id="a23ff-188">To enable the user control to be a drop target</span></span>  
  
1.  <span data-ttu-id="a23ff-189">Circle.xaml을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="a23ff-189">Open Circle.xaml.</span></span>  
  
2.  <span data-ttu-id="a23ff-190">여에서 <xref:System.Windows.Controls.UserControl> 태그를 추가 합니다 <xref:System.Windows.UIElement.AllowDrop%2A> 속성으로 설정 하 고 `true`.</span><span class="sxs-lookup"><span data-stu-id="a23ff-190">In the opening <xref:System.Windows.Controls.UserControl> tag, add the <xref:System.Windows.UIElement.AllowDrop%2A> property and set it to `true`.</span></span>  
  
     [!code-xaml[DragDropWalkthrough#UCTagXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/Circle.xaml#uctagxaml)]  
  
 <span data-ttu-id="a23ff-191"><xref:System.Windows.UIElement.OnDrop%2A> 메서드를 호출한 경우 합니다 <xref:System.Windows.UIElement.AllowDrop%2A> 속성이 `true` 끌기 원본에서 데이터를 원 사용자 정의 컨트롤에서 삭제 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a23ff-191">The <xref:System.Windows.UIElement.OnDrop%2A> method is called when the <xref:System.Windows.UIElement.AllowDrop%2A> property is set to `true` and data from the drag source is dropped on the Circle user control.</span></span> <span data-ttu-id="a23ff-192">이 메서드에서는 끌어 놓은 데이터를 처리하고 해당 데이터를 원에 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="a23ff-192">In this method, you will process the data that was dropped and apply the data to the Circle.</span></span>  
  
### <a name="to-process-the-dropped-data"></a><span data-ttu-id="a23ff-193">끌어 놓은 데이터를 처리하려면</span><span class="sxs-lookup"><span data-stu-id="a23ff-193">To process the dropped data</span></span>  
  
1.  <span data-ttu-id="a23ff-194">Circle.xaml.cs 또는 Circle.xaml.vb를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="a23ff-194">Open Circle.xaml.cs or Circle.xaml.vb.</span></span>  
  
2.  <span data-ttu-id="a23ff-195">다음을 추가 합니다 <xref:System.Windows.UIElement.OnDrop%2A> 클래스에 대 한 처리를 제공 하는 재정의 <xref:System.Windows.UIElement.Drop> 이벤트입니다.</span><span class="sxs-lookup"><span data-stu-id="a23ff-195">Add the following <xref:System.Windows.UIElement.OnDrop%2A> override to provide class handling for the <xref:System.Windows.UIElement.Drop> event.</span></span>  
  
     [!code-csharp[DragDropWalkthrough#OnDrop](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/Circle.xaml.cs#ondrop)]
     [!code-vb[DragDropWalkthrough#OnDrop](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DragDropWalkthrough/VB/Circle.xaml.vb#ondrop)]  
  
     <span data-ttu-id="a23ff-196">이 <xref:System.Windows.UIElement.OnDrop%2A> 재정의 다음 작업을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="a23ff-196">This <xref:System.Windows.UIElement.OnDrop%2A> override performs the following tasks:</span></span>  
  
    -   <span data-ttu-id="a23ff-197">사용 하 여 <xref:System.Windows.DataObject.GetDataPresent%2A> 문자열 개체를 끌어 온된 데이터에 포함 되어 있는지 확인 하는 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="a23ff-197">Uses the <xref:System.Windows.DataObject.GetDataPresent%2A> method to check if the dragged data contains a string object.</span></span>  
  
    -   <span data-ttu-id="a23ff-198">사용 하 여 <xref:System.Windows.DataObject.GetData%2A> 있는 경우 문자열 데이터를 추출 하는 방법.</span><span class="sxs-lookup"><span data-stu-id="a23ff-198">Uses the <xref:System.Windows.DataObject.GetData%2A> method to extract the string data if it is present.</span></span>  
  
    -   <span data-ttu-id="a23ff-199">사용 하는 <xref:System.Windows.Media.BrushConverter> 문자열을 변환 하려고를 <xref:System.Windows.Media.Brush>입니다.</span><span class="sxs-lookup"><span data-stu-id="a23ff-199">Uses a <xref:System.Windows.Media.BrushConverter> to try to convert the string to a <xref:System.Windows.Media.Brush>.</span></span>  
  
    -   <span data-ttu-id="a23ff-200">변환이 성공한 경우에 브러시를 적용 합니다 <xref:System.Windows.Shapes.Shape.Fill%2A> 의 <xref:System.Windows.Shapes.Ellipse> 원 컨트롤의 UI를 제공 하는 합니다.</span><span class="sxs-lookup"><span data-stu-id="a23ff-200">If the conversion is successful, applies the brush to the <xref:System.Windows.Shapes.Shape.Fill%2A> of the <xref:System.Windows.Shapes.Ellipse> that provides the UI of the Circle control.</span></span>  
  
    -   <span data-ttu-id="a23ff-201">표시 된 <xref:System.Windows.UIElement.Drop> 이벤트를 처리 합니다.</span><span class="sxs-lookup"><span data-stu-id="a23ff-201">Marks the <xref:System.Windows.UIElement.Drop> event as handled.</span></span> <span data-ttu-id="a23ff-202">이 이벤트를 수신하는 다른 요소가 원 사용자 정의 컨트롤에서 해당 이벤트를 처리했음을 알 수 있도록 놓기 이벤트를 처리된 것으로 표시해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a23ff-202">You should mark the drop event as handled so that other elements that receive this event know that the Circle user control handled it.</span></span>  
  
3.  <span data-ttu-id="a23ff-203">F5 키를 눌러 응용 프로그램을 빌드하고 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="a23ff-203">Press F5 to build and run the application.</span></span>  
  
4.  <span data-ttu-id="a23ff-204">텍스트 선택 `green` 에 <xref:System.Windows.Controls.TextBox>합니다.</span><span class="sxs-lookup"><span data-stu-id="a23ff-204">Select the text `green` in the <xref:System.Windows.Controls.TextBox>.</span></span>  
  
5.  <span data-ttu-id="a23ff-205">텍스트를 원 컨트롤로 끌어서 놓습니다.</span><span class="sxs-lookup"><span data-stu-id="a23ff-205">Drag the text to a Circle control and drop it.</span></span> <span data-ttu-id="a23ff-206">원이 파란색에서 녹색으로 바뀝니다.</span><span class="sxs-lookup"><span data-stu-id="a23ff-206">The Circle changes from blue to green.</span></span>  
  
     <span data-ttu-id="a23ff-207">![문자열을 브러시로 변환](../../../../docs/framework/wpf/advanced/media/dragdrop-dropgreentext.png "DragDrop_DropGreenText")</span><span class="sxs-lookup"><span data-stu-id="a23ff-207">![Convert a string to a brush](../../../../docs/framework/wpf/advanced/media/dragdrop-dropgreentext.png "DragDrop_DropGreenText")</span></span>  
  
6.  <span data-ttu-id="a23ff-208">텍스트 입력 `green` 에 <xref:System.Windows.Controls.TextBox>합니다.</span><span class="sxs-lookup"><span data-stu-id="a23ff-208">Type the text `green` in the <xref:System.Windows.Controls.TextBox>.</span></span>  
  
7.  <span data-ttu-id="a23ff-209">텍스트 선택 `gre` 에 <xref:System.Windows.Controls.TextBox>합니다.</span><span class="sxs-lookup"><span data-stu-id="a23ff-209">Select the text `gre` in the <xref:System.Windows.Controls.TextBox>.</span></span>  
  
8.  <span data-ttu-id="a23ff-210">이 텍스트를 원 컨트롤로 끌어서 놓습니다.</span><span class="sxs-lookup"><span data-stu-id="a23ff-210">Drag it to a Circle control and drop it.</span></span> <span data-ttu-id="a23ff-211">놓기가 허용됨을 나타내도록 커서가 변경되지만 `gre`가 유효한 색이 아니기 때문에 원의 색은 변경되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a23ff-211">Notice that the cursor changes to indicate that the drop is allowed, but the color of the Circle does not change because `gre` is not a valid color.</span></span>  
  
9. <span data-ttu-id="a23ff-212">녹색 원 컨트롤에서 끌어서 파란색 원 컨트롤에 놓습니다.</span><span class="sxs-lookup"><span data-stu-id="a23ff-212">Drag from the green Circle control and drop on the blue Circle control.</span></span> <span data-ttu-id="a23ff-213">원이 파란색에서 녹색으로 바뀝니다.</span><span class="sxs-lookup"><span data-stu-id="a23ff-213">The Circle changes from blue to green.</span></span> <span data-ttu-id="a23ff-214">표시 되는 커서 인지 여부에 따라 달라 지는 공지를 <xref:System.Windows.Controls.TextBox> 원 끌기 소스 또는 합니다.</span><span class="sxs-lookup"><span data-stu-id="a23ff-214">Notice that which cursor is shown depends on whether the <xref:System.Windows.Controls.TextBox> or the Circle is the drag source.</span></span>  
  
 <span data-ttu-id="a23ff-215">설정 된 <xref:System.Windows.UIElement.AllowDrop%2A> 속성을 `true` 놓기 대상이 될 요소를 사용 하도록 설정 하는 데 필요한 모든는 끌어 놓은 데이터를 처리 합니다.</span><span class="sxs-lookup"><span data-stu-id="a23ff-215">Setting the <xref:System.Windows.UIElement.AllowDrop%2A> property to `true` and processing the dropped data is all that is required to enable an element to be a drop target.</span></span> <span data-ttu-id="a23ff-216">그러나 더 나은 사용자 환경을 위해 처리 해야 합니다 <xref:System.Windows.UIElement.DragEnter>, <xref:System.Windows.UIElement.DragLeave>, 및 <xref:System.Windows.UIElement.DragOver> 이벤트입니다.</span><span class="sxs-lookup"><span data-stu-id="a23ff-216">However, to provide a better user experience, you should also handle the <xref:System.Windows.UIElement.DragEnter>, <xref:System.Windows.UIElement.DragLeave>, and <xref:System.Windows.UIElement.DragOver> events.</span></span> <span data-ttu-id="a23ff-217">이러한 이벤트에서 데이터를 놓기 전에 검사를 수행하고 사용자에게 추가 피드백을 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a23ff-217">In these events, you can perform checks and provide additional feedback to the user before the data is dropped.</span></span>  
  
 <span data-ttu-id="a23ff-218">데이터를 원 사용자 정의 컨트롤로 끌면 컨트롤에서 끌고 있는 데이터를 처리할 수 있는지 여부를 끌기 소스에 알려야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a23ff-218">When data is dragged over the Circle user control, the control should notify the drag source whether it can process the data that is being dragged.</span></span> <span data-ttu-id="a23ff-219">컨트롤에서 데이터 처리 방법을 알지 못하는 경우 놓기를 거부해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a23ff-219">If the control does not know how to process the data, it should refuse the drop.</span></span> <span data-ttu-id="a23ff-220">처리 하는이 작업을 수행 하는 <xref:System.Windows.UIElement.DragOver> 이벤트 집합과 <xref:System.Windows.DragEventArgs.Effects%2A> 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="a23ff-220">To do this, you will handle the <xref:System.Windows.UIElement.DragOver> event and set the <xref:System.Windows.DragEventArgs.Effects%2A> property.</span></span>  
  
### <a name="to-verify-that-the-data-drop-is-allowed"></a><span data-ttu-id="a23ff-221">데이터 놓기가 허용되는지 확인하려면</span><span class="sxs-lookup"><span data-stu-id="a23ff-221">To verify that the data drop is allowed</span></span>  
  
1.  <span data-ttu-id="a23ff-222">Circle.xaml.cs 또는 Circle.xaml.vb를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="a23ff-222">Open Circle.xaml.cs or Circle.xaml.vb.</span></span>  
  
2.  <span data-ttu-id="a23ff-223">다음을 추가 합니다 <xref:System.Windows.UIElement.OnDragOver%2A> 클래스에 대 한 처리를 제공 하는 재정의 <xref:System.Windows.UIElement.DragOver> 이벤트입니다.</span><span class="sxs-lookup"><span data-stu-id="a23ff-223">Add the following <xref:System.Windows.UIElement.OnDragOver%2A> override to provide class handling for the <xref:System.Windows.UIElement.DragOver> event.</span></span>  
  
     [!code-csharp[DragDropWalkthrough#OnDragOver](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/Circle.xaml.cs#ondragover)]
     [!code-vb[DragDropWalkthrough#OnDragOver](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DragDropWalkthrough/VB/Circle.xaml.vb#ondragover)]  
  
     <span data-ttu-id="a23ff-224">이 <xref:System.Windows.UIElement.OnDragOver%2A> 재정의 다음 작업을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="a23ff-224">This <xref:System.Windows.UIElement.OnDragOver%2A> override performs the following tasks:</span></span>  
  
    -   <span data-ttu-id="a23ff-225"><xref:System.Windows.DragEventArgs.Effects%2A> 속성을 <xref:System.Windows.DragDropEffects.None>로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="a23ff-225">Sets the <xref:System.Windows.DragEventArgs.Effects%2A> property to <xref:System.Windows.DragDropEffects.None>.</span></span>  
  
    -   <span data-ttu-id="a23ff-226">수행 되는 동일한 검사를 수행 합니다 <xref:System.Windows.UIElement.OnDrop%2A> 원 사용자 정의 컨트롤로 끌어 온된 데이터를 처리할 수 있는지 여부를 결정 하는 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="a23ff-226">Performs the same checks that are performed in the <xref:System.Windows.UIElement.OnDrop%2A> method to determine whether the Circle user control can process the dragged data.</span></span>  
  
    -   <span data-ttu-id="a23ff-227">사용자 정의 컨트롤에 데이터를 처리할 수를 설정 합니다 <xref:System.Windows.DragEventArgs.Effects%2A> 속성을 <xref:System.Windows.DragDropEffects.Copy> 또는 <xref:System.Windows.DragDropEffects.Move>합니다.</span><span class="sxs-lookup"><span data-stu-id="a23ff-227">If the user control can process the data, sets the <xref:System.Windows.DragEventArgs.Effects%2A> property to <xref:System.Windows.DragDropEffects.Copy> or <xref:System.Windows.DragDropEffects.Move>.</span></span>  
  
3.  <span data-ttu-id="a23ff-228">F5 키를 눌러 응용 프로그램을 빌드하고 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="a23ff-228">Press F5 to build and run the application.</span></span>  
  
4.  <span data-ttu-id="a23ff-229">텍스트 선택 `gre` 에 <xref:System.Windows.Controls.TextBox>합니다.</span><span class="sxs-lookup"><span data-stu-id="a23ff-229">Select the text `gre` in the <xref:System.Windows.Controls.TextBox>.</span></span>  
  
5.  <span data-ttu-id="a23ff-230">텍스트를 원 컨트롤로 끕니다.</span><span class="sxs-lookup"><span data-stu-id="a23ff-230">Drag the text to a Circle control.</span></span> <span data-ttu-id="a23ff-231">`gre`가 유효한 색이 아니므로 놓기가 허용되지 않음을 나타내도록 커서가 변경됩니다.</span><span class="sxs-lookup"><span data-stu-id="a23ff-231">Notice that the cursor now changes to indicate that the drop is not allowed because `gre` is not a valid color.</span></span>  
  
 <span data-ttu-id="a23ff-232">놓기 작업의 미리 보기를 적용하여 사용자 환경을 더욱 향상시킬 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a23ff-232">You can further enhance the user experience by applying a preview of the drop operation.</span></span> <span data-ttu-id="a23ff-233">원 사용자 정의 컨트롤에 대 한 재정의 <xref:System.Windows.UIElement.OnDragEnter%2A> 고 <xref:System.Windows.UIElement.OnDragLeave%2A> 메서드.</span><span class="sxs-lookup"><span data-stu-id="a23ff-233">For the Circle user control, you will override the <xref:System.Windows.UIElement.OnDragEnter%2A> and <xref:System.Windows.UIElement.OnDragLeave%2A> methods.</span></span> <span data-ttu-id="a23ff-234">데이터 컨트롤에 현재 배경 위로 끌 때 <xref:System.Windows.Shapes.Shape.Fill%2A> 자리 표시자 변수에 저장 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a23ff-234">When the data is dragged over the control, the current background <xref:System.Windows.Shapes.Shape.Fill%2A> is saved in a placeholder variable.</span></span> <span data-ttu-id="a23ff-235">문자열 다음 브러시로 변환 되 고 적용 합니다 <xref:System.Windows.Shapes.Ellipse> 원의 제공 하는 UI입니다.</span><span class="sxs-lookup"><span data-stu-id="a23ff-235">The string is then converted to a brush and applied to the <xref:System.Windows.Shapes.Ellipse> that provides the Circle's UI.</span></span> <span data-ttu-id="a23ff-236">데이터를 놓지, 원래 않고 원 밖으로 끌어 놓으면 <xref:System.Windows.Shapes.Shape.Fill%2A> 값 원에 다시 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a23ff-236">If the data is dragged out of the Circle without being dropped, the original <xref:System.Windows.Shapes.Shape.Fill%2A> value is re-applied to the Circle.</span></span>  
  
### <a name="to-preview-the-effects-of-the-drag-and-drop-operation"></a><span data-ttu-id="a23ff-237">끌어서 놓기 작업의 결과를 미리 보려면</span><span class="sxs-lookup"><span data-stu-id="a23ff-237">To preview the effects of the drag-and-drop operation</span></span>  
  
1.  <span data-ttu-id="a23ff-238">Circle.xaml.cs 또는 Circle.xaml.vb를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="a23ff-238">Open Circle.xaml.cs or Circle.xaml.vb.</span></span>  
  
2.  <span data-ttu-id="a23ff-239">Circle 클래스에서 private 선언 <xref:System.Windows.Media.Brush> 라는 변수에 `_previousFill` 로 초기화 `null`합니다.</span><span class="sxs-lookup"><span data-stu-id="a23ff-239">In the Circle class, declare a private <xref:System.Windows.Media.Brush> variable named `_previousFill` and initialize it to `null`.</span></span>  
  
     [!code-csharp[DragDropWalkthrough#Brush](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/Circle.xaml.cs#brush)]
     [!code-vb[DragDropWalkthrough#Brush](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DragDropWalkthrough/VB/Circle.xaml.vb#brush)]  
  
3.  <span data-ttu-id="a23ff-240">다음을 추가 합니다 <xref:System.Windows.UIElement.OnDragEnter%2A> 클래스에 대 한 처리를 제공 하는 재정의 <xref:System.Windows.UIElement.DragEnter> 이벤트입니다.</span><span class="sxs-lookup"><span data-stu-id="a23ff-240">Add the following <xref:System.Windows.UIElement.OnDragEnter%2A> override to provide class handling for the <xref:System.Windows.UIElement.DragEnter> event.</span></span>  
  
     [!code-csharp[DragDropWalkthrough#OnDragEnter](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/Circle.xaml.cs#ondragenter)]
     [!code-vb[DragDropWalkthrough#OnDragEnter](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DragDropWalkthrough/VB/Circle.xaml.vb#ondragenter)]  
  
     <span data-ttu-id="a23ff-241">이 <xref:System.Windows.UIElement.OnDragEnter%2A> 재정의 다음 작업을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="a23ff-241">This <xref:System.Windows.UIElement.OnDragEnter%2A> override performs the following tasks:</span></span>  
  
    -   <span data-ttu-id="a23ff-242">저장를 <xref:System.Windows.Shapes.Shape.Fill%2A> 의 속성을 <xref:System.Windows.Shapes.Ellipse> 에 `_previousFill` 변수.</span><span class="sxs-lookup"><span data-stu-id="a23ff-242">Saves the <xref:System.Windows.Shapes.Shape.Fill%2A> property of the <xref:System.Windows.Shapes.Ellipse> in the `_previousFill` variable.</span></span>  
  
    -   <span data-ttu-id="a23ff-243">수행 되는 동일한 검사를 수행 합니다 <xref:System.Windows.UIElement.OnDrop%2A> 데이터를 변환할 수 있는지 여부를 결정 하는 메서드를 <xref:System.Windows.Media.Brush>합니다.</span><span class="sxs-lookup"><span data-stu-id="a23ff-243">Performs the same checks that are performed in the <xref:System.Windows.UIElement.OnDrop%2A> method to determine whether the data can be converted to a <xref:System.Windows.Media.Brush>.</span></span>  
  
    -   <span data-ttu-id="a23ff-244">유효한 데이터 변환 <xref:System.Windows.Media.Brush>에 적용 합니다 <xref:System.Windows.Shapes.Shape.Fill%2A> 의 <xref:System.Windows.Shapes.Ellipse>합니다.</span><span class="sxs-lookup"><span data-stu-id="a23ff-244">If the data is converted to a valid <xref:System.Windows.Media.Brush>, applies it to the <xref:System.Windows.Shapes.Shape.Fill%2A> of the <xref:System.Windows.Shapes.Ellipse>.</span></span>  
  
4.  <span data-ttu-id="a23ff-245">다음을 추가 합니다 <xref:System.Windows.UIElement.OnDragLeave%2A> 클래스에 대 한 처리를 제공 하는 재정의 <xref:System.Windows.UIElement.DragLeave> 이벤트입니다.</span><span class="sxs-lookup"><span data-stu-id="a23ff-245">Add the following <xref:System.Windows.UIElement.OnDragLeave%2A> override to provide class handling for the <xref:System.Windows.UIElement.DragLeave> event.</span></span>  
  
     [!code-csharp[DragDropWalkthrough#OnDragLeave](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/Circle.xaml.cs#ondragleave)]
     [!code-vb[DragDropWalkthrough#OnDragLeave](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DragDropWalkthrough/VB/Circle.xaml.vb#ondragleave)]  
  
     <span data-ttu-id="a23ff-246">이 <xref:System.Windows.UIElement.OnDragLeave%2A> 재정의 다음 작업을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="a23ff-246">This <xref:System.Windows.UIElement.OnDragLeave%2A> override performs the following tasks:</span></span>  
  
    -   <span data-ttu-id="a23ff-247">적용 됩니다는 <xref:System.Windows.Media.Brush> 에 저장 합니다 `_previousFill` 변수를 <xref:System.Windows.Shapes.Shape.Fill%2A> 의 <xref:System.Windows.Shapes.Ellipse> 원 사용자 정의 컨트롤의 UI를 제공 하는 합니다.</span><span class="sxs-lookup"><span data-stu-id="a23ff-247">Applies the <xref:System.Windows.Media.Brush> saved in the `_previousFill` variable to the <xref:System.Windows.Shapes.Shape.Fill%2A> of the <xref:System.Windows.Shapes.Ellipse> that provides the UI of the Circle user control.</span></span>  
  
5.  <span data-ttu-id="a23ff-248">F5 키를 눌러 응용 프로그램을 빌드하고 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="a23ff-248">Press F5 to build and run the application.</span></span>  
  
6.  <span data-ttu-id="a23ff-249">텍스트 선택 `green` 에 <xref:System.Windows.Controls.TextBox>합니다.</span><span class="sxs-lookup"><span data-stu-id="a23ff-249">Select the text `green` in the <xref:System.Windows.Controls.TextBox>.</span></span>  
  
7.  <span data-ttu-id="a23ff-250">텍스트를 놓지 않고 원 컨트롤 위로 끕니다.</span><span class="sxs-lookup"><span data-stu-id="a23ff-250">Drag the text over a Circle control without dropping it.</span></span> <span data-ttu-id="a23ff-251">원이 파란색에서 녹색으로 바뀝니다.</span><span class="sxs-lookup"><span data-stu-id="a23ff-251">The Circle changes from blue to green.</span></span>  
  
     <span data-ttu-id="a23ff-252">![끌어서 놓기 작업의 결과 미리 보기](../../../../docs/framework/wpf/advanced/media/dragdrop-previeweffects.png "DragDrop_PreviewEffects")</span><span class="sxs-lookup"><span data-stu-id="a23ff-252">![Preview the effects of a drag&#45;and&#45;drop operation](../../../../docs/framework/wpf/advanced/media/dragdrop-previeweffects.png "DragDrop_PreviewEffects")</span></span>  
  
8.  <span data-ttu-id="a23ff-253">원 컨트롤에서 멀리 텍스트를 끕니다.</span><span class="sxs-lookup"><span data-stu-id="a23ff-253">Drag the text away from the Circle control.</span></span> <span data-ttu-id="a23ff-254">원이 녹색에서 다시 파란색으로 바뀝니다.</span><span class="sxs-lookup"><span data-stu-id="a23ff-254">The Circle changes from green back to blue.</span></span>  
  
## <a name="enabling-a-panel-to-receive-dropped-data"></a><span data-ttu-id="a23ff-255">패널이 끌어 놓은 데이터를 수신할 수 있도록 설정</span><span class="sxs-lookup"><span data-stu-id="a23ff-255">Enabling a Panel to Receive Dropped Data</span></span>  
 <span data-ttu-id="a23ff-256">이 섹션에서는 원 사용자 정의 컨트롤을 호스트하는 패널이 끌어 온 원 데이터의 놓기 대상 역할을 하도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="a23ff-256">In this section, you will enable the panels that host the Circle user controls to act as drop targets for dragged Circle data.</span></span> <span data-ttu-id="a23ff-257">패널 간에 원을 이동하거나, Ctrl 키를 누른 상태로 원을 끌어서 놓아 원 컨트롤의 복사본을 만들 수 있도록 하는 코드를 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="a23ff-257">You will implement code that enables you to move a Circle from one panel to another, or to make a copy of a Circle control by holding down the CTRL key while dragging and dropping a Circle.</span></span>  
  
### <a name="to-enable-the-panel-to-be-a-drop-target"></a><span data-ttu-id="a23ff-258">패널을 놓기 대상으로 사용할 수 있도록 설정하려면</span><span class="sxs-lookup"><span data-stu-id="a23ff-258">To enable the panel to be a drop target</span></span>  
  
1.  <span data-ttu-id="a23ff-259">MainWindow.xaml을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="a23ff-259">Open MainWindow.xaml.</span></span>  
  
2.  <span data-ttu-id="a23ff-260">다음 XAML을 각 에서처럼 합니다 <xref:System.Windows.Controls.StackPanel> 컨트롤에 대 한 처리기를 추가 합니다 <xref:System.Windows.UIElement.DragOver> 및 <xref:System.Windows.UIElement.Drop> 이벤트.</span><span class="sxs-lookup"><span data-stu-id="a23ff-260">As shown in the following XAML, in each of the <xref:System.Windows.Controls.StackPanel> controls, add handlers for the <xref:System.Windows.UIElement.DragOver> and <xref:System.Windows.UIElement.Drop> events.</span></span> <span data-ttu-id="a23ff-261">이름 합니다 <xref:System.Windows.UIElement.DragOver> 이벤트 처리기 `panel_DragOver`, 이름을 <xref:System.Windows.UIElement.Drop> 이벤트 처리기 `panel_Drop`합니다.</span><span class="sxs-lookup"><span data-stu-id="a23ff-261">Name the <xref:System.Windows.UIElement.DragOver> event handler, `panel_DragOver`, and name the <xref:System.Windows.UIElement.Drop> event handler, `panel_Drop`.</span></span>  
  
     [!code-xaml[DragDropWalkthrough#PanelsXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/MainWindow.xaml#panelsxaml)]  
  
3.  <span data-ttu-id="a23ff-262">MainWindows.xaml.cs 또는 MainWindow.xaml.vb를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="a23ff-262">Open MainWindows.xaml.cs or MainWindow.xaml.vb.</span></span>  
  
4.  <span data-ttu-id="a23ff-263">다음 코드를 추가 합니다 <xref:System.Windows.UIElement.DragOver> 이벤트 처리기입니다.</span><span class="sxs-lookup"><span data-stu-id="a23ff-263">Add the following code for the <xref:System.Windows.UIElement.DragOver> event handler.</span></span>  
  
     [!code-csharp[DragDropWalkthrough#PanelDragOver](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/MainWindow.xaml.cs#paneldragover)]
     [!code-vb[DragDropWalkthrough#PanelDragOver](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DragDropWalkthrough/VB/MainWindow.xaml.vb#paneldragover)]  
  
     <span data-ttu-id="a23ff-264">이 <xref:System.Windows.UIElement.DragOver> 이벤트 처리기는 다음 작업을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="a23ff-264">This <xref:System.Windows.UIElement.DragOver> event handler performs the following tasks:</span></span>  
  
    -   <span data-ttu-id="a23ff-265">에 패키지 된 "Object" 데이터가 끌어 온된 데이터 포함을 확인 합니다 <xref:System.Windows.DataObject> 원 사용자 정의 컨트롤에서 호출에 전달 하 고 <xref:System.Windows.DragDrop.DoDragDrop%2A>입니다.</span><span class="sxs-lookup"><span data-stu-id="a23ff-265">Checks that the dragged data contains the "Object" data that was packaged in the <xref:System.Windows.DataObject> by the Circle user control and passed in the call to <xref:System.Windows.DragDrop.DoDragDrop%2A>.</span></span>  
  
    -   <span data-ttu-id="a23ff-266">"Object" 데이터가 있는 경우 Ctrl 키를 눌렀는지 여부를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="a23ff-266">If the "Object" data is present, checks whether the CTRL key is pressed.</span></span>  
  
    -   <span data-ttu-id="a23ff-267">CTRL 키를 누르는 경우 설정 합니다 <xref:System.Windows.DragEventArgs.Effects%2A> 속성을 <xref:System.Windows.DragDropEffects.Copy>입니다.</span><span class="sxs-lookup"><span data-stu-id="a23ff-267">If the CTRL key is pressed, sets the <xref:System.Windows.DragEventArgs.Effects%2A> property to <xref:System.Windows.DragDropEffects.Copy>.</span></span> <span data-ttu-id="a23ff-268">그렇지 않으면 설정 합니다 <xref:System.Windows.DragEventArgs.Effects%2A> 속성을 <xref:System.Windows.DragDropEffects.Move>입니다.</span><span class="sxs-lookup"><span data-stu-id="a23ff-268">Otherwise, set the <xref:System.Windows.DragEventArgs.Effects%2A> property to <xref:System.Windows.DragDropEffects.Move>.</span></span>  
  
5.  <span data-ttu-id="a23ff-269">다음 코드를 추가 합니다 <xref:System.Windows.UIElement.Drop> 이벤트 처리기입니다.</span><span class="sxs-lookup"><span data-stu-id="a23ff-269">Add the following code for the <xref:System.Windows.UIElement.Drop> event handler.</span></span>  
  
     [!code-csharp[DragDropWalkthrough#PanelDrop](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/MainWindow.xaml.cs#paneldrop)]
     [!code-vb[DragDropWalkthrough#PanelDrop](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DragDropWalkthrough/VB/MainWindow.xaml.vb#paneldrop)]  
  
     <span data-ttu-id="a23ff-270">이 <xref:System.Windows.UIElement.Drop> 이벤트 처리기는 다음 작업을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="a23ff-270">This <xref:System.Windows.UIElement.Drop> event handler performs the following tasks:</span></span>  
  
    -   <span data-ttu-id="a23ff-271">확인 여부를 <xref:System.Windows.UIElement.Drop> 이벤트가 이미 처리 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="a23ff-271">Checks whether the <xref:System.Windows.UIElement.Drop> event has already been handled.</span></span> <span data-ttu-id="a23ff-272">예를 들어 다른 원을 놓는 경우 원는 핸들을 <xref:System.Windows.UIElement.Drop> 이벤트를 원하지 않는 처리 원이 포함 된 패널입니다.</span><span class="sxs-lookup"><span data-stu-id="a23ff-272">For instance, if a Circle is dropped on another Circle which handles the <xref:System.Windows.UIElement.Drop> event, you do not want the panel that contains the Circle to also handle it.</span></span>  
  
    -   <span data-ttu-id="a23ff-273">경우는 <xref:System.Windows.UIElement.Drop> 이벤트 처리 되지 않으면 검사 CTRL 키가 눌러져 있는지 여부를 합니다.</span><span class="sxs-lookup"><span data-stu-id="a23ff-273">If the <xref:System.Windows.UIElement.Drop> event is not handled, checks whether the CTRL key is pressed.</span></span>  
  
    -   <span data-ttu-id="a23ff-274">때 CTRL 키를 누르는 경우는 <xref:System.Windows.UIElement.Drop> 발생 원의 복사 하면 제어에 추가 하는 <xref:System.Windows.Controls.Panel.Children%2A> 의 컬렉션을 <xref:System.Windows.Controls.StackPanel>.</span><span class="sxs-lookup"><span data-stu-id="a23ff-274">If the CTRL key is pressed when the <xref:System.Windows.UIElement.Drop> happens, makes a copy of the Circle control and add it to the <xref:System.Windows.Controls.Panel.Children%2A> collection of the <xref:System.Windows.Controls.StackPanel>.</span></span>  
  
    -   <span data-ttu-id="a23ff-275">CTRL 키를 누르지에서 원을 이동 합니다 <xref:System.Windows.Controls.Panel.Children%2A> 를 부모 컨트롤의 컬렉션을 <xref:System.Windows.Controls.Panel.Children%2A> 놓은 패널의 컬렉션.</span><span class="sxs-lookup"><span data-stu-id="a23ff-275">If the CTRL key is not pressed, moves the Circle from the <xref:System.Windows.Controls.Panel.Children%2A> collection of its parent panel to the <xref:System.Windows.Controls.Panel.Children%2A> collection of the panel that it was dropped on.</span></span>  
  
    -   <span data-ttu-id="a23ff-276">집합의 <xref:System.Windows.DragEventArgs.Effects%2A> 에 알리기 위해 속성을 <xref:System.Windows.DragDrop.DoDragDrop%2A> 메서드 이동 또는 복사 작업을 수행 하는지 여부입니다.</span><span class="sxs-lookup"><span data-stu-id="a23ff-276">Sets the <xref:System.Windows.DragEventArgs.Effects%2A> property to notify the <xref:System.Windows.DragDrop.DoDragDrop%2A> method whether a move or copy operation was performed.</span></span>  
  
6.  <span data-ttu-id="a23ff-277">F5 키를 눌러 응용 프로그램을 빌드하고 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="a23ff-277">Press F5 to build and run the application.</span></span>  
  
7.  <span data-ttu-id="a23ff-278">텍스트 선택 `green` 에서 <xref:System.Windows.Controls.TextBox>합니다.</span><span class="sxs-lookup"><span data-stu-id="a23ff-278">Select the text `green` from the <xref:System.Windows.Controls.TextBox>.</span></span>  
  
8.  <span data-ttu-id="a23ff-279">텍스트를 원 컨트롤로 끌어서 놓습니다.</span><span class="sxs-lookup"><span data-stu-id="a23ff-279">Drag the text over a Circle control and drop it.</span></span>  
  
9. <span data-ttu-id="a23ff-280">왼쪽 패널에서 오른쪽 패널로 원 컨트롤을 끌어서 놓습니다.</span><span class="sxs-lookup"><span data-stu-id="a23ff-280">Drag a Circle control from the left panel to the right panel and drop it.</span></span> <span data-ttu-id="a23ff-281">원에서 제거 되는 <xref:System.Windows.Controls.Panel.Children%2A> 왼쪽된 패널의 컬렉션 오른쪽 패널의 자식 컬렉션에 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="a23ff-281">The Circle is removed from the <xref:System.Windows.Controls.Panel.Children%2A> collection of the left panel and added to the Children collection of the right panel.</span></span>  
  
10. <span data-ttu-id="a23ff-282">원 컨트롤이 있는 패널에서 다른 패널로 원 컨트롤을 끌고 Ctrl 키를 누른 채 놓습니다.</span><span class="sxs-lookup"><span data-stu-id="a23ff-282">Drag a Circle control from the panel it is in to the other panel and drop it while pressing the CTRL key.</span></span> <span data-ttu-id="a23ff-283">원이 복사 되 고 복사본에 추가 됩니다는 <xref:System.Windows.Controls.Panel.Children%2A> 수신 패널의 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="a23ff-283">The Circle is copied and the copy is added to the <xref:System.Windows.Controls.Panel.Children%2A> collection of the receiving panel.</span></span>  
  
     <span data-ttu-id="a23ff-284">![Ctrl 키를 누른 채 원 끌기](../../../../docs/framework/wpf/advanced/media/dragdrop-paneldrop.png "DragDrop_PanelDrop")</span><span class="sxs-lookup"><span data-stu-id="a23ff-284">![Dragging a Circle while pressing the CTRL key](../../../../docs/framework/wpf/advanced/media/dragdrop-paneldrop.png "DragDrop_PanelDrop")</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a23ff-285">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a23ff-285">See Also</span></span>  
 [<span data-ttu-id="a23ff-286">끌어서 놓기 개요</span><span class="sxs-lookup"><span data-stu-id="a23ff-286">Drag and Drop Overview</span></span>](../../../../docs/framework/wpf/advanced/drag-and-drop-overview.md)
