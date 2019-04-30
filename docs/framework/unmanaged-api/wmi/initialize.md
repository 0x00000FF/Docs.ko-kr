---
title: Initialize 함수 (관리 되지 않는 API 참조)
description: Initialize 함수 WMI 초기화를 수행합니다.
ms.date: 11/06/2017
api_name:
- Initialize
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- Initialize
helpviewer_keywords:
- Initialize function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7c71b2b6d6f102d19d30d480ee9bafcac3c204be
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62049299"
---
# <a name="initialize-function"></a><span data-ttu-id="d95d9-103">Initialize 함수</span><span class="sxs-lookup"><span data-stu-id="d95d9-103">Initialize function</span></span>

<span data-ttu-id="d95d9-104">WMI 초기화를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="d95d9-104">Performs WMI initialization.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a><span data-ttu-id="d95d9-105">구문</span><span class="sxs-lookup"><span data-stu-id="d95d9-105">Syntax</span></span>

```cpp
HRESULT Initialize(
   [in] boolean bAllowIManagementObjectQI
);
```

## <a name="parameters"></a><span data-ttu-id="d95d9-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="d95d9-106">Parameters</span></span>

`bAllowIManagementObjectQI`

<span data-ttu-id="d95d9-107">[in] `true` WMI 개체에서 QueryInterface 호출할 수 있도록; 나타내려면 `false` 그렇지 않은 경우.</span><span class="sxs-lookup"><span data-stu-id="d95d9-107">[in] `true` to indicate that calls to QueryInterface on WMI objects are allowed; `false` otherwise.</span></span>

## <a name="return-value"></a><span data-ttu-id="d95d9-108">반환 값</span><span class="sxs-lookup"><span data-stu-id="d95d9-108">Return value</span></span>

<span data-ttu-id="d95d9-109">항상 반환 `S_OK` (0).</span><span class="sxs-lookup"><span data-stu-id="d95d9-109">The function always returns `S_OK` (0).</span></span>

## <a name="requirements"></a><span data-ttu-id="d95d9-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="d95d9-110">Requirements</span></span>

<span data-ttu-id="d95d9-111">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="d95d9-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>

<span data-ttu-id="d95d9-112">**헤더:** WMINet_Utils.def</span><span class="sxs-lookup"><span data-stu-id="d95d9-112">**Header:** WMINet_Utils.def</span></span>

<span data-ttu-id="d95d9-113">**.NET Framework 버전:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="d95d9-113">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="d95d9-114">참고자료</span><span class="sxs-lookup"><span data-stu-id="d95d9-114">See also</span></span>

- [<span data-ttu-id="d95d9-115">WMI 및 성능 카운터 (관리 되지 않는 API 참조)</span><span class="sxs-lookup"><span data-stu-id="d95d9-115">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
