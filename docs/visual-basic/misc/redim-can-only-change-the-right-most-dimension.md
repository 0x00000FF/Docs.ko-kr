---
title: "'ReDim'으로는 맨 오른쪽 차원만 변경할 수 있습니다."
ms.date: 07/20/2015
f1_keywords:
- vbrArray_TypeMismatch
ms.assetid: d53cf41b-7a7a-466c-a29a-920d99698fa9
ms.openlocfilehash: d20d0374cd5183b6216d1c6e5b138256cf0a4f17
ms.sourcegitcommit: facefcacd7ae2e5645e463bc841df213c505ffd4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/05/2019
ms.locfileid: "55738957"
---
# <a name="redim-can-only-change-the-right-most-dimension"></a><span data-ttu-id="3744f-102">'ReDim'으로는 맨 오른쪽 차원만 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3744f-102">'ReDim' can only change the right-most dimension</span></span>
<span data-ttu-id="3744f-103">`ReDim` 문에서 `Preserve` 키워드를 사용하여 마지막 차원이 아닌 배열의 차원을 변경하려고 했습니다.</span><span class="sxs-lookup"><span data-stu-id="3744f-103">A `ReDim` statement attempted to use the `Preserve` keyword to change a dimension of an array that is not the last dimension.</span></span> <span data-ttu-id="3744f-104">`Preserve`를 사용하는 경우 배열의 마지막 차원만 크기를 조정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3744f-104">When using `Preserve`, you can resize only the last dimension of an array.</span></span> <span data-ttu-id="3744f-105">다른 모든 차원의 경우 기존 배열과 동일한 크기를 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3744f-105">For all other dimensions, you must specify the same size as for the existing array.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="3744f-106">이 오류를 해결하려면</span><span class="sxs-lookup"><span data-stu-id="3744f-106">To correct this error</span></span>  
  
-   <span data-ttu-id="3744f-107">`Preserve` 키워드를 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="3744f-107">Remove the `Preserve` keyword.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3744f-108">참고자료</span><span class="sxs-lookup"><span data-stu-id="3744f-108">See also</span></span>
- [<span data-ttu-id="3744f-109">Visual Basic의 배열</span><span class="sxs-lookup"><span data-stu-id="3744f-109">Arrays in Visual Basic</span></span>](~/docs/visual-basic/programming-guide/language-features/arrays/index.md)
- [<span data-ttu-id="3744f-110">Visual Basic의 배열 크기</span><span class="sxs-lookup"><span data-stu-id="3744f-110">Array dimensions in Visual Basic</span></span>](~/docs/visual-basic/programming-guide/language-features/arrays/array-dimensions.md)
- [<span data-ttu-id="3744f-111">ReDim 문</span><span class="sxs-lookup"><span data-stu-id="3744f-111">ReDim Statement</span></span>](../../visual-basic/language-reference/statements/redim-statement.md)
- [<span data-ttu-id="3744f-112">Dim 문</span><span class="sxs-lookup"><span data-stu-id="3744f-112">Dim Statement</span></span>](../../visual-basic/language-reference/statements/dim-statement.md)
