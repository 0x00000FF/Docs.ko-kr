---
title: ICLRRuntimeInfo::GetVersionString 메서드
ms.date: 03/30/2017
api_name:
- ICLRRuntimeInfo.GetVersionString
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRRuntimeInfo::GetVersionString
helpviewer_keywords:
- ICLRRuntimeInfo::GetVersionString method [.NET Framework hosting]
- GetVersionString method, ICLRRuntimeInfo interface [.NET Framework hosting]
ms.assetid: 98b097ef-2276-4dd9-8551-b03c972e8179
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a886106e5da49e7124dac5c8ea7416859aa441da
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2019
ms.locfileid: "69929854"
---
# <a name="iclrruntimeinfogetversionstring-method"></a><span data-ttu-id="80c08-102">ICLRRuntimeInfo::GetVersionString 메서드</span><span class="sxs-lookup"><span data-stu-id="80c08-102">ICLRRuntimeInfo::GetVersionString Method</span></span>
<span data-ttu-id="80c08-103">지정 된 [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) 인터페이스와 연결 된 CLR (공용 언어 런타임) 버전 정보를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="80c08-103">Gets common language runtime (CLR) version information associated with a given [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) interface.</span></span>  
  
 <span data-ttu-id="80c08-104">이 메서드는 다음 함수를 대체 합니다.</span><span class="sxs-lookup"><span data-stu-id="80c08-104">This method supersedes the following functions:</span></span>  
  
- [<span data-ttu-id="80c08-105">GetRequestedRuntimeInfo</span><span class="sxs-lookup"><span data-stu-id="80c08-105">GetRequestedRuntimeInfo</span></span>](../../../../docs/framework/unmanaged-api/hosting/getrequestedruntimeinfo-function.md)  
  
- [<span data-ttu-id="80c08-106">GetRequestedRuntimeVersion</span><span class="sxs-lookup"><span data-stu-id="80c08-106">GetRequestedRuntimeVersion</span></span>](../../../../docs/framework/unmanaged-api/hosting/getrequestedruntimeversion-function.md)  
  
## <a name="syntax"></a><span data-ttu-id="80c08-107">구문</span><span class="sxs-lookup"><span data-stu-id="80c08-107">Syntax</span></span>  
  
```cpp  
HRESULT GetVersionString(  
    [out, size_is(*pcchBuffer)] LPWSTR pwzBuffer,  
    [in, out]  DWORD *pcchBuffer);  
```  
  
## <a name="parameters"></a><span data-ttu-id="80c08-108">매개 변수</span><span class="sxs-lookup"><span data-stu-id="80c08-108">Parameters</span></span>  
 `pwzBuffer`  
 <span data-ttu-id="80c08-109">제한이 "V*A*. 형식의 .NET Framework 컴파일 버전입니다. *B* [. *X*] ".</span><span class="sxs-lookup"><span data-stu-id="80c08-109">[out] The .NET Framework compilation version in the format "v*A*.*B*[.*X*]".</span></span> <span data-ttu-id="80c08-110">*A*, *B*및 *X* 는 주 버전, 부 버전 및 빌드 번호에 해당 하는 10 진수입니다.</span><span class="sxs-lookup"><span data-stu-id="80c08-110">*A*, *B*, and *X* are decimal numbers that correspond to the major version, the minor version, and the build number.</span></span> <span data-ttu-id="80c08-111">*X* 는 선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="80c08-111">*X* is optional.</span></span> <span data-ttu-id="80c08-112">*X* 가 없는 경우에는 후행 기간이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="80c08-112">If *X* is not present, there is no trailing period.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="80c08-113">이 매개 변수는 C:\Windows\Microsoft.NET\Framework. 아래에 표시 되는 .NET Framework 버전의 디렉터리 이름과 일치 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="80c08-113">This parameter must match the directory name for the .NET Framework version, as it appears under C:\Windows\Microsoft.NET\Framework.</span></span>  
  
 <span data-ttu-id="80c08-114">예제 값은 "v v1.0.3705", "v 1.1.4322", "v 2.0.50727" 및 "v 4.0입니다. *x*", 여기서 *x* 는 설치 된 빌드 번호에 따라 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="80c08-114">Example values are "v1.0.3705", "v1.1.4322", "v2.0.50727", and "v4.0.*x*", where *x* depends on the build number installed.</span></span> <span data-ttu-id="80c08-115">"V" 접두사는 필수입니다.</span><span class="sxs-lookup"><span data-stu-id="80c08-115">Note that the "v" prefix is mandatory.</span></span>  
  
 `pchBuffer`  
 <span data-ttu-id="80c08-116">[in, out] 버퍼 오버런을 방지 `pwzBuffer` 하기 위해의 크기를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="80c08-116">[in, out] Specifies the size of `pwzBuffer` to avoid buffer overruns.</span></span> <span data-ttu-id="80c08-117">가 이면 미리 할당을 허용 하기 위해의 `pwzBuffer` 필요한 크기를 반환합니다.`pchBuffer` `null` `pwzBuffer`</span><span class="sxs-lookup"><span data-stu-id="80c08-117">If `pwzBuffer` is `null`, `pchBuffer` returns the required size of `pwzBuffer` to allow preallocation.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="80c08-118">반환 값</span><span class="sxs-lookup"><span data-stu-id="80c08-118">Return Value</span></span>  
 <span data-ttu-id="80c08-119">이 메서드는 다음과 같은 특정 HRESULT뿐만 아니라 메서드 오류를 나타내는 HRESULT 오류도 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="80c08-119">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="80c08-120">HRESULT</span><span class="sxs-lookup"><span data-stu-id="80c08-120">HRESULT</span></span>|<span data-ttu-id="80c08-121">설명</span><span class="sxs-lookup"><span data-stu-id="80c08-121">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="80c08-122">S_OK</span><span class="sxs-lookup"><span data-stu-id="80c08-122">S_OK</span></span>|<span data-ttu-id="80c08-123">메서드가 완료되었습니다.</span><span class="sxs-lookup"><span data-stu-id="80c08-123">The method completed successfully.</span></span>|  
|<span data-ttu-id="80c08-124">E_POINTER</span><span class="sxs-lookup"><span data-stu-id="80c08-124">E_POINTER</span></span>|<span data-ttu-id="80c08-125">`pwzBuffer` 또는 `pchBuffer`이 null입니다.</span><span class="sxs-lookup"><span data-stu-id="80c08-125">`pwzBuffer` or `pchBuffer` is null.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="80c08-126">요구 사항</span><span class="sxs-lookup"><span data-stu-id="80c08-126">Requirements</span></span>  
 <span data-ttu-id="80c08-127">**플랫폼** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="80c08-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="80c08-128">**헤더:** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="80c08-128">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="80c08-129">**라이브러리** Mscoree.dll에 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="80c08-129">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="80c08-130">**.NET Framework 버전:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="80c08-130">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="80c08-131">참고자료</span><span class="sxs-lookup"><span data-stu-id="80c08-131">See also</span></span>

- [<span data-ttu-id="80c08-132">ICLRRuntimeInfo 인터페이스</span><span class="sxs-lookup"><span data-stu-id="80c08-132">ICLRRuntimeInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md)
- [<span data-ttu-id="80c08-133">호스팅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="80c08-133">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
- [<span data-ttu-id="80c08-134">.NET Framework 4 및 4.5에 추가된 CLR 호스팅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="80c08-134">CLR Hosting Interfaces Added in the .NET Framework 4 and 4.5</span></span>](../../../../docs/framework/unmanaged-api/hosting/clr-hosting-interfaces-added-in-the-net-framework-4-and-4-5.md)
- [<span data-ttu-id="80c08-135">호스팅</span><span class="sxs-lookup"><span data-stu-id="80c08-135">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
