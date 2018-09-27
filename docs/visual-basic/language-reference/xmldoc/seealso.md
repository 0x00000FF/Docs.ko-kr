---
title: '&lt;seealso&gt; (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- <seealso> XML tag
- seealso XML tag
ms.assetid: 36050c95-1af2-4284-b9b6-1a70691ed978
ms.openlocfilehash: a792bbea108bcdf33d430c47773466ef3dccdb0c
ms.sourcegitcommit: fb78d8abbdb87144a3872cf154930157090dd933
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/27/2018
ms.locfileid: "47401185"
---
# <a name="ltseealsogt-visual-basic"></a><span data-ttu-id="5611e-102">&lt;seealso&gt; (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="5611e-102">&lt;seealso&gt; (Visual Basic)</span></span>
<span data-ttu-id="5611e-103">참고 항목 섹션에 표시 되는 링크를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="5611e-103">Specifies a link that appears in the See Also section.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5611e-104">구문</span><span class="sxs-lookup"><span data-stu-id="5611e-104">Syntax</span></span>  
  
```xml  
<seealso cref="member"/>  
```  
  
#### <a name="parameters"></a><span data-ttu-id="5611e-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="5611e-105">Parameters</span></span>  
 `member`  
 <span data-ttu-id="5611e-106">현재 컴파일 환경에서 호출할 수 있는 멤버 또는 필드에 대한 참조입니다.</span><span class="sxs-lookup"><span data-stu-id="5611e-106">A reference to a member or field that is available to be called from the current compilation environment.</span></span> <span data-ttu-id="5611e-107">컴파일러는 지정 된 코드 요소가 있고 전달 확인 `member` 를 출력 XML에에서 요소 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="5611e-107">The compiler checks that the given code element exists and passes `member` to the element name in the output XML.</span></span> <span data-ttu-id="5611e-108">`member`는 큰따옴표(" ")로 묶어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5611e-108">`member` must appear within double quotation marks (" ").</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5611e-109">설명</span><span class="sxs-lookup"><span data-stu-id="5611e-109">Remarks</span></span>  
 <span data-ttu-id="5611e-110">사용 된 `<seealso>` 참고 항목 섹션에 표시 하려는 텍스트를 지정 하는 태그입니다.</span><span class="sxs-lookup"><span data-stu-id="5611e-110">Use the `<seealso>` tag to specify the text that you want to appear in a See Also section.</span></span> <span data-ttu-id="5611e-111">텍스트 내에서 링크를 지정하려면 [\<see>](../../../visual-basic/language-reference/xmldoc/see.md)를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="5611e-111">Use [\<see>](../../../visual-basic/language-reference/xmldoc/see.md) to specify a link from within text.</span></span>  
  
 <span data-ttu-id="5611e-112">[/doc](../../../visual-basic/reference/command-line-compiler/doc.md)로 컴파일하여 문서 주석을 파일로 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="5611e-112">Compile with [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5611e-113">예제</span><span class="sxs-lookup"><span data-stu-id="5611e-113">Example</span></span>  
 <span data-ttu-id="5611e-114">이 예제에서는 합니다 `<seealso>` 태그를 `DoesRecordExist` 주의 섹션을 참조는 `UpdateRecord` 메서드.</span><span class="sxs-lookup"><span data-stu-id="5611e-114">This example uses the `<seealso>` tag in the `DoesRecordExist` remarks section to refer to the `UpdateRecord` method.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#6](../../../visual-basic/language-reference/xmldoc/codesnippet/VisualBasic/seealso_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="5611e-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="5611e-115">See Also</span></span>  
 [<span data-ttu-id="5611e-116">XML 주석 태그</span><span class="sxs-lookup"><span data-stu-id="5611e-116">XML Comment Tags</span></span>](../../../visual-basic/language-reference/xmldoc/index.md)
