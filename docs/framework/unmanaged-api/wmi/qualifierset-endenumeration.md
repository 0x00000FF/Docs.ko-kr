---
title: QualifierSet_EndEnumeration 함수 (관리 되지 않는 API 참조)
description: QualifierSet_EndEnumeration 함수는 열거형을 종료 합니다.
ms.date: 11/06/2017
api_name:
- QualifierSet_EndEnumeration
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- QualifierSet_EndEnumeration
helpviewer_keywords:
- QualifierSet_EndEnumeration function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2c5a817174ec4c4e4407c19bb1d6d2d852d86dd2
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/07/2019
ms.locfileid: "70798324"
---
# <a name="qualifierset_endenumeration-function"></a><span data-ttu-id="1d417-103">QualifierSet_EndEnumeration 함수</span><span class="sxs-lookup"><span data-stu-id="1d417-103">QualifierSet_EndEnumeration function</span></span>
<span data-ttu-id="1d417-104">[QualifierSet_BeginEnumeration](qualifierset-beginenumeration.md) 함수를 호출 하 여 시작 된 열거를 종료 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d417-104">Terminates the enumeration begun with a call to the [QualifierSet_BeginEnumeration](qualifierset-beginenumeration.md) function.</span></span>  

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="1d417-105">구문</span><span class="sxs-lookup"><span data-stu-id="1d417-105">Syntax</span></span>  
  
```cpp  
HRESULT QualifierSet_EndEnumeration (
   [in] int                  vFunc, 
   [in] IWbemQualifierSet*   ptr
); 
```  

## <a name="parameters"></a><span data-ttu-id="1d417-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="1d417-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="1d417-107">진행 이 매개 변수는 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1d417-107">[in] This parameter is unused.</span></span>

`ptr`   
<span data-ttu-id="1d417-108">진행 [IWbemQualifierSet](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset) 인스턴스에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="1d417-108">[in] A pointer to an [IWbemQualifierSet](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset) instance.</span></span>

## <a name="return-value"></a><span data-ttu-id="1d417-109">반환 값</span><span class="sxs-lookup"><span data-stu-id="1d417-109">Return value</span></span>

<span data-ttu-id="1d417-110">이 함수에서 반환 되는 다음 값은 *WbemCli* 헤더 파일에 정의 되어 있거나 코드에서 상수로 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1d417-110">The following value returned by this function is defined in the *WbemCli.h* header file, or you can define it as a constant in your code:</span></span>

|<span data-ttu-id="1d417-111">상수</span><span class="sxs-lookup"><span data-stu-id="1d417-111">Constant</span></span>  |<span data-ttu-id="1d417-112">값</span><span class="sxs-lookup"><span data-stu-id="1d417-112">Value</span></span>  |<span data-ttu-id="1d417-113">설명</span><span class="sxs-lookup"><span data-stu-id="1d417-113">Description</span></span>  |
|---------|---------|---------|
|`WBEM_S_NO_ERROR` | <span data-ttu-id="1d417-114">0</span><span class="sxs-lookup"><span data-stu-id="1d417-114">0</span></span> | <span data-ttu-id="1d417-115">함수 호출에 성공 했습니다.</span><span class="sxs-lookup"><span data-stu-id="1d417-115">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="1d417-116">설명</span><span class="sxs-lookup"><span data-stu-id="1d417-116">Remarks</span></span>

<span data-ttu-id="1d417-117">이 함수는 [IWbemQualifierSet:: EndEnumeration](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemqualifierset-endenumeration) 메서드에 대 한 호출을 래핑합니다.</span><span class="sxs-lookup"><span data-stu-id="1d417-117">This function wraps a call to the [IWbemQualifierSet::EndEnumeration](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemqualifierset-endenumeration) method.</span></span>

<span data-ttu-id="1d417-118">이 호출은 권장 되지만 반드시 필요한 것은 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="1d417-118">This call is recommended, but not required.</span></span> <span data-ttu-id="1d417-119">열거형과 연결 된 리소스를 즉시 해제 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d417-119">It immediately releases resources associated with the enumeration.</span></span>

## <a name="requirements"></a><span data-ttu-id="1d417-120">요구 사항</span><span class="sxs-lookup"><span data-stu-id="1d417-120">Requirements</span></span>  

<span data-ttu-id="1d417-121">**플랫폼** [시스템 요구 사항](../../get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="1d417-121">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
<span data-ttu-id="1d417-122">**헤더:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="1d417-122">**Header:** WMINet_Utils.idl</span></span>  
  
<span data-ttu-id="1d417-123">**.NET Framework 버전:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="1d417-123">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1d417-124">참고자료</span><span class="sxs-lookup"><span data-stu-id="1d417-124">See also</span></span>

- [<span data-ttu-id="1d417-125">WMI 및 성능 카운터 (관리 되지 않는 API 참조)</span><span class="sxs-lookup"><span data-stu-id="1d417-125">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
