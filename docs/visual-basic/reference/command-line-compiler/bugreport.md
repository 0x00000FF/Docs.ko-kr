---
title: -bugreport
ms.date: 03/08/2018
helpviewer_keywords:
- -bugreport compiler option [Visual Basic]
- bugreport compiler option [Visual Basic]
- /bugreport compiler option [Visual Basic]
ms.assetid: e4325406-8dbd-4b48-b311-9ee0799e48bb
ms.openlocfilehash: e7b4ebc58b6fe9850b92ef945cb0d715e4369efe
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "58820913"
---
# <a name="-bugreport"></a><span data-ttu-id="63073-102">-bugreport</span><span class="sxs-lookup"><span data-stu-id="63073-102">-bugreport</span></span>
<span data-ttu-id="63073-103">버그 보고서를 파일로 작성할 때는 사용할 수 있는 파일을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="63073-103">Creates a file that you can use when you file a bug report.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="63073-104">구문</span><span class="sxs-lookup"><span data-stu-id="63073-104">Syntax</span></span>  
  
```  
-bugreport:file  
```  
  
## <a name="arguments"></a><span data-ttu-id="63073-105">인수</span><span class="sxs-lookup"><span data-stu-id="63073-105">Arguments</span></span>  
  
|<span data-ttu-id="63073-106">용어</span><span class="sxs-lookup"><span data-stu-id="63073-106">Term</span></span>|<span data-ttu-id="63073-107">정의</span><span class="sxs-lookup"><span data-stu-id="63073-107">Definition</span></span>|  
|---|---|  
|`file`|<span data-ttu-id="63073-108">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="63073-108">Required.</span></span> <span data-ttu-id="63073-109">버그 보고서를 포함 하는 파일의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="63073-109">The name of the file that will contain your bug report.</span></span> <span data-ttu-id="63073-110">파일 이름을 따옴표로 묶습니다 ("") 이름에 공백이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="63073-110">Enclose the file name in quotation marks (" ") if the name contains a space.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="63073-111">설명</span><span class="sxs-lookup"><span data-stu-id="63073-111">Remarks</span></span>  
 <span data-ttu-id="63073-112">다음 정보를 추가할 `file`:</span><span class="sxs-lookup"><span data-stu-id="63073-112">The following information is added to `file`:</span></span>  
  
-   <span data-ttu-id="63073-113">컴파일할 때 모든 소스 코드 파일의 복사본입니다.</span><span class="sxs-lookup"><span data-stu-id="63073-113">A copy of all source-code files in the compilation.</span></span>  
  
-   <span data-ttu-id="63073-114">컴파일에 사용 된 컴파일러 옵션의 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="63073-114">A list of the compiler options used in the compilation.</span></span>  
  
-   <span data-ttu-id="63073-115">컴파일러, 공용 언어 런타임 및 운영 체제에 대 한 버전 정보입니다.</span><span class="sxs-lookup"><span data-stu-id="63073-115">Version information about your compiler, common language runtime, and operating system.</span></span>  
  
-   <span data-ttu-id="63073-116">컴파일러 출력입니다(있는 경우).</span><span class="sxs-lookup"><span data-stu-id="63073-116">Compiler output, if any.</span></span>  
  
-   <span data-ttu-id="63073-117">메시지가 표시 되는 문제를 설명입니다.</span><span class="sxs-lookup"><span data-stu-id="63073-117">A description of the problem, for which you are prompted.</span></span>  
  
-   <span data-ttu-id="63073-118">메시지가 표시 되는 문제를 생각 하는 방법에 대 한 설명을 수정 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="63073-118">A description of how you think the problem should be fixed, for which you are prompted.</span></span>  
  
 <span data-ttu-id="63073-119">모든 소스 코드 파일의 복사본에 포함 되어 있으므로 `file`을 최대한 짧은 프로그램에 코드 결함을 재현 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="63073-119">Because a copy of all source-code files is included in `file`, you may want to reproduce the (suspected) code defect in the shortest possible program.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="63073-120">`-bugreport` 옵션은 잠재적으로 중요 한 정보가 포함 된 파일을 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="63073-120">The `-bugreport` option produces a file that contains potentially sensitive information.</span></span> <span data-ttu-id="63073-121">현재 컴파일러 버전을 여기에 [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] 버전, OS 버전, 사용자 이름, 명령줄 인수는 컴파일러가 실행 된 모든 소스 코드와 참조 된 어셈블리의 이진 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="63073-121">This includes current time, compiler version, [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] version, OS version, user name, the command-line arguments with which the compiler was run, all source code, and the binary form of any referenced assembly.</span></span> <span data-ttu-id="63073-122">이 옵션의 서버 쪽 컴파일에 Web.config 파일에서 명령줄 옵션을 지정 하 여 액세스할 수는 [!INCLUDE[vstecasp](~/includes/vstecasp-md.md)] 응용 프로그램입니다.</span><span class="sxs-lookup"><span data-stu-id="63073-122">This option can be accessed by specifying command-line options in the Web.config file for a server-side compilation of an [!INCLUDE[vstecasp](~/includes/vstecasp-md.md)] application.</span></span> <span data-ttu-id="63073-123">이 방지 하려면 사용자가 서버에서 컴파일하지 합니다 Machine.config 파일을 수정 합니다.</span><span class="sxs-lookup"><span data-stu-id="63073-123">To prevent this, modify the Machine.config file to disallow users from compiling on the server.</span></span>  
  
 <span data-ttu-id="63073-124">이 옵션을 사용 하 여 사용 하는 경우 `-errorreport:prompt`, `-errorreport:queue`, 또는 `-errorreport:send`, 응용 프로그램에서 정보를 내부 컴파일러 오류를 발견 한 `file` Microsoft Corporation에 전송 됩니다.</span><span class="sxs-lookup"><span data-stu-id="63073-124">If this option is used with `-errorreport:prompt`, `-errorreport:queue`, or `-errorreport:send`, and your application encounters an internal compiler error, the information in `file` is sent to Microsoft Corporation.</span></span> <span data-ttu-id="63073-125">이 정보는 Microsoft 엔지니어가 오류의 원인을 파악 하는 데 도움이 되며 Visual Basic의 다음 릴리스를 개선 하는 데 도움이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="63073-125">That information will help Microsoft engineers identify the cause of the error and may help improve the next release of Visual Basic.</span></span> <span data-ttu-id="63073-126">기본적으로 정보가 Microsoft로 전송 됩니다.</span><span class="sxs-lookup"><span data-stu-id="63073-126">By default, no information is sent to Microsoft.</span></span> <span data-ttu-id="63073-127">그러나 컴파일하는 경우 응용 프로그램 사용 하 여 `-errorreport:queue`기본적으로 설정 되는, 응용 프로그램은 해당 오류 보고서를 수집 합니다.</span><span class="sxs-lookup"><span data-stu-id="63073-127">However, when you compile an application by using `-errorreport:queue`, which is enabled by default, the application collects its error reports.</span></span> <span data-ttu-id="63073-128">그런 다음 컴퓨터의 관리자가 로그인 할 때 오류 보고 시스템 관리자 로그온 이후 발생 한 모든 오류를 보고 하는 Microsoft로 전달할 수 있도록 하는 팝업 창을 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="63073-128">Then, when the computer's administrator logs in, the error reporting system displays a pop-up window that enables the administrator to forward to Microsoft any error reports that occurred since the logon.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="63073-129">`/bugreport` 옵션은 Visual Studio 개발 환경 내에서 사용할 수 없는 경우 즉, 사용 가능한 명령줄에서 컴파일할 때만 합니다.</span><span class="sxs-lookup"><span data-stu-id="63073-129">The `/bugreport` option is not available from within the Visual Studio development environment; it is available only when you compile from the command line.</span></span>  
  
## <a name="example"></a><span data-ttu-id="63073-130">예제</span><span class="sxs-lookup"><span data-stu-id="63073-130">Example</span></span>  
 <span data-ttu-id="63073-131">다음 예제에서는 컴파일합니다 `T2.vb` 파일에서 모든 버그 보고 정보를 저장 하 고 `Problem.txt`입니다.</span><span class="sxs-lookup"><span data-stu-id="63073-131">The following example compiles `T2.vb` and puts all bug-reporting information in the file `Problem.txt`.</span></span>  
  
```  
vbc -bugreport:problem.txt t2.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="63073-132">참고자료</span><span class="sxs-lookup"><span data-stu-id="63073-132">See also</span></span>

- [<span data-ttu-id="63073-133">Visual Basic 명령줄 컴파일러</span><span class="sxs-lookup"><span data-stu-id="63073-133">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="63073-134">-디버그 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="63073-134">-debug (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/debug.md)
- [<span data-ttu-id="63073-135">-errorreport</span><span class="sxs-lookup"><span data-stu-id="63073-135">-errorreport</span></span>](../../../visual-basic/reference/command-line-compiler/errorreport.md)
- [<span data-ttu-id="63073-136">샘플 컴파일 명령줄</span><span class="sxs-lookup"><span data-stu-id="63073-136">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
- <span data-ttu-id="63073-137">[securityPolicy (ASP.NET 설정 스키마)에 대 한 trustLevel 요소](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/as399f0x(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="63073-137">[trustLevel Element for securityPolicy (ASP.NET Settings Schema)](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/as399f0x(v=vs.100))</span></span>
