---
title: GetCurrentApartmentType 함수 (관리 되지 않는 API 참조)
description: GetCurrentApartmentType 함수 호출자가 실행 하는 아파트의 형식을 검색 합니다.
ms.date: 11/06/2017
api_name:
- GetCurrentApartmentType
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- GetCurrentApartmentType
helpviewer_keywords:
- GetCurrentApartmentType function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 4de85eb310de70dc8fd61f7c06abca95ec267f87
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/04/2018
ms.locfileid: "43522527"
---
# <a name="getcurrentapartmenttype-function"></a><span data-ttu-id="86c6a-103">GetCurrentApartmentType 함수</span><span class="sxs-lookup"><span data-stu-id="86c6a-103">GetCurrentApartmentType function</span></span>
<span data-ttu-id="86c6a-104">호출자가 실행 중인 아파트의 유형을 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="86c6a-104">Retrieves the type of apartment in which the caller is executing.</span></span>   
  
[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="86c6a-105">구문</span><span class="sxs-lookup"><span data-stu-id="86c6a-105">Syntax</span></span>  
  
```  
HRESULT GetCurrentApartmentType (
   [in] int                   vFunc, 
   [in] IComThreadingInfo*    ptr, 
   [out] APTTYPE*             aptType
); 
```  

## <a name="parameters"></a><span data-ttu-id="86c6a-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="86c6a-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="86c6a-107">[in] 이 매개 변수 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="86c6a-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="86c6a-108">[in] 에 대 한 포인터를 [IComThreadingInfo](/windows/desktop/api/objidlbase/nn-objidlbase-icomthreadinginfo) 인스턴스.</span><span class="sxs-lookup"><span data-stu-id="86c6a-108">[in] A pointer to an [IComThreadingInfo](/windows/desktop/api/objidlbase/nn-objidlbase-icomthreadinginfo) instance.</span></span>

`aptType`  
<span data-ttu-id="86c6a-109">[out] 에 대 한 포인터를 [APTTYPE](/windows/desktop/api/objidlbase/ne-objidlbase-_apttype) 호출자의 아파트를 나타내는 열거형 값입니다.</span><span class="sxs-lookup"><span data-stu-id="86c6a-109">[out] A pointer to an [APTTYPE](/windows/desktop/api/objidlbase/ne-objidlbase-_apttype) enumeration value that indicates the caller's apartment.</span></span>

## <a name="return-value"></a><span data-ttu-id="86c6a-110">반환 값</span><span class="sxs-lookup"><span data-stu-id="86c6a-110">Return value</span></span>


|<span data-ttu-id="86c6a-111">상수</span><span class="sxs-lookup"><span data-stu-id="86c6a-111">Constant</span></span>  |<span data-ttu-id="86c6a-112">값</span><span class="sxs-lookup"><span data-stu-id="86c6a-112">Value</span></span>  |<span data-ttu-id="86c6a-113">설명</span><span class="sxs-lookup"><span data-stu-id="86c6a-113">Description</span></span>  |
|---------|---------|---------|
| `S_OK` | <span data-ttu-id="86c6a-114">0</span><span class="sxs-lookup"><span data-stu-id="86c6a-114">0</span></span> | <span data-ttu-id="86c6a-115">함수는 성공적으로 완료 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="86c6a-115">The function completed successfully.</span></span> |
| `E_FAIL` | <span data-ttu-id="86c6a-116">0x80000008</span><span class="sxs-lookup"><span data-stu-id="86c6a-116">0x80000008</span></span> | <span data-ttu-id="86c6a-117">호출자는 아파트에서 실행할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="86c6a-117">The caller is not executing in an apartment.</span></span> |
  
## <a name="remarks"></a><span data-ttu-id="86c6a-118">설명</span><span class="sxs-lookup"><span data-stu-id="86c6a-118">Remarks</span></span>

<span data-ttu-id="86c6a-119">이 함수에 대 한 호출을 래핑하는 [IComThreadingInfo::GetCurrentApartmentType](/windows/desktop/api/objidlbase/nf-objidlbase-icomthreadinginfo-getcurrentapartmenttype) 메서드.</span><span class="sxs-lookup"><span data-stu-id="86c6a-119">This function wraps a call to the [IComThreadingInfo::GetCurrentApartmentType](/windows/desktop/api/objidlbase/nf-objidlbase-icomthreadinginfo-getcurrentapartmenttype) method.</span></span>

## <a name="requirements"></a><span data-ttu-id="86c6a-120">요구 사항</span><span class="sxs-lookup"><span data-stu-id="86c6a-120">Requirements</span></span>  
 <span data-ttu-id="86c6a-121">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="86c6a-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="86c6a-122">**헤더:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="86c6a-122">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="86c6a-123">**.NET Framework 버전:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="86c6a-123">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="86c6a-124">참고자료</span><span class="sxs-lookup"><span data-stu-id="86c6a-124">See also</span></span>  
[<span data-ttu-id="86c6a-125">WMI 및 성능 카운터 (관리 되지 않는 API 참조)</span><span class="sxs-lookup"><span data-stu-id="86c6a-125">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
