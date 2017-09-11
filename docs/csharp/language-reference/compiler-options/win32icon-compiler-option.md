---
title: "-win32icon(C# 컴파일러 옵션)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- /win32icon
dev_langs:
- CSharp
helpviewer_keywords:
- win32icon compiler option [C#]
- /win32icon compiler option [C#]
- -win32icon compiler option [C#]
ms.assetid: 756d9b6d-ab07-41b7-ba58-5bd88f711138
caps.latest.revision: 18
author: BillWagner
ms.author: wiwagn
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
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: af5b9c3a44163167d932d378cbac4976e07eacbf
ms.contentlocale: ko-kr
ms.lasthandoff: 07/28/2017

---
# <a name="win32icon-c-compiler-options"></a><span data-ttu-id="dda95-102">/win32icon(C# 컴파일러 옵션)</span><span class="sxs-lookup"><span data-stu-id="dda95-102">/win32icon (C# Compiler Options)</span></span>
<span data-ttu-id="dda95-103">**/win32icon** 옵션은 .ico 파일을 출력 파일에 삽입하여 파일 탐색기에서 출력 파일을 원하는 모양으로 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="dda95-103">The **/win32icon** option inserts an .ico file in the output file, which gives the output file the desired appearance in the File Explorer.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dda95-104">구문</span><span class="sxs-lookup"><span data-stu-id="dda95-104">Syntax</span></span>  
  
```console  
/win32icon:filename  
```  
  
## <a name="arguments"></a><span data-ttu-id="dda95-105">인수</span><span class="sxs-lookup"><span data-stu-id="dda95-105">Arguments</span></span>  
 `filename`  
 <span data-ttu-id="dda95-106">출력 파일에 추가하려는 .ico 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="dda95-106">The .ico file that you want to add to your output file.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="dda95-107">설명</span><span class="sxs-lookup"><span data-stu-id="dda95-107">Remarks</span></span>  
 <span data-ttu-id="dda95-108">.ico 파일은 [리소스 컴파일러](http://go.microsoft.com/fwlink/?LinkId=148370)로 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dda95-108">An .ico file can be created with the [Resource Compiler](http://go.microsoft.com/fwlink/?LinkId=148370).</span></span> <span data-ttu-id="dda95-109">리소스 컴파일러는 Visual C++ 프로그램을 컴파일할 때 실행되며 .rc 파일에서 .iso 파일이 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="dda95-109">The Resource Compiler is invoked when you compile a Visual C++ program; an .ico file is created from the .rc file.</span></span>  
  
 <span data-ttu-id="dda95-110">.NET Framework 리소스 파일을 참조하려면 [/linkresource](../../../csharp/language-reference/compiler-options/linkresource-compiler-option.md)를, 첨부하려면 [/resource](../../../csharp/language-reference/compiler-options/resource-compiler-option.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="dda95-110">See [/linkresource](../../../csharp/language-reference/compiler-options/linkresource-compiler-option.md) (to reference) or [/resource](../../../csharp/language-reference/compiler-options/resource-compiler-option.md) (to attach) a .NET Framework resource file.</span></span> <span data-ttu-id="dda95-111">.res 파일을 가져오려면 [/win32res](../../../csharp/language-reference/compiler-options/win32res-compiler-option.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="dda95-111">See [/win32res](../../../csharp/language-reference/compiler-options/win32res-compiler-option.md) to import a .res file.</span></span>  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a><span data-ttu-id="dda95-112">Visual Studio 개발 환경에서 이 컴파일러 옵션을 설정하려면</span><span class="sxs-lookup"><span data-stu-id="dda95-112">To set this compiler option in the Visual Studio development environment</span></span>  
  
1.  <span data-ttu-id="dda95-113">프로젝트 **속성** 페이지를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="dda95-113">Open the project's **Properties** pages.</span></span>  
  
2.  <span data-ttu-id="dda95-114">**응용 프로그램** 속성 페이지를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="dda95-114">Click the **Application** property page.</span></span>  
  
3.  <span data-ttu-id="dda95-115">**응용 프로그램 아이콘** 속성을 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="dda95-115">Modify the **Application icon** property.</span></span>  
  
 <span data-ttu-id="dda95-116">이 컴파일러 옵션을 프로그래밍 방식으로 설정하는 방법에 대한 자세한 내용은 <xref:VSLangProj80.ProjectProperties3.ApplicationIcon%2A>을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="dda95-116">For information on how to set this compiler option programmatically, see <xref:VSLangProj80.ProjectProperties3.ApplicationIcon%2A>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="dda95-117">예제</span><span class="sxs-lookup"><span data-stu-id="dda95-117">Example</span></span>  
 <span data-ttu-id="dda95-118">`in.cs`를 컴파일하고 .ico 파일 `rf.ico`를 첨부하여 `in.exe`를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="dda95-118">Compile `in.cs` and attach an .ico file `rf.ico` to produce `in.exe`:</span></span>  
  
```console  
csc /win32icon:rf.ico in.cs  
```  
  
## <a name="see-also"></a><span data-ttu-id="dda95-119">참고 항목</span><span class="sxs-lookup"><span data-stu-id="dda95-119">See Also</span></span>  
 <span data-ttu-id="dda95-120">[C# 컴파일러 옵션](../../../csharp/language-reference/compiler-options/index.md) </span><span class="sxs-lookup"><span data-stu-id="dda95-120">[C# Compiler Options](../../../csharp/language-reference/compiler-options/index.md) </span></span>  
 [<span data-ttu-id="dda95-121">프로젝트 및 솔루션 속성 관리</span><span class="sxs-lookup"><span data-stu-id="dda95-121">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)

