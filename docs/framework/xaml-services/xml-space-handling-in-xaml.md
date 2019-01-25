---
title: XAML의 xml:space 처리
ms.date: 03/30/2017
helpviewer_keywords:
- XAML [XAML Services], xml:space attribute
- XAML [XAML Services], white-space processing
- xml:space attribute [XAML Services]
- white-space processing [XAML Services]
ms.assetid: 5e1814f0-5b30-43d5-8c88-dede335a89d7
ms.openlocfilehash: a7c3775f2e49a80eabc61f24d086a94fcadfd574
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54617579"
---
# <a name="xmlspace-handling-in-xaml"></a><span data-ttu-id="6e976-102">XAML의 xml:space 처리</span><span class="sxs-lookup"><span data-stu-id="6e976-102">xml:space Handling in XAML</span></span>
<span data-ttu-id="6e976-103">`xml:space` 특성은 개체 요소 내에서 중요 한 공백 처리 동작을 선언 하는 XML로 정의 된 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="6e976-103">The `xml:space` attribute is an XML-defined attribute that declares the significant white-space processing behavior within an object element.</span></span> <span data-ttu-id="6e976-104">이 동작 요소에 포함 된 모든 콘텐츠 (내부 텍스트)와 관련이 있는 `xml:space` 선언 되 고도 범위가 정해 집니다 자식 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="6e976-104">This behavior is relevant for all content (inner text) contained within the element where `xml:space` is declared, and also scopes to child elements.</span></span>  
  
## <a name="xaml-attribute-usage"></a><span data-ttu-id="6e976-105">XAML 특성 사용</span><span class="sxs-lookup"><span data-stu-id="6e976-105">XAML Attribute Usage</span></span>  
  
```xaml  
<object xml:space="preserve" />  
```  
  
 <span data-ttu-id="6e976-106">\- 또는 -</span><span class="sxs-lookup"><span data-stu-id="6e976-106">\- or -</span></span>  
  
```xaml  
<object xml:space="default" />  
```  
  
## <a name="remarks"></a><span data-ttu-id="6e976-107">설명</span><span class="sxs-lookup"><span data-stu-id="6e976-107">Remarks</span></span>  
 <span data-ttu-id="6e976-108">에 대 한 정의 `xml:space` 가능한 두 값을 포함 하 여 XAML의 특성에서 파생 된 `xml:space` XML에 대 한 W3C 사양 "특수 특성"으로 정의 된 대로 합니다.</span><span class="sxs-lookup"><span data-stu-id="6e976-108">The definition for the `xml:space` attribute in XAML including its two possible values is derived from `xml:space` as defined as a "special attribute" by W3C specifications for XML.</span></span>  
  
 <span data-ttu-id="6e976-109">기본값은 `xml:space` 특성은 리터럴 값 `"default"`합니다.</span><span class="sxs-lookup"><span data-stu-id="6e976-109">The default value of the `xml:space` attribute is the literal value `"default"`.</span></span> <span data-ttu-id="6e976-110">값에 대 한 `"default"`, 또는 `xml:space` 항목에 정의 된 대로 중요 한 공백이 구문 분석의 동작은 기본 처리를 전혀 표시 되지 않습니다 [공백 XAML 처리](../../../docs/framework/xaml-services/whitespace-processing-in-xaml.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="6e976-110">For the value `"default"`, or if `xml:space` is not indicated at all, the behavior of significant white-space parsing is the default handling, as defined in the topic [White-space processing in XAML](../../../docs/framework/xaml-services/whitespace-processing-in-xaml.md).</span></span>  
  
 <span data-ttu-id="6e976-111">개체 요소 콘텐츠 내에서 공백을 유지 하려면 지정 `xml:space="preserve"` 개체 요소에 해당 합니다.</span><span class="sxs-lookup"><span data-stu-id="6e976-111">To preserve white space within object element content, specify `xml:space="preserve"` on that object element.</span></span>  
  
 <span data-ttu-id="6e976-112">대부분의 해석 된 `xml:space` 특성 효과 및 특성은 자식 요소에 범위가 지정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6e976-112">Under most interpretations, the `xml:space` attribute effects and the value of the attribute are scoped to child elements.</span></span>  
  
 <span data-ttu-id="6e976-113">설명은 공백을 XAML 처리에 대 한 참조 [공백 XAML 처리](../../../docs/framework/xaml-services/whitespace-processing-in-xaml.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="6e976-113">For a complete discussion of white-space processing in XAML, see [White-space processing in XAML](../../../docs/framework/xaml-services/whitespace-processing-in-xaml.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6e976-114">참고자료</span><span class="sxs-lookup"><span data-stu-id="6e976-114">See also</span></span>
- [<span data-ttu-id="6e976-115">공백에서 XAML 처리</span><span class="sxs-lookup"><span data-stu-id="6e976-115">White-space processing in XAML</span></span>](../../../docs/framework/xaml-services/whitespace-processing-in-xaml.md)
- [<span data-ttu-id="6e976-116">XAML 개요(WPF)</span><span class="sxs-lookup"><span data-stu-id="6e976-116">XAML Overview (WPF)</span></span>](../../../docs/framework/wpf/advanced/xaml-overview-wpf.md)
