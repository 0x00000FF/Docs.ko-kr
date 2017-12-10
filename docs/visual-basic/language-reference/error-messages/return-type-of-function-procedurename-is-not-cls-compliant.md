---
title: "함수 &#39;의 반환 형식 &lt;procedurename&gt;&#39; CLS 규격이 아닙니다"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- bc40027
- vbc40027
helpviewer_keywords: BC40027
ms.assetid: 33c088c7-48e7-400c-920e-6d8967e1f3fc
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 14adc6f8f2d89713bd681a1d55e4801b930cf642
ms.sourcegitcommit: 685143b62385500f59bc36274b8adb191f573a16
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/09/2017
---
# <a name="return-type-of-function-39ltprocedurenamegt39-is-not-cls-compliant"></a><span data-ttu-id="16f3c-102">함수 &#39;의 반환 형식 &lt;procedurename&gt;&#39; CLS 규격이 아닙니다</span><span class="sxs-lookup"><span data-stu-id="16f3c-102">Return type of function &#39;&lt;procedurename&gt;&#39; is not CLS-compliant</span></span>
<span data-ttu-id="16f3c-103">A `Function` 절차로 표시 되어 `<CLSCompliant(True)>` 로 표시 된 형식을 반환 하지만 `<CLSCompliant(False)>`은 표시 되지 않았거나, 비규격 형식 이므로 사용할 수 없는 합니다.</span><span class="sxs-lookup"><span data-stu-id="16f3c-103">A `Function` procedure is marked as `<CLSCompliant(True)>` but returns a type that is marked as `<CLSCompliant(False)>`, is not marked, or does not qualify because it is a noncompliant type.</span></span>  
  
 <span data-ttu-id="16f3c-104">프로시저가 [언어 독립성 및 언어 독립적 구성 요소](../../../../docs/standard/language-independence-and-language-independent-components.md)(CLS)와 호환되려면 CLS 규격 형식만 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="16f3c-104">For a procedure to be compliant with the [Language Independence and Language-Independent Components](../../../../docs/standard/language-independence-and-language-independent-components.md) (CLS), it must use only CLS-compliant types.</span></span> <span data-ttu-id="16f3c-105">이는 매개 변수 형식, 반환 형식 및 모든 로컬 변수 형식에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="16f3c-105">This applies to the types of the parameters, the return type, and the types of all its local variables.</span></span>  
  
 <span data-ttu-id="16f3c-106">다음 [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] 데이터 형식은 CLS 규격이 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="16f3c-106">The following [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] data types are not CLS-compliant:</span></span>  
  
-   [<span data-ttu-id="16f3c-107">SByte 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="16f3c-107">SByte Data Type</span></span>](../../../visual-basic/language-reference/data-types/sbyte-data-type.md)  
  
-   [<span data-ttu-id="16f3c-108">UInteger 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="16f3c-108">UInteger Data Type</span></span>](../../../visual-basic/language-reference/data-types/uinteger-data-type.md)  
  
-   [<span data-ttu-id="16f3c-109">ULong 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="16f3c-109">ULong Data Type</span></span>](../../../visual-basic/language-reference/data-types/ulong-data-type.md)  
  
-   [<span data-ttu-id="16f3c-110">UShort 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="16f3c-110">UShort Data Type</span></span>](../../../visual-basic/language-reference/data-types/ushort-data-type.md)  
  
 <span data-ttu-id="16f3c-111"><xref:System.CLSCompliantAttribute> 를 프로그래밍 요소에 적용하는 경우 특성의 `isCompliant` 매개 변수를 `True` 또는 `False` 로 설정하여 준수 여부를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="16f3c-111">When you apply the <xref:System.CLSCompliantAttribute> to a programming element, you set the attribute's `isCompliant` parameter to either `True` or `False` to indicate compliance or noncompliance.</span></span> <span data-ttu-id="16f3c-112">이 매개 변수에는 기본값이 없으며 값을 제공해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="16f3c-112">There is no default for this parameter, and you must supply a value.</span></span>  
  
 <span data-ttu-id="16f3c-113">요소에 <xref:System.CLSCompliantAttribute> 를 적용하지 않으면 비규격인 것으로 간주됩니다.</span><span class="sxs-lookup"><span data-stu-id="16f3c-113">If you do not apply the <xref:System.CLSCompliantAttribute> to an element, it is considered to be noncompliant.</span></span>  
  
 <span data-ttu-id="16f3c-114">이 메시지는 기본적으로 경고입니다.</span><span class="sxs-lookup"><span data-stu-id="16f3c-114">By default, this message is a warning.</span></span> <span data-ttu-id="16f3c-115">경고를 숨기거나 오류로 처리하는 방법에 대한 자세한 내용은 [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="16f3c-115">For information on hiding warnings or treating warnings as errors, see [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span></span>  
  
 <span data-ttu-id="16f3c-116">**오류 ID:** BC40027</span><span class="sxs-lookup"><span data-stu-id="16f3c-116">**Error ID:** BC40027</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="16f3c-117">이 오류를 해결하려면</span><span class="sxs-lookup"><span data-stu-id="16f3c-117">To correct this error</span></span>  
  
-   <span data-ttu-id="16f3c-118">경우는 `Function` 프로시저 해야이 특정 형식 반환, 제거는 <xref:System.CLSCompliantAttribute>합니다.</span><span class="sxs-lookup"><span data-stu-id="16f3c-118">If the `Function` procedure must return this particular type, remove the <xref:System.CLSCompliantAttribute>.</span></span> <span data-ttu-id="16f3c-119">프로시저는 CLS 규격일 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="16f3c-119">The procedure cannot be CLS-compliant.</span></span>  
  
-   <span data-ttu-id="16f3c-120">경우는 `Function` 프로시저 CLS 규격을 준수 해야, 가장 가까운 CLS 규격 형식으로 반환 형식을 변경 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="16f3c-120">If the `Function` procedure must be CLS-compliant, change the return type to the closest CLS-compliant type.</span></span> <span data-ttu-id="16f3c-121">예를 들어 2,147,483,647을 초과하는 값 범위가 필요하지 않은 경우 `UInteger` 대신 `Integer` 을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="16f3c-121">For example, in place of `UInteger` you might be able to use `Integer` if you do not need the value range above 2,147,483,647.</span></span> <span data-ttu-id="16f3c-122">확장된 범위가 필요한 경우 `UInteger` 를 `Long`으로 바꿀 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="16f3c-122">If you do need the extended range, you can replace `UInteger` with `Long`.</span></span>  
  
-   <span data-ttu-id="16f3c-123">자동화 또는 COM 개체와 상호 작용하는 경우 일부 형식의 데이터 너비가 [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)]와 다르다는 점을 염두에 두어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="16f3c-123">If you are interfacing with Automation or COM objects, keep in mind that some types have different data widths than in the [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)].</span></span> <span data-ttu-id="16f3c-124">예를 들어 `int`는 다른 환경에서 16비트인 경우가 많습니다.</span><span class="sxs-lookup"><span data-stu-id="16f3c-124">For example, `int` is often 16 bits in other environments.</span></span> <span data-ttu-id="16f3c-125">이러한 구성 요소에는 16 비트 정수를 반환 하는 경우로 선언 `Short` 대신 `Integer` 관리 되는 [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="16f3c-125">If you are returning a 16-bit integer to such a component, declare it as `Short` instead of `Integer` in your managed [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] code.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="16f3c-126">참고 항목</span><span class="sxs-lookup"><span data-stu-id="16f3c-126">See Also</span></span>  
 [<span data-ttu-id="16f3c-127">\<통해 PAVE > CLS 규격 코드 작성</span><span class="sxs-lookup"><span data-stu-id="16f3c-127">\<PAVE OVER> Writing CLS-Compliant Code</span></span>](http://msdn.microsoft.com/en-us/4c705105-69a2-4e5e-b24e-0633bc32c7f3)
