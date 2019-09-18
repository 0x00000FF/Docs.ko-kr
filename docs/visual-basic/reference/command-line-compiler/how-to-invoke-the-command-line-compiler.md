---
title: '방법: 명령줄 컴파일러 호출 (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- command-line arguments
- vbc.exe
- Visual Basic compiler, starting
- command line [Visual Basic], arguments
ms.assetid: 0fd9a8f6-f34e-4c35-a49d-9b9bbd8da4a9
ms.openlocfilehash: a81d5b4f4eae76b0306e2d27475cb8527bda0ff2
ms.sourcegitcommit: 289e06e904b72f34ac717dbcc5074239b977e707
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/17/2019
ms.locfileid: "71054225"
---
# <a name="how-to-invoke-the-command-line-compiler-visual-basic"></a><span data-ttu-id="56525-102">방법: 명령줄 컴파일러 호출 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="56525-102">How to: Invoke the Command-Line Compiler (Visual Basic)</span></span>

<span data-ttu-id="56525-103">명령줄에서 실행 파일의 이름을 입력 하 여 명령줄 컴파일러를 호출할 수 있습니다 .이는 MS-DOS 프롬프트 라고도 합니다.</span><span class="sxs-lookup"><span data-stu-id="56525-103">You can invoke the command-line compiler by typing the name of its executable file into the command line, also known as the MS-DOS prompt.</span></span> <span data-ttu-id="56525-104">기본 Windows 명령 프롬프트에서 컴파일하는 경우 실행 파일의 정규화 된 경로를 입력 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="56525-104">If you compile from the default Windows Command Prompt, you must type the fully qualified path to the executable file.</span></span> <span data-ttu-id="56525-105">이 기본 동작을 재정의 하려면 Visual Studio 용 개발자 명령 프롬프트를 사용 하거나 PATH 환경 변수를 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="56525-105">To override this default behavior, you can either use the Developer Command Prompt for Visual Studio, or modify the PATH environment variable.</span></span> <span data-ttu-id="56525-106">둘 다 컴파일러 이름을 입력 하기만 하면 모든 디렉터리에서 컴파일할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="56525-106">Both allow you to compile from any directory by simply typing the compiler name.</span></span>

[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]

## <a name="to-invoke-the-compiler-using-the-developer-command-prompt-for-visual-studio"></a><span data-ttu-id="56525-107">Visual Studio에 대 한 개발자 명령 프롬프트를 사용 하 여 컴파일러를 호출 하려면</span><span class="sxs-lookup"><span data-stu-id="56525-107">To invoke the compiler using the Developer Command Prompt for Visual Studio</span></span>

1. <span data-ttu-id="56525-108">Microsoft Visual Studio 프로그램 그룹 내에서 Visual Studio Tools 프로그램 폴더를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="56525-108">Open the Visual Studio Tools program folder within the Microsoft Visual Studio program group.</span></span>

2. <span data-ttu-id="56525-109">Visual studio가 설치 되어 있는 경우 Visual Studio 용 개발자 명령 프롬프트를 사용 하 여 컴퓨터의 모든 디렉터리에서 컴파일러에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="56525-109">You can use the Developer Command Prompt for Visual Studio to access the compiler from any directory on your machine, if Visual Studio is installed.</span></span>

3. <span data-ttu-id="56525-110">Visual Studio에 대 한 개발자 명령 프롬프트를 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="56525-110">Invoke the Developer Command Prompt for Visual Studio.</span></span>

4. <span data-ttu-id="56525-111">명령줄에 *sourcefilename* 을 입력 `vbc.exe` 한 다음 enter 키를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="56525-111">At the command line, type `vbc.exe` *sourceFileName* and then press ENTER.</span></span>

    <span data-ttu-id="56525-112">예를 들어, 라는 `SourceFiles`디렉터리에 소스 코드를 저장 한 경우 명령 프롬프트를 열고를 입력 `cd SourceFiles` 하 여 해당 디렉터리로 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="56525-112">For example, if you stored your source code in a directory called `SourceFiles`, you would open the Command Prompt and type `cd SourceFiles` to change to that directory.</span></span> <span data-ttu-id="56525-113">디렉터리에 라는 `Source.vb`원본 파일이 있는 경우를 입력 `vbc.exe Source.vb`하 여 컴파일할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="56525-113">If the directory contained a source file named `Source.vb`, you could compile it by typing `vbc.exe Source.vb`.</span></span>

## <a name="to-set-the-path-environment-variable-to-the-compiler-for-the-windows-command-prompt"></a><span data-ttu-id="56525-114">PATH 환경 변수를 Windows 명령 프롬프트의 컴파일러로 설정 하려면</span><span class="sxs-lookup"><span data-stu-id="56525-114">To set the PATH environment variable to the compiler for the Windows Command Prompt</span></span>

1. <span data-ttu-id="56525-115">Windows 검색 기능을 사용 하 여 로컬 디스크에서 Vbc.exe를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="56525-115">Use the Windows Search feature to find Vbc.exe on your local disk.</span></span>

    <span data-ttu-id="56525-116">컴파일러가 있는 디렉터리의 정확한 이름은 Windows 디렉터리의 위치와 설치 된 ".NET Framework"의 버전에 따라 달라 집니다.</span><span class="sxs-lookup"><span data-stu-id="56525-116">The exact name of the directory where the compiler is located depends on the location of the Windows directory and the version of the ".NET Framework" installed.</span></span> <span data-ttu-id="56525-117">".NET Framework" 버전이 둘 이상 설치 되어 있는 경우 사용할 버전 (일반적으로 최신 버전)을 결정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="56525-117">If you have more than one version of the ".NET Framework" installed, you must determine which version to use (typically the latest version).</span></span>

2. <span data-ttu-id="56525-118">**시작** 메뉴에서 **내 컴퓨터**를 마우스 오른쪽 단추로 클릭 한 다음 바로 가기 메뉴에서 **속성** 을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="56525-118">From your **Start** Menu, right-click **My Computer**, and then click **Properties** from the shortcut menu.</span></span>

3. <span data-ttu-id="56525-119">**고급** 탭을 클릭 한 다음 **환경 변수**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="56525-119">Click the **Advanced** tab, and then click **Environment Variables**.</span></span>

4. <span data-ttu-id="56525-120">**시스템** 변수 창의 목록에서 **경로** 를 선택 하 고 **편집**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="56525-120">In the **System** variables pane, select **Path** from the list and click **Edit**.</span></span>

5. <span data-ttu-id="56525-121">시스템 변수 **편집** 대화 상자에서 **변수 값** 필드에 있는 문자열의 끝 부분으로 삽입 지점을 이동 하 고 세미콜론 (;)을 입력 합니다. 다음에 1 단계에서 찾은 전체 디렉터리 이름을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="56525-121">In the **Edit System** Variable dialog box, move the insertion point to the end of the string in the **Variable Value** field and type a semicolon (;) followed by the full directory name found in Step 1.</span></span>

6. <span data-ttu-id="56525-122">**확인** 을 클릭 하 여 편집 내용을 확인 하 고 대화 상자를 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="56525-122">Click **OK** to confirm your edits and close the dialog boxes.</span></span>

     <span data-ttu-id="56525-123">PATH 환경 변수를 변경한 후에는 컴퓨터의 모든 디렉터리에서 Windows 명령 프롬프트에서 Visual Basic 컴파일러를 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="56525-123">After you change the PATH environment variable, you can run the Visual Basic compiler at the Windows Command Prompt from any directory on the computer.</span></span>

## <a name="to-invoke-the-compiler-using-the-windows-command-prompt"></a><span data-ttu-id="56525-124">Windows 명령 프롬프트를 사용 하 여 컴파일러를 호출 하려면</span><span class="sxs-lookup"><span data-stu-id="56525-124">To invoke the compiler using the Windows Command Prompt</span></span>

1. <span data-ttu-id="56525-125">**시작** 메뉴에서 **보조 프로그램** 폴더를 클릭 하 고 **Windows 명령 프롬프트**를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="56525-125">From the **Start** menu, click on the **Accessories** folder, and then open the **Windows Command Prompt**.</span></span>

2. <span data-ttu-id="56525-126">명령줄에 *sourcefilename* 을 입력 `vbc.exe`한 다음 enter 키를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="56525-126">At the command line, type `vbc.exe`*sourceFileName* and then press ENTER.</span></span>

     <span data-ttu-id="56525-127">예를 들어, 라는 `SourceFiles`디렉터리에 소스 코드를 저장 한 경우 명령 프롬프트를 열고를 입력 `cd SourceFiles` 하 여 해당 디렉터리로 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="56525-127">For example, if you stored your source code in a directory called `SourceFiles`, you would open the Command Prompt and type `cd SourceFiles` to change to that directory.</span></span> <span data-ttu-id="56525-128">디렉터리에 라는 `Source.vb`원본 파일이 있는 경우를 입력 `vbc.exe Source.vb`하 여 컴파일할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="56525-128">If the directory contained a source file named `Source.vb`, you could compile it by typing `vbc.exe Source.vb`.</span></span>

## <a name="see-also"></a><span data-ttu-id="56525-129">참고자료</span><span class="sxs-lookup"><span data-stu-id="56525-129">See also</span></span>

- [<span data-ttu-id="56525-130">Visual Basic 명령줄 컴파일러</span><span class="sxs-lookup"><span data-stu-id="56525-130">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="56525-131">조건부 컴파일</span><span class="sxs-lookup"><span data-stu-id="56525-131">Conditional Compilation</span></span>](../../../visual-basic/programming-guide/program-structure/conditional-compilation.md)
