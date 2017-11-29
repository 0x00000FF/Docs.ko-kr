---
title: "ICorRuntimeHost::SwitchOutLogicalThreadState 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorRuntimeHost.SwitchOutLogicalThreadState
api_location: mscoree.dll
api_type: COM
f1_keywords: ICorRuntimeHost::SwitchOutLogicalThreadState
helpviewer_keywords:
- ICorRuntimeHost::SwitchOutLogicalThreadState method [.NET Framework hosting]
- SwitchOutLogicalThreadState method [.NET Framework hosting]
ms.assetid: e1968f0b-2675-4dc2-8507-46164e1df154
topic_type: apiref
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 9eed11dd0a5ebd30952946f640957e9960485524
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="icorruntimehostswitchoutlogicalthreadstate-method"></a><span data-ttu-id="83477-102">ICorRuntimeHost::SwitchOutLogicalThreadState 메서드</span><span class="sxs-lookup"><span data-stu-id="83477-102">ICorRuntimeHost::SwitchOutLogicalThreadState Method</span></span>
<span data-ttu-id="83477-103">이 메서드는 .NET Framework 인프라를 지원하며 사용자 코드에서 직접 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="83477-103">This method supports the .NET Framework infrastructure and is not intended to be used directly from your code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="83477-104">구문</span><span class="sxs-lookup"><span data-stu-id="83477-104">Syntax</span></span>  
  
```  
HRESULT SwitchOutLogicalThreadState(  
    [out] DWORD **pFiberCookie  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="83477-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="83477-105">Parameters</span></span>  
 `pFiberCookie`  
 <span data-ttu-id="83477-106">[out] 스위치 아웃 되 고 파이버를 나타내는 쿠키입니다.</span><span class="sxs-lookup"><span data-stu-id="83477-106">[out] Cookie that indicates the fiber being switched out.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="83477-107">요구 사항</span><span class="sxs-lookup"><span data-stu-id="83477-107">Requirements</span></span>  
 <span data-ttu-id="83477-108">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="83477-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="83477-109">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="83477-109">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="83477-110">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="83477-110">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="83477-111">**.NET framework 버전:** 1.0, 1.1</span><span class="sxs-lookup"><span data-stu-id="83477-111">**.NET Framework Version:** 1.0, 1.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="83477-112">참고 항목</span><span class="sxs-lookup"><span data-stu-id="83477-112">See Also</span></span>  
 [<span data-ttu-id="83477-113">ICorRuntimeHost 인터페이스</span><span class="sxs-lookup"><span data-stu-id="83477-113">ICorRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)
