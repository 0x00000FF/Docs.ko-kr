---
title: "/optioninfer | Microsoft 문서"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- /optioninfer
dev_langs:
- VB
helpviewer_keywords:
- -optioninfer compiler option [Visual Basic]
- /optioninfer compiler option [Visual Basic]
- optioninfer compiler option [Visual Basic]
ms.assetid: f6c09db1-0553-464a-abe3-d4510c61d6ed
caps.latest.revision: 19
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
ms.openlocfilehash: 4bcc35da2a255ca75805c8a918027d2ccb61b154
ms.contentlocale: ko-kr
ms.lasthandoff: 04/12/2017

---
# <a name="optioninfer"></a><span data-ttu-id="e71b0-102">/optioninfer</span><span class="sxs-lookup"><span data-stu-id="e71b0-102">/optioninfer</span></span>
<span data-ttu-id="e71b0-103">변수 선언에서 지역 형식 유추를 사용하도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="e71b0-103">Enables the use of local type inference in variable declarations.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e71b0-104">구문</span><span class="sxs-lookup"><span data-stu-id="e71b0-104">Syntax</span></span>  
  
```  
/optioninfer[+ | -]  
```  
  
## <a name="arguments"></a><span data-ttu-id="e71b0-105">인수</span><span class="sxs-lookup"><span data-stu-id="e71b0-105">Arguments</span></span>  
  
|<span data-ttu-id="e71b0-106">용어</span><span class="sxs-lookup"><span data-stu-id="e71b0-106">Term</span></span>|<span data-ttu-id="e71b0-107">정의</span><span class="sxs-lookup"><span data-stu-id="e71b0-107">Definition</span></span>|  
|---|---|  
|<span data-ttu-id="e71b0-108">`+` &#124; `-`</span><span class="sxs-lookup"><span data-stu-id="e71b0-108">`+` &#124; `-`</span></span>|<span data-ttu-id="e71b0-109">선택적 요소.</span><span class="sxs-lookup"><span data-stu-id="e71b0-109">Optional.</span></span> <span data-ttu-id="e71b0-110">지역 형식 유추를 사용하도록 설정하려면 `/optioninfer+`를 지정하고, 차단하려면 `/optioninfer-`를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="e71b0-110">Specify `/optioninfer+` to enable local type inference, or `/optioninfer-` to block it.</span></span> <span data-ttu-id="e71b0-111">값을 지정하지 않은 `/optioninfer` 옵션은 `/optioninfer+`와 같습니다.</span><span class="sxs-lookup"><span data-stu-id="e71b0-111">The `/optioninfer` option, with no value specified, is the same as `/optioninfer+`.</span></span> <span data-ttu-id="e71b0-112">`/optioninfer` 스위치가 없을 때의 기본값도 `/optioninfer+`입니다.</span><span class="sxs-lookup"><span data-stu-id="e71b0-112">The default value when the `/optioninfer` switch is not present is also `/optioninfer+`.</span></span> <span data-ttu-id="e71b0-113">기본값은 vbc.rsp 지시 파일에서 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="e71b0-113">The default value is set in the Vbc.rsp response file.</span></span>|  
  
> [!NOTE]
>  <span data-ttu-id="e71b0-114">`/noconfig` 옵션을 사용하여 vbc.rsp에 지정된 값 대신 컴파일러의 내부 기본값을 유지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e71b0-114">You can use the `/noconfig` option to retain the compiler's internal defaults instead of those specified in vbc.rsp.</span></span> <span data-ttu-id="e71b0-115">이 옵션에 대한 컴파일러 기본값은 `/optioninfer-`입니다.</span><span class="sxs-lookup"><span data-stu-id="e71b0-115">The compiler default for this option is `/optioninfer-`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e71b0-116">설명</span><span class="sxs-lookup"><span data-stu-id="e71b0-116">Remarks</span></span>  
 <span data-ttu-id="e71b0-117">소스 코드 파일을 포함 하는 경우는 [Option Infer 문](../../../visual-basic/language-reference/statements/option-infer-statement.md), 문은 재정의 `/optioninfer` 명령줄 컴파일러 설정을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="e71b0-117">If the source code file contains an [Option Infer Statement](../../../visual-basic/language-reference/statements/option-infer-statement.md), the statement overrides the `/optioninfer` command-line compiler setting.</span></span>  
  
### <a name="to-set-optioninfer-in-the-visual-studio-ide"></a><span data-ttu-id="e71b0-118">Visual Studio IDE에서 /optioninfer를 설정하려면</span><span class="sxs-lookup"><span data-stu-id="e71b0-118">To set /optioninfer in the Visual Studio IDE</span></span>  
  
1.  <span data-ttu-id="e71b0-119">프로젝트를 선택 **솔루션 탐색기**합니다.</span><span class="sxs-lookup"><span data-stu-id="e71b0-119">Select a project in **Solution Explorer**.</span></span> <span data-ttu-id="e71b0-120">에 **프로젝트** 메뉴를 클릭 하 여 **속성**합니다.</span><span class="sxs-lookup"><span data-stu-id="e71b0-120">On the **Project** menu, click **Properties**.</span></span> <span data-ttu-id="e71b0-121">자세한 내용은 참조 [NIB: 프로젝트 디자이너를 사용 하 여 프로젝트 속성 관리](http://msdn.microsoft.com/en-us/983f3c18-832f-4666-afec-74b716ff3e0e)합니다.</span><span class="sxs-lookup"><span data-stu-id="e71b0-121">For more information, see [NIB: Managing Project Properties with the Project Designer](http://msdn.microsoft.com/en-us/983f3c18-832f-4666-afec-74b716ff3e0e).</span></span>  
  
2.  <span data-ttu-id="e71b0-122">에 **컴파일** 탭에서 값을 수정 된 **Option infer** 상자입니다.</span><span class="sxs-lookup"><span data-stu-id="e71b0-122">On the **Compile** tab, modify the value in the **Option infer** box.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e71b0-123">예제</span><span class="sxs-lookup"><span data-stu-id="e71b0-123">Example</span></span>  
 <span data-ttu-id="e71b0-124">다음 코드에서는 지역 형식 유추를 사용하도록 설정한 상태로 `test.vb`를 컴파일합니다.</span><span class="sxs-lookup"><span data-stu-id="e71b0-124">The following code compiles `test.vb` with local type inference enabled.</span></span>  
  
```  
vbc /optioninfer+ test.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="e71b0-125">참고 항목</span><span class="sxs-lookup"><span data-stu-id="e71b0-125">See Also</span></span>  
 <span data-ttu-id="e71b0-126">[Visual Basic 명령줄 컴파일러](../../../visual-basic/reference/command-line-compiler/index.md) </span><span class="sxs-lookup"><span data-stu-id="e71b0-126">[Visual Basic Command-Line Compiler](../../../visual-basic/reference/command-line-compiler/index.md) </span></span>  
<span data-ttu-id="e71b0-127"> [/optioncompare](../../../visual-basic/reference/command-line-compiler/optioncompare.md) </span><span class="sxs-lookup"><span data-stu-id="e71b0-127"> [/optioncompare](../../../visual-basic/reference/command-line-compiler/optioncompare.md) </span></span>  
<span data-ttu-id="e71b0-128"> [/optionexplicit](../../../visual-basic/reference/command-line-compiler/optionexplicit.md) </span><span class="sxs-lookup"><span data-stu-id="e71b0-128"> [/optionexplicit](../../../visual-basic/reference/command-line-compiler/optionexplicit.md) </span></span>  
<span data-ttu-id="e71b0-129"> [/optionstrict](../../../visual-basic/reference/command-line-compiler/optionstrict.md) </span><span class="sxs-lookup"><span data-stu-id="e71b0-129"> [/optionstrict](../../../visual-basic/reference/command-line-compiler/optionstrict.md) </span></span>  
<span data-ttu-id="e71b0-130"> [샘플 컴파일 명령줄](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md) </span><span class="sxs-lookup"><span data-stu-id="e71b0-130"> [Sample Compilation Command Lines](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md) </span></span>  
<span data-ttu-id="e71b0-131"> [Option Infer 문](../../../visual-basic/language-reference/statements/option-infer-statement.md) </span><span class="sxs-lookup"><span data-stu-id="e71b0-131"> [Option Infer Statement](../../../visual-basic/language-reference/statements/option-infer-statement.md) </span></span>  
<span data-ttu-id="e71b0-132"> [지역 형식 유추](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md) </span><span class="sxs-lookup"><span data-stu-id="e71b0-132"> [Local Type Inference](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md) </span></span>  
<span data-ttu-id="e71b0-133"> [Visual Basic 프로젝트의 경우 옵션 대화 상자, 기본값](https://docs.microsoft.com/visualstudio/ide/reference/visual-basic-defaults-projects-options-dialog-box) </span><span class="sxs-lookup"><span data-stu-id="e71b0-133"> [Visual Basic Defaults, Projects, Options Dialog Box](https://docs.microsoft.com/visualstudio/ide/reference/visual-basic-defaults-projects-options-dialog-box) </span></span>  
<span data-ttu-id="e71b0-134"> [프로젝트 디자이너, 컴파일 페이지(Visual Basic)](https://docs.microsoft.com/visualstudio/ide/reference/compile-page-project-designer-visual-basic) </span><span class="sxs-lookup"><span data-stu-id="e71b0-134"> [Compile Page, Project Designer (Visual Basic)](https://docs.microsoft.com/visualstudio/ide/reference/compile-page-project-designer-visual-basic) </span></span>  
<span data-ttu-id="e71b0-135"> [/noconfig](../../../visual-basic/reference/command-line-compiler/noconfig.md) </span><span class="sxs-lookup"><span data-stu-id="e71b0-135"> [/noconfig](../../../visual-basic/reference/command-line-compiler/noconfig.md) </span></span>  
<span data-ttu-id="e71b0-136"> [명령줄에서 빌드](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md)</span><span class="sxs-lookup"><span data-stu-id="e71b0-136"> [Building from the Command Line](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md)</span></span>
