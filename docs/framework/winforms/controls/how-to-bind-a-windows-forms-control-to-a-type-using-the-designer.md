---
title: '방법: 디자이너를 사용 하 여 형식에는 Windows Forms 컨트롤 바인딩'
ms.date: 03/30/2017
helpviewer_keywords:
- controls [Windows Forms], binding to a type
- BindingSource component [Windows Forms], binding to a type
- types [Windows Forms], binding controls to
ms.assetid: 5ab984b5-c2d0-4638-a572-1c84013e8746
ms.openlocfilehash: 6c307c913fc8deb62bc18ca2c01bb8621d9b0642
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54496441"
---
# <a name="how-to-bind-a-windows-forms-control-to-a-type-using-the-designer"></a><span data-ttu-id="402d3-102">방법: 디자이너를 사용 하 여 형식에는 Windows Forms 컨트롤 바인딩</span><span class="sxs-lookup"><span data-stu-id="402d3-102">How to: Bind a Windows Forms Control to a Type Using the Designer</span></span>
<span data-ttu-id="402d3-103">데이터와 상호 작용하는 컨트롤을 빌드하는 경우 때로는 개체가 아니라 형식에 컨트롤을 바인딩해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="402d3-103">When you are building controls that interact with data, you sometimes need to bind a control to a type, rather than an object.</span></span> <span data-ttu-id="402d3-104">데이터를 사용할 수 없지만 데이터 바인딩된 컨트롤에서 형식의 공용 인터페이스에서 가져온 데이터를 표시하려는 경우 일반적으로 디자인 타임에 컨트롤을 형식에 바인딩해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="402d3-104">You typically need to bind a control to a type at design time, when data may not be available, but you still want your data-bound controls to display data from a type's public interface.</span></span> <span data-ttu-id="402d3-105">다음 절차에는 새로 만드는 방법을 보여 줍니다 <xref:System.Windows.Forms.BindingSource> 즉 형식, 바인딩 및 다음 형식의 속성 중 하나를 바인딩하는 방법의 <xref:System.Windows.Forms.TextBox.Text%2A> 의 속성을 <xref:System.Windows.Forms.TextBox>입니다.</span><span class="sxs-lookup"><span data-stu-id="402d3-105">The following procedures demonstrate how to create a new <xref:System.Windows.Forms.BindingSource> that is bound to a type, and then how to bind one of the type's properties to the <xref:System.Windows.Forms.TextBox.Text%2A> property of a <xref:System.Windows.Forms.TextBox>.</span></span>  
  
### <a name="to-bind-the-bindingsource-to-a-type"></a><span data-ttu-id="402d3-106">BindingSource를 형식에 바인딩하려면</span><span class="sxs-lookup"><span data-stu-id="402d3-106">To bind the BindingSource to a type</span></span>  
  
1.  <span data-ttu-id="402d3-107">Windows Forms 프로젝트를 만듭니다 (**파일** > **새로 만들기** > **프로젝트** > **Visual C#** 또는 **Visual Basic** > **클래식 데스크톱** > **Windows Forms 응용 프로그램**).</span><span class="sxs-lookup"><span data-stu-id="402d3-107">Create a Windows Forms project (**File** > **New** > **Project** > **Visual C#** or **Visual Basic** > **Classic Desktop** > **Windows Forms Application**).</span></span>  
  
2.  <span data-ttu-id="402d3-108">**디자인** 보기에서 끌어서는 <xref:System.Windows.Forms.BindingSource> 폼에 구성 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="402d3-108">In **Design** view, drag a <xref:System.Windows.Forms.BindingSource> component onto the form.</span></span>  
  
3.  <span data-ttu-id="402d3-109">에 **속성** 창에서 화살표를 클릭 합니다 <xref:System.Windows.Forms.BindingSource.DataSource%2A> 속성.</span><span class="sxs-lookup"><span data-stu-id="402d3-109">In the **Properties** window, click the arrow for the <xref:System.Windows.Forms.BindingSource.DataSource%2A> property.</span></span>  
  
4.  <span data-ttu-id="402d3-110">**DataSource UI 형식 편집기**에서 **프로젝트 데이터 소스 추가**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="402d3-110">In the **DataSource UI Type Editor**, click **Add Project Data Source**.</span></span>  
  
5.  <span data-ttu-id="402d3-111">**데이터 소스 형식 선택** 페이지에서 **개체**를 선택하고 **다음**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="402d3-111">On the **Choose a Data Source Type** page, select **Object** and click **Next**.</span></span>  
  
6.  <span data-ttu-id="402d3-112">바인딩할 형식을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="402d3-112">Select the type to bind to:</span></span>  
  
    -   <span data-ttu-id="402d3-113">바인딩하려는 형식이 현재 프로젝트에 있거나 형식을 포함한 어셈블리가 이미 참조로 추가된 경우 노드를 확장하여 원하는 형식을 찾은 다음 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="402d3-113">If the type you want to bind to is in the current project, or the assembly that contains the type is already added as a reference, expand the nodes to find the type you want, and then select it.</span></span>  
  
         <span data-ttu-id="402d3-114">또는</span><span class="sxs-lookup"><span data-stu-id="402d3-114">-or-</span></span>  
  
    -   <span data-ttu-id="402d3-115">바인딩하려는 형식이 현재 참조 목록에 있지 않고 다른 어셈블리에 있는 경우 **참조 추가**를 클릭한 다음 **프로젝트** 탭을 클릭합니다. 원하는 비즈니스 개체를 포함하는 프로젝트를 선택하고 **확인**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="402d3-115">If the type you want to bind to is in another assembly, not currently in the list of references, click **Add Reference**, and then click the **Projects** tab. Select the project that contains the business object you want and click **OK**.</span></span> <span data-ttu-id="402d3-116">이 프로젝트는 어셈블리 목록에 표시됩니다. 따라서 노드를 확장하여 원하는 형식을 찾은 다음 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="402d3-116">This project will appear in the list of assemblies, so you can expand the nodes to find the type you want, and then select it.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="402d3-117">프레임워크 또는 Microsoft 어셈블리에 있는 형식에 바인딩하려는 경우 **Microsoft 또는 시스템을 시작하는 어셈블리 숨기기** 확인란의 선택을 취소합니다.</span><span class="sxs-lookup"><span data-stu-id="402d3-117">If you want to bind to a type in a framework or Microsoft assembly, clear the **Hide assemblies that begin with Microsoft or System** check box.</span></span>  
  
7.  <span data-ttu-id="402d3-118">**다음**을 클릭한 다음 **마침**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="402d3-118">Click **Next**, and then click **Finish**.</span></span>  
  
### <a name="to-bind-the-control-to-the-bindingsource"></a><span data-ttu-id="402d3-119">BindingSource에 컨트롤을 바인딩하려면</span><span class="sxs-lookup"><span data-stu-id="402d3-119">To bind the control to the BindingSource</span></span>  
  
1.  <span data-ttu-id="402d3-120">폼에 <xref:System.Windows.Forms.TextBox>를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="402d3-120">Add a <xref:System.Windows.Forms.TextBox> to the form.</span></span>  
  
2.  <span data-ttu-id="402d3-121">**속성** 창에서 **(DataBindings)** 노드를 확장합니다.</span><span class="sxs-lookup"><span data-stu-id="402d3-121">In the **Properties** window, expand the **(DataBindings)** node.</span></span>  
  
3.  <span data-ttu-id="402d3-122">다음 화살표를 클릭 합니다 <xref:System.Windows.Forms.TextBox.Text%2A> 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="402d3-122">Click the arrow next to the <xref:System.Windows.Forms.TextBox.Text%2A> property.</span></span>  
  
4.  <span data-ttu-id="402d3-123">에 **DataSource UI 형식 편집기**, 노드를 확장 합니다를 <xref:System.Windows.Forms.BindingSource> 에 바인딩하려는 바인딩된 형식의 속성을 선택 하 고 이전에 추가 <xref:System.Windows.Forms.TextBox.Text%2A> 속성의는 <xref:System.Windows.Forms.TextBox>.</span><span class="sxs-lookup"><span data-stu-id="402d3-123">In the **DataSource UI Type Editor**, expand the node for the <xref:System.Windows.Forms.BindingSource> added previously, and select the property of the bound type you want to bind to the <xref:System.Windows.Forms.TextBox.Text%2A> property of the <xref:System.Windows.Forms.TextBox>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="402d3-124">참고자료</span><span class="sxs-lookup"><span data-stu-id="402d3-124">See also</span></span>
- [<span data-ttu-id="402d3-125">BindingSource 구성 요소</span><span class="sxs-lookup"><span data-stu-id="402d3-125">BindingSource Component</span></span>](../../../../docs/framework/winforms/controls/bindingsource-component.md)
- [<span data-ttu-id="402d3-126">방법: 형식에는 Windows Forms 컨트롤 바인딩</span><span class="sxs-lookup"><span data-stu-id="402d3-126">How to: Bind a Windows Forms Control to a Type</span></span>](../../../../docs/framework/winforms/controls/how-to-bind-a-windows-forms-control-to-a-type.md)
- [<span data-ttu-id="402d3-127">Visual Studio에서 데이터에 컨트롤 바인딩</span><span class="sxs-lookup"><span data-stu-id="402d3-127">Bind controls to data in Visual Studio</span></span>](/visualstudio/data-tools/bind-controls-to-data-in-visual-studio)
