---
title: 이 'Sub New'의 첫째 문은 'MyBase.New' 또는 'MyClass.New'에 대한 호출이어야 합니다(매개 변수가 없는 액세스할 수 있는 생성자가 없음).
ms.date: 07/20/2015
f1_keywords:
- bc30148
- vbc30148
helpviewer_keywords:
- BC30148
ms.assetid: 4426e8fc-cb39-4eb8-ba95-503cd32fcc89
ms.openlocfilehash: d29d7609f8f3f38eadda9a9c763f3ba8e6b99e61
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/30/2019
ms.locfileid: "55278540"
---
# <a name="first-statement-of-this-sub-new-must-be-a-call-to-mybasenew-or-myclassnew-no-accessible-constructor-without-parameters"></a><span data-ttu-id="2e1fc-102">이 'Sub New'의 첫째 문은 'MyBase.New' 또는 'MyClass.New'에 대한 호출이어야 합니다(매개 변수가 없는 액세스할 수 있는 생성자가 없음).</span><span class="sxs-lookup"><span data-stu-id="2e1fc-102">First statement of this 'Sub New' must be a call to 'MyBase.New' or 'MyClass.New' (No Accessible Constructor Without Parameters)</span></span>
<span data-ttu-id="2e1fc-103">때문에이 ' Sub n e '의 첫째 문은 'MyBase.New' 또는 'm y'에 대 한 호출 이어야 합니다 기본 클래스\<basename >'의 '\<derivedname >' 인수 없이 호출할 수 있는 액세스 가능한 ' Sub n이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="2e1fc-103">First statement of this 'Sub New' must be a call to 'MyBase.New' or 'MyClass.New' because base class '\<basename>' of '\<derivedname>' does not have an accessible 'Sub New' that can be called with no arguments.</span></span>  
  
 <span data-ttu-id="2e1fc-104">모든 생성자는 파생된 클래스에서 기본 클래스 생성자를 호출 해야 합니다 (`MyBase.New`).</span><span class="sxs-lookup"><span data-stu-id="2e1fc-104">In a derived class, every constructor must call a base class constructor (`MyBase.New`).</span></span> <span data-ttu-id="2e1fc-105">기본 클래스에 파생된 클래스에 액세스할 수 있는 매개 변수가 없는 생성자가 하는 경우 `MyBase.New` 자동으로 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2e1fc-105">If the base class has a constructor with no parameters that is accessible to derived classes, `MyBase.New` can be called automatically.</span></span> <span data-ttu-id="2e1fc-106">그렇지 않은 경우 매개 변수를 사용 하 여 기본 클래스 생성자를 호출 해야 하 고 자동으로 수행할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="2e1fc-106">If not, a base class constructor must be called with parameters, and this cannot be done automatically.</span></span> <span data-ttu-id="2e1fc-107">이 경우 모든 파생된 클래스 생성자의 첫 번째 문 기본 클래스에서 매개 변수화 된 생성자를 호출 하거나 기본 클래스 생성자를 호출 하는 파생된 클래스의 다른 생성자를 호출 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2e1fc-107">In this case, the first statement of every derived class constructor must call a parameterized constructor on the base class, or call another constructor in the derived class that makes a base class constructor call.</span></span>  
  
 <span data-ttu-id="2e1fc-108">**오류 ID:** BC30148</span><span class="sxs-lookup"><span data-stu-id="2e1fc-108">**Error ID:** BC30148</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="2e1fc-109">이 오류를 해결하려면</span><span class="sxs-lookup"><span data-stu-id="2e1fc-109">To correct this error</span></span>  
  
-   <span data-ttu-id="2e1fc-110">호출 `MyBase.New` 필수 매개 변수를 제공 하거나 이러한 호출 피어 생성자를 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="2e1fc-110">Either call `MyBase.New` supplying the required parameters, or call a peer constructor that makes such a call.</span></span>  
  
     <span data-ttu-id="2e1fc-111">예를 들어, 기본 클래스에 생성자로 선언 된 경우 `Public Sub New(ByVal index as Integer)`, 파생의 첫째 문은 클래스 생성자 않을 `MyBase.New(100)`합니다.</span><span class="sxs-lookup"><span data-stu-id="2e1fc-111">For example, if the base class has a constructor that’s declared as `Public Sub New(ByVal index as Integer)`, the first statement in the derived class constructor might be `MyBase.New(100)`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2e1fc-112">참고자료</span><span class="sxs-lookup"><span data-stu-id="2e1fc-112">See also</span></span>
- [<span data-ttu-id="2e1fc-113">상속 기본 사항</span><span class="sxs-lookup"><span data-stu-id="2e1fc-113">Inheritance Basics</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md)
