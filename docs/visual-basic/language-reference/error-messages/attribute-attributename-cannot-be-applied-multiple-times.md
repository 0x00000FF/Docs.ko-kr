---
title: "'<attributename>' 특성을 여러 번 사용할 수 없습니다."
ms.date: 07/20/2015
f1_keywords:
- bc30663
- vbc30663
helpviewer_keywords:
- BC30663
ms.assetid: 3760e7ff-7238-40a1-8676-77d858a64fc0
ms.openlocfilehash: 62e84d174e4e218472eda9b7c08ed677e0140438
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/30/2019
ms.locfileid: "55278709"
---
# <a name="attribute-attributename-cannot-be-applied-multiple-times"></a><span data-ttu-id="fb3fe-102">특성 '\<attributename >' 여러 번 적용할 수 없습니다</span><span class="sxs-lookup"><span data-stu-id="fb3fe-102">Attribute '\<attributename>' cannot be applied multiple times</span></span>
<span data-ttu-id="fb3fe-103">특성 한 번만 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fb3fe-103">The attribute can only be applied once.</span></span> <span data-ttu-id="fb3fe-104">`AttributeUsage` 특성 특성을 두 번 이상 적용할 수 있는지 여부를 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="fb3fe-104">The `AttributeUsage` attribute determines whether an attribute can be applied more than once.</span></span>  
  
 <span data-ttu-id="fb3fe-105">**오류 ID:** BC30663</span><span class="sxs-lookup"><span data-stu-id="fb3fe-105">**Error ID:** BC30663</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="fb3fe-106">이 오류를 해결하려면</span><span class="sxs-lookup"><span data-stu-id="fb3fe-106">To correct this error</span></span>  
  
1.  <span data-ttu-id="fb3fe-107">특성은 한 번만 적용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fb3fe-107">Make sure the attribute is only applied once.</span></span>  
  
2.  <span data-ttu-id="fb3fe-108">개발한 사용자 지정 특성을 사용 하는 경우 변경해 보십시오 해당 `AttributeUsage` 다음 예제에서와 마찬가지로 여러 특성 사용을 허용 하는 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="fb3fe-108">If you are using custom attributes you developed, consider changing their `AttributeUsage` attribute to allow multiple attribute usage, as with the following example.</span></span>  
  
```vb  
<AttributeUsage(AllowMultiple := True)>  
```  
  
## <a name="see-also"></a><span data-ttu-id="fb3fe-109">참고자료</span><span class="sxs-lookup"><span data-stu-id="fb3fe-109">See also</span></span>
- <xref:System.AttributeUsageAttribute>
- [<span data-ttu-id="fb3fe-110">사용자 지정 특성 만들기</span><span class="sxs-lookup"><span data-stu-id="fb3fe-110">Creating Custom Attributes</span></span>](../../../visual-basic/programming-guide/concepts/attributes/creating-custom-attributes.md)
- [<span data-ttu-id="fb3fe-111">AttributeUsage</span><span class="sxs-lookup"><span data-stu-id="fb3fe-111">AttributeUsage</span></span>](../../../visual-basic/programming-guide/concepts/attributes/attributeusage.md)
