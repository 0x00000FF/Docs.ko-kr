---
title: "방법: Visual C# 기능을 사용하여 Office Interop 개체에 액세스(C# 프로그래밍 가이드)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- optional parameters [C#], Office programming
- named and optional arguments [C#], Office programming
- dynamic [C#], Office programming
- optional arguments [C#], Office programming
- named arguments [C#], Office programming
- Office programming [C#]
ms.assetid: 041b25c2-3512-4e0f-a4ea-ceb2999e4d5e
caps.latest.revision: 33
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
ms.openlocfilehash: 5ed3716e5c0d8cd143148522a2fb3aed5ec433ab
ms.contentlocale: ko-kr
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-access-office-interop-objects-by-using-visual-c-features-c-programming-guide"></a><span data-ttu-id="c7799-102">방법: Visual C# 기능을 사용하여 Office Interop 개체에 액세스(C# 프로그래밍 가이드)</span><span class="sxs-lookup"><span data-stu-id="c7799-102">How to: Access Office Interop Objects by Using Visual C# Features (C# Programming Guide)</span></span>
<span data-ttu-id="c7799-103">Visual C#에는 Office API 개체에 간편하게 액세스할 수 있는 기능이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c7799-103">Visual C# has features that simplify access to Office API objects.</span></span> <span data-ttu-id="c7799-104">새로운 기능에는 명명된 인수와 선택적 인수, `dynamic`이라는 새 형식 그리고 인수를 값 매개 변수처럼 COM 메서드의 참조 매개 변수로 전달하는 기능이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="c7799-104">The new features include named and optional arguments, a new type called `dynamic`, and the ability to pass arguments to reference parameters in COM methods as if they were value parameters.</span></span>  
  
 <span data-ttu-id="c7799-105">이 항목에서는 새 기능을 사용하여 Microsoft Office Excel 워크시트를 만들고 표시하는 코드를 작성합니다.</span><span class="sxs-lookup"><span data-stu-id="c7799-105">In this topic you will use the new features to write code that creates and displays a Microsoft Office Excel worksheet.</span></span> <span data-ttu-id="c7799-106">그런 다음 Excel 워크시트에 연결된 아이콘이 들어 있는 Office Word 문서를 추가하는 코드를 작성합니다.</span><span class="sxs-lookup"><span data-stu-id="c7799-106">You will then write code to add an Office Word document that contains an icon that is linked to the Excel worksheet.</span></span>  
  
 <span data-ttu-id="c7799-107">이 연습을 완료하려면 Microsoft Office Excel 2007 및 Microsoft Office Word 2007 이상 버전이 컴퓨터에 설치되어 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c7799-107">To complete this walkthrough, you must have Microsoft Office Excel 2007 and Microsoft Office Word 2007, or later versions, installed on your computer.</span></span>  
  
 <span data-ttu-id="c7799-108">[!INCLUDE[windowsver](~/includes/windowsver-md.md)]이전 버전의 운영 체제를 사용 중이라면 [!INCLUDE[dnprdnlong](~/includes/dnprdnlong-md.md)]이 설치되어 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="c7799-108">If you are using an operating system that is older than [!INCLUDE[windowsver](~/includes/windowsver-md.md)], make sure that [!INCLUDE[dnprdnlong](~/includes/dnprdnlong-md.md)] is installed.</span></span>  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
### <a name="to-create-a-new-console-application"></a><span data-ttu-id="c7799-109">새 콘솔 응용 프로그램을 만들려면</span><span class="sxs-lookup"><span data-stu-id="c7799-109">To create a new console application</span></span>  
  
1.  <span data-ttu-id="c7799-110">Visual Studio를 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="c7799-110">Start Visual Studio.</span></span>  
  
2.  <span data-ttu-id="c7799-111">**파일** 메뉴에서 **새로 만들기**를 가리킨 다음 **프로젝트**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="c7799-111">On the **File** menu, point to **New**, and then click **Project**.</span></span> <span data-ttu-id="c7799-112">**새 프로젝트** 대화 상자가 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="c7799-112">The **New Project** dialog box appears.</span></span>  
  
3.  <span data-ttu-id="c7799-113">**설치된 템플릿** 창에서 **Visual C#**을 확장한 다음 **Windows**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="c7799-113">In the **Installed Templates** pane, expand **Visual C#**, and then click **Windows**.</span></span>  
  
4.  <span data-ttu-id="c7799-114">**새 프로젝트** 대화 상자 위쪽에서 **.NET Framework 4** 이상 버전이 대상 프레임워크로 선택되어 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="c7799-114">Look at the top of the **New Project** dialog box to make sure that **.NET Framework 4** (or later version) is selected as a target framework.</span></span>  
  
5.  <span data-ttu-id="c7799-115">**템플릿** 창에서 **콘솔 응용 프로그램**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="c7799-115">In the **Templates** pane, click **Console Application**.</span></span>  
  
6.  <span data-ttu-id="c7799-116">**이름** 필드에 프로젝트의 이름을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="c7799-116">Type a name for your project in the **Name** field.</span></span>  
  
7.  <span data-ttu-id="c7799-117">**확인**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="c7799-117">Click **OK**.</span></span>  
  
     <span data-ttu-id="c7799-118">**솔루션 탐색기**에 새 프로젝트가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="c7799-118">The new project appears in **Solution Explorer**.</span></span>  
  
### <a name="to-add-references"></a><span data-ttu-id="c7799-119">참조를 추가하려면</span><span class="sxs-lookup"><span data-stu-id="c7799-119">To add references</span></span>  
  
1.  <span data-ttu-id="c7799-120">**솔루션 탐색기**에서 프로젝트 이름을 마우스 오른쪽 단추로 클릭하고 **참조 추가**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="c7799-120">In **Solution Explorer**, right-click your project's name and then click **Add Reference**.</span></span> <span data-ttu-id="c7799-121">**참조 추가** 대화 상자가 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="c7799-121">The **Add Reference** dialog box appears.</span></span>  
  
2.  <span data-ttu-id="c7799-122">**어셈블리** 페이지의 **구성 요소 이름** 목록에서 **Microsoft.Office.Interop.Word**를 선택하고 Ctrl 키를 누른 상태로 **Microsoft.Office.Interop.Excel**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="c7799-122">On the **Assemblies**  page, select **Microsoft.Office.Interop.Word** in the **Component Name** list, and then hold down the CTRL key and select **Microsoft.Office.Interop.Excel**.</span></span>  <span data-ttu-id="c7799-123">이러한 어셈블리가 보이지 않으면 어셈블리가 설치되어 있으며 표시되는지를 확인해야 할 수 있습니다([방법: Office 주 Interop 어셈블리 설치](/visualstudio/vsto/how-to-install-office-primary-interop-assemblies) 참조).</span><span class="sxs-lookup"><span data-stu-id="c7799-123">If you do not see the assemblies, you may need to ensure they are installed and displayed (see [How to: Install Office Primary Interop Assemblies](/visualstudio/vsto/how-to-install-office-primary-interop-assemblies))</span></span>  
  
3.  <span data-ttu-id="c7799-124">**확인**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="c7799-124">Click **OK**.</span></span>  
  
### <a name="to-add-necessary-using-directives"></a><span data-ttu-id="c7799-125">필요한 using 지시문을 추가하려면</span><span class="sxs-lookup"><span data-stu-id="c7799-125">To add necessary using directives</span></span>  
  
1.  <span data-ttu-id="c7799-126">**솔루션 탐색기**에서 **Program.cs** 파일을 마우스 오른쪽 단추로 클릭하고 **코드 보기**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="c7799-126">In **Solution Explorer**, right-click the **Program.cs** file and then click **View Code**.</span></span>  
  
2.  <span data-ttu-id="c7799-127">다음 `using` 지시문을 코드 파일의 맨 위에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="c7799-127">Add the following `using` directives to the top of the code file.</span></span>  
  
     <span data-ttu-id="c7799-128">[!code-cs[csProgGuideOfficeHowTo#1](../../../csharp/programming-guide/interop/codesnippet/CSharp/how-to-access-office-onterop-objects_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="c7799-128">[!code-cs[csProgGuideOfficeHowTo#1](../../../csharp/programming-guide/interop/codesnippet/CSharp/how-to-access-office-onterop-objects_1.cs)]</span></span>  
  
### <a name="to-create-a-list-of-bank-accounts"></a><span data-ttu-id="c7799-129">은행 계좌 목록을 만들려면</span><span class="sxs-lookup"><span data-stu-id="c7799-129">To create a list of bank accounts</span></span>  
  
1.  <span data-ttu-id="c7799-130">다음 클래스 정의를 **Program.cs**의 `Program` 클래스 아래에 붙여 넣습니다.</span><span class="sxs-lookup"><span data-stu-id="c7799-130">Paste the following class definition into **Program.cs**, under the `Program` class.</span></span>  
  
     <span data-ttu-id="c7799-131">[!code-cs[csProgGuideOfficeHowTo#2](../../../csharp/programming-guide/interop/codesnippet/CSharp/how-to-access-office-onterop-objects_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="c7799-131">[!code-cs[csProgGuideOfficeHowTo#2](../../../csharp/programming-guide/interop/codesnippet/CSharp/how-to-access-office-onterop-objects_2.cs)]</span></span>  
  
2.  <span data-ttu-id="c7799-132">다음 코드를 `Main` 메서드에 추가하여 계좌 두 개가 포함된 `bankAccounts` 목록을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="c7799-132">Add the following code to the `Main` method to create a `bankAccounts` list that contains two accounts.</span></span>  
  
     <span data-ttu-id="c7799-133">[!code-cs[csProgGuideOfficeHowTo#3](../../../csharp/programming-guide/interop/codesnippet/CSharp/how-to-access-office-onterop-objects_3.cs)]</span><span class="sxs-lookup"><span data-stu-id="c7799-133">[!code-cs[csProgGuideOfficeHowTo#3](../../../csharp/programming-guide/interop/codesnippet/CSharp/how-to-access-office-onterop-objects_3.cs)]</span></span>  
  
### <a name="to-declare-a-method-that-exports-account-information-to-excel"></a><span data-ttu-id="c7799-134">계좌 정보를 Excel로 내보내는 메서드를 선언하려면</span><span class="sxs-lookup"><span data-stu-id="c7799-134">To declare a method that exports account information to Excel</span></span>  
  
1.  <span data-ttu-id="c7799-135">다음 메서드를 `Program` 클래스에 추가하여 Excel 워크시트를 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="c7799-135">Add the following method to the `Program` class to set up an Excel worksheet.</span></span>  
  
     <span data-ttu-id="c7799-136">[Add](http://go.microsoft.com/fwlink/?LinkId=210910) 메서드에는 특정 템플릿을 지정하기 위한 선택적 매개 변수가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c7799-136">Method [Add](http://go.microsoft.com/fwlink/?LinkId=210910) has an optional parameter for specifying a particular template.</span></span> <span data-ttu-id="c7799-137">[!INCLUDE[csharp_dev10_long](~/includes/csharp-dev10-long-md.md)]에서 새롭게 제공되는 선택적 매개 변수를 사용하면 매개 변수의 기본값을 사용하려는 경우 해당 매개 변수의 인수를 생략할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c7799-137">Optional parameters, new in [!INCLUDE[csharp_dev10_long](~/includes/csharp-dev10-long-md.md)], enable you to omit the argument for that parameter if you want to use the parameter's default value.</span></span> <span data-ttu-id="c7799-138">다음 코드에서는 인수가 전송되지 않으므로 `Add`는 기본 템플릿을 사용하며 새 통합 문서를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="c7799-138">Because no argument is sent in the following code, `Add` uses the default template and creates a new workbook.</span></span> <span data-ttu-id="c7799-139">이전 버전의 C#에서 이와 동일한 문을 사용하려면 자리 표시자 인수인 `ExcelApp.Workbooks.Add(Type.Missing)`를 사용해야 했습니다.</span><span class="sxs-lookup"><span data-stu-id="c7799-139">The equivalent statement in earlier versions of C# requires a placeholder argument: `ExcelApp.Workbooks.Add(Type.Missing)`.</span></span>  
  
     <span data-ttu-id="c7799-140">[!code-cs[csProgGuideOfficeHowTo#4](../../../csharp/programming-guide/interop/codesnippet/CSharp/how-to-access-office-onterop-objects_4.cs)]</span><span class="sxs-lookup"><span data-stu-id="c7799-140">[!code-cs[csProgGuideOfficeHowTo#4](../../../csharp/programming-guide/interop/codesnippet/CSharp/how-to-access-office-onterop-objects_4.cs)]</span></span>  
  
2.  <span data-ttu-id="c7799-141">`DisplayInExcel` 끝에 다음 코드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="c7799-141">Add the following code at the end of `DisplayInExcel`.</span></span> <span data-ttu-id="c7799-142">이 코드는 워크시트 첫 번째 행의 처음 두 열에 값을 삽입합니다.</span><span class="sxs-lookup"><span data-stu-id="c7799-142">The code inserts values into the first two columns of the first row of the worksheet.</span></span>  
  
     <span data-ttu-id="c7799-143">[!code-cs[csProgGuideOfficeHowTo#5](../../../csharp/programming-guide/interop/codesnippet/CSharp/how-to-access-office-onterop-objects_5.cs)]</span><span class="sxs-lookup"><span data-stu-id="c7799-143">[!code-cs[csProgGuideOfficeHowTo#5](../../../csharp/programming-guide/interop/codesnippet/CSharp/how-to-access-office-onterop-objects_5.cs)]</span></span>  
  
3.  <span data-ttu-id="c7799-144">`DisplayInExcel` 끝에 다음 코드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="c7799-144">Add the following code at the end of `DisplayInExcel`.</span></span> <span data-ttu-id="c7799-145">`foreach` 루프는 계좌 목록의 정보를 워크시트에서 연속 행의 처음 두 열에 삽입합니다.</span><span class="sxs-lookup"><span data-stu-id="c7799-145">The `foreach` loop puts the information from the list of accounts into the first two columns of successive rows of the worksheet.</span></span>  
  
     <span data-ttu-id="c7799-146">[!code-cs[csProgGuideOfficeHowTo#7](../../../csharp/programming-guide/interop/codesnippet/CSharp/how-to-access-office-onterop-objects_6.cs)]</span><span class="sxs-lookup"><span data-stu-id="c7799-146">[!code-cs[csProgGuideOfficeHowTo#7](../../../csharp/programming-guide/interop/codesnippet/CSharp/how-to-access-office-onterop-objects_6.cs)]</span></span>  
  
4.  <span data-ttu-id="c7799-147">열 너비를 콘텐츠에 맞게 조정하려면 `DisplayInExcel` 끝에 다음 코드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="c7799-147">Add the following code at the end of `DisplayInExcel` to adjust the column widths to fit the content.</span></span>  
  
     <span data-ttu-id="c7799-148">[!code-cs[csProgGuideOfficeHowTo#13](../../../csharp/programming-guide/interop/codesnippet/CSharp/how-to-access-office-onterop-objects_7.cs)]</span><span class="sxs-lookup"><span data-stu-id="c7799-148">[!code-cs[csProgGuideOfficeHowTo#13](../../../csharp/programming-guide/interop/codesnippet/CSharp/how-to-access-office-onterop-objects_7.cs)]</span></span>  
  
     <span data-ttu-id="c7799-149">이전 버전의 C#에서는 이러한 작업을 명시적으로 캐스트해야 했습니다. `ExcelApp.Columns[1]`은 `Object`를 반환하며 `AutoFit`은 Excel [Range](http://go.microsoft.com/fwlink/?LinkId=210911) 메서드이기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="c7799-149">Earlier versions of C# require explicit casting for these operations because `ExcelApp.Columns[1]` returns an `Object`, and `AutoFit` is an Excel [Range](http://go.microsoft.com/fwlink/?LinkId=210911) method.</span></span> <span data-ttu-id="c7799-150">다음 줄에는 캐스팅이 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c7799-150">The following lines show the casting.</span></span>  
  
     <span data-ttu-id="c7799-151">[!code-cs[csProgGuideOfficeHowTo#14](../../../csharp/programming-guide/interop/codesnippet/CSharp/how-to-access-office-onterop-objects_8.cs)]</span><span class="sxs-lookup"><span data-stu-id="c7799-151">[!code-cs[csProgGuideOfficeHowTo#14](../../../csharp/programming-guide/interop/codesnippet/CSharp/how-to-access-office-onterop-objects_8.cs)]</span></span>  
  
     [!INCLUDE[csharp_dev10_long](~/includes/csharp-dev10-long-md.md)]<span data-ttu-id="c7799-152"> 이상 버전에서는 [/link](../../../csharp/language-reference/compiler-options/link-compiler-option.md) 컴파일러 옵션이 어셈블리를 참조하거나 Excel의 **Interop 형식 포함** 속성이 true로 설정되어 있으면(결과는 동일함) 반환된 `Object`를 `dynamic`으로 자동 변환합니다.</span><span class="sxs-lookup"><span data-stu-id="c7799-152">, and later versions, converts the returned `Object` to `dynamic` automatically if the assembly is referenced by the [/link](../../../csharp/language-reference/compiler-options/link-compiler-option.md) compiler option or, equivalently, if the Excel **Embed Interop Types** property is set to true.</span></span> <span data-ttu-id="c7799-153">이 속성의 기본값은 true입니다.</span><span class="sxs-lookup"><span data-stu-id="c7799-153">True is the default value for this property.</span></span>  
  
### <a name="to-run-the-project"></a><span data-ttu-id="c7799-154">프로젝트를 실행하려면</span><span class="sxs-lookup"><span data-stu-id="c7799-154">To run the project</span></span>  
  
1.  <span data-ttu-id="c7799-155">`Main` 끝에 다음 줄을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="c7799-155">Add the following line at the end of `Main`.</span></span>  
  
     <span data-ttu-id="c7799-156">[!code-cs[csProgGuideOfficeHowTo#8](../../../csharp/programming-guide/interop/codesnippet/CSharp/how-to-access-office-onterop-objects_9.cs)]</span><span class="sxs-lookup"><span data-stu-id="c7799-156">[!code-cs[csProgGuideOfficeHowTo#8](../../../csharp/programming-guide/interop/codesnippet/CSharp/how-to-access-office-onterop-objects_9.cs)]</span></span>  
  
2.  <span data-ttu-id="c7799-157">Ctrl+F5를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="c7799-157">Press CTRL+F5.</span></span>  
  
     <span data-ttu-id="c7799-158">두 계좌의 데이터가 포함된 Excel 워크시트가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="c7799-158">An Excel worksheet appears that contains the data from the two accounts.</span></span>  
  
### <a name="to-add-a-word-document"></a><span data-ttu-id="c7799-159">Word 문서를 추가하려면</span><span class="sxs-lookup"><span data-stu-id="c7799-159">To add a Word document</span></span>  
  
1.  <span data-ttu-id="c7799-160">[!INCLUDE[csharp_dev10_long](~/includes/csharp-dev10-long-md.md)] 이상 버전에서 Office 프로그래밍을 향상시키는 추가 방식을 설명하기 위해 다음 코드는 Word 응용 프로그램을 열고 Excel 워크시트에 연결되는 아이콘을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="c7799-160">To illustrate additional ways in which [!INCLUDE[csharp_dev10_long](~/includes/csharp-dev10-long-md.md)], and later versions, enhances Office programming, the following code opens a Word application and creates an icon that links to the Excel worksheet.</span></span>  
  
     <span data-ttu-id="c7799-161">이 단계의 뒷부분에서 제공되는 `CreateIconInWordDoc` 메서드를 `Program` 클래스에 붙여 넣습니다.</span><span class="sxs-lookup"><span data-stu-id="c7799-161">Paste method `CreateIconInWordDoc`, provided later in this step, into the `Program` class.</span></span> <span data-ttu-id="c7799-162">`CreateIconInWordDoc`는 [Add](http://go.microsoft.com/fwlink/?LinkId=210937) 및 [PasteSpecial](http://go.microsoft.com/fwlink/?LinkId=147099)에 대한 메서드 호출의 복잡성을 줄이기 위해 명명된 인수와 선택적 인수를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="c7799-162">`CreateIconInWordDoc` uses named and optional arguments to reduce the complexity of the method calls to [Add](http://go.microsoft.com/fwlink/?LinkId=210937) and [PasteSpecial](http://go.microsoft.com/fwlink/?LinkId=147099).</span></span> <span data-ttu-id="c7799-163">이러한 호출에는 [!INCLUDE[csharp_dev10_long](~/includes/csharp-dev10-long-md.md)]에 도입된 다른 두 가지 새 기능이 통합됩니다. 이러한 기능은 참조 매개 변수가 포함된 COM 메서드 호출을 간소화합니다.</span><span class="sxs-lookup"><span data-stu-id="c7799-163">These calls incorporate two other new features introduced in [!INCLUDE[csharp_dev10_long](~/includes/csharp-dev10-long-md.md)] that simplify calls to COM methods that have reference parameters.</span></span> <span data-ttu-id="c7799-164">그 중 첫 번째 기능은 인수를 값 매개 변수처럼 참조 매개 변수로 전달하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="c7799-164">First, you can send arguments to the reference parameters as if they were value parameters.</span></span> <span data-ttu-id="c7799-165">즉, 각 참조 매개 변수에 대한 변수를 만들지 않고 직접 값을 보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c7799-165">That is, you can send values directly, without creating a variable for each reference parameter.</span></span> <span data-ttu-id="c7799-166">컴파일러는 인수 값을 저장하기 위한 임시 변수를 생성하고 호출에서 값이 반환되면 해당 변수를 삭제합니다.</span><span class="sxs-lookup"><span data-stu-id="c7799-166">The compiler generates temporary variables to hold the argument values, and discards the variables when you return from the call.</span></span> <span data-ttu-id="c7799-167">두 번째 기능은 인수 목록의 `ref` 키워드를 생략하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="c7799-167">Second, you can omit the `ref` keyword in the argument list.</span></span>  
  
     <span data-ttu-id="c7799-168">`Add` 메서드에는 참조 매개 변수 4개가 있습니다(모두 선택적 매개 변수임).</span><span class="sxs-lookup"><span data-stu-id="c7799-168">The `Add` method has four reference parameters, all of which are optional.</span></span> <span data-ttu-id="c7799-169">[!INCLUDE[csharp_dev10_long](~/includes/csharp-dev10-long-md.md)] 이상 버전에서는 기본값을 사용하려는 경우 모든 매개 변수 또는 원하는 매개 변수의 인수를 생략할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c7799-169">In [!INCLUDE[csharp_dev10_long](~/includes/csharp-dev10-long-md.md)], or later versions, you can omit arguments for any or all of the parameters if you want to use their default values.</span></span> <span data-ttu-id="c7799-170">[!INCLUDE[csharp_orcas_long](~/includes/csharp-orcas-long-md.md)] 이하 버전에서는 각 매개 변수에 대해 인수를 제공해야 하며 매개 변수가 참조 매개 변수이므로 인수는 변수여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c7799-170">In [!INCLUDE[csharp_orcas_long](~/includes/csharp-orcas-long-md.md)] and earlier versions, an argument must be provided for each parameter, and the argument must be a variable because the parameters are reference parameters.</span></span>  
  
     <span data-ttu-id="c7799-171">`PasteSpecial` 메서드는 클립보드의 내용을 삽입합니다.</span><span class="sxs-lookup"><span data-stu-id="c7799-171">The `PasteSpecial` method inserts the contents of the Clipboard.</span></span> <span data-ttu-id="c7799-172">이 메서드에는 참조 매개 변수 7개가 있습니다(모두 선택적 매개 변수임).</span><span class="sxs-lookup"><span data-stu-id="c7799-172">The method has seven reference parameters, all of which are optional.</span></span> <span data-ttu-id="c7799-173">다음 코드는 이러한 매개 변수 중 두 개에 대해 인수를 지정합니다. 그 중 하나는 클립보드 내용의 소스에 대한 링크를 만드는 `Link`이고 다른 하나는 링크를 아이콘으로 표시하는 `DisplayAsIcon`입니다.</span><span class="sxs-lookup"><span data-stu-id="c7799-173">The following code specifies arguments for two of them: `Link`, to create a link to the source of the Clipboard contents, and `DisplayAsIcon`, to display the link as an icon.</span></span> <span data-ttu-id="c7799-174">[!INCLUDE[csharp_dev10_long](~/includes/csharp-dev10-long-md.md)]에서는 이 두 매개 변수에 대해 명명된 인수를 사용하고 나머지 인수는 생략할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c7799-174">In [!INCLUDE[csharp_dev10_long](~/includes/csharp-dev10-long-md.md)], you can use named arguments for those two and omit the others.</span></span> <span data-ttu-id="c7799-175">이러한 매개 변수는 참조 매개 변수이지만 `ref` 키워드를 사용하거나 인수로 보낼 변수를 만들 필요가 없으며,</span><span class="sxs-lookup"><span data-stu-id="c7799-175">Although these are reference parameters, you do not have to use the `ref` keyword, or to create variables to send in as arguments.</span></span> <span data-ttu-id="c7799-176">값을 직접 보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c7799-176">You can send the values directly.</span></span> <span data-ttu-id="c7799-177">[!INCLUDE[csharp_orcas_long](~/includes/csharp-orcas-long-md.md)] 이하 버전에서는 각 참조 매개 변수에 대해 가변 인수를 보내야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c7799-177">In [!INCLUDE[csharp_orcas_long](~/includes/csharp-orcas-long-md.md)] and earlier versions, you must send a variable argument for each reference parameter.</span></span>  
  
     <span data-ttu-id="c7799-178">[!code-cs[csProgGuideOfficeHowTo#9](../../../csharp/programming-guide/interop/codesnippet/CSharp/how-to-access-office-onterop-objects_10.cs)]</span><span class="sxs-lookup"><span data-stu-id="c7799-178">[!code-cs[csProgGuideOfficeHowTo#9](../../../csharp/programming-guide/interop/codesnippet/CSharp/how-to-access-office-onterop-objects_10.cs)]</span></span>  
  
     <span data-ttu-id="c7799-179">[!INCLUDE[csharp_orcas_long](~/includes/csharp-orcas-long-md.md)] 이하 버전의 언어에서는 다음과 같은 더 복잡한 코드를 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c7799-179">In [!INCLUDE[csharp_orcas_long](~/includes/csharp-orcas-long-md.md)] or earlier versions of the language, the following more complex code is required.</span></span>  
  
     <span data-ttu-id="c7799-180">[!code-cs[csProgGuideOfficeHowTo#10](../../../csharp/programming-guide/interop/codesnippet/CSharp/how-to-access-office-onterop-objects_11.cs)]</span><span class="sxs-lookup"><span data-stu-id="c7799-180">[!code-cs[csProgGuideOfficeHowTo#10](../../../csharp/programming-guide/interop/codesnippet/CSharp/how-to-access-office-onterop-objects_11.cs)]</span></span>  
  
2.  <span data-ttu-id="c7799-181">`Main` 끝에 다음 문을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="c7799-181">Add the following statement at the end of `Main`.</span></span>  
  
     <span data-ttu-id="c7799-182">[!code-cs[csProgGuideOfficeHowTo#11](../../../csharp/programming-guide/interop/codesnippet/CSharp/how-to-access-office-onterop-objects_12.cs)]</span><span class="sxs-lookup"><span data-stu-id="c7799-182">[!code-cs[csProgGuideOfficeHowTo#11](../../../csharp/programming-guide/interop/codesnippet/CSharp/how-to-access-office-onterop-objects_12.cs)]</span></span>  
  
3.  <span data-ttu-id="c7799-183">`DisplayInExcel` 끝에 다음 문을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="c7799-183">Add the following statement at the end of `DisplayInExcel`.</span></span> <span data-ttu-id="c7799-184">`Copy` 메서드는 클립보드에 워크시트를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="c7799-184">The `Copy` method adds the worksheet to the Clipboard.</span></span>  
  
     <span data-ttu-id="c7799-185">[!code-cs[csProgGuideOfficeHowTo#12](../../../csharp/programming-guide/interop/codesnippet/CSharp/how-to-access-office-onterop-objects_13.cs)]</span><span class="sxs-lookup"><span data-stu-id="c7799-185">[!code-cs[csProgGuideOfficeHowTo#12](../../../csharp/programming-guide/interop/codesnippet/CSharp/how-to-access-office-onterop-objects_13.cs)]</span></span>  
  
4.  <span data-ttu-id="c7799-186">Ctrl+F5를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="c7799-186">Press CTRL+F5.</span></span>  
  
     <span data-ttu-id="c7799-187">아이콘이 포함된 Word 문서가 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="c7799-187">A Word document appears that contains an icon.</span></span> <span data-ttu-id="c7799-188">아이콘을 두 번 클릭하여 워크시트를 포그라운드로 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="c7799-188">Double-click the icon to bring the worksheet to the foreground.</span></span>  
  
### <a name="to-set-the-embed-interop-types-property"></a><span data-ttu-id="c7799-189">Interop 형식 포함 속성을 설정하려면</span><span class="sxs-lookup"><span data-stu-id="c7799-189">To set the Embed Interop Types property</span></span>  
  
1.  <span data-ttu-id="c7799-190">런타임에 PIA(주 interop 어셈블리)를 사용하지 않아도 되는 COM 형식을 호출할 때는 코드를 추가로 개선할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c7799-190">Additional enhancements are possible when you call a COM type that does not require a primary interop assembly (PIA) at run time.</span></span> <span data-ttu-id="c7799-191">PIA에 대한 종속성을 제거하면 버전을 독립적으로 실행할 수 있으며 보다 쉽게 배포할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c7799-191">Removing the dependency on PIAs results in version independence and easier deployment.</span></span> <span data-ttu-id="c7799-192">PIA를 사용하지 않는 프로그래밍의 장점에 대한 자세한 내용은 [Walkthrough: Embedding Types from Managed Assemblies](http://msdn.microsoft.com/library/b28ec92c-1867-4847-95c0-61adfe095e21)(연습: 관리되는 어셈블리의 형식 포함)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c7799-192">For more information about the advantages of programming without PIAs, see [Walkthrough: Embedding Types from Managed Assemblies](http://msdn.microsoft.com/library/b28ec92c-1867-4847-95c0-61adfe095e21).</span></span>  
  
     <span data-ttu-id="c7799-193">또한 COM 메서드에서 사용해야 하며 반환되는 형식은 `dynamic`가 아닌 `Object` 형식을 사용하여 표시할 수 있으므로 프로그램이 더욱 쉬워집니다.</span><span class="sxs-lookup"><span data-stu-id="c7799-193">In addition, programming is easier because the types that are required and returned by COM methods can be represented by using the type `dynamic` instead of `Object`.</span></span> <span data-ttu-id="c7799-194">`dynamic` 형식이 포함된 변수는 런타임까지 평가되지 않으므로 명시적 캐스팅을 수행할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c7799-194">Variables that have type `dynamic` are not evaluated until run time, which eliminates the need for explicit casting.</span></span> <span data-ttu-id="c7799-195">자세한 내용은 [dynamic 형식 사용](../../../csharp/programming-guide/types/using-type-dynamic.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c7799-195">For more information, see [Using Type dynamic](../../../csharp/programming-guide/types/using-type-dynamic.md).</span></span>  
  
     <span data-ttu-id="c7799-196">[!INCLUDE[csharp_dev10_long](~/includes/csharp-dev10-long-md.md)]에서는 PIA를 사용하는 대신 형식 정보를 포함하는 것이 기본 동작입니다.</span><span class="sxs-lookup"><span data-stu-id="c7799-196">In [!INCLUDE[csharp_dev10_long](~/includes/csharp-dev10-long-md.md)], embedding type information instead of using PIAs is default behavior.</span></span> <span data-ttu-id="c7799-197">이러한 기본 동작으로 인해 명시적 캐스팅이 필요하지 않으므로 위의 여러 예제가 간소화됩니다.</span><span class="sxs-lookup"><span data-stu-id="c7799-197">Because of that default, several of the previous examples are simplified because explicit casting is not required.</span></span> <span data-ttu-id="c7799-198">예를 들어 `worksheet`의 `DisplayInExcel` 선언은 `Excel._Worksheet workSheet = excelApp.ActiveSheet`가 아닌 `Excel._Worksheet workSheet = (Excel.Worksheet)excelApp.ActiveSheet`로 작성됩니다.</span><span class="sxs-lookup"><span data-stu-id="c7799-198">For example, the declaration of `worksheet` in `DisplayInExcel` is written as `Excel._Worksheet workSheet = excelApp.ActiveSheet` rather than `Excel._Worksheet workSheet = (Excel.Worksheet)excelApp.ActiveSheet`.</span></span> <span data-ttu-id="c7799-199">마찬가지로 기본 동작이 없으면 같은 메서드의 `AutoFit`에 대한 호출에서도 명시적 캐스팅을 수행해야 합니다. `ExcelApp.Columns[1]`는 `Object`를 반환하며 `AutoFit`은 Excel 메서드이기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="c7799-199">The calls to `AutoFit` in the same method also would require explicit casting without the default, because `ExcelApp.Columns[1]` returns an `Object`, and `AutoFit` is an Excel  method.</span></span> <span data-ttu-id="c7799-200">다음 코드에서는 캐스팅을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="c7799-200">The following code shows the casting.</span></span>  
  
     <span data-ttu-id="c7799-201">[!code-cs[csProgGuideOfficeHowTo#14](../../../csharp/programming-guide/interop/codesnippet/CSharp/how-to-access-office-onterop-objects_8.cs)]</span><span class="sxs-lookup"><span data-stu-id="c7799-201">[!code-cs[csProgGuideOfficeHowTo#14](../../../csharp/programming-guide/interop/codesnippet/CSharp/how-to-access-office-onterop-objects_8.cs)]</span></span>  
  
2.  <span data-ttu-id="c7799-202">형식 정보를 포함하는 대신 기본값을 변경하여 PIA를 사용하려면 **솔루션 탐색기**에서 **참조** 노드를 확장하고 **Microsoft.Office.Interop.Excel** 또는 **Microsoft.Office.Interop.Word**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="c7799-202">To change the default and use PIAs instead of embedding type information, expand the **References** node in **Solution Explorer** and then select **Microsoft.Office.Interop.Excel** or **Microsoft.Office.Interop.Word**.</span></span>  
  
3.  <span data-ttu-id="c7799-203">**속성** 창이 보이지 않으면 **F4**키를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="c7799-203">If you cannot see the **Properties** window, press **F4**.</span></span>  
  
4.  <span data-ttu-id="c7799-204">속성 목록에서 **Interop 형식 포함**을 찾은 다음 해당 값을 **False**로 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="c7799-204">Find **Embed Interop Types** in the list of properties, and change its value to **False**.</span></span> <span data-ttu-id="c7799-205">마찬가지로 명령 프롬프트에서 [/link](../../../csharp/language-reference/compiler-options/link-compiler-option.md) 대신 [/reference](../../../csharp/language-reference/compiler-options/reference-compiler-option.md) 컴파일러 옵션을 사용하여 컴파일할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c7799-205">Equivalently, you can compile by using the [/reference](../../../csharp/language-reference/compiler-options/reference-compiler-option.md) compiler option instead of [/link](../../../csharp/language-reference/compiler-options/link-compiler-option.md) at a command prompt.</span></span>  
  
### <a name="to-add-additional-formatting-to-the-table"></a><span data-ttu-id="c7799-206">표에 서식을 더 추가하려면</span><span class="sxs-lookup"><span data-stu-id="c7799-206">To add additional formatting to the table</span></span>  
  
1.  <span data-ttu-id="c7799-207">`AutoFit`에서 `DisplayInExcel`에 대한 두 호출을 다음 문으로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="c7799-207">Replace the two calls to `AutoFit` in `DisplayInExcel` with the following statement.</span></span>  
  
     <span data-ttu-id="c7799-208">[!code-cs[csProgGuideOfficeHowTo#15](../../../csharp/programming-guide/interop/codesnippet/CSharp/how-to-access-office-onterop-objects_14.cs)]</span><span class="sxs-lookup"><span data-stu-id="c7799-208">[!code-cs[csProgGuideOfficeHowTo#15](../../../csharp/programming-guide/interop/codesnippet/CSharp/how-to-access-office-onterop-objects_14.cs)]</span></span>  
  
     <span data-ttu-id="c7799-209">[AutoFormat](http://go.microsoft.com/fwlink/?LinkId=210948) 메서드에는 값 매개 변수 7개가 있습니다(모두 선택적 매개 변수임).</span><span class="sxs-lookup"><span data-stu-id="c7799-209">The [AutoFormat](http://go.microsoft.com/fwlink/?LinkId=210948) method has seven value parameters, all of which are optional.</span></span> <span data-ttu-id="c7799-210">명명된 인수와 선택적 인수를 사용하여 이러한 매개 변수 중 일부 또는 모두에 대해 인수를 제공할 수도 있고 모든 매개 변수에 인수를 제공하지 않을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c7799-210">Named and optional arguments enable you to provide arguments for none, some, or all of them.</span></span> <span data-ttu-id="c7799-211">위의 문에서는 `Format` 매개 변수 하나에만 인수가 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="c7799-211">In the previous statement, an argument is supplied for only one of the parameters, `Format`.</span></span> <span data-ttu-id="c7799-212">`Format`은 매개 변수 목록의 첫 번째 매개 변수이므로 매개 변수 이름은 지정하지 않아도 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c7799-212">Because `Format` is the first parameter in the parameter list, you do not have to provide the parameter name.</span></span> <span data-ttu-id="c7799-213">그러나 다음 코드에 나와 있는 것처럼 매개 변수 이름을 포함하면 문을 더 쉽게 이해할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c7799-213">However, the statement might be easier to understand if the parameter name is included, as is shown in the following code.</span></span>  
  
     <span data-ttu-id="c7799-214">[!code-cs[csProgGuideOfficeHowTo#16](../../../csharp/programming-guide/interop/codesnippet/CSharp/how-to-access-office-onterop-objects_15.cs)]</span><span class="sxs-lookup"><span data-stu-id="c7799-214">[!code-cs[csProgGuideOfficeHowTo#16](../../../csharp/programming-guide/interop/codesnippet/CSharp/how-to-access-office-onterop-objects_15.cs)]</span></span>  
  
2.  <span data-ttu-id="c7799-215">결과를 보려면 CTRL+F5를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="c7799-215">Press CTRL+F5 to see the result.</span></span> <span data-ttu-id="c7799-216">기타 서식은 [XlRangeAutoFormat](http://go.microsoft.com/fwlink/?LinkId=210967) 열거형에 나열됩니다.</span><span class="sxs-lookup"><span data-stu-id="c7799-216">Other formats are listed in the [XlRangeAutoFormat](http://go.microsoft.com/fwlink/?LinkId=210967) enumeration.</span></span>  
  
3.  <span data-ttu-id="c7799-217">1단계의 문을 다음 코드와 비교합니다. 이 코드는 [!INCLUDE[csharp_orcas_long](~/includes/csharp-orcas-long-md.md)] 이하 버전에 필요한 인수를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="c7799-217">Compare the statement in step 1 with the following code, which shows the arguments that are required in [!INCLUDE[csharp_orcas_long](~/includes/csharp-orcas-long-md.md)] or earlier versions.</span></span>  
  
     <span data-ttu-id="c7799-218">[!code-cs[csProgGuideOfficeHowTo#17](../../../csharp/programming-guide/interop/codesnippet/CSharp/how-to-access-office-onterop-objects_16.cs)]</span><span class="sxs-lookup"><span data-stu-id="c7799-218">[!code-cs[csProgGuideOfficeHowTo#17](../../../csharp/programming-guide/interop/codesnippet/CSharp/how-to-access-office-onterop-objects_16.cs)]</span></span>  
  
## <a name="example"></a><span data-ttu-id="c7799-219">예제</span><span class="sxs-lookup"><span data-stu-id="c7799-219">Example</span></span>  
 <span data-ttu-id="c7799-220">다음 코드에서는 전체 예제를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="c7799-220">The following code shows the complete example.</span></span>  
  
 <span data-ttu-id="c7799-221">[!code-cs[csProgGuideOfficeHowTo#18](../../../csharp/programming-guide/interop/codesnippet/CSharp/how-to-access-office-onterop-objects_17.cs)]</span><span class="sxs-lookup"><span data-stu-id="c7799-221">[!code-cs[csProgGuideOfficeHowTo#18](../../../csharp/programming-guide/interop/codesnippet/CSharp/how-to-access-office-onterop-objects_17.cs)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c7799-222">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c7799-222">See Also</span></span>  
 <span data-ttu-id="c7799-223"><xref:System.Type.Missing?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="c7799-223"><xref:System.Type.Missing?displayProperty=fullName></span></span>   
 <span data-ttu-id="c7799-224">[dynamic](../../../csharp/language-reference/keywords/dynamic.md) </span><span class="sxs-lookup"><span data-stu-id="c7799-224">[dynamic](../../../csharp/language-reference/keywords/dynamic.md) </span></span>  
 <span data-ttu-id="c7799-225">[dynamic 형식 사용](../../../csharp/programming-guide/types/using-type-dynamic.md) </span><span class="sxs-lookup"><span data-stu-id="c7799-225">[Using Type dynamic](../../../csharp/programming-guide/types/using-type-dynamic.md) </span></span>  
 <span data-ttu-id="c7799-226">[명명된 인수 및 선택적 인수](../../../csharp/programming-guide/classes-and-structs/named-and-optional-arguments.md) </span><span class="sxs-lookup"><span data-stu-id="c7799-226">[Named and Optional Arguments](../../../csharp/programming-guide/classes-and-structs/named-and-optional-arguments.md) </span></span>  
 [<span data-ttu-id="c7799-227">방법: Office 프로그래밍에서 명명된 인수 및 선택적 인수 사용</span><span class="sxs-lookup"><span data-stu-id="c7799-227">How to: Use Named and Optional Arguments in Office Programming</span></span>](../../../csharp/programming-guide/classes-and-structs/how-to-use-named-and-optional-arguments-in-office-programming.md)

