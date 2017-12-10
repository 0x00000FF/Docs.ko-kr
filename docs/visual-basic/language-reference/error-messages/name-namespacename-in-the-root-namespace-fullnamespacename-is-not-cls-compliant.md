---
title: "이름 &lt;namespacename&gt; 루트 네임 스페이스에 &lt;fullnamespacename&gt; CLS 규격이 아닙니다"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc40039
- bc40039
helpviewer_keywords: BC40039
ms.assetid: c5bd5914-ae71-416a-8bed-f76f644f78be
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 36de8b6a27c47e9e7192aed10e6b561bb0c07acc
ms.sourcegitcommit: 685143b62385500f59bc36274b8adb191f573a16
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/09/2017
---
# <a name="name-ltnamespacenamegt-in-the-root-namespace-ltfullnamespacenamegt-is-not-cls-compliant"></a><span data-ttu-id="c7860-102">이름 &lt;namespacename&gt; 루트 네임 스페이스에 &lt;fullnamespacename&gt; CLS 규격이 아닙니다</span><span class="sxs-lookup"><span data-stu-id="c7860-102">Name &lt;namespacename&gt; in the root namespace &lt;fullnamespacename&gt; is not CLS-compliant</span></span>
<span data-ttu-id="c7860-103">로 어셈블리 표시 되어 `<CLSCompliant(True)>`, 루트 네임 스페이스 이름의 요소가 밑줄로 시작 하지만 (`_`).</span><span class="sxs-lookup"><span data-stu-id="c7860-103">An assembly is marked as `<CLSCompliant(True)>`, but an element of the root namespace name begins with an underscore (`_`).</span></span>  
  
 <span data-ttu-id="c7860-104">프로그래밍 요소를 준수 해야 하지만 하나 이상의 밑줄을 포함할 수 있습니다는 [언어 독립성 및 언어 독립적 구성 요소](../../../../docs/standard/language-independence-and-language-independent-components.md) (CLS) 시작 하지 않아야 밑줄로 합니다.</span><span class="sxs-lookup"><span data-stu-id="c7860-104">A programming element can contain one or more underscores, but to be compliant with the [Language Independence and Language-Independent Components](../../../../docs/standard/language-independence-and-language-independent-components.md) (CLS), it must not begin with an underscore.</span></span> <span data-ttu-id="c7860-105">참조 [선언 된 요소 이름](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="c7860-105">See [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).</span></span>  
  
 <span data-ttu-id="c7860-106"><xref:System.CLSCompliantAttribute> 를 프로그래밍 요소에 적용하는 경우 특성의 `isCompliant` 매개 변수를 `True` 또는 `False` 로 설정하여 준수 여부를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="c7860-106">When you apply the <xref:System.CLSCompliantAttribute> to a programming element, you set the attribute's `isCompliant` parameter to either `True` or `False` to indicate compliance or noncompliance.</span></span> <span data-ttu-id="c7860-107">이 매개 변수에는 기본값이 없으며 값을 제공해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c7860-107">There is no default for this parameter, and you must supply a value.</span></span>  
  
 <span data-ttu-id="c7860-108">요소에 <xref:System.CLSCompliantAttribute> 를 적용하지 않으면 비규격인 것으로 간주됩니다.</span><span class="sxs-lookup"><span data-stu-id="c7860-108">If you do not apply the <xref:System.CLSCompliantAttribute> to an element, it is considered to be noncompliant.</span></span>  
  
 <span data-ttu-id="c7860-109">이 메시지는 기본적으로 경고입니다.</span><span class="sxs-lookup"><span data-stu-id="c7860-109">By default, this message is a warning.</span></span> <span data-ttu-id="c7860-110">경고를 숨기거나 오류로 처리하는 방법에 대한 자세한 내용은 [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c7860-110">For information on hiding warnings or treating warnings as errors, see [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span></span>  
  
 <span data-ttu-id="c7860-111">**오류 ID:** BC40039</span><span class="sxs-lookup"><span data-stu-id="c7860-111">**Error ID:** BC40039</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="c7860-112">이 오류를 해결하려면</span><span class="sxs-lookup"><span data-stu-id="c7860-112">To correct this error</span></span>  
  
-   <span data-ttu-id="c7860-113">CLS 규격이 필요 하면 밑줄로 시작 하는 해당 요소 중 루트 네임 스페이스 이름을 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="c7860-113">If you require CLS compliance, change the root namespace name so that none of its elements begins with an underscore.</span></span>  
  
-   <span data-ttu-id="c7860-114">네임 스페이스 이름은 변경 되지 않고 유지, 필요한 경우 제거 합니다는 <xref:System.CLSCompliantAttribute> 어셈블리에서로 표시 하거나 `<CLSCompliant(False)>`합니다.</span><span class="sxs-lookup"><span data-stu-id="c7860-114">If you require that the namespace name remain unchanged, then remove the <xref:System.CLSCompliantAttribute> from the assembly or mark it as `<CLSCompliant(False)>`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c7860-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c7860-115">See Also</span></span>  
 [<span data-ttu-id="c7860-116">Namespace 문</span><span class="sxs-lookup"><span data-stu-id="c7860-116">Namespace Statement</span></span>](../../../visual-basic/language-reference/statements/namespace-statement.md)  
 [<span data-ttu-id="c7860-117">Visual Basic의 네임 스페이스</span><span class="sxs-lookup"><span data-stu-id="c7860-117">Namespaces in Visual Basic</span></span>](../../../visual-basic/programming-guide/program-structure/namespaces.md)  
 [<span data-ttu-id="c7860-118">/rootnamespace</span><span class="sxs-lookup"><span data-stu-id="c7860-118">/rootnamespace</span></span>](../../../visual-basic/reference/command-line-compiler/rootnamespace.md)  
 [<span data-ttu-id="c7860-119">프로젝트 디자이너, 응용 프로그램 페이지(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c7860-119">Application Page, Project Designer (Visual Basic)</span></span>](/visualstudio/ide/reference/application-page-project-designer-visual-basic)  
 [<span data-ttu-id="c7860-120">선언 요소 이름</span><span class="sxs-lookup"><span data-stu-id="c7860-120">Declared Element Names</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md)  
 [<span data-ttu-id="c7860-121">Visual Basic 명명 규칙</span><span class="sxs-lookup"><span data-stu-id="c7860-121">Visual Basic Naming Conventions</span></span>](../../../visual-basic/programming-guide/program-structure/naming-conventions.md)  
 [<span data-ttu-id="c7860-122">\<통해 PAVE > CLS 규격 코드 작성</span><span class="sxs-lookup"><span data-stu-id="c7860-122">\<PAVE OVER> Writing CLS-Compliant Code</span></span>](http://msdn.microsoft.com/en-us/4c705105-69a2-4e5e-b24e-0633bc32c7f3)
