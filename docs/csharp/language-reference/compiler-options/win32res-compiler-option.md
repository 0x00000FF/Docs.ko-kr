---
title: -win32res(C# 컴파일러 옵션)
ms.date: 07/20/2015
f1_keywords:
- /win32res
helpviewer_keywords:
- win32res compiler option
- /win32res compiler option [C#]
- -win32res compiler option [C#]
- win32res compiler option [C#]
ms.assetid: 3c33f750-6948-4c7e-a27e-bef98f77255b
ms.openlocfilehash: 3f7f5f323006024c393cb066284712ed60836372
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33216767"
---
# <a name="-win32res-c-compiler-options"></a><span data-ttu-id="c76a2-102">-win32res(C# 컴파일러 옵션)</span><span class="sxs-lookup"><span data-stu-id="c76a2-102">-win32res (C# Compiler Options)</span></span>
<span data-ttu-id="c76a2-103">**-win32res** 옵션은 출력 파일에 Win32 리소스를 삽입합니다.</span><span class="sxs-lookup"><span data-stu-id="c76a2-103">The **-win32res** option inserts a Win32 resource in the output file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c76a2-104">구문</span><span class="sxs-lookup"><span data-stu-id="c76a2-104">Syntax</span></span>  
  
```console  
-win32res:filename  
```  
  
## <a name="arguments"></a><span data-ttu-id="c76a2-105">인수</span><span class="sxs-lookup"><span data-stu-id="c76a2-105">Arguments</span></span>  
 `filename`  
 <span data-ttu-id="c76a2-106">출력 파일에 추가하려는 리소스 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="c76a2-106">The resource file that you want to add to your output file.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c76a2-107">설명</span><span class="sxs-lookup"><span data-stu-id="c76a2-107">Remarks</span></span>  
 <span data-ttu-id="c76a2-108">Win32 리소스 파일은 [리소스 컴파일러](../../language-reference/compiler-options/resource-compiler-option.md)로 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c76a2-108">A Win32 resource file can be created with the [Resource Compiler](../../language-reference/compiler-options/resource-compiler-option.md).</span></span> <span data-ttu-id="c76a2-109">리소스 컴파일러는 Visual C++ 프로그램을 컴파일할 때 실행되며 .rc 파일에서 .res 파일이 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="c76a2-109">The Resource Compiler is invoked when you compile a Visual C++ program; a .res file is created from the .rc file.</span></span>  
  
 <span data-ttu-id="c76a2-110">Win32 리소스는 파일 탐색기에서 응용 프로그램을 식별하는 데 도움이 되는 버전 정보나 비트맵 (아이콘) 정보를 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c76a2-110">A Win32 resource can contain version or bitmap (icon) information that would help identify your application in the File Explorer.</span></span> <span data-ttu-id="c76a2-111">**-win32res**를 지정하지 않으면 컴파일러에서 어셈블리 버전을 기반으로 하여 버전 정보를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="c76a2-111">If you do not specify **-win32res**, the compiler will generate version information based on the assembly version.</span></span>  
  
 <span data-ttu-id="c76a2-112">.NET Framework 리소스 파일을 참조하려면 [-linkresource](../../../csharp/language-reference/compiler-options/linkresource-compiler-option.md)를, 첨부하려면 [-resource](../../../csharp/language-reference/compiler-options/resource-compiler-option.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c76a2-112">See [-linkresource](../../../csharp/language-reference/compiler-options/linkresource-compiler-option.md) (to reference) or [-resource](../../../csharp/language-reference/compiler-options/resource-compiler-option.md) (to attach) a .NET Framework resource file.</span></span>  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a><span data-ttu-id="c76a2-113">Visual Studio 개발 환경에서 이 컴파일러 옵션을 설정하려면</span><span class="sxs-lookup"><span data-stu-id="c76a2-113">To set this compiler option in the Visual Studio development environment</span></span>  
  
1.  <span data-ttu-id="c76a2-114">프로젝트 **속성** 페이지를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="c76a2-114">Open the project's **Properties** page.</span></span>  
  
2.  <span data-ttu-id="c76a2-115">**응용 프로그램** 속성 페이지를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="c76a2-115">Click the **Application** property page.</span></span>  
  
3.  <span data-ttu-id="c76a2-116">**리소스 파일** 단추를 클릭한 다음 콤보 상자를 사용하여 파일을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="c76a2-116">Click on the **Resource File** button and choose a file by using the combo box.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c76a2-117">예</span><span class="sxs-lookup"><span data-stu-id="c76a2-117">Example</span></span>  
 <span data-ttu-id="c76a2-118">`in.cs`를 컴파일하고 Win32 리소스 파일 `rf.res`를 첨부하여 `in.exe`를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="c76a2-118">Compile `in.cs` and attach a Win32 resource file `rf.res` to produce `in.exe`:</span></span>  
  
```console  
csc -win32res:rf.res in.cs  
```  
  
## <a name="see-also"></a><span data-ttu-id="c76a2-119">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c76a2-119">See Also</span></span>  
 [<span data-ttu-id="c76a2-120">C# 컴파일러 옵션</span><span class="sxs-lookup"><span data-stu-id="c76a2-120">C# Compiler Options</span></span>](../../../csharp/language-reference/compiler-options/index.md)  
 [<span data-ttu-id="c76a2-121">프로젝트 및 솔루션 속성 관리</span><span class="sxs-lookup"><span data-stu-id="c76a2-121">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)
