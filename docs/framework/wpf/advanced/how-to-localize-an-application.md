---
title: '방법: 애플리케이션 지역화'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- localization [WPF], applications
- LocBaml tool [WPF]
- applications [WPF], localizing
ms.assetid: 5001227e-9326-48a4-9dcd-ba1b89ee6653
ms.openlocfilehash: 749ba2dd9318976289d9d4140cfadd711e0548d4
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/30/2019
ms.locfileid: "68629878"
---
# <a name="how-to-localize-an-application"></a><span data-ttu-id="44320-102">방법: 애플리케이션 지역화</span><span class="sxs-lookup"><span data-stu-id="44320-102">How to: Localize an Application</span></span>
<span data-ttu-id="44320-103">이 자습서에서는 LocBaml 도구를 사용하여 지역화된 애플리케이션을 만드는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="44320-103">This tutorial explains how to create a localized application by using the LocBaml tool.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="44320-104">LocBaml 도구는 프로덕션용 애플리케이션이 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="44320-104">The LocBaml tool is not a production-ready application.</span></span> <span data-ttu-id="44320-105">지역화 API 중 일부를 사용하며 지역화 도구를 작성하는 방법을 설명하는 샘플로 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="44320-105">It is presented as a sample that uses some of the localization APIs and illustrates how you might write a localization tool.</span></span>  
  
<a name="Introduction"></a>   
## <a name="overview"></a><span data-ttu-id="44320-106">개요</span><span class="sxs-lookup"><span data-stu-id="44320-106">Overview</span></span>  
 <span data-ttu-id="44320-107">이 설명에서는 애플리케이션을 지역화하는 단계별 접근 방식을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="44320-107">This discussion gives you a step-by-step approach to localizing an application.</span></span> <span data-ttu-id="44320-108">먼저 번역할 텍스트를 추출할 수 있도록 애플리케이션을 준비합니다.</span><span class="sxs-lookup"><span data-stu-id="44320-108">First, you will prepare your application so that the text that will be translated can be extracted.</span></span> <span data-ttu-id="44320-109">텍스트를 번역한 후에 번역된 텍스트를 원래 애플리케이션의 새 복사본으로 병합합니다.</span><span class="sxs-lookup"><span data-stu-id="44320-109">After the text is translated, you will merge the translated text into a new copy of the original application.</span></span>  
  
<a name="Requirements"></a>   
## <a name="requirements"></a><span data-ttu-id="44320-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="44320-110">Requirements</span></span>  
 <span data-ttu-id="44320-111">이 설명에서는 명령줄에서 실행되는 컴파일러인 [!INCLUDE[TLA#tla_msbuild](../../../../includes/tlasharptla-msbuild-md.md)]를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="44320-111">Over the course of this discussion, you will use [!INCLUDE[TLA#tla_msbuild](../../../../includes/tlasharptla-msbuild-md.md)], which is a compiler that runs from the command line.</span></span>  
  
 <span data-ttu-id="44320-112">또한 프로젝트 파일을 사용하도록 지시됩니다.</span><span class="sxs-lookup"><span data-stu-id="44320-112">Also, you will be instructed to use a project file.</span></span> <span data-ttu-id="44320-113">및 프로젝트 파일을 사용 [!INCLUDE[TLA2#tla_msbuild](../../../../includes/tla2sharptla-msbuild-md.md)] 하는 방법에 대 한 지침은 [빌드 및 배포](../app-development/building-and-deploying-wpf-applications.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="44320-113">For instructions on how to use [!INCLUDE[TLA2#tla_msbuild](../../../../includes/tla2sharptla-msbuild-md.md)] and project files, see [Build and Deploy](../app-development/building-and-deploying-wpf-applications.md).</span></span>  
  
 <span data-ttu-id="44320-114">이 설명의 모든 예제에서는 문화권으로 en-US(영어-미국)를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="44320-114">All the examples in this discussion use en-US (English-US) as the culture.</span></span> <span data-ttu-id="44320-115">이렇게 하면 다른 언어를 설치하지 않고 예제의 단계를 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="44320-115">This enables you to work through the steps of the examples without installing a different language.</span></span>  
  
<a name="create_sample_app"></a>   
## <a name="create-a-sample-application"></a><span data-ttu-id="44320-116">샘플 애플리케이션 만들기</span><span class="sxs-lookup"><span data-stu-id="44320-116">Create a Sample Application</span></span>  
 <span data-ttu-id="44320-117">이 단계에서는 지역화를 위해 애플리케이션을 준비합니다.</span><span class="sxs-lookup"><span data-stu-id="44320-117">In this step, you will prepare your application for localization.</span></span> <span data-ttu-id="44320-118">[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] 샘플에서는 이 설명의 코드 예제에 사용되는 HelloApp 샘플이 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="44320-118">In the [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] samples, a HelloApp sample is supplied that will be used for the code examples in this discussion.</span></span> <span data-ttu-id="44320-119">이 샘플을 사용 하려면 [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] [LocBaml 도구 샘플](https://go.microsoft.com/fwlink/?LinkID=160016)에서 파일을 다운로드 하세요.</span><span class="sxs-lookup"><span data-stu-id="44320-119">If you would like to use this sample, download the [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] files from the [LocBaml Tool Sample](https://go.microsoft.com/fwlink/?LinkID=160016).</span></span>  
  
1. <span data-ttu-id="44320-120">지역화를 시작하려는 지점까지 애플리케이션을 개발합니다.</span><span class="sxs-lookup"><span data-stu-id="44320-120">Develop your application to the point where you want to start localization.</span></span>  
  
2. <span data-ttu-id="44320-121">[!INCLUDE[TLA2#tla_msbuild](../../../../includes/tla2sharptla-msbuild-md.md)]에서 주 어셈블리와 중립 언어 리소스가 포함될 위성 어셈블리(확장명이 .resources.dll인 파일)를 생성하도록 프로젝트 파일에서 개발 언어를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="44320-121">Specify the development language in the project file so that [!INCLUDE[TLA2#tla_msbuild](../../../../includes/tla2sharptla-msbuild-md.md)] generates a main assembly and a satellite assembly (a file with the .resources.dll extension) to contain the neutral language resources.</span></span> <span data-ttu-id="44320-122">HelloApp 샘플의 프로젝트 파일은 HelloApp.csproj입니다.</span><span class="sxs-lookup"><span data-stu-id="44320-122">The project file in the HelloApp sample is HelloApp.csproj.</span></span> <span data-ttu-id="44320-123">해당 파일에서 다음과 같이 식별된 개발 언어를 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="44320-123">In that file, you will find the development language identified as follows:</span></span>  
  
     `<UICulture>en-US</UICulture>`  
  
3. <span data-ttu-id="44320-124">[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 파일에 Uid를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="44320-124">Add Uids to your [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] files.</span></span> <span data-ttu-id="44320-125">Uid는 파일의 변경 내용을 추적하고 번역해야 하는 항목을 식별하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="44320-125">Uids are used to keep track of changes to files and to identify items that must be translated.</span></span> <span data-ttu-id="44320-126">파일에 Uid를 추가 하려면 프로젝트 파일에서 **updateuid** 를 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="44320-126">To add Uids to your files, run **updateuid** on your project file:</span></span>  
  
     <span data-ttu-id="44320-127">**msbuild -t:updateuid helloapp.csproj**</span><span class="sxs-lookup"><span data-stu-id="44320-127">**msbuild -t:updateuid helloapp.csproj**</span></span>  
  
     <span data-ttu-id="44320-128">누락 되었거나 중복 된 Uid가 없는지 확인 하려면 **checkuid**를 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="44320-128">To verify that you have no missing or duplicate Uids, run **checkuid**:</span></span>  
  
     <span data-ttu-id="44320-129">**msbuild -t:checkuid helloapp.csproj**</span><span class="sxs-lookup"><span data-stu-id="44320-129">**msbuild -t:checkuid helloapp.csproj**</span></span>  
  
     <span data-ttu-id="44320-130">**Updateuid**를 실행 한 후 파일에는 uid가 포함 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="44320-130">After running **updateuid**, your files should contain Uids.</span></span> <span data-ttu-id="44320-131">예를 들어 HelloApp의 Pane1.xaml 파일에서는 다음을 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="44320-131">For example, in the Pane1.xaml file of HelloApp, you should find the following:</span></span>  
  
     `<StackPanel x:Uid="StackPanel_1">`  
  
     `<TextBlock x:Uid="TextBlock_1">Hello World</TextBlock>`  
  
     `<TextBlock x:Uid="TextBlock_2">Goodbye World</TextBlock>`  
  
     `</StackPanel>`  
  
<a name="create_dll"></a>   
## <a name="create-the-neutral-language-resources-satellite-assembly"></a><span data-ttu-id="44320-132">중립 언어 리소스 위성 어셈블리 만들기</span><span class="sxs-lookup"><span data-stu-id="44320-132">Create the Neutral Language Resources Satellite Assembly</span></span>  
 <span data-ttu-id="44320-133">애플리케이션이 중립 언어 리소스 위성 어셈블리를 생성하도록 구성된 후 애플리케이션을 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="44320-133">After the application is configured to generate a neutral language resources satellite assembly, you build the application.</span></span> <span data-ttu-id="44320-134">그러면 지역화를 위해 LocBaml에 필요한 중립 언어 리소스 위성 어셈블리와 주 애플리케이션 어셈블리가 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="44320-134">This generates the main application assembly, as well as the neutral language resources satellite assembly that is required by LocBaml for localization.</span></span> <span data-ttu-id="44320-135">애플리케이션을 빌드하려면</span><span class="sxs-lookup"><span data-stu-id="44320-135">To build the application:</span></span>  
  
1. <span data-ttu-id="44320-136">Helloapp.resources.dll를 컴파일하여 DLL (동적 연결 라이브러리)을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="44320-136">Compile HelloApp to create a dynamic-link library (DLL):</span></span>  
  
     <span data-ttu-id="44320-137">**msbuild helloapp.csproj**</span><span class="sxs-lookup"><span data-stu-id="44320-137">**msbuild helloapp.csproj**</span></span>  
  
2. <span data-ttu-id="44320-138">새로 만든 주 애플리케이션 어셈블리인 HelloApp.exe는 다음 폴더에 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="44320-138">The newly created main application assembly, HelloApp.exe, is created in the following folder:</span></span>  
  
     `C:\HelloApp\Bin\Debug\`  
  
3. <span data-ttu-id="44320-139">새로 만든 중립 언어 리소스 위성 어셈블리인 HelloApp.resources.dll은 다음 폴더에 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="44320-139">The newly created neutral language resources satellite assembly, HelloApp.resources.dll, is created in the following folder:</span></span>  
  
     `C:\HelloApp\Bin\Debug\en-US\`  
  
<a name="build_locbaml"></a>   
## <a name="build-the-locbaml-tool"></a><span data-ttu-id="44320-140">LocBaml 도구 빌드</span><span class="sxs-lookup"><span data-stu-id="44320-140">Build the LocBaml Tool</span></span>  
  
1. <span data-ttu-id="44320-141">LocBaml을 빌드하는 데 필요한 모든 파일은 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 샘플에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="44320-141">All the files necessary to build LocBaml are located in the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] samples.</span></span> <span data-ttu-id="44320-142">C# [LocBaml 도구 샘플](https://go.microsoft.com/fwlink/?LinkID=160016)에서 파일을 다운로드 합니다.</span><span class="sxs-lookup"><span data-stu-id="44320-142">Download the C# files from the [LocBaml Tool Sample](https://go.microsoft.com/fwlink/?LinkID=160016).</span></span>  
  
2. <span data-ttu-id="44320-143">명령줄에서 프로젝트 파일(locbaml.csproj)을 실행하여 도구를 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="44320-143">From the command line, run the project file (locbaml.csproj) to build the tool:</span></span>  
  
     <span data-ttu-id="44320-144">**msbuild locbaml.csproj**</span><span class="sxs-lookup"><span data-stu-id="44320-144">**msbuild locbaml.csproj**</span></span>  
  
3. <span data-ttu-id="44320-145">Bin\Release 디렉터리로 이동하여 새로 만든 실행 파일(locbaml.exe)을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="44320-145">Go to the Bin\Release directory to find the newly created executable file (locbaml.exe).</span></span> <span data-ttu-id="44320-146">예: C:\LocBaml\Bin\Release\locbaml.exe.</span><span class="sxs-lookup"><span data-stu-id="44320-146">Example:C:\LocBaml\Bin\Release\locbaml.exe.</span></span>  
  
4. <span data-ttu-id="44320-147">LocBaml을 실행할 때 지정할 수 있는 옵션은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="44320-147">The options that you can specify when you run LocBaml are as follows:</span></span>  
  
    - <span data-ttu-id="44320-148">**parse** 또는 **-p:** Baml, 리소스 또는 DLL 파일을 구문 분석 하 여 .csv 또는 .txt 파일을 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="44320-148">**parse** or **-p:** Parses Baml, resources, or DLL files to generate a .csv or .txt file.</span></span>  
  
    - <span data-ttu-id="44320-149">**생성** 또는 **-g:** 번역 된 파일을 사용 하 여 지역화 된 이진 파일을 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="44320-149">**generate** or **-g:** Generates a localized binary file by using a translated file.</span></span>  
  
    - <span data-ttu-id="44320-150">**out** 또는 **-o** {*filedirectory*] **:** 출력 파일 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="44320-150">**out** or **-o** {*filedirectory*] **:** Output file name.</span></span>  
  
    - <span data-ttu-id="44320-151">**culture** 또는 **-al** {*culture*] **:** 출력 어셈블리의 로캘입니다.</span><span class="sxs-lookup"><span data-stu-id="44320-151">**culture** or **-cul** {*culture*] **:** Locale of output assemblies.</span></span>  
  
    - <span data-ttu-id="44320-152">**변환** 또는 **트랜잭션** {*translation* **:** 번역 또는 지역화 된 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="44320-152">**translation** or **-trans** {*translation.csv*] **:** Translated or localized file.</span></span>  
  
    - <span data-ttu-id="44320-153">**asmpath** 또는 **-asmpath:** {*filedirectory*] **:** 코드에 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 사용자 지정 컨트롤이 포함 된 경우 사용자 지정 컨트롤 어셈블리에 **asmpath** 을 제공 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="44320-153">**asmpath** or **-asmpath:** {*filedirectory*] **:** If your [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] code contains custom controls, you must supply the **asmpath** to the custom control assembly.</span></span>  
  
    - <span data-ttu-id="44320-154">**nologo** 로고 또는 저작권 정보를 표시 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="44320-154">**nologo:** Displays no logo or copyright information.</span></span>  
  
    - <span data-ttu-id="44320-155">**구문** 자세한 정보 표시 모드 정보를 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="44320-155">**verbose:** Displays verbose mode information.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="44320-156">도구를 실행할 때 옵션 목록이 필요한 경우 **LocBaml** 을 입력 하 고 enter 키를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="44320-156">If you need a list of the options when you are running the tool, type     **LocBaml.exe** and press ENTER.</span></span>  
  
<a name="parse_dll"></a>   
## <a name="use-locbaml-to-parse-a-file"></a><span data-ttu-id="44320-157">LocBaml을 사용하여 파일 구문 분석</span><span class="sxs-lookup"><span data-stu-id="44320-157">Use LocBaml to Parse a File</span></span>  
 <span data-ttu-id="44320-158">LocBaml 도구를 만들었으므로 이제 이 도구를 통해 HelloApp.resources.dll을 구문 분석하여 지역화할 텍스트 콘텐츠를 추출할 준비가 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="44320-158">Now that you have created the LocBaml tool, you are ready to use it to parse HelloApp.resources.dll to extract the text content that will be localized.</span></span>  
  
1. <span data-ttu-id="44320-159">주 애플리케이션 어셈블리가 만들어진 애플리케이션의 bin\debug 폴더에 LocBaml.exe를 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="44320-159">Copy LocBaml.exe to your application's bin\debug folder, where the main application assembly was created.</span></span>  
  
2. <span data-ttu-id="44320-160">위성 어셈블리 파일을 구문 분석하고 출력을 .csv 파일로 저장하려면 다음 명령을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="44320-160">To parse the satellite assembly file and store the output as a .csv file, use the following command:</span></span>  
  
     <span data-ttu-id="44320-161">**LocBaml.exe /parse HelloApp.resources.dll /out:Hello.csv**</span><span class="sxs-lookup"><span data-stu-id="44320-161">**LocBaml.exe /parse HelloApp.resources.dll /out:Hello.csv**</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="44320-162">입력 파일 HelloApp.resources.dll이 LocBaml.exe와 동일한 디렉터리에 없는 경우 두 파일이 동일한 디렉터리에 있도록 파일 중 하나를 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="44320-162">If the input file, HelloApp.resources.dll, is not in the same directory as LocBaml.exe move one of the files so that both files are in the same directory.</span></span>  
  
3. <span data-ttu-id="44320-163">LocBaml을 실행하여 파일을 구문 분석하는 경우 출력은 쉼표(.csv 파일) 또는 탭(.txt 파일)으로 구분된 7개 필드로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="44320-163">When you run LocBaml to parse files, the output consists of seven fields delimited by commas (.csv files) or tabs (.txt files).</span></span> <span data-ttu-id="44320-164">다음은 HelloApp.resources.dll에 대해 구문 분석된 .csv 파일을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="44320-164">The following shows the parsed .csv file for the HelloApp.resources.dll:</span></span>

   | |
   |-|
   |<span data-ttu-id="44320-165">HelloApp.g.en-US.resources:window1.baml,Stack1:System.Windows.Controls.StackPanel.$Content,Ignore,FALSE, FALSE,,#Text1;#Text2;</span><span class="sxs-lookup"><span data-stu-id="44320-165">HelloApp.g.en-US.resources:window1.baml,Stack1:System.Windows.Controls.StackPanel.$Content,Ignore,FALSE, FALSE,,#Text1;#Text2;</span></span>|
   |<span data-ttu-id="44320-166">HelloApp.g.en-US.resources:window1.baml,Text1:System.Windows.Controls.TextBlock.$Content,None,TRUE, TRUE,,Hello World</span><span class="sxs-lookup"><span data-stu-id="44320-166">HelloApp.g.en-US.resources:window1.baml,Text1:System.Windows.Controls.TextBlock.$Content,None,TRUE, TRUE,,Hello World</span></span>|
   |<span data-ttu-id="44320-167">HelloApp.g.en-US.resources:window1.baml,Text2:System.Windows.Controls.TextBlock.$Content,None,TRUE, TRUE,,Goodbye World</span><span class="sxs-lookup"><span data-stu-id="44320-167">HelloApp.g.en-US.resources:window1.baml,Text2:System.Windows.Controls.TextBlock.$Content,None,TRUE, TRUE,,Goodbye World</span></span>|

   <span data-ttu-id="44320-168">7개 필드는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="44320-168">The seven fields are:</span></span>  
  
   1. <span data-ttu-id="44320-169">**BAML 이름**.</span><span class="sxs-lookup"><span data-stu-id="44320-169">**BAML Name**.</span></span> <span data-ttu-id="44320-170">소스 언어 위성 어셈블리와 관련된 BAML 리소스의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="44320-170">The name of the BAML resource with respect to the source language satellite assembly.</span></span>  
  
   2. <span data-ttu-id="44320-171">**리소스 키**.</span><span class="sxs-lookup"><span data-stu-id="44320-171">**Resource Key**.</span></span> <span data-ttu-id="44320-172">지역화된 리소스 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="44320-172">The localized resource identifier.</span></span>  
  
   3. <span data-ttu-id="44320-173">**범주**.</span><span class="sxs-lookup"><span data-stu-id="44320-173">**Category**.</span></span> <span data-ttu-id="44320-174">값 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="44320-174">The value type.</span></span> <span data-ttu-id="44320-175">[지역화 특성 및 주석](localization-attributes-and-comments.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="44320-175">See [Localization Attributes and Comments](localization-attributes-and-comments.md).</span></span>  
  
   4. <span data-ttu-id="44320-176">**가독성**.</span><span class="sxs-lookup"><span data-stu-id="44320-176">**Readability**.</span></span> <span data-ttu-id="44320-177">로컬라이저가 값을 읽을 수 있는지 여부입니다.</span><span class="sxs-lookup"><span data-stu-id="44320-177">Whether the value can be read by a localizer.</span></span> <span data-ttu-id="44320-178">[지역화 특성 및 주석](localization-attributes-and-comments.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="44320-178">See [Localization Attributes and Comments](localization-attributes-and-comments.md).</span></span>  
  
   5. <span data-ttu-id="44320-179">**수정 가능성**.</span><span class="sxs-lookup"><span data-stu-id="44320-179">**Modifiability**.</span></span> <span data-ttu-id="44320-180">로컬라이저가 값을 수정할 수 있는지 여부입니다.</span><span class="sxs-lookup"><span data-stu-id="44320-180">Whether the value can be modified by a localizer.</span></span> <span data-ttu-id="44320-181">[지역화 특성 및 주석](localization-attributes-and-comments.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="44320-181">See [Localization Attributes and Comments](localization-attributes-and-comments.md).</span></span>  
  
   6. <span data-ttu-id="44320-182">**설명**.</span><span class="sxs-lookup"><span data-stu-id="44320-182">**Comments**.</span></span> <span data-ttu-id="44320-183">값은 지역화하는 방법을 확인하는 데 도움이 되는 값에 대한 추가 설명입니다.</span><span class="sxs-lookup"><span data-stu-id="44320-183">Additional description of the value to help determine how a value is localized.</span></span> <span data-ttu-id="44320-184">[지역화 특성 및 주석](localization-attributes-and-comments.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="44320-184">See [Localization Attributes and Comments](localization-attributes-and-comments.md).</span></span>  
  
   7. <span data-ttu-id="44320-185">**값**.</span><span class="sxs-lookup"><span data-stu-id="44320-185">**Value**.</span></span> <span data-ttu-id="44320-186">원하는 문화권으로 번역할 텍스트 값입니다.</span><span class="sxs-lookup"><span data-stu-id="44320-186">The text value to translate to the desired culture.</span></span>  
  
   <span data-ttu-id="44320-187">다음 표에서는 이러한 필드가 .csv 파일의 구분된 값에 매핑되는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="44320-187">The following table shows how these fields map to the delimited values of the .csv file:</span></span>  
  
   |<span data-ttu-id="44320-188">BAML 이름</span><span class="sxs-lookup"><span data-stu-id="44320-188">BAML name</span></span>|<span data-ttu-id="44320-189">리소스 키</span><span class="sxs-lookup"><span data-stu-id="44320-189">Resource key</span></span>|<span data-ttu-id="44320-190">범주</span><span class="sxs-lookup"><span data-stu-id="44320-190">Category</span></span>|<span data-ttu-id="44320-191">가독성</span><span class="sxs-lookup"><span data-stu-id="44320-191">Readability</span></span>|<span data-ttu-id="44320-192">수정 가능성</span><span class="sxs-lookup"><span data-stu-id="44320-192">Modifiability</span></span>|<span data-ttu-id="44320-193">설명</span><span class="sxs-lookup"><span data-stu-id="44320-193">Comments</span></span>|<span data-ttu-id="44320-194">값</span><span class="sxs-lookup"><span data-stu-id="44320-194">Value</span></span>|  
   |---------------|------------------|--------------|-----------------|-------------------|--------------|-----------|
   |<span data-ttu-id="44320-195">HelloApp.g.en-US.resources:window1.baml</span><span class="sxs-lookup"><span data-stu-id="44320-195">HelloApp.g.en-US.resources:window1.baml</span></span>|<span data-ttu-id="44320-196">Stack1:System.Windows.Controls.StackPanel.$Content</span><span class="sxs-lookup"><span data-stu-id="44320-196">Stack1:System.Windows.Controls.StackPanel.$Content</span></span>|<span data-ttu-id="44320-197">무시</span><span class="sxs-lookup"><span data-stu-id="44320-197">Ignore</span></span>|<span data-ttu-id="44320-198">FALSE</span><span class="sxs-lookup"><span data-stu-id="44320-198">FALSE</span></span>|<span data-ttu-id="44320-199">FALSE</span><span class="sxs-lookup"><span data-stu-id="44320-199">FALSE</span></span>||<span data-ttu-id="44320-200">#Text1;#Text2</span><span class="sxs-lookup"><span data-stu-id="44320-200">#Text1;#Text2</span></span>|
   |<span data-ttu-id="44320-201">HelloApp.g.en-US.resources:window1.baml</span><span class="sxs-lookup"><span data-stu-id="44320-201">HelloApp.g.en-US.resources:window1.baml</span></span>|<span data-ttu-id="44320-202">Text1:System.Windows.Controls.TextBlock.$Content</span><span class="sxs-lookup"><span data-stu-id="44320-202">Text1:System.Windows.Controls.TextBlock.$Content</span></span>|<span data-ttu-id="44320-203">없음</span><span class="sxs-lookup"><span data-stu-id="44320-203">None</span></span>|<span data-ttu-id="44320-204">TRUE</span><span class="sxs-lookup"><span data-stu-id="44320-204">TRUE</span></span>|<span data-ttu-id="44320-205">TRUE</span><span class="sxs-lookup"><span data-stu-id="44320-205">TRUE</span></span>||<span data-ttu-id="44320-206">Hello World</span><span class="sxs-lookup"><span data-stu-id="44320-206">Hello World</span></span>|
   |<span data-ttu-id="44320-207">HelloApp.g.en-US.resources:window1.baml</span><span class="sxs-lookup"><span data-stu-id="44320-207">HelloApp.g.en-US.resources:window1.baml</span></span>|<span data-ttu-id="44320-208">Text2:System.Windows.Controls.TextBlock.$Content</span><span class="sxs-lookup"><span data-stu-id="44320-208">Text2:System.Windows.Controls.TextBlock.$Content</span></span>|<span data-ttu-id="44320-209">없음</span><span class="sxs-lookup"><span data-stu-id="44320-209">None</span></span>|<span data-ttu-id="44320-210">TRUE</span><span class="sxs-lookup"><span data-stu-id="44320-210">TRUE</span></span>|<span data-ttu-id="44320-211">TRUE</span><span class="sxs-lookup"><span data-stu-id="44320-211">TRUE</span></span>||<span data-ttu-id="44320-212">Goodbye World</span><span class="sxs-lookup"><span data-stu-id="44320-212">Goodbye World</span></span>|
  
   <span data-ttu-id="44320-213">**설명** 필드의 모든 값에는 값이 포함 되어 있지 않습니다. 필드에 값이 없는 경우 비어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="44320-213">Notice that all the values for the **Comments** field contain no values; if a field doesn't have a value, it is empty.</span></span> <span data-ttu-id="44320-214">또한 첫 번째 행의 항목은 읽고 수정할 수 없으며 해당 **범주** 값으로 "Ignore"가 있으므로 값을 지역화할 수 없음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="44320-214">Also notice that the item in the first row is neither readable nor modifiable, and has "Ignore" as its **Category** value, all of which indicates that the value is not localizable.</span></span>  
  
4. <span data-ttu-id="44320-215">구문 분석 된 파일, 특히 많은 파일에서 지역화 가능한 항목의 검색을 용이 하 게 하기 위해 **범주**, **가독성**및 **수정 가능성**을 기준으로 항목을 정렬 하거나 필터링 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="44320-215">To facilitate discovery of localizable items in parsed files, particularly in large files, you can sort or filter the items by **Category**, **Readability**, and **Modifiability**.</span></span> <span data-ttu-id="44320-216">예를 들어 읽을 수 없는 값과 수정할 수 없는 값을 필터링할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="44320-216">For example, you can filter out unreadable and unmodifiable values.</span></span>  
  
<a name="translate_loc_content"></a>   
## <a name="translate-the-localizable-content"></a><span data-ttu-id="44320-217">지역화할 수 있는 콘텐츠 번역</span><span class="sxs-lookup"><span data-stu-id="44320-217">Translate the Localizable Content</span></span>  
 <span data-ttu-id="44320-218">사용 가능한 임의 도구를 사용하여 추출한 콘텐츠를 번역합니다.</span><span class="sxs-lookup"><span data-stu-id="44320-218">Use any tool that you have available to translate the extracted content.</span></span> <span data-ttu-id="44320-219">이 작업을 효율적으로 수행하려면 .csv 파일에 리소스를 쓴 다음 [!INCLUDE[TLA#tla_xl](../../../../includes/tlasharptla-xl-md.md)]에서 보고 마지막 열(값)에서 번역하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="44320-219">A good way to do this is to write the resources to a .csv file and view them in [!INCLUDE[TLA#tla_xl](../../../../includes/tlasharptla-xl-md.md)], making translation changes to the last column (value).</span></span>  
  
<a name="merge_translations"></a>   
## <a name="use-locbaml-to-generate-a-new-resourcesdll-file"></a><span data-ttu-id="44320-220">LocBaml을 사용하여 새 .resources.dll 파일 생성</span><span class="sxs-lookup"><span data-stu-id="44320-220">Use LocBaml to Generate a New .resources.dll File</span></span>  
 <span data-ttu-id="44320-221">LocBaml로 HelloApp.resources.dll을 구문 분석하여 식별된 콘텐츠가 번역되었으며 원래 애플리케이션에 다시 병합해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="44320-221">The content that was identified by parsing HelloApp.resources.dll with LocBaml has been translated and must be merged back into the original application.</span></span> <span data-ttu-id="44320-222">**Generate** 또는 **-g** 옵션을 사용 하 여 새 .resources .dll 파일을 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="44320-222">Use the **generate** or **-g** option to generate a new .resources.dll file.</span></span>  
  
1. <span data-ttu-id="44320-223">다음 구문을 사용하여 새 HelloApp.resources.dll 파일을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="44320-223">Use the following syntax to generate a new HelloApp.resources.dll file.</span></span> <span data-ttu-id="44320-224">문화권을 en-US로 표시합니다(/cul:en-US).</span><span class="sxs-lookup"><span data-stu-id="44320-224">Mark the culture as en-US (/cul:en-US).</span></span>  
  
     <span data-ttu-id="44320-225">**LocBaml.exe /generate HelloApp.resources.dll /trans:Hello.csv /out:c:\ /cul:en-US**</span><span class="sxs-lookup"><span data-stu-id="44320-225">**LocBaml.exe /generate HelloApp.resources.dll /trans:Hello.csv /out:c:\ /cul:en-US**</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="44320-226">입력 파일 Hello.csv가 LocBaml.exe 실행 파일과 동일한 디렉터리에 없는 경우 두 파일이 동일한 디렉터리에 있도록 파일 중 하나를 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="44320-226">If the input file, Hello.csv, is not in the same directory as the executable, LocBaml.exe, move one of the files so that both files are in the same directory.</span></span>  
  
2. <span data-ttu-id="44320-227">C:\HelloApp\Bin\Debug\en-US\HelloApp.resources.dll 디렉터리에 있는 기존 HelloApp.resources.dll 파일을 새로 만든 HelloApp.resources.dll 파일로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="44320-227">Replace the old HelloApp.resources.dll file in the C:\HelloApp\Bin\Debug\en-US\HelloApp.resources.dll directory with your newly created HelloApp.resources.dll file.</span></span>  
  
3. <span data-ttu-id="44320-228">이제 애플리케이션에서 "Hello World" 및 "Goodbye World"가 번역됩니다.</span><span class="sxs-lookup"><span data-stu-id="44320-228">"Hello World" and "Goodbye World" should now be translated in your application.</span></span>  
  
4. <span data-ttu-id="44320-229">다른 문화권으로 번역하려면 번역할 대상 언어의 문화권을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="44320-229">To translate to a different culture, use the culture of the language that you are translating to.</span></span> <span data-ttu-id="44320-230">다음 예제에서는 프랑스어-캐나다로 번역하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="44320-230">The following example shows how to translate to French-Canadian:</span></span>  
  
     <span data-ttu-id="44320-231">**LocBaml.exe /generate HelloApp.resources.dll /trans:Hellofr-CA.csv /out:c:\ /cul:fr-CA**</span><span class="sxs-lookup"><span data-stu-id="44320-231">**LocBaml.exe /generate HelloApp.resources.dll /trans:Hellofr-CA.csv /out:c:\ /cul:fr-CA**</span></span>  
  
5. <span data-ttu-id="44320-232">주 애플리케이션 어셈블리와 동일한 어셈블리에서 새 위성 어셈블리를 포함할 새 문화권별 폴더를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="44320-232">In the same assembly as the main application assembly, create a new culture-specific folder to house the new satellite assembly.</span></span> <span data-ttu-id="44320-233">프랑스어-캐나다의 경우 폴더는 fr-CA입니다.</span><span class="sxs-lookup"><span data-stu-id="44320-233">For French-Canadian, the folder would be fr-CA.</span></span>  
  
6. <span data-ttu-id="44320-234">생성된 위성 어셈블리를 새 폴더에 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="44320-234">Copy the generated satellite assembly to the new folder.</span></span>  
  
7. <span data-ttu-id="44320-235">새 위성 어셈블리를 테스트하려면 애플리케이션이 실행되는 문화권을 변경해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="44320-235">To test the new satellite assembly, you need to change the culture under which your application will run.</span></span> <span data-ttu-id="44320-236">이 작업은 다음 두 가지 방법 중 하나로 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="44320-236">You can do this in one of two ways:</span></span>  
  
    - <span data-ttu-id="44320-237">운영 체제의 국가별 설정을 변경 합니다 ( &#124; **제어판** &#124; 의 **국가 및 언어 옵션**시작).</span><span class="sxs-lookup"><span data-stu-id="44320-237">Change your operating system's regional settings (**Start** &#124; **Control Panel** &#124; **Regional and Language Options**).</span></span>  
  
    - <span data-ttu-id="44320-238">애플리케이션에서 다음 코드를 App.xaml.cs에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="44320-238">In your application, add the following code to App.xaml.cs:</span></span>  
  
   [!code-xaml[LocBamlChangeCultureSnippets#LocBamlChangeCultureMARKUP](~/samples/snippets/csharp/VS_Snippets_Wpf/LocBamlChangeCultureSnippets/CSharp/App.xaml#locbamlchangeculturemarkup)]
   [!code-csharp[LocBamlChangeCultureSnippets#LocBamlChangeCultureCODEBEHIND](~/samples/snippets/csharp/VS_Snippets_Wpf/LocBamlChangeCultureSnippets/CSharp/App.xaml.cs#locbamlchangeculturecodebehind)]
   [!code-vb[LocBamlChangeCultureSnippets#LocBamlChangeCultureCODEBEHIND](~/samples/snippets/visualbasic/VS_Snippets_Wpf/LocBamlChangeCultureSnippets/VisualBasic/Application.xaml.vb#locbamlchangeculturecodebehind)]  
  
<a name="Some_Tips_for_Using_LocBaml"></a>   
## <a name="some-tips-for-using-locbaml"></a><span data-ttu-id="44320-239">LocBaml 사용과 관련된 몇 가지 팁</span><span class="sxs-lookup"><span data-stu-id="44320-239">Some Tips for Using LocBaml</span></span>  
  
- <span data-ttu-id="44320-240">사용자 지정 컨트롤을 정의하는 모든 종속 어셈블리를 LocBaml의 로컬 디렉터리에 복사하거나 GAC에 설치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="44320-240">All dependent assemblies that define custom controls must be copied into the local directory of LocBaml or installed into the GAC.</span></span> <span data-ttu-id="44320-241">이는 지역화 API가 BAML (이진 XAML)을 읽을 때 종속 어셈블리에 액세스할 수 있어야 하기 때문에 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="44320-241">This is necessary because the localization API must have access to the dependent assemblies when it reads the binary XAML (BAML).</span></span>  
  
- <span data-ttu-id="44320-242">주 어셈블리가 서명된 경우 생성된 리소스 DLL도 서명되어야 로드됩니다.</span><span class="sxs-lookup"><span data-stu-id="44320-242">If the main assembly is signed, the generated resource DLL must also be signed in order for it to be loaded.</span></span>  
  
- <span data-ttu-id="44320-243">지역화된 리소스 DLL 버전을 주 어셈블리와 동기화해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="44320-243">The version of the localized resource DLL needs to be synchronized with the main assembly.</span></span>  
  
<a name="Whats_Next"></a>   
## <a name="whats-next"></a><span data-ttu-id="44320-244">새로운 기능</span><span class="sxs-lookup"><span data-stu-id="44320-244">What's Next</span></span>  
 <span data-ttu-id="44320-245">지금까지 LocBaml 도구를 사용하는 방법에 대한 기본 사항을 알아보았습니다.</span><span class="sxs-lookup"><span data-stu-id="44320-245">You should now have a basic understanding of how to use the LocBaml tool.</span></span>  <span data-ttu-id="44320-246">Uid를 포함하는 파일을 만들 수 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="44320-246">You should be able to make a file that contains Uids.</span></span> <span data-ttu-id="44320-247">LocBaml 도구를 통해 파일을 구문 분석하여 지역화할 수 있는 콘텐츠를 추출할 수 있어야 하며, 콘텐츠가 번역된 후 번역된 콘텐츠를 병합하는 .resources.dll 파일을 생성할 수 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="44320-247">By using the LocBaml tool, you should be able to parse a file to extract the localizable content, and after the content is translated, you should be able to generate a .resources.dll file that merges the translated content.</span></span> <span data-ttu-id="44320-248">이 항목에 가능한 모든 세부 정보가 포함되어 있지는 않지만 이제 LocBaml를 애플리케이션 지역화에 사용하는 데 필요한 지식을 습득했습니다.</span><span class="sxs-lookup"><span data-stu-id="44320-248">This topic does not include every possible detail, but you now have the knowledge necessary to use LocBaml for localizing your applications.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="44320-249">참고자료</span><span class="sxs-lookup"><span data-stu-id="44320-249">See also</span></span>

- [<span data-ttu-id="44320-250">WPF의 전역화</span><span class="sxs-lookup"><span data-stu-id="44320-250">Globalization for WPF</span></span>](globalization-for-wpf.md)
- [<span data-ttu-id="44320-251">자동 레이아웃 사용 개요</span><span class="sxs-lookup"><span data-stu-id="44320-251">Use Automatic Layout Overview</span></span>](use-automatic-layout-overview.md)
