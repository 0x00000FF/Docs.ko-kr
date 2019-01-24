---
title: GetRequestedRuntimeInfo 함수
ms.date: 03/30/2017
api_name:
- GetRequestedRuntimeInfo
api_location:
- mscoree.dll
- mscoreei.dll
api_type:
- DLLExport
f1_keywords:
- GetRequestedRuntimeInfo
helpviewer_keywords:
- GetRequestedRuntimeInfo function [.NET Framework hosting]
ms.assetid: 0dfd7cdc-c116-4e25-b56a-ac7b0378c942
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 51cd834b92dd595b5b3e7f668ef252462f4287de
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54695285"
---
# <a name="getrequestedruntimeinfo-function"></a><span data-ttu-id="5f07a-102">GetRequestedRuntimeInfo 함수</span><span class="sxs-lookup"><span data-stu-id="5f07a-102">GetRequestedRuntimeInfo Function</span></span>
<span data-ttu-id="5f07a-103">버전 및 디렉터리는 CLR (공용 언어 런타임) 응용 프로그램에서 요청한 정보를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="5f07a-103">Gets version and directory information about the common language runtime (CLR) requested by an application.</span></span>  
  
 <span data-ttu-id="5f07a-104">이 함수에서 사용 중단에 [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)]합니다.</span><span class="sxs-lookup"><span data-stu-id="5f07a-104">This function has been deprecated in the [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5f07a-105">구문</span><span class="sxs-lookup"><span data-stu-id="5f07a-105">Syntax</span></span>  
  
```  
HRESULT GetRequestedRuntimeInfo (  
    [in]  LPCWSTR  pExe,   
    [in]  LPCWSTR  pwszVersion,   
    [in]  LPCWSTR  pConfigurationFile,   
    [in]  DWORD    startupFlags,   
    [in]  DWORD    runtimeInfoFlags,   
    [out] LPWSTR   pDirectory,   
    [in]  DWORD    dwDirectory,   
    [out] DWORD   *dwDirectoryLength,   
    [out] LPWSTR   pVersion,   
    [in]  DWORD    cchBuffer,   
    [out] DWORD   *dwlength  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="5f07a-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="5f07a-106">Parameters</span></span>  
 `pExe`  
 <span data-ttu-id="5f07a-107">[in] 응용 프로그램의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="5f07a-107">[in] The name of the application.</span></span>  
  
 `pwszVersion`  
 <span data-ttu-id="5f07a-108">[in] 런타임의 버전 번호를 지정 하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="5f07a-108">[in] A string specifying the version number of the runtime.</span></span>  
  
 `pConfigurationFile`  
 <span data-ttu-id="5f07a-109">[in] 연결 된 구성 파일의 이름을 `pExe`입니다.</span><span class="sxs-lookup"><span data-stu-id="5f07a-109">[in] The name of the configuration file that is associated with `pExe`.</span></span>  
  
 `startupFlags`  
 <span data-ttu-id="5f07a-110">[in] 하나 이상의 합니다 [STARTUP_FLAGS](../../../../docs/framework/unmanaged-api/hosting/startup-flags-enumeration.md) 열거형 값입니다.</span><span class="sxs-lookup"><span data-stu-id="5f07a-110">[in] One or more of the [STARTUP_FLAGS](../../../../docs/framework/unmanaged-api/hosting/startup-flags-enumeration.md) enumeration values.</span></span>  
  
 `runtimeInfoFlags`  
 <span data-ttu-id="5f07a-111">[in] 하나 이상의 합니다 [RUNTIME_INFO_FLAGS](../../../../docs/framework/unmanaged-api/hosting/runtime-info-flags-enumeration.md) 열거형 값입니다.</span><span class="sxs-lookup"><span data-stu-id="5f07a-111">[in] One or more of the [RUNTIME_INFO_FLAGS](../../../../docs/framework/unmanaged-api/hosting/runtime-info-flags-enumeration.md) enumeration values.</span></span>  
  
 `pDirectory`  
 <span data-ttu-id="5f07a-112">[out] 완료 되 면 런타임에 대 한 디렉터리 경로 포함 하는 버퍼입니다.</span><span class="sxs-lookup"><span data-stu-id="5f07a-112">[out] A buffer that contains the directory path to the runtime upon successful completion.</span></span>  
  
 `dwDirectory`  
 <span data-ttu-id="5f07a-113">[in] Directory 버퍼의 길이입니다.</span><span class="sxs-lookup"><span data-stu-id="5f07a-113">[in] The length of the directory buffer.</span></span>  
  
 `dwDirectoryLength`  
 <span data-ttu-id="5f07a-114">[out] 디렉터리 경로 문자열의 길이에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="5f07a-114">[out] A pointer to the length of the directory path string.</span></span>  
  
 `pVersion`  
 <span data-ttu-id="5f07a-115">[out] 성공적으로 완료 되는 런타임의 버전 번호를 포함 하는 버퍼입니다.</span><span class="sxs-lookup"><span data-stu-id="5f07a-115">[out] A buffer that contains the version number of the runtime upon successful completion.</span></span>  
  
 `cchBuffer`  
 <span data-ttu-id="5f07a-116">[in] 버전 문자열 버퍼의 길이입니다.</span><span class="sxs-lookup"><span data-stu-id="5f07a-116">[in] The length of the version string buffer.</span></span>  
  
 `dwlength`  
 <span data-ttu-id="5f07a-117">[out] 버전 문자열의 길이에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="5f07a-117">[out] A pointer to the length of the version string.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="5f07a-118">반환 값</span><span class="sxs-lookup"><span data-stu-id="5f07a-118">Return Value</span></span>  
 <span data-ttu-id="5f07a-119">이 메서드는 다음 값 외에도 WinError.h에 정의 된 대로 표준 구성 요소 개체 모델 (COM) 오류 코드를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="5f07a-119">This method returns standard Component Object Model (COM) error codes, as defined in WinError.h, in addition to the following values.</span></span>  
  
|<span data-ttu-id="5f07a-120">반환 코드</span><span class="sxs-lookup"><span data-stu-id="5f07a-120">Return code</span></span>|<span data-ttu-id="5f07a-121">설명</span><span class="sxs-lookup"><span data-stu-id="5f07a-121">Description</span></span>|  
|-----------------|-----------------|  
|<span data-ttu-id="5f07a-122">S_OK</span><span class="sxs-lookup"><span data-stu-id="5f07a-122">S_OK</span></span>|<span data-ttu-id="5f07a-123">메서드가 완료되었습니다.</span><span class="sxs-lookup"><span data-stu-id="5f07a-123">The method completed successfully.</span></span>|  
|<span data-ttu-id="5f07a-124">ERROR_INSUFFICIENT_BUFFER</span><span class="sxs-lookup"><span data-stu-id="5f07a-124">ERROR_INSUFFICIENT_BUFFER</span></span>|<span data-ttu-id="5f07a-125">디렉터리 버퍼가 디렉터리 경로 저장 하기에 충분 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5f07a-125">The directory buffer is not large enough to store the directory path.</span></span><br /><br /> <span data-ttu-id="5f07a-126">또는</span><span class="sxs-lookup"><span data-stu-id="5f07a-126">- or -</span></span><br /><br /> <span data-ttu-id="5f07a-127">버전 버퍼의 버전 문자열을 저장할 만큼 크지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5f07a-127">The version buffer is not large enough to store the version string.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5f07a-128">설명</span><span class="sxs-lookup"><span data-stu-id="5f07a-128">Remarks</span></span>  
 <span data-ttu-id="5f07a-129">`GetRequestedRuntimeInfo` 메서드 최신 컴퓨터에 설치할 필요가 없는 프로세스에 로드 된 버전에 대 한 런타임 정보를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="5f07a-129">The `GetRequestedRuntimeInfo` method returns run-time information about the version loaded into the process, which is not necessarily the latest version installed on the computer.</span></span>  
  
 <span data-ttu-id="5f07a-130">.NET framework 버전 2.0에서 사용 하 여 최신 버전에 대 한 정보를 얻을 수는 `GetRequestedRuntimeInfo` 같이 메서드:</span><span class="sxs-lookup"><span data-stu-id="5f07a-130">In the .NET Framework version 2.0, you can get information about the latest installed version by using the `GetRequestedRuntimeInfo` method as follows:</span></span>  
  
-   <span data-ttu-id="5f07a-131">지정 된 `pExe`, `pwszVersion`, 및 `pConfigurationFile` 매개 변수를 null로 합니다.</span><span class="sxs-lookup"><span data-stu-id="5f07a-131">Specify the `pExe`, `pwszVersion`, and `pConfigurationFile` parameters as null.</span></span>  
  
-   <span data-ttu-id="5f07a-132">RUNTIME_INFO_UPGRADE_VERSION 플래그를 지정 합니다 `RUNTIME_INFO_FLAGS` 열거형을 `runtimeInfoFlags` 매개 변수.</span><span class="sxs-lookup"><span data-stu-id="5f07a-132">Specify the RUNTIME_INFO_UPGRADE_VERSION flag in the `RUNTIME_INFO_FLAGS` enumerations for the `runtimeInfoFlags` parameter.</span></span>  
  
 <span data-ttu-id="5f07a-133">`GetRequestedRuntimeInfo` 메서드는 다음과 같은 상황에서 최신 CLR 버전을 반환 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5f07a-133">The `GetRequestedRuntimeInfo` method does not return the latest CLR version in the following circumstances:</span></span>  
  
-   <span data-ttu-id="5f07a-134">특정 CLR 버전을 로드 하도록 지정 하는 응용 프로그램 구성 파일에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5f07a-134">An application configuration file that specifies loading a particular CLR version exists.</span></span> <span data-ttu-id="5f07a-135">.NET Framework를 사용 하 여 구성 파일에 대 한 null을 지정 하는 경우에는 `pConfigurationFile` 매개 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="5f07a-135">Note that the .NET Framework will use the configuration file even if you specify null for the `pConfigurationFile` parameter.</span></span>  
  
-   <span data-ttu-id="5f07a-136">합니다 [CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) 이전 버전의 CLR 지정 메서드가 호출 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="5f07a-136">The [CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) method was called specifying an earlier CLR version.</span></span>  
  
-   <span data-ttu-id="5f07a-137">이전 버전의 CLR에 대해 컴파일된 응용 프로그램 실행 중입니다.</span><span class="sxs-lookup"><span data-stu-id="5f07a-137">An application that was compiled for an earlier CLR version is currently running.</span></span>  
  
 <span data-ttu-id="5f07a-138">에 대 한 합니다 `runtimeInfoFlags` 매개 변수를 지정할 수 있습니다만 아키텍처 상수 중 하나는 `RUNTIME_INFO_FLAGS` 번 열거형:</span><span class="sxs-lookup"><span data-stu-id="5f07a-138">For the `runtimeInfoFlags` parameter, you can specify only one of the architecture constants of the `RUNTIME_INFO_FLAGS` enumeration at a time:</span></span>  
  
-   <span data-ttu-id="5f07a-139">RUNTIME_INFO_REQUEST_IA64</span><span class="sxs-lookup"><span data-stu-id="5f07a-139">RUNTIME_INFO_REQUEST_IA64</span></span>  
  
-   <span data-ttu-id="5f07a-140">RUNTIME_INFO_REQUEST_AMD64</span><span class="sxs-lookup"><span data-stu-id="5f07a-140">RUNTIME_INFO_REQUEST_AMD64</span></span>  
  
-   <span data-ttu-id="5f07a-141">RUNTIME_INFO_REQUEST_X86</span><span class="sxs-lookup"><span data-stu-id="5f07a-141">RUNTIME_INFO_REQUEST_X86</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5f07a-142">요구 사항</span><span class="sxs-lookup"><span data-stu-id="5f07a-142">Requirements</span></span>  
 <span data-ttu-id="5f07a-143">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="5f07a-143">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5f07a-144">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="5f07a-144">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="5f07a-145">**라이브러리:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="5f07a-145">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="5f07a-146">**.NET Framework 버전:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5f07a-146">**.NET Framework Versions:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5f07a-147">참고자료</span><span class="sxs-lookup"><span data-stu-id="5f07a-147">See also</span></span>
- [<span data-ttu-id="5f07a-148">GetRequestedRuntimeVersion 함수</span><span class="sxs-lookup"><span data-stu-id="5f07a-148">GetRequestedRuntimeVersion Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/getrequestedruntimeversion-function.md)
- [<span data-ttu-id="5f07a-149">GetVersionFromProcess 함수</span><span class="sxs-lookup"><span data-stu-id="5f07a-149">GetVersionFromProcess Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/getversionfromprocess-function.md)
- [<span data-ttu-id="5f07a-150">사용되지 않는 CLR 호스팅 함수</span><span class="sxs-lookup"><span data-stu-id="5f07a-150">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
