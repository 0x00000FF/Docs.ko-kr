---
title: 문서 주석에 대한 권장 XML 태그(Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.XmlDocComment
helpviewer_keywords:
- tags, XML
- XML comments, recommended tags [Visual Basic]
- comments, recommended XML tags
ms.assetid: 294e0736-ff1e-498e-af83-6db71ed41a72
ms.openlocfilehash: e59ee25b22c51e47dc83233af33099e6c55de87b
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/02/2019
ms.locfileid: "58814952"
---
# <a name="recommended-xml-tags-for-documentation-comments-visual-basic"></a><span data-ttu-id="7ec44-102">문서 주석에 대한 권장 XML 태그(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="7ec44-102">Recommended XML Tags for Documentation Comments (Visual Basic)</span></span>
<span data-ttu-id="7ec44-103">Visual Basic 컴파일러는 XML 파일에 코드에서 문서 주석을 처리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7ec44-103">The Visual Basic compiler can process documentation comments in your code to an XML file.</span></span> <span data-ttu-id="7ec44-104">설명서에 XML 파일을 처리 하는 데 추가 도구를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7ec44-104">You can use additional tools to process the XML file into documentation.</span></span>  
  
 <span data-ttu-id="7ec44-105">XML 주석 형식 등의 코드 구문에는 사용할 수 및 멤버를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="7ec44-105">XML comments are allowed on code constructs such as types and type members.</span></span> <span data-ttu-id="7ec44-106">부분 형식에 대 한 형식의 파트가 하나만 포함할 수 XML 주석, 있지만 해당 멤버의 주석 처리에 대 한 제한은 없습니다.</span><span class="sxs-lookup"><span data-stu-id="7ec44-106">For partial types, only one part of the type can have XML comments, although there is no restriction on commenting its members.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="7ec44-107">네임 스페이스에 문서 주석은 적용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="7ec44-107">Documentation comments cannot be applied to namespaces.</span></span> <span data-ttu-id="7ec44-108">이유는 하나의 네임 스페이스에는 여러 어셈블리에 걸쳐 있을 수 있으며 일부 어셈블리를 동시에 로드할 필요가입니다.</span><span class="sxs-lookup"><span data-stu-id="7ec44-108">The reason is that one namespace can span several assemblies, and not all assemblies have to be loaded at the same time.</span></span>  
  
 <span data-ttu-id="7ec44-109">컴파일러는 유효한 XML 태그를 모두 처리 합니다.</span><span class="sxs-lookup"><span data-stu-id="7ec44-109">The compiler processes any tag that is valid XML.</span></span> <span data-ttu-id="7ec44-110">다음 태그가 사용자 설명서에서 자주 사용 되는 기능을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="7ec44-110">The following tags provide commonly used functionality in user documentation.</span></span>  
  
||||  
|---|---|---|  
|[<span data-ttu-id="7ec44-111">\<c></span><span class="sxs-lookup"><span data-stu-id="7ec44-111">\<c></span></span>](../../../visual-basic/language-reference/xmldoc/c.md)|[<span data-ttu-id="7ec44-112">\<code></span><span class="sxs-lookup"><span data-stu-id="7ec44-112">\<code></span></span>](../../../visual-basic/language-reference/xmldoc/code.md)|[<span data-ttu-id="7ec44-113">\<example></span><span class="sxs-lookup"><span data-stu-id="7ec44-113">\<example></span></span>](../../../visual-basic/language-reference/xmldoc/example.md)|  
|<span data-ttu-id="7ec44-114">[\<exception>](../../../visual-basic/language-reference/xmldoc/exception.md) <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="7ec44-114">[\<exception>](../../../visual-basic/language-reference/xmldoc/exception.md) <sup>1</sup></span></span>|<span data-ttu-id="7ec44-115">[\<include>](../../../visual-basic/language-reference/xmldoc/include.md) <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="7ec44-115">[\<include>](../../../visual-basic/language-reference/xmldoc/include.md) <sup>1</sup></span></span>|[<span data-ttu-id="7ec44-116">\<list></span><span class="sxs-lookup"><span data-stu-id="7ec44-116">\<list></span></span>](../../../visual-basic/language-reference/xmldoc/list.md)|  
|[<span data-ttu-id="7ec44-117">\<para></span><span class="sxs-lookup"><span data-stu-id="7ec44-117">\<para></span></span>](../../../visual-basic/language-reference/xmldoc/para.md)|<span data-ttu-id="7ec44-118">[\<param>](../../../visual-basic/language-reference/xmldoc/param.md) <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="7ec44-118">[\<param>](../../../visual-basic/language-reference/xmldoc/param.md) <sup>1</sup></span></span>|[<span data-ttu-id="7ec44-119">\<paramref></span><span class="sxs-lookup"><span data-stu-id="7ec44-119">\<paramref></span></span>](../../../visual-basic/language-reference/xmldoc/paramref.md)|  
|<span data-ttu-id="7ec44-120">[\<permission>](../../../visual-basic/language-reference/xmldoc/permission.md) <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="7ec44-120">[\<permission>](../../../visual-basic/language-reference/xmldoc/permission.md) <sup>1</sup></span></span>|[<span data-ttu-id="7ec44-121">\<remarks></span><span class="sxs-lookup"><span data-stu-id="7ec44-121">\<remarks></span></span>](../../../visual-basic/language-reference/xmldoc/remarks.md)|[<span data-ttu-id="7ec44-122">\<returns></span><span class="sxs-lookup"><span data-stu-id="7ec44-122">\<returns></span></span>](../../../visual-basic/language-reference/xmldoc/returns.md)|  
|<span data-ttu-id="7ec44-123">[\<see>](../../../visual-basic/language-reference/xmldoc/see.md) <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="7ec44-123">[\<see>](../../../visual-basic/language-reference/xmldoc/see.md) <sup>1</sup></span></span>|<span data-ttu-id="7ec44-124">[\<seealso>](../../../visual-basic/language-reference/xmldoc/seealso.md) <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="7ec44-124">[\<seealso>](../../../visual-basic/language-reference/xmldoc/seealso.md) <sup>1</sup></span></span>|[<span data-ttu-id="7ec44-125">\<summary></span><span class="sxs-lookup"><span data-stu-id="7ec44-125">\<summary></span></span>](../../../visual-basic/language-reference/xmldoc/summary.md)|  
|<span data-ttu-id="7ec44-126">[\<typeparam>](../../../visual-basic/language-reference/xmldoc/typeparam.md) <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="7ec44-126">[\<typeparam>](../../../visual-basic/language-reference/xmldoc/typeparam.md) <sup>1</sup></span></span>|[<span data-ttu-id="7ec44-127">\<value></span><span class="sxs-lookup"><span data-stu-id="7ec44-127">\<value></span></span>](../../../visual-basic/language-reference/xmldoc/value.md)||  
  
 <span data-ttu-id="7ec44-128">(<sup>1</sup> 컴파일러에서 구문을 확인 합니다.)</span><span class="sxs-lookup"><span data-stu-id="7ec44-128">(<sup>1</sup> The compiler verifies syntax.)</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="7ec44-129">문서 주석의 텍스트에 꺾쇠 괄호를 하려는 경우 사용할 `&lt;` 고 `&gt;`입니다.</span><span class="sxs-lookup"><span data-stu-id="7ec44-129">If you want angle brackets to appear in the text of a documentation comment, use `&lt;` and `&gt;`.</span></span> <span data-ttu-id="7ec44-130">예를 들어, 문자열 `"&lt;text in angle brackets&gt;"` 으로 표시 됩니다 `<text in angle brackets>`합니다.</span><span class="sxs-lookup"><span data-stu-id="7ec44-130">For example, the string `"&lt;text in angle brackets&gt;"` will appear as `<text in angle brackets>`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7ec44-131">참고자료</span><span class="sxs-lookup"><span data-stu-id="7ec44-131">See also</span></span>

- [<span data-ttu-id="7ec44-132">코드를 XML로 문서화</span><span class="sxs-lookup"><span data-stu-id="7ec44-132">Documenting Your Code with XML</span></span>](../../../visual-basic/programming-guide/program-structure/documenting-your-code-with-xml.md)
- [<span data-ttu-id="7ec44-133">/doc</span><span class="sxs-lookup"><span data-stu-id="7ec44-133">/doc</span></span>](../../../visual-basic/reference/command-line-compiler/doc.md)
- [<span data-ttu-id="7ec44-134">방법: XML 문서 만들기</span><span class="sxs-lookup"><span data-stu-id="7ec44-134">How to: Create XML Documentation</span></span>](../../../visual-basic/programming-guide/program-structure/how-to-create-xml-documentation.md)
