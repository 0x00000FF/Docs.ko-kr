---
title: -baseaddress(C# 컴파일러 옵션)
ms.date: 07/20/2015
f1_keywords:
- /dllbase
helpviewer_keywords:
- baseaddress compiler option [C#]
- -baseaddress compiler option [C#]
- /baseaddress compiler option [C#]
ms.assetid: ce13c965-dfe4-4433-94f5-63b476e3a608
ms.openlocfilehash: aa76e3d1d30e394f28b5112e45fc72229e9a78fc
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59295785"
---
# <a name="-baseaddress-c-compiler-options"></a><span data-ttu-id="c7856-102">-baseaddress(C# 컴파일러 옵션)</span><span class="sxs-lookup"><span data-stu-id="c7856-102">-baseaddress (C# Compiler Options)</span></span>
<span data-ttu-id="c7856-103">**-baseaddress** 옵션을 사용하면 DLL을 로드할 기본 기준 주소를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c7856-103">The **-baseaddress** option lets you specify the preferred base address at which to load a DLL.</span></span> <span data-ttu-id="c7856-104">이 옵션을 사용하는 시기와 이유에 대한 자세한 내용은 [Larry Osterman's WebLog](https://blogs.msdn.microsoft.com/larryosterman/2004/07/06/why-should-i-even-bother-to-use-dlls-in-my-system/)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c7856-104">For more information about when and why to use this option, see [Larry Osterman's WebLog](https://blogs.msdn.microsoft.com/larryosterman/2004/07/06/why-should-i-even-bother-to-use-dlls-in-my-system/).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c7856-105">구문</span><span class="sxs-lookup"><span data-stu-id="c7856-105">Syntax</span></span>  
  
```console  
-baseaddress:address  
```  
  
## <a name="arguments"></a><span data-ttu-id="c7856-106">인수</span><span class="sxs-lookup"><span data-stu-id="c7856-106">Arguments</span></span>  
 `address`  
 <span data-ttu-id="c7856-107">DLL의 기준 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="c7856-107">The base address for the DLL.</span></span> <span data-ttu-id="c7856-108">이 주소는 10진수, 16진수 또는 8진수 숫자로 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c7856-108">This address can be specified as a decimal, hexadecimal, or octal number.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c7856-109">주의</span><span class="sxs-lookup"><span data-stu-id="c7856-109">Remarks</span></span>  
 <span data-ttu-id="c7856-110">DLL에 대한 기본 기준 주소는 .NET Framework 공용 언어 런타임에 의해 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="c7856-110">The default base address for a DLL is set by the .NET Framework common language runtime.</span></span>  
  
 <span data-ttu-id="c7856-111">이 주소의 하위 단어는 반올림됩니다.</span><span class="sxs-lookup"><span data-stu-id="c7856-111">Be aware that the lower-order word in this address will be rounded.</span></span> <span data-ttu-id="c7856-112">예를 들어 0x11110001을 지정하면 0x11110000으로 반올림됩니다.</span><span class="sxs-lookup"><span data-stu-id="c7856-112">For example, if you specify 0x11110001, it will be rounded to 0x11110000.</span></span>  
  
 <span data-ttu-id="c7856-113">DLL에 대한 서명 프로세스를 완료하려면 SN.EXE에 -R 옵션을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="c7856-113">To complete the signing process for a DLL, use SN.EXE with the -R option.</span></span>  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a><span data-ttu-id="c7856-114">Visual Studio 개발 환경에서 이 컴파일러 옵션을 설정하려면</span><span class="sxs-lookup"><span data-stu-id="c7856-114">To set this compiler option in the Visual Studio development environment</span></span>  
  
1. <span data-ttu-id="c7856-115">프로젝트 **속성** 페이지를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="c7856-115">Open the project's **Properties** page.</span></span>  
  
2. <span data-ttu-id="c7856-116">**빌드** 속성 페이지를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="c7856-116">Click the **Build** property page.</span></span>  
  
3. <span data-ttu-id="c7856-117">**고급** 단추를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="c7856-117">Click the **Advanced** button.</span></span>  
  
4. <span data-ttu-id="c7856-118">**DLL 기준 주소** 속성을 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="c7856-118">Modify the **DLL Base Address** property.</span></span>  
  
     <span data-ttu-id="c7856-119">프로그래밍 방식으로 이 컴파일러 옵션을 설정하려면 <xref:VSLangProj80.CSharpProjectConfigurationProperties3.BaseAddress%2A>를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c7856-119">To set this compiler option programmatically, see <xref:VSLangProj80.CSharpProjectConfigurationProperties3.BaseAddress%2A>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c7856-120">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c7856-120">See also</span></span>

- <xref:System.Diagnostics.ProcessModule.BaseAddress%2A?displayProperty=nameWithType>
- [<span data-ttu-id="c7856-121">C# 컴파일러 옵션</span><span class="sxs-lookup"><span data-stu-id="c7856-121">C# Compiler Options</span></span>](../../../csharp/language-reference/compiler-options/index.md)
- [<span data-ttu-id="c7856-122">프로젝트 및 솔루션 속성 관리</span><span class="sxs-lookup"><span data-stu-id="c7856-122">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)
