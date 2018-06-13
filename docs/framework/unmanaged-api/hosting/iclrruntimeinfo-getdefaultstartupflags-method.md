---
title: ICLRRuntimeInfo::GetDefaultStartupFlags 메서드
ms.date: 03/30/2017
api_name:
- ICLRRuntimeInfo.GetDefaultStartupFlags
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRRuntimeInfo::GetDefaultStartupFlags
helpviewer_keywords:
- ICLRRuntimeInfo::GetDefaultStartupFlags method [.NET Framework hosting]
- GetDefaultStartupFlags method [.NET Framework hosting]
ms.assetid: 35c2173e-3b0b-4b2a-950d-e0a01c6df052
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 546a26306a1faaeceb1337b79bd2d27970d9f5be
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33434215"
---
# <a name="iclrruntimeinfogetdefaultstartupflags-method"></a><span data-ttu-id="49404-102">ICLRRuntimeInfo::GetDefaultStartupFlags 메서드</span><span class="sxs-lookup"><span data-stu-id="49404-102">ICLRRuntimeInfo::GetDefaultStartupFlags Method</span></span>
<span data-ttu-id="49404-103">시작 플래그와 런타임을 시작 하는 호스트 구성 파일을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="49404-103">Gets the startup flags and host configuration file that will be used to start the runtime.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="49404-104">구문</span><span class="sxs-lookup"><span data-stu-id="49404-104">Syntax</span></span>  
  
```  
HRESULT GetDefaultStartupFlags(  
     [out]  DWORD *pdwStartupFlags,  
     [out, size_is(*pcchHostConfigFile)] LPWSTR pwzHostConfigFile,  
     [in, out]  DWORD *pcchHostConfigFile);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="49404-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="49404-105">Parameters</span></span>  
 `pdwStartupFlags`  
 <span data-ttu-id="49404-106">[out] 현재 설정 되어 있는 호스트 시작 플래그에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="49404-106">[out] A pointer to the host startup flags that are currently set.</span></span>  
  
 `pwzHostConfigFile`  
 <span data-ttu-id="49404-107">[out] 현재 호스트 구성 파일의 디렉터리 경로에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="49404-107">[out] A pointer to the directory path of the current host configuration file.</span></span>  
  
 `pcchHostConfigFile`  
 <span data-ttu-id="49404-108">[out에서] 입력에 크기 `pwzHostConfigFile`버퍼 오버런을 방지 하려면.</span><span class="sxs-lookup"><span data-stu-id="49404-108">[in, out] On input, the size of `pwzHostConfigFile`, to avoid buffer overruns.</span></span> <span data-ttu-id="49404-109">경우 `pwzHostConfigFile` 가 null 인 메서드가 필요한 크기의 `pwzHostConfigFile` 사전 할당에 대 한 합니다.</span><span class="sxs-lookup"><span data-stu-id="49404-109">If `pwzHostConfigFile` is null, the method returns the required size of `pwzHostConfigFile` for pre-allocation.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="49404-110">반환 값</span><span class="sxs-lookup"><span data-stu-id="49404-110">Return Value</span></span>  
 <span data-ttu-id="49404-111">이 메서드는 다음과 같은 특정 HRESULT를 반환 합니다. 메서드 오류를 나타내는 HRESULT 오류도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="49404-111">This method returns the following specific HRESULT as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="49404-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="49404-112">HRESULT</span></span>|<span data-ttu-id="49404-113">설명</span><span class="sxs-lookup"><span data-stu-id="49404-113">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="49404-114">S_OK</span><span class="sxs-lookup"><span data-stu-id="49404-114">S_OK</span></span>|<span data-ttu-id="49404-115">메서드가 완료되었습니다.</span><span class="sxs-lookup"><span data-stu-id="49404-115">The method completed successfully.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="49404-116">설명</span><span class="sxs-lookup"><span data-stu-id="49404-116">Remarks</span></span>  
 <span data-ttu-id="49404-117">이 메서드는 기본 플래그 값을 반환 (`STARTUP_CONCURRENT_GC` 및 `NULL`), 또는 대 한 이전 호출에서 제공 하는 값은 [iclrruntimeinfo:: Setdefaultstartupflags 메서드](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-setdefaultstartupflags-method.md), 또는 중 하나에 의해 설정 값은 `CorBind*` 메서드를이 런타임에 바인딩된 경우를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="49404-117">This method returns the default flag values (`STARTUP_CONCURRENT_GC` and `NULL`), or the values provided by a previous call to the [ICLRRuntimeInfo::SetDefaultStartupFlags method](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-setdefaultstartupflags-method.md), or the values set by any of the `CorBind*` methods if they are bound to this runtime.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="49404-118">요구 사항</span><span class="sxs-lookup"><span data-stu-id="49404-118">Requirements</span></span>  
 <span data-ttu-id="49404-119">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="49404-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="49404-120">**헤더:** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="49404-120">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="49404-121">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="49404-121">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="49404-122">**.NET framework 버전:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="49404-122">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="49404-123">참고 항목</span><span class="sxs-lookup"><span data-stu-id="49404-123">See Also</span></span>  
 [<span data-ttu-id="49404-124">ICLRRuntimeInfo 인터페이스</span><span class="sxs-lookup"><span data-stu-id="49404-124">ICLRRuntimeInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md)  
 [<span data-ttu-id="49404-125">호스팅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="49404-125">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)  
 [<span data-ttu-id="49404-126">호스팅</span><span class="sxs-lookup"><span data-stu-id="49404-126">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
