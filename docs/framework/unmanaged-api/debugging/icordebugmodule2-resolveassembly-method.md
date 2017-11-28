---
title: "ICorDebugModule2::ResolveAssembly 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugModule2.ResolveAssembly
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugModule2::ResolveAssembly
helpviewer_keywords:
- ICorDebugModule2::ResolveAssembly method [.NET Framework debugging]
- ResolveAssembly method [.NET Framework debugging]
ms.assetid: ddf9085c-7161-44bd-9609-cd2732b9009f
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 37ddb0e8871d9ec5f8eed4f00d81098feafb01de
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugmodule2resolveassembly-method"></a><span data-ttu-id="e9b74-102">ICorDebugModule2::ResolveAssembly 메서드</span><span class="sxs-lookup"><span data-stu-id="e9b74-102">ICorDebugModule2::ResolveAssembly Method</span></span>
<span data-ttu-id="e9b74-103">지정한 메타 데이터 토큰에서 참조 하는 어셈블리를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="e9b74-103">Resolves the assembly referenced by the specified metadata token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e9b74-104">구문</span><span class="sxs-lookup"><span data-stu-id="e9b74-104">Syntax</span></span>  
  
```  
HRESULT ResolveAssembly (  
    [in]  mdToken             tkAssemblyRef,  
    [out] ICorDebugAssembly   **ppAssembly  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="e9b74-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="e9b74-105">Parameters</span></span>  
 `tkAsemblyRef`  
 <span data-ttu-id="e9b74-106">[in] `mdToken` 어셈블리를 참조 하는 값입니다.</span><span class="sxs-lookup"><span data-stu-id="e9b74-106">[in] An `mdToken` value that references the assembly.</span></span>  
  
 `ppAssembly`  
 <span data-ttu-id="e9b74-107">[out] 어셈블리를 나타내는 ICorDebugAssembly 개체의 주소에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="e9b74-107">[out] A pointer to the address of an ICorDebugAssembly object that represents the assembly.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e9b74-108">설명</span><span class="sxs-lookup"><span data-stu-id="e9b74-108">Remarks</span></span>  
 <span data-ttu-id="e9b74-109">어셈블리가 아직 로드 되지 않은 경우 경우 `ResolveAssembly` 호출 되는 HRESULT CORDBG_E_CANNOT_RESOLVE_ASSEMBLY의 값이 반환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e9b74-109">If the assembly is not already loaded when `ResolveAssembly` is called, an HRESULT value of CORDBG_E_CANNOT_RESOLVE_ASSEMBLY is returned.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e9b74-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="e9b74-110">Requirements</span></span>  
 <span data-ttu-id="e9b74-111">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="e9b74-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e9b74-112">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e9b74-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e9b74-113">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e9b74-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e9b74-114">**.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e9b74-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
