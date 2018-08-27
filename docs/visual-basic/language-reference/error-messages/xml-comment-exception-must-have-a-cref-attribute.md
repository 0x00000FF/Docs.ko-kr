---
title: XML 주석 예외 있어야는 &#39;cref&#39; 특성
ms.date: 07/20/2015
f1_keywords:
- bc42319
- vbc42319
helpviewer_keywords:
- BC42319
ms.assetid: 62eeeba3-6811-48be-b1ef-c2e4feda3177
ms.openlocfilehash: abe9fe0f6216f81fa223fe83a122b580577e1c32
ms.sourcegitcommit: e614e0f3b031293e4107f37f752be43652f3f253
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/26/2018
ms.locfileid: "42930030"
---
# <a name="xml-comment-exception-must-have-a-39cref39-attribute"></a><span data-ttu-id="eb330-102">XML 주석 예외 있어야는 &#39;cref&#39; 특성</span><span class="sxs-lookup"><span data-stu-id="eb330-102">XML comment exception must have a &#39;cref&#39; attribute</span></span>
<span data-ttu-id="eb330-103">\<예외 > 태그는 메서드에서 throw 될 수 있는 예외를 문서화 하는 방법을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="eb330-103">The \<exception> tag provides a way to document the exceptions that may be thrown by a method.</span></span> <span data-ttu-id="eb330-104">필수 `cref` 특성 설명서 생성기에서 확인 하는 멤버의 이름을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="eb330-104">The required `cref` attribute designates the name of a member, which is checked by the documentation generator.</span></span> <span data-ttu-id="eb330-105">멤버가 있는 경우 문서 파일의 정식 요소 이름으로 변환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="eb330-105">If the member exists, it is translated to the canonical element name in the documentation file.</span></span>  
  
 <span data-ttu-id="eb330-106">**오류 ID:** BC42319</span><span class="sxs-lookup"><span data-stu-id="eb330-106">**Error ID:** BC42319</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="eb330-107">이 오류를 해결하려면</span><span class="sxs-lookup"><span data-stu-id="eb330-107">To correct this error</span></span>  
  
-   <span data-ttu-id="eb330-108">추가 된 `cref` 예외에 특성을 다음과 같이 합니다.</span><span class="sxs-lookup"><span data-stu-id="eb330-108">Add the `cref` attribute to the exception as follows:</span></span>  
  
    ```  
    '''<exception cref="member">description</exception>  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="eb330-109">참고 항목</span><span class="sxs-lookup"><span data-stu-id="eb330-109">See Also</span></span>  
 [<span data-ttu-id="eb330-110">\<exception></span><span class="sxs-lookup"><span data-stu-id="eb330-110">\<exception></span></span>](../../../visual-basic/language-reference/xmldoc/exception.md)  
 [<span data-ttu-id="eb330-111">방법: XML 문서 만들기</span><span class="sxs-lookup"><span data-stu-id="eb330-111">How to: Create XML Documentation</span></span>](../../../visual-basic/programming-guide/program-structure/how-to-create-xml-documentation.md)  
 [<span data-ttu-id="eb330-112">XML 주석 태그</span><span class="sxs-lookup"><span data-stu-id="eb330-112">XML Comment Tags</span></span>](../../../visual-basic/language-reference/xmldoc/index.md)
