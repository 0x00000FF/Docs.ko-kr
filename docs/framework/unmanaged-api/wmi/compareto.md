---
title: CompareTo 함수 (관리 되지 않는 API 참조)
description: CompareTo 함수는 개체를 다른 WMI 개체와 비교 합니다.
ms.date: 11/06/2017
api_name:
- CompareTo
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- CompareTo
helpviewer_keywords:
- CompareTo function [.NET WMI and performance counters]
topic_type:
- Reference
ms.openlocfilehash: 0d210795016cd2e0179b902a224ca0c62f4ac01f
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73128709"
---
# <a name="compareto-function"></a><span data-ttu-id="3e773-103">CompareTo 함수</span><span class="sxs-lookup"><span data-stu-id="3e773-103">CompareTo function</span></span>

<span data-ttu-id="3e773-104">개체를 다른 Windows 관리 개체와 비교합니다.</span><span class="sxs-lookup"><span data-stu-id="3e773-104">Compares an object to another Windows management object.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a><span data-ttu-id="3e773-105">구문</span><span class="sxs-lookup"><span data-stu-id="3e773-105">Syntax</span></span>

```cpp
HRESULT CompareTo (
   [in] int               vFunc,
   [in] IWbemClassObject* ptr,
   [in] LONG              flags,
   [in] IWbemClassObject* pCompareTo
);
```

## <a name="parameters"></a><span data-ttu-id="3e773-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="3e773-106">Parameters</span></span>

`vFunc`\
<span data-ttu-id="3e773-107">진행 이 매개 변수는 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3e773-107">[in] This parameter is unused.</span></span>

`ptr`\
<span data-ttu-id="3e773-108">진행 [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) 인스턴스에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="3e773-108">[in] A pointer to an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instance.</span></span>

`flags`\
<span data-ttu-id="3e773-109">진행 비교를 위해 고려할 개체 특성을 지정 하는 플래그의 비트 조합입니다.</span><span class="sxs-lookup"><span data-stu-id="3e773-109">[in] A bitwise combination of the flags that specify the object characteristics to consider for the comparison.</span></span> <span data-ttu-id="3e773-110">자세한 내용은 [설명](#remarks) 부분을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="3e773-110">See the [Remarks](#remarks) section for more information.</span></span>

`pCompareTo`\
<span data-ttu-id="3e773-111">진행 비교할 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="3e773-111">[in] The object for comparison.</span></span> <span data-ttu-id="3e773-112">`pCompareTo`은 유효한 [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) 인스턴스여야 합니다. `null`수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="3e773-112">`pCompareTo` must be a valid [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instance; it cannot be `null`.</span></span>

## <a name="return-value"></a><span data-ttu-id="3e773-113">반환 값</span><span class="sxs-lookup"><span data-stu-id="3e773-113">Return value</span></span>

<span data-ttu-id="3e773-114">이 함수에서 반환 되는 다음 값은 *WbemCli* 헤더 파일에 정의 되어 있거나 코드에서 상수로 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3e773-114">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="3e773-115">상수</span><span class="sxs-lookup"><span data-stu-id="3e773-115">Constant</span></span>  |<span data-ttu-id="3e773-116">값</span><span class="sxs-lookup"><span data-stu-id="3e773-116">Value</span></span>  |<span data-ttu-id="3e773-117">설명</span><span class="sxs-lookup"><span data-stu-id="3e773-117">Description</span></span>  |
|---------|---------|---------|
| `WBEM_E_FAILED` | <span data-ttu-id="3e773-118">0x80041001</span><span class="sxs-lookup"><span data-stu-id="3e773-118">0x80041001</span></span> | <span data-ttu-id="3e773-119">지정 되지 않은 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="3e773-119">An unspecified error has occurred.</span></span> |
| `WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="3e773-120">0x80041008</span><span class="sxs-lookup"><span data-stu-id="3e773-120">0x80041008</span></span> | <span data-ttu-id="3e773-121">매개 변수가 잘못 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="3e773-121">A parameter is invalid.</span></span> |
| `WBEM_E_UNEXPECTED` | <span data-ttu-id="3e773-122">0x8004101d</span><span class="sxs-lookup"><span data-stu-id="3e773-122">0x8004101d</span></span> | <span data-ttu-id="3e773-123">[`EndEnumeration`](endenumeration.md)를 중간에 호출 하지 않고 `BeginEnumeration`에 대 한 두 번째 호출을 수행 했습니다.</span><span class="sxs-lookup"><span data-stu-id="3e773-123">A second call to `BeginEnumeration` was made without an intervening call to [`EndEnumeration`](endenumeration.md).</span></span> |
| `WBEM_S_NO_ERROR` | <span data-ttu-id="3e773-124">0</span><span class="sxs-lookup"><span data-stu-id="3e773-124">0</span></span> | <span data-ttu-id="3e773-125">함수 호출에 성공 했습니다.</span><span class="sxs-lookup"><span data-stu-id="3e773-125">The function call was successful.</span></span>  |
| `WBEM_S_DIFFERENT` | <span data-ttu-id="3e773-126">0x40003</span><span class="sxs-lookup"><span data-stu-id="3e773-126">0x40003</span></span> | <span data-ttu-id="3e773-127">개체가 서로 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="3e773-127">The objects are different.</span></span> |
| `WBEM_S_SAME` | <span data-ttu-id="3e773-128">0</span><span class="sxs-lookup"><span data-stu-id="3e773-128">0</span></span> | <span data-ttu-id="3e773-129">개체는 비교 플래그를 기준으로 동일 합니다.</span><span class="sxs-lookup"><span data-stu-id="3e773-129">The objects are the same based on the comparison flags.</span></span> |

## <a name="remarks"></a><span data-ttu-id="3e773-130">주의</span><span class="sxs-lookup"><span data-stu-id="3e773-130">Remarks</span></span>

<span data-ttu-id="3e773-131">이 함수는 [IWbemClassObject:: CompareTo](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-compareto) 메서드에 대 한 호출을 래핑합니다.</span><span class="sxs-lookup"><span data-stu-id="3e773-131">This function wraps a call to the [IWbemClassObject::CompareTo](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-compareto) method.</span></span>

<span data-ttu-id="3e773-132">`lEnumFlags` 인수로 전달 될 수 있는 플래그는 *WbemCli* 헤더 파일에 정의 되어 있거나 코드에서 상수로 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3e773-132">The flags that can be passed as the `lEnumFlags` argument are defined in the *WbemCli.h* header file, or you can define them as constants in your code.</span></span> <span data-ttu-id="3e773-133">다음 플래그의 비트 조합을 지정 하 여 비교와 관련 된 개별 특성을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3e773-133">You can specify the individual characteristics involved in the comparison by specifying a bitwise combination of the following flags:</span></span>

|<span data-ttu-id="3e773-134">상수</span><span class="sxs-lookup"><span data-stu-id="3e773-134">Constant</span></span>  |<span data-ttu-id="3e773-135">값</span><span class="sxs-lookup"><span data-stu-id="3e773-135">Value</span></span>  |<span data-ttu-id="3e773-136">설명</span><span class="sxs-lookup"><span data-stu-id="3e773-136">Description</span></span>  |
|---------|---------|---------|
| `WBEM_FLAG_IGNORE_OBJECT_SOURCE` | <span data-ttu-id="3e773-137">2</span><span class="sxs-lookup"><span data-stu-id="3e773-137">2</span></span> | <span data-ttu-id="3e773-138">원본 (서버와 원본에서 가져온 네임 스페이스)을 무시 합니다.</span><span class="sxs-lookup"><span data-stu-id="3e773-138">Ignore the source (the server and the namespace they came from).</span></span> |
| `WBEM_FLAG_IGNORE_QUALIFIERS` | <span data-ttu-id="3e773-139">1</span><span class="sxs-lookup"><span data-stu-id="3e773-139">1</span></span> | <span data-ttu-id="3e773-140">모든 한정자 무시 ( **키** 및 **동적**포함)</span><span class="sxs-lookup"><span data-stu-id="3e773-140">Ignore all qualifiers (including **Key** and **Dynamic**)</span></span> |
| `WBEM_FLAG_IGNORE_DEFAULT_VALUES` | <span data-ttu-id="3e773-141">4</span><span class="sxs-lookup"><span data-stu-id="3e773-141">4</span></span> | <span data-ttu-id="3e773-142">속성의 기본값을 무시 합니다.</span><span class="sxs-lookup"><span data-stu-id="3e773-142">Ignore default values of properties.</span></span> <span data-ttu-id="3e773-143">이 플래그는 클래스 비교에만 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3e773-143">This flag only applies to comparison of classes.</span></span> |
| `WBEM_FLAG_IGNORE_FLAVOR` | <span data-ttu-id="3e773-144">0x20</span><span class="sxs-lookup"><span data-stu-id="3e773-144">0x20</span></span> | <span data-ttu-id="3e773-145">한정자 특색을 무시 합니다.</span><span class="sxs-lookup"><span data-stu-id="3e773-145">Ignore qualifier flavors.</span></span> <span data-ttu-id="3e773-146">이 플래그는 한정자를 계속 고려 하지만 전파 규칙 및 재정의 제한과 같은 버전 차이는 무시 합니다.</span><span class="sxs-lookup"><span data-stu-id="3e773-146">This flag still takes qualifiers into account, but ignores flavor distinctions such as propagation rules and override restrictions.</span></span> |
| `WBEM_FLAG_IGNORE_CASE` | <span data-ttu-id="3e773-147">0x10</span><span class="sxs-lookup"><span data-stu-id="3e773-147">0x10</span></span> | <span data-ttu-id="3e773-148">문자열 값을 비교할 때 대/소문자를 무시 합니다.</span><span class="sxs-lookup"><span data-stu-id="3e773-148">Ignore case in comparing string values.</span></span> <span data-ttu-id="3e773-149">이는 문자열 및 한정자 값 모두에 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3e773-149">This applies both to strings and qualifier values.</span></span> <span data-ttu-id="3e773-150">이 플래그가 설정 되었는지 여부에 관계 없이 속성 및 한정자 이름의 비교는 항상 대/소문자를 구분 합니다.</span><span class="sxs-lookup"><span data-stu-id="3e773-150">The comparison of property and qualifier names is always case-sensitive regardless of whether this flag is set.</span></span> |
| `WBEM_FLAG_IGNORE_CLASS` | <span data-ttu-id="3e773-151">나오는</span><span class="sxs-lookup"><span data-stu-id="3e773-151">0x8</span></span> | <span data-ttu-id="3e773-152">비교할 개체가 동일한 클래스의 인스턴스인 것으로 가정 합니다.</span><span class="sxs-lookup"><span data-stu-id="3e773-152">Assume that the objects being compared are instances of the same class.</span></span> <span data-ttu-id="3e773-153">따라서이 플래그는 인스턴스 관련 정보만을 비교 합니다.</span><span class="sxs-lookup"><span data-stu-id="3e773-153">Consequently, this flag compares instance-related information only.</span></span> <span data-ttu-id="3e773-154">이 플래그를 사용 하 여 성능을 최적화 합니다.</span><span class="sxs-lookup"><span data-stu-id="3e773-154">Use this flags to optimize performance.</span></span> <span data-ttu-id="3e773-155">개체가 동일한 클래스가 아니면 결과가 정의 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3e773-155">If the objects are not of the same class, the results are undefined.</span></span> |

<span data-ttu-id="3e773-156">또는 단일 복합 플래그를 다음과 같이 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3e773-156">Or you can specify a single composite flag as follows:</span></span>

|<span data-ttu-id="3e773-157">상수</span><span class="sxs-lookup"><span data-stu-id="3e773-157">Constant</span></span>  |<span data-ttu-id="3e773-158">값</span><span class="sxs-lookup"><span data-stu-id="3e773-158">Value</span></span>  |<span data-ttu-id="3e773-159">설명</span><span class="sxs-lookup"><span data-stu-id="3e773-159">Description</span></span>  |
|---------|---------|---------|
|`WBEM_COMPARISON_INCLUDE_ALL` | <span data-ttu-id="3e773-160">0</span><span class="sxs-lookup"><span data-stu-id="3e773-160">0</span></span> | <span data-ttu-id="3e773-161">비교의 모든 기능을 고려 합니다.</span><span class="sxs-lookup"><span data-stu-id="3e773-161">Consider all features in the comparison.</span></span> |

## <a name="requirements"></a><span data-ttu-id="3e773-162">요구 사항</span><span class="sxs-lookup"><span data-stu-id="3e773-162">Requirements</span></span>

<span data-ttu-id="3e773-163">**플랫폼:** [시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="3e773-163">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>

<span data-ttu-id="3e773-164">**헤더:** WMINet_Utils</span><span class="sxs-lookup"><span data-stu-id="3e773-164">**Header:** WMINet_Utils.idl</span></span>

<span data-ttu-id="3e773-165">**.NET Framework 버전:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="3e773-165">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="3e773-166">참조</span><span class="sxs-lookup"><span data-stu-id="3e773-166">See also</span></span>

- [<span data-ttu-id="3e773-167">WMI 및 성능 카운터 (관리 되지 않는 API 참조)</span><span class="sxs-lookup"><span data-stu-id="3e773-167">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
