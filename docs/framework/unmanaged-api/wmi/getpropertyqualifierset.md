---
title: GetPropertyQualifierSet 함수 (관리 되지 않는 API 참조)
description: GetPropertyQualifierSet 함수 속성에 설정할 한정자를 검색 합니다.
ms.date: 11/06/2017
api_name:
- GetPropertyQualifierSet
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- GetPropertyQualifierSet
helpviewer_keywords:
- GetPropertyQualifierSet function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: fcddca2e435a3f5bf4b8d083784613254d9801a4
ms.sourcegitcommit: a885cc8c3e444ca6471348893d5373c6e9e49a47
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/06/2018
ms.locfileid: "43880317"
---
# <a name="getpropertyqualifierset-function"></a><span data-ttu-id="04b96-103">GetPropertyQualifierSet 함수</span><span class="sxs-lookup"><span data-stu-id="04b96-103">GetPropertyQualifierSet function</span></span>
<span data-ttu-id="04b96-104">특정 속성에 대한 한정자 집합을 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="04b96-104">Retrieves the qualifier set for a particular property.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
    
## <a name="syntax"></a><span data-ttu-id="04b96-105">구문</span><span class="sxs-lookup"><span data-stu-id="04b96-105">Syntax</span></span>  
  
```  
HRESULT GetPropertyQualifierSet (
   [in] int                 vFunc, 
   [in] IWbemClassObject*   ptr, 
   [in] LPCWSTR             wszProperty,
   [out] IWbemQualifierSet  **ppQualSet
); 
```  

## <a name="parameters"></a><span data-ttu-id="04b96-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="04b96-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="04b96-107">[in] 이 매개 변수 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="04b96-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="04b96-108">[in] 에 대 한 포인터를 [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) 인스턴스.</span><span class="sxs-lookup"><span data-stu-id="04b96-108">[in] A pointer to an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instance.</span></span>

`wszMethod`  
<span data-ttu-id="04b96-109">[in] 속성 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="04b96-109">[in] The property  name.</span></span> <span data-ttu-id="04b96-110">`wszProperty` 유효한 가리켜야 `LPCWSTR`합니다.</span><span class="sxs-lookup"><span data-stu-id="04b96-110">`wszProperty` must point to a valid `LPCWSTR`.</span></span> 

`ppQualSet`  
<span data-ttu-id="04b96-111">[out] 속성의 한정자에 대 한 액세스를 허용 하는 인터페이스 포인터를 받습니다.</span><span class="sxs-lookup"><span data-stu-id="04b96-111">[out] Receives the interface pointer that allows access to the qualifiers of the property.</span></span> <span data-ttu-id="04b96-112">`ppQualSet`가 `null`이 될 수 없는 경우</span><span class="sxs-lookup"><span data-stu-id="04b96-112">`ppQualSet` cannot be `null`.</span></span> <span data-ttu-id="04b96-113">오류가 발생 하는 경우 새 개체를 반환 되지 않으면 및 포인터를 가리키도록 설정 되어 `null`입니다.</span><span class="sxs-lookup"><span data-stu-id="04b96-113">If an error occurs, a new object is not returned, and the pointer is set to point to `null`.</span></span> 

## <a name="return-value"></a><span data-ttu-id="04b96-114">반환 값</span><span class="sxs-lookup"><span data-stu-id="04b96-114">Return value</span></span>

<span data-ttu-id="04b96-115">이 함수에 의해 반환 되는 다음 값에 정의 된 합니다 *WbemCli.h* 헤더 파일에서 정의할 수 상수로 코드:</span><span class="sxs-lookup"><span data-stu-id="04b96-115">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="04b96-116">상수</span><span class="sxs-lookup"><span data-stu-id="04b96-116">Constant</span></span>  |<span data-ttu-id="04b96-117">값</span><span class="sxs-lookup"><span data-stu-id="04b96-117">Value</span></span>  |<span data-ttu-id="04b96-118">설명</span><span class="sxs-lookup"><span data-stu-id="04b96-118">Description</span></span>  |
|---------|---------|---------|
|`WBEM_E_FAILED` | <span data-ttu-id="04b96-119">0x80041001</span><span class="sxs-lookup"><span data-stu-id="04b96-119">0x80041001</span></span> | <span data-ttu-id="04b96-120">일반 오류가 발생이 했습니다.</span><span class="sxs-lookup"><span data-stu-id="04b96-120">There has been a general failure.</span></span> |
| `WBEM_E_NOT_FOUND` | <span data-ttu-id="04b96-121">0x80041002</span><span class="sxs-lookup"><span data-stu-id="04b96-121">0x80041002</span></span> | <span data-ttu-id="04b96-122">지정된 된 메서드가 존재 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="04b96-122">The specified method does not exist.</span></span> |
|`WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="04b96-123">0x80041006("</span><span class="sxs-lookup"><span data-stu-id="04b96-123">0x80041006</span></span> | <span data-ttu-id="04b96-124">메모리가 부족 하 여 작업을 완료할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="04b96-124">Not enough memory is available to complete the operation.</span></span> |
|`WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="04b96-125">'(0x80041008</span><span class="sxs-lookup"><span data-stu-id="04b96-125">0x80041008</span></span> | <span data-ttu-id="04b96-126">매개 변수는 `null`합니다.</span><span class="sxs-lookup"><span data-stu-id="04b96-126">A parameter is `null`.</span></span> |
| `WBEM_E_SYSTEM_PROPERTY` | <span data-ttu-id="04b96-127">0x80041030</span><span class="sxs-lookup"><span data-stu-id="04b96-127">0x80041030</span></span> | <span data-ttu-id="04b96-128">함수는 시스템 속성의 한정자를 가져오려고 시도 합니다.</span><span class="sxs-lookup"><span data-stu-id="04b96-128">The function attempts to get qualifiers of a system property.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="04b96-129">0</span><span class="sxs-lookup"><span data-stu-id="04b96-129">0</span></span> | <span data-ttu-id="04b96-130">함수 호출이 성공 했습니다.</span><span class="sxs-lookup"><span data-stu-id="04b96-130">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="04b96-131">설명</span><span class="sxs-lookup"><span data-stu-id="04b96-131">Remarks</span></span>

<span data-ttu-id="04b96-132">이 함수에 대 한 호출을 래핑하는 [IWbemClassObject::GetPropertyQualifierSet](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-getpropertyqualifierset) 메서드.</span><span class="sxs-lookup"><span data-stu-id="04b96-132">This function wraps a call to the [IWbemClassObject::GetPropertyQualifierSet](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-getpropertyqualifierset) method.</span></span> 

<span data-ttu-id="04b96-133">이 함수에 대 한 호출에는 현재 개체가 CIM 클래스 정의 하는 경우에 지원 됩니다.</span><span class="sxs-lookup"><span data-stu-id="04b96-133">A call to this function is supported only if the current object is a CIM class definition.</span></span> <span data-ttu-id="04b96-134">사용할 수 없는 메서드 조작 [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) CIM 인스턴스를 가리키는 ponters 합니다.</span><span class="sxs-lookup"><span data-stu-id="04b96-134">Method manipulation is not available for [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) ponters that point to CIM instances.</span></span>

<span data-ttu-id="04b96-135">각 메서드는 자체 한정자가 있을 수 있으므로 합니다 [IWbemQualifierSet 포인터](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset) 호출자가 추가, 편집 또는 이러한 한정자를 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="04b96-135">Because each method may have its own qualifiers, the [IWbemQualifierSet pointer](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset) lets the caller add, edit, or delete these qualifiers.</span></span>

<span data-ttu-id="04b96-136">함수를 반환 하는 시스템 속성 한정자가 있으므로 `WBEM_E_SYSTEM_PROPERTY` 가져오려고 시도 하는 경우는 [IWbemQualifierSet](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset) 시스템 속성에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="04b96-136">Because system properties have no qualifiers, the function returns `WBEM_E_SYSTEM_PROPERTY` if you attempt to obtain a [IWbemQualifierSet](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset) pointer for a system property.</span></span>

## <a name="requirements"></a><span data-ttu-id="04b96-137">요구 사항</span><span class="sxs-lookup"><span data-stu-id="04b96-137">Requirements</span></span>  
<span data-ttu-id="04b96-138">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="04b96-138">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="04b96-139">**헤더:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="04b96-139">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="04b96-140">**.NET Framework 버전:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="04b96-140">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="04b96-141">참고자료</span><span class="sxs-lookup"><span data-stu-id="04b96-141">See also</span></span>  
[<span data-ttu-id="04b96-142">WMI 및 성능 카운터 (관리 되지 않는 API 참조)</span><span class="sxs-lookup"><span data-stu-id="04b96-142">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
