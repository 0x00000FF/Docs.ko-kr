---
title: '&lt;코드&gt; (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- code XML tag
- <code> XML tag
ms.assetid: 925e5342-be05-45f2-bf66-7398bbd6710e
ms.openlocfilehash: 8a4708a7b50b0e221c1ebe7f95d4f8ff80cd1ebe
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54566309"
---
# <a name="ltcodegt-visual-basic"></a><span data-ttu-id="cd4ae-102">&lt;코드&gt; (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="cd4ae-102">&lt;code&gt; (Visual Basic)</span></span>
<span data-ttu-id="cd4ae-103">텍스트가 여러 줄의 코드 임을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="cd4ae-103">Indicates that the text is multiple lines of code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cd4ae-104">구문</span><span class="sxs-lookup"><span data-stu-id="cd4ae-104">Syntax</span></span>  
  
```xml  
<code>content</code>  
```  
  
#### <a name="parameters"></a><span data-ttu-id="cd4ae-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="cd4ae-105">Parameters</span></span>  
 `content`  
 <span data-ttu-id="cd4ae-106">코드로 표시할 텍스트입니다.</span><span class="sxs-lookup"><span data-stu-id="cd4ae-106">The text to mark as code.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="cd4ae-107">설명</span><span class="sxs-lookup"><span data-stu-id="cd4ae-107">Remarks</span></span>  
 <span data-ttu-id="cd4ae-108">사용 된 `<code>` 태그를 여러 줄을 코드로 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="cd4ae-108">Use the `<code>` tag to indicate multiple lines as code.</span></span> <span data-ttu-id="cd4ae-109">설명 내의 텍스트가 코드로 표시되도록 지정하려면 [\<c>](../../../visual-basic/language-reference/xmldoc/c.md)를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="cd4ae-109">Use [\<c>](../../../visual-basic/language-reference/xmldoc/c.md) to indicate that text within a description should be marked as code.</span></span>  
  
 <span data-ttu-id="cd4ae-110">[/doc](../../../visual-basic/reference/command-line-compiler/doc.md)로 컴파일하여 문서 주석을 파일로 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="cd4ae-110">Compile with [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="cd4ae-111">예제</span><span class="sxs-lookup"><span data-stu-id="cd4ae-111">Example</span></span>  
 <span data-ttu-id="cd4ae-112">이 예제에서는 합니다 \<코드 > 태그를 사용 하 여에 대 한 예제 코드를 포함 하는 `ID` 필드.</span><span class="sxs-lookup"><span data-stu-id="cd4ae-112">This example uses the \<code> tag to include example code for using the `ID` field.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#2](../../../visual-basic/language-reference/xmldoc/codesnippet/VisualBasic/code_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="cd4ae-113">참고자료</span><span class="sxs-lookup"><span data-stu-id="cd4ae-113">See also</span></span>
- [<span data-ttu-id="cd4ae-114">XML 주석 태그</span><span class="sxs-lookup"><span data-stu-id="cd4ae-114">XML Comment Tags</span></span>](../../../visual-basic/language-reference/xmldoc/index.md)
