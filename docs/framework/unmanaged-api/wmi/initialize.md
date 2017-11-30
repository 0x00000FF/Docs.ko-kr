---
title: "Initialize 함수 (관리 되지 않는 API 참조)"
description: "Initialize 함수 WMI 초기화를 수행합니다."
ms.date: 11/06/2017
ms.prod: .net-framework
ms.technology: dotnet-clr
ms.topic: reference
api_name: Initialize
api_location: WMINet_Utils.dll
api_type: DLLExport
f1_keywords: Initialize
helpviewer_keywords: Initialize function [.NET WMI and performance counters]
topic_type: Reference
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 9ed0e0127608f9f80a2661067dd9a6025fd579a7
ms.sourcegitcommit: a53799f81351ad9afb3007cd68846ce6aeeb10cb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/15/2017
---
# <a name="initialize-function"></a><span data-ttu-id="6d14c-103">Initialize 함수</span><span class="sxs-lookup"><span data-stu-id="6d14c-103">Initialize function</span></span>
<span data-ttu-id="6d14c-104">WMI 초기화를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="6d14c-104">Performs WMI initialization.</span></span>  
  
[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="6d14c-105">구문</span><span class="sxs-lookup"><span data-stu-id="6d14c-105">Syntax</span></span> 
```  
HRESULT Initialize(
   [in] boolean bAllowIManagementObjectQI
); 
```  
## <a name="parameters"></a><span data-ttu-id="6d14c-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="6d14c-106">Parameters</span></span>

`bAllowIManagementObjectQI`   
<span data-ttu-id="6d14c-107">[in] `true` WMI 개체에서 QueryInterface 호출할 수 있도록; 나타내기 위해 `false` 그렇지 않은 경우.</span><span class="sxs-lookup"><span data-stu-id="6d14c-107">[in] `true` to indicate that calls to QueryInterface on WMI objects are allowed; `false` otherwise.</span></span>

## <a name="return-value"></a><span data-ttu-id="6d14c-108">반환 값</span><span class="sxs-lookup"><span data-stu-id="6d14c-108">Return value</span></span>

<span data-ttu-id="6d14c-109">함수는 항상 반환 `S_OK` (0).</span><span class="sxs-lookup"><span data-stu-id="6d14c-109">The function always returns `S_OK` (0).</span></span>
  
## <a name="requirements"></a><span data-ttu-id="6d14c-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="6d14c-110">Requirements</span></span>  
 <span data-ttu-id="6d14c-111">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="6d14c-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6d14c-112">**헤더:** WMINet_Utils.def</span><span class="sxs-lookup"><span data-stu-id="6d14c-112">**Header:** WMINet_Utils.def</span></span>  
  
 <span data-ttu-id="6d14c-113">**.NET framework 버전:**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="6d14c-113">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6d14c-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="6d14c-114">See also</span></span>  
[<span data-ttu-id="6d14c-115">WMI 및 성능 카운터 (관리 되지 않는 API 참조)</span><span class="sxs-lookup"><span data-stu-id="6d14c-115">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
