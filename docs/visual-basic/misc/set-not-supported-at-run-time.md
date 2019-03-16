---
title: Set은 런타임에 지원되지 않습니다.
ms.date: 07/20/2015
f1_keywords:
- vbrID382
ms.assetid: cb7285d3-778f-423d-a2be-88573be8ad48
ms.openlocfilehash: 5a229bdea576f5edeaad9cc5dd63d6223ffce7d9
ms.sourcegitcommit: 5c1abeec15fbddcc7dbaa729fabc1f1f29f12045
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/15/2019
ms.locfileid: "58049354"
---
# <a name="set-not-supported-at-run-time"></a><span data-ttu-id="8e0b7-102">Set은 런타임에 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8e0b7-102">Set not supported at run time</span></span>
<span data-ttu-id="8e0b7-103">디자인 타임에만 값을 설정할 수 있는 속성을 설정하거나 변경하려고 했습니다.</span><span class="sxs-lookup"><span data-stu-id="8e0b7-103">You tried to set or change a property whose value can only be set at design time.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="8e0b7-104">이 오류를 해결하려면</span><span class="sxs-lookup"><span data-stu-id="8e0b7-104">To correct this error</span></span>  
  
1.  <span data-ttu-id="8e0b7-105">사용자 코드에서 속성에 대한 참조를 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="8e0b7-105">Remove the reference to the property from your code.</span></span>  
  
2.  <span data-ttu-id="8e0b7-106">런타임에만 속성의 값을 반환하도록 참조를 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="8e0b7-106">Change the reference to only return the value of the property at run time.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8e0b7-107">참고자료</span><span class="sxs-lookup"><span data-stu-id="8e0b7-107">See also</span></span>

- [<span data-ttu-id="8e0b7-108">프로젝트 및 솔루션 속성 관리</span><span class="sxs-lookup"><span data-stu-id="8e0b7-108">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)
