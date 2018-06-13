---
title: ICorDebugManagedCallback::UnloadAssembly 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback.UnloadAssembly
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback::UnloadAssembly
helpviewer_keywords:
- ICorDebugManagedCallback::UnloadAssembly method [.NET Framework debugging]
- UnloadAssembly method [.NET Framework debugging]
ms.assetid: 6734321c-c8a9-401f-a558-cad715ec4a77
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a892012e872dcf44512adbe0d6890812d84ed899
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33412596"
---
# <a name="icordebugmanagedcallbackunloadassembly-method"></a><span data-ttu-id="46be0-102">ICorDebugManagedCallback::UnloadAssembly 메서드</span><span class="sxs-lookup"><span data-stu-id="46be0-102">ICorDebugManagedCallback::UnloadAssembly Method</span></span>
<span data-ttu-id="46be0-103">공용 언어 런타임 어셈블리 로드 되었음을 디버거에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="46be0-103">Notifies the debugger that a common language runtime assembly has been unloaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="46be0-104">구문</span><span class="sxs-lookup"><span data-stu-id="46be0-104">Syntax</span></span>  
  
```  
HRESULT UnloadAssembly (  
    [in] IcorDebugAppDomain  *pAppDomain,  
    [in] ICorDebugAssembly   *pAssembly  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="46be0-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="46be0-105">Parameters</span></span>  
 `pAppDomain`  
 <span data-ttu-id="46be0-106">[in] 어셈블리를 포함 하는 응용 프로그램 도메인을 나타내는 ICorDebugAppDomain 개체에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="46be0-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain that contained the assembly.</span></span>  
  
 `pAssembly`  
 <span data-ttu-id="46be0-107">[in] 어셈블리를 나타내는 ICorDebugAssembly 개체에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="46be0-107">[in] A pointer to an ICorDebugAssembly object that represents the assembly.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="46be0-108">설명</span><span class="sxs-lookup"><span data-stu-id="46be0-108">Remarks</span></span>  
 <span data-ttu-id="46be0-109">이 콜백은 후 어셈블리를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="46be0-109">The assembly should not be used after this callback.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="46be0-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="46be0-110">Requirements</span></span>  
 <span data-ttu-id="46be0-111">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="46be0-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="46be0-112">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="46be0-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="46be0-113">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="46be0-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="46be0-114">**.NET framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="46be0-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="46be0-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="46be0-115">See Also</span></span>  
 [<span data-ttu-id="46be0-116">LoadAssembly 메서드</span><span class="sxs-lookup"><span data-stu-id="46be0-116">LoadAssembly Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-loadassembly-method.md)  
 [<span data-ttu-id="46be0-117">ICorDebugManagedCallback 인터페이스</span><span class="sxs-lookup"><span data-stu-id="46be0-117">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
