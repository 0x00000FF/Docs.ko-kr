---
title: GetRequestedRuntimeVersion 함수
ms.date: 03/30/2017
api_name:
- GetRequestedRuntimeVersion
api_location:
- mscoree.dll
- mscoreei.dll
api_type:
- DLLExport
f1_keywords:
- GetRequestedRuntimeVersion
helpviewer_keywords:
- GetRequestedRuntimeVersion function [.NET Framework hosting]
ms.assetid: 82f596a4-483d-4509-b0c5-a84c53c3da1b
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 1ee737f4c6d34e77996f5ba08ce4d84132a99238
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59207333"
---
# <a name="getrequestedruntimeversion-function"></a><span data-ttu-id="95e13-102">GetRequestedRuntimeVersion 함수</span><span class="sxs-lookup"><span data-stu-id="95e13-102">GetRequestedRuntimeVersion Function</span></span>
<span data-ttu-id="95e13-103">지정된 된 응용 프로그램에서 요청한 공용 언어 런타임 (CLR)의 버전 번호를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="95e13-103">Gets the version number of the common language runtime (CLR) requested by the specified application.</span></span> <span data-ttu-id="95e13-104">해당 버전이 설치 되지 않은 경우 요청 된 버전 보다 먼저 설치 되는 최신 버전을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="95e13-104">If that version is not installed, gets the most recent version that is installed before the requested version.</span></span>  
  
 <span data-ttu-id="95e13-105">이 함수에서 사용 중단에 [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)]합니다.</span><span class="sxs-lookup"><span data-stu-id="95e13-105">This function has been deprecated in the [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="95e13-106">구문</span><span class="sxs-lookup"><span data-stu-id="95e13-106">Syntax</span></span>  
  
```  
HRESULT GetRequestedRuntimeVersion (  
    [in]  LPWSTR  pExe,   
    [out] LPWSTR  pVersion,   
    [in]  DWORD   cchBuffer,   
    [out] DWORD  *pdwLength  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="95e13-107">매개 변수</span><span class="sxs-lookup"><span data-stu-id="95e13-107">Parameters</span></span>  
 `pExe`  
 <span data-ttu-id="95e13-108">[in] 응용 프로그램의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="95e13-108">[in] The name of the application.</span></span>  
  
 `pVersion`  
 <span data-ttu-id="95e13-109">[out] 성공적으로 완료 되는 버전 번호 문자열을 포함 하는 버퍼입니다.</span><span class="sxs-lookup"><span data-stu-id="95e13-109">[out] A buffer that contains the version number string upon successful completion.</span></span>  
  
 `cchBuffer`  
 <span data-ttu-id="95e13-110">[in] 버전 버퍼의 길이입니다.</span><span class="sxs-lookup"><span data-stu-id="95e13-110">[in] The length of the version buffer.</span></span>  
  
 `pdwLength`  
 <span data-ttu-id="95e13-111">[out] 버전 번호 문자열의 길이에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="95e13-111">[out] A pointer to the length of the version number string.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="95e13-112">반환 값</span><span class="sxs-lookup"><span data-stu-id="95e13-112">Return Value</span></span>  
 <span data-ttu-id="95e13-113">이 메서드는 다음 값 외에도 WinError.h에 정의 된 대로 표준 구성 요소 개체 모델 (COM) 오류 코드를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="95e13-113">This method returns standard Component Object Model (COM) error codes, as defined in WinError.h, in addition to the following values.</span></span>  
  
|<span data-ttu-id="95e13-114">반환 코드</span><span class="sxs-lookup"><span data-stu-id="95e13-114">Return code</span></span>|<span data-ttu-id="95e13-115">설명</span><span class="sxs-lookup"><span data-stu-id="95e13-115">Description</span></span>|  
|-----------------|-----------------|  
|<span data-ttu-id="95e13-116">S_OK</span><span class="sxs-lookup"><span data-stu-id="95e13-116">S_OK</span></span>|<span data-ttu-id="95e13-117">메서드가 완료되었습니다.</span><span class="sxs-lookup"><span data-stu-id="95e13-117">The method completed successfully.</span></span>|  
|<span data-ttu-id="95e13-118">ERROR_INSUFFICIENT_BUFFER</span><span class="sxs-lookup"><span data-stu-id="95e13-118">ERROR_INSUFFICIENT_BUFFER</span></span>|<span data-ttu-id="95e13-119">버전 버퍼의 버전 문자열을 저장할 만큼 크지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="95e13-119">The version buffer is not large enough to store the version string.</span></span>|  
|<span data-ttu-id="95e13-120">E_POINTER</span><span class="sxs-lookup"><span data-stu-id="95e13-120">E_POINTER</span></span>|`pdwLength` <span data-ttu-id="95e13-121">null입니다.</span><span class="sxs-lookup"><span data-stu-id="95e13-121">is null.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="95e13-122">요구 사항</span><span class="sxs-lookup"><span data-stu-id="95e13-122">Requirements</span></span>  
 <span data-ttu-id="95e13-123">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="95e13-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="95e13-124">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="95e13-124">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="95e13-125">**라이브러리:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="95e13-125">**Library:** MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="95e13-126">.NET Framework 버전:</span><span class="sxs-lookup"><span data-stu-id="95e13-126">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="95e13-127">참고자료</span><span class="sxs-lookup"><span data-stu-id="95e13-127">See also</span></span>

- [<span data-ttu-id="95e13-128">GetRequestedRuntimeInfo 함수</span><span class="sxs-lookup"><span data-stu-id="95e13-128">GetRequestedRuntimeInfo Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/getrequestedruntimeinfo-function.md)
- [<span data-ttu-id="95e13-129">GetVersionFromProcess 함수</span><span class="sxs-lookup"><span data-stu-id="95e13-129">GetVersionFromProcess Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/getversionfromprocess-function.md)
- [<span data-ttu-id="95e13-130">사용되지 않는 CLR 호스팅 함수</span><span class="sxs-lookup"><span data-stu-id="95e13-130">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
