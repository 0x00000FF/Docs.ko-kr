---
title: '&lt;seealso&gt; - C# 프로그래밍 가이드'
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- cref
- <seealso>
- seealso
helpviewer_keywords:
- cref [C#], see also
- seealso C# XML tag
- cref [C#]
- cross-references [C#], tags
- <seealso> C# XML tag
ms.assetid: 8e157f3f-f220-4fcf-9010-88905b080b18
ms.openlocfilehash: eec4a0c2041d7d10b5887950bfec03ec8847c82b
ms.sourcegitcommit: bdd930b5df20a45c29483d905526a2a3e4d17c5b
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/11/2018
ms.locfileid: "53244793"
---
# <a name="ltseealsogt-c-programming-guide"></a><span data-ttu-id="4afe2-102">&lt;seealso&gt;(C# 프로그래밍 가이드)</span><span class="sxs-lookup"><span data-stu-id="4afe2-102">&lt;seealso&gt; (C# Programming Guide)</span></span>
## <a name="syntax"></a><span data-ttu-id="4afe2-103">구문</span><span class="sxs-lookup"><span data-stu-id="4afe2-103">Syntax</span></span>  
  
```xml  
<seealso cref="member"/>  
```  
  
#### <a name="parameters"></a><span data-ttu-id="4afe2-104">매개 변수</span><span class="sxs-lookup"><span data-stu-id="4afe2-104">Parameters</span></span>  
 <span data-ttu-id="4afe2-105">cref = " `member`"</span><span class="sxs-lookup"><span data-stu-id="4afe2-105">cref = " `member`"</span></span>  
 <span data-ttu-id="4afe2-106">현재 컴파일 환경에서 호출할 수 있는 멤버 또는 필드에 대한 참조입니다.</span><span class="sxs-lookup"><span data-stu-id="4afe2-106">A reference to a member or field that is available to be called from the current compilation environment.</span></span> <span data-ttu-id="4afe2-107">컴파일러는 지정된 코드 요소가 있으며 `member`를 출력 XML의 요소 이름에 전달하는지 확인합니다. `member`</span><span class="sxs-lookup"><span data-stu-id="4afe2-107">The compiler checks that the given code element exists and passes `member` to the element name in the output XML.`member`</span></span> <span data-ttu-id="4afe2-108">는 큰따옴표(“ ”)로 묶어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4afe2-108">must appear within double quotation marks (" ").</span></span>  
  
 <span data-ttu-id="4afe2-109">제네릭 형식에 대한 cref 참조를 만드는 방법에 대한 자세한 내용은 [\<see>](../../../csharp/programming-guide/xmldoc/see.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="4afe2-109">For information on how to create a cref reference to a generic type, see [\<see>](../../../csharp/programming-guide/xmldoc/see.md).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4afe2-110">설명</span><span class="sxs-lookup"><span data-stu-id="4afe2-110">Remarks</span></span>  
 <span data-ttu-id="4afe2-111">\<seealso> 태그를 사용하면 참고 항목 섹션에 표시할 텍스트를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4afe2-111">The \<seealso> tag lets you specify the text that you might want to appear in a See Also section.</span></span> <span data-ttu-id="4afe2-112">텍스트 내에서 링크를 지정하려면 [\<see>](../../../csharp/programming-guide/xmldoc/see.md)를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="4afe2-112">Use [\<see>](../../../csharp/programming-guide/xmldoc/see.md) to specify a link from within text.</span></span>  
  
 <span data-ttu-id="4afe2-113">[/doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md)로 컴파일하여 문서 주석을 파일로 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="4afe2-113">Compile with [/doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4afe2-114">예</span><span class="sxs-lookup"><span data-stu-id="4afe2-114">Example</span></span>  
 <span data-ttu-id="4afe2-115">\<seealso>를 사용한 예제는 [\<summary>](../../../csharp/programming-guide/xmldoc/summary.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="4afe2-115">See [\<summary>](../../../csharp/programming-guide/xmldoc/summary.md) for an example of using \<seealso>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4afe2-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="4afe2-116">See Also</span></span>

- [<span data-ttu-id="4afe2-117">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="4afe2-117">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="4afe2-118">문서 주석에 대한 권장 태그</span><span class="sxs-lookup"><span data-stu-id="4afe2-118">Recommended Tags for Documentation Comments</span></span>](../../../csharp/programming-guide/xmldoc/recommended-tags-for-documentation-comments.md)
