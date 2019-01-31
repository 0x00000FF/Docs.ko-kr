---
title: 문이 'If' 문 줄 외부의 블록에서 끝날 수 없습니다.
ms.date: 07/20/2015
f1_keywords:
- vbc32005
- bc32005
helpviewer_keywords:
- BC32005
ms.assetid: 4039f51b-e0ee-4789-a89b-45d06de06b5d
ms.openlocfilehash: 0cee52f0ca00395d93c469aae6498fd3793f1085
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/30/2019
ms.locfileid: "55266315"
---
# <a name="statement-cannot-end-a-block-outside-of-a-line-if-statement"></a><span data-ttu-id="98806-102">문이 'If' 문 줄 외부의 블록에서 끝날 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="98806-102">Statement cannot end a block outside of a line 'If' statement</span></span>
<span data-ttu-id="98806-103">한 줄 `If` 문에서 여러 개의 문이 콜론 (:), 그 중 하나는 `End` 문을 한 줄의 외부 컨트롤 블록용 `If`합니다.</span><span class="sxs-lookup"><span data-stu-id="98806-103">A single-line `If` statement contains several statements separated by colons (:), one of which is an `End` statement for a control block outside the single-line `If`.</span></span> <span data-ttu-id="98806-104">한 줄 `If` 문을 사용 하지 마십시오는 `End If` 문입니다.</span><span class="sxs-lookup"><span data-stu-id="98806-104">Single-line `If` statements do not use the `End If` statement.</span></span>  
  
 <span data-ttu-id="98806-105">**오류 ID:** BC32005</span><span class="sxs-lookup"><span data-stu-id="98806-105">**Error ID:** BC32005</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="98806-106">이 오류를 해결하려면</span><span class="sxs-lookup"><span data-stu-id="98806-106">To correct this error</span></span>  
  
-   <span data-ttu-id="98806-107">단일 줄으로 이동 `If` 문을 포함 하는 컨트롤 블록 밖의 `End If` 문입니다.</span><span class="sxs-lookup"><span data-stu-id="98806-107">Move the single-line `If` statement outside the control block that contains the `End If` statement.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="98806-108">참고자료</span><span class="sxs-lookup"><span data-stu-id="98806-108">See also</span></span>
- [<span data-ttu-id="98806-109">If...Then...Else 문</span><span class="sxs-lookup"><span data-stu-id="98806-109">If...Then...Else Statement</span></span>](../../../visual-basic/language-reference/statements/if-then-else-statement.md)
