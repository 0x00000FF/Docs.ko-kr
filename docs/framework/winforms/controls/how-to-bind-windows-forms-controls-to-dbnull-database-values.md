---
title: '방법: DBNull 데이터베이스 값에 Windows Forms 컨트롤 바인딩'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- BindingSource component [Windows Forms], binding to DBNull values
- examples [Windows Forms], BindingSource component
- controls [Windows Forms], binding to DBNull values
ms.assetid: 96494e6f-5f40-4f83-af97-bbd7192c2af8
ms.openlocfilehash: 3233d210af342eb4a28f7ea7047eed0ed3dffd20
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/28/2019
ms.locfileid: "64650884"
---
# <a name="how-to-bind-windows-forms-controls-to-dbnull-database-values"></a><span data-ttu-id="7bec2-102">방법: DBNull 데이터베이스 값에 Windows Forms 컨트롤 바인딩</span><span class="sxs-lookup"><span data-stu-id="7bec2-102">How to: Bind Windows Forms Controls to DBNull Database Values</span></span>
<span data-ttu-id="7bec2-103">Windows Forms 컨트롤을 데이터 소스에 바인딩하고 데이터 소스가 <xref:System.DBNull> 값을 반환하는 경우 이벤트를 처리, 형식 지정 또는 구문 분석하지 않고 적절한 값을 대체할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7bec2-103">When you bind Windows Forms controls to a data source and the data source returns a <xref:System.DBNull> value, you can substitute an appropriate value without handling, formatting, or parsing events.</span></span> <span data-ttu-id="7bec2-104"><xref:System.Windows.Forms.Binding.NullValue%2A> 속성은 데이터 소스 값을 형식 지정 또는 구문 분석할 때 <xref:System.DBNull>을 지정된 개체로 변환합니다.</span><span class="sxs-lookup"><span data-stu-id="7bec2-104">The <xref:System.Windows.Forms.Binding.NullValue%2A> property will convert <xref:System.DBNull> to a specified object when formatting or parsing the data source values.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7bec2-105">예제</span><span class="sxs-lookup"><span data-stu-id="7bec2-105">Example</span></span>  
 <span data-ttu-id="7bec2-106">다음 예제에서는 두 가지 다른 상황에서 <xref:System.DBNull> 값을 바인딩하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="7bec2-106">The following example demonstrates how to bind a <xref:System.DBNull> value in two different situations.</span></span> <span data-ttu-id="7bec2-107">첫 번째 예제에서는 문자열 속성에 대해 <xref:System.Windows.Forms.Binding.NullValue%2A>를 설정하는 방법을 보여 주고, 두 번째 예제에서는 이미지 속성에 대해 <xref:System.Windows.Forms.Binding.NullValue%2A>를 설정하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="7bec2-107">The first demonstrates how to set the <xref:System.Windows.Forms.Binding.NullValue%2A> for a string property; the second demonstrates how to set the <xref:System.Windows.Forms.Binding.NullValue%2A> for an image property.</span></span>  
  
 [!code-csharp[System.Windows.Forms.BindingDBNull#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.BindingDBNull/CS/form1.cs#1)]
 [!code-vb[System.Windows.Forms.BindingDBNull#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.BindingDBNull/VB/form1.vb#1)]  
  
 <span data-ttu-id="7bec2-108">바인딩된 속성의 형식 및 <xref:System.Windows.Forms.Binding.NullValue%2A> 속성은 같아야 합니다. 그러지 않으면 오류가 발생하고 더 이상 <xref:System.Windows.Forms.Binding.NullValue%2A> 값이 처리되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7bec2-108">The types of the bound property and the <xref:System.Windows.Forms.Binding.NullValue%2A> property must be the same or an error will result, and no further <xref:System.Windows.Forms.Binding.NullValue%2A> values will be processed.</span></span> <span data-ttu-id="7bec2-109">이 경우 예외가 발생하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7bec2-109">In this situation, an exception will not be thrown.</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="7bec2-110">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="7bec2-110">Compiling the Code</span></span>  
 <span data-ttu-id="7bec2-111">이 예제에는 다음 사항이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="7bec2-111">This example requires:</span></span>  
  
- <span data-ttu-id="7bec2-112">System, System.Data, System.Drawing 및 System.Windows.Forms 어셈블리에 대한 참조</span><span class="sxs-lookup"><span data-stu-id="7bec2-112">References to the System, System.Data, System.Drawing and System.Windows.Forms assemblies.</span></span>  
  
 <span data-ttu-id="7bec2-113">Visual Basic 또는 Visual C#에 대 한 명령줄에서이 예제를 빌드하는 방법에 대 한 내용은 [명령줄에서 빌드](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md) 하거나 [csc.exe를 사용한 명령줄 빌드](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="7bec2-113">For information about building this example from the command line for Visual Basic or Visual C#, see [Building from the Command Line](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md) or [Command-line Building With csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span></span> <span data-ttu-id="7bec2-114">또한 새 프로젝트에 코드를 붙여 넣어 Visual Studio에서이 예제를 빌드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7bec2-114">You can also build this example in Visual Studio by pasting the code into a new project.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7bec2-115">참고자료</span><span class="sxs-lookup"><span data-stu-id="7bec2-115">See also</span></span>

- [<span data-ttu-id="7bec2-116">BindingSource 구성 요소</span><span class="sxs-lookup"><span data-stu-id="7bec2-116">BindingSource Component</span></span>](bindingsource-component.md)
- [<span data-ttu-id="7bec2-117">방법: 오류 및 데이터 바인딩에서 발생 하는 예외 처리</span><span class="sxs-lookup"><span data-stu-id="7bec2-117">How to: Handle Errors and Exceptions that Occur with Databinding</span></span>](how-to-handle-errors-and-exceptions-that-occur-with-databinding.md)
- [<span data-ttu-id="7bec2-118">방법: 형식에는 Windows Forms 컨트롤 바인딩</span><span class="sxs-lookup"><span data-stu-id="7bec2-118">How to: Bind a Windows Forms Control to a Type</span></span>](how-to-bind-a-windows-forms-control-to-a-type.md)
