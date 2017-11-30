---
title: "&#39; ReDim &#39; 오른쪽 차원만 변경할 수 있습니다."
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: vbrArray_TypeMismatch
ms.assetid: d53cf41b-7a7a-466c-a29a-920d99698fa9
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 989a06f94824dfd051d1a7d2e7749dbb8c8e11a0
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="39redim39-can-only-change-the-right-most-dimension"></a><span data-ttu-id="ef172-102">&#39; ReDim &#39; 오른쪽 차원만 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ef172-102">&#39;ReDim&#39; can only change the right-most dimension</span></span>
<span data-ttu-id="ef172-103">`ReDim` 문에서 `Preserve` 키워드를 사용하여 마지막 차원이 아닌 배열의 차원을 변경하려고 했습니다.</span><span class="sxs-lookup"><span data-stu-id="ef172-103">A `ReDim` statement attempted to use the `Preserve` keyword to change a dimension of an array that is not the last dimension.</span></span> <span data-ttu-id="ef172-104">`Preserve`를 사용하는 경우 배열의 마지막 차원만 크기를 조정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ef172-104">When using `Preserve`, you can resize only the last dimension of an array.</span></span> <span data-ttu-id="ef172-105">다른 모든 차원의 경우 기존 배열과 동일한 크기를 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ef172-105">For all other dimensions, you must specify the same size as for the existing array.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="ef172-106">이 오류를 해결하려면</span><span class="sxs-lookup"><span data-stu-id="ef172-106">To correct this error</span></span>  
  
-   <span data-ttu-id="ef172-107">`Preserve` 키워드를 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="ef172-107">Remove the `Preserve` keyword.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ef172-108">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ef172-108">See Also</span></span>  
 [<span data-ttu-id="ef172-109">Visual Basic의 배열</span><span class="sxs-lookup"><span data-stu-id="ef172-109">Arrays in Visual Basic</span></span>](~/docs/visual-basic/programming-guide/language-features/arrays/index.md)  
 [<span data-ttu-id="ef172-110">Visual Basic의 배열 크기</span><span class="sxs-lookup"><span data-stu-id="ef172-110">Array dimensions in Visual Basic</span></span>](~/docs/visual-basic/programming-guide/language-features/arrays/array-dimensions.md)  
 [<span data-ttu-id="ef172-111">ReDim 문</span><span class="sxs-lookup"><span data-stu-id="ef172-111">ReDim Statement</span></span>](../../visual-basic/language-reference/statements/redim-statement.md)  
 [<span data-ttu-id="ef172-112">Dim 문</span><span class="sxs-lookup"><span data-stu-id="ef172-112">Dim Statement</span></span>](../../visual-basic/language-reference/statements/dim-statement.md)  
 [<span data-ttu-id="ef172-113">Preserve-삭제</span><span class="sxs-lookup"><span data-stu-id="ef172-113">Preserve - delete</span></span>](http://msdn.microsoft.com/en-us/91badeab-b4e0-48b6-92c9-9f0c8f995d81)
