---
title: ICLRDebugging 인터페이스
ms.date: 03/30/2017
api_name:
- ICLRDebugging
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICLRDebugging
helpviewer_keywords:
- ICLRDebugging interface [.NET Framework debugging]
ms.assetid: 429d8fce-b1b1-49d7-895c-28c1c1aa2dbd
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a0357b5b072216173546a1aafc03e1a347c48c57
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54730051"
---
# <a name="iclrdebugging-interface"></a><span data-ttu-id="71c16-102">ICLRDebugging 인터페이스</span><span class="sxs-lookup"><span data-stu-id="71c16-102">ICLRDebugging Interface</span></span>
<span data-ttu-id="71c16-103">디버깅을 위해 모듈을 로드 및 언로드하는 작업을 처리하는 메서드를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="71c16-103">Provides methods that handle loading and unloading modules for debugging.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="71c16-104">메서드</span><span class="sxs-lookup"><span data-stu-id="71c16-104">Methods</span></span>  
  
|<span data-ttu-id="71c16-105">메서드</span><span class="sxs-lookup"><span data-stu-id="71c16-105">Method</span></span>|<span data-ttu-id="71c16-106">설명</span><span class="sxs-lookup"><span data-stu-id="71c16-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="71c16-107">OpenVirtualProcess 메서드</span><span class="sxs-lookup"><span data-stu-id="71c16-107">OpenVirtualProcess Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdebugging-openvirtualprocess-method.md)|<span data-ttu-id="71c16-108">프로세스에 로드 된 공용 언어 런타임 (CLR) 모듈에 해당 하는 "ICorDebugProcess" 인터페이스를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="71c16-108">Gets the "ICorDebugProcess" interface that corresponds to a common language runtime (CLR) module loaded in the process.</span></span>|  
|[<span data-ttu-id="71c16-109">CanUnloadNow 메서드</span><span class="sxs-lookup"><span data-stu-id="71c16-109">CanUnloadNow Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdebugging-canunloadnow-method.md)|<span data-ttu-id="71c16-110">라이브러리에서 제공 하는 여부를 확인 한 [ICLRDebuggingLibraryProvider](../../../../docs/framework/unmanaged-api/debugging/iclrdebugginglibraryprovider-interface.md) 인터페이스 사용에서 되었거나 언로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="71c16-110">Determines whether a library that was provided by an [ICLRDebuggingLibraryProvider](../../../../docs/framework/unmanaged-api/debugging/iclrdebugginglibraryprovider-interface.md) interface is still in use or can be unloaded.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="71c16-111">설명</span><span class="sxs-lookup"><span data-stu-id="71c16-111">Remarks</span></span>  
 <span data-ttu-id="71c16-112">인스턴스를 가져올 수는 `ICLRDebugging` 인터페이스를 사용 하 여 합니다 [CLRCreateInstance](../../../../docs/framework/unmanaged-api/hosting/clrcreateinstance-function.md) 함수입니다.</span><span class="sxs-lookup"><span data-stu-id="71c16-112">You can obtain an instance of the `ICLRDebugging` interface by using the [CLRCreateInstance](../../../../docs/framework/unmanaged-api/hosting/clrcreateinstance-function.md) function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="71c16-113">요구 사항</span><span class="sxs-lookup"><span data-stu-id="71c16-113">Requirements</span></span>  
 <span data-ttu-id="71c16-114">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="71c16-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="71c16-115">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="71c16-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="71c16-116">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="71c16-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="71c16-117">**.NET Framework 버전:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="71c16-117">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="71c16-118">참고자료</span><span class="sxs-lookup"><span data-stu-id="71c16-118">See also</span></span>
- [<span data-ttu-id="71c16-119">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="71c16-119">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="71c16-120">디버깅</span><span class="sxs-lookup"><span data-stu-id="71c16-120">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
