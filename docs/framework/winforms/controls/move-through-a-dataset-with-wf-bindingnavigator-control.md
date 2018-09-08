---
title: '방법: Windows Forms BindingNavigator 컨트롤을 사용하여 데이터 집합에서 이동'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- datasets [Windows Forms], moving through
- BindingNavigator control [Windows Forms], moving through datasets
- examples [Windows Forms], BindingNavigator control
ms.assetid: 146d97be-3d97-400e-accb-860bbf47729d
ms.openlocfilehash: 272291a6c4d8b008b9efae23f392676ae1af7180
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/08/2018
ms.locfileid: "44205458"
---
# <a name="how-to-move-through-a-dataset-with-the-windows-forms-bindingnavigator-control"></a><span data-ttu-id="691f2-102">방법: Windows Forms BindingNavigator 컨트롤을 사용하여 데이터 집합에서 이동</span><span class="sxs-lookup"><span data-stu-id="691f2-102">How to: Move Through a DataSet with the Windows Forms BindingNavigator Control</span></span>
<span data-ttu-id="691f2-103">데이터 기반 응용 프로그램을 빌드할 때 사용자에게 데이터 컬렉션을 표시해야 하는 경우가 많습니다.</span><span class="sxs-lookup"><span data-stu-id="691f2-103">As you build data-driven applications, you will often need to display collections of data to users.</span></span> <span data-ttu-id="691f2-104"><xref:System.Windows.Forms.BindingSource> 구성 요소와 더불어 <xref:System.Windows.Forms.BindingNavigator> 컨트롤은 컬렉션을 탐색하고 항목을 순차적으로 표시하기 위한 편리하고 확장 가능한 솔루션을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="691f2-104">The <xref:System.Windows.Forms.BindingNavigator> control, in conjunction with the <xref:System.Windows.Forms.BindingSource> component, provides a convenient and extensible solution for moving through a collection and displaying items sequentially.</span></span>  
  
## <a name="example"></a><span data-ttu-id="691f2-105">예제</span><span class="sxs-lookup"><span data-stu-id="691f2-105">Example</span></span>  
 <span data-ttu-id="691f2-106">다음 코드 예제에서는 <xref:System.Windows.Forms.BindingNavigator> 컨트롤을 사용하여 데이터를 탐색하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="691f2-106">The following code example demonstrates how to use a <xref:System.Windows.Forms.BindingNavigator> control to move through data.</span></span> <span data-ttu-id="691f2-107">집합은 <xref:System.Windows.Forms.BindingSource> 구성 요소를 사용하여 <xref:System.Windows.Forms.TextBox> 컨트롤에 바인딩된 <xref:System.Data.DataView>에 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="691f2-107">The set is contained in a <xref:System.Data.DataView>, which is bound to a <xref:System.Windows.Forms.TextBox> control with a <xref:System.Windows.Forms.BindingSource> component.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="691f2-108">암호와 같은 중요한 정보를 연결 문자열 내에 저장하면 응용 프로그램 보안 문제가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="691f2-108">Storing sensitive information, such as a password, within the connection string can affect the security of your application.</span></span> <span data-ttu-id="691f2-109">데이터베이스 액세스를 제어할 경우에는 통합 보안이라고도 하는 Windows 인증을 사용하는 방법이 더 안전합니다.</span><span class="sxs-lookup"><span data-stu-id="691f2-109">Using Windows Authentication (also known as integrated security) is a more secure way to control access to a database.</span></span> <span data-ttu-id="691f2-110">자세한 내용은 [연결 정보 보호](../../../../docs/framework/data/adonet/protecting-connection-information.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="691f2-110">For more information, see [Protecting Connection Information](../../../../docs/framework/data/adonet/protecting-connection-information.md).</span></span>  
  
 [!code-csharp[System.Windows.Forms.DataNavigator#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataNavigator/CS/form1.cs#1)]
 [!code-vb[System.Windows.Forms.DataNavigator#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataNavigator/VB/form1.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="691f2-111">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="691f2-111">Compiling the Code</span></span>  
 <span data-ttu-id="691f2-112">이 예제에는 다음 사항이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="691f2-112">This example requires:</span></span>  
  
-   <span data-ttu-id="691f2-113">System, System.Data, System.Drawing, System.Windows.Forms and System.Xml 어셈블리에 대한 참조</span><span class="sxs-lookup"><span data-stu-id="691f2-113">References to the System, System.Data, System.Drawing, System.Windows.Forms and System.Xml assemblies.</span></span>  
  
 <span data-ttu-id="691f2-114">Visual Basic 또는 Visual C#에 대 한 명령줄에서이 예제를 빌드하는 방법에 대 한 내용은 [명령줄에서 빌드](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) 하거나 [csc.exe를 사용한 명령줄 빌드](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="691f2-114">For information about building this example from the command line for Visual Basic or Visual C#, see [Building from the Command Line](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) or [Command-line Building With csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span></span> <span data-ttu-id="691f2-115">또한 새 프로젝트에 코드를 붙여 넣어 Visual Studio에서이 예제를 빌드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="691f2-115">You can also build this example in Visual Studio by pasting the code into a new project.</span></span>  <span data-ttu-id="691f2-116">[방법: Visual Studio를 사용하여 전체 Windows Forms 코드 예제 컴파일 및 실행](https://msdn.microsoft.com/library/Bb129228\(v=vs.110\))을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="691f2-116">Also see [How to: Compile and Run a Complete Windows Forms Code Example Using Visual Studio](https://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="691f2-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="691f2-117">See Also</span></span>  
 <xref:System.Windows.Forms.BindingSource>  
 <xref:System.Windows.Forms.DataGridView>  
 <xref:System.Windows.Forms.BindingSource>  
 [<span data-ttu-id="691f2-118">BindingNavigator 컨트롤</span><span class="sxs-lookup"><span data-stu-id="691f2-118">BindingNavigator Control</span></span>](../../../../docs/framework/winforms/controls/bindingnavigator-control-windows-forms.md)  
 [<span data-ttu-id="691f2-119">BindingSource 구성 요소</span><span class="sxs-lookup"><span data-stu-id="691f2-119">BindingSource Component</span></span>](../../../../docs/framework/winforms/controls/bindingsource-component.md)  
 [<span data-ttu-id="691f2-120">방법: 형식에 Windows Forms 컨트롤 바인딩</span><span class="sxs-lookup"><span data-stu-id="691f2-120">How to: Bind a Windows Forms Control to a Type</span></span>](../../../../docs/framework/winforms/controls/how-to-bind-a-windows-forms-control-to-a-type.md)
