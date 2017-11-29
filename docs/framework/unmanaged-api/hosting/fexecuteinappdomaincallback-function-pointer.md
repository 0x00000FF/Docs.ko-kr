---
title: "FExecuteInAppDomainCallback 함수 포인터"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: FExecuteInAppDomainCallback
api_location: mscoree.dll
api_type: COM
f1_keywords: FExecuteInAppDomainCallback
helpviewer_keywords: FExecuteInAppDomainCallback function pointer [.NET Framework hosting]
ms.assetid: 2709f18f-3eee-497f-bc33-3ab7a485599b
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 5e6c04a964b50357dc3687f3faf5710505bae364
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="fexecuteinappdomaincallback-function-pointer"></a><span data-ttu-id="d8594-102">FExecuteInAppDomainCallback 함수 포인터</span><span class="sxs-lookup"><span data-stu-id="d8594-102">FExecuteInAppDomainCallback Function Pointer</span></span>
<span data-ttu-id="d8594-103">관리 코드를 실행 하기 위해 공용 언어 런타임 (CLR)에 의해 호출 되는 함수를 가리킵니다.</span><span class="sxs-lookup"><span data-stu-id="d8594-103">Points to a function that is called by the common language runtime (CLR) to execute managed code.</span></span>  
  
 <span data-ttu-id="d8594-104">이 함수 포인터에서 더 이상 사용 되지는 [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)]합니다.</span><span class="sxs-lookup"><span data-stu-id="d8594-104">This function pointer has been deprecated in the [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d8594-105">구문</span><span class="sxs-lookup"><span data-stu-id="d8594-105">Syntax</span></span>  
  
```  
typedef HRESULT (__stdcall *FExecuteInAppDomainCallback) (  
    [in] void  *cookie  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="d8594-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="d8594-106">Parameters</span></span>  
 `cookie`  
 <span data-ttu-id="d8594-107">[in] 관리 되는 코드를 실행할 수 있는 불투명 호출자에 게 할당 된 메모리에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="d8594-107">[in] A pointer to opaque caller-allocated memory that contains the managed code to be executed.</span></span>  
  
 <span data-ttu-id="d8594-108">할당 및이 메모리의 수명 (CLR) 호출자에 의해 제어 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d8594-108">The allocation and lifetime of this memory are controlled by the caller (that is, the CLR).</span></span> <span data-ttu-id="d8594-109">CLR 관리 되는 힙 메모리 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="d8594-109">This is not CLR managed-heap memory.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d8594-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="d8594-110">Requirements</span></span>  
 <span data-ttu-id="d8594-111">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="d8594-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d8594-112">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="d8594-112">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="d8594-113">**라이브러리:** MSCorWks.dll</span><span class="sxs-lookup"><span data-stu-id="d8594-113">**Library:** MSCorWks.dll</span></span>  
  
 <span data-ttu-id="d8594-114">**.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d8594-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d8594-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d8594-115">See Also</span></span>  
 [<span data-ttu-id="d8594-116">사용 되지 않는 CLR 호스팅 함수</span><span class="sxs-lookup"><span data-stu-id="d8594-116">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
