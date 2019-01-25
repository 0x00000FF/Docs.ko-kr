---
title: SetSecurity 함수 (관리 되지 않는 API 참조)
description: SetSecurity 함수는 현재 스레드의 가장 토큰을 검색합니다.
ms.date: 11/06/2017
api_name:
- SetSecurity
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- SetSecurity
helpviewer_keywords:
- SetSecurity function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3b3e8ddb34849611daae4dfa1d2762a25ac5cf82
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54721141"
---
# <a name="setsecurity-function"></a><span data-ttu-id="a165f-103">SetSecurity 함수</span><span class="sxs-lookup"><span data-stu-id="a165f-103">SetSecurity function</span></span>
<span data-ttu-id="a165f-104">현재 스레드와 연결된 가장 토큰을 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="a165f-104">Retrieves the impersonation token associated with the current thread.</span></span>   
  
[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="a165f-105">구문</span><span class="sxs-lookup"><span data-stu-id="a165f-105">Syntax</span></span>  
  
```  
HRESULT SetSecurity (
   [out] boolean* pNeedToReset, 
   [out] HANDLE* pCurrentThreadToken
); 
```  

## <a name="parameters"></a><span data-ttu-id="a165f-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="a165f-106">Parameters</span></span>

<span data-ttu-id="a165f-107">`pNeedToReset` [out] 함수는 반환 될 때 포함에 대 한 포인터를 `boolean` 를 호출 하 여 토큰을 다시 설정 해야 하는지 여부를 나타내는 합니다 [ResetSecurity](resetsecurity.md) 함수입니다.</span><span class="sxs-lookup"><span data-stu-id="a165f-107">`pNeedToReset` [out] When the function returns, contains a pointer to a `boolean` that indicates whether the token should be reset by calling the [ResetSecurity](resetsecurity.md) function.</span></span>  

`token`  
<span data-ttu-id="a165f-108">[out] 함수는 반환 될 때 현재 스레드와 연결 된 가장 토큰 핸들에 대 한 포인터를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="a165f-108">[out] When the function returns, contains a pointer to the handle of the impersonation token associated with the current thread.</span></span> <span data-ttu-id="a165f-109">해당 값은 `null` 현재 스레드와 연결 된 토큰이 없는 경우.</span><span class="sxs-lookup"><span data-stu-id="a165f-109">Its value can be `null` if there is no token associated with the current thread.</span></span> 

## <a name="return-value"></a><span data-ttu-id="a165f-110">반환 값</span><span class="sxs-lookup"><span data-stu-id="a165f-110">Return value</span></span>

<span data-ttu-id="a165f-111">함수가 성공할 경우 반환 값은 `S_OK` (0).</span><span class="sxs-lookup"><span data-stu-id="a165f-111">If the function succeeds, the return value is `S_OK` (0).</span></span>

<span data-ttu-id="a165f-112">함수가 실패 한 경우 반환 값은 0이 아닌 오류 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="a165f-112">If the function fails, the return value is a non-zero error code.</span></span> <span data-ttu-id="a165f-113">오류 정보를 호출 합니다 [GetErrorInfo](geterrorinfo.md) 함수입니다.</span><span class="sxs-lookup"><span data-stu-id="a165f-113">To get extended error information, call the [GetErrorInfo](geterrorinfo.md) function.</span></span>
  
## <a name="requirements"></a><span data-ttu-id="a165f-114">요구 사항</span><span class="sxs-lookup"><span data-stu-id="a165f-114">Requirements</span></span>  
 <span data-ttu-id="a165f-115">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="a165f-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a165f-116">**헤더:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="a165f-116">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="a165f-117">**.NET Framework 버전:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="a165f-117">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a165f-118">참고자료</span><span class="sxs-lookup"><span data-stu-id="a165f-118">See also</span></span>
- [<span data-ttu-id="a165f-119">WMI 및 성능 카운터 (관리 되지 않는 API 참조)</span><span class="sxs-lookup"><span data-stu-id="a165f-119">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
