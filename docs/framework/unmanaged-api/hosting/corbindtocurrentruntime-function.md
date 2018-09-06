---
title: CorBindToCurrentRuntime 함수
ms.date: 03/30/2017
api_name:
- CorBindToCurrentRuntime
api_location:
- mscoree.dll
- mscoreei.dll
api_type:
- HeaderDef
f1_keywords:
- CorBindToCurrentRuntime
helpviewer_keywords:
- CorBindToCurrentRuntime function [.NET Framework hosting]
ms.assetid: 6105c13e-d9cd-44d2-a95a-924e042830c7
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 021f2b7a720c2190d56bdb2b35214c581a7b5f56
ms.sourcegitcommit: a885cc8c3e444ca6471348893d5373c6e9e49a47
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/06/2018
ms.locfileid: "43872142"
---
# <a name="corbindtocurrentruntime-function"></a><span data-ttu-id="3bc14-102">CorBindToCurrentRuntime 함수</span><span class="sxs-lookup"><span data-stu-id="3bc14-102">CorBindToCurrentRuntime Function</span></span>
<span data-ttu-id="3bc14-103">XML 파일에 저장 된 버전 정보를 사용 하 여 프로세스에는 CLR (공용 언어 런타임)을 로드 합니다.</span><span class="sxs-lookup"><span data-stu-id="3bc14-103">Loads the common language runtime (CLR) into a process by using version information stored in an XML file.</span></span> <span data-ttu-id="3bc14-104">XML 파일의 형식은 표준 응용 프로그램 구성 파일을 따라 모델링 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3bc14-104">The format of the XML file is modeled after the standard application configuration file.</span></span> <span data-ttu-id="3bc14-105">구성 파일에 대한 자세한 내용은 [구성 파일 스키마](../../../../docs/framework/configure-apps/file-schema/index.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="3bc14-105">For more information about configuration files, see [Configuration File Schema](../../../../docs/framework/configure-apps/file-schema/index.md).</span></span>  
  
 <span data-ttu-id="3bc14-106">이 함수에서 사용 중단에 [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)]합니다.</span><span class="sxs-lookup"><span data-stu-id="3bc14-106">This function has been deprecated in the [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span></span> <span data-ttu-id="3bc14-107">참조 [공용 언어 런타임을 프로세스로 로드](https://msdn.microsoft.com/library/1e2d6dc1-6aab-43e2-bbc0-aae40756d24f)합니다.</span><span class="sxs-lookup"><span data-stu-id="3bc14-107">See [Loading the Common Language Runtime into a Process](https://msdn.microsoft.com/library/1e2d6dc1-6aab-43e2-bbc0-aae40756d24f).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3bc14-108">구문</span><span class="sxs-lookup"><span data-stu-id="3bc14-108">Syntax</span></span>  
  
```  
HRESULT CorBindToCurrentRuntime (  
    [in]  LPCWSTR   pwszFileName,  
    [in]  REFCLSID  rclsid,  
    [in]  REFIID    riid,  
    [out] LPVOID    *ppv  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="3bc14-109">매개 변수</span><span class="sxs-lookup"><span data-stu-id="3bc14-109">Parameters</span></span>  
 `pwszFileName`  
 <span data-ttu-id="3bc14-110">[in] 로드 하기 위해 CLR의 버전을 지정 하는 응용 프로그램 구성 파일의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="3bc14-110">[in] The name of an application configuration file that specifies the version of the CLR to load.</span></span> <span data-ttu-id="3bc14-111">파일 이름이 정규화 되지 않은 경우 호출을 수행 하는 실행 파일과 동일한 디렉터리에 있는 간주 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3bc14-111">If the file name is not fully qualified, it is assumed to be in the same directory as the executable making the call.</span></span>  
  
 <span data-ttu-id="3bc14-112">로드할 런타임 버전을 version 특성에 의해 설명 됩니다 합니다 [ \<requiredRuntime >](../../../../docs/framework/configure-apps/file-schema/startup/requiredruntime-element.md) 구성 파일의 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="3bc14-112">The version of the runtime to be loaded is described by the version attribute in the [\<requiredRuntime>](../../../../docs/framework/configure-apps/file-schema/startup/requiredruntime-element.md) element of the configuration file.</span></span>  
  
 <span data-ttu-id="3bc14-113">버전이 지정 된 경우 또는 경우는 `<requiredRuntime>` 요소를 찾을 수 없습니다, 최신 버전의 컴퓨터에 설치 된 CLR 로드 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3bc14-113">If no version is specified, or if the `<requiredRuntime>` element cannot be found, the latest version of the CLR that is installed on the machine is loaded.</span></span>  
  
 `rclsid`  
 <span data-ttu-id="3bc14-114">[in] 합니다 `CLSID` 중 하나를 구현 하는 coclass의 합니다 [ICorRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md) 또는 [ICLRRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md) 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="3bc14-114">[in] The `CLSID` of the coclass that implements either the [ICorRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md) or the [ICLRRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md) interface.</span></span> <span data-ttu-id="3bc14-115">지원 되는 값은 CLSID_CorRuntimeHost CLSID_CLRRuntimeHost입니다.</span><span class="sxs-lookup"><span data-stu-id="3bc14-115">Supported values are CLSID_CorRuntimeHost or CLSID_CLRRuntimeHost.</span></span>  
  
 `riid`  
 <span data-ttu-id="3bc14-116">[in] `IID` 요청 하는 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="3bc14-116">[in] The `IID` of the interface you are requesting.</span></span> <span data-ttu-id="3bc14-117">지원 되는 값은 IID_ICorRuntimeHost IID_ICLRRuntimeHost입니다.</span><span class="sxs-lookup"><span data-stu-id="3bc14-117">Supported values are IID_ICorRuntimeHost or IID_ICLRRuntimeHost.</span></span>  
  
 `ppv`  
 <span data-ttu-id="3bc14-118">[out] 반환 된 인터페이스 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="3bc14-118">[out] The returned interface pointer.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3bc14-119">요구 사항</span><span class="sxs-lookup"><span data-stu-id="3bc14-119">Requirements</span></span>  
 <span data-ttu-id="3bc14-120">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="3bc14-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3bc14-121">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="3bc14-121">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="3bc14-122">**라이브러리:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="3bc14-122">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="3bc14-123">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3bc14-123">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3bc14-124">참고 항목</span><span class="sxs-lookup"><span data-stu-id="3bc14-124">See Also</span></span>  
 [<span data-ttu-id="3bc14-125">CorBindToRuntime 함수</span><span class="sxs-lookup"><span data-stu-id="3bc14-125">CorBindToRuntime Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntime-function.md)  
 [<span data-ttu-id="3bc14-126">CorBindToRuntimeByCfg 함수</span><span class="sxs-lookup"><span data-stu-id="3bc14-126">CorBindToRuntimeByCfg Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimebycfg-function.md)  
 [<span data-ttu-id="3bc14-127">CorBindToRuntimeEx 함수</span><span class="sxs-lookup"><span data-stu-id="3bc14-127">CorBindToRuntimeEx Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md)  
 [<span data-ttu-id="3bc14-128">CorBindToRuntimeHost 함수</span><span class="sxs-lookup"><span data-stu-id="3bc14-128">CorBindToRuntimeHost Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimehost-function.md)  
 [<span data-ttu-id="3bc14-129">ICorRuntimeHost 인터페이스</span><span class="sxs-lookup"><span data-stu-id="3bc14-129">ICorRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)  
 [<span data-ttu-id="3bc14-130">사용되지 않는 CLR 호스팅 함수</span><span class="sxs-lookup"><span data-stu-id="3bc14-130">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
