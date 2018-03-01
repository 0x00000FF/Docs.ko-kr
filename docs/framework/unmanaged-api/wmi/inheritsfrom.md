---
title: "InheritsFrom 함수 (관리 되지 않는 API 참조)"
description: "InheritsFrom 함수 클래스 또는 인스턴스는 특정 부모 클래스 로부터 파생 있는지 여부를 결정 합니다."
ms.date: 11/06/2017
ms.prod: .net-framework
ms.technology:
- dotnet-clr
ms.topic: reference
api_name:
- InheritsFrom
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- InheritsFrom
helpviewer_keywords:
- InheritsFrom function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 0dce964829399e6761152a8ff424671b47cc6eb3
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="inheritsfrom-function"></a><span data-ttu-id="9f774-103">InheritsFrom 함수</span><span class="sxs-lookup"><span data-stu-id="9f774-103">InheritsFrom function</span></span>
<span data-ttu-id="9f774-104">현재 클래스 또는 인스턴스를 지정 된 부모 클래스에서 파생 있는지 여부를 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="9f774-104">Determines whether the current class or instance derives from a specified parent class.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
    
## <a name="syntax"></a><span data-ttu-id="9f774-105">구문</span><span class="sxs-lookup"><span data-stu-id="9f774-105">Syntax</span></span>  
  
```
HRESULT InheritsFrom (
   [in] int               vFunc, 
   [in] IWbemClassObject* ptr, 
   [in] LPCWSTR           wszAncestor 
); 
```  

## <a name="parameters"></a><span data-ttu-id="9f774-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="9f774-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="9f774-107">[in] 이 매개 변수를 사용 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9f774-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="9f774-108">[in] 에 대 한 포인터는 [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) 인스턴스.</span><span class="sxs-lookup"><span data-stu-id="9f774-108">[in] A pointer to an [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) instance.</span></span>

`wszAncestor`  
<span data-ttu-id="9f774-109">[in] 클래스의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="9f774-109">[in] The name of the class.</span></span> <span data-ttu-id="9f774-110">`wszAncestor`유효한 가리켜야 `LPCWSTR`합니다.</span><span class="sxs-lookup"><span data-stu-id="9f774-110">`wszAncestor` must point to a valid `LPCWSTR`.</span></span>

## <a name="return-value"></a><span data-ttu-id="9f774-111">반환 값</span><span class="sxs-lookup"><span data-stu-id="9f774-111">Return value</span></span>

<span data-ttu-id="9f774-112">이 함수에서 반환 되는 다음 값에 정의 된는 *WbemCli.h* 헤더 파일 또는 있습니다를 정의할 수 상수로 코드:</span><span class="sxs-lookup"><span data-stu-id="9f774-112">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="9f774-113">상수</span><span class="sxs-lookup"><span data-stu-id="9f774-113">Constant</span></span>  |<span data-ttu-id="9f774-114">값</span><span class="sxs-lookup"><span data-stu-id="9f774-114">Value</span></span>  |<span data-ttu-id="9f774-115">설명</span><span class="sxs-lookup"><span data-stu-id="9f774-115">Description</span></span>  |
|---------|---------|---------|
| `WBEM_S_NO_ERROR` | <span data-ttu-id="9f774-116">0</span><span class="sxs-lookup"><span data-stu-id="9f774-116">0</span></span> | <span data-ttu-id="9f774-117">현재 개체에서 상속 `wszAncestor`합니다.</span><span class="sxs-lookup"><span data-stu-id="9f774-117">The current object inherits from `wszAncestor`.</span></span>  |
| `WBEM_S_FALSE` | <span data-ttu-id="9f774-118">1</span><span class="sxs-lookup"><span data-stu-id="9f774-118">1</span></span> | <span data-ttu-id="9f774-119">현재 개체에서 상속 되지 않는 `wszAncestor`합니다.</span><span class="sxs-lookup"><span data-stu-id="9f774-119">The current object does not inherit from `wszAncestor`.</span></span> |
|`WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="9f774-120">0x80041008</span><span class="sxs-lookup"><span data-stu-id="9f774-120">0x80041008</span></span> | <span data-ttu-id="9f774-121">`wszAncestor`가 `null`인 경우</span><span class="sxs-lookup"><span data-stu-id="9f774-121">`wszAncestor` is `null`.</span></span> |
  
## <a name="remarks"></a><span data-ttu-id="9f774-122">설명</span><span class="sxs-lookup"><span data-stu-id="9f774-122">Remarks</span></span>

<span data-ttu-id="9f774-123">이 함수에 대 한 호출을 래핑하는 [IWbemClassObject::InheritsFrom](https://msdn.microsoft.com/library/aa391452(v=vs.85).aspx) 메서드.</span><span class="sxs-lookup"><span data-stu-id="9f774-123">This function wraps a call to the [IWbemClassObject::InheritsFrom](https://msdn.microsoft.com/library/aa391452(v=vs.85).aspx) method.</span></span>

## <a name="requirements"></a><span data-ttu-id="9f774-124">요구 사항</span><span class="sxs-lookup"><span data-stu-id="9f774-124">Requirements</span></span>  
 <span data-ttu-id="9f774-125">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="9f774-125">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9f774-126">**헤더:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="9f774-126">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="9f774-127">**.NET framework 버전:**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="9f774-127">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9f774-128">참고 항목</span><span class="sxs-lookup"><span data-stu-id="9f774-128">See also</span></span>  
[<span data-ttu-id="9f774-129">WMI 및 성능 카운터 (관리 되지 않는 API 참조)</span><span class="sxs-lookup"><span data-stu-id="9f774-129">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
