---
title: ICorThreadpool::CorCreateTimer 메서드
ms.date: 03/30/2017
api_name:
- ICorThreadpool.CorCreateTimer
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorCreateTimer
helpviewer_keywords:
- CorCreateTimer method [.NET Framework hosting]
- ICorThreadpool::CorCreateTimer method [.NET Framework hosting]
ms.assetid: 0d56ef25-30f1-4499-8a1f-76e7654ec614
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7dfa1dd15f38263ffdfef594ab030867b3fed1de
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33436779"
---
# <a name="icorthreadpoolcorcreatetimer-method"></a><span data-ttu-id="63181-102">ICorThreadpool::CorCreateTimer 메서드</span><span class="sxs-lookup"><span data-stu-id="63181-102">ICorThreadpool::CorCreateTimer Method</span></span>
<span data-ttu-id="63181-103">이 메서드는 .NET Framework 인프라를 지원하며 사용자 코드에서 직접 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="63181-103">This method supports the .NET Framework infrastructure and is not intended to be used directly from your code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="63181-104">구문</span><span class="sxs-lookup"><span data-stu-id="63181-104">Syntax</span></span>  
  
```  
HRESULT CorCreateTimer (  
    [in]  HANDLE*             phNewTimer,  
    [in]  WAITORTIMERCALLBACK Callback,  
    [in]  PVOID               Parameter,  
    [in]  DWORD               DueTime,  
    [in]  DWORD               Period,  
    [out] BOOL*               result  
);  
```  
  
## <a name="requirements"></a><span data-ttu-id="63181-105">요구 사항</span><span class="sxs-lookup"><span data-stu-id="63181-105">Requirements</span></span>  
 <span data-ttu-id="63181-106">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="63181-106">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="63181-107">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="63181-107">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="63181-108">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="63181-108">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="63181-109">**.NET framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="63181-109">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="63181-110">참고 항목</span><span class="sxs-lookup"><span data-stu-id="63181-110">See Also</span></span>  
 [<span data-ttu-id="63181-111">ICorThreadpool 인터페이스</span><span class="sxs-lookup"><span data-stu-id="63181-111">ICorThreadpool Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorthreadpool-interface.md)
