---
title: CreateClassEnumWmi 함수 (관리 되지 않는 API 참조)
description: CreateClassEnumWmi 함수는 지정 된 조건을 충족 하는 모든 클래스에 대 한 열거자를 반환 합니다.
ms.date: 11/06/2017
api_name:
- CreateClassEnumWmi
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- CreateClassEnumWmi
helpviewer_keywords:
- CreateClassEnumWmi function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 0a4d2c2bd28640d0ac7124f8e0864e9e72fb1eb9
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/05/2019
ms.locfileid: "57372336"
---
# <a name="createclassenumwmi-function"></a><span data-ttu-id="803bc-103">CreateClassEnumWmi 함수</span><span class="sxs-lookup"><span data-stu-id="803bc-103">CreateClassEnumWmi function</span></span>
<span data-ttu-id="803bc-104">지정된 선택 조건을 충족하는 모든 클래스에 대한 열거자를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="803bc-104">Returns an enumerator for all classes that satisfy the specified selection criteria.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a><span data-ttu-id="803bc-105">구문</span><span class="sxs-lookup"><span data-stu-id="803bc-105">Syntax</span></span>

```cpp
HRESULT CreateClassEnumWmi (
   [in] BSTR                    strSuperclass,
   [in] long                    lFlags,
   [in] IWbemContext*           pCtx,
   [out] IEnumWbemClassObject** ppEnum,
   [in] DWORD                   authLevel,
   [in] DWORD                   impLevel,
   [in] IWbemServices*          pCurrentNamespace,
   [in] BSTR                    strUser,
   [in] BSTR                    strPassword,
   [in] BSTR                    strAuthority
);
```

## <a name="parameters"></a><span data-ttu-id="803bc-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="803bc-106">Parameters</span></span>

`strSuperclass`\
<span data-ttu-id="803bc-107">[in] 그렇지 않은 경우 `null` 빈, 부모 클래스의 이름을 지정 하거나 열거자만이 클래스의 서브 클래스를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="803bc-107">[in] If not `null` or blank, specifies the name of a parent class; the enumerator returns only subclasses of this class.</span></span> <span data-ttu-id="803bc-108">있으면 `null` 또는 빈 및 `lFlags` WBEM_FLAG_SHALLOW를 최상위 클래스 (부모 클래스가 없는 클래스)를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="803bc-108">If it is `null` or blank and `lFlags` is WBEM_FLAG_SHALLOW, returns only top-level classes (classes with no parent class).</span></span> <span data-ttu-id="803bc-109">있으면 `null` 또는 빈 및 `lFlags` 는 `WBEM_FLAG_DEEP`, 네임 스페이스의 모든 클래스를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="803bc-109">If it is `null` or blank and `lFlags` is `WBEM_FLAG_DEEP`, returns all classes in the namespace.</span></span>

`lFlags`\
<span data-ttu-id="803bc-110">[in] 이 함수의 동작에 영향을 주는 플래그의 조합입니다.</span><span class="sxs-lookup"><span data-stu-id="803bc-110">[in] A combination of flags that affect the behavior of this function.</span></span> <span data-ttu-id="803bc-111">에 정의 된 다음 값을 *WbemCli.h* 헤더 파일에서 정의할 수 상수로 코드:</span><span class="sxs-lookup"><span data-stu-id="803bc-111">The following values are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="803bc-112">상수</span><span class="sxs-lookup"><span data-stu-id="803bc-112">Constant</span></span>  |<span data-ttu-id="803bc-113">값</span><span class="sxs-lookup"><span data-stu-id="803bc-113">Value</span></span>  |<span data-ttu-id="803bc-114">설명</span><span class="sxs-lookup"><span data-stu-id="803bc-114">Description</span></span>  |
|---------|---------|---------|
| `WBEM_FLAG_USE_AMENDED_QUALIFIERS` | <span data-ttu-id="803bc-115">0x20000</span><span class="sxs-lookup"><span data-stu-id="803bc-115">0x20000</span></span> | <span data-ttu-id="803bc-116">경우 집합 함수는 현재 연결의 로캘의 지역화 된 네임 스페이스에 저장 된 수정 된 한정자를 검색 합니다.</span><span class="sxs-lookup"><span data-stu-id="803bc-116">If set, the function retrieves the amended qualifiers stored in the localized namespace of the current connection's locale.</span></span> <br/> <span data-ttu-id="803bc-117">그렇지 않은 경우 집합 함수를 즉시 네임 스페이스에 저장 된 한정자만 검색 합니다.</span><span class="sxs-lookup"><span data-stu-id="803bc-117">If not set, the function retrieves only the qualifiers stored in the immediate namespace.</span></span> |
| `WBEM_FLAG_DEEP` | <span data-ttu-id="803bc-118">0</span><span class="sxs-lookup"><span data-stu-id="803bc-118">0</span></span> | <span data-ttu-id="803bc-119">열거형이이 클래스가 아닌 계층에서 모든 하위 클래스를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="803bc-119">The enumeration includes all subclasses in the hierarchy, but not this class.</span></span> |
| `WBEM_FLAG_SHALLOW` | <span data-ttu-id="803bc-120">1</span><span class="sxs-lookup"><span data-stu-id="803bc-120">1</span></span> | <span data-ttu-id="803bc-121">이 클래스의 순수 인스턴스만 포함이 클래스에 없는 속성을 제공 하는 서브 클래스의 모든 인스턴스를 제외 하는 열거형입니다.</span><span class="sxs-lookup"><span data-stu-id="803bc-121">The enumeration includes only pure instances of this class and excludes all instances of subclasses that supply properties not found in this class.</span></span> |
| `WBEM_FLAG_RETURN_IMMEDIATELY` | <span data-ttu-id="803bc-122">0x10</span><span class="sxs-lookup"><span data-stu-id="803bc-122">0x10</span></span> | <span data-ttu-id="803bc-123">플래그를 사용 하면 일부 동기 호출입니다.</span><span class="sxs-lookup"><span data-stu-id="803bc-123">The flag causes a semisynchronous call.</span></span> |
| `WBEM_FLAG_FORWARD_ONLY` | <span data-ttu-id="803bc-124">0x20</span><span class="sxs-lookup"><span data-stu-id="803bc-124">0x20</span></span> | <span data-ttu-id="803bc-125">함수에는 정방향 전용 열거자를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="803bc-125">The function returns a forward-only enumerator.</span></span> <span data-ttu-id="803bc-126">일반적으로 앞 으로만 이동 가능한 열거자 빠르고 기본 열거자 보다 적은 메모리를 사용 하지만 호출을 허용 하지 않습니다 [복제](clone.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="803bc-126">Typically, forward-only enumerators are faster and use less memory than conventional enumerators, but they do not allow calls to [Clone](clone.md).</span></span> |
| `WBEM_FLAG_BIDIRECTIONAL` | <span data-ttu-id="803bc-127">0</span><span class="sxs-lookup"><span data-stu-id="803bc-127">0</span></span> | <span data-ttu-id="803bc-128">WMI가 릴리스될 때까지 열거형에는 개체에 대 한 포인터를 유지 합니다.</span><span class="sxs-lookup"><span data-stu-id="803bc-128">WMI retains pointers to objects in the enumeration until they are released.</span></span> |

<span data-ttu-id="803bc-129">권장 되는 플래그가 `WBEM_FLAG_RETURN_IMMEDIATELY` 고 `WBEM_FLAG_FORWARD_ONLY` 최상의 성능을 위해.</span><span class="sxs-lookup"><span data-stu-id="803bc-129">The recommended flags are `WBEM_FLAG_RETURN_IMMEDIATELY` and `WBEM_FLAG_FORWARD_ONLY` for best performance.</span></span>

`pCtx`\
<span data-ttu-id="803bc-130">[in] 이 값은 일반적으로 `null`입니다.</span><span class="sxs-lookup"><span data-stu-id="803bc-130">[in] Typically, this value is `null`.</span></span> <span data-ttu-id="803bc-131">그렇지 않을 경우에 대 한 포인터를 [IWbemContext](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemcontext) 요청 된 클래스를 제공 하는 공급자가 사용할 수 있는 인스턴스.</span><span class="sxs-lookup"><span data-stu-id="803bc-131">Otherwise, it is a pointer to an [IWbemContext](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemcontext) instance that can be used by the provider that is providing the requested classes.</span></span>

`ppEnum`\
<span data-ttu-id="803bc-132">[out] 열거자에 대 한 포인터를 받습니다.</span><span class="sxs-lookup"><span data-stu-id="803bc-132">[out] Receives the pointer to the enumerator.</span></span>

`authLevel`\
<span data-ttu-id="803bc-133">[in] 권한 부여 수준입니다.</span><span class="sxs-lookup"><span data-stu-id="803bc-133">[in] The authorization level.</span></span>

`impLevel`\
<span data-ttu-id="803bc-134">[in] 가장 수준입니다.</span><span class="sxs-lookup"><span data-stu-id="803bc-134">[in] The impersonation level.</span></span>

`pCurrentNamespace`\
<span data-ttu-id="803bc-135">[in] 에 대 한 포인터를 [IWbemServices](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemservices) 현재 네임 스페이스를 나타내는 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="803bc-135">[in] A pointer to an [IWbemServices](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemservices) object that represents the current namespace.</span></span>

`strUser`\
<span data-ttu-id="803bc-136">[in] 사용자 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="803bc-136">[in] The user name.</span></span> <span data-ttu-id="803bc-137">참조 된 [ConnectServerWmi](connectserverwmi.md) 자세한 함수입니다.</span><span class="sxs-lookup"><span data-stu-id="803bc-137">See the [ConnectServerWmi](connectserverwmi.md) function for more information.</span></span>

`strPassword`\
<span data-ttu-id="803bc-138">[in] 암호입니다.</span><span class="sxs-lookup"><span data-stu-id="803bc-138">[in] The password.</span></span> <span data-ttu-id="803bc-139">참조 된 [ConnectServerWmi](connectserverwmi.md) 자세한 함수입니다.</span><span class="sxs-lookup"><span data-stu-id="803bc-139">See the [ConnectServerWmi](connectserverwmi.md) function for more information.</span></span>

`strAuthority`\
<span data-ttu-id="803bc-140">[in] 사용자의 도메인 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="803bc-140">[in] The domain name of the user.</span></span> <span data-ttu-id="803bc-141">참조 된 [ConnectServerWmi](connectserverwmi.md) 자세한 함수입니다.</span><span class="sxs-lookup"><span data-stu-id="803bc-141">See the [ConnectServerWmi](connectserverwmi.md) function for more information.</span></span>

## <a name="return-value"></a><span data-ttu-id="803bc-142">반환 값</span><span class="sxs-lookup"><span data-stu-id="803bc-142">Return value</span></span>

<span data-ttu-id="803bc-143">이 함수에 의해 반환 되는 다음 값에 정의 된 합니다 *WbemCli.h* 헤더 파일에서 정의할 수 상수로 코드:</span><span class="sxs-lookup"><span data-stu-id="803bc-143">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="803bc-144">상수</span><span class="sxs-lookup"><span data-stu-id="803bc-144">Constant</span></span>  |<span data-ttu-id="803bc-145">값</span><span class="sxs-lookup"><span data-stu-id="803bc-145">Value</span></span>  |<span data-ttu-id="803bc-146">설명</span><span class="sxs-lookup"><span data-stu-id="803bc-146">Description</span></span>  |
|---------|---------|---------|
| `WBEM_E_ACCESS_DENIED` | <span data-ttu-id="803bc-147">0x80041003</span><span class="sxs-lookup"><span data-stu-id="803bc-147">0x80041003</span></span> | <span data-ttu-id="803bc-148">사용자 함수를 반환할 수 있는 클래스 중 하나 이상을 볼 수 있는 권한이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="803bc-148">The user does not have permission to view one or more of the classes that the function can return.</span></span> |
| `WBEM_E_FAILED` | <span data-ttu-id="803bc-149">0x80041001</span><span class="sxs-lookup"><span data-stu-id="803bc-149">0x80041001</span></span> | <span data-ttu-id="803bc-150">지정 되지 않은 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="803bc-150">An unspecified error has occurred.</span></span> |
| `WBEM_E_INVALID_CLASS` | <span data-ttu-id="803bc-151">0x80041010</span><span class="sxs-lookup"><span data-stu-id="803bc-151">0x80041010</span></span> | <span data-ttu-id="803bc-152">`strSuperClass`가 없는 경우</span><span class="sxs-lookup"><span data-stu-id="803bc-152">`strSuperClass` does not exist.</span></span> |
| `WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="803bc-153">0x80041008</span><span class="sxs-lookup"><span data-stu-id="803bc-153">0x80041008</span></span> | <span data-ttu-id="803bc-154">매개 변수가 잘못 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="803bc-154">A parameter is not valid.</span></span> |
| `WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="803bc-155">0x80041006</span><span class="sxs-lookup"><span data-stu-id="803bc-155">0x80041006</span></span> | <span data-ttu-id="803bc-156">메모리가 부족 하 여 작업을 완료할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="803bc-156">Not enough memory is available to complete the operation.</span></span> |
| `WBEM_E_SHUTTING_DOWN` | <span data-ttu-id="803bc-157">0x80041033</span><span class="sxs-lookup"><span data-stu-id="803bc-157">0x80041033</span></span> | <span data-ttu-id="803bc-158">WMI는 아마도 중지 및 다시 시작 했습니다.</span><span class="sxs-lookup"><span data-stu-id="803bc-158">WMI was probably stopped and restarting.</span></span> <span data-ttu-id="803bc-159">호출 [ConnectServerWmi](connectserverwmi.md) 다시 합니다.</span><span class="sxs-lookup"><span data-stu-id="803bc-159">Call [ConnectServerWmi](connectserverwmi.md) again.</span></span> |
| `WBEM_E_TRANSPORT_FAILURE` | <span data-ttu-id="803bc-160">0x80041015</span><span class="sxs-lookup"><span data-stu-id="803bc-160">0x80041015</span></span> | <span data-ttu-id="803bc-161">현재 프로세스와 WMI 원격 프로시저 호출 (RPC) 연결 하지 못했습니다.</span><span class="sxs-lookup"><span data-stu-id="803bc-161">The remote procedure call (RPC) link between the current process and WMI has failed.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="803bc-162">0</span><span class="sxs-lookup"><span data-stu-id="803bc-162">0</span></span> | <span data-ttu-id="803bc-163">함수 호출이 성공 했습니다.</span><span class="sxs-lookup"><span data-stu-id="803bc-163">The function call was successful.</span></span>  |

## <a name="remarks"></a><span data-ttu-id="803bc-164">설명</span><span class="sxs-lookup"><span data-stu-id="803bc-164">Remarks</span></span>

<span data-ttu-id="803bc-165">이 함수에 대 한 호출을 래핑하는 [IWbemServices::CreateClassEnum](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemservices-createclassenum) 메서드.</span><span class="sxs-lookup"><span data-stu-id="803bc-165">This function wraps a call to the [IWbemServices::CreateClassEnum](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemservices-createclassenum) method.</span></span>

<span data-ttu-id="803bc-166">함수 호출에 실패 하는 경우 호출 하 여 추가 오류 정보를 얻을 수 있습니다 합니다 [GetErrorInfo](geterrorinfo.md) 함수입니다.</span><span class="sxs-lookup"><span data-stu-id="803bc-166">If the function call fails, you can obtain additional error information by calling the [GetErrorInfo](geterrorinfo.md) function.</span></span>

## <a name="requirements"></a><span data-ttu-id="803bc-167">요구 사항</span><span class="sxs-lookup"><span data-stu-id="803bc-167">Requirements</span></span>

<span data-ttu-id="803bc-168">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="803bc-168">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>

<span data-ttu-id="803bc-169">**헤더:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="803bc-169">**Header:** WMINet_Utils.idl</span></span>

<span data-ttu-id="803bc-170">**.NET Framework 버전:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="803bc-170">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="803bc-171">참고자료</span><span class="sxs-lookup"><span data-stu-id="803bc-171">See also</span></span>

- [<span data-ttu-id="803bc-172">WMI 및 성능 카운터 (관리 되지 않는 API 참조)</span><span class="sxs-lookup"><span data-stu-id="803bc-172">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)