---
title: 배열 범위는 형식 지정자에 사용할 수 없습니다.
ms.date: 07/20/2015
f1_keywords:
- vbc30638
- bc30638
helpviewer_keywords:
- BC30638
ms.assetid: 93b654f4-70fa-4a48-baed-ffae42075550
ms.openlocfilehash: f31aea5a98233c8f262a77ba5c99eea389bc33ee
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54715441"
---
# <a name="array-bounds-cannot-appear-in-type-specifiers"></a><span data-ttu-id="e8f80-102">배열 범위는 형식 지정자에 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e8f80-102">Array bounds cannot appear in type specifiers</span></span>
<span data-ttu-id="e8f80-103">배열 크기는 데이터 형식 지정자의 일부로 선언할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e8f80-103">Array sizes cannot be declared as part of a data type specifier.</span></span>  
  
 <span data-ttu-id="e8f80-104">**오류 ID:** BC30638</span><span class="sxs-lookup"><span data-stu-id="e8f80-104">**Error ID:** BC30638</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="e8f80-105">이 오류를 해결하려면</span><span class="sxs-lookup"><span data-stu-id="e8f80-105">To correct this error</span></span>  
  
-   <span data-ttu-id="e8f80-106">이름 바로 뒤에 변수 형식, 배열 크기를 배치 하는 대신 다음 예와에서 같이 배열 크기를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="e8f80-106">Specify the size of the array immediately following the variable name instead of placing the array size after the type, as shown in the following example.</span></span>  
  
    ```  
    Dim Array(8) As Integer   
    ```  
  
-   <span data-ttu-id="e8f80-107">배열을 정의 하 고 다음 예와에서 같이 원하는 수의 요소를 초기화 합니다.</span><span class="sxs-lookup"><span data-stu-id="e8f80-107">Define an array and initialize it with the desired number of elements, as shown in the following example.</span></span>  
  
    ```  
    Dim Array2() As Integer = New Integer(8) {}  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="e8f80-108">참고자료</span><span class="sxs-lookup"><span data-stu-id="e8f80-108">See also</span></span>
- [<span data-ttu-id="e8f80-109">배열(C++)</span><span class="sxs-lookup"><span data-stu-id="e8f80-109">Arrays</span></span>](../../../visual-basic/programming-guide/language-features/arrays/index.md)
