---
title: -win32resource
ms.date: 03/13/2018
f1_keywords:
- -win32resource
- win32resource
helpviewer_keywords:
- /win32resource compiler option [Visual Basic]
- -win32resource compiler option [Visual Basic]
- win32resource compiler option [Visual Basic]
ms.assetid: e226946d-19ce-4cc9-91f5-aed24f77aa2b
ms.openlocfilehash: 382dcc6571aa06ecdfc32bf43080c4b7a36eb1f0
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2019
ms.locfileid: "69961299"
---
# <a name="-win32resource"></a><span data-ttu-id="9fa82-102">-win32resource</span><span class="sxs-lookup"><span data-stu-id="9fa82-102">-win32resource</span></span>
<span data-ttu-id="9fa82-103">Win32 리소스 파일을 출력 파일에 삽입 합니다.</span><span class="sxs-lookup"><span data-stu-id="9fa82-103">Inserts a Win32 resource file in the output file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9fa82-104">구문</span><span class="sxs-lookup"><span data-stu-id="9fa82-104">Syntax</span></span>  
  
```  
-win32resource:filename  
```  
  
## <a name="arguments"></a><span data-ttu-id="9fa82-105">인수</span><span class="sxs-lookup"><span data-stu-id="9fa82-105">Arguments</span></span>  
 `filename`  
 <span data-ttu-id="9fa82-106">출력 파일에 추가할 리소스 파일의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="9fa82-106">The name of the resource file to add to your output file.</span></span> <span data-ttu-id="9fa82-107">공백을 포함 하는 경우 파일 이름을 따옴표 ("")로 묶습니다.</span><span class="sxs-lookup"><span data-stu-id="9fa82-107">Enclose the file name in quotation marks (" ") if it contains a space.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9fa82-108">설명</span><span class="sxs-lookup"><span data-stu-id="9fa82-108">Remarks</span></span>  
 <span data-ttu-id="9fa82-109">Microsoft Windows 리소스 컴파일러 (RC)를 사용 하 여 Win32 리소스 파일을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9fa82-109">You can create a Win32 resource file with the Microsoft Windows Resource Compiler (RC).</span></span>  
  
 <span data-ttu-id="9fa82-110">Win32 리소스는 **파일 탐색기**에서 응용 프로그램을 식별 하는 데 도움이 되는 버전 또는 비트맵 (아이콘) 정보를 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9fa82-110">A Win32 resource can contain version or bitmap (icon) information that helps identify your application in **File Explorer**.</span></span> <span data-ttu-id="9fa82-111">을 지정 `-win32resource`하지 않으면 컴파일러에서 어셈블리 버전을 기반으로 버전 정보를 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="9fa82-111">If you do not specify `-win32resource`, the compiler generates version information based on the assembly version.</span></span> <span data-ttu-id="9fa82-112">`-win32resource` 및`-win32icon` 옵션은 함께 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="9fa82-112">The `-win32resource` and `-win32icon` options are mutually exclusive.</span></span>  
  
 <span data-ttu-id="9fa82-113">.NET Framework 리소스 파일을 첨부 하려면- [linkresource (Visual Basic)](../../../visual-basic/reference/command-line-compiler/linkresource.md) 을 참조 하 여 .NET Framework 리소스 파일 또는 [-리소스 (Visual Basic)](../../../visual-basic/reference/command-line-compiler/resource.md) 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="9fa82-113">See [-linkresource (Visual Basic)](../../../visual-basic/reference/command-line-compiler/linkresource.md) to reference a .NET Framework resource file, or [-resource (Visual Basic)](../../../visual-basic/reference/command-line-compiler/resource.md) to attach a .NET Framework resource file.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="9fa82-114">이 `-win32resource` 옵션은 Visual Studio 개발 환경에서 사용할 수 없습니다. 명령줄에서 컴파일하는 경우에만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9fa82-114">The `-win32resource` option is not available from within the Visual Studio development environment; it is available only when compiling from the command line.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9fa82-115">예제</span><span class="sxs-lookup"><span data-stu-id="9fa82-115">Example</span></span>  
 <span data-ttu-id="9fa82-116">다음 코드는 Win32 `In.vb` 리소스 파일을 `Rf.res`컴파일하고 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="9fa82-116">The following code compiles `In.vb` and attaches a Win32 resource file, `Rf.res`:</span></span>  
  
```console  
vbc -win32resource:rf.res in.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="9fa82-117">참고자료</span><span class="sxs-lookup"><span data-stu-id="9fa82-117">See also</span></span>

- [<span data-ttu-id="9fa82-118">Visual Basic 명령줄 컴파일러</span><span class="sxs-lookup"><span data-stu-id="9fa82-118">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="9fa82-119">샘플 컴파일 명령줄</span><span class="sxs-lookup"><span data-stu-id="9fa82-119">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
