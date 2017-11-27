---
title: "CLRCreateInstance 함수"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CLRCreateInstance
api_location:
- mscoree.dll
- mscoreei.dll
api_type: COM
f1_keywords: CLRCreateInstance
helpviewer_keywords: CLRCreateInstance function [.NET Framework hosting]
ms.assetid: 5de13327-96c6-4697-a89e-b8bf40717855
topic_type: apiref
caps.latest.revision: "16"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: f10fe48bc2b61a9de5d0703720629f31531c1ea1
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="clrcreateinstance-function"></a><span data-ttu-id="7e036-102">CLRCreateInstance 함수</span><span class="sxs-lookup"><span data-stu-id="7e036-102">CLRCreateInstance Function</span></span>
<span data-ttu-id="7e036-103">세 가지 인터페이스 중 하나를 제공: [ICLRMetaHost](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-interface.md), [ICLRMetaHostPolicy](../../../../docs/framework/unmanaged-api/hosting/iclrmetahostpolicy-interface.md), 또는 [ICLRDebugging](../../../../docs/framework/unmanaged-api/debugging/iclrdebugging-interface.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="7e036-103">Provides one of three interfaces: [ICLRMetaHost](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-interface.md), [ICLRMetaHostPolicy](../../../../docs/framework/unmanaged-api/hosting/iclrmetahostpolicy-interface.md), or [ICLRDebugging](../../../../docs/framework/unmanaged-api/debugging/iclrdebugging-interface.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7e036-104">구문</span><span class="sxs-lookup"><span data-stu-id="7e036-104">Syntax</span></span>  
  
```  
HRESULT CLRCreateInstance(  
    [in]  REFCLSID  clsid,  
    [in]  REFIID     riid,  
    [out] LPVOID  * ppInterface  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="7e036-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="7e036-105">Parameters</span></span>  
 `clsid`  
 <span data-ttu-id="7e036-106">[in] 세 가지 클래스 식별자 중 하나: CLSID_CLRMetaHost, CLSID_CLRMetaHostPolicy, 또는 CLSID_CLRDebugging 합니다.</span><span class="sxs-lookup"><span data-stu-id="7e036-106">[in] One of three class identifiers: CLSID_CLRMetaHost, CLSID_CLRMetaHostPolicy, or CLSID_CLRDebugging.</span></span>  
  
 `riid`  
 <span data-ttu-id="7e036-107">[in] 세 가지 인터페이스 식별자 (Iid) 중 하나: IID_ICLRMetaHost, IID_ICLRMetaHostPolicy, 또는 IID_ICLRDebugging 합니다.</span><span class="sxs-lookup"><span data-stu-id="7e036-107">[in] One of three interface identifiers (IIDs): IID_ICLRMetaHost, IID_ICLRMetaHostPolicy, or IID_ICLRDebugging.</span></span>  
  
 `ppInterface`  
 <span data-ttu-id="7e036-108">[out] 세 가지 인터페이스 중 하나: [ICLRMetaHost](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-interface.md), [ICLRMetaHostPolicy](../../../../docs/framework/unmanaged-api/hosting/iclrmetahostpolicy-interface.md), 또는 [ICLRDebugging](../../../../docs/framework/unmanaged-api/debugging/iclrdebugging-interface.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="7e036-108">[out] One of three interfaces: [ICLRMetaHost](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-interface.md), [ICLRMetaHostPolicy](../../../../docs/framework/unmanaged-api/hosting/iclrmetahostpolicy-interface.md), or [ICLRDebugging](../../../../docs/framework/unmanaged-api/debugging/iclrdebugging-interface.md).</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="7e036-109">반환 값</span><span class="sxs-lookup"><span data-stu-id="7e036-109">Return Value</span></span>  
 <span data-ttu-id="7e036-110">이 메서드는 다음과 같은 특정 HRESULT뿐만 아니라 메서드 오류를 나타내는 HRESULT 오류도 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="7e036-110">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="7e036-111">HRESULT</span><span class="sxs-lookup"><span data-stu-id="7e036-111">HRESULT</span></span>|<span data-ttu-id="7e036-112">설명</span><span class="sxs-lookup"><span data-stu-id="7e036-112">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="7e036-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="7e036-113">S_OK</span></span>|<span data-ttu-id="7e036-114">메서드가 완료되었습니다.</span><span class="sxs-lookup"><span data-stu-id="7e036-114">The method completed successfully.</span></span>|  
|<span data-ttu-id="7e036-115">E_POINTER</span><span class="sxs-lookup"><span data-stu-id="7e036-115">E_POINTER</span></span>|<span data-ttu-id="7e036-116">`ppInterface`가 null인 경우</span><span class="sxs-lookup"><span data-stu-id="7e036-116">`ppInterface` is null.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7e036-117">설명</span><span class="sxs-lookup"><span data-stu-id="7e036-117">Remarks</span></span>  
 <span data-ttu-id="7e036-118">다음 표에서 지원 되는 조합을 `clsid` 및 `riid`합니다.</span><span class="sxs-lookup"><span data-stu-id="7e036-118">The following table shows the supported combinations for `clsid` and `riid`.</span></span>  
  
|`rclsid`|`riid`|  
|--------------|------------|  
|<span data-ttu-id="7e036-119">CLSID_CLRMetaHost</span><span class="sxs-lookup"><span data-stu-id="7e036-119">CLSID_CLRMetaHost</span></span>|<span data-ttu-id="7e036-120">IID_ICLRMetaHost</span><span class="sxs-lookup"><span data-stu-id="7e036-120">IID_ICLRMetaHost</span></span>|  
|<span data-ttu-id="7e036-121">CLSID_CLRMetaHostPolicy</span><span class="sxs-lookup"><span data-stu-id="7e036-121">CLSID_CLRMetaHostPolicy</span></span>|<span data-ttu-id="7e036-122">IID_ICLRMetaHostPolicy</span><span class="sxs-lookup"><span data-stu-id="7e036-122">IID_ICLRMetaHostPolicy</span></span>|  
|<span data-ttu-id="7e036-123">CLSID_CLRDebugging</span><span class="sxs-lookup"><span data-stu-id="7e036-123">CLSID_CLRDebugging</span></span>|<span data-ttu-id="7e036-124">IID_ICLRDebugging</span><span class="sxs-lookup"><span data-stu-id="7e036-124">IID_ICLRDebugging</span></span>|  
  
 <span data-ttu-id="7e036-125">다음 코드를 사용 하는 방법을 보여 줍니다 `CLRCreateInstance` 모든 세 가지 인터페이스를 얻으려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="7e036-125">The following code shows how to use `CLRCreateInstance` to get all three interfaces:</span></span>  
  
```  
#include <metahost.h>  
#pragma comment(lib, "mscoree.lib")  
  
ICLRMetaHost       *pMetaHost       = NULL;  
ICLRMetaHostPolicy *pMetaHostPolicy = NULL;  
ICLRDebugging      *pCLRDebugging   = NULL;  
HRESULT hr;  
hr = CLRCreateInstance(CLSID_CLRMetaHost, IID_ICLRMetaHost,  
                    (LPVOID*)&pMetaHost);  
hr = CLRCreateInstance (CLSID_CLRMetaHostPolicy, IID_ICLRMetaHostPolicy,  
                    (LPVOID*)&pMetaHostPolicy);  
hr = CLRCreateInstance (CLSID_CLRDebugging, IID_ICLRDebugging,  
                    (LPVOID*)&pCLRDebugging);  
```  
  
## <a name="requirements"></a><span data-ttu-id="7e036-126">요구 사항</span><span class="sxs-lookup"><span data-stu-id="7e036-126">Requirements</span></span>  
 <span data-ttu-id="7e036-127">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="7e036-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7e036-128">**헤더:** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="7e036-128">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="7e036-129">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="7e036-129">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="7e036-130">**.NET framework 버전:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7e036-130">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7e036-131">참고 항목</span><span class="sxs-lookup"><span data-stu-id="7e036-131">See Also</span></span>  
 [<span data-ttu-id="7e036-132">호스팅</span><span class="sxs-lookup"><span data-stu-id="7e036-132">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
