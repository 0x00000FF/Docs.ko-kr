---
title: LoadStringRCEx 함수
ms.date: 03/30/2017
api_name:
- LoadStringRCEx
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- LoadStringRCEx
helpviewer_keywords:
- LoadStringRCEx function [.NET Framework hosting]
ms.assetid: bc789636-ca14-4f07-8f77-9305874d7495
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 8ec8e5dfc92a818bfc23c28f3058086c3bd1a8ed
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54597946"
---
# <a name="loadstringrcex-function"></a><span data-ttu-id="0d27f-102">LoadStringRCEx 함수</span><span class="sxs-lookup"><span data-stu-id="0d27f-102">LoadStringRCEx Function</span></span>
<span data-ttu-id="0d27f-103">지정된 된 문화권에 대 한 적절 한 오류 메시지에는 HRESULT 값으로 변환합니다.</span><span class="sxs-lookup"><span data-stu-id="0d27f-103">Translates an HRESULT value to an appropriate error message for the specified culture.</span></span>  
  
 <span data-ttu-id="0d27f-104">이 함수에서 사용 중단에 [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)]합니다.</span><span class="sxs-lookup"><span data-stu-id="0d27f-104">This function has been deprecated in the [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0d27f-105">구문</span><span class="sxs-lookup"><span data-stu-id="0d27f-105">Syntax</span></span>  
  
```  
HRESULT LoadStringRCEx (  
    [in]  LCID    lcid,   
    [in]  UINT    iResouceID,   
    [out] LPWSTR  szBuffer,   
    [in]  int     iMax,   
    [in]  int     bQuiet,   
    [out] int    *pcwchUsed  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="0d27f-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="0d27f-106">Parameters</span></span>  
 `lcid`  
 <span data-ttu-id="0d27f-107">[in] 문화권 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="0d27f-107">[in] A culture identifier.</span></span> <span data-ttu-id="0d27f-108">-1을 전달 `lcid` 를 기본 문화권을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="0d27f-108">Pass -1 for `lcid` to use the default culture.</span></span>  
  
 `iResourceID`  
 <span data-ttu-id="0d27f-109">[in] An HRESULT.</span><span class="sxs-lookup"><span data-stu-id="0d27f-109">[in] An HRESULT.</span></span>  
  
 `szBuffer`  
 <span data-ttu-id="0d27f-110">[out] 성공적으로 완료 되는 오류 메시지를 포함 하는 버퍼입니다.</span><span class="sxs-lookup"><span data-stu-id="0d27f-110">[out] A buffer that contains the error message upon successful completion.</span></span>  
  
 `iMax`  
 <span data-ttu-id="0d27f-111">[in] 오류 메시지 버퍼의 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="0d27f-111">[in] The size of the error message buffer.</span></span>  
  
 `bQuiet`  
 <span data-ttu-id="0d27f-112">[in] Ignored.</span><span class="sxs-lookup"><span data-stu-id="0d27f-112">[in] Ignored.</span></span>  
  
 `pcwchUsed`  
 <span data-ttu-id="0d27f-113">[out] 오류 메시지의 길이에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="0d27f-113">[out] A pointer to the length of the error message.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="0d27f-114">반환 값</span><span class="sxs-lookup"><span data-stu-id="0d27f-114">Return Value</span></span>  
 <span data-ttu-id="0d27f-115">이 메서드는 다음 값 외에도 WinError.h에 정의 된 대로 표준 COM 오류 코드를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="0d27f-115">This method returns standard COM error codes, as defined in WinError.h, in addition to the following values.</span></span>  
  
|<span data-ttu-id="0d27f-116">반환 코드</span><span class="sxs-lookup"><span data-stu-id="0d27f-116">Return code</span></span>|<span data-ttu-id="0d27f-117">설명</span><span class="sxs-lookup"><span data-stu-id="0d27f-117">Description</span></span>|  
|-----------------|-----------------|  
|<span data-ttu-id="0d27f-118">S_OK</span><span class="sxs-lookup"><span data-stu-id="0d27f-118">S_OK</span></span>|<span data-ttu-id="0d27f-119">메서드가 완료되었습니다.</span><span class="sxs-lookup"><span data-stu-id="0d27f-119">The method completed successfully.</span></span>|  
|<span data-ttu-id="0d27f-120">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="0d27f-120">E_INVALIDARG</span></span>|<span data-ttu-id="0d27f-121">`szBuffer` 이 null 또는 `iMax` 은 영 (0).</span><span class="sxs-lookup"><span data-stu-id="0d27f-121">`szBuffer` is null, or `iMax` is zero (0).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0d27f-122">설명</span><span class="sxs-lookup"><span data-stu-id="0d27f-122">Remarks</span></span>  
 <span data-ttu-id="0d27f-123">메서드가 성공적으로 완료 되지 않으면 `szBuffer` 빈 문자열을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="0d27f-123">If the method does not complete successfully, `szBuffer` contains an empty string.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0d27f-124">요구 사항</span><span class="sxs-lookup"><span data-stu-id="0d27f-124">Requirements</span></span>  
 <span data-ttu-id="0d27f-125">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="0d27f-125">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0d27f-126">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="0d27f-126">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="0d27f-127">**라이브러리:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="0d27f-127">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="0d27f-128">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0d27f-128">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0d27f-129">참고자료</span><span class="sxs-lookup"><span data-stu-id="0d27f-129">See also</span></span>
- <xref:System.Globalization.CultureInfo.LCID%2A?displayProperty=nameWithType>
- [<span data-ttu-id="0d27f-130">LoadStringRC 함수</span><span class="sxs-lookup"><span data-stu-id="0d27f-130">LoadStringRC Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/loadstringrc-function.md)
- [<span data-ttu-id="0d27f-131">사용되지 않는 CLR 호스팅 함수</span><span class="sxs-lookup"><span data-stu-id="0d27f-131">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
