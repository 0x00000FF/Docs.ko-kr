---
title: Visual Studio에서 WPF 응용 프로그램 만들기
ms.date: 04/12/2018
dev_langs:
- csharp
- vb
helpviewer_keywords:
- getting started [WPF], WPF
- WPF [WPF], getting started
ms.assetid: b96bed40-8946-4285-8fe4-88045ab854ed
author: mairaw
ms.author: mairaw
ms.openlocfilehash: a8f806a1f1f7840f21e82d77d1b639b9318259e7
ms.sourcegitcommit: a885cc8c3e444ca6471348893d5373c6e9e49a47
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/06/2018
ms.locfileid: "43885183"
---
# <a name="walkthrough-my-first-wpf-desktop-application"></a><span data-ttu-id="1eaec-102">연습: 내 첫 WPF 데스크톱 응용 프로그램</span><span class="sxs-lookup"><span data-stu-id="1eaec-102">Walkthrough: My first WPF desktop application</span></span>

<span data-ttu-id="1eaec-103">이 문서에서는 대부분의 WPF 응용 프로그램에 공통 된 요소를 포함 하는 간단한 Windows Presentation Foundation (WPF) 응용 프로그램을 개발 하는 방법을 보여 줍니다: Extensible Application Markup Language (XAML) 태그, 코드 숨김, 응용 프로그램 정의 컨트롤, 레이아웃, 데이터 바인딩 및 스타일.</span><span class="sxs-lookup"><span data-stu-id="1eaec-103">This article shows you how to develop a simple Windows Presentation Foundation (WPF) application that includes the elements that are common to most WPF applications: Extensible Application Markup Language (XAML) markup, code-behind, application definitions, controls, layout, data binding, and styles.</span></span>

<span data-ttu-id="1eaec-104">이 연습에는 다음 단계가 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1eaec-104">This walkthrough includes the following steps:</span></span>

- <span data-ttu-id="1eaec-105">응용 프로그램의 UI (사용자 인터페이스) 모양에 XAML을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="1eaec-105">Use XAML to design the appearance of the application's user interface (UI).</span></span>

- <span data-ttu-id="1eaec-106">응용 프로그램의 동작을 작성 하기 위해 코드를 작성 합니다.</span><span class="sxs-lookup"><span data-stu-id="1eaec-106">Write code to build the application's behavior.</span></span>

- <span data-ttu-id="1eaec-107">응용 프로그램을 관리 하기 위한 응용 프로그램 정을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="1eaec-107">Create an application definition to manage the application.</span></span>

- <span data-ttu-id="1eaec-108">컨트롤을 추가 하 고 응용 프로그램 UI를 작성 하는 레이아웃을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="1eaec-108">Add controls and create the layout to compose the application UI.</span></span>

- <span data-ttu-id="1eaec-109">응용 프로그램의 UI 전체에서 일관 된 모양을 위해 스타일을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="1eaec-109">Create styles for a consistent appearance throughout an application's UI.</span></span>

- <span data-ttu-id="1eaec-110">둘 다 UI 데이터를 채우고 데이터와 동기화 하는 UI를 보존 하는 데이터에 UI를 바인딩하십시오.</span><span class="sxs-lookup"><span data-stu-id="1eaec-110">Bind the UI to data to both populate the UI from data and keep the data and UI synchronized.</span></span>

<span data-ttu-id="1eaec-111">연습의 끝에서 독립 실행형 Windows 응용 프로그램 사용자가 선택한 사용자에 대 한 경비 보고서를 볼 수 있도록 작성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1eaec-111">By the end of the walkthrough, you'll have built a standalone Windows application that allows users to view expense reports for selected people.</span></span> <span data-ttu-id="1eaec-112">응용 프로그램은 브라우저 스타일 창에서 호스트 되는 여러 WPF 페이지로 구성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1eaec-112">The application is composed of several WPF pages that are hosted in a browser-style window.</span></span>

> [!TIP]
> <span data-ttu-id="1eaec-113">이 연습을 빌드하는 데 사용 하는 샘플 코드는 Visual Basic 및 C#에서 사용할 수 있습니다 [WPF 응용 프로그램 빌드 소개](https://go.microsoft.com/fwlink/?LinkID=160008)합니다.</span><span class="sxs-lookup"><span data-stu-id="1eaec-113">The sample code that is used to build this walkthrough is available for both Visual Basic and C# at [Introduction to Building WPF Applications](https://go.microsoft.com/fwlink/?LinkID=160008).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="1eaec-114">전제 조건</span><span class="sxs-lookup"><span data-stu-id="1eaec-114">Prerequisites</span></span>

- <span data-ttu-id="1eaec-115">Visual Studio 2012 이상</span><span class="sxs-lookup"><span data-stu-id="1eaec-115">Visual Studio 2012 or later</span></span>

<span data-ttu-id="1eaec-116">Visual Studio의 최신 버전을 설치 하는 방법에 대 한 자세한 내용은 참조 하세요. [Visual Studio 설치](/visualstudio/install/install-visual-studio)합니다.</span><span class="sxs-lookup"><span data-stu-id="1eaec-116">For more information about installing the latest version of Visual Studio, see [Install Visual Studio](/visualstudio/install/install-visual-studio).</span></span>

## <a name="create-the-application-project"></a><span data-ttu-id="1eaec-117">응용 프로그램 프로젝트 만들기</span><span class="sxs-lookup"><span data-stu-id="1eaec-117">Create the application project</span></span>

<span data-ttu-id="1eaec-118">첫 번째 단계는 응용 프로그램 정의 두 페이지 및 이미지를 포함 하는 응용 프로그램 인프라를 만드는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="1eaec-118">The first step is to create the application infrastructure, which includes an application definition, two pages, and an image.</span></span>

1. <span data-ttu-id="1eaec-119">Visual Basic 또는 Visual C#에서 새 WPF 응용 프로그램 프로젝트를 만듭니다 **`ExpenseIt`**:</span><span class="sxs-lookup"><span data-stu-id="1eaec-119">Create a new WPF Application project in Visual Basic or Visual C# named **`ExpenseIt`**:</span></span>

   1. <span data-ttu-id="1eaec-120">Visual Studio를 열고 선택 **파일** > **새로 만들기** > **프로젝트**합니다.</span><span class="sxs-lookup"><span data-stu-id="1eaec-120">Open Visual Studio and select **File** > **New** > **Project**.</span></span>

      <span data-ttu-id="1eaec-121">합니다 **새 프로젝트** 대화 상자가 열립니다.</span><span class="sxs-lookup"><span data-stu-id="1eaec-121">The **New Project** dialog opens.</span></span>

   2. <span data-ttu-id="1eaec-122">아래는 **설치 됨** 범주를 확장 합니다 **Visual C#** 또는 **Visual Basic** 노드를 선택한 후 **Windows 클래식 바탕 화면**.</span><span class="sxs-lookup"><span data-stu-id="1eaec-122">Under the **Installed** category, expand either the **Visual C#** or **Visual Basic** node, and then select **Windows Classic Desktop**.</span></span>

   3. <span data-ttu-id="1eaec-123">선택 된 **WPF 앱 (.NET Framework)** 템플릿.</span><span class="sxs-lookup"><span data-stu-id="1eaec-123">Select the **WPF App (.NET Framework)** template.</span></span> <span data-ttu-id="1eaec-124">이름을 입력 **`ExpenseIt`** 선택한 후 **확인**합니다.</span><span class="sxs-lookup"><span data-stu-id="1eaec-124">Enter the name **`ExpenseIt`** and then select **OK**.</span></span>

      ![WPF 앱이 선택 된 새 프로젝트 대화 상자](media/new-project-dialog.png)

      <span data-ttu-id="1eaec-126">Visual Studio 프로젝트를 만들고 이라는 기본 응용 프로그램 창에 대 한 디자이너를 엽니다 **MainWindow.xaml**합니다.</span><span class="sxs-lookup"><span data-stu-id="1eaec-126">Visual Studio creates the project and opens the designer for the default application window named **MainWindow.xaml**.</span></span>

   > [!NOTE]
   > <span data-ttu-id="1eaec-127">이 연습에서는 <xref:System.Windows.Controls.DataGrid> 컨트롤 이상.NET Framework 4에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1eaec-127">This walkthrough uses the <xref:System.Windows.Controls.DataGrid> control that is available in the .NET Framework 4 and later.</span></span> <span data-ttu-id="1eaec-128">프로젝트가.NET Framework 4를 대상으로 하는지 이상 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1eaec-128">Be sure that your project targets the .NET Framework 4 or later.</span></span> <span data-ttu-id="1eaec-129">자세한 내용은 [방법: 한 버전의 .NET Framework를 대상으로 지정](/visualstudio/ide/how-to-target-a-version-of-the-dotnet-framework)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="1eaec-129">For more information, see [How to: Target a Version of the .NET Framework](/visualstudio/ide/how-to-target-a-version-of-the-dotnet-framework).</span></span>

2. <span data-ttu-id="1eaec-130">오픈 *Application.xaml* (Visual Basic) 또는 *App.xaml* (C#).</span><span class="sxs-lookup"><span data-stu-id="1eaec-130">Open *Application.xaml* (Visual Basic) or *App.xaml* (C#).</span></span>

    <span data-ttu-id="1eaec-131">이 XAML 파일이 WPF 응용 프로그램 및 모든 응용 프로그램 리소스를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="1eaec-131">This XAML file defines a WPF application and any application resources.</span></span> <span data-ttu-id="1eaec-132">또한 자동으로 표시 하는 UI를 지정 하려면이 파일을 사용 응용 프로그램을 시작 합니다. 이 예에서 *MainWindow.xaml*합니다.</span><span class="sxs-lookup"><span data-stu-id="1eaec-132">You also use this file to specify the UI that automatically shows when the application starts; in this case, *MainWindow.xaml*.</span></span>

    <span data-ttu-id="1eaec-133">에 XAML Visual Basic에서 다음과 같이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1eaec-133">Your XAML should look like this in Visual Basic:</span></span>

    [!code-xaml[ExpenseIt#1_A](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt1_A/Application.xaml#1_a)]

    <span data-ttu-id="1eaec-134">C#에서는 다음과 같이 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="1eaec-134">Or like this in C#:</span></span>

    [!code-xaml[ExpenseIt#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt/App.xaml#1)]

3. <span data-ttu-id="1eaec-135">오픈 *MainWindow.xaml*합니다.</span><span class="sxs-lookup"><span data-stu-id="1eaec-135">Open *MainWindow.xaml*.</span></span>

    <span data-ttu-id="1eaec-136">이 XAML 파일은 응용 프로그램의 주 창이 하 고 페이지에서 만든 콘텐츠를 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="1eaec-136">This XAML file is the main window of your application and displays content created in pages.</span></span> <span data-ttu-id="1eaec-137"><xref:System.Windows.Window> 클래스의 제목, 크기 또는 아이콘 같은 창의 속성을 정의 하 고 닫기 또는 숨기기와 같은 이벤트를 처리 합니다.</span><span class="sxs-lookup"><span data-stu-id="1eaec-137">The <xref:System.Windows.Window> class defines the properties of a window, such as its title, size, or icon, and handles events, such as closing or hiding.</span></span>

4. <span data-ttu-id="1eaec-138">변경 된 <xref:System.Windows.Window> 요소는 <xref:System.Windows.Navigation.NavigationWindow>다음 XAML과 같이:</span><span class="sxs-lookup"><span data-stu-id="1eaec-138">Change the <xref:System.Windows.Window> element to a <xref:System.Windows.Navigation.NavigationWindow>, as shown in the following XAML:</span></span>

   ```xaml
   <NavigationWindow x:Class="ExpenseIt.MainWindow"
        xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
        xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
        ...
   </NavigationWindow>
   ```

   <span data-ttu-id="1eaec-139">이 앱은 사용자 입력에 따라 다른 콘텐츠를 탐색 합니다.</span><span class="sxs-lookup"><span data-stu-id="1eaec-139">This app navigates to different content depending on the user input.</span></span> <span data-ttu-id="1eaec-140">이 인해 주 <xref:System.Windows.Window> 로 변경 해야 하는 경우는 <xref:System.Windows.Navigation.NavigationWindow>합니다.</span><span class="sxs-lookup"><span data-stu-id="1eaec-140">This is why the main <xref:System.Windows.Window> needs to be changed to a <xref:System.Windows.Navigation.NavigationWindow>.</span></span> <span data-ttu-id="1eaec-141"><xref:System.Windows.Navigation.NavigationWindow> 모든 속성을 상속 <xref:System.Windows.Window>합니다.</span><span class="sxs-lookup"><span data-stu-id="1eaec-141"><xref:System.Windows.Navigation.NavigationWindow> inherits all the properties of <xref:System.Windows.Window>.</span></span> <span data-ttu-id="1eaec-142"><xref:System.Windows.Navigation.NavigationWindow> 의 인스턴스를 만들고 XAML 파일의 요소를 <xref:System.Windows.Navigation.NavigationWindow> 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="1eaec-142">The <xref:System.Windows.Navigation.NavigationWindow> element in the XAML file creates an instance of the <xref:System.Windows.Navigation.NavigationWindow> class.</span></span> <span data-ttu-id="1eaec-143">자세한 내용은 [탐색 개요](../../../../docs/framework/wpf/app-development/navigation-overview.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="1eaec-143">For more information, see [Navigation overview](../../../../docs/framework/wpf/app-development/navigation-overview.md).</span></span>

5. <span data-ttu-id="1eaec-144">다음 속성을 변경 합니다 <xref:System.Windows.Navigation.NavigationWindow> 요소:</span><span class="sxs-lookup"><span data-stu-id="1eaec-144">Change the following properties on the <xref:System.Windows.Navigation.NavigationWindow> element:</span></span>

    - <span data-ttu-id="1eaec-145">설정 된 <xref:System.Windows.Window.Title%2A> 속성을 "`ExpenseIt`"입니다.</span><span class="sxs-lookup"><span data-stu-id="1eaec-145">Set the <xref:System.Windows.Window.Title%2A> property to "`ExpenseIt`".</span></span>

    - <span data-ttu-id="1eaec-146">설정 된 <xref:System.Windows.FrameworkElement.Width%2A> 속성을 500 픽셀로 합니다.</span><span class="sxs-lookup"><span data-stu-id="1eaec-146">Set the <xref:System.Windows.FrameworkElement.Width%2A> property to 500 pixels.</span></span>

    - <span data-ttu-id="1eaec-147">설정 된 <xref:System.Windows.FrameworkElement.Height%2A> 속성을 350 픽셀로 합니다.</span><span class="sxs-lookup"><span data-stu-id="1eaec-147">Set the <xref:System.Windows.FrameworkElement.Height%2A> property to 350 pixels.</span></span>

    - <span data-ttu-id="1eaec-148">제거 된 <xref:System.Windows.Controls.Grid> 사이의 요소를 <xref:System.Windows.Navigation.NavigationWindow> 태그입니다.</span><span class="sxs-lookup"><span data-stu-id="1eaec-148">Remove the <xref:System.Windows.Controls.Grid> elements between the <xref:System.Windows.Navigation.NavigationWindow> tags.</span></span>

    <span data-ttu-id="1eaec-149">에 XAML Visual Basic에서 다음과 같이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1eaec-149">Your XAML should look like this in Visual Basic:</span></span>

    [!code-xaml[ExpenseIt#2_A](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt/MainWindow.xaml#2_a)]

    <span data-ttu-id="1eaec-150">C#에서는 다음과 같이 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="1eaec-150">Or like this in C#:</span></span>

    [!code-xaml[ExpenseIt#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt/MainWindow.xaml#2)]

6. <span data-ttu-id="1eaec-151">오픈 *MainWindow.xaml.vb* 하거나 *MainWindow.xaml.cs*합니다.</span><span class="sxs-lookup"><span data-stu-id="1eaec-151">Open *MainWindow.xaml.vb* or *MainWindow.xaml.cs*.</span></span>

    <span data-ttu-id="1eaec-152">이 파일에 선언 된 이벤트를 처리 하는 코드를 포함 하는 코드 숨김 파일은 *MainWindow.xaml*합니다.</span><span class="sxs-lookup"><span data-stu-id="1eaec-152">This file is a code-behind file that contains code to handle the events declared in *MainWindow.xaml*.</span></span> <span data-ttu-id="1eaec-153">이 파일에는 XAML에 정의된 창의 부분 클래스가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1eaec-153">This file contains a partial class for the window defined in XAML.</span></span>

7. <span data-ttu-id="1eaec-154">C#을 사용 하는 경우 변경 합니다 `MainWindow` 에서 파생 된 클래스 <xref:System.Windows.Navigation.NavigationWindow>합니다.</span><span class="sxs-lookup"><span data-stu-id="1eaec-154">If you are using C#, change the `MainWindow` class to derive from <xref:System.Windows.Navigation.NavigationWindow>.</span></span> <span data-ttu-id="1eaec-155">(Visual basic에서는 자동으로 이루어집니다 XAML에서 창을 변경 하면 됩니다.)</span><span class="sxs-lookup"><span data-stu-id="1eaec-155">(In Visual Basic, this happens automatically when you change the window in XAML.)</span></span>

   <span data-ttu-id="1eaec-156">코드는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="1eaec-156">Your code should look like this:</span></span>

   [!code-csharp[ExpenseIt#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt/MainWindow.xaml.cs#3)]
   [!code-vb[ExpenseIt#3](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt1_A/MainWindow.xaml.vb#3)]

   > [!TIP]
   > <span data-ttu-id="1eaec-157">C#과 Visual Basic에서 샘플 코드의 코드 언어를 전환할 수 있습니다 합니다 **언어** 이 문서의 상단 오른쪽에 드롭다운 합니다.</span><span class="sxs-lookup"><span data-stu-id="1eaec-157">You can toggle the code language of the sample code between C# and Visual Basic in the **Language** drop-down on the upper right side of this article.</span></span>

## <a name="add-files-to-the-application"></a><span data-ttu-id="1eaec-158">응용 프로그램에 파일 추가</span><span class="sxs-lookup"><span data-stu-id="1eaec-158">Add files to the application</span></span>

<span data-ttu-id="1eaec-159">이 섹션에서는 응용 프로그램에 두 페이지와 이미지를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="1eaec-159">In this section, you'll add two pages and an image to the application.</span></span>

1. <span data-ttu-id="1eaec-160">프로젝트에 새 WPF 페이지를 추가 하 고 이름을 *`ExpenseItHome.xaml`*:</span><span class="sxs-lookup"><span data-stu-id="1eaec-160">Add a new WPF page to the project, and name it *`ExpenseItHome.xaml`*:</span></span>

   1. <span data-ttu-id="1eaec-161">**솔루션 탐색기**를 마우스 오른쪽 단추로 클릭 합니다 **`ExpenseIt`** 선택한 프로젝트 노드 **추가** > **페이지**합니다.</span><span class="sxs-lookup"><span data-stu-id="1eaec-161">In **Solution Explorer**, right-click on the **`ExpenseIt`** project node and choose **Add** > **Page**.</span></span>

   1. <span data-ttu-id="1eaec-162">에 **새 항목 추가** 대화 상자에서를 **페이지 (WPF)** 템플릿을 이미 선택 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1eaec-162">In the **Add New Item** dialog, the **Page (WPF)** template is already selected.</span></span> <span data-ttu-id="1eaec-163">이름을 입력 **`ExpenseItHome`** 를 선택한 후 **추가**합니다.</span><span class="sxs-lookup"><span data-stu-id="1eaec-163">Enter the name **`ExpenseItHome`**, and then select **Add**.</span></span>

    <span data-ttu-id="1eaec-164">이 페이지에는 응용 프로그램을 시작할 때 표시 되는 첫 번째 페이지가입니다.</span><span class="sxs-lookup"><span data-stu-id="1eaec-164">This page is the first page that's displayed when the application is launched.</span></span> <span data-ttu-id="1eaec-165">비용 보고서를 표시 하려면를 선택 하 게 목록이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1eaec-165">It will show a list of people to select from, to show an expense report for.</span></span>

2. <span data-ttu-id="1eaec-166">오픈 *`ExpenseItHome.xaml`* 합니다.</span><span class="sxs-lookup"><span data-stu-id="1eaec-166">Open *`ExpenseItHome.xaml`*.</span></span>

3. <span data-ttu-id="1eaec-167">설정 된 <xref:System.Windows.Controls.Page.Title%2A> 에 "`ExpenseIt - Home`"입니다.</span><span class="sxs-lookup"><span data-stu-id="1eaec-167">Set the <xref:System.Windows.Controls.Page.Title%2A> to "`ExpenseIt - Home`".</span></span>

    <span data-ttu-id="1eaec-168">에 XAML Visual Basic에서 다음과 같이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1eaec-168">Your XAML should look like this in Visual Basic:</span></span>

    [!code-xaml[ExpenseIt#6_A](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt1_A/ExpenseItHome.xaml#6_a)]

    <span data-ttu-id="1eaec-169">C#에서는 다음과 같이 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="1eaec-169">Or this in C#:</span></span>

    [!code-xaml[ExpenseIt#6](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt2/ExpenseItHome.xaml#6)]

4. <span data-ttu-id="1eaec-170">오픈 *MainWindow.xaml*합니다.</span><span class="sxs-lookup"><span data-stu-id="1eaec-170">Open *MainWindow.xaml*.</span></span>

5. <span data-ttu-id="1eaec-171">설정 합니다 <xref:System.Windows.Navigation.NavigationWindow.Source%2A> 속성에는 <xref:System.Windows.Navigation.NavigationWindow> 에 "`ExpenseItHome.xaml`"입니다.</span><span class="sxs-lookup"><span data-stu-id="1eaec-171">Set the <xref:System.Windows.Navigation.NavigationWindow.Source%2A> property on the <xref:System.Windows.Navigation.NavigationWindow> to "`ExpenseItHome.xaml`".</span></span>

    <span data-ttu-id="1eaec-172">이 설정 *`ExpenseItHome.xaml`* 응용 프로그램을 시작할 때 열리는 첫 번째 페이지 수입니다.</span><span class="sxs-lookup"><span data-stu-id="1eaec-172">This sets *`ExpenseItHome.xaml`* to be the first page opened when the application starts.</span></span> <span data-ttu-id="1eaec-173">에 XAML Visual Basic에서 다음과 같이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1eaec-173">Your XAML should look like this in Visual Basic:</span></span>

    [!code-xaml[ExpenseIt#7_A](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt1_A/MainWindow.xaml#7_a)]

    <span data-ttu-id="1eaec-174">C#에서는 다음과 같이 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="1eaec-174">Or this in C#:</span></span>

    [!code-xaml[ExpenseIt#7](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt2/MainWindow.xaml#7)]

   > [!TIP]
   > <span data-ttu-id="1eaec-175">설정할 수도 있습니다는 **원본** 속성에는 **기타** 범주의 합니다 **속성** 창.</span><span class="sxs-lookup"><span data-stu-id="1eaec-175">You can also set the **Source** property in the **Miscellaneous** category of the **Properties** window.</span></span>
   >
   > ![속성 창에서 source 속성](media/properties-source.png)

6. <span data-ttu-id="1eaec-177">프로젝트에 새 WPF의 다른 페이지를 추가 하 고 이름을 *ExpenseReportPage.xaml*::</span><span class="sxs-lookup"><span data-stu-id="1eaec-177">Add another new WPF page to the project, and name it *ExpenseReportPage.xaml*::</span></span>

   1. <span data-ttu-id="1eaec-178">**솔루션 탐색기**를 마우스 오른쪽 단추로 클릭 합니다 **`ExpenseIt`** 선택한 프로젝트 노드 **추가** > **페이지**합니다.</span><span class="sxs-lookup"><span data-stu-id="1eaec-178">In **Solution Explorer**, right-click on the **`ExpenseIt`** project node and choose **Add** > **Page**.</span></span>

   1. <span data-ttu-id="1eaec-179">에 **새 항목 추가** 대화 상자에서를 **페이지 (WPF)** 템플릿을 이미 선택 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1eaec-179">In the **Add New Item** dialog, the **Page (WPF)** template is already selected.</span></span> <span data-ttu-id="1eaec-180">이름을 입력 **ExpenseReportPage**를 선택한 후 **추가**합니다.</span><span class="sxs-lookup"><span data-stu-id="1eaec-180">Enter the name **ExpenseReportPage**, and then select **Add**.</span></span>

    <span data-ttu-id="1eaec-181">이 페이지에서 선택 된 사람의 비용 보고서에 표시 됩니다는 **`ExpenseItHome`** 페이지입니다.</span><span class="sxs-lookup"><span data-stu-id="1eaec-181">This page will show the expense report for the person that is selected on the **`ExpenseItHome`** page.</span></span>

7. <span data-ttu-id="1eaec-182">*ExpenseReportPage.xaml*을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="1eaec-182">Open *ExpenseReportPage.xaml*.</span></span>

8. <span data-ttu-id="1eaec-183">설정 된 <xref:System.Windows.Controls.Page.Title%2A> 에 "`ExpenseIt - View Expense`"입니다.</span><span class="sxs-lookup"><span data-stu-id="1eaec-183">Set the <xref:System.Windows.Controls.Page.Title%2A> to "`ExpenseIt - View Expense`".</span></span>

    <span data-ttu-id="1eaec-184">에 XAML Visual Basic에서 다음과 같이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1eaec-184">Your XAML should look like this in Visual Basic:</span></span>

    [!code-xaml[ExpenseIt#4_A](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt1_A/ExpenseReportPage.xaml#4_a)]

    <span data-ttu-id="1eaec-185">C#에서는 다음과 같이 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="1eaec-185">Or this in C#:</span></span>

    [!code-xaml[ExpenseIt#4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt/ExpenseReportPage.xaml#4)]

9. <span data-ttu-id="1eaec-186">오픈 *ExpenseItHome.xaml.vb* 하 고 *ExpenseReportPage.xaml.vb*, 또는 *ExpenseItHome.xaml.cs* 및 *ExpenseReportPage.xaml.cs*.</span><span class="sxs-lookup"><span data-stu-id="1eaec-186">Open *ExpenseItHome.xaml.vb* and *ExpenseReportPage.xaml.vb*, or *ExpenseItHome.xaml.cs* and *ExpenseReportPage.xaml.cs*.</span></span>

    <span data-ttu-id="1eaec-187">새 페이지 파일을 만들려면 Visual Studio 자동으로 만듭니다는 *코드 숨김* 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="1eaec-187">When you create a new Page file, Visual Studio automatically creates a *code-behind* file.</span></span> <span data-ttu-id="1eaec-188">이러한 코드 숨김 파일은 사용자 입력에 응답하기 위한 논리를 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="1eaec-188">These code-behind files handle the logic for responding to user input.</span></span>

    <span data-ttu-id="1eaec-189">코드에 대 한 다음과 같아야 **`ExpenseItHome`**:</span><span class="sxs-lookup"><span data-stu-id="1eaec-189">Your code should look like this for **`ExpenseItHome`**:</span></span>

    [!code-csharp[ExpenseIt#2_5](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt2/ExpenseItHome.xaml.cs#2_5)]
    [!code-vb[ExpenseIt#2_5](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt1_A/ExpenseItHome.xaml.vb#2_5)]

    <span data-ttu-id="1eaec-190">이 개체와 마찬가지로 **ExpenseReportPage**:</span><span class="sxs-lookup"><span data-stu-id="1eaec-190">And like this for **ExpenseReportPage**:</span></span>

    [!code-csharp[ExpenseIt#5](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt/ExpenseReportPage.xaml.cs#5)]
    [!code-vb[ExpenseIt#5](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt1_A/ExpenseReportPage.xaml.vb#5)]

10. <span data-ttu-id="1eaec-191">명명 된 이미지를 추가할 *watermark.png* 프로젝트입니다.</span><span class="sxs-lookup"><span data-stu-id="1eaec-191">Add an image named *watermark.png* to the project.</span></span> <span data-ttu-id="1eaec-192">사용자 고유의 이미지를 만들기, 샘플 코드에서 파일을 복사 하거나 가져올 수 있습니다 [여기](https://github.com/dotnet/docs/blob/master/docs/framework/wpf/getting-started/media/watermark.png)합니다.</span><span class="sxs-lookup"><span data-stu-id="1eaec-192">You can create your own image, copy the file from the sample code, or get it [here](https://github.com/dotnet/docs/blob/master/docs/framework/wpf/getting-started/media/watermark.png).</span></span>

   1. <span data-ttu-id="1eaec-193">프로젝트 노드를 마우스 오른쪽 단추로 클릭 하 고 선택 **추가** > **기존 항목**를 누르거나 **Shift**+**Alt** + **는**합니다.</span><span class="sxs-lookup"><span data-stu-id="1eaec-193">Right-click on the project node and select **Add** > **Existing Item**, or press **Shift**+**Alt**+**A**.</span></span>

   2. <span data-ttu-id="1eaec-194">에 **기존 항목 추가** 대화 상자를 사용 하 고 선택한 이미지 파일을 찾은 **추가**합니다.</span><span class="sxs-lookup"><span data-stu-id="1eaec-194">In the **Add Existing Item** dialog, browse to the image file you want to use, and then select **Add**.</span></span>

## <a name="build-and-run-the-application"></a><span data-ttu-id="1eaec-195">응용 프로그램 빌드 및 실행</span><span class="sxs-lookup"><span data-stu-id="1eaec-195">Build and run the application</span></span>

1. <span data-ttu-id="1eaec-196">를 빌드 및 응용 프로그램을 실행 하려면 키를 누릅니다 **F5** 누르거나 **디버깅 시작** 에서 **디버그** 메뉴.</span><span class="sxs-lookup"><span data-stu-id="1eaec-196">To build and run the application, press **F5** or select **Start Debugging** from the **Debug** menu.</span></span>

    <span data-ttu-id="1eaec-197">다음 그림에 나와 있는 응용 프로그램을 <xref:System.Windows.Navigation.NavigationWindow> 단추:</span><span class="sxs-lookup"><span data-stu-id="1eaec-197">The following illustration shows the application with the <xref:System.Windows.Navigation.NavigationWindow> buttons:</span></span>

    ![ExpenseIt 샘플 스크린샷](../../../../docs/framework/wpf/getting-started/media/gettingstartedfigure1.png)

2. <span data-ttu-id="1eaec-199">Visual Studio로 돌아가서 응용 프로그램을 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="1eaec-199">Close the application to return to Visual Studio.</span></span>

## <a name="create-the-layout"></a><span data-ttu-id="1eaec-200">레이아웃 만들기</span><span class="sxs-lookup"><span data-stu-id="1eaec-200">Create the layout</span></span>

<span data-ttu-id="1eaec-201">레이아웃 UI 요소를 배치 하는 순서가 지정 된 방법을 제공 하 고 UI의 크기를 조정할 때의 크기와 해당 요소의 위치를 관리 합니다.</span><span class="sxs-lookup"><span data-stu-id="1eaec-201">Layout provides an ordered way to place UI elements, and also manages the size and position of those elements when a UI is resized.</span></span> <span data-ttu-id="1eaec-202">일반적으로 다음 레이아웃 컨트롤 중 하나를 사용하여 레이아웃을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="1eaec-202">You typically create a layout with one of the following layout controls:</span></span>

- <xref:System.Windows.Controls.Canvas>
- <xref:System.Windows.Controls.DockPanel>
- <xref:System.Windows.Controls.Grid>
- <xref:System.Windows.Controls.StackPanel>
- <xref:System.Windows.Controls.VirtualizingStackPanel>
- <xref:System.Windows.Controls.WrapPanel>

<span data-ttu-id="1eaec-203">이러한 레이아웃 컨트롤은 각각 자식 요소의 특수 레이아웃 형식을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="1eaec-203">Each of these layout controls supports a special type of layout for its child elements.</span></span> <span data-ttu-id="1eaec-204">`ExpenseIt` 페이지 크기를 조정할 수, 하 고 각 페이지의 다른 요소와 함께 가로 및 세로로 정렬 된 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="1eaec-204">`ExpenseIt` pages can be resized, and each page has elements that are arranged horizontally and vertically alongside other elements.</span></span> <span data-ttu-id="1eaec-205">결과적으로 <xref:System.Windows.Controls.Grid> 응용 프로그램에 대 한 적합 한 레이아웃 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="1eaec-205">Consequently, the <xref:System.Windows.Controls.Grid> is the ideal layout element for the application.</span></span>

> [!TIP]
> <span data-ttu-id="1eaec-206">에 대 한 자세한 내용은 <xref:System.Windows.Controls.Panel> 요소를 참조 하세요 [Panel 개요](../../../../docs/framework/wpf/controls/panels-overview.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="1eaec-206">For more information about <xref:System.Windows.Controls.Panel> elements, see [Panels overview](../../../../docs/framework/wpf/controls/panels-overview.md).</span></span> <span data-ttu-id="1eaec-207">레이아웃에 대 한 자세한 내용은 참조 하세요. [레이아웃](../../../../docs/framework/wpf/advanced/layout.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="1eaec-207">For more information about layout, see [Layout](../../../../docs/framework/wpf/advanced/layout.md).</span></span>

<span data-ttu-id="1eaec-208">섹션에서 만든 단일 열 테이블을 세 개의 행과를 10-여백 (픽셀)를 사용 하 여 행 및 열 정의를 추가 하 여 합니다 <xref:System.Windows.Controls.Grid> 에 *`ExpenseItHome.xaml`* 합니다.</span><span class="sxs-lookup"><span data-stu-id="1eaec-208">In the section, you create a single-column table with three rows and a 10-pixel margin by adding column and row definitions to the <xref:System.Windows.Controls.Grid> in *`ExpenseItHome.xaml`*.</span></span>

1. <span data-ttu-id="1eaec-209">오픈 *`ExpenseItHome.xaml`* 합니다.</span><span class="sxs-lookup"><span data-stu-id="1eaec-209">Open *`ExpenseItHome.xaml`*.</span></span>

2. <span data-ttu-id="1eaec-210">설정 합니다 <xref:System.Windows.FrameworkElement.Margin%2A> 속성에는 <xref:System.Windows.Controls.Grid> "10,0,10,10" 왼쪽, 위쪽, 오른쪽 및 아래쪽 여백에 해당 하는 요소:</span><span class="sxs-lookup"><span data-stu-id="1eaec-210">Set the <xref:System.Windows.FrameworkElement.Margin%2A> property on the <xref:System.Windows.Controls.Grid> element to "10,0,10,10", which corresponds to left, top, right and bottom margins:</span></span>

   ```xaml
   <Grid Margin="10,0,10,10">
   ```

   > [!TIP]
   > <span data-ttu-id="1eaec-211">설정할 수도 있습니다는 **여백** 값을 **속성** 창 아래에 있는 합니다 **레이아웃** 범주:</span><span class="sxs-lookup"><span data-stu-id="1eaec-211">You can also set the **Margin** values in the **Properties** window, under the **Layout** category:</span></span>
   >
   > ![속성 창의 여백 값](media/properties-margin.png)

3. <span data-ttu-id="1eaec-213">간에 다음 XAML을 추가 합니다 <xref:System.Windows.Controls.Grid> 태그의 행 및 열 정의 만들려면:</span><span class="sxs-lookup"><span data-stu-id="1eaec-213">Add the following XAML between the <xref:System.Windows.Controls.Grid> tags to create the row and column definitions:</span></span>

    [!code-xaml[ExpenseIt#8](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt3/ExpenseItHome.xaml#8)]

    <span data-ttu-id="1eaec-214">합니다 <xref:System.Windows.Controls.RowDefinition.Height%2A> 로 설정 되어 두 행의 <xref:System.Windows.GridLength.Auto%2A>, 행의 콘텐츠를 기준으로 행 크기가 조정 되는 의미입니다.</span><span class="sxs-lookup"><span data-stu-id="1eaec-214">The <xref:System.Windows.Controls.RowDefinition.Height%2A> of two rows is set to <xref:System.Windows.GridLength.Auto%2A>, which means that the rows are sized base on the content in the rows.</span></span> <span data-ttu-id="1eaec-215">기본값 <xref:System.Windows.Controls.RowDefinition.Height%2A> 는 <xref:System.Windows.GridUnitType.Star> 행 높이가 사용 가능한 공간에 대 한 가중치 임을 의미 하는 크기 조정 합니다.</span><span class="sxs-lookup"><span data-stu-id="1eaec-215">The default <xref:System.Windows.Controls.RowDefinition.Height%2A> is <xref:System.Windows.GridUnitType.Star> sizing, which means that the row height is a weighted proportion of the available space.</span></span> <span data-ttu-id="1eaec-216">예를 들어 두 행을 <xref:System.Windows.Controls.RowDefinition.Height%2A> 의 "\*"를 사용 가능한 공간의 절반는 높이가 각각.</span><span class="sxs-lookup"><span data-stu-id="1eaec-216">For example if two rows each have a <xref:System.Windows.Controls.RowDefinition.Height%2A> of "\*", they each have a height that is half of the available space.</span></span>

    <span data-ttu-id="1eaec-217">프로그램 <xref:System.Windows.Controls.Grid> 다음 XAML 다음과 같아집니다.</span><span class="sxs-lookup"><span data-stu-id="1eaec-217">Your <xref:System.Windows.Controls.Grid> should now look like the following XAML:</span></span>

    [!code-xaml[ExpenseIt#9](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt3/ExpenseItHome.xaml#9)]

## <a name="add-controls"></a><span data-ttu-id="1eaec-218">컨트롤 추가</span><span class="sxs-lookup"><span data-stu-id="1eaec-218">Add controls</span></span>

<span data-ttu-id="1eaec-219">이 섹션에서는 홈 페이지 UI 사용자에 대 한 경비 보고서를 표시 하도록 선택할 수 있는 사람의 목록을 표시 하려면를 업데이트 합니다.</span><span class="sxs-lookup"><span data-stu-id="1eaec-219">In this section, you'll update the home page UI to show a list of people that a user can select from to show the expense report for.</span></span> <span data-ttu-id="1eaec-220">컨트롤은 사용자가 응용 프로그램과 상호 작용할 수 있게 하는 UI 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="1eaec-220">Controls are UI objects that allow users to interact with your application.</span></span> <span data-ttu-id="1eaec-221">자세한 내용은 [컨트롤](../../../../docs/framework/wpf/controls/index.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="1eaec-221">For more information, see [Controls](../../../../docs/framework/wpf/controls/index.md).</span></span>

<span data-ttu-id="1eaec-222">이 UI를 만들려면 다음 요소를 추가할 *`ExpenseItHome.xaml`*:</span><span class="sxs-lookup"><span data-stu-id="1eaec-222">To create this UI, you'll add the following elements to *`ExpenseItHome.xaml`*:</span></span>

- <span data-ttu-id="1eaec-223"><xref:System.Windows.Controls.ListBox> (목록에 대해 사용자).</span><span class="sxs-lookup"><span data-stu-id="1eaec-223"><xref:System.Windows.Controls.ListBox> (for the list of people).</span></span>
- <span data-ttu-id="1eaec-224"><xref:System.Windows.Controls.Label> (예: 목록 헤더의 경우)입니다.</span><span class="sxs-lookup"><span data-stu-id="1eaec-224"><xref:System.Windows.Controls.Label> (for the list header).</span></span>
- <span data-ttu-id="1eaec-225"><xref:System.Windows.Controls.Button> (클릭 하 목록에서 선택한 사람의 비용 보고서를 보려는).</span><span class="sxs-lookup"><span data-stu-id="1eaec-225"><xref:System.Windows.Controls.Button> (to click to view the expense report for the person that is selected in the list).</span></span>

<span data-ttu-id="1eaec-226">각 컨트롤의 행에 배치 되는 <xref:System.Windows.Controls.Grid> 설정 하 여는 <xref:System.Windows.Controls.Grid.Row%2A?displayProperty=nameWithType> 연결 된 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="1eaec-226">Each control is placed in a row of the <xref:System.Windows.Controls.Grid> by setting the <xref:System.Windows.Controls.Grid.Row%2A?displayProperty=nameWithType> attached property.</span></span> <span data-ttu-id="1eaec-227">연결 된 속성에 대 한 자세한 내용은 참조 하세요. [연결 된 속성 개요](../../../../docs/framework/wpf/advanced/attached-properties-overview.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="1eaec-227">For more information about attached properties, see [Attached Properties Overview](../../../../docs/framework/wpf/advanced/attached-properties-overview.md).</span></span>

1. <span data-ttu-id="1eaec-228">오픈 *`ExpenseItHome.xaml`* 합니다.</span><span class="sxs-lookup"><span data-stu-id="1eaec-228">Open *`ExpenseItHome.xaml`*.</span></span>

2. <span data-ttu-id="1eaec-229">사이 어딘가에 다음 XAML을 추가 합니다 <xref:System.Windows.Controls.Grid> 태그:</span><span class="sxs-lookup"><span data-stu-id="1eaec-229">Add the following XAML somewhere between the <xref:System.Windows.Controls.Grid> tags:</span></span>

   [!code-xaml[ExpenseIt#10](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt4/ExpenseItHome.xaml#10)]

   > [!TIP]
   > <span data-ttu-id="1eaec-230">끌어서 컨트롤을 만들 수도 있습니다는 **도구 상자** 창에서 디자인 창 및 다음에서 해당 속성을 설정 합니다 **속성** 창입니다.</span><span class="sxs-lookup"><span data-stu-id="1eaec-230">You can also create the controls by dragging them from the **Toolbox** window onto the design window, and then setting their properties in the **Properties** window.</span></span>

3. <span data-ttu-id="1eaec-231">응용 프로그램을 빌드 및 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="1eaec-231">Build and run the application.</span></span>

<span data-ttu-id="1eaec-232">다음 그림에서는 방금 만든 컨트롤을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="1eaec-232">The following illustration shows the controls you just created:</span></span>

![ExpenseIt 샘플 스크린샷](../../../../docs/framework/wpf/getting-started/media/gettingstartedfigure2.png)

## <a name="add-an-image-and-a-title"></a><span data-ttu-id="1eaec-234">이미지 및 제목 추가</span><span class="sxs-lookup"><span data-stu-id="1eaec-234">Add an image and a title</span></span>

<span data-ttu-id="1eaec-235">이 섹션에서는 이미지와 페이지 제목이 홈 페이지 UI를 업데이트 합니다.</span><span class="sxs-lookup"><span data-stu-id="1eaec-235">In this section, you'll update the home page UI with an image and a page title.</span></span>

1. <span data-ttu-id="1eaec-236">오픈 *`ExpenseItHome.xaml`* 합니다.</span><span class="sxs-lookup"><span data-stu-id="1eaec-236">Open *`ExpenseItHome.xaml`*.</span></span>

2. <span data-ttu-id="1eaec-237">다른 열을 추가 합니다 <xref:System.Windows.Controls.Grid.ColumnDefinitions%2A> 고정 <xref:System.Windows.Controls.ColumnDefinition.Width%2A> 230 픽셀인:</span><span class="sxs-lookup"><span data-stu-id="1eaec-237">Add another column to the <xref:System.Windows.Controls.Grid.ColumnDefinitions%2A> with a fixed <xref:System.Windows.Controls.ColumnDefinition.Width%2A> of 230 pixels:</span></span>

    [!code-xaml[ExpenseIt#11](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt5/ExpenseItHome.xaml#11)]

3. <span data-ttu-id="1eaec-238">다른 행을 추가 하는 <xref:System.Windows.Controls.Grid.RowDefinitions%2A>, 총 4 개의 행에 대 한 합니다.</span><span class="sxs-lookup"><span data-stu-id="1eaec-238">Add another row to the <xref:System.Windows.Controls.Grid.RowDefinitions%2A>, for a total of four rows:</span></span>

    [!code-xaml[ExpenseIt#11b](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt5/ExpenseItHome.xaml#11b)]

4. <span data-ttu-id="1eaec-239">컨트롤을 설정 하 여 두 번째 열으로 이동 합니다 <xref:System.Windows.Controls.Grid.Column%2A?displayProperty=nameWithType> 각 세 가지 컨트롤 (테두리, 목록 상자 및 단추)에서 1로 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="1eaec-239">Move the controls to the second column by setting the <xref:System.Windows.Controls.Grid.Column%2A?displayProperty=nameWithType> property to 1 in each of the three controls (Border, ListBox, and Button).</span></span>

5. <span data-ttu-id="1eaec-240">증가 시켜 각 컨트롤을 한 행 아래로 이동 해당 <xref:System.Windows.Controls.Grid.Row%2A?displayProperty=nameWithType> 1만 값입니다.</span><span class="sxs-lookup"><span data-stu-id="1eaec-240">Move each control down a row, by incrementing its <xref:System.Windows.Controls.Grid.Row%2A?displayProperty=nameWithType> value by 1.</span></span>

   <span data-ttu-id="1eaec-241">이제 세 가지 컨트롤에 대 한 XAML은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="1eaec-241">The XAML for the three controls now looks like this:</span></span>

    [!code-xaml[ExpenseIt#12](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt5/ExpenseItHome.xaml#12)]

6. <span data-ttu-id="1eaec-242">설정 합니다 <xref:System.Windows.Controls.Panel.Background%2A> 의 <xref:System.Windows.Controls.Grid> 되도록 합니다 *watermark.png* 사이 어딘가에 다음 XAML을 추가 하 여 이미지 파일을는 `<Grid>` 및 `</Grid>` 태그:</span><span class="sxs-lookup"><span data-stu-id="1eaec-242">Set the <xref:System.Windows.Controls.Panel.Background%2A> of the <xref:System.Windows.Controls.Grid> to be the *watermark.png* image file, by adding the following XAML somewhere between the `<Grid>` and `</Grid>` tags:</span></span>

    [!code-xaml[ExpenseIt#14](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt5/ExpenseItHome.xaml#14)]

7. <span data-ttu-id="1eaec-243">전에 <xref:System.Windows.Controls.Border> 요소를 추가 <xref:System.Windows.Controls.Label> 콘텐츠가 "View Expense Report"를 사용 하 여 합니다.</span><span class="sxs-lookup"><span data-stu-id="1eaec-243">Before the <xref:System.Windows.Controls.Border> element, add a <xref:System.Windows.Controls.Label> with the content "View Expense Report".</span></span> <span data-ttu-id="1eaec-244">페이지의 제목입니다.</span><span class="sxs-lookup"><span data-stu-id="1eaec-244">This is the title of the page.</span></span>

    [!code-xaml[ExpenseIt#13](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt5/ExpenseItHome.xaml#13)]

8. <span data-ttu-id="1eaec-245">응용 프로그램을 빌드 및 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="1eaec-245">Build and run the application.</span></span>

<span data-ttu-id="1eaec-246">다음 그림에서는 방금 추가한 새로운 결과 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="1eaec-246">The following illustration shows the results of what you just added:</span></span>

![ExpenseIt 샘플 스크린샷](../../../../docs/framework/wpf/getting-started/media/gettingstartedfigure3.png)

## <a name="add-code-to-handle-events"></a><span data-ttu-id="1eaec-248">이벤트를 처리 하는 코드를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="1eaec-248">Add code to handle events</span></span>

1. <span data-ttu-id="1eaec-249">오픈 *`ExpenseItHome.xaml`* 합니다.</span><span class="sxs-lookup"><span data-stu-id="1eaec-249">Open *`ExpenseItHome.xaml`*.</span></span>

2. <span data-ttu-id="1eaec-250">추가 된 <xref:System.Windows.Controls.Primitives.ButtonBase.Click> 이벤트 처리기를는 <xref:System.Windows.Controls.Button> 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="1eaec-250">Add a <xref:System.Windows.Controls.Primitives.ButtonBase.Click> event handler to the <xref:System.Windows.Controls.Button> element.</span></span> <span data-ttu-id="1eaec-251">자세한 내용은 [방법: 간단한 이벤트 처리기를 만들고](https://msdn.microsoft.com/library/b1456e07-9dec-4354-99cf-18666b64f480)합니다.</span><span class="sxs-lookup"><span data-stu-id="1eaec-251">For more information, see [How to: Create a simple event handler](https://msdn.microsoft.com/library/b1456e07-9dec-4354-99cf-18666b64f480).</span></span>

    [!code-xaml[ExpenseIt#15](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt6/ExpenseItHome.xaml#15)]

3. <span data-ttu-id="1eaec-252">오픈 *`ExpenseItHome.xaml.vb`* 하거나 *`ExpenseItHome.xaml.cs`* 합니다.</span><span class="sxs-lookup"><span data-stu-id="1eaec-252">Open *`ExpenseItHome.xaml.vb`* or *`ExpenseItHome.xaml.cs`*.</span></span>

4. <span data-ttu-id="1eaec-253">다음 코드를 추가 합니다 `ExpenseItHome` 단추를 추가 하는 클래스 이벤트 처리기를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="1eaec-253">Add the following code to the `ExpenseItHome` class to add a button click event handler.</span></span> <span data-ttu-id="1eaec-254">이벤트 처리기 열립니다는 **ExpenseReportPage** 페이지입니다.</span><span class="sxs-lookup"><span data-stu-id="1eaec-254">The event handler opens the **ExpenseReportPage** page.</span></span>

    [!code-csharp[ExpenseIt#16](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt6/ExpenseItHome.xaml.cs#16)]
    [!code-vb[ExpenseIt#16](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt6/ExpenseItHome.xaml.vb#16)]

## <a name="create-the-ui-for-expensereportpage"></a><span data-ttu-id="1eaec-255">ExpenseReportPage의 UI 만들기</span><span class="sxs-lookup"><span data-stu-id="1eaec-255">Create the UI for ExpenseReportPage</span></span>

<span data-ttu-id="1eaec-256">*ExpenseReportPage.xaml* 에서 선택한 사람의 비용 보고서를 표시 합니다 **`ExpenseItHome`** 페이지입니다.</span><span class="sxs-lookup"><span data-stu-id="1eaec-256">*ExpenseReportPage.xaml* displays the expense report for the person that's selected on the **`ExpenseItHome`** page.</span></span> <span data-ttu-id="1eaec-257">이 섹션에서는 UI를 만듭니다 **ExpenseReportPage**합니다.</span><span class="sxs-lookup"><span data-stu-id="1eaec-257">In this section, you'll create the UI for **ExpenseReportPage**.</span></span> <span data-ttu-id="1eaec-258">또한 배경 추가 하 고 다양 한 UI 요소에 색 채우기 합니다.</span><span class="sxs-lookup"><span data-stu-id="1eaec-258">You'll also add background and fill colors to the various UI elements.</span></span>

1. <span data-ttu-id="1eaec-259">*ExpenseReportPage.xaml*을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="1eaec-259">Open *ExpenseReportPage.xaml*.</span></span>

2. <span data-ttu-id="1eaec-260">간에 다음 XAML을 추가 합니다 <xref:System.Windows.Controls.Grid> 태그:</span><span class="sxs-lookup"><span data-stu-id="1eaec-260">Add the following XAML between the <xref:System.Windows.Controls.Grid> tags:</span></span>

    [!code-xaml[ExpenseIt#17](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt6/ExpenseReportPage.xaml#17)]

    <span data-ttu-id="1eaec-261">이 UI는 비슷합니다 *`ExpenseItHome.xaml`* 에서 보고서 데이터는 제외 하 고는 <xref:System.Windows.Controls.DataGrid>합니다.</span><span class="sxs-lookup"><span data-stu-id="1eaec-261">This UI is similar to *`ExpenseItHome.xaml`*, except the report data is displayed in a <xref:System.Windows.Controls.DataGrid>.</span></span>

3. <span data-ttu-id="1eaec-262">응용 프로그램을 빌드 및 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="1eaec-262">Build and run the application.</span></span>

    > [!NOTE]
    > <span data-ttu-id="1eaec-263">오류가 발생 하는 경우는 <xref:System.Windows.Controls.DataGrid> 찾을 수 없습니다 또는 존재 하지 않거나, 프로젝트가.NET Framework 4 이상을 대상으로 하는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="1eaec-263">If you get an error that the <xref:System.Windows.Controls.DataGrid> was not found or does not exist, make sure that your project targets the .NET Framework 4 or later.</span></span> <span data-ttu-id="1eaec-264">자세한 내용은 [방법: 한 버전의 .NET Framework를 대상으로 지정](/visualstudio/ide/how-to-target-a-version-of-the-dotnet-framework)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="1eaec-264">For more information, see [How to: Target a Version of the .NET Framework](/visualstudio/ide/how-to-target-a-version-of-the-dotnet-framework).</span></span>

4. <span data-ttu-id="1eaec-265">선택 된 **보기** 단추입니다.</span><span class="sxs-lookup"><span data-stu-id="1eaec-265">Select the **View** button.</span></span>

    <span data-ttu-id="1eaec-266">경비 보고서 페이지가 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="1eaec-266">The expense report page appears.</span></span> <span data-ttu-id="1eaec-267">또한 뒤로 탐색 단추를 사용할 수 있음을 알 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1eaec-267">Also notice that the back navigation button is enabled.</span></span>

<span data-ttu-id="1eaec-268">다음 그림에 추가 UI 요소를 보여 줍니다 *ExpenseReportPage.xaml*합니다.</span><span class="sxs-lookup"><span data-stu-id="1eaec-268">The following illustration shows the UI elements added to *ExpenseReportPage.xaml*.</span></span>

![ExpenseIt 샘플 스크린샷](../../../../docs/framework/wpf/getting-started/media/gettingstartedfigure4.png)

## <a name="style-controls"></a><span data-ttu-id="1eaec-270">컨트롤 스타일 지정</span><span class="sxs-lookup"><span data-stu-id="1eaec-270">Style controls</span></span>

<span data-ttu-id="1eaec-271">다양 한 요소의 모양이 UI에서 동일한 형식의 모든 요소에 대 한 자주 동일합니다.</span><span class="sxs-lookup"><span data-stu-id="1eaec-271">The appearance of various elements is often the same for all elements of the same type in a UI.</span></span> <span data-ttu-id="1eaec-272">UI를 사용 하 여 [스타일](../../../../docs/framework/wpf/controls/styling-and-templating.md) 을 여러 요소 간에 모양을 다시 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1eaec-272">UI uses [styles](../../../../docs/framework/wpf/controls/styling-and-templating.md) to make appearances reusable across multiple elements.</span></span> <span data-ttu-id="1eaec-273">스타일의 재사용 가능성 XAML 만들기 및 관리를 간소화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1eaec-273">The reusability of styles helps to simplify XAML creation and management.</span></span> <span data-ttu-id="1eaec-274">이 섹션에서는 이전 단계에서 정의된 요소별 특성을 스타일로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="1eaec-274">This section replaces the per-element attributes that were defined in previous steps with styles.</span></span>

1. <span data-ttu-id="1eaec-275">오픈 *Application.xaml* 하거나 *App.xaml*합니다.</span><span class="sxs-lookup"><span data-stu-id="1eaec-275">Open *Application.xaml* or *App.xaml*.</span></span>

2. <span data-ttu-id="1eaec-276">간에 다음 XAML을 추가 합니다 <xref:System.Windows.Application.Resources%2A?displayProperty=nameWithType> 태그:</span><span class="sxs-lookup"><span data-stu-id="1eaec-276">Add the following XAML between the <xref:System.Windows.Application.Resources%2A?displayProperty=nameWithType> tags:</span></span>

    [!code-xaml[ExpenseIt#18](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt7/App.xaml#18)]

    <span data-ttu-id="1eaec-277">이 XAML은 다음 스타일을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="1eaec-277">This XAML adds the following styles:</span></span>

    - <span data-ttu-id="1eaec-278">`headerTextStyle`: 페이지 제목 <xref:System.Windows.Controls.Label>의 형식을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="1eaec-278">`headerTextStyle`: To format the page title <xref:System.Windows.Controls.Label>.</span></span>

    - <span data-ttu-id="1eaec-279">`labelStyle`: <xref:System.Windows.Controls.Label> 컨트롤의 형식을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="1eaec-279">`labelStyle`: To format the <xref:System.Windows.Controls.Label> controls.</span></span>

    - <span data-ttu-id="1eaec-280">`columnHeaderStyle`: <xref:System.Windows.Controls.Primitives.DataGridColumnHeader>의 형식을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="1eaec-280">`columnHeaderStyle`: To format the <xref:System.Windows.Controls.Primitives.DataGridColumnHeader>.</span></span>

    - <span data-ttu-id="1eaec-281">`listHeaderStyle`: 목록 헤더 <xref:System.Windows.Controls.Border> 컨트롤의 형식을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="1eaec-281">`listHeaderStyle`: To format the list header <xref:System.Windows.Controls.Border> controls.</span></span>

    - <span data-ttu-id="1eaec-282">`listHeaderTextStyle`: 목록 헤더의 형식을 사용 하려면 <xref:System.Windows.Controls.Label>합니다.</span><span class="sxs-lookup"><span data-stu-id="1eaec-282">`listHeaderTextStyle`: To format the list header <xref:System.Windows.Controls.Label>.</span></span>

    - <span data-ttu-id="1eaec-283">`buttonStyle`: 서식을 지정 하려면 다음을 수행 합니다는 <xref:System.Windows.Controls.Button> 에서 `ExpenseItHome.xaml`합니다.</span><span class="sxs-lookup"><span data-stu-id="1eaec-283">`buttonStyle`: To format the <xref:System.Windows.Controls.Button> on `ExpenseItHome.xaml`.</span></span>

    <span data-ttu-id="1eaec-284">스타일의 자식 이며 리소스는는 <xref:System.Windows.Application.Resources%2A?displayProperty=nameWithType> 속성 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="1eaec-284">Notice that the styles are resources and children of the <xref:System.Windows.Application.Resources%2A?displayProperty=nameWithType> property element.</span></span> <span data-ttu-id="1eaec-285">이 위치에서 스타일은 응용 프로그램의 모든 요소에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="1eaec-285">In this location, the styles are applied to all the elements in an application.</span></span> <span data-ttu-id="1eaec-286">.NET Framework 응용 프로그램에서 리소스를 사용 하 여 예제를 참조 하세요 [사용 하 여 응용 프로그램 리소스](../../../../docs/framework/wpf/advanced/how-to-use-application-resources.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="1eaec-286">For an example of using resources in a .NET Framework application, see [Use Application Resources](../../../../docs/framework/wpf/advanced/how-to-use-application-resources.md).</span></span>

3. <span data-ttu-id="1eaec-287">오픈 *`ExpenseItHome.xaml`* 합니다.</span><span class="sxs-lookup"><span data-stu-id="1eaec-287">Open *`ExpenseItHome.xaml`*.</span></span>

4. <span data-ttu-id="1eaec-288">간의 대체는 <xref:System.Windows.Controls.Grid> 다음 XAML 사용 하 여 요소:</span><span class="sxs-lookup"><span data-stu-id="1eaec-288">Replace everything between the <xref:System.Windows.Controls.Grid> elements with the following XAML:</span></span>

    [!code-xaml[ExpenseIt#19](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt7/ExpenseItHome.xaml#19)]

    <span data-ttu-id="1eaec-289">스타일을 적용하면 각 컨트롤의 모양을 정의하는 <xref:System.Windows.VerticalAlignment> 및 <xref:System.Windows.Media.FontFamily> 와 같은 속성이 제거되고 바뀝니다.</span><span class="sxs-lookup"><span data-stu-id="1eaec-289">The properties such as <xref:System.Windows.VerticalAlignment> and <xref:System.Windows.Media.FontFamily> that define the look of each control are removed and replaced by applying the styles.</span></span> <span data-ttu-id="1eaec-290">예를 들어 합니다 `headerTextStyle` "View Expense Report" 적용할 <xref:System.Windows.Controls.Label>합니다.</span><span class="sxs-lookup"><span data-stu-id="1eaec-290">For example, the `headerTextStyle` is applied to the "View Expense Report" <xref:System.Windows.Controls.Label>.</span></span>

5. <span data-ttu-id="1eaec-291">*ExpenseReportPage.xaml*을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="1eaec-291">Open *ExpenseReportPage.xaml*.</span></span>

6. <span data-ttu-id="1eaec-292">간의 대체는 <xref:System.Windows.Controls.Grid> 다음 XAML 사용 하 여 요소:</span><span class="sxs-lookup"><span data-stu-id="1eaec-292">Replace everything between the <xref:System.Windows.Controls.Grid> elements with the following XAML:</span></span>

    [!code-xaml[ExpenseIt#20](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt7/ExpenseReportPage.xaml#20)]

    <span data-ttu-id="1eaec-293">이렇게 하면 <xref:System.Windows.Controls.Label> 및 <xref:System.Windows.Controls.Border> 요소에 스타일이 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="1eaec-293">This adds styles to the <xref:System.Windows.Controls.Label> and <xref:System.Windows.Controls.Border> elements.</span></span>

## <a name="bind-data-to-a-control"></a><span data-ttu-id="1eaec-294">컨트롤에 데이터 바인딩</span><span class="sxs-lookup"><span data-stu-id="1eaec-294">Bind data to a control</span></span>

<span data-ttu-id="1eaec-295">이 섹션에서는 다양 한 컨트롤에 바인딩된 XML 데이터를 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1eaec-295">In this section, you'll create the XML data that is bound to various controls.</span></span>

1. <span data-ttu-id="1eaec-296">오픈 *`ExpenseItHome.xaml`* 합니다.</span><span class="sxs-lookup"><span data-stu-id="1eaec-296">Open *`ExpenseItHome.xaml`*.</span></span>

2. <span data-ttu-id="1eaec-297">연 후 <xref:System.Windows.Controls.Grid> 요소를 만들려면 다음 XAML을 추가 <xref:System.Windows.Data.XmlDataProvider> 각 사용자에 대 한 데이터가 포함 된:</span><span class="sxs-lookup"><span data-stu-id="1eaec-297">After the opening <xref:System.Windows.Controls.Grid> element, add the following XAML to create an <xref:System.Windows.Data.XmlDataProvider> that contains the data for each person:</span></span>

    [!code-xaml[ExpenseIt#21](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt8/ExpenseItHome.xaml#21)]
    [!code-xaml[ExpenseIt#23](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt8/ExpenseItHome.xaml#23)]
    [!code-xaml[ExpenseIt#22](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt8/ExpenseItHome.xaml#22)]

    <span data-ttu-id="1eaec-298">으로 데이터가 생성 되었는지는 <xref:System.Windows.Controls.Grid> 리소스입니다.</span><span class="sxs-lookup"><span data-stu-id="1eaec-298">The data is created as a <xref:System.Windows.Controls.Grid> resource.</span></span> <span data-ttu-id="1eaec-299">일반적으로 파일로 로드되지만 편의상 데이터가 인라인으로 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="1eaec-299">Normally this would be loaded as a file, but for simplicity the data is added inline.</span></span>

3. <span data-ttu-id="1eaec-300">내 합니다 `<Grid.Resources>` 요소를 다음을 추가 합니다 <xref:System.Windows.DataTemplate>, 데이터를 표시 하는 방법을 정의 하는 <xref:System.Windows.Controls.ListBox>:</span><span class="sxs-lookup"><span data-stu-id="1eaec-300">Within the `<Grid.Resources>` element, add the following <xref:System.Windows.DataTemplate>, which defines how to display the data in the <xref:System.Windows.Controls.ListBox>:</span></span>

    [!code-xaml[ExpenseIt#21](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt8/ExpenseItHome.xaml#21)]
    [!code-xaml[ExpenseIt#24](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt8/ExpenseItHome.xaml#24)]
    [!code-xaml[ExpenseIt#22](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt8/ExpenseItHome.xaml#22)]

    <span data-ttu-id="1eaec-301">데이터 템플릿에 대 한 자세한 내용은 참조 하세요. [데이터 템플릿 개요](../../../../docs/framework/wpf/data/data-templating-overview.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="1eaec-301">For more information about data templates, see [Data templating overview](../../../../docs/framework/wpf/data/data-templating-overview.md).</span></span>

4. <span data-ttu-id="1eaec-302">기존 대체 <xref:System.Windows.Controls.ListBox> 다음 XAML을 사용 하 여:</span><span class="sxs-lookup"><span data-stu-id="1eaec-302">Replace the existing <xref:System.Windows.Controls.ListBox> with the following XAML:</span></span>

    [!code-xaml[ExpenseIt#25](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt8/ExpenseItHome.xaml#25)]

    <span data-ttu-id="1eaec-303">이 XAML에 바인딩합니다를 <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> 의 속성을 <xref:System.Windows.Controls.ListBox> 데이터 원본에으로 데이터 템플릿을 적용 하 고는 <xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A>.</span><span class="sxs-lookup"><span data-stu-id="1eaec-303">This XAML binds the <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> property of the <xref:System.Windows.Controls.ListBox> to the data source and applies the data template as the <xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A>.</span></span>

## <a name="connect-data-to-controls"></a><span data-ttu-id="1eaec-304">컨트롤에 데이터 연결</span><span class="sxs-lookup"><span data-stu-id="1eaec-304">Connect data to controls</span></span>

<span data-ttu-id="1eaec-305">선택한 이름을 검색 하는 코드를 다음을 추가 합니다 **`ExpenseItHome`** 페이지의 생성자에 전달 하 **ExpenseReportPage**합니다.</span><span class="sxs-lookup"><span data-stu-id="1eaec-305">Next, you'll add code to retrieve the name that's selected on the **`ExpenseItHome`** page and pass it to the constructor of **ExpenseReportPage**.</span></span> <span data-ttu-id="1eaec-306">**ExpenseReportPage** 컨트롤의 정의 전달 된 항목을 사용 하 여 데이터 컨텍스트를 설정에서 *ExpenseReportPage.xaml* 에 바인딩합니다.</span><span class="sxs-lookup"><span data-stu-id="1eaec-306">**ExpenseReportPage** sets its data context with the passed item, which is what the controls defined in *ExpenseReportPage.xaml* bind to.</span></span>

1. <span data-ttu-id="1eaec-307">*ExpenseReportPage.xaml.vb* 또는 *ExpenseReportPage.xaml.cs*를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="1eaec-307">Open *ExpenseReportPage.xaml.vb* or *ExpenseReportPage.xaml.cs*.</span></span>

2. <span data-ttu-id="1eaec-308">선택한 사람의 비용 보고서 데이터를 전달할 수 있도록 개체를 사용하는 생성자를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="1eaec-308">Add a constructor that takes an object so you can pass the expense report data of the selected person.</span></span>

    [!code-csharp[ExpenseIt#26](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt8/ExpenseReportPage.xaml.cs#26)]
    [!code-vb[ExpenseIt#26](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt8/ExpenseReportPage.xaml.vb#26)]

3. <span data-ttu-id="1eaec-309">오픈 *`ExpenseItHome.xaml.vb`* 하거나 *`ExpenseItHome.xaml.cs`* 합니다.</span><span class="sxs-lookup"><span data-stu-id="1eaec-309">Open *`ExpenseItHome.xaml.vb`* or *`ExpenseItHome.xaml.cs`*.</span></span>

4. <span data-ttu-id="1eaec-310">변경 된 <xref:System.Windows.Controls.Primitives.ButtonBase.Click> 선택한 사람의 비용 보고서 데이터를 전달 하 여 새 생성자를 호출 하도록 이벤트 처리기입니다.</span><span class="sxs-lookup"><span data-stu-id="1eaec-310">Change the <xref:System.Windows.Controls.Primitives.ButtonBase.Click> event handler to call the new constructor passing the expense report data of the selected person.</span></span>

    [!code-csharp[ExpenseIt#27](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt8/ExpenseItHome.xaml.cs#27)]
    [!code-vb[ExpenseIt#27](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt8/ExpenseItHome.xaml.vb#27)]

## <a name="style-data-with-data-templates"></a><span data-ttu-id="1eaec-311">데이터 템플릿 사용 하 여 데이터 스타일</span><span class="sxs-lookup"><span data-stu-id="1eaec-311">Style data with data templates</span></span>

<span data-ttu-id="1eaec-312">이 섹션에서는 데이터 템플릿을 사용 하 여 데이터 바인딩된 목록에 있는 각 항목에 대 한 UI를 업데이트 합니다.</span><span class="sxs-lookup"><span data-stu-id="1eaec-312">In this section, you'll update the UI for each item in the data-bound lists by using data templates.</span></span>

1. <span data-ttu-id="1eaec-313">*ExpenseReportPage.xaml*을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="1eaec-313">Open *ExpenseReportPage.xaml*.</span></span>

2. <span data-ttu-id="1eaec-314">"Name" 및 "Department" 콘텐츠 바인딩 <xref:System.Windows.Controls.Label> 요소를 사용 하는 적절 한 데이터 원본 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="1eaec-314">Bind the content of the "Name" and "Department" <xref:System.Windows.Controls.Label> elements to the appropriate data source property.</span></span> <span data-ttu-id="1eaec-315">데이터 바인딩에 대 한 자세한 내용은 참조 하세요. [데이터 바인딩 개요](../../../../docs/framework/wpf/data/data-binding-overview.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="1eaec-315">For more information about data binding, see [Data binding overview](../../../../docs/framework/wpf/data/data-binding-overview.md).</span></span>

    [!code-xaml[ExpenseIt#31](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt9/ExpenseReportPage.xaml#31)]

3. <span data-ttu-id="1eaec-316">연 후 <xref:System.Windows.Controls.Grid> 요소인 비용 보고서 데이터를 표시 하는 방법을 정의 하는 다음 데이터 템플릿을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="1eaec-316">After the opening <xref:System.Windows.Controls.Grid> element, add the following data templates, which define how to display the expense report data:</span></span>

    [!code-xaml[ExpenseIt#30](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt9/ExpenseReportPage.xaml#30)]

4. <span data-ttu-id="1eaec-317">대체는 <xref:System.Windows.Controls.DataGridTextColumn> 요소 <xref:System.Windows.Controls.DataGridTemplateColumn> 아래에서 <xref:System.Windows.Controls.DataGrid> 요소에 템플릿을 적용 합니다.</span><span class="sxs-lookup"><span data-stu-id="1eaec-317">Replace the <xref:System.Windows.Controls.DataGridTextColumn> elements with <xref:System.Windows.Controls.DataGridTemplateColumn> under the <xref:System.Windows.Controls.DataGrid> element and apply the templates to them.</span></span>

    [!code-xaml[ExpenseIt#32](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt9/ExpenseReportPage.xaml#32)]

5. <span data-ttu-id="1eaec-318">응용 프로그램을 빌드 및 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="1eaec-318">Build and run the application.</span></span>

6. <span data-ttu-id="1eaec-319">사용자를 선택 하 고 다음을 선택 합니다 **보기** 단추입니다.</span><span class="sxs-lookup"><span data-stu-id="1eaec-319">Select a person and then select the **View** button.</span></span>

<span data-ttu-id="1eaec-320">다음 그림에서는 두 페이지는 `ExpenseIt` 컨트롤, 레이아웃, 스타일, 데이터 바인딩 및 데이터 템플릿을 적용을 사용 하 여 응용 프로그램:</span><span class="sxs-lookup"><span data-stu-id="1eaec-320">The following illustration shows both pages of the `ExpenseIt` application with controls, layout, styles, data binding, and data templates applied:</span></span>

![ExpenseIt 샘플 스크린샷](../../../../docs/framework/wpf/getting-started/media/gettingstartedfigure5.png)

> [!NOTE]
> <span data-ttu-id="1eaec-322">이 샘플은 WPF의 특정 기능을 보여 줍니다 및 보안, 지역화, 접근성 등을 위해 모든 모범 사례를 따르지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1eaec-322">This sample demonstrates a specific feature of WPF and doesn't follow all best practices for things like security, localization, and accessibility.</span></span> <span data-ttu-id="1eaec-323">포괄적인 WPF 및.NET Framework 응용 프로그램 개발 모범 사례, 다음 항목을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="1eaec-323">For comprehensive coverage of WPF and the .NET Framework application development best practices, see the following topics:</span></span>
>
> - [<span data-ttu-id="1eaec-324">액세스 가능성</span><span class="sxs-lookup"><span data-stu-id="1eaec-324">Accessibility</span></span>](../../../../docs/framework/ui-automation/accessibility-best-practices.md)
>
> - [<span data-ttu-id="1eaec-325">보안</span><span class="sxs-lookup"><span data-stu-id="1eaec-325">Security</span></span>](../../../../docs/framework/wpf/security-wpf.md)
>
> - [<span data-ttu-id="1eaec-326">WPF 전역화 및 지역화</span><span class="sxs-lookup"><span data-stu-id="1eaec-326">WPF globalization and localization</span></span>](../../../../docs/framework/wpf/advanced/wpf-globalization-and-localization-overview.md)
>
> - [<span data-ttu-id="1eaec-327">WPF 성능</span><span class="sxs-lookup"><span data-stu-id="1eaec-327">WPF performance</span></span>](../../../../docs/framework/wpf/advanced/optimizing-wpf-application-performance.md)

## <a name="next-steps"></a><span data-ttu-id="1eaec-328">다음 단계</span><span class="sxs-lookup"><span data-stu-id="1eaec-328">Next steps</span></span>

<span data-ttu-id="1eaec-329">이 연습에서는 다양 한 Windows Presentation Foundation (WPF)를 사용 하 여 UI 만들기에 대 한 기술 배웠습니다.</span><span class="sxs-lookup"><span data-stu-id="1eaec-329">In this walkthrough you learned a number of techniques for creating a UI using Windows Presentation Foundation (WPF).</span></span> <span data-ttu-id="1eaec-330">이제 데이터 바인딩된.NET Framework 응용 프로그램의 구성 요소에 대 한 기본적인 지식이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1eaec-330">You should now have a basic understanding of the building blocks of a data-bound, .NET Framework application.</span></span> <span data-ttu-id="1eaec-331">WPF 아키텍처 및 프로그래밍 모델에 대한 자세한 내용은 다음 항목을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="1eaec-331">For more information about the WPF architecture and programming models, see the following topics:</span></span>

- [<span data-ttu-id="1eaec-332">WPF 아키텍처</span><span class="sxs-lookup"><span data-stu-id="1eaec-332">WPF architecture</span></span>](../../../../docs/framework/wpf/advanced/wpf-architecture.md)
- [<span data-ttu-id="1eaec-333">XAML 개요(WPF)</span><span class="sxs-lookup"><span data-stu-id="1eaec-333">XAML overview (WPF)</span></span>](../../../../docs/framework/wpf/advanced/xaml-overview-wpf.md)
- [<span data-ttu-id="1eaec-334">종속성 속성 개요</span><span class="sxs-lookup"><span data-stu-id="1eaec-334">Dependency properties overview</span></span>](../../../../docs/framework/wpf/advanced/dependency-properties-overview.md)
- [<span data-ttu-id="1eaec-335">레이아웃</span><span class="sxs-lookup"><span data-stu-id="1eaec-335">Layout</span></span>](../../../../docs/framework/wpf/advanced/layout.md)

<span data-ttu-id="1eaec-336">응용 프로그램을 만드는 방법에 대한 자세한 내용은 다음 항목을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="1eaec-336">For more information about creating applications, see the following topics:</span></span>

- [<span data-ttu-id="1eaec-337">응용 프로그램 개발</span><span class="sxs-lookup"><span data-stu-id="1eaec-337">Application development</span></span>](../../../../docs/framework/wpf/app-development/index.md)
- [<span data-ttu-id="1eaec-338">컨트롤</span><span class="sxs-lookup"><span data-stu-id="1eaec-338">Controls</span></span>](../../../../docs/framework/wpf/controls/index.md)
- [<span data-ttu-id="1eaec-339">데이터 바인딩 개요</span><span class="sxs-lookup"><span data-stu-id="1eaec-339">Data binding overview</span></span>](../../../../docs/framework/wpf/data/data-binding-overview.md)
- [<span data-ttu-id="1eaec-340">그래픽 및 멀티미디어</span><span class="sxs-lookup"><span data-stu-id="1eaec-340">Graphics and multimedia</span></span>](../../../../docs/framework/wpf/graphics-multimedia/index.md)
- [<span data-ttu-id="1eaec-341">WPF의 문서</span><span class="sxs-lookup"><span data-stu-id="1eaec-341">Documents in WPF</span></span>](../../../../docs/framework/wpf/advanced/documents-in-wpf.md)

## <a name="see-also"></a><span data-ttu-id="1eaec-342">참고자료</span><span class="sxs-lookup"><span data-stu-id="1eaec-342">See also</span></span>

- [<span data-ttu-id="1eaec-343">패널 개요</span><span class="sxs-lookup"><span data-stu-id="1eaec-343">Panels overview</span></span>](../../../../docs/framework/wpf/controls/panels-overview.md)
- [<span data-ttu-id="1eaec-344">데이터 템플릿 개요</span><span class="sxs-lookup"><span data-stu-id="1eaec-344">Data templating overview</span></span>](../../../../docs/framework/wpf/data/data-templating-overview.md)
- [<span data-ttu-id="1eaec-345">WPF 응용 프로그램 빌드</span><span class="sxs-lookup"><span data-stu-id="1eaec-345">Build a WPF application</span></span>](../../../../docs/framework/wpf/app-development/building-a-wpf-application-wpf.md)
- [<span data-ttu-id="1eaec-346">스타일 및 템플릿</span><span class="sxs-lookup"><span data-stu-id="1eaec-346">Styles and templates</span></span>](../../../../docs/framework/wpf/controls/styles-and-templates.md)
