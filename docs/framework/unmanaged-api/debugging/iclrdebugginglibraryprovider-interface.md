---
title: ICLRDebuggingLibraryProvider 인터페이스
ms.date: 03/30/2017
api_name:
- ICLRDebuggingLibraryProvider
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICLRDebuggingLibraryProvider
helpviewer_keywords:
- ICLRDebuggingLibraryProvider interface [.NET Framework debugging]
ms.assetid: 67739617-6add-41a9-9de5-a3200c3109ce
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c9d851a31cbbf429f49b9f369ce9bc03fa110b5b
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54731987"
---
# <a name="iclrdebugginglibraryprovider-interface"></a><span data-ttu-id="2cbf7-102">ICLRDebuggingLibraryProvider 인터페이스</span><span class="sxs-lookup"><span data-stu-id="2cbf7-102">ICLRDebuggingLibraryProvider Interface</span></span>
<span data-ttu-id="2cbf7-103">포함 된 [ProvideLibrary 메서드](../../../../docs/framework/unmanaged-api/debugging/iclrdebugginglibraryprovider-providelibrary-method.md) 메서드 라이브러리 공급자 콜백 인터페이스 공용 언어 런타임 버전별 디버깅 라이브러리 있고에 로드 된 요청 수를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="2cbf7-103">Includes the [ProvideLibrary Method](../../../../docs/framework/unmanaged-api/debugging/iclrdebugginglibraryprovider-providelibrary-method.md) method, which gets a library provider callback interface that allows common language runtime version-specific debugging libraries to be located and loaded on demand.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="2cbf7-104">메서드</span><span class="sxs-lookup"><span data-stu-id="2cbf7-104">Methods</span></span>  
  
|<span data-ttu-id="2cbf7-105">메서드</span><span class="sxs-lookup"><span data-stu-id="2cbf7-105">Method</span></span>|<span data-ttu-id="2cbf7-106">설명</span><span class="sxs-lookup"><span data-stu-id="2cbf7-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="2cbf7-107">ProvideLibrary 메서드</span><span class="sxs-lookup"><span data-stu-id="2cbf7-107">ProvideLibrary Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdebugginglibraryprovider-providelibrary-method.md)|<span data-ttu-id="2cbf7-108">디버그 라이브러리를 로드를 사용할 수 있는 모듈에 대 한 핸들을 제공 하기 위해 디버거에서 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2cbf7-108">Allows the debugger to provide a handle to a module which can be used to load a debug library.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="2cbf7-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="2cbf7-109">Requirements</span></span>  
 <span data-ttu-id="2cbf7-110">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="2cbf7-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2cbf7-111">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="2cbf7-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="2cbf7-112">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2cbf7-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2cbf7-113">**.NET Framework 버전:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2cbf7-113">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2cbf7-114">참고자료</span><span class="sxs-lookup"><span data-stu-id="2cbf7-114">See also</span></span>
- [<span data-ttu-id="2cbf7-115">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="2cbf7-115">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="2cbf7-116">디버깅</span><span class="sxs-lookup"><span data-stu-id="2cbf7-116">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
