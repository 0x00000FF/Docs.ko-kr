---
title: -sdkpath
ms.date: 07/20/2015
f1_keywords:
- sdkpath
- -sdkpath
helpviewer_keywords:
- -sdkpath compiler option [Visual Basic]
- /sdkpath compiler option [Visual Basic]
- sdkpath compiler option [Visual Basic]
ms.assetid: fec8a3f1-b791-4a37-8af7-344859f8212d
ms.openlocfilehash: bf665082f079901ec45122ce7797090b7519fafe
ms.sourcegitcommit: 9bd8f213b50f0e1a73e03bd1e840c917fbd6d20a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2018
ms.locfileid: "50046801"
---
# <a name="-sdkpath"></a><span data-ttu-id="23d86-102">-sdkpath</span><span class="sxs-lookup"><span data-stu-id="23d86-102">-sdkpath</span></span>
<span data-ttu-id="23d86-103">Mscorlib.dll 및 Microsoft.VisualBasic.dll의 위치를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="23d86-103">Specifies the location of mscorlib.dll and Microsoft.VisualBasic.dll.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="23d86-104">구문</span><span class="sxs-lookup"><span data-stu-id="23d86-104">Syntax</span></span>  
  
```  
-sdkpath:path  
```  
  
## <a name="arguments"></a><span data-ttu-id="23d86-105">인수</span><span class="sxs-lookup"><span data-stu-id="23d86-105">Arguments</span></span>  
 `path`  
 <span data-ttu-id="23d86-106">Mscorlib.dll 및 Microsoft.VisualBasic.dll 컴파일에 사용할의 버전이 포함 된 디렉터리입니다.</span><span class="sxs-lookup"><span data-stu-id="23d86-106">The directory containing the versions of mscorlib.dll and Microsoft.VisualBasic.dll to use for compilation.</span></span> <span data-ttu-id="23d86-107">이 경로 로드 될 때까지 확인 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="23d86-107">This path is not verified until it is loaded.</span></span> <span data-ttu-id="23d86-108">디렉터리 이름을 따옴표로 묶습니다 ("")에 공백이 있는 경우.</span><span class="sxs-lookup"><span data-stu-id="23d86-108">Enclose the directory name in quotation marks (" ") if it contains a space.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="23d86-109">설명</span><span class="sxs-lookup"><span data-stu-id="23d86-109">Remarks</span></span>  
 <span data-ttu-id="23d86-110">이 옵션을 Visual Basic 컴파일러가 기본이 아닌 위치에서 mscorlib.dll 및 Microsoft.VisualBasic.dll 파일을 로드 합니다.</span><span class="sxs-lookup"><span data-stu-id="23d86-110">This option tells the Visual Basic compiler to load the mscorlib.dll and Microsoft.VisualBasic.dll files from a non-default location.</span></span> <span data-ttu-id="23d86-111">합니다 `-sdkpath` 옵션은 사용 하도록 설계 되었습니다 [-netcf](../../../visual-basic/reference/command-line-compiler/netcf.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="23d86-111">The `-sdkpath` option was designed to be used with [-netcf](../../../visual-basic/reference/command-line-compiler/netcf.md).</span></span> <span data-ttu-id="23d86-112">[!INCLUDE[Compact](~/includes/compact-md.md)] 이러한 서로 다른 버전을 사용 하 여 형식 및 장치에 없는 언어 기능을 사용 하지 않는 라이브러리를 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="23d86-112">The [!INCLUDE[Compact](~/includes/compact-md.md)] uses different versions of these support libraries to avoid the use of types and language features not found on the devices.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="23d86-113">`-sdkpath` 옵션은 Visual Studio 개발 환경 내에서 사용할 수 있는 명령줄에서 컴파일할 경우에 사용할 수 있는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="23d86-113">The `-sdkpath` option is not available from within the Visual Studio development environment; it is available only when compiling from the command line.</span></span> <span data-ttu-id="23d86-114">`-sdkpath` Visual Basic 장치 프로젝트를 로드 하면 옵션이 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="23d86-114">The `-sdkpath` option is set when a Visual Basic device project is loaded.</span></span>  
  
 <span data-ttu-id="23d86-115">컴파일러를 사용 하 여 Visual Basic 런타임 라이브러리에 대 한 참조 없이 컴파일하도록 할지 지정할 수 있습니다는 `-vbruntime` 컴파일러 옵션입니다.</span><span class="sxs-lookup"><span data-stu-id="23d86-115">You can specify that the compiler should compile without a reference to the Visual Basic Runtime Library by using the `-vbruntime` compiler option.</span></span> <span data-ttu-id="23d86-116">자세한 내용은 [-vbruntime](../../../visual-basic/reference/command-line-compiler/vbruntime.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="23d86-116">For more information, see [-vbruntime](../../../visual-basic/reference/command-line-compiler/vbruntime.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="23d86-117">예제</span><span class="sxs-lookup"><span data-stu-id="23d86-117">Example</span></span>  
 <span data-ttu-id="23d86-118">다음 코드에서는 `Myfile.vb` 사용 하 여 합니다 [!INCLUDE[Compact](~/includes/compact-md.md)]의 기본 설치 디렉터리에서 찾을 Mscorlib.dll 및 Microsoft.VisualBasic.dll의 버전을 사용 하는 [!INCLUDE[Compact](~/includes/compact-md.md)] C 드라이브에 합니다.</span><span class="sxs-lookup"><span data-stu-id="23d86-118">The following code compiles `Myfile.vb` with the [!INCLUDE[Compact](~/includes/compact-md.md)], using the versions of Mscorlib.dll and Microsoft.VisualBasic.dll found in the default installation directory of the [!INCLUDE[Compact](~/includes/compact-md.md)] on the C drive.</span></span> <span data-ttu-id="23d86-119">최신 버전의 사용은 일반적으로 [!INCLUDE[Compact](~/includes/compact-md.md)]합니다.</span><span class="sxs-lookup"><span data-stu-id="23d86-119">Typically, you would use the most recent version of the [!INCLUDE[Compact](~/includes/compact-md.md)].</span></span>  
  
```console
vbc -netcf -sdkpath:"c:\Program Files\Microsoft Visual Studio .NET 2003\CompactFrameworkSDK\v1.0.5000\Windows CE " myfile.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="23d86-120">참고 항목</span><span class="sxs-lookup"><span data-stu-id="23d86-120">See Also</span></span>  
 [<span data-ttu-id="23d86-121">Visual Basic 명령줄 컴파일러</span><span class="sxs-lookup"><span data-stu-id="23d86-121">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)  
 [<span data-ttu-id="23d86-122">샘플 컴파일 명령줄</span><span class="sxs-lookup"><span data-stu-id="23d86-122">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)  
 [<span data-ttu-id="23d86-123">-netcf</span><span class="sxs-lookup"><span data-stu-id="23d86-123">-netcf</span></span>](../../../visual-basic/reference/command-line-compiler/netcf.md)  
 [<span data-ttu-id="23d86-124">-vbruntime</span><span class="sxs-lookup"><span data-stu-id="23d86-124">-vbruntime</span></span>](../../../visual-basic/reference/command-line-compiler/vbruntime.md)
