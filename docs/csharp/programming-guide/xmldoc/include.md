---
title: '&lt;include&gt;(C# 프로그래밍 가이드)'
ms.date: 07/20/2015
f1_keywords:
- include
- <include>
helpviewer_keywords:
- <include> C# XML tag
- include C# XML tag
ms.assetid: a8a70302-6196-4643-bd09-ef33f411f18f
ms.openlocfilehash: 854c8b61fa8164bccfc9451f2f163dab4a56388f
ms.sourcegitcommit: fb78d8abbdb87144a3872cf154930157090dd933
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/01/2018
ms.locfileid: "47192994"
---
# <a name="ltincludegt-c-programming-guide"></a><span data-ttu-id="f263e-102">&lt;include&gt;(C# 프로그래밍 가이드)</span><span class="sxs-lookup"><span data-stu-id="f263e-102">&lt;include&gt; (C# Programming Guide)</span></span>
## <a name="syntax"></a><span data-ttu-id="f263e-103">구문</span><span class="sxs-lookup"><span data-stu-id="f263e-103">Syntax</span></span>  
  
```xml  
<include file='filename' path='tagpath[@name="id"]' />  
```  
  
#### <a name="parameters"></a><span data-ttu-id="f263e-104">매개 변수</span><span class="sxs-lookup"><span data-stu-id="f263e-104">Parameters</span></span>  
 `filename`  
 <span data-ttu-id="f263e-105">문서가 포함된 XML 파일의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="f263e-105">The name of the XML file containing the documentation.</span></span> <span data-ttu-id="f263e-106">파일 이름은 소스 코드 파일에 상대 경로로 한정될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f263e-106">The file name can be qualified with a path relative to the source code file.</span></span> <span data-ttu-id="f263e-107">`filename`을 작은따옴표(‘ ’)로 묶습니다.</span><span class="sxs-lookup"><span data-stu-id="f263e-107">Enclose `filename` in single quotation marks (' ').</span></span>  
  
 `tagpath`  
 <span data-ttu-id="f263e-108">`filename`의 태그 경로로, `name` 태그에 연결됩니다.</span><span class="sxs-lookup"><span data-stu-id="f263e-108">The path of the tags in `filename` that leads to the tag `name`.</span></span> <span data-ttu-id="f263e-109">경로를 작은따옴표(‘ ’)로 묶습니다.</span><span class="sxs-lookup"><span data-stu-id="f263e-109">Enclose the path in single quotation marks (' ').</span></span>  
  
 `name`  
 <span data-ttu-id="f263e-110">주석 앞에 오는 태그의 이름 지정자입니다. `name`에는 `id`가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f263e-110">The name specifier in the tag that precedes the comments; `name` will have an `id`.</span></span>  
  
 `id`  
 <span data-ttu-id="f263e-111">주석 앞에 오는 태그의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="f263e-111">The ID for the tag that precedes the comments.</span></span> <span data-ttu-id="f263e-112">ID를 큰따옴표(“ ”)로 묶습니다.</span><span class="sxs-lookup"><span data-stu-id="f263e-112">Enclose the ID in double quotation marks (" ").</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f263e-113">설명</span><span class="sxs-lookup"><span data-stu-id="f263e-113">Remarks</span></span>  
 <span data-ttu-id="f263e-114">\<include> 태그를 사용하면 소스 코드의 형식과 멤버를 설명하는 다른 파일의 주석을 참조할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f263e-114">The \<include> tag lets you refer to comments in another file that describe the types and members in your source code.</span></span> <span data-ttu-id="f263e-115">소스 코드 파일에 직접 문서 주석을 포함하는 대신 사용되는 대안입니다.</span><span class="sxs-lookup"><span data-stu-id="f263e-115">This is an alternative to placing documentation comments directly in your source code file.</span></span> <span data-ttu-id="f263e-116">별도 파일에 문서를 배치하면 소스 코드와 별도로 문서에 소스 제어를 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f263e-116">By putting the documentation in a separate file, you can apply source control to the documentation separately from the source code.</span></span> <span data-ttu-id="f263e-117">한 사람은 소스 코드 파일을 체크 아웃하고 다른 사람은 문서 파일을 체크 아웃할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f263e-117">One person can have the source code file checked out and someone else can have the documentation file checked out.</span></span>  
  
 <span data-ttu-id="f263e-118">\<include> 태그는 XML XPath 구문을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="f263e-118">The \<include> tag uses the XML XPath syntax.</span></span> <span data-ttu-id="f263e-119">\<include> 사용을 사용자 지정하는 방법은 XPath 설명서를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f263e-119">Refer to XPath documentation for ways to customize your \<include> use.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f263e-120">예</span><span class="sxs-lookup"><span data-stu-id="f263e-120">Example</span></span>  
 <span data-ttu-id="f263e-121">다중 파일 예제입니다.</span><span class="sxs-lookup"><span data-stu-id="f263e-121">This is a multifile example.</span></span> <span data-ttu-id="f263e-122">아래에는 \<include>를 사용하는 첫 번째 파일이 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f263e-122">The first file, which uses \<include>, is listed below:</span></span>  
  
 [!code-csharp[csProgGuideDocComments#5](../../../csharp/programming-guide/xmldoc/codesnippet/CSharp/include_1.cs)]  
  
 <span data-ttu-id="f263e-123">두 번째 파일인 xml_include_tag.doc에는 다음과 같은 문서 주석이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f263e-123">The second file, xml_include_tag.doc, contains the following documentation comments:</span></span>  
  
```xml  
<MyDocs>  
  
<MyMembers name="test">  
<summary>  
The summary for this type.  
</summary>  
</MyMembers>  
  
<MyMembers name="test2">  
<summary>  
The summary for this other type.  
</summary>  
</MyMembers>  
  
</MyDocs>  
```  
  
## <a name="program-output"></a><span data-ttu-id="f263e-124">프로그램 출력</span><span class="sxs-lookup"><span data-stu-id="f263e-124">Program Output</span></span>  
 <span data-ttu-id="f263e-125">`/doc:DocFileName.xml.` 명령줄을 사용하여 Test 및 Test2 클래스를 컴파일하면 다음 출력이 생성됩니다. Visual Studio에서 프로젝트 디자이너의 빌드 창에 있는 XML 문서 주석 옵션을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="f263e-125">The following output is generated when you compile the Test and Test2 classes with the following command line: `/doc:DocFileName.xml.` In Visual Studio, you specify the XML doc comments option in the Build pane of the Project Designer.</span></span> <span data-ttu-id="f263e-126">C# 컴파일러는 \<inclue> 태그를 발견할 경우 현재 소스 파일 대신 xml_include_tag.doc에서 문서 주석을 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="f263e-126">When the C# compiler sees the \<include> tag, it will search for documentation comments in xml_include_tag.doc instead of the current source file.</span></span> <span data-ttu-id="f263e-127">그런 다음 컴파일러는 DocFileName.xml을 생성합니다. 이 파일은 [Sandcastle](https://github.com/EWSoftware/SHFB) 등의 문서 도구에서 최종 문서를 생성하는 데 사용하는 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="f263e-127">The compiler then generates DocFileName.xml, and this is the file that is consumed by documentation tools such as [Sandcastle](https://github.com/EWSoftware/SHFB) to produce the final documentation.</span></span>  
  
```xml  
<?xml version="1.0"?>   
<doc>   
    <assembly>   
        <name>xml_include_tag</name>   
    </assembly>   
    <members>   
        <member name="T:Test">   
            <summary>   
The summary for this type.   
</summary>   
        </member>   
        <member name="T:Test2">   
            <summary>   
The summary for this other type.   
</summary>   
        </member>   
    </members>   
</doc>   
```  
  
## <a name="see-also"></a><span data-ttu-id="f263e-128">참고 항목</span><span class="sxs-lookup"><span data-stu-id="f263e-128">See Also</span></span>

- [<span data-ttu-id="f263e-129">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="f263e-129">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="f263e-130">문서 주석에 대한 권장 태그</span><span class="sxs-lookup"><span data-stu-id="f263e-130">Recommended Tags for Documentation Comments</span></span>](../../../csharp/programming-guide/xmldoc/recommended-tags-for-documentation-comments.md)
