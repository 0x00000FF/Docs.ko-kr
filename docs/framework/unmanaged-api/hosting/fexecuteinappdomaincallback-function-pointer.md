---
title: FExecuteInAppDomainCallback 함수 포인터
ms.date: 03/30/2017
api_name:
- FExecuteInAppDomainCallback
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- FExecuteInAppDomainCallback
helpviewer_keywords:
- FExecuteInAppDomainCallback function pointer [.NET Framework hosting]
ms.assetid: 2709f18f-3eee-497f-bc33-3ab7a485599b
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e3031ce0eb6f23fdf5e5366d33ff075ea7816b0b
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54649546"
---
# <a name="fexecuteinappdomaincallback-function-pointer"></a><span data-ttu-id="0a6f5-102">FExecuteInAppDomainCallback 함수 포인터</span><span class="sxs-lookup"><span data-stu-id="0a6f5-102">FExecuteInAppDomainCallback Function Pointer</span></span>
<span data-ttu-id="0a6f5-103">CLR (공용 언어 런타임) 관리 되는 코드를 실행 하 여 호출 되는 함수를 가리킵니다.</span><span class="sxs-lookup"><span data-stu-id="0a6f5-103">Points to a function that is called by the common language runtime (CLR) to execute managed code.</span></span>  
  
 <span data-ttu-id="0a6f5-104">이 함수 포인터에서 사용 중단에 [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)]합니다.</span><span class="sxs-lookup"><span data-stu-id="0a6f5-104">This function pointer has been deprecated in the [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0a6f5-105">구문</span><span class="sxs-lookup"><span data-stu-id="0a6f5-105">Syntax</span></span>  
  
```  
typedef HRESULT (__stdcall *FExecuteInAppDomainCallback) (  
    [in] void  *cookie  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="0a6f5-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="0a6f5-106">Parameters</span></span>  
 `cookie`  
 <span data-ttu-id="0a6f5-107">[in] 관리 되는 코드를 실행할 수 있는 불투명 호출자에 게 할당 된 메모리에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="0a6f5-107">[in] A pointer to opaque caller-allocated memory that contains the managed code to be executed.</span></span>  
  
 <span data-ttu-id="0a6f5-108">할당 및이 메모리의 수명을 (CLR) 호출자에 의해 제어 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0a6f5-108">The allocation and lifetime of this memory are controlled by the caller (that is, the CLR).</span></span> <span data-ttu-id="0a6f5-109">CLR 관리 되는 힙 메모리 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="0a6f5-109">This is not CLR managed-heap memory.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0a6f5-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="0a6f5-110">Requirements</span></span>  
 <span data-ttu-id="0a6f5-111">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="0a6f5-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0a6f5-112">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="0a6f5-112">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="0a6f5-113">**라이브러리:** MSCorWks.dll</span><span class="sxs-lookup"><span data-stu-id="0a6f5-113">**Library:** MSCorWks.dll</span></span>  
  
 <span data-ttu-id="0a6f5-114">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0a6f5-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0a6f5-115">참고자료</span><span class="sxs-lookup"><span data-stu-id="0a6f5-115">See also</span></span>
- [<span data-ttu-id="0a6f5-116">사용되지 않는 CLR 호스팅 함수</span><span class="sxs-lookup"><span data-stu-id="0a6f5-116">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
