---
title: '&lt;see&gt; - C# 프로그래밍 가이드'
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- <see>
- see
helpviewer_keywords:
- cref [C#], <see> tag
- <see> C# XML tag
- cross-references [C#]
- see C# XML tag
ms.assetid: 0200de01-7e2f-45c4-9094-829d61236383
ms.openlocfilehash: fb8b7dd0f1620895ff95917977745ac391dadf61
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54718600"
---
# <a name="ltseegt-c-programming-guide"></a><span data-ttu-id="2ac24-102">&lt;see&gt;(C# 프로그래밍 가이드)</span><span class="sxs-lookup"><span data-stu-id="2ac24-102">&lt;see&gt; (C# Programming Guide)</span></span>
## <a name="syntax"></a><span data-ttu-id="2ac24-103">구문</span><span class="sxs-lookup"><span data-stu-id="2ac24-103">Syntax</span></span>  
  
```xml  
<see cref="member"/>  
```  
  
#### <a name="parameters"></a><span data-ttu-id="2ac24-104">매개 변수</span><span class="sxs-lookup"><span data-stu-id="2ac24-104">Parameters</span></span>  
 <span data-ttu-id="2ac24-105">cref = " `member`"</span><span class="sxs-lookup"><span data-stu-id="2ac24-105">cref = " `member`"</span></span>  
 <span data-ttu-id="2ac24-106">현재 컴파일 환경에서 호출할 수 있는 멤버 또는 필드에 대한 참조입니다.</span><span class="sxs-lookup"><span data-stu-id="2ac24-106">A reference to a member or field that is available to be called from the current compilation environment.</span></span> <span data-ttu-id="2ac24-107">컴파일러는 지정된 코드 요소가 있으며 `member`를 출력 XML의 요소 이름에 전달하는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="2ac24-107">The compiler checks that the given code element exists and passes `member` to the element name in the output XML.</span></span> <span data-ttu-id="2ac24-108">*멤버*는 큰따옴표(“ ”)로 묶으세요.</span><span class="sxs-lookup"><span data-stu-id="2ac24-108">Place *member* within double quotation marks (" ").</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2ac24-109">주의</span><span class="sxs-lookup"><span data-stu-id="2ac24-109">Remarks</span></span>  
 <span data-ttu-id="2ac24-110">\<see> 태그를 사용하면 텍스트 내부에서 링크를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2ac24-110">The \<see> tag lets you specify a link from within text.</span></span> <span data-ttu-id="2ac24-111">참고 항목 부분에 배치할 텍스트를 지정하려면 [\<seealso>](../../../csharp/programming-guide/xmldoc/seealso.md)를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="2ac24-111">Use [\<seealso>](../../../csharp/programming-guide/xmldoc/seealso.md) to indicate that text should be placed in a See Also section.</span></span> <span data-ttu-id="2ac24-112">코드 요소의 문서 페이지에 대한 내부 하이퍼링크를 만들려면 [cref 특성](../../../csharp/programming-guide/xmldoc/cref-attribute.md)을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="2ac24-112">Use the [cref Attribute](../../../csharp/programming-guide/xmldoc/cref-attribute.md) to create internal hyperlinks to documentation pages for code elements.</span></span>  
  
 <span data-ttu-id="2ac24-113">[-doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md)로 컴파일하여 문서 주석을 파일로 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="2ac24-113">Compile with [-doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md) to process documentation comments to a file.</span></span>  
  
 <span data-ttu-id="2ac24-114">다음 예제에서는 요약 섹션의 \<see> 태그를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="2ac24-114">The following example shows a \<see> tag within a summary section.</span></span>  
  
 [!code-csharp[csProgGuideDocComments#12](../../../csharp/programming-guide/xmldoc/codesnippet/CSharp/see_1.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="2ac24-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="2ac24-115">See also</span></span>

- [<span data-ttu-id="2ac24-116">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="2ac24-116">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)
- [<span data-ttu-id="2ac24-117">문서 주석에 대한 권장 태그</span><span class="sxs-lookup"><span data-stu-id="2ac24-117">Recommended Tags for Documentation Comments</span></span>](../../../csharp/programming-guide/xmldoc/recommended-tags-for-documentation-comments.md)
