---
title: ".NET 이식성 분석기 - .NET | Microsoft Docs"
description: ".NET 이식성 분석기 도구를 사용하여 다양한 .NET 구현에서 코드가 얼마나 이식성이 있는지 평가하는 방법을 알아봅니다."
keywords: .NET, .NET Core
author: blackdwarf
ms.author: mairaw
ms.date: 07/26/2017
ms.topic: article
ms.prod: .net
ms.technology: dotnet-standard
ms.devlang: dotnet
ms.assetid: 0375250f-5704-4993-a6d5-e21c499cea1e
ms.translationtype: HT
ms.sourcegitcommit: 3155295489e1188640dae5aa5bf9fdceb7480ed6
ms.openlocfilehash: adb1971c14c8ff8c147dba378ae0e9a5bc0fb5ad
ms.contentlocale: ko-kr
ms.lasthandoff: 08/21/2017

---

# <a name="the-net-portability-analyzer"></a><span data-ttu-id="42695-104">.NET 이식성 분석기</span><span class="sxs-lookup"><span data-stu-id="42695-104">The .NET Portability Analyzer</span></span>

<span data-ttu-id="42695-105">라이브러리를 다중 플랫폼으로 만들고 싶으세요?</span><span class="sxs-lookup"><span data-stu-id="42695-105">Want to make your libraries multi-platform?</span></span> <span data-ttu-id="42695-106">응용 프로그램이 다른 .NET 구현과 호환되도록 하는 데 필요한 작업량을 확인하고 싶으세요?</span><span class="sxs-lookup"><span data-stu-id="42695-106">Want to see how much work is required to make your application compatible with other .NET implementations?</span></span> <span data-ttu-id="42695-107">[.NET 이식성 분석기](http://go.microsoft.com/fwlink/?LinkID=507467)는 어셈블리를 분석하여 프로그램이 .NET 구현에서 얼마나 유연한지에 대한 자세한 보고서를 제공하는 도구입니다.</span><span class="sxs-lookup"><span data-stu-id="42695-107">The [.NET Portability Analyzer](http://go.microsoft.com/fwlink/?LinkID=507467) is a tool that provides you with a detailed report on how flexible your program is across .NET implementations by analyzing assemblies.</span></span> <span data-ttu-id="42695-108">이식성 분석기는 Visual Studio 확장 및 콘솔 앱으로 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="42695-108">The Portability Analyzer is offered as a Visual Studio Extension and as a console app.</span></span>

## <a name="new-targets"></a><span data-ttu-id="42695-109">새 대상</span><span class="sxs-lookup"><span data-stu-id="42695-109">New targets</span></span>

* <span data-ttu-id="42695-110">[.NET Core](https://dotnetfoundation.org/net-core): 모듈형 디자인을 포함하고, Side-by-Side를 이용하며, 플랫폼 간 시나리오를 대상으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="42695-110">[.NET Core](https://dotnetfoundation.org/net-core): Has a modular design, employs side-by-side, and targets cross-platform scenarios.</span></span> <span data-ttu-id="42695-111">Side-by-Side를 사용하면 다른 앱을 중단하지 않고 새로운 .NET Core 버전을 채택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="42695-111">Side-by-side allows you to adopt new .NET Core versions without breaking other apps.</span></span>
* <span data-ttu-id="42695-112">[ASP.NET Core](https://dotnetfoundation.org/asp-net-core): .NET Core를 기반으로 하는 최신 웹 프레임워크이므로 개발자에게 동일한 혜택을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="42695-112">[ASP.NET Core](https://dotnetfoundation.org/asp-net-core): is a modern web-framework built on .NET Core thus giving developers the same benefits.</span></span>
* <span data-ttu-id="42695-113">[유니버설 Windows 플랫폼](https://blogs.msdn.microsoft.com/dotnet/2014/04/24/net-native-performance): .NET 네이티브의 정적 컴파일을 사용하여 x64 및 ARM 컴퓨터에서 실행되는 Windows 스토어 앱의 성능을 향상합니다.</span><span class="sxs-lookup"><span data-stu-id="42695-113">[Universal Windows Platform](https://blogs.msdn.microsoft.com/dotnet/2014/04/24/net-native-performance): Improve performance of your Windows Store apps that run on x64 and ARM machines by using .NET Native’s static compilation.</span></span> 
* <span data-ttu-id="42695-114">.NET Core + 플랫폼 확장: .NET Core API뿐만 아니라 WCF, ASP.NET Core, FSharp 및 Azure 같은 .NET 에코시스템의 다른 API도 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="42695-114">.NET Core + Platform Extensions: Includes the .NET Core APIs in addition to other APIs in the .NET ecosystem such as WCF, ASP.NET Core, FSharp, and Azure.</span></span>
* <span data-ttu-id="42695-115">.NET Standard + 플랫폼 확장: .NET Standard API뿐만 아니라 WCF, ASP.NET Core, FSharp 및 Azure 같은 다른 .NET 에코시스템도 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="42695-115">.NET Standard + Platform Extensions: Includes the .NET Standard APIs in addition to other .NET ecosystem such as WCF, ASP.NET Core, FSharp, and Azure.</span></span>

## <a name="how-to-use-portability-analyzer"></a><span data-ttu-id="42695-116">이식성 분석기를 사용하는 방법</span><span class="sxs-lookup"><span data-stu-id="42695-116">How to use Portability Analyzer</span></span>

<span data-ttu-id="42695-117">.NET 이식성 분석기 사용을 시작하려면 먼저 [Visual Studio 갤러리](http://go.microsoft.com/fwlink/?LinkID=507467)에서 확장을 다운로드하고 설치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="42695-117">To begin using the .NET Portability Analyzer, you first need to download and install the extension from the [Visual Studio Gallery](http://go.microsoft.com/fwlink/?LinkID=507467).</span></span> <span data-ttu-id="42695-118">Visual Studio 2015 및 Visual Studio 2017에서 작동합니다.</span><span class="sxs-lookup"><span data-stu-id="42695-118">It works on Visual Studio 2015 and Visual Studio 2017.</span></span> <span data-ttu-id="42695-119">Visual Studio에서 **분석** > **Portability Analyzer Settings**(이식성 분석기 설정)를 통해 구성하고 대상 플랫폼을 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="42695-119">You can configure it in Visual Studio via **Analyze** > **Portability Analyzer Settings** and select your Target Platforms.</span></span>

![이식성 스크린샷](./media/portability-analyzer/portability-screenshot.png)

<span data-ttu-id="42695-121">전체 프로젝트를 분석하려면 **솔루션 탐색기**에서 프로젝트를 마우스 오른쪽 단추로 클릭하고 **어셈블리 이식성 분석**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="42695-121">To analyze your entire project, right-click on your project in **Solution Explorer** and select **Analyze Assembly Portability**.</span></span> <span data-ttu-id="42695-122">전체 프로젝트를 분석하지 않으려면 **분석** 메뉴로 이동한 다음 **어셈블리 이식성 분석**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="42695-122">Otherwise, go to the **Analyze** menu and select **Analyze Assembly Portability**.</span></span> <span data-ttu-id="42695-123">여기서 프로젝트의 실행 파일 또는 DLL을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="42695-123">From there, select your project’s executable or DLL.</span></span>

![이식성 솔루션 탐색기](./media/portability-analyzer/portability-solution-explorer.png)

<span data-ttu-id="42695-125">분석을 실행한 후 .NET 이식성 보고서를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="42695-125">After running the analysis, you will see your .NET Portability Report.</span></span> <span data-ttu-id="42695-126">대상 플랫폼에서 지원되지 않는 형식만 목록에 표시되며, **오류 목록**의 **메시지** 탭에서 권장 사항을 검토할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="42695-126">Only types that are unsupported by a target platform appear in the list and you can review recommendations in the **Messages** tab in the **Error List**.</span></span> <span data-ttu-id="42695-127">**메시지** 탭에서 문제 영역으로 직접 이동할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="42695-127">You can also jump to problem areas directly from the **Messages** tab.</span></span>

![이식성 보고서](./media/portability-analyzer/portability-report.png)

<span data-ttu-id="42695-129">Visual Studio를 사용하고 싶지 않으신가요?</span><span class="sxs-lookup"><span data-stu-id="42695-129">Don’t want to use Visual Studio?</span></span> <span data-ttu-id="42695-130">명령 프롬프트에서 이식성 분석기를 사용할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="42695-130">You can also use the Portability Analyzer from the command prompt.</span></span> <span data-ttu-id="42695-131">[API 이식성 분석기](http://www.microsoft.com/download/details.aspx?id=42678)를 다운로드합니다.</span><span class="sxs-lookup"><span data-stu-id="42695-131">Just download the [API Portability Analyzer](http://www.microsoft.com/download/details.aspx?id=42678).</span></span>

*   <span data-ttu-id="42695-132">현재 디렉터리를 분석하려면 다음 명령을 입력합니다. `\...\ApiPort.exe analyze -f .`</span><span class="sxs-lookup"><span data-stu-id="42695-132">Type the following command to analyze the current directory: `\...\ApiPort.exe analyze -f .`</span></span>
*   <span data-ttu-id="42695-133">.dll 파일의 특정 목록을 분석하려면 다음 명령을 입력합니다. `\...\ApiPort.exe analyze -f first.dll -f second.dll -f third.dll`</span><span class="sxs-lookup"><span data-stu-id="42695-133">To analyze a specific list of .dll files, type the following command: `\...\ApiPort.exe analyze -f first.dll -f second.dll -f third.dll`</span></span>

<span data-ttu-id="42695-134">.NET 이식성 보고서는 현재 디렉터리에 Excel 파일(*.xlsx*)로 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="42695-134">Your .NET Portability Report is saved as an Excel file (*.xlsx*) in your current directory.</span></span> <span data-ttu-id="42695-135">Excel 통합 문서의 **세부 정보** 탭에는 추가 정보가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="42695-135">The **Details** tab in the Excel Workbook contains more information.</span></span>

<span data-ttu-id="42695-136">.NET 이식성 분석기에 대한 자세한 내용은 [GitHub 문서](https://github.com/Microsoft/dotnet-apiport#documentation) 및 [A Brief Look at the .NET Portability Analyzer](https://channel9.msdn.com/Blogs/Seth-Juarez/A-Brief-Look-at-the-NET-Portability-Analyzer)(.NET 이식성 분석기 간단하게 살펴보기) Channel 9 비디오를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="42695-136">For more information on the .NET Portability Analyzer, visit the [GitHub documentation](https://github.com/Microsoft/dotnet-apiport#documentation) and [A Brief Look at the .NET Portability Analyzer](https://channel9.msdn.com/Blogs/Seth-Juarez/A-Brief-Look-at-the-NET-Portability-Analyzer) Channel 9 video.</span></span>

