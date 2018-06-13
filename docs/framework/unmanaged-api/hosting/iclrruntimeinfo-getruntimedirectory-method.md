---
title: ICLRRuntimeInfo::GetRuntimeDirectory 메서드
ms.date: 03/30/2017
api_name:
- ICLRRuntimeInfo.GetRuntimeDirectory
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRRuntimeInfo::GetRuntimeDirectory
helpviewer_keywords:
- GetRuntimeDirectory method [.NET Framework hosting]
- ICLRRuntimeInfo::GetRuntimeDirectory method [.NET Framework hosting]
ms.assetid: 4401546e-4d48-453f-a1fb-b2ebda54df5c
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f366e736c90ffd8cf588af3a6e5f6240426b9980
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33434527"
---
# <a name="iclrruntimeinfogetruntimedirectory-method"></a><span data-ttu-id="ca723-102">ICLRRuntimeInfo::GetRuntimeDirectory 메서드</span><span class="sxs-lookup"><span data-stu-id="ca723-102">ICLRRuntimeInfo::GetRuntimeDirectory Method</span></span>
<span data-ttu-id="ca723-103">이 인터페이스와 연결 된 공용 언어 런타임 (CLR)의 설치 디렉터리를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="ca723-103">Gets the installation directory of the common language runtime (CLR) associated with this interface.</span></span>  
  
 <span data-ttu-id="ca723-104">이 메서드를 대체는 [GetCORSystemDirectory](../../../../docs/framework/unmanaged-api/hosting/getcorsystemdirectory-function.md) .NET Framework 버전 2.0, 3.0 및 3.5에서에서 제공 하는 함수입니다.</span><span class="sxs-lookup"><span data-stu-id="ca723-104">This method supersedes the [GetCORSystemDirectory](../../../../docs/framework/unmanaged-api/hosting/getcorsystemdirectory-function.md) function provided in the .NET Framework versions 2.0, 3.0, and 3.5.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ca723-105">구문</span><span class="sxs-lookup"><span data-stu-id="ca723-105">Syntax</span></span>  
  
```  
HRESULT GetRuntimeDirectory(  
[out, size_is(*pcchBuffer)] LPWSTR pwzBuffer,  
[in, out]  DWORD *pcchBuffer);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="ca723-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="ca723-106">Parameters</span></span>  
 `pwzBuffer`  
 <span data-ttu-id="ca723-107">[out] CLR 설치 디렉터리를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="ca723-107">[out] Returns the CLR installation directory.</span></span> <span data-ttu-id="ca723-108">설치 경로 정규화 되었습니다. 예를 들어 "c:\windows\microsoft.net\framework\v1.0.3705\\"입니다.</span><span class="sxs-lookup"><span data-stu-id="ca723-108">The installation path is fully qualified; for example, "c:\windows\microsoft.net\framework\v1.0.3705\\".</span></span>  
  
 `pchBuffer`  
 <span data-ttu-id="ca723-109">[out에서] 크기를 지정 `pwzBuffer` 버퍼 오버런을 방지 하기.</span><span class="sxs-lookup"><span data-stu-id="ca723-109">[in, out] Specifies the size of `pwzBuffer` to avoid buffer overruns.</span></span> <span data-ttu-id="ca723-110">경우 `pwzBuffer` 매개 변수가 null 이면 `pchBuffer` 필요한 크기의 반환 `pwzBuffer`합니다.</span><span class="sxs-lookup"><span data-stu-id="ca723-110">If `pwzBuffer` is null, `pchBuffer` returns the required size of `pwzBuffer`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ca723-111">반환 값</span><span class="sxs-lookup"><span data-stu-id="ca723-111">Return Value</span></span>  
 <span data-ttu-id="ca723-112">이 메서드는 다음과 같은 특정 HRESULT뿐만 아니라 메서드 오류를 나타내는 HRESULT 오류도 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="ca723-112">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="ca723-113">HRESULT</span><span class="sxs-lookup"><span data-stu-id="ca723-113">HRESULT</span></span>|<span data-ttu-id="ca723-114">설명</span><span class="sxs-lookup"><span data-stu-id="ca723-114">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="ca723-115">S_OK</span><span class="sxs-lookup"><span data-stu-id="ca723-115">S_OK</span></span>|<span data-ttu-id="ca723-116">메서드가 완료되었습니다.</span><span class="sxs-lookup"><span data-stu-id="ca723-116">The method completed successfully.</span></span>|  
|<span data-ttu-id="ca723-117">E_POINTER</span><span class="sxs-lookup"><span data-stu-id="ca723-117">E_POINTER</span></span>|<span data-ttu-id="ca723-118">`pwzBuffer` 또는 `pchBuffer`이 null입니다.</span><span class="sxs-lookup"><span data-stu-id="ca723-118">`pwzBuffer` or `pchBuffer` is null.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ca723-119">설명</span><span class="sxs-lookup"><span data-stu-id="ca723-119">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ca723-120">요구 사항</span><span class="sxs-lookup"><span data-stu-id="ca723-120">Requirements</span></span>  
 <span data-ttu-id="ca723-121">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="ca723-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ca723-122">**헤더:** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="ca723-122">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="ca723-123">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="ca723-123">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="ca723-124">**.NET framework 버전:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ca723-124">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ca723-125">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ca723-125">See Also</span></span>  
 [<span data-ttu-id="ca723-126">ICLRRuntimeInfo 인터페이스</span><span class="sxs-lookup"><span data-stu-id="ca723-126">ICLRRuntimeInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md)  
 [<span data-ttu-id="ca723-127">호스팅</span><span class="sxs-lookup"><span data-stu-id="ca723-127">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
