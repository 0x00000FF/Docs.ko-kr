---
title: "방법: 명령줄 컴파일러 (Visual Basic)를 호출 합니다. | Microsoft 문서"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- command-line arguments
- vbc.exe
- Visual Basic compiler, starting
- command line, arguments
ms.assetid: 0fd9a8f6-f34e-4c35-a49d-9b9bbd8da4a9
caps.latest.revision: 28
author: dotnet-bot
ms.author: dotnetcontent
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: e19bb506b016b774d2c497f8b17d91b35afb3eef
ms.contentlocale: ko-kr
ms.lasthandoff: 04/12/2017

---
# <a name="how-to-invoke-the-command-line-compiler-visual-basic"></a><span data-ttu-id="2293a-102">방법: 명령줄 컴파일러 호출(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="2293a-102">How to: Invoke the Command-Line Compiler (Visual Basic)</span></span>
<span data-ttu-id="2293a-103">MS-DOS 프롬프트 라고도 하는 명령줄에 실행 파일의 이름을 입력 하 여 명령줄 컴파일러를 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2293a-103">You can invoke the command-line compiler by typing the name of its executable file into the command line, also known as the MS-DOS prompt.</span></span> <span data-ttu-id="2293a-104">기본 Windows 명령 프롬프트에서에서 컴파일하는 경우에 실행 파일의 정규화 된 경로 입력 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2293a-104">If you compile from the default Windows Command Prompt, you must type the fully qualified path to the executable file.</span></span> <span data-ttu-id="2293a-105">이 기본 동작을 재정의 하는 방법은 사용 하 여는 [!INCLUDE[vsprvs](../../../csharp/includes/vsprvs_md.md)] 명령 프롬프트를 하거나 PATH 환경 변수를 수정 합니다.</span><span class="sxs-lookup"><span data-stu-id="2293a-105">To override this default behavior, you can either use the [!INCLUDE[vsprvs](../../../csharp/includes/vsprvs_md.md)] Command Prompt, or modify the PATH environment variable.</span></span> <span data-ttu-id="2293a-106">둘 다 컴파일러 이름을 입력 하 여 원하는 디렉터리에서 컴파일할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2293a-106">Both allow you to compile from any directory by simply typing the compiler name.</span></span>  
  
[!INCLUDE[note_settings_general](../../../csharp/language-reference/compiler-messages/includes/note_settings_general_md.md)]  
  
### <a name="to-invoke-the-compiler-using-the-visual-studio-command-prompt"></a><span data-ttu-id="2293a-107">Visual Studio 명령 프롬프트를 사용 하 여 컴파일러를 호출 하려면</span><span class="sxs-lookup"><span data-stu-id="2293a-107">To invoke the compiler using the Visual Studio Command Prompt</span></span>  
  
1.  <span data-ttu-id="2293a-108">Microsoft Visual Studio 프로그램 그룹 내에서 Visual Studio Tools 프로그램 폴더를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="2293a-108">Open the Visual Studio Tools program folder within the Microsoft Visual Studio program group.</span></span>  
  
2.  <span data-ttu-id="2293a-109">사용할 수는 [!INCLUDE[vsprvs](../../../csharp/includes/vsprvs_md.md)] Visual Studio가 설치 된 경우 컴퓨터에 모든 디렉터리에서 컴파일러에 액세스 하려면 명령 프롬프트입니다.</span><span class="sxs-lookup"><span data-stu-id="2293a-109">You can use the [!INCLUDE[vsprvs](../../../csharp/includes/vsprvs_md.md)] Command Prompt to access the compiler from any directory on your machine, if Visual Studio is installed.</span></span>  
  
3.  <span data-ttu-id="2293a-110">호출 된 [!INCLUDE[vsprvs](../../../csharp/includes/vsprvs_md.md)] 명령 프롬프트입니다.</span><span class="sxs-lookup"><span data-stu-id="2293a-110">Invoke the [!INCLUDE[vsprvs](../../../csharp/includes/vsprvs_md.md)] Command Prompt.</span></span>  
  
4.  <span data-ttu-id="2293a-111">명령줄에서 입력 `vbc.exe` *sourceFileName* 한 다음 ENTER를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="2293a-111">At the command line, type `vbc.exe` *sourceFileName* and then press ENTER.</span></span>  
  
     <span data-ttu-id="2293a-112">예를 들어 라는 디렉터리에 소스 코드를 저장 하는 경우 `SourceFiles`를 입력 하 고 명령 프롬프트를 열 때 `cd SourceFiles` 해당 디렉터리로 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="2293a-112">For example, if you stored your source code in a directory called `SourceFiles`, you would open the Command Prompt and type `cd SourceFiles` to change to that directory.</span></span> <span data-ttu-id="2293a-113">디렉터리 라는 소스 파일을 포함 하는 경우 `Source.vb`를 입력 하 여 컴파일할 수 `vbc.exe Source.vb`합니다.</span><span class="sxs-lookup"><span data-stu-id="2293a-113">If the directory contained a source file named `Source.vb`, you could compile it by typing `vbc.exe Source.vb`.</span></span>  
  
### <a name="to-set-the-path-environment-variable-to-the-compiler-for-the-windows-command-prompt"></a><span data-ttu-id="2293a-114">Windows 명령 프롬프트에 대 한 컴파일러에 PATH 환경 변수를 설정 하려면</span><span class="sxs-lookup"><span data-stu-id="2293a-114">To set the PATH environment variable to the compiler for the Windows Command Prompt</span></span>  
  
1.  <span data-ttu-id="2293a-115">로컬 디스크에 Vbc.exe를 찾으려고 Windows 검색 기능을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="2293a-115">Use the Windows Search feature to find Vbc.exe on your local disk.</span></span>  
  
     <span data-ttu-id="2293a-116">컴파일러가 있는 디렉터리의 정확한 이름을 Windows 디렉터리의 위치와의 버전에 따라 달라 집니다는 [!INCLUDE[Compact](../../../visual-basic/reference/command-line-compiler/includes/compact_md.md)] 설치 합니다.</span><span class="sxs-lookup"><span data-stu-id="2293a-116">The exact name of the directory where the compiler is located depends on the location of the Windows directory and the version of the [!INCLUDE[Compact](../../../visual-basic/reference/command-line-compiler/includes/compact_md.md)] installed.</span></span> <span data-ttu-id="2293a-117">버전이 여러 개 있는 경우는 [!INCLUDE[Compact](../../../visual-basic/reference/command-line-compiler/includes/compact_md.md)] 설치 (일반적으로 최신 버전)를 사용 하 여 버전을를 결정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2293a-117">If you have more than one version of the [!INCLUDE[Compact](../../../visual-basic/reference/command-line-compiler/includes/compact_md.md)] installed, you must determine which version to use (typically the latest version).</span></span>  
  
2.  <span data-ttu-id="2293a-118">사용자 **시작** 메뉴를 마우스 오른쪽 단추로 클릭 **내 컴퓨터**, 클릭 하 고 **속성** 바로 가기 메뉴에서.</span><span class="sxs-lookup"><span data-stu-id="2293a-118">From your **Start** Menu, right-click **My Computer**, and then click **Properties** from the shortcut menu.</span></span>  
  
3.  <span data-ttu-id="2293a-119">클릭 하 고 **고급** 탭을 클릭 한 후 **환경 변수**합니다.</span><span class="sxs-lookup"><span data-stu-id="2293a-119">Click the **Advanced** tab, and then click **Environment Variables**.</span></span>  
  
4.  <span data-ttu-id="2293a-120">에 **시스템** 변수 창의 **경로** 의 목록에서 클릭 **편집**합니다.</span><span class="sxs-lookup"><span data-stu-id="2293a-120">In the **System** variables pane, select **Path** from the list and click **Edit**.</span></span>  
  
5.  <span data-ttu-id="2293a-121">에 **편집 시스템** 변수 대화 상자에서 문자열의 끝에 삽입 지점을 이동는 **변수 값** 필드를 세미콜론 (;)을 입력 1 단계에서에서 찾은 전체 디렉터리 이름이 차례로 나옵니다.</span><span class="sxs-lookup"><span data-stu-id="2293a-121">In the **Edit System** Variable dialog box, move the insertion point to the end of the string in the **Variable Value** field and type a semicolon (;) followed by the full directory name found in Step 1.</span></span>  
  
6.  <span data-ttu-id="2293a-122">클릭 **확인** 편집 내용을 확인 하 여 대화 상자를 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="2293a-122">Click **OK** to confirm your edits and close the dialog boxes.</span></span>  
  
     <span data-ttu-id="2293a-123">PATH 환경 변수를 변경한 후 실행할 수 있습니다는 [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] 컴퓨터에 모든 디렉터리에서 Windows 명령 프롬프트에서 컴파일러입니다.</span><span class="sxs-lookup"><span data-stu-id="2293a-123">After you change the PATH environment variable, you can run the [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] compiler at the Windows Command Prompt from any directory on the computer.</span></span>  
  
### <a name="to-invoke-the-compiler-using-the-windows-command-prompt"></a><span data-ttu-id="2293a-124">Windows 명령 프롬프트를 사용 하 여 컴파일러를 호출 하려면</span><span class="sxs-lookup"><span data-stu-id="2293a-124">To invoke the compiler using the Windows Command Prompt</span></span>  
  
1.  <span data-ttu-id="2293a-125">**시작** 메뉴를 클릭은 **액세서리** 폴더를 연 후의 **Windows 명령 프롬프트**합니다.</span><span class="sxs-lookup"><span data-stu-id="2293a-125">From the **Start** menu, click on the **Accessories** folder, and then open the **Windows Command Prompt**.</span></span>  
  
2.  <span data-ttu-id="2293a-126">명령줄에서 입력 `vbc.exe` *sourceFileName* 한 다음 ENTER를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="2293a-126">At the command line, type `vbc.exe`*sourceFileName* and then press ENTER.</span></span>  
  
     <span data-ttu-id="2293a-127">예를 들어 라는 디렉터리에 소스 코드를 저장 하는 경우 `SourceFiles`를 입력 하 고 명령 프롬프트를 열 때 `cd SourceFiles` 해당 디렉터리로 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="2293a-127">For example, if you stored your source code in a directory called `SourceFiles`, you would open the Command Prompt and type `cd SourceFiles` to change to that directory.</span></span> <span data-ttu-id="2293a-128">디렉터리 라는 소스 파일을 포함 하는 경우 `Source.vb`를 입력 하 여 컴파일할 수 `vbc.exe Source.vb`합니다.</span><span class="sxs-lookup"><span data-stu-id="2293a-128">If the directory contained a source file named `Source.vb`, you could compile it by typing `vbc.exe Source.vb`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2293a-129">참고 항목</span><span class="sxs-lookup"><span data-stu-id="2293a-129">See Also</span></span>  
 <span data-ttu-id="2293a-130">[Visual Basic 명령줄 컴파일러](../../../visual-basic/reference/command-line-compiler/index.md) </span><span class="sxs-lookup"><span data-stu-id="2293a-130">[Visual Basic Command-Line Compiler](../../../visual-basic/reference/command-line-compiler/index.md) </span></span>  
<span data-ttu-id="2293a-131"> [조건부 컴파일](../../../visual-basic/programming-guide/program-structure/conditional-compilation.md)</span><span class="sxs-lookup"><span data-stu-id="2293a-131"> [Conditional Compilation](../../../visual-basic/programming-guide/program-structure/conditional-compilation.md)</span></span>
