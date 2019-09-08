---
title: ConnectServerWmi 함수 (관리 되지 않는 API 참조)
description: ConnectServerWmi 함수는 DCOM을 사용 하 여 WMI 네임 스페이스에 대 한 연결을 만듭니다.
ms.date: 11/06/2017
api_name:
- ConnectServerWmi
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- ConnectServerWmi
helpviewer_keywords:
- ConnectServerWmi function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2ebb268dcee877f4e9aea0c88852333897030dd1
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/07/2019
ms.locfileid: "70798744"
---
# <a name="connectserverwmi-function"></a><span data-ttu-id="aa5a4-103">ConnectServerWmi 함수</span><span class="sxs-lookup"><span data-stu-id="aa5a4-103">ConnectServerWmi function</span></span>

<span data-ttu-id="aa5a4-104">DCOM 통해 지정된 컴퓨터의 WMI 네임스페이스에 대한 연결을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="aa5a4-104">Creates a connection through DCOM to a WMI namespace on a specified computer.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a><span data-ttu-id="aa5a4-105">구문</span><span class="sxs-lookup"><span data-stu-id="aa5a4-105">Syntax</span></span>

```cpp
HRESULT ConnectServerWmi (
   [in] BSTR               strNetworkResource,
   [in] BSTR               strUser,
   [in] BSTR               strPassword,
   [in] BSTR               strLocale,
   [in] long               lSecurityFlags,
   [in] BSTR               strAuthority,
   [in] IWbemContext*      pCtx,
   [out] IWbemServices**   ppNamespace,
   [in] DWORD              impLevel,
   [in] DWORD              authLevel
);
```

## <a name="parameters"></a><span data-ttu-id="aa5a4-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="aa5a4-106">Parameters</span></span>

`strNetworkResource`\
<span data-ttu-id="aa5a4-107">진행 올바른 WMI 네임 스페이스 `BSTR` 의 개체 경로를 포함 하는 유효한에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="aa5a4-107">[in] Pointer to a valid `BSTR` that contains the object path of the correct WMI namespace.</span></span> <span data-ttu-id="aa5a4-108">자세한 내용은 [설명](#remarks) 부분을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="aa5a4-108">See the [Remarks](#remarks) section for more information.</span></span>

`strUser`\
<span data-ttu-id="aa5a4-109">진행 사용자 이름이 포함 된 유효한 `BSTR` 에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="aa5a4-109">[in] A pointer to a valid `BSTR` that contains the user name.</span></span> <span data-ttu-id="aa5a4-110">현재 보안 컨텍스트를 나타내는 값입니다.`null`</span><span class="sxs-lookup"><span data-stu-id="aa5a4-110">A `null` value indicates the current security context.</span></span> <span data-ttu-id="aa5a4-111">사용자가 현재 사용자와 다른 도메인에 있는 경우에 `strUser` 는 도메인 및 사용자 이름을 백슬래시로 구분 하 여 포함할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aa5a4-111">If the user is from a different domain than the current one, `strUser` can also contain the domain and user name separated by a backslash.</span></span> <span data-ttu-id="aa5a4-112">`strUser`는와 `userName@domainName`같은 UPN (사용자 계정 이름) 형식으로도 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aa5a4-112">`strUser` can also be in user principal name (UPN) format, such as `userName@domainName`.</span></span> <span data-ttu-id="aa5a4-113">자세한 내용은 [설명](#remarks) 부분을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="aa5a4-113">See the [Remarks](#remarks) section for more information.</span></span>

`strPassword`\
<span data-ttu-id="aa5a4-114">진행 암호가 포함 된 유효한 `BSTR` 에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="aa5a4-114">[in] A pointer to a valid `BSTR` that contains the password.</span></span> <span data-ttu-id="aa5a4-115">는 `null` 현재 보안 컨텍스트를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="aa5a4-115">A `null` indicates the current security context.</span></span> <span data-ttu-id="aa5a4-116">빈 문자열 ("")은 길이가 0 인 유효한 암호를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="aa5a4-116">An empty string ("") indicates a valid zero-length password.</span></span>

`strLocale`\
<span data-ttu-id="aa5a4-117">진행 정보 검색의 올바른 로캘을 `BSTR` 나타내는 유효한에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="aa5a4-117">[in] A pointer to a valid `BSTR` that indicates the correct locale for information retrieval.</span></span> <span data-ttu-id="aa5a4-118">Microsoft 로캘 식별자의 경우 문자열의 형식은 "MS\_*xxx*"입니다. 여기서 *xxx* 는 LCID (로캘 id)를 나타내는 16 진수 형식의 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="aa5a4-118">For Microsoft locale identifiers, the format of the string is "MS\_*xxx*", where *xxx* is a string in hexadecimal form that indicates the locale identifier (LCID).</span></span> <span data-ttu-id="aa5a4-119">잘못 된 로캘이 지정 된 경우 메서드는 Windows 7 `WBEM_E_INVALID_PARAMETER` 을 제외 하 고를 반환 합니다 .이 경우 서버 기본 로캘이 대신 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="aa5a4-119">If an invalid locale is specified, the method returns `WBEM_E_INVALID_PARAMETER` except on Windows 7, where the default locale of the server is used instead.</span></span> <span data-ttu-id="aa5a4-120">' Null1 ' 이면 현재 로캘이 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="aa5a4-120">If \`null1, the current locale is used.</span></span>

`lSecurityFlags`\
<span data-ttu-id="aa5a4-121">진행 `ConnectServerWmi` 메서드에 전달할 플래그입니다.</span><span class="sxs-lookup"><span data-stu-id="aa5a4-121">[in] Flags to pass to the `ConnectServerWmi` method.</span></span> <span data-ttu-id="aa5a4-122">이 매개 변수의 값이 0 이면 서버에 대 한 연결이 설정 된 후 `ConnectServerWmi` 에만를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="aa5a4-122">A value of zero (0) for this parameter results in the call to `ConnectServerWmi` returning only after a connection to the server is established.</span></span> <span data-ttu-id="aa5a4-123">이로 인해 서버가 중단 되 면 응용 프로그램이 무기한 응답 하지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aa5a4-123">This could result in an application not responding indefinitely if the server is broken.</span></span> <span data-ttu-id="aa5a4-124">다른 유효한 값은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="aa5a4-124">The other valid values are:</span></span>

| <span data-ttu-id="aa5a4-125">상수</span><span class="sxs-lookup"><span data-stu-id="aa5a4-125">Constant</span></span>  | <span data-ttu-id="aa5a4-126">값</span><span class="sxs-lookup"><span data-stu-id="aa5a4-126">Value</span></span>  | <span data-ttu-id="aa5a4-127">설명</span><span class="sxs-lookup"><span data-stu-id="aa5a4-127">Description</span></span>  |
|---------|---------|---------|
| `CONNECT_REPOSITORY_ONLY` | <span data-ttu-id="aa5a4-128">0x40</span><span class="sxs-lookup"><span data-stu-id="aa5a4-128">0x40</span></span> | <span data-ttu-id="aa5a4-129">내부용으로 예약됩니다.</span><span class="sxs-lookup"><span data-stu-id="aa5a4-129">Reserved for internal use.</span></span> <span data-ttu-id="aa5a4-130">사용하지 마십시오.</span><span class="sxs-lookup"><span data-stu-id="aa5a4-130">Do not use.</span></span> |
| `WBEM_FLAG_CONNECT_USE_MAX_WAIT` | <span data-ttu-id="aa5a4-131">0x80</span><span class="sxs-lookup"><span data-stu-id="aa5a4-131">0x80</span></span> | <span data-ttu-id="aa5a4-132">`ConnectServerWmi`2 분 이내에 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="aa5a4-132">`ConnectServerWmi` returns in two minutes or less.</span></span> |

`strAuthority`\
<span data-ttu-id="aa5a4-133">진행 사용자의 도메인 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="aa5a4-133">[in] The domain name of the user.</span></span> <span data-ttu-id="aa5a4-134">다음 값을 가질 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aa5a4-134">It can have the following values:</span></span>

| <span data-ttu-id="aa5a4-135">값</span><span class="sxs-lookup"><span data-stu-id="aa5a4-135">Value</span></span> | <span data-ttu-id="aa5a4-136">설명</span><span class="sxs-lookup"><span data-stu-id="aa5a4-136">Description</span></span> |
|---------|---------|
| <span data-ttu-id="aa5a4-137">비어 있음</span><span class="sxs-lookup"><span data-stu-id="aa5a4-137">blank</span></span> | <span data-ttu-id="aa5a4-138">NTLM 인증을 사용 하 고 현재 사용자의 NTLM 도메인을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="aa5a4-138">NTLM authentication is used, and the NTLM domain of the current user is used.</span></span> <span data-ttu-id="aa5a4-139">에서 `strUser` 도메인을 지정 하는 경우 (권장 위치) 여기에서 지정 하면 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="aa5a4-139">If `strUser` specifies the domain (the recommended location), it must not be specified here.</span></span> <span data-ttu-id="aa5a4-140">이 함수는 `WBEM_E_INVALID_PARAMETER` 두 매개 변수 모두에 도메인을 지정 하는 경우를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="aa5a4-140">The function returns `WBEM_E_INVALID_PARAMETER` if you specify the domain in both parameters.</span></span> |
| <span data-ttu-id="aa5a4-141">Kerberos:*보안 주체 이름*</span><span class="sxs-lookup"><span data-stu-id="aa5a4-141">Kerberos:*principal name*</span></span> | <span data-ttu-id="aa5a4-142">Kerberos 인증을 사용 하며,이 매개 변수에는 Kerberos 사용자 이름이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="aa5a4-142">Kerberos authentication is used, and this parameter contains a Kerberos principal name.</span></span> |
| <span data-ttu-id="aa5a4-143">NTLMDOMAIN:*도메인 이름*</span><span class="sxs-lookup"><span data-stu-id="aa5a4-143">NTLMDOMAIN:*domain name*</span></span> | <span data-ttu-id="aa5a4-144">NT LAN Manager 인증을 사용 하며이 매개 변수에는 NTLM 도메인 이름이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="aa5a4-144">NT LAN Manager authentication is used, and this parameter contains an NTLM domain name.</span></span> |

`pCtx`\
<span data-ttu-id="aa5a4-145">진행 일반적으로이 매개 변수 `null`는입니다.</span><span class="sxs-lookup"><span data-stu-id="aa5a4-145">[in] Typically, this parameter is `null`.</span></span> <span data-ttu-id="aa5a4-146">그렇지 않으면 하나 이상의 동적 클래스 공급자가 필요로 하는 [iwbemcontext 개체가 올바르지](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemcontext) 개체에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="aa5a4-146">Otherwise, it is a pointer to an [IWbemContext](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemcontext) object required by one or more dynamic class providers.</span></span>

`ppNamespace`\
<span data-ttu-id="aa5a4-147">제한이 함수가 반환 될 때 지정 된 네임 스페이스에 바인딩된 [IWbemServices](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemservices) 개체에 대 한 포인터를 수신 합니다.</span><span class="sxs-lookup"><span data-stu-id="aa5a4-147">[out] When the function returns, receives a pointer to an [IWbemServices](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemservices) object bound to the specified namespace.</span></span> <span data-ttu-id="aa5a4-148">오류가 있는 경우를 `null` 가리키도록 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="aa5a4-148">It is set to point to `null` when there is an error.</span></span>

`impLevel`\
<span data-ttu-id="aa5a4-149">진행 가장 수준입니다.</span><span class="sxs-lookup"><span data-stu-id="aa5a4-149">[in] The impersonation level.</span></span>

`authLevel`\
<span data-ttu-id="aa5a4-150">진행 권한 수준입니다.</span><span class="sxs-lookup"><span data-stu-id="aa5a4-150">[in] The authorization level.</span></span>

## <a name="return-value"></a><span data-ttu-id="aa5a4-151">반환 값</span><span class="sxs-lookup"><span data-stu-id="aa5a4-151">Return value</span></span>

<span data-ttu-id="aa5a4-152">이 함수에서 반환 되는 다음 값은 *WbemCli* 헤더 파일에 정의 되어 있거나 코드에서 상수로 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aa5a4-152">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="aa5a4-153">상수</span><span class="sxs-lookup"><span data-stu-id="aa5a4-153">Constant</span></span>  |<span data-ttu-id="aa5a4-154">값</span><span class="sxs-lookup"><span data-stu-id="aa5a4-154">Value</span></span>  |<span data-ttu-id="aa5a4-155">Description</span><span class="sxs-lookup"><span data-stu-id="aa5a4-155">Description</span></span>  |
|---------|---------|---------|
| `WBEM_E_FAILED` | <span data-ttu-id="aa5a4-156">0x80041001</span><span class="sxs-lookup"><span data-stu-id="aa5a4-156">0x80041001</span></span> | <span data-ttu-id="aa5a4-157">일반 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="aa5a4-157">There has been a general failure.</span></span> |
| `WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="aa5a4-158">0x80041008</span><span class="sxs-lookup"><span data-stu-id="aa5a4-158">0x80041008</span></span> | <span data-ttu-id="aa5a4-159">매개 변수가 잘못 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="aa5a4-159">A parameter is not valid.</span></span> |
| `WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="aa5a4-160">0x80041006</span><span class="sxs-lookup"><span data-stu-id="aa5a4-160">0x80041006</span></span> | <span data-ttu-id="aa5a4-161">메모리가 부족 하 여 작업을 완료할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="aa5a4-161">Not enough memory is available to complete the operation.</span></span> |
| `WBEM_S_NO_ERROR` | <span data-ttu-id="aa5a4-162">0</span><span class="sxs-lookup"><span data-stu-id="aa5a4-162">0</span></span> | <span data-ttu-id="aa5a4-163">함수 호출에 성공 했습니다.</span><span class="sxs-lookup"><span data-stu-id="aa5a4-163">The function call was successful.</span></span>  |

## <a name="remarks"></a><span data-ttu-id="aa5a4-164">설명</span><span class="sxs-lookup"><span data-stu-id="aa5a4-164">Remarks</span></span>

<span data-ttu-id="aa5a4-165">이 함수는 [IWbemLocator:: ConnectServer](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemlocator-connectserver) 메서드에 대 한 호출을 래핑합니다.</span><span class="sxs-lookup"><span data-stu-id="aa5a4-165">This function wraps a call to the [IWbemLocator::ConnectServer](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemlocator-connectserver) method.</span></span>

<span data-ttu-id="aa5a4-166">기본 네임 스페이스 `strNetworkResource` 에 대 한 로컬 액세스의 경우는 간단한 개체 경로 ("root\default" 또는 "\\.\root\default") 일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aa5a4-166">For local access to the default namespace, `strNetworkResource` can be a simple object path: "root\default" or "\\.\root\default".</span></span> <span data-ttu-id="aa5a4-167">COM 또는 Microsoft 호환 네트워킹을 사용 하는 원격 컴퓨터의 기본 네임 스페이스에 액세스 하려면 컴퓨터 이름 "\\myserver\root\default"를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="aa5a4-167">For access to the default namespace on a remote computer using COM or Microsoft-compatible networking, include the computer name: "\\myserver\root\default".</span></span> <span data-ttu-id="aa5a4-168">컴퓨터 이름은 DNS 이름 또는 IP 주소일 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aa5a4-168">The computer name also can be a DNS name or IP address.</span></span> <span data-ttu-id="aa5a4-169">이 `ConnectServerWmi` 함수는 ipv6 주소를 사용 하 여 i p v 6을 실행 하는 컴퓨터에 연결할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aa5a4-169">The `ConnectServerWmi` function can also connect with computers running IPv6 using an IPv6 address.</span></span>

<span data-ttu-id="aa5a4-170">`strUser`는 빈 문자열일 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="aa5a4-170">`strUser` cannot be an empty string.</span></span> <span data-ttu-id="aa5a4-171">에서 `strAuthority`지정 된 도메인은에 `strUser`포함 되지 않아야 합니다. 그렇지 않으면 함수가를 반환 `WBEM_E_INVALID_PARAMETER`합니다.</span><span class="sxs-lookup"><span data-stu-id="aa5a4-171">If the domain is specified in `strAuthority`, it must not also be included in `strUser`, or the function returns `WBEM_E_INVALID_PARAMETER`.</span></span>

## <a name="requirements"></a><span data-ttu-id="aa5a4-172">요구 사항</span><span class="sxs-lookup"><span data-stu-id="aa5a4-172">Requirements</span></span>

 <span data-ttu-id="aa5a4-173">**플랫폼** [시스템 요구 사항](../../get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="aa5a4-173">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>

 <span data-ttu-id="aa5a4-174">**헤더:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="aa5a4-174">**Header:** WMINet_Utils.idl</span></span>

 <span data-ttu-id="aa5a4-175">**.NET Framework 버전:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="aa5a4-175">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="aa5a4-176">참고자료</span><span class="sxs-lookup"><span data-stu-id="aa5a4-176">See also</span></span>

- [<span data-ttu-id="aa5a4-177">WMI 및 성능 카운터 (관리 되지 않는 API 참조)</span><span class="sxs-lookup"><span data-stu-id="aa5a4-177">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
