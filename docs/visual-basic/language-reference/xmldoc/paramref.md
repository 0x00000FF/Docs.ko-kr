---
title: '&lt;paramref&gt; (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- paramref XML tag
- <paramref> XML tag
ms.assetid: 8979d53b-beb1-41b7-b41e-6bbea1c17a03
ms.openlocfilehash: 153f5ddeeb7d09159049af4d466b0695f5cb6f23
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/04/2018
ms.locfileid: "43503204"
---
# <a name="ltparamrefgt-visual-basic"></a><span data-ttu-id="6d5ab-102">&lt;paramref&gt; (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="6d5ab-102">&lt;paramref&gt; (Visual Basic)</span></span>
<span data-ttu-id="6d5ab-103">단어를 형식을 매개 변수로 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="6d5ab-103">Formats a word as a parameter.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6d5ab-104">구문</span><span class="sxs-lookup"><span data-stu-id="6d5ab-104">Syntax</span></span>  
  
```xml  
<paramref name="name"/>  
```  
  
#### <a name="parameters"></a><span data-ttu-id="6d5ab-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="6d5ab-105">Parameters</span></span>  
 `name`  
 <span data-ttu-id="6d5ab-106">참조할 매개 변수의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="6d5ab-106">The name of the parameter to refer to.</span></span> <span data-ttu-id="6d5ab-107">이름을 큰따옴표(“ ”)로 묶습니다.</span><span class="sxs-lookup"><span data-stu-id="6d5ab-107">Enclose the name in double quotation marks (" ").</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6d5ab-108">설명</span><span class="sxs-lookup"><span data-stu-id="6d5ab-108">Remarks</span></span>  
 <span data-ttu-id="6d5ab-109">`<paramref>` 태그 하면 단어는 매개 변수를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6d5ab-109">The `<paramref>` tag gives you a way to indicate that a word is a parameter.</span></span> <span data-ttu-id="6d5ab-110">XML 파일을 다른 방식으로이 매개 변수 형식을 처리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6d5ab-110">The XML file can be processed to format this parameter in some distinct way.</span></span>  
  
 <span data-ttu-id="6d5ab-111">[/doc](../../../visual-basic/reference/command-line-compiler/doc.md)로 컴파일하여 문서 주석을 파일로 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="6d5ab-111">Compile with [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6d5ab-112">예제</span><span class="sxs-lookup"><span data-stu-id="6d5ab-112">Example</span></span>  
 <span data-ttu-id="6d5ab-113">이 예제에서는 합니다 `<paramref>` 참조 하는 태그를 `id` 매개 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="6d5ab-113">This example uses the `<paramref>` tag to refer to the `id` parameter.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#6](../../../visual-basic/language-reference/xmldoc/codesnippet/VisualBasic/paramref_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="6d5ab-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="6d5ab-114">See Also</span></span>  
 [<span data-ttu-id="6d5ab-115">XML 주석 태그</span><span class="sxs-lookup"><span data-stu-id="6d5ab-115">XML Comment Tags</span></span>](../../../visual-basic/language-reference/xmldoc/index.md)
