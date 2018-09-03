---
title: EndEnumeration 함수 (관리 되지 않는 API 참조)
description: EndEnumeration 함수 열거형을 종료합니다.
ms.date: 11/06/2017
api_name:
- EndEnumeration
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- EndEnumeration
helpviewer_keywords:
- EndEnumeration function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 33c73e58be39a7f1ffa9300947c3ee552231adab
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/02/2018
ms.locfileid: "43462313"
---
# <a name="endenumeration-function"></a><span data-ttu-id="d8f0b-103">EndEnumeration 함수</span><span class="sxs-lookup"><span data-stu-id="d8f0b-103">EndEnumeration function</span></span>
<span data-ttu-id="d8f0b-104">에 대 한 호출을 시작 하는 열거형 시퀀스를 종료 합니다 [BeginEnumeration 함수](beginenumeration.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="d8f0b-104">Terminates an enumeration sequence started with a call to the [BeginEnumeration function](beginenumeration.md).</span></span>  

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
    
## <a name="syntax"></a><span data-ttu-id="d8f0b-105">구문</span><span class="sxs-lookup"><span data-stu-id="d8f0b-105">Syntax</span></span>  
  
```  
HRESULT EndEnumeration (
   [in] int               vFunc, 
   [in] IWbemClassObject* ptr 
); 
```  

## <a name="parameters"></a><span data-ttu-id="d8f0b-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="d8f0b-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="d8f0b-107">[in] 이 매개 변수 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d8f0b-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="d8f0b-108">[in] 에 대 한 포인터를 [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) 인스턴스.</span><span class="sxs-lookup"><span data-stu-id="d8f0b-108">[in] A pointer to an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instance.</span></span>


## <a name="return-value"></a><span data-ttu-id="d8f0b-109">반환 값</span><span class="sxs-lookup"><span data-stu-id="d8f0b-109">Return value</span></span>

<span data-ttu-id="d8f0b-110">이 함수에 의해 반환 되는 다음 값에 정의 된 합니다 *WbemCli.h* 헤더 파일에서 정의할 수 상수로 코드:</span><span class="sxs-lookup"><span data-stu-id="d8f0b-110">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="d8f0b-111">상수</span><span class="sxs-lookup"><span data-stu-id="d8f0b-111">Constant</span></span>  |<span data-ttu-id="d8f0b-112">값</span><span class="sxs-lookup"><span data-stu-id="d8f0b-112">Value</span></span>  |<span data-ttu-id="d8f0b-113">설명</span><span class="sxs-lookup"><span data-stu-id="d8f0b-113">Description</span></span>  |
|---------|---------|---------|
|`WBEM_E_FAILED` | <span data-ttu-id="d8f0b-114">0x80041001</span><span class="sxs-lookup"><span data-stu-id="d8f0b-114">0x80041001</span></span> | <span data-ttu-id="d8f0b-115">일반 오류가 발생이 했습니다.</span><span class="sxs-lookup"><span data-stu-id="d8f0b-115">There has been a general failure.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="d8f0b-116">0</span><span class="sxs-lookup"><span data-stu-id="d8f0b-116">0</span></span> | <span data-ttu-id="d8f0b-117">함수 호출이 성공 했습니다.</span><span class="sxs-lookup"><span data-stu-id="d8f0b-117">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="d8f0b-118">설명</span><span class="sxs-lookup"><span data-stu-id="d8f0b-118">Remarks</span></span>

<span data-ttu-id="d8f0b-119">이 함수에 대 한 호출을 래핑하는 [IWbemClassObject::EndEnumeration](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) 메서드.</span><span class="sxs-lookup"><span data-stu-id="d8f0b-119">This function wraps a call to the [IWbemClassObject::EndEnumeration](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) method.</span></span>

<span data-ttu-id="d8f0b-120">에 대 한 호출을 `EndEnumeration` 함수는 필요 하지 않지만 열거와 연결 된 리소스를 해제 하므로 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="d8f0b-120">A call to the `EndEnumeration` function is not required, but it is recommended because it releases resources associated with the enumeration.</span></span> <span data-ttu-id="d8f0b-121">그러나 리소스의 할당이 취소 됩니다 자동으로 다음 열거를 시작 하거나 개체가 해제 될 때.</span><span class="sxs-lookup"><span data-stu-id="d8f0b-121">However, the resoruces are deallocated automatically when the next enumeration is started or the object is released.</span></span>

## <a name="requirements"></a><span data-ttu-id="d8f0b-122">요구 사항</span><span class="sxs-lookup"><span data-stu-id="d8f0b-122">Requirements</span></span>  
 <span data-ttu-id="d8f0b-123">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d8f0b-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d8f0b-124">**헤더:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="d8f0b-124">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="d8f0b-125">**.NET Framework 버전:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="d8f0b-125">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d8f0b-126">참고자료</span><span class="sxs-lookup"><span data-stu-id="d8f0b-126">See also</span></span>  
[<span data-ttu-id="d8f0b-127">WMI 및 성능 카운터 (관리 되지 않는 API 참조)</span><span class="sxs-lookup"><span data-stu-id="d8f0b-127">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
