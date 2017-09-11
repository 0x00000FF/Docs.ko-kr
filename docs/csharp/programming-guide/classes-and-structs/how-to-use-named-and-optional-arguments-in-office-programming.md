---
title: "방법: Office 프로그래밍에 명명된 인수와 선택적 인수 사용(C# 프로그래밍 가이드)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- named and optional arguments [C#], Office programming
- optional arguments [C#], Office programming
- named arguments [C#], Office programming
ms.assetid: 65b8a222-bcd8-454c-845f-84adff5a356f
caps.latest.revision: 34
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: c773e7a6d902b9e61e724a69c9fdf5d61606de50
ms.contentlocale: ko-kr
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-use-named-and-optional-arguments-in-office-programming-c-programming-guide"></a><span data-ttu-id="38130-102">방법: Office 프로그래밍에 명명된 인수와 선택적 인수 사용(C# 프로그래밍 가이드)</span><span class="sxs-lookup"><span data-stu-id="38130-102">How to: Use Named and Optional Arguments in Office Programming (C# Programming Guide)</span></span>
<span data-ttu-id="38130-103">[!INCLUDE[csharp_dev10_long](~/includes/csharp-dev10-long-md.md)]에서 도입된 명명된 인수 및 선택적 인수는 C# 프로그래밍의 편의성, 유연성 및 가독성을 향상합니다.</span><span class="sxs-lookup"><span data-stu-id="38130-103">Named arguments and optional arguments, introduced in [!INCLUDE[csharp_dev10_long](~/includes/csharp-dev10-long-md.md)], enhance convenience, flexibility, and readability in C# programming.</span></span> <span data-ttu-id="38130-104">또한 이러한 기능은 Microsoft Office 자동화 API와 같은 COM 인터페이스에 대한 액세스에 큰 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="38130-104">In addition, these features greatly facilitate access to COM interfaces such as the Microsoft Office automation APIs.</span></span>  
  
 <span data-ttu-id="38130-105">다음 예제의 [ConvertToTable](http://go.microsoft.com/fwlink/?LinkId=145378) 메서드에는 열과 행 수, 서식, 테두리, 글꼴, 색 등의 테이블 특성을 나타내는 매개 변수 16개가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="38130-105">In the following example, method [ConvertToTable](http://go.microsoft.com/fwlink/?LinkId=145378) has sixteen parameters that represent characteristics of a table, such as number of columns and rows, formatting, borders, fonts, and colors.</span></span> <span data-ttu-id="38130-106">대부분의 경우 모든 매개 변수에 대해 특정 값을 지정하지는 않으므로 16개 매개 변수는 모두 선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="38130-106">All sixteen parameters are optional, because most of the time you do not want to specify particular values for all of them.</span></span> <span data-ttu-id="38130-107">그러나 명명된 인수와 선택적 인수를 사용하지 않을 경우 각 매개 변수에 대해 값 또는 자리 표시자 값을 제공해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="38130-107">However, without named and optional arguments, a value or a placeholder value has to be provided for each parameter.</span></span> <span data-ttu-id="38130-108">명명된 인수와 선택적 인수를 사용할 경우 프로젝트에 필요한 매개 변수의 값만 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="38130-108">With named and optional arguments, you specify values only for the parameters that are required for your project.</span></span>  
  
 <span data-ttu-id="38130-109">이 절차를 완료하려면 컴퓨터에 Microsoft Office Word가 설치되어 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="38130-109">You must have Microsoft Office Word installed on your computer to complete these procedures.</span></span>  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
### <a name="to-create-a-new-console-application"></a><span data-ttu-id="38130-110">새 콘솔 응용 프로그램을 만들려면</span><span class="sxs-lookup"><span data-stu-id="38130-110">To create a new console application</span></span>  
  
1.  <span data-ttu-id="38130-111">Visual Studio를 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="38130-111">Start Visual Studio.</span></span>  
  
2.  <span data-ttu-id="38130-112">**파일** 메뉴에서 **새로 만들기**를 가리킨 다음 **프로젝트**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="38130-112">On the **File** menu, point to **New**, and then click **Project**.</span></span>  
  
3.  <span data-ttu-id="38130-113">**템플릿 범주** 창에서 **Visual C#**을 확장한 다음 **Windows**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="38130-113">In the **Templates Categories** pane, expand **Visual C#**, and then click **Windows**.</span></span>  
  
4.  <span data-ttu-id="38130-114">**템플릿** 창의 맨 위에서 **.NET Framework 4**가 **대상 프레임워크** 상자에 표시되는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="38130-114">Look in the top of the **Templates** pane to make sure that **.NET Framework 4** appears in the **Target Framework** box.</span></span>  
  
5.  <span data-ttu-id="38130-115">**템플릿** 창에서 **콘솔 응용 프로그램**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="38130-115">In the **Templates** pane, click **Console Application**.</span></span>  
  
6.  <span data-ttu-id="38130-116">**이름** 필드에 프로젝트의 이름을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="38130-116">Type a name for your project in the **Name** field.</span></span>  
  
7.  <span data-ttu-id="38130-117">**확인**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="38130-117">Click **OK**.</span></span>  
  
     <span data-ttu-id="38130-118">**솔루션 탐색기**에 새 프로젝트가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="38130-118">The new project appears in **Solution Explorer**.</span></span>  
  
### <a name="to-add-a-reference"></a><span data-ttu-id="38130-119">참조를 추가하려면</span><span class="sxs-lookup"><span data-stu-id="38130-119">To add a reference</span></span>  
  
1.  <span data-ttu-id="38130-120">**솔루션 탐색기**에서 프로젝트 이름을 마우스 오른쪽 단추로 클릭하고 **참조 추가**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="38130-120">In **Solution Explorer**, right-click your project's name and then click **Add Reference**.</span></span> <span data-ttu-id="38130-121">**참조 추가** 대화 상자가 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="38130-121">The **Add Reference** dialog box appears.</span></span>  
  
2.  <span data-ttu-id="38130-122">**.NET** 페이지의 **구성 요소 이름** 목록에서 **Microsoft.Office.Interop.Word**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="38130-122">On the **.NET** page, select **Microsoft.Office.Interop.Word** in the **Component Name** list.</span></span>  
  
3.  <span data-ttu-id="38130-123">**확인**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="38130-123">Click **OK**.</span></span>  
  
### <a name="to-add-necessary-using-directives"></a><span data-ttu-id="38130-124">필요한 using 지시문을 추가하려면</span><span class="sxs-lookup"><span data-stu-id="38130-124">To add necessary using directives</span></span>  
  
1.  <span data-ttu-id="38130-125">**솔루션 탐색기**에서 **Program.cs** 파일을 마우스 오른쪽 단추로 클릭하고 **코드 보기**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="38130-125">In **Solution Explorer**, right-click the **Program.cs** file and then click **View Code**.</span></span>  
  
2.  <span data-ttu-id="38130-126">다음 `using` 지시문을 코드 파일의 맨 위에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="38130-126">Add the following `using` directives to the top of the code file.</span></span>  
  
     <span data-ttu-id="38130-127">[!code-cs[csProgGuideNamedAndOptional#4](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-use-named-and-optional-arguments-in-office-programming_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="38130-127">[!code-cs[csProgGuideNamedAndOptional#4](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-use-named-and-optional-arguments-in-office-programming_1.cs)]</span></span>  
  
### <a name="to-display-text-in-a-word-document"></a><span data-ttu-id="38130-128">Word 문서에 텍스트를 표시하려면</span><span class="sxs-lookup"><span data-stu-id="38130-128">To display text in a Word document</span></span>  
  
1.  <span data-ttu-id="38130-129">Program.cs의 `Program` 클래스에서 다음 메서드를 추가하여 Word 응용 프로그램과 Word 문서를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="38130-129">In the `Program` class in Program.cs, add the following method to create a Word application and a Word document.</span></span> <span data-ttu-id="38130-130">[Add](http://go.microsoft.com/fwlink/?LinkId=145381) 메서드에는 선택적 매개 변수 4개가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="38130-130">The [Add](http://go.microsoft.com/fwlink/?LinkId=145381) method has four optional parameters.</span></span> <span data-ttu-id="38130-131">이 예제에서는 해당 기본값을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="38130-131">This example uses their default values.</span></span> <span data-ttu-id="38130-132">따라서 호출하는 문에 인수가 필요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="38130-132">Therefore, no arguments are necessary in the calling statement.</span></span>  
  
     <span data-ttu-id="38130-133">[!code-cs[csProgGuideNamedAndOptional#6](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-use-named-and-optional-arguments-in-office-programming_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="38130-133">[!code-cs[csProgGuideNamedAndOptional#6](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-use-named-and-optional-arguments-in-office-programming_2.cs)]</span></span>  
  
2.  <span data-ttu-id="38130-134">메서드의 끝에 다음 코드를 추가하여 문서에서 텍스트를 표시할 위치 및 표시할 텍스트를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="38130-134">Add the following code at the end of the method to define where to display text in the document, and what text to display.</span></span>  
  
     <span data-ttu-id="38130-135">[!code-cs[csProgGuideNamedAndOptional#7](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-use-named-and-optional-arguments-in-office-programming_3.cs)]</span><span class="sxs-lookup"><span data-stu-id="38130-135">[!code-cs[csProgGuideNamedAndOptional#7](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-use-named-and-optional-arguments-in-office-programming_3.cs)]</span></span>  
  
### <a name="to-run-the-application"></a><span data-ttu-id="38130-136">응용 프로그램을 실행하려면</span><span class="sxs-lookup"><span data-stu-id="38130-136">To run the application</span></span>  
  
1.  <span data-ttu-id="38130-137">다음 문을 Main에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="38130-137">Add the following statement to Main.</span></span>  
  
     <span data-ttu-id="38130-138">[!code-cs[csProgGuideNamedAndOptional#8](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-use-named-and-optional-arguments-in-office-programming_4.cs)]</span><span class="sxs-lookup"><span data-stu-id="38130-138">[!code-cs[csProgGuideNamedAndOptional#8](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-use-named-and-optional-arguments-in-office-programming_4.cs)]</span></span>  
  
2.  <span data-ttu-id="38130-139">Ctrl+F5를 눌러 프로젝트를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="38130-139">Press CTRL+F5 to run the project.</span></span> <span data-ttu-id="38130-140">지정된 텍스트를 포함하는 Word 문서가 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="38130-140">A Word document appears that contains the specified text.</span></span>  
  
### <a name="to-change-the-text-to-a-table"></a><span data-ttu-id="38130-141">텍스트를 표로 변경하려면</span><span class="sxs-lookup"><span data-stu-id="38130-141">To change the text to a table</span></span>  
  
1.  <span data-ttu-id="38130-142">`ConvertToTable` 메서드를 사용하여 텍스트를 표로 묶습니다.</span><span class="sxs-lookup"><span data-stu-id="38130-142">Use the `ConvertToTable` method to enclose the text in a table.</span></span> <span data-ttu-id="38130-143">이 메서드에는 선택적 매개 변수 16개가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="38130-143">The method has sixteen optional parameters.</span></span> <span data-ttu-id="38130-144">IntelliSense는 다음 그림과 같이 선택적 매개 변수를 중괄호로 묶습니다.</span><span class="sxs-lookup"><span data-stu-id="38130-144">IntelliSense encloses optional parameters in brackets, as shown in the following illustration.</span></span>  
  
     <span data-ttu-id="38130-145">![ConvertToTable 메서드의 매개 변수 목록](../../../csharp/programming-guide/classes-and-structs/media/convert_tableparameters.png "Convert_TableParameters")</span><span class="sxs-lookup"><span data-stu-id="38130-145">![List of parameters for ConvertToTable method.](../../../csharp/programming-guide/classes-and-structs/media/convert_tableparameters.png "Convert_TableParameters")</span></span>  
<span data-ttu-id="38130-146">ConvertToTable 매개 변수</span><span class="sxs-lookup"><span data-stu-id="38130-146">ConvertToTable parameters</span></span>  
  
     <span data-ttu-id="38130-147">명명된 인수 및 선택적 인수를 사용하면 변경하려는 매개 변수의 값만 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="38130-147">Named and optional arguments enable you to specify values for only the parameters that you want to change.</span></span> <span data-ttu-id="38130-148">`DisplayInWord` 메서드의 끝에 다음 코드를 추가하여 간단한 표를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="38130-148">Add the following code to the end of method `DisplayInWord` to create a simple table.</span></span> <span data-ttu-id="38130-149">인수는 `range`의 텍스트 문자열에 있는 쉼표가 표의 셀을 구분하도록 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="38130-149">The argument specifies that the commas in the text string in `range` separate the cells of the table.</span></span>  
  
     <span data-ttu-id="38130-150">[!code-cs[csProgGuideNamedAndOptional#9](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-use-named-and-optional-arguments-in-office-programming_5.cs)]</span><span class="sxs-lookup"><span data-stu-id="38130-150">[!code-cs[csProgGuideNamedAndOptional#9](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-use-named-and-optional-arguments-in-office-programming_5.cs)]</span></span>  
  
     <span data-ttu-id="38130-151">이전 버전의 C#에서 `ConvertToTable`을 호출하려면 다음 코드와 같이 각 매개 변수에 대한 참조 인수가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="38130-151">In earlier versions of C#, the call to `ConvertToTable` requires a reference argument for each parameter, as shown in the following code.</span></span>  
  
     <span data-ttu-id="38130-152">[!code-cs[csProgGuideNamedAndOptional#14](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-use-named-and-optional-arguments-in-office-programming_6.cs)]</span><span class="sxs-lookup"><span data-stu-id="38130-152">[!code-cs[csProgGuideNamedAndOptional#14](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-use-named-and-optional-arguments-in-office-programming_6.cs)]</span></span>  
  
2.  <span data-ttu-id="38130-153">Ctrl+F5를 눌러 프로젝트를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="38130-153">Press CTRL+F5 to run the project.</span></span>  
  
### <a name="to-experiment-with-other-parameters"></a><span data-ttu-id="38130-154">다른 매개 변수로 실험하려면</span><span class="sxs-lookup"><span data-stu-id="38130-154">To experiment with other parameters</span></span>  
  
1.  <span data-ttu-id="38130-155">열 1개와 행 3개가 포함되도록 표를 변경하려면 `DisplayInWord`의 마지막 줄을 다음 문으로 바꾼 다음 Ctrl+F5를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="38130-155">To change the table so that it has one column and three rows, replace the last line in `DisplayInWord` with the following statement and then type CTRL+F5.</span></span>  
  
     <span data-ttu-id="38130-156">[!code-cs[csProgGuideNamedAndOptional#10](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-use-named-and-optional-arguments-in-office-programming_7.cs)]</span><span class="sxs-lookup"><span data-stu-id="38130-156">[!code-cs[csProgGuideNamedAndOptional#10](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-use-named-and-optional-arguments-in-office-programming_7.cs)]</span></span>  
  
2.  <span data-ttu-id="38130-157">미리 정의된 표 형식을 지정하려면 `DisplayInWord`의 마지막 줄을 다음 문으로 바꾼 다음 Ctrl+F5를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="38130-157">To specify a predefined format for the table, replace the last line in `DisplayInWord` with the following statement and then type CTRL+F5.</span></span> <span data-ttu-id="38130-158">형식은 [WdTableFormat](http://go.microsoft.com/fwlink/?LinkId=145382) 상수 중 하나일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="38130-158">The format can be any of the [WdTableFormat](http://go.microsoft.com/fwlink/?LinkId=145382) constants.</span></span>  
  
     <span data-ttu-id="38130-159">[!code-cs[csProgGuideNamedAndOptional#11](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-use-named-and-optional-arguments-in-office-programming_8.cs)]</span><span class="sxs-lookup"><span data-stu-id="38130-159">[!code-cs[csProgGuideNamedAndOptional#11](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-use-named-and-optional-arguments-in-office-programming_8.cs)]</span></span>  
  
## <a name="example"></a><span data-ttu-id="38130-160">예제</span><span class="sxs-lookup"><span data-stu-id="38130-160">Example</span></span>  
 <span data-ttu-id="38130-161">다음 코드에는 전체 예제가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="38130-161">The following code includes the full example.</span></span>  
  
 <span data-ttu-id="38130-162">[!code-cs[csProgGuideNamedAndOptional#12](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-use-named-and-optional-arguments-in-office-programming_9.cs)]</span><span class="sxs-lookup"><span data-stu-id="38130-162">[!code-cs[csProgGuideNamedAndOptional#12](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-use-named-and-optional-arguments-in-office-programming_9.cs)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="38130-163">참고 항목</span><span class="sxs-lookup"><span data-stu-id="38130-163">See Also</span></span>  
 [<span data-ttu-id="38130-164">명명된 인수 및 선택적 인수</span><span class="sxs-lookup"><span data-stu-id="38130-164">Named and Optional Arguments</span></span>](../../../csharp/programming-guide/classes-and-structs/named-and-optional-arguments.md)

