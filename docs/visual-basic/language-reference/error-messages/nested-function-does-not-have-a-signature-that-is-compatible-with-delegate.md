---
title: 중첩된 함수에 '<delegatename>' 대리자와 호환되는 시그니처가 없습니다.
ms.date: 07/20/2015
f1_keywords:
- vbc36532
- bc36532
helpviewer_keywords:
- BC36532
ms.assetid: 493f292c-d81e-40ef-8b47-61f020571829
ms.openlocfilehash: ea6f230715520cb35809d57db76b300da326ec9a
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/30/2019
ms.locfileid: "55283467"
---
# <a name="nested-function-does-not-have-a-signature-that-is-compatible-with-delegate-delegatename"></a><span data-ttu-id="cab49-102">중첩 된 함수에서 대리자와 호환 되는 서명 되지 않은 '\<delegatename >'</span><span class="sxs-lookup"><span data-stu-id="cab49-102">Nested function does not have a signature that is compatible with delegate '\<delegatename>'</span></span>
<span data-ttu-id="cab49-103">람다 식에 호환 되지 않는 서명이 대리자에 할당 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="cab49-103">A lambda expression has been assigned to a delegate that has an incompatible signature.</span></span> <span data-ttu-id="cab49-104">예를 들어, 다음 코드를 대리자 `Del` 은 두 개의 정수 매개 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="cab49-104">For example, in the following code, delegate `Del` has two integer parameters.</span></span>  
  
```vb  
Delegate Function Del(ByVal p As Integer, ByVal q As Integer) As Integer  
```  
  
 <span data-ttu-id="cab49-105">하나의 인수를 사용 하 여 람다 식 형식으로 선언 된 경우 오류는 발생 `Del`:</span><span class="sxs-lookup"><span data-stu-id="cab49-105">The error is raised if a lambda expression with one argument is declared as type `Del`:</span></span>  
  
```vb  
' Neither of these is valid.   
' Dim lambda1 As Del = Function(n As Integer) n + 1  
' Dim lambda2 As Del = Function(n) n + 1  
```  
  
 <span data-ttu-id="cab49-106">**오류 ID:** BC36532</span><span class="sxs-lookup"><span data-stu-id="cab49-106">**Error ID:** BC36532</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="cab49-107">이 오류를 해결하려면</span><span class="sxs-lookup"><span data-stu-id="cab49-107">To correct this error</span></span>  
  
-   <span data-ttu-id="cab49-108">서명을 호환 되도록 할당 된 람다 식 또는 대리자 정의 조정 합니다.</span><span class="sxs-lookup"><span data-stu-id="cab49-108">Adjust either the delegate definition or the assigned lambda expression so that the signatures are compatible.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cab49-109">참고자료</span><span class="sxs-lookup"><span data-stu-id="cab49-109">See also</span></span>
- [<span data-ttu-id="cab49-110">완화된 대리자 변환</span><span class="sxs-lookup"><span data-stu-id="cab49-110">Relaxed Delegate Conversion</span></span>](../../../visual-basic/programming-guide/language-features/delegates/relaxed-delegate-conversion.md)
- [<span data-ttu-id="cab49-111">람다 식</span><span class="sxs-lookup"><span data-stu-id="cab49-111">Lambda Expressions</span></span>](../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md)
