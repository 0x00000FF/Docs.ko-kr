---
title: "/optionstrict | Microsoft 문서"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- /optionstrict
dev_langs:
- VB
helpviewer_keywords:
- -optionstrict compiler option [Visual Basic]
- optionstrict compiler option [Visual Basic]
- /optionstrict compiler option [Visual Basic]
ms.assetid: c7b10086-0fa4-49db-b3c8-4ae0db5957da
caps.latest.revision: 17
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
ms.openlocfilehash: c22445cb53ca4f5621cf7aa69ab840b26f8e08c9
ms.contentlocale: ko-kr
ms.lasthandoff: 04/12/2017

---
# <a name="optionstrict"></a><span data-ttu-id="8742f-102">/optionstrict</span><span class="sxs-lookup"><span data-stu-id="8742f-102">/optionstrict</span></span>
<span data-ttu-id="8742f-103">암시적 형식 변환을 제한 하는 엄격한 형식 의미 체계를 적용 합니다.</span><span class="sxs-lookup"><span data-stu-id="8742f-103">Enforces strict type semantics to restrict implicit type conversions.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8742f-104">구문</span><span class="sxs-lookup"><span data-stu-id="8742f-104">Syntax</span></span>  
  
```  
/optionstrict[+ | -]  
/optionstrict[:custom]  
```  
  
## <a name="arguments"></a><span data-ttu-id="8742f-105">인수</span><span class="sxs-lookup"><span data-stu-id="8742f-105">Arguments</span></span>  
 <span data-ttu-id="8742f-106">`+` &#124; `-`</span><span class="sxs-lookup"><span data-stu-id="8742f-106">`+` &#124; `-`</span></span>  
 <span data-ttu-id="8742f-107">선택적 요소.</span><span class="sxs-lookup"><span data-stu-id="8742f-107">Optional.</span></span> <span data-ttu-id="8742f-108">`/optionstrict+` 옵션 암시적 형식 변환을 제한 합니다.</span><span class="sxs-lookup"><span data-stu-id="8742f-108">The `/optionstrict+` option restricts implicit type conversion.</span></span> <span data-ttu-id="8742f-109">이 옵션의 기본값은 `/optionstrict-`합니다.</span><span class="sxs-lookup"><span data-stu-id="8742f-109">The default for this option is `/optionstrict-`.</span></span> <span data-ttu-id="8742f-110">`/optionstrict+` 옵션은 동일 `/optionstrict`합니다.</span><span class="sxs-lookup"><span data-stu-id="8742f-110">The `/optionstrict+` option is the same as `/optionstrict`.</span></span> <span data-ttu-id="8742f-111">관대 한 형식 의미 체계를 모두 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8742f-111">You can use both for permissive type semantics.</span></span>  
  
 `custom`  
 <span data-ttu-id="8742f-112">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="8742f-112">Required.</span></span> <span data-ttu-id="8742f-113">엄격한 언어 의미 체계를 준수하지 않을 경우 경고합니다.</span><span class="sxs-lookup"><span data-stu-id="8742f-113">Warn when strict language semantics are not respected.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8742f-114">주의</span><span class="sxs-lookup"><span data-stu-id="8742f-114">Remarks</span></span>  
 <span data-ttu-id="8742f-115">때 `/optionstrict+` 사실에 확장 유형 변환만 암시적으로 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8742f-115">When `/optionstrict+` is in effect, only widening type conversions can be made implicitly.</span></span> <span data-ttu-id="8742f-116">암시적 형식 변환의 경우 할당 하는 등 축소는 `Decimal` integer 형식 개체를 object 형식, 오류로 보고 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8742f-116">Implicit narrowing type conversions, such as assigning a `Decimal` type object to an integer type object, are reported as errors.</span></span>  
  
 <span data-ttu-id="8742f-117">축소 하는 암시적 형식 변환에 대 한 경고를 생성 하려면 사용 `/optionstrict:custom`합니다.</span><span class="sxs-lookup"><span data-stu-id="8742f-117">To generate warnings for implicit narrowing type conversions, use `/optionstrict:custom`.</span></span> <span data-ttu-id="8742f-118">사용 하 여 `/nowarn:numberlist` 특정 경고를 무시 하 고 `/warnaserror:numberlist` 특정 경고를 오류로 처리 하도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="8742f-118">Use `/nowarn:numberlist` to ignore particular warnings and `/warnaserror:numberlist` to treat particular warnings as errors.</span></span>  
  
### <a name="to-set-optionstrict-in-the-visual-studio-ide"></a><span data-ttu-id="8742f-119">Visual Studio IDE에서 /optionstrict을 설정 하려면</span><span class="sxs-lookup"><span data-stu-id="8742f-119">To set /optionstrict in the Visual Studio IDE</span></span>  
  
1.  <span data-ttu-id="8742f-120">**솔루션 탐색기**에서 프로젝트를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="8742f-120">Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="8742f-121">에 **프로젝트** 메뉴를 클릭 하 여 **속성입니다.**</span><span class="sxs-lookup"><span data-stu-id="8742f-121">On the **Project** menu, click **Properties.**</span></span> <span data-ttu-id="8742f-122">자세한 내용은 [프로젝트 디자이너 소개](http://msdn.microsoft.com/en-us/898dd854-c98d-430c-ba1b-a913ce3c73d7)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="8742f-122">For more information, see [Introduction to the Project Designer](http://msdn.microsoft.com/en-us/898dd854-c98d-430c-ba1b-a913ce3c73d7).</span></span>  
  
2.  <span data-ttu-id="8742f-123">클릭 하 고 **컴파일** 탭 합니다.</span><span class="sxs-lookup"><span data-stu-id="8742f-123">Click the **Compile** tab.</span></span>  
  
3.  <span data-ttu-id="8742f-124">값을 수정 된 **Option Strict** 상자입니다.</span><span class="sxs-lookup"><span data-stu-id="8742f-124">Modify the value in the **Option Strict** box.</span></span>  
  
### <a name="to-set-optionstrict-programmatically"></a><span data-ttu-id="8742f-125">/Optionstrict을 프로그래밍 방식으로 설정 하려면</span><span class="sxs-lookup"><span data-stu-id="8742f-125">To set /optionstrict programmatically</span></span>  
  
-   <span data-ttu-id="8742f-126">참조 [Option Strict 문](../../../visual-basic/language-reference/statements/option-strict-statement.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="8742f-126">See [Option Strict Statement](../../../visual-basic/language-reference/statements/option-strict-statement.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="8742f-127">예제</span><span class="sxs-lookup"><span data-stu-id="8742f-127">Example</span></span>  
 <span data-ttu-id="8742f-128">다음 코드에서는 `Test.vb` 엄격한 형식 의미 체계를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="8742f-128">The following code compiles `Test.vb` using strict type semantics.</span></span>  
  
```  
vbc /optionstrict+ test.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="8742f-129">참고 항목</span><span class="sxs-lookup"><span data-stu-id="8742f-129">See Also</span></span>  
 <span data-ttu-id="8742f-130">[Visual Basic 명령줄 컴파일러](../../../visual-basic/reference/command-line-compiler/index.md) </span><span class="sxs-lookup"><span data-stu-id="8742f-130">[Visual Basic Command-Line Compiler](../../../visual-basic/reference/command-line-compiler/index.md) </span></span>  
<span data-ttu-id="8742f-131"> [/optioncompare](../../../visual-basic/reference/command-line-compiler/optioncompare.md) </span><span class="sxs-lookup"><span data-stu-id="8742f-131"> [/optioncompare](../../../visual-basic/reference/command-line-compiler/optioncompare.md) </span></span>  
<span data-ttu-id="8742f-132"> [/optionexplicit](../../../visual-basic/reference/command-line-compiler/optionexplicit.md) </span><span class="sxs-lookup"><span data-stu-id="8742f-132"> [/optionexplicit](../../../visual-basic/reference/command-line-compiler/optionexplicit.md) </span></span>  
<span data-ttu-id="8742f-133"> [/optioninfer](../../../visual-basic/reference/command-line-compiler/optioninfer.md) </span><span class="sxs-lookup"><span data-stu-id="8742f-133"> [/optioninfer](../../../visual-basic/reference/command-line-compiler/optioninfer.md) </span></span>  
<span data-ttu-id="8742f-134"> [/nowarn](../../../visual-basic/reference/command-line-compiler/nowarn.md) </span><span class="sxs-lookup"><span data-stu-id="8742f-134"> [/nowarn](../../../visual-basic/reference/command-line-compiler/nowarn.md) </span></span>  
<span data-ttu-id="8742f-135"> [/warnaserror(Visual Basic)](../../../visual-basic/reference/command-line-compiler/warnaserror.md) </span><span class="sxs-lookup"><span data-stu-id="8742f-135"> [/warnaserror (Visual Basic)](../../../visual-basic/reference/command-line-compiler/warnaserror.md) </span></span>  
<span data-ttu-id="8742f-136"> [샘플 컴파일 명령줄](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md) </span><span class="sxs-lookup"><span data-stu-id="8742f-136"> [Sample Compilation Command Lines](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md) </span></span>  
<span data-ttu-id="8742f-137"> [Option Strict 문](../../../visual-basic/language-reference/statements/option-strict-statement.md) </span><span class="sxs-lookup"><span data-stu-id="8742f-137"> [Option Strict Statement](../../../visual-basic/language-reference/statements/option-strict-statement.md) </span></span>  
<span data-ttu-id="8742f-138"> [옵션 대화 상자, 프로젝트, Visual Basic 기본값](https://docs.microsoft.com/visualstudio/ide/reference/visual-basic-defaults-projects-options-dialog-box)</span><span class="sxs-lookup"><span data-stu-id="8742f-138"> [Visual Basic Defaults, Projects, Options Dialog Box](https://docs.microsoft.com/visualstudio/ide/reference/visual-basic-defaults-projects-options-dialog-box)</span></span>
