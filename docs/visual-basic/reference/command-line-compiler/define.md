---
title: -정의 (Visual Basic)
ms.date: 03/10/2018
helpviewer_keywords:
- -d compiler option [Visual Basic]
- /d compiler option [Visual Basic]
- -define compiler option [Visual Basic]
- d compiler option [Visual Basic]
- /define compiler option [Visual Basic]
- define compiler option [Visual Basic]
ms.assetid: f735c57d-1cf9-4f2f-a26f-0de630fd4077
ms.openlocfilehash: d0a483e7a3c9e9863db39e89d655cf172c1e8c81
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61649727"
---
# <a name="-define-visual-basic"></a><span data-ttu-id="71ee5-102">-정의 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="71ee5-102">-define (Visual Basic)</span></span>
<span data-ttu-id="71ee5-103">조건부 컴파일러 상수를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="71ee5-103">Defines conditional compiler constants.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="71ee5-104">구문</span><span class="sxs-lookup"><span data-stu-id="71ee5-104">Syntax</span></span>  
  
```  
-define:["]symbol[=value][,symbol[=value]]["]  
' -or-  
-d:["]symbol[=value][,symbol[=value]]["]  
```  
  
## <a name="arguments"></a><span data-ttu-id="71ee5-105">인수</span><span class="sxs-lookup"><span data-stu-id="71ee5-105">Arguments</span></span>  
  
|<span data-ttu-id="71ee5-106">용어</span><span class="sxs-lookup"><span data-stu-id="71ee5-106">Term</span></span>|<span data-ttu-id="71ee5-107">정의</span><span class="sxs-lookup"><span data-stu-id="71ee5-107">Definition</span></span>|  
|---|---|  
|`symbol`|<span data-ttu-id="71ee5-108">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="71ee5-108">Required.</span></span> <span data-ttu-id="71ee5-109">정의할 기호입니다.</span><span class="sxs-lookup"><span data-stu-id="71ee5-109">The symbol to define.</span></span>|  
|`value`|<span data-ttu-id="71ee5-110">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="71ee5-110">Optional.</span></span> <span data-ttu-id="71ee5-111">`symbol`을 할당할 값입니다.</span><span class="sxs-lookup"><span data-stu-id="71ee5-111">The value to assign `symbol`.</span></span> <span data-ttu-id="71ee5-112">하는 경우 `value` 문자열은 백슬래시/따옴표 시퀀스로 묶어야 (\\") 따옴표 대신 합니다.</span><span class="sxs-lookup"><span data-stu-id="71ee5-112">If `value` is a string, it must be surrounded by backslash/quotation-mark sequences (\\") instead of quotation marks.</span></span> <span data-ttu-id="71ee5-113">값을 지정하지 않으면 True가 지정됩니다.</span><span class="sxs-lookup"><span data-stu-id="71ee5-113">If no value is specified, then it is taken to be True.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="71ee5-114">설명</span><span class="sxs-lookup"><span data-stu-id="71ee5-114">Remarks</span></span>  
 <span data-ttu-id="71ee5-115">`-define` 옵션은 사용과 비슷합니다는 `#Const` 사용 하 여 정의 하는 상수를 제외 하 고 원본 파일에서 전처리기 지시문 `-define` 공용 이며 프로젝트의 모든 파일에 적용 합니다.</span><span class="sxs-lookup"><span data-stu-id="71ee5-115">The `-define` option has an effect similar to using a `#Const` preprocessor directive in your source file, except that constants defined with `-define` are public and apply to all files in the project.</span></span>  
  
 <span data-ttu-id="71ee5-116">이 옵션으로 만든 기호를 `#If`...`Then`...`#Else` 지시문과 함께 사용하면 소스 파일을 조건부 컴파일할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="71ee5-116">You can use symbols created by this option with the `#If`...`Then`...`#Else` directive to compile source files conditionally.</span></span>  
  
 <span data-ttu-id="71ee5-117">`-d`는 약식 `-define`입니다.</span><span class="sxs-lookup"><span data-stu-id="71ee5-117">`-d` is the short form of `-define`.</span></span>  
  
 <span data-ttu-id="71ee5-118">쉼표를 사용해 기호 정의를 구분하여 `-define`으로 여러 기호를 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="71ee5-118">You can define multiple symbols with `-define` by using a comma to separate symbol definitions.</span></span>  
  
|<span data-ttu-id="71ee5-119">Visual Studio 통합 개발 환경에서 /define을 설정하려면</span><span class="sxs-lookup"><span data-stu-id="71ee5-119">To set /define in the Visual Studio integrated development environment</span></span>|  
|---|  
|<span data-ttu-id="71ee5-120">1.  **솔루션 탐색기**에서 프로젝트를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="71ee5-120">1.  Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="71ee5-121">**프로젝트** 메뉴에서 **속성**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="71ee5-121">On the **Project** menu, click **Properties**.</span></span> <br /><span data-ttu-id="71ee5-122">2.  **컴파일** 탭을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="71ee5-122">2.  Click the **Compile** tab.</span></span><br /><span data-ttu-id="71ee5-123">3.  **고급**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="71ee5-123">3.  Click **Advanced**.</span></span><br /><span data-ttu-id="71ee5-124">4.  값을 수정 합니다 **사용자 지정 상수** 상자입니다.</span><span class="sxs-lookup"><span data-stu-id="71ee5-124">4.  Modify the value in the **Custom Constants** box.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="71ee5-125">예제</span><span class="sxs-lookup"><span data-stu-id="71ee5-125">Example</span></span>  
 <span data-ttu-id="71ee5-126">다음 코드는 두 조건부 컴파일러 상수를 정의한 다음 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="71ee5-126">The following code defines and then uses two conditional compiler constants.</span></span>  
  
 [!code-vb[VbVbalrCompiler#45](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCompiler/VB/Class1.vb#45)]  
  
## <a name="see-also"></a><span data-ttu-id="71ee5-127">참고자료</span><span class="sxs-lookup"><span data-stu-id="71ee5-127">See also</span></span>

- [<span data-ttu-id="71ee5-128">Visual Basic 명령줄 컴파일러</span><span class="sxs-lookup"><span data-stu-id="71ee5-128">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="71ee5-129">#If...Then...#Else 지시문</span><span class="sxs-lookup"><span data-stu-id="71ee5-129">#If...Then...#Else Directives</span></span>](../../../visual-basic/language-reference/directives/if-then-else-directives.md)
- [<span data-ttu-id="71ee5-130">#Const 지시문</span><span class="sxs-lookup"><span data-stu-id="71ee5-130">#Const Directive</span></span>](../../../visual-basic/language-reference/directives/const-directive.md)
- [<span data-ttu-id="71ee5-131">샘플 컴파일 명령줄</span><span class="sxs-lookup"><span data-stu-id="71ee5-131">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
