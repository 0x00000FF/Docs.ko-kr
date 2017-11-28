---
title: "명령줄에서 빌드(Visual Basic)"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- builds [Visual Basic], command-line
- Visual Basic compiler, about Visual Basic compiler
- command line [Visual Basic], compilers
- command line [Visual Basic], building from
- command line [Visual Basic], builds
- compilers [Visual Basic], invoking from command line
- command-line builds
- compiling source code
- command-line compilers [Visual Basic], Visual Basic
- command line [Visual Basic], Visual Basic
ms.assetid: e61947e9-a42e-4717-a699-5f70a98cdd03
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: d982506af2c4f01e80ae5b3862fcbcfff2aa9d99
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/22/2017
---
# <a name="building-from-the-command-line-visual-basic"></a><span data-ttu-id="7547a-102">명령줄에서 빌드(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="7547a-102">Building from the Command Line (Visual Basic)</span></span>
<span data-ttu-id="7547a-103">A [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] 프로젝트 하나 이상의 별도 소스 파일로 구성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7547a-103">A [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] project is made up of one or more separate source files.</span></span> <span data-ttu-id="7547a-104">컴파일 이라는 프로세스 동안 이러한 파일 통합할 하나의 패키지로-응용 프로그램으로 실행할 수 있는 단일 실행 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="7547a-104">During the process known as compilation, these files are brought together into one package—a single executable file that can be run as an application.</span></span>  
  
 [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]<span data-ttu-id="7547a-105">내에서 프로그램을 컴파일 하는 대신 명령줄 컴파일러를 제공는 [!INCLUDE[vsprvs](~/includes/vsprvs-md.md)] 통합된 개발 환경 (IDE).</span><span class="sxs-lookup"><span data-stu-id="7547a-105"> provides a command-line compiler as an alternative to compiling programs from within the [!INCLUDE[vsprvs](~/includes/vsprvs-md.md)] integrated development environment (IDE).</span></span> <span data-ttu-id="7547a-106">명령줄 컴파일러는 필요 하지 않으면 IDE의 기능 중 일부만 상황 용인지-예를 들어 경우 있습니다 하거나 작성 하는 제한 된 시스템 메모리 또는 저장소 공간이 있는 컴퓨터에 대 한 합니다.</span><span class="sxs-lookup"><span data-stu-id="7547a-106">The command-line compiler is designed for situations in which you do not require the full set of features in the IDE—for example, when you are using or writing for computers with limited system memory or storage space.</span></span>  
  
 <span data-ttu-id="7547a-107">Microsoft를 명령줄에서 컴파일하는 경우 명시적으로 참조 해야 [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] 를 통해 런타임 라이브러리는 `/reference` 컴파일러 옵션입니다.</span><span class="sxs-lookup"><span data-stu-id="7547a-107">When compiling from the command line, you must explicitly reference the Microsoft [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] run-time library through the `/reference` compiler option.</span></span>  
  
 <span data-ttu-id="7547a-108">내에서 소스 파일을 컴파일하는 [!INCLUDE[vsprvs](~/includes/vsprvs-md.md)] IDE, 선택는 **빌드** 명령을 **빌드** 메뉴.</span><span class="sxs-lookup"><span data-stu-id="7547a-108">To compile source files from within the [!INCLUDE[vsprvs](~/includes/vsprvs-md.md)] IDE, choose the **Build** command from the **Build** menu.</span></span>  
  
> [!TIP]
>  <span data-ttu-id="7547a-109">연결 된 작업에 대 한 정보를 표시할 수는 Visual Studio IDE를 사용 하 여 프로젝트 파일을 빌드할 때 **vbc** 명령 및 출력 창에 해당 스위치입니다.</span><span class="sxs-lookup"><span data-stu-id="7547a-109">When you build project files by using the Visual Studio IDE, you can display information about the associated **vbc** command and its switches in the output window.</span></span> <span data-ttu-id="7547a-110">이 정보를 표시 하려면 엽니다는 [옵션 대화 상자, 프로젝트 및 솔루션, 빌드 및 실행](/visualstudio/ide/reference/options-dialog-box-projects-and-solutions-build-and-run)를 설정한는 **MSBuild 프로젝트 빌드 출력의 자세한 정도** 를 **보통** 또는 더 높은 수준의 세부 정보 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="7547a-110">To display this information, open the [Options Dialog Box,  Projects and Solutions, Build and Run](/visualstudio/ide/reference/options-dialog-box-projects-and-solutions-build-and-run), and then set the **MSBuild project build output verbosity** to **Normal** or a higher level of verbosity.</span></span> <span data-ttu-id="7547a-111">자세한 내용은 [방법: 빌드 로그 파일 보기, 저장 및 구성](http://msdn.microsoft.com/library/75d38b76-26d6-4f43-bbe7-cbacd7cc81e7)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="7547a-111">For more information, see [How to: View, Save, and Configure Build Log Files](http://msdn.microsoft.com/library/75d38b76-26d6-4f43-bbe7-cbacd7cc81e7).</span></span>  
  
 <span data-ttu-id="7547a-112">MSBuild를 사용 하 여 명령 프롬프트에서 프로젝트 (.vbproj) 파일을 컴파일할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7547a-112">You can compile project (.vbproj) files at a command prompt by using MSBuild.</span></span> <span data-ttu-id="7547a-113">자세한 내용은 참조 [Command-Line Reference](/visualstudio/msbuild/msbuild-command-line-reference) 및 [연습: MSBuild를 사용 하 여](/visualstudio/msbuild/walkthrough-using-msbuild)합니다.</span><span class="sxs-lookup"><span data-stu-id="7547a-113">For more information, see [Command-Line Reference](/visualstudio/msbuild/msbuild-command-line-reference) and [Walkthrough: Using MSBuild](/visualstudio/msbuild/walkthrough-using-msbuild).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="7547a-114">단원 내용</span><span class="sxs-lookup"><span data-stu-id="7547a-114">In This Section</span></span>  
 [<span data-ttu-id="7547a-115">방법: 명령줄 컴파일러 호출</span><span class="sxs-lookup"><span data-stu-id="7547a-115">How to: Invoke the Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/how-to-invoke-the-command-line-compiler.md)  
 <span data-ttu-id="7547a-116">MS-DOS 프롬프트 또는 특정 하위 디렉터리에서 명령줄 컴파일러를 호출 하는 방법을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="7547a-116">Describes how to invoke the command-line compiler at the MS-DOS prompt or from a specific subdirectory.</span></span>  
  
 [<span data-ttu-id="7547a-117">샘플 컴파일 명령줄</span><span class="sxs-lookup"><span data-stu-id="7547a-117">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)  
 <span data-ttu-id="7547a-118">사용자만 수정할 수 있는 샘플 명령줄의 목록을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="7547a-118">Provides a list of sample command lines that you can modify for your own use.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="7547a-119">관련 단원</span><span class="sxs-lookup"><span data-stu-id="7547a-119">Related Sections</span></span>  
 [<span data-ttu-id="7547a-120">Visual Basic 명령줄 컴파일러</span><span class="sxs-lookup"><span data-stu-id="7547a-120">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)  
 <span data-ttu-id="7547a-121">컴파일러 옵션을 사전순 또는 용도 따라 구성의 목록을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="7547a-121">Provides lists of compiler options, organized alphabetically or by purpose.</span></span>  
  
 [<span data-ttu-id="7547a-122">조건부 컴파일</span><span class="sxs-lookup"><span data-stu-id="7547a-122">Conditional Compilation</span></span>](../../../visual-basic/programming-guide/program-structure/conditional-compilation.md)  
 <span data-ttu-id="7547a-123">코드의 특정 섹션을 컴파일하는 방법에 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="7547a-123">Describes how to compile particular sections of code.</span></span>  
  
 [<span data-ttu-id="7547a-124">Visual Studio에서 프로젝트 및 솔루션 빌드 및 정리</span><span class="sxs-lookup"><span data-stu-id="7547a-124">Building and Cleaning Projects and Solutions in Visual Studio</span></span>](/visualstudio/ide/building-and-cleaning-projects-and-solutions-in-visual-studio)  
 <span data-ttu-id="7547a-125">다양 한 빌드에 포함 될 것, 프로젝트 속성을 선택 및 올바른 순서로 프로젝트를 빌드하는 기능을 구성 하는 방법에 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="7547a-125">Describes how to organize what will be included in different builds, choose project properties, and ensure that projects build in the correct order.</span></span>
