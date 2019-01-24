---
title: 익명 형식 멤버 이름은 인수가 없는 단순한 이름 또는 정규화된 이름에서만 유추할 수 있습니다.
ms.date: 07/20/2015
f1_keywords:
- vbc36556
- bc36556
helpviewer_keywords:
- BC36556
ms.assetid: e3ba1f33-3a71-4f03-9b04-ed5ec17de17c
ms.openlocfilehash: 4d91b7a3c57db38fde3cf371773e8d64834a8f72
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54715272"
---
# <a name="anonymous-type-member-name-can-be-inferred-only-from-a-simple-or-qualified-name-with-no-arguments"></a><span data-ttu-id="3e853-102">익명 형식 멤버 이름은 인수가 없는 단순한 이름 또는 정규화된 이름에서만 유추할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3e853-102">Anonymous type member name can be inferred only from a simple or qualified name with no arguments</span></span>
<span data-ttu-id="3e853-103">복잡 한 식에서 무명 형식 멤버 이름은 유추할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="3e853-103">You cannot infer an anonymous type member name from a complex expression.</span></span>  
  
```vb  
Dim numbers() As Integer = {1, 2, 3, 4, 5}  
' Not valid.  
' Dim instanceName1 = New With {numbers(3)}  
```  
  
 <span data-ttu-id="3e853-104">익명 형식 및 멤버 이름 및 형식을 유추할 수 없습니다. 원본에 대 한 자세한 내용은 참조 하세요. [방법: 무명 형식 선언에서 속성 이름 및 형식 유추](../../../visual-basic/programming-guide/language-features/objects-and-classes/how-to-infer-property-names-and-types-in-anonymous-type-declarations.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="3e853-104">For more information about sources from which anonymous types can and cannot infer member names and types, see [How to: Infer Property Names and Types in Anonymous Type Declarations](../../../visual-basic/programming-guide/language-features/objects-and-classes/how-to-infer-property-names-and-types-in-anonymous-type-declarations.md).</span></span>  
  
 <span data-ttu-id="3e853-105">**오류 ID:** BC36556</span><span class="sxs-lookup"><span data-stu-id="3e853-105">**Error ID:** BC36556</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="3e853-106">이 오류를 해결하려면</span><span class="sxs-lookup"><span data-stu-id="3e853-106">To correct this error</span></span>  
  
-   <span data-ttu-id="3e853-107">다음 코드와 같이 식을 멤버 이름으로 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="3e853-107">Assign the expression to a member name, as shown in the following code:</span></span>  
  
    ```  
    Dim instanceName2 = New With {.number = numbers(3)}  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="3e853-108">참고자료</span><span class="sxs-lookup"><span data-stu-id="3e853-108">See also</span></span>
- [<span data-ttu-id="3e853-109">익명 형식</span><span class="sxs-lookup"><span data-stu-id="3e853-109">Anonymous Types</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md)
- [<span data-ttu-id="3e853-110">방법: 무명 형식 선언에서 속성 이름 및 형식 유추</span><span class="sxs-lookup"><span data-stu-id="3e853-110">How to: Infer Property Names and Types in Anonymous Type Declarations</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/how-to-infer-property-names-and-types-in-anonymous-type-declarations.md)
