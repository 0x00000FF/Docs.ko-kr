---
title: "'<procedurename>' 함수의 반환 형식이 CLS 규격이 아닙니다."
ms.date: 07/20/2015
f1_keywords:
- bc40027
- vbc40027
helpviewer_keywords:
- BC40027
ms.assetid: 33c088c7-48e7-400c-920e-6d8967e1f3fc
ms.openlocfilehash: 5e746981d10ba8e662aebf86f67f08856ba37199
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/30/2019
ms.locfileid: "55260517"
---
# <a name="return-type-of-function-procedurename-is-not-cls-compliant"></a><span data-ttu-id="db734-102">함수의 반환 형식이 '\<procedurename >' CLS 규격이 아님</span><span class="sxs-lookup"><span data-stu-id="db734-102">Return type of function '\<procedurename>' is not CLS-compliant</span></span>
<span data-ttu-id="db734-103">A `Function` 절차로 표시 됩니다 `<CLSCompliant(True)>` 로 표시 된 형식을 반환 하지만 `<CLSCompliant(False)>`는 표시 되지 않았거나, 비규격 형식 이므로 적합 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="db734-103">A `Function` procedure is marked as `<CLSCompliant(True)>` but returns a type that is marked as `<CLSCompliant(False)>`, is not marked, or does not qualify because it is a noncompliant type.</span></span>  
  
 <span data-ttu-id="db734-104">프로시저가 [언어 독립성 및 언어 독립적 구성 요소](../../../standard/language-independence-and-language-independent-components.md)(CLS)와 호환되려면 CLS 규격 형식만 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="db734-104">For a procedure to be compliant with the [Language Independence and Language-Independent Components](../../../standard/language-independence-and-language-independent-components.md) (CLS), it must use only CLS-compliant types.</span></span> <span data-ttu-id="db734-105">이는 매개 변수 형식, 반환 형식 및 모든 로컬 변수 형식에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="db734-105">This applies to the types of the parameters, the return type, and the types of all its local variables.</span></span>  
  
 <span data-ttu-id="db734-106">다음 Visual Basic 데이터 형식은 CLS 규격이 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="db734-106">The following Visual Basic data types are not CLS-compliant:</span></span>  
  
-   [<span data-ttu-id="db734-107">SByte 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="db734-107">SByte Data Type</span></span>](../../../visual-basic/language-reference/data-types/sbyte-data-type.md)  
  
-   [<span data-ttu-id="db734-108">UInteger 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="db734-108">UInteger Data Type</span></span>](../../../visual-basic/language-reference/data-types/uinteger-data-type.md)  
  
-   [<span data-ttu-id="db734-109">ULong 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="db734-109">ULong Data Type</span></span>](../../../visual-basic/language-reference/data-types/ulong-data-type.md)  
  
-   [<span data-ttu-id="db734-110">UShort 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="db734-110">UShort Data Type</span></span>](../../../visual-basic/language-reference/data-types/ushort-data-type.md)  
  
 <span data-ttu-id="db734-111"><xref:System.CLSCompliantAttribute>를 프로그래밍 요소에 적용하는 경우 특성의 `isCompliant` 매개 변수를 `True` 또는 `False`로 설정하여 준수 여부를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="db734-111">When you apply the <xref:System.CLSCompliantAttribute> to a programming element, you set the attribute's `isCompliant` parameter to either `True` or `False` to indicate compliance or noncompliance.</span></span> <span data-ttu-id="db734-112">이 매개 변수에는 기본값이 없으며 값을 제공해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="db734-112">There is no default for this parameter, and you must supply a value.</span></span>  
  
 <span data-ttu-id="db734-113">요소에 <xref:System.CLSCompliantAttribute> 를 적용하지 않으면 비규격인 것으로 간주됩니다.</span><span class="sxs-lookup"><span data-stu-id="db734-113">If you do not apply the <xref:System.CLSCompliantAttribute> to an element, it is considered to be noncompliant.</span></span>  
  
 <span data-ttu-id="db734-114">이 메시지는 기본적으로 경고입니다.</span><span class="sxs-lookup"><span data-stu-id="db734-114">By default, this message is a warning.</span></span> <span data-ttu-id="db734-115">경고를 숨기거나 오류로 처리하는 방법에 대한 자세한 내용은 [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="db734-115">For information on hiding warnings or treating warnings as errors, see [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span></span>  
  
 <span data-ttu-id="db734-116">**오류 ID:** BC40027</span><span class="sxs-lookup"><span data-stu-id="db734-116">**Error ID:** BC40027</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="db734-117">이 오류를 해결하려면</span><span class="sxs-lookup"><span data-stu-id="db734-117">To correct this error</span></span>  
  
-   <span data-ttu-id="db734-118">경우는 `Function` 프로시저가 특정 형식을 반환 해야, 제거는 <xref:System.CLSCompliantAttribute>합니다.</span><span class="sxs-lookup"><span data-stu-id="db734-118">If the `Function` procedure must return this particular type, remove the <xref:System.CLSCompliantAttribute>.</span></span> <span data-ttu-id="db734-119">프로시저는 CLS 규격일 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="db734-119">The procedure cannot be CLS-compliant.</span></span>  
  
-   <span data-ttu-id="db734-120">경우는 `Function` 프로시저 CLS 규격 이어야, 가장 가까운 CLS 규격 형식 반환 형식을 변경 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="db734-120">If the `Function` procedure must be CLS-compliant, change the return type to the closest CLS-compliant type.</span></span> <span data-ttu-id="db734-121">예를 들어 2,147,483,647을 초과하는 값 범위가 필요하지 않은 경우 `UInteger` 대신 `Integer` 을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="db734-121">For example, in place of `UInteger` you might be able to use `Integer` if you do not need the value range above 2,147,483,647.</span></span> <span data-ttu-id="db734-122">확장된 범위가 필요한 경우 `UInteger` 를 `Long`으로 바꿀 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="db734-122">If you do need the extended range, you can replace `UInteger` with `Long`.</span></span>  
  
-   <span data-ttu-id="db734-123">자동화 또는 COM 개체와 상호 작용하는 경우 일부 형식의 데이터 너비가 [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)]와 다르다는 점을 염두에 두어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="db734-123">If you are interfacing with Automation or COM objects, keep in mind that some types have different data widths than in the [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)].</span></span> <span data-ttu-id="db734-124">예를 들어 `int`는 다른 환경에서 16비트인 경우가 많습니다.</span><span class="sxs-lookup"><span data-stu-id="db734-124">For example, `int` is often 16 bits in other environments.</span></span> <span data-ttu-id="db734-125">이러한 구성 요소는 16 비트 정수를 반환 하는 경우로 선언 `Short` 대신 `Integer` 관리 되는 Visual Basic 코드에서.</span><span class="sxs-lookup"><span data-stu-id="db734-125">If you are returning a 16-bit integer to such a component, declare it as `Short` instead of `Integer` in your managed Visual Basic code.</span></span>