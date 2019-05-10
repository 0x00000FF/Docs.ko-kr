---
title: '방법: Windows Forms BindingSource를 사용하여 항목 추가 사용자 지정'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- controls [Windows Forms], creating new items
- BindingSource component [Windows Forms], customizing item addition with
- examples [Windows Forms], BindingSource component
- BindingSource component [Windows Forms], examples
ms.assetid: 1aae11fc-6fb2-4cb9-b3d0-e0638fe77ef0
ms.openlocfilehash: 33a82fbb4cd105491714cc07d997dd1eddb8fe24
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/28/2019
ms.locfileid: "64666353"
---
# <a name="how-to-customize-item-addition-with-the-windows-forms-bindingsource"></a><span data-ttu-id="550f2-102">방법: Windows Forms BindingSource를 사용하여 항목 추가 사용자 지정</span><span class="sxs-lookup"><span data-stu-id="550f2-102">How to: Customize Item Addition with the Windows Forms BindingSource</span></span>
<span data-ttu-id="550f2-103"><xref:System.Windows.Forms.BindingSource> 구성 요소를 사용하여 Windows Forms 컨트롤을 데이터 소스에 바인딩하는 경우 새 항목의 생성을 사용자 지정해야 할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="550f2-103">When you use a <xref:System.Windows.Forms.BindingSource> component to bind a Windows Forms control to a data source, you may find it necessary to customize the creation of new items.</span></span> <span data-ttu-id="550f2-104"><xref:System.Windows.Forms.BindingSource> 구성 요소는 일반적으로 바인딩된 컨트롤이 새 항목을 만들어야 할 때 발생하는 <xref:System.Windows.Forms.BindingSource.AddingNew> 이벤트를 제공하여 이 작업을 간소화합니다.</span><span class="sxs-lookup"><span data-stu-id="550f2-104">The <xref:System.Windows.Forms.BindingSource> component makes this straightforward by providing the <xref:System.Windows.Forms.BindingSource.AddingNew> event, which is typically raised when the bound control needs to create a new item.</span></span> <span data-ttu-id="550f2-105">이벤트 처리기에서 필요한 사용자 지정 동작(예: 웹 서비스에 대해 메서드 호출 또는 클래스 팩터리에서 새 개체 가져오기)을 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="550f2-105">Your event handler can provide whatever custom behavior is required (for example, calling a method on a Web service or getting a new object from a class factory).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="550f2-106"><xref:System.Windows.Forms.BindingSource.AddingNew> 이벤트를 처리하여 항목을 추가하는 경우 추가 작업을 취소할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="550f2-106">When an item is added by handling the <xref:System.Windows.Forms.BindingSource.AddingNew> event, the addition cannot be canceled.</span></span>  
  
## <a name="example"></a><span data-ttu-id="550f2-107">예제</span><span class="sxs-lookup"><span data-stu-id="550f2-107">Example</span></span>  
 <span data-ttu-id="550f2-108">다음 예제에서는 <xref:System.Windows.Forms.DataGridView> 구성 요소를 사용하여 <xref:System.Windows.Forms.BindingSource> 컨트롤을 클래스 팩터리에 바인딩하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="550f2-108">The following example demonstrates how to bind a <xref:System.Windows.Forms.DataGridView> control to a class factory by using a <xref:System.Windows.Forms.BindingSource> component.</span></span> <span data-ttu-id="550f2-109">사용자가 <xref:System.Windows.Forms.DataGridView> 컨트롤의 새 행을 클릭하면 <xref:System.Windows.Forms.BindingSource.AddingNew> 이벤트가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="550f2-109">When the user clicks the <xref:System.Windows.Forms.DataGridView> control's new row, the <xref:System.Windows.Forms.BindingSource.AddingNew> event is raised.</span></span> <span data-ttu-id="550f2-110">이벤트 처리기에서 `DemoCustomer` 개체를 새로 만들고 <xref:System.ComponentModel.AddingNewEventArgs.NewObject%2A?displayProperty=nameWithType> 속성에 개체가 할당됩니다.</span><span class="sxs-lookup"><span data-stu-id="550f2-110">The event handler creates a new `DemoCustomer` object, which is assigned to the <xref:System.ComponentModel.AddingNewEventArgs.NewObject%2A?displayProperty=nameWithType> property.</span></span> <span data-ttu-id="550f2-111">그러면 새 `DemoCustomer` 개체가 <xref:System.Windows.Forms.BindingSource> 구성 요소의 목록에 추가되고 <xref:System.Windows.Forms.DataGridView> 컨트롤의 새 행에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="550f2-111">This causes the new `DemoCustomer` object to be added to the <xref:System.Windows.Forms.BindingSource> component's list and to be displayed in the new row of the <xref:System.Windows.Forms.DataGridView> control.</span></span>  
  
 [!code-cpp[System.Windows.Forms.DataConnector.AddingNew#1](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataConnector.AddingNew/CPP/form1.cpp#1)]
 [!code-csharp[System.Windows.Forms.DataConnector.AddingNew#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataConnector.AddingNew/CS/form1.cs#1)]
 [!code-vb[System.Windows.Forms.DataConnector.AddingNew#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataConnector.AddingNew/VB/form1.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="550f2-112">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="550f2-112">Compiling the Code</span></span>  
 <span data-ttu-id="550f2-113">이 예제에는 다음 사항이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="550f2-113">This example requires:</span></span>  
  
- <span data-ttu-id="550f2-114">System, System.Data, System.Drawing 및 System.Windows.Forms 어셈블리에 대한 참조</span><span class="sxs-lookup"><span data-stu-id="550f2-114">References to the System, System.Data, System.Drawing and System.Windows.Forms assemblies.</span></span>  
  
 <span data-ttu-id="550f2-115">Visual Basic 또는 Visual C#에 대 한 명령줄에서이 예제를 빌드하는 방법에 대 한 내용은 [명령줄에서 빌드](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md) 하거나 [csc.exe를 사용한 명령줄 빌드](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="550f2-115">For information about building this example from the command line for Visual Basic or Visual C#, see [Building from the Command Line](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md) or [Command-line Building With csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span></span> <span data-ttu-id="550f2-116">또한 새 프로젝트에 코드를 붙여 넣어 Visual Studio에서이 예제를 빌드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="550f2-116">You can also build this example in Visual Studio by pasting the code into a new project.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="550f2-117">참고자료</span><span class="sxs-lookup"><span data-stu-id="550f2-117">See also</span></span>

- <xref:System.Windows.Forms.BindingNavigator>
- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.BindingSource>
- [<span data-ttu-id="550f2-118">BindingSource 구성 요소</span><span class="sxs-lookup"><span data-stu-id="550f2-118">BindingSource Component</span></span>](bindingsource-component.md)
- [<span data-ttu-id="550f2-119">방법: 형식에는 Windows Forms 컨트롤 바인딩</span><span class="sxs-lookup"><span data-stu-id="550f2-119">How to: Bind a Windows Forms Control to a Type</span></span>](how-to-bind-a-windows-forms-control-to-a-type.md)
