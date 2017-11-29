---
title: "GetRequestedRuntimeVersionForCLSID 함수"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: GetRequestedRuntimeVersionForCLSID
api_location: mscoree.dll
api_type: DLLExport
f1_keywords: GetRequestedRuntimeVersionForCLSID
helpviewer_keywords: GetRequestedRuntimeVersionForCLSID function [.NET Framework hosting]
ms.assetid: 5bb12f9a-0612-434b-b4ed-2db636a20bec
topic_type: apiref
caps.latest.revision: "17"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 4a5b9e4b186b6c9b91c1182e8700268f0e1c038f
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="getrequestedruntimeversionforclsid-function"></a><span data-ttu-id="6ccbc-102">GetRequestedRuntimeVersionForCLSID 함수</span><span class="sxs-lookup"><span data-stu-id="6ccbc-102">GetRequestedRuntimeVersionForCLSID Function</span></span>
<span data-ttu-id="6ccbc-103">적절 한 공용 언어 런타임 정보를 가져옵니다 (CLR) 버전 지정 된 클래스에 대 한 `CLSID`합니다.</span><span class="sxs-lookup"><span data-stu-id="6ccbc-103">Gets the appropriate common language runtime (CLR) version information for the class with the specified `CLSID`.</span></span>  
  
 <span data-ttu-id="6ccbc-104">이 함수에 더 이상 사용 되지는 [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)]합니다.</span><span class="sxs-lookup"><span data-stu-id="6ccbc-104">This function has been deprecated in the [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6ccbc-105">구문</span><span class="sxs-lookup"><span data-stu-id="6ccbc-105">Syntax</span></span>  
  
```  
HRESULT GetRequestedRuntimeVersionForCLSID (  
    [in]  REFCLSID   rclsid,   
    [out]  LPWSTR     pVersion,   
    [in]  DWORD      cchBuffer,   
    [out] DWORD*     dwLength,   
    [in]  CLSID_RESOLUTION_FLAGS dwResolutionFlags  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="6ccbc-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="6ccbc-106">Parameters</span></span>  
 `rclsid`  
 <span data-ttu-id="6ccbc-107">[in]  `CLSID` 의 구성 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="6ccbc-107">[in]  The `CLSID` of the component.</span></span>  
  
 `pVersion`  
 <span data-ttu-id="6ccbc-108">[out]  완료 되 면 버전 번호 문자열을 포함 하는 버퍼입니다.</span><span class="sxs-lookup"><span data-stu-id="6ccbc-108">[out]  A buffer that contains the version number string upon successful completion.</span></span>  
  
 `cchBuffer`  
 <span data-ttu-id="6ccbc-109">[in]  와이드 문자에서 크기의는 `pVersion` 버퍼입니다.</span><span class="sxs-lookup"><span data-stu-id="6ccbc-109">[in]  The size, in wide characters, of the `pVersion` buffer.</span></span>  
  
 `dwLength`  
 <span data-ttu-id="6ccbc-110">[out] 반환된 된 버퍼의 길이 (바이트)를 합니다.</span><span class="sxs-lookup"><span data-stu-id="6ccbc-110">[out] The length, in bytes, of the returned buffer.</span></span>  
  
 `dwResolutionFlags`  
 <span data-ttu-id="6ccbc-111">[in]  CLSID_RESOLUTION_FLAGS 값 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="6ccbc-111">[in]  One of the CLSID_RESOLUTION_FLAGS values.</span></span> <span data-ttu-id="6ccbc-112">다음 값이 지원 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6ccbc-112">The following values are supported:</span></span>  
  
-   <span data-ttu-id="6ccbc-113">CLSID_RESOLUTION_DEFAULT: (0x0) 해당 기본 interop 동작을 지정 해야 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="6ccbc-113">CLSID_RESOLUTION_DEFAULT: (0x0) Specifies that default interop behavior should be used.</span></span>  
  
-   <span data-ttu-id="6ccbc-114">CLSID_RESOLUTION_REGISTERED: (0x1) 레지스트리를 검색 하 고 정책 shim을 지정 해야 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6ccbc-114">CLSID_RESOLUTION_REGISTERED: (0x1) Specifies that the registry should be searched and shim policy should be applied.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="6ccbc-115">반환 값</span><span class="sxs-lookup"><span data-stu-id="6ccbc-115">Return Value</span></span>  
  
|<span data-ttu-id="6ccbc-116">HRESULT</span><span class="sxs-lookup"><span data-stu-id="6ccbc-116">HRESULT</span></span>|<span data-ttu-id="6ccbc-117">설명</span><span class="sxs-lookup"><span data-stu-id="6ccbc-117">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="6ccbc-118">S_OK</span><span class="sxs-lookup"><span data-stu-id="6ccbc-118">S_OK</span></span>|<span data-ttu-id="6ccbc-119">함수 반환 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="6ccbc-119">The function returned successfully.</span></span>|  
|<span data-ttu-id="6ccbc-120">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="6ccbc-120">E_INVALIDARG</span></span>|<span data-ttu-id="6ccbc-121">매개 변수 중 하나는 잘못 된 유형 또는 미디어 형식에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6ccbc-121">One of the parameters has an invalid type or format.</span></span>|  
|<span data-ttu-id="6ccbc-122">ERROR_INSUFFICIENT_BUFFER</span><span class="sxs-lookup"><span data-stu-id="6ccbc-122">ERROR_INSUFFICIENT_BUFFER</span></span>|<span data-ttu-id="6ccbc-123">`pVersion` 버퍼를 전체 버전 문자열을 보관할 만큼 크지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6ccbc-123">The `pVersion` buffer is not large enough to hold the entire version string.</span></span>|  
|<span data-ttu-id="6ccbc-124">REGDB_E_CLASSNOTREG</span><span class="sxs-lookup"><span data-stu-id="6ccbc-124">REGDB_E_CLASSNOTREG</span></span>|<span data-ttu-id="6ccbc-125">등록 된 지정 된 클래스가 없습니다 `CLSID`합니다.</span><span class="sxs-lookup"><span data-stu-id="6ccbc-125">There is no class registered with the specified `CLSID`.</span></span>|  
|<span data-ttu-id="6ccbc-126">E_POINTER</span><span class="sxs-lookup"><span data-stu-id="6ccbc-126">E_POINTER</span></span>|<span data-ttu-id="6ccbc-127">`dwLength`매개 변수가 null 이면 또는 `cchBuffer` 버전 문자열을 저장할 수 있도록 충분히 큰 있지만 `pVersion` null입니다.</span><span class="sxs-lookup"><span data-stu-id="6ccbc-127">`dwLength` is null, or `cchBuffer` is large enough to hold the version string, but `pVersion` is null.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="6ccbc-128">요구 사항</span><span class="sxs-lookup"><span data-stu-id="6ccbc-128">Requirements</span></span>  
 <span data-ttu-id="6ccbc-129">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="6ccbc-129">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6ccbc-130">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="6ccbc-130">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="6ccbc-131">**.NET framework 버전:**[!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6ccbc-131">**.NET Framework Versions:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6ccbc-132">참고 항목</span><span class="sxs-lookup"><span data-stu-id="6ccbc-132">See Also</span></span>  
 [<span data-ttu-id="6ccbc-133">사용 되지 않는 CLR 호스팅 함수</span><span class="sxs-lookup"><span data-stu-id="6ccbc-133">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
