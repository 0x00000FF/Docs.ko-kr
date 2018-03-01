---
title: "CorExitProcess 함수"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- CorExitProcess
api_location:
- mscoree.dll
- clr.dll
- mscorwks.dll
- mscoreei.dll
api_type:
- DLLExport
f1_keywords:
- CorExitProcess
helpviewer_keywords:
- CorExitProcess function [.NET Framework hosting]
ms.assetid: a5cab4c6-990e-47f3-8798-cf422b791015
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 560f63c131ad336a3ff4b4edec0aed2b58d33ba5
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="corexitprocess-function"></a><span data-ttu-id="e458c-102">CorExitProcess 함수</span><span class="sxs-lookup"><span data-stu-id="e458c-102">CorExitProcess Function</span></span>
<span data-ttu-id="e458c-103">현재 관리 되지 않는 프로세스를 종료합니다.</span><span class="sxs-lookup"><span data-stu-id="e458c-103">Shuts down the current unmanaged process.</span></span>  
  
 <span data-ttu-id="e458c-104">이 함수에 더 이상 사용 되지는 [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)]합니다.</span><span class="sxs-lookup"><span data-stu-id="e458c-104">This function has been deprecated in the [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span></span> <span data-ttu-id="e458c-105">사용 하 여 [iclrmetahost:: Exitprocess](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-exitprocess-method.md) 메서드 대신 합니다.</span><span class="sxs-lookup"><span data-stu-id="e458c-105">Use the [ICLRMetaHost::ExitProcess](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-exitprocess-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e458c-106">구문</span><span class="sxs-lookup"><span data-stu-id="e458c-106">Syntax</span></span>  
  
```  
void STDMETHODCALLTYPE CorExitProcess (   
  int  exitCode  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="e458c-107">매개 변수</span><span class="sxs-lookup"><span data-stu-id="e458c-107">Parameters</span></span>  
 `exitCode`  
 <span data-ttu-id="e458c-108">프로세스 종료 코드를 지정 하는 정수입니다.</span><span class="sxs-lookup"><span data-stu-id="e458c-108">An integer that specifies the process exit code.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e458c-109">설명</span><span class="sxs-lookup"><span data-stu-id="e458c-109">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e458c-110">부터는 [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)], `CorExitProcess` 레거시 Api가 바인딩된 런타임 뿐 아니라 프로세스의 모든 시작된 된 런타임을 종료 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e458c-110">Beginning with the [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)], `CorExitProcess` exits every started runtime in the process, not just the runtime to which the legacy APIs have been bound.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e458c-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="e458c-111">Requirements</span></span>  
 <span data-ttu-id="e458c-112">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="e458c-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e458c-113">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="e458c-113">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="e458c-114">**라이브러리:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="e458c-114">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="e458c-115">**.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e458c-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e458c-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="e458c-116">See Also</span></span>  
 [<span data-ttu-id="e458c-117">사용되지 않는 CLR 호스팅 함수</span><span class="sxs-lookup"><span data-stu-id="e458c-117">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
