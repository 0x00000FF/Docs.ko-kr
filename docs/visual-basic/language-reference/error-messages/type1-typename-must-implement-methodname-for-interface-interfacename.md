---
title: '&lt;type1&gt;&#39;&lt;typename&gt; &#39; 를 구현 해야 합니다 &#39; &lt;methodname&gt; &#39; 인터페이스 &#39; &lt;interfacename&gt;&#39;'
ms.date: 07/20/2015
f1_keywords:
- vbc30149
- bc30149
helpviewer_keywords:
- BC30149
ms.assetid: 29d1b7f4-dca7-478c-bbe7-c657f342c183
ms.openlocfilehash: ff9ffd50f7f21814d5e4c23fd8df50b12bf746f5
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54642444"
---
# <a name="lttype1gt39lttypenamegt39-must-implement-39ltmethodnamegt39-for-interface-39ltinterfacenamegt39"></a><span data-ttu-id="0f978-102">&lt;type1&gt;&#39;&lt;typename&gt; &#39; 를 구현 해야 합니다 &#39; &lt;methodname&gt; &#39; 인터페이스 &#39; &lt;interfacename&gt;&#39;</span><span class="sxs-lookup"><span data-stu-id="0f978-102">&lt;type1&gt;&#39;&lt;typename&gt;&#39; must implement &#39;&lt;methodname&gt;&#39; for interface &#39;&lt;interfacename&gt;&#39;</span></span>
<span data-ttu-id="0f978-103">클래스 또는 구조체는 인터페이스를 구현 하지만 인터페이스에 의해 정의 된 프로시저를 구현 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0f978-103">A class or structure claims to implement an interface but does not implement a procedure defined by the interface.</span></span> <span data-ttu-id="0f978-104">인터페이스의 모든 멤버를 구현 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0f978-104">Every member of the interface must be implemented.</span></span>  
  
 <span data-ttu-id="0f978-105">**오류 ID:** BC30149</span><span class="sxs-lookup"><span data-stu-id="0f978-105">**Error ID:** BC30149</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="0f978-106">이 오류를 해결하려면</span><span class="sxs-lookup"><span data-stu-id="0f978-106">To correct this error</span></span>  
  
1.  <span data-ttu-id="0f978-107">동일한 이름 및 서명을 인터페이스에 정의 된 대로 사용 하 여 프로시저를 선언 합니다.</span><span class="sxs-lookup"><span data-stu-id="0f978-107">Declare a procedure with the same name and signature as defined in the interface.</span></span> <span data-ttu-id="0f978-108">포함 해야 적어도 `End Function` 또는 `End Sub` 문입니다.</span><span class="sxs-lookup"><span data-stu-id="0f978-108">Be sure to include at least the `End Function` or `End Sub` statement.</span></span>  
  
2.  <span data-ttu-id="0f978-109">추가 `Implements` 의 끝에 절을 `Function` 또는 `Sub` 문입니다.</span><span class="sxs-lookup"><span data-stu-id="0f978-109">Add an `Implements` clause to the end of the `Function` or `Sub` statement.</span></span> <span data-ttu-id="0f978-110">예를 들어:</span><span class="sxs-lookup"><span data-stu-id="0f978-110">For example:</span></span>  
  
    ```  
    Public Sub DoSomething() Implements IBaseInterface.DoSomething  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="0f978-111">참고자료</span><span class="sxs-lookup"><span data-stu-id="0f978-111">See also</span></span>
- [<span data-ttu-id="0f978-112">Implements 문</span><span class="sxs-lookup"><span data-stu-id="0f978-112">Implements Statement</span></span>](../../../visual-basic/language-reference/statements/implements-statement.md)
- [<span data-ttu-id="0f978-113">인터페이스</span><span class="sxs-lookup"><span data-stu-id="0f978-113">Interfaces</span></span>](../../../visual-basic/programming-guide/language-features/interfaces/index.md)
