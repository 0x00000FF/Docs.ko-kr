---
title: Get 함수 (관리 되지 않는 API 참조)
description: Get 함수는 지정된 된 속성 값을 검색합니다.
ms.date: 11/06/2017
api_name:
- Get
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- Get
helpviewer_keywords:
- Get function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: cd85ac8b98d8613924a4acd73ac74a69f3d9b41d
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54535348"
---
# <a name="get-function"></a><span data-ttu-id="4929c-103">Get 함수</span><span class="sxs-lookup"><span data-stu-id="4929c-103">Get function</span></span>
<span data-ttu-id="4929c-104">존재 하는 경우 지정된 된 속성 값을 검색 합니다.</span><span class="sxs-lookup"><span data-stu-id="4929c-104">Retrieves the specified property value if it exists.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
    
## <a name="syntax"></a><span data-ttu-id="4929c-105">구문</span><span class="sxs-lookup"><span data-stu-id="4929c-105">Syntax</span></span>  
  
```  
HRESULT Get (
   [in] int               vFunc, 
   [in] IWbemClassObject* ptr, 
   [in] LPCWSTR           wszName,
   [in] LONG              lFlags,
   [out] VARIANT*         pVal,
   [out] CIMTYPE*         pvtType,
   [out] LONG*            plFlavor
); 
```  

## <a name="parameters"></a><span data-ttu-id="4929c-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="4929c-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="4929c-107">[in] 이 매개 변수 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4929c-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="4929c-108">[in] 에 대 한 포인터를 [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) 인스턴스.</span><span class="sxs-lookup"><span data-stu-id="4929c-108">[in] A pointer to an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instance.</span></span>

`wszName`  
<span data-ttu-id="4929c-109">[in] 속성의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="4929c-109">[in] The name of the property.</span></span>

<span data-ttu-id="4929c-110">`lFlags` [in] 예약 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4929c-110">`lFlags` [in] Reserved.</span></span> <span data-ttu-id="4929c-111">이 매개 변수는 0 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4929c-111">This parameter must be 0.</span></span>

<span data-ttu-id="4929c-112">`pVal` [out] 함수가 성공적으로 반환 하는 경우의 값이 포함 된 `wszName` 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="4929c-112">`pVal` [out] If the function returns successfully, contains the value of the `wszName` property.</span></span> <span data-ttu-id="4929c-113">`pval` 인수는 올바른 형식 및 한정자의 값에 할당 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4929c-113">The `pval` argument is assigned the correct type and value for the qualifier.</span></span>

<span data-ttu-id="4929c-114">`pvtType` [out] 함수가 성공적으로 반환 하는 경우 포함 된 [CIM 형식 상수](/windows/desktop/api/wbemcli/ne-wbemcli-tag_cimtype_enumeration) 속성 형식을 나타내는입니다.</span><span class="sxs-lookup"><span data-stu-id="4929c-114">`pvtType` [out] If the function returns successfully, contains a [CIM-type constant](/windows/desktop/api/wbemcli/ne-wbemcli-tag_cimtype_enumeration) that indicates the property type.</span></span> <span data-ttu-id="4929c-115">해당 값을 수도 있습니다 `null`합니다.</span><span class="sxs-lookup"><span data-stu-id="4929c-115">Its value can also be `null`.</span></span> 

<span data-ttu-id="4929c-116">`plFlavor` [out] 함수가 성공적으로 반환 하는 경우 속성의 원본에 대 한 정보를 받습니다.</span><span class="sxs-lookup"><span data-stu-id="4929c-116">`plFlavor` [out] If the function returns successfully, receives information about the origin of the property.</span></span> <span data-ttu-id="4929c-117">해당 값이 될 수 있습니다 `null`, 또는에 정의 된 다음 WBEM_FLAVOR_TYPE 상수 중 하나는 *WbemCli.h* 헤더 파일:</span><span class="sxs-lookup"><span data-stu-id="4929c-117">Its value can be `null`, or one of the following WBEM_FLAVOR_TYPE constants defined in the *WbemCli.h* header file:</span></span> 

|<span data-ttu-id="4929c-118">상수</span><span class="sxs-lookup"><span data-stu-id="4929c-118">Constant</span></span>  |<span data-ttu-id="4929c-119">값</span><span class="sxs-lookup"><span data-stu-id="4929c-119">Value</span></span>  |<span data-ttu-id="4929c-120">설명</span><span class="sxs-lookup"><span data-stu-id="4929c-120">Description</span></span>  |
|---------|---------|---------|
| `WBEM_FLAVOR_ORIGIN_SYSTEM` | <span data-ttu-id="4929c-121">0x40</span><span class="sxs-lookup"><span data-stu-id="4929c-121">0x40</span></span> | <span data-ttu-id="4929c-122">속성에는 표준 시스템 속성이입니다.</span><span class="sxs-lookup"><span data-stu-id="4929c-122">The property is a standard system property.</span></span> |
| `WBEM_FLAVOR_ORIGIN_PROPAGATED` | <span data-ttu-id="4929c-123">0x20</span><span class="sxs-lookup"><span data-stu-id="4929c-123">0x20</span></span> | <span data-ttu-id="4929c-124">클래스: 속성은 부모 클래스에서 상속 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4929c-124">For a class: The property is inherited from the parent class.</span></span> </br> <span data-ttu-id="4929c-125">인스턴스: 속성을 부모 클래스에서 상속 하는 동안에 의해 수정 되지 인스턴스.</span><span class="sxs-lookup"><span data-stu-id="4929c-125">For an instance: The property, while inherited from the parent class, has not been modified by the instance.</span></span>  |
| `WBEM_FLAVOR_ORIGIN_LOCAL` | <span data-ttu-id="4929c-126">0</span><span class="sxs-lookup"><span data-stu-id="4929c-126">0</span></span> | <span data-ttu-id="4929c-127">클래스: 속성은 파생된 클래스에 속합니다.</span><span class="sxs-lookup"><span data-stu-id="4929c-127">For a class: The property belongs to the derived class.</span></span> </br> <span data-ttu-id="4929c-128">인스턴스: 인스턴스에서; 속성이 수정 됩니다. 즉, 값이 제공 된 또는 한정자를 추가 또는 수정 합니다.</span><span class="sxs-lookup"><span data-stu-id="4929c-128">For an instance: The property is modified by the instance; that is, a value was supplied, or a qualifier was added or modified.</span></span> |

## <a name="return-value"></a><span data-ttu-id="4929c-129">반환 값</span><span class="sxs-lookup"><span data-stu-id="4929c-129">Return value</span></span>

<span data-ttu-id="4929c-130">이 함수에 의해 반환 되는 다음 값에 정의 된 합니다 *WbemCli.h* 헤더 파일에서 정의할 수 상수로 코드:</span><span class="sxs-lookup"><span data-stu-id="4929c-130">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="4929c-131">상수</span><span class="sxs-lookup"><span data-stu-id="4929c-131">Constant</span></span>  |<span data-ttu-id="4929c-132">값</span><span class="sxs-lookup"><span data-stu-id="4929c-132">Value</span></span>  |<span data-ttu-id="4929c-133">설명</span><span class="sxs-lookup"><span data-stu-id="4929c-133">Description</span></span>  |
|---------|---------|---------|
|`WBEM_E_FAILED` | <span data-ttu-id="4929c-134">0x80041001</span><span class="sxs-lookup"><span data-stu-id="4929c-134">0x80041001</span></span> | <span data-ttu-id="4929c-135">일반 오류가 발생이 했습니다.</span><span class="sxs-lookup"><span data-stu-id="4929c-135">There has been a general failure.</span></span> |
|`WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="4929c-136">0x80041008</span><span class="sxs-lookup"><span data-stu-id="4929c-136">0x80041008</span></span> | <span data-ttu-id="4929c-137">하나 이상의 매개 변수가 올바르지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4929c-137">One or more parameters are not valid.</span></span> |
|`WBEM_E_NOT_FOUND` | <span data-ttu-id="4929c-138">0x80041002</span><span class="sxs-lookup"><span data-stu-id="4929c-138">0x80041002</span></span> | <span data-ttu-id="4929c-139">지정된 된 속성을 찾을 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="4929c-139">The specified property was not found.</span></span> |
|`WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="4929c-140">0x80041006</span><span class="sxs-lookup"><span data-stu-id="4929c-140">0x80041006</span></span> | <span data-ttu-id="4929c-141">메모리가 부족하여 작업을 완료할 수 없는 경우</span><span class="sxs-lookup"><span data-stu-id="4929c-141">Not enough memory is available to complete the operation.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="4929c-142">0</span><span class="sxs-lookup"><span data-stu-id="4929c-142">0</span></span> | <span data-ttu-id="4929c-143">함수 호출이 성공 했습니다.</span><span class="sxs-lookup"><span data-stu-id="4929c-143">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="4929c-144">설명</span><span class="sxs-lookup"><span data-stu-id="4929c-144">Remarks</span></span>

<span data-ttu-id="4929c-145">이 함수에 대 한 호출을 래핑하는 [IWbemClassObject::Get](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-get) 메서드.</span><span class="sxs-lookup"><span data-stu-id="4929c-145">This function wraps a call to the [IWbemClassObject::Get](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-get) method.</span></span>

<span data-ttu-id="4929c-146">`Get` 함수 시스템 속성을 반환할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4929c-146">The `Get` function can also return system properties.</span></span>

<span data-ttu-id="4929c-147">합니다 `pVal` 인수는 올바른 형식 및 한정자 및 COM에 대 한 값에 할당 됩니다 [VariantInit](https://docs.microsoft.com/previous-versions/windows/desktop/api/oleauto/nf-oleauto-variantinit) 함수</span><span class="sxs-lookup"><span data-stu-id="4929c-147">The `pVal` argument is assigned the correct type and value for the qualifier and the COM [VariantInit](https://docs.microsoft.com/previous-versions/windows/desktop/api/oleauto/nf-oleauto-variantinit) function</span></span>

## <a name="requirements"></a><span data-ttu-id="4929c-148">요구 사항</span><span class="sxs-lookup"><span data-stu-id="4929c-148">Requirements</span></span>  
 <span data-ttu-id="4929c-149">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="4929c-149">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4929c-150">**헤더:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="4929c-150">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="4929c-151">**.NET Framework 버전:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="4929c-151">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4929c-152">참고자료</span><span class="sxs-lookup"><span data-stu-id="4929c-152">See also</span></span>
- [<span data-ttu-id="4929c-153">WMI 및 성능 카운터 (관리 되지 않는 API 참조)</span><span class="sxs-lookup"><span data-stu-id="4929c-153">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
