---
title: BlessIWbemServicesObject 함수 (관리 되지 않는 API 참조)
description: BlessIWbemServicesObject 함수 사용자 자격 증명이 IWbemServices 개체에 대 한 액세스를 허용 하는지 여부를 나타냅니다.
ms.date: 11/06/2017
api_name:
- BlessIWbemServicesObject
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- BlessIWbemServicesObject
helpviewer_keywords:
- BlessIWbemServicesObject function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a561c5af868968624ee9ee81050d87b17c4591be
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54624420"
---
# <a name="blessiwbemservicesobject-function"></a><span data-ttu-id="9e737-103">BlessIWbemServicesObject 함수</span><span class="sxs-lookup"><span data-stu-id="9e737-103">BlessIWbemServicesObject function</span></span>
<span data-ttu-id="9e737-104">사용자 자격 증명을 지정 된 액세스를 허용 하는지 여부를 나타냅니다 [IWbemServices](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemservices) 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="9e737-104">Indicates whether the user credentials permit access to a specified [IWbemServices](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemservices) object.</span></span>   
  
[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="9e737-105">구문</span><span class="sxs-lookup"><span data-stu-id="9e737-105">Syntax</span></span>  
  
```  
HRESULT BlessIWbemServicesObject (
   [in] IUnknown* pIUnknown,
   [in] BSTR strUser, 
   [in] BSTR strPassword, 
   [in] BSTR strAuthority, 
   [in] DWORD impLevel, 
   [in] DWORD authnLevel
);
```  

## <a name="parameters"></a><span data-ttu-id="9e737-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="9e737-106">Parameters</span></span>

`pIWbemServices`  
<span data-ttu-id="9e737-107">[in] WMI 서비스 개체에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="9e737-107">[in] A pointer to a WMI service object.</span></span>

`strUser`  
<span data-ttu-id="9e737-108">[in] 사용자 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="9e737-108">[in] The user name.</span></span>

`strPassword`  
<span data-ttu-id="9e737-109">[in] 연결 된 암호 `strUser`합니다.</span><span class="sxs-lookup"><span data-stu-id="9e737-109">[in] The password associated with `strUser`.</span></span>

<span data-ttu-id="9e737-110">`strAuthority` [in] 사용자의 도메인 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="9e737-110">`strAuthority` [in] The domain name of the user.</span></span> <span data-ttu-id="9e737-111">참조 된 [ConnectServerWmi](connectserverwmi.md) 자세한 함수입니다.</span><span class="sxs-lookup"><span data-stu-id="9e737-111">See the [ConnectServerWmi](connectserverwmi.md) function for more information.</span></span>

<span data-ttu-id="9e737-112">`impLevel` [in] 가장 수준입니다.</span><span class="sxs-lookup"><span data-stu-id="9e737-112">`impLevel` [in] The impersonation level.</span></span>

<span data-ttu-id="9e737-113">`authnLevel` [in] 권한 부여 수준입니다.</span><span class="sxs-lookup"><span data-stu-id="9e737-113">`authnLevel` [in] The authorization level.</span></span>

## <a name="return-value"></a><span data-ttu-id="9e737-114">반환 값</span><span class="sxs-lookup"><span data-stu-id="9e737-114">Return value</span></span>

<span data-ttu-id="9e737-115">이 함수에 의해 반환 되는 다음 값에 정의 된 합니다 *WinError.h* 헤더 파일에서 정의할 수 상수로 코드:</span><span class="sxs-lookup"><span data-stu-id="9e737-115">The following values returned by this function are defined in the *WinError.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="9e737-116">상수</span><span class="sxs-lookup"><span data-stu-id="9e737-116">Constant</span></span>  |<span data-ttu-id="9e737-117">값</span><span class="sxs-lookup"><span data-stu-id="9e737-117">Value</span></span>  |<span data-ttu-id="9e737-118">설명</span><span class="sxs-lookup"><span data-stu-id="9e737-118">Description</span></span>  |
|---------|---------|---------|
| `E_INVALIDARG` | <span data-ttu-id="9e737-119">0x80070057</span><span class="sxs-lookup"><span data-stu-id="9e737-119">0x80070057</span></span> | <span data-ttu-id="9e737-120">하나 이상의 인수가 잘못 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="9e737-120">One or more arguments are invalid.</span></span> |
| `E_POINTER` | <span data-ttu-id="9e737-121">0x80004003</span><span class="sxs-lookup"><span data-stu-id="9e737-121">0x80004003</span></span> | <span data-ttu-id="9e737-122">`pIWbemServices`가 `null`인 경우</span><span class="sxs-lookup"><span data-stu-id="9e737-122">`pIWbemServices` is `null`.</span></span> | 
| `E_FAIL` | <span data-ttu-id="9e737-123">0x80000008</span><span class="sxs-lookup"><span data-stu-id="9e737-123">0x80000008</span></span> | <span data-ttu-id="9e737-124">지정 되지 않은 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="9e737-124">An unspecified error has occurred.</span></span> |
| `E_OUTOFMEMORY` | <span data-ttu-id="9e737-125">0x80000002</span><span class="sxs-lookup"><span data-stu-id="9e737-125">0x80000002</span></span> | <span data-ttu-id="9e737-126">메모리가 부족 하 여 작업을 수행할 수 있는 경우</span><span class="sxs-lookup"><span data-stu-id="9e737-126">Insufficient memory is available to perform the operation.</span></span> | 
| `S_OK` | <span data-ttu-id="9e737-127">0</span><span class="sxs-lookup"><span data-stu-id="9e737-127">0</span></span> | <span data-ttu-id="9e737-128">함수 호출이 성공 했습니다.</span><span class="sxs-lookup"><span data-stu-id="9e737-128">The function call was successful.</span></span> | 

## <a name="requirements"></a><span data-ttu-id="9e737-129">요구 사항</span><span class="sxs-lookup"><span data-stu-id="9e737-129">Requirements</span></span>  
 <span data-ttu-id="9e737-130">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="9e737-130">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9e737-131">**헤더:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="9e737-131">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="9e737-132">**.NET Framework 버전:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="9e737-132">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9e737-133">참고자료</span><span class="sxs-lookup"><span data-stu-id="9e737-133">See also</span></span>
- [<span data-ttu-id="9e737-134">WMI 및 성능 카운터 (관리 되지 않는 API 참조)</span><span class="sxs-lookup"><span data-stu-id="9e737-134">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
